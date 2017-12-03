---
title: "Úprava DataView"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 697a3991-b660-4a5a-8a54-1a2304ff158e
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0a8478e9b21c6c2abdc02677305e468109e7b9fe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="modifying-dataviews"></a><span data-ttu-id="74733-102">Úprava DataView</span><span class="sxs-lookup"><span data-stu-id="74733-102">Modifying DataViews</span></span>
<span data-ttu-id="74733-103">Můžete použít <xref:System.Data.DataView> Pokud chcete přidat, odstranit ani změnit řádky dat v podkladové tabulce.</span><span class="sxs-lookup"><span data-stu-id="74733-103">You can use the <xref:System.Data.DataView> to add, delete, or modify rows of data in the underlying table.</span></span> <span data-ttu-id="74733-104">Možnost používat **DataView** změnit data v základní tabulce je řízeno nastavení jedné z vlastností tři logické **DataView**.</span><span class="sxs-lookup"><span data-stu-id="74733-104">The ability to use the **DataView** to modify data in the underlying table is controlled by setting one of three Boolean properties of the **DataView**.</span></span> <span data-ttu-id="74733-105">Tyto vlastnosti jsou <xref:System.Data.DataView.AllowNew%2A>, <xref:System.Data.DataView.AllowEdit%2A>, a <xref:System.Data.DataView.AllowDelete%2A>.</span><span class="sxs-lookup"><span data-stu-id="74733-105">These properties are <xref:System.Data.DataView.AllowNew%2A>, <xref:System.Data.DataView.AllowEdit%2A>, and <xref:System.Data.DataView.AllowDelete%2A>.</span></span> <span data-ttu-id="74733-106">Jsou nastaveny na **true** ve výchozím nastavení.</span><span class="sxs-lookup"><span data-stu-id="74733-106">They are set to **true** by default.</span></span>  
  
 <span data-ttu-id="74733-107">Pokud **AllowNew** je **true**, můžete použít <xref:System.Data.DataView.AddNew%2A> metodu **DataView** pro vytvoření nového <xref:System.Data.DataRowView>.</span><span class="sxs-lookup"><span data-stu-id="74733-107">If **AllowNew** is **true**, you can use the <xref:System.Data.DataView.AddNew%2A> method of the **DataView** to create a new <xref:System.Data.DataRowView>.</span></span> <span data-ttu-id="74733-108">Všimněte si, že nový řádek není ve skutečnosti přidán do základní <xref:System.Data.DataTable> dokud <xref:System.Data.DataRowView.EndEdit%2A> metodu **DataRowView** je volána.</span><span class="sxs-lookup"><span data-stu-id="74733-108">Note that a new row is not actually added to the underlying <xref:System.Data.DataTable> until the <xref:System.Data.DataRowView.EndEdit%2A> method of the **DataRowView** is called.</span></span> <span data-ttu-id="74733-109">Pokud <xref:System.Data.DataRowView.CancelEdit%2A> metodu **DataRowView** je volána, budou zahozeny nový řádek.</span><span class="sxs-lookup"><span data-stu-id="74733-109">If the <xref:System.Data.DataRowView.CancelEdit%2A> method of the **DataRowView** is called, the new row is discarded.</span></span> <span data-ttu-id="74733-110">Všimněte si také, že můžete upravit pouze jeden **DataRowView** najednou.</span><span class="sxs-lookup"><span data-stu-id="74733-110">Note also that you can edit only one **DataRowView** at a time.</span></span> <span data-ttu-id="74733-111">Při volání **AddNew** nebo **BeginEdit** metodu **DataRowView** čekající řádek existuje, **EndEdit –** se implicitně volá na čeká na řádek.</span><span class="sxs-lookup"><span data-stu-id="74733-111">If you call the **AddNew** or **BeginEdit** method of the **DataRowView** while a pending row exists, **EndEdit** is implicitly called on the pending row.</span></span> <span data-ttu-id="74733-112">Při **EndEdit –** je volána, změny se použijí na odpovídající **DataTable** a může být později potvrzené nebo odmítnuté, pomocí **metoda AcceptChanges** nebo  **RejectChanges** metody **DataTable**, **datovou sadu**, nebo **DataRow** objektu.</span><span class="sxs-lookup"><span data-stu-id="74733-112">When **EndEdit** is called, the changes are applied to the underlying **DataTable** and can later be committed or rejected using the **AcceptChanges** or **RejectChanges** methods of the **DataTable**, **DataSet**, or **DataRow** object.</span></span> <span data-ttu-id="74733-113">Pokud **AllowNew** je **false**, je vyvolána výjimka při volání **AddNew** metodu **DataRowView**.</span><span class="sxs-lookup"><span data-stu-id="74733-113">If **AllowNew** is **false**, an exception is thrown if you call the **AddNew** method of the **DataRowView**.</span></span>  
  
 <span data-ttu-id="74733-114">Pokud **AllowEdit** je **true**, můžete upravit obsah **DataRow** prostřednictvím **DataRowView**.</span><span class="sxs-lookup"><span data-stu-id="74733-114">If **AllowEdit** is **true**, you can modify the contents of a **DataRow** via the **DataRowView**.</span></span> <span data-ttu-id="74733-115">Můžete potvrdit změny základní řádek pomocí **DataRowView.EndEdit** nebo odmítnout změny pomocí **DataRowView.CancelEdit**.</span><span class="sxs-lookup"><span data-stu-id="74733-115">You can confirm changes to the underlying row using **DataRowView.EndEdit** or reject the changes using **DataRowView.CancelEdit**.</span></span> <span data-ttu-id="74733-116">Všimněte si, že pouze jeden řádek se dá upravit v čase.</span><span class="sxs-lookup"><span data-stu-id="74733-116">Note that only one row can be edited at a time.</span></span> <span data-ttu-id="74733-117">Když zavoláte **AddNew** nebo **BeginEdit** metody **DataRowView** čekající řádek existuje, **EndEdit –** se implicitně volá na čeká na řádek.</span><span class="sxs-lookup"><span data-stu-id="74733-117">If you call the **AddNew** or **BeginEdit** methods of the **DataRowView** while a pending row exists, **EndEdit** is implicitly called on the pending row.</span></span> <span data-ttu-id="74733-118">Když **EndEdit –** je volána, navrhované změny, které jsou umístěny v **aktuální** verze řádku základní **DataRow** a může být později potvrzené nebo odmítnuté, pomocí  **Metoda AcceptChanges** nebo **RejectChanges** metody **DataTable**, **datovou sadu**, nebo **DataRow** objekt.</span><span class="sxs-lookup"><span data-stu-id="74733-118">When **EndEdit** is called, proposed changes are placed in the **Current** row version of the underlying **DataRow** and can later be committed or rejected using the **AcceptChanges** or **RejectChanges** methods of the **DataTable**, **DataSet**, or **DataRow** object.</span></span> <span data-ttu-id="74733-119">Pokud **AllowEdit** je **false**, je vyvolána výjimka, pokud se pokusíte změnit hodnotu v **DataView**.</span><span class="sxs-lookup"><span data-stu-id="74733-119">If **AllowEdit** is **false**, an exception is thrown if you attempt to modify a value in the **DataView**.</span></span>  
  
 <span data-ttu-id="74733-120">Pokud stávající **DataRowView** upravována, události základní **DataTable** bude stále vyvolána s navrhované změny.</span><span class="sxs-lookup"><span data-stu-id="74733-120">When an existing **DataRowView** is being edited, events of the underlying **DataTable** will still be raised with the proposed changes.</span></span> <span data-ttu-id="74733-121">Všimněte si, že při volání **EndEdit –** nebo **CancelEdit** na základní **DataRow**, čekající změny budou použity nebo došlo ke zrušení bez ohledu na to, jestli se  **EndEdit –** nebo **CancelEdit** se volá na **DataRowView**.</span><span class="sxs-lookup"><span data-stu-id="74733-121">Note that if you call **EndEdit** or **CancelEdit** on the underlying **DataRow**, pending changes will be applied or canceled regardless of whether **EndEdit** or **CancelEdit** is called on the **DataRowView**.</span></span>  
  
 <span data-ttu-id="74733-122">Pokud **vlastnost AllowDelete** je **true**, můžete odstranit řádky z **DataView** pomocí **odstranit** metodu **zobrazení dat**  nebo **DataRowView** objekt a řádky budou odstraněny ze základní **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="74733-122">If **AllowDelete** is **true**, you can delete rows from the **DataView** by using the **Delete** method of the **DataView** or **DataRowView** object, and the rows are deleted from the underlying **DataTable**.</span></span> <span data-ttu-id="74733-123">Později můžete potvrdit nebo odmítnout odstranění pomocí **metoda AcceptChanges** nebo **RejectChanges** v uvedeném pořadí.</span><span class="sxs-lookup"><span data-stu-id="74733-123">You can later commit or reject the deletes using **AcceptChanges** or **RejectChanges** respectively.</span></span> <span data-ttu-id="74733-124">Pokud **vlastnost AllowDelete** je **false**, je vyvolána výjimka při volání **odstranit** metodu **DataView** nebo  **DataRowView**.</span><span class="sxs-lookup"><span data-stu-id="74733-124">If **AllowDelete** is **false**, an exception is thrown if you call the **Delete** method of the **DataView** or **DataRowView**.</span></span>  
  
 <span data-ttu-id="74733-125">Následující příklad kódu zakáže použití **DataView** k odstranění řádků a přidá nový řádek na základní tabulku pomocí **DataView**.</span><span class="sxs-lookup"><span data-stu-id="74733-125">The following code example disables using the **DataView** to delete rows  and adds a new row to the underlying table using the **DataView**.</span></span>  
  
```vb  
Dim custTable As DataTable = custDS.Tables("Customers")  
Dim custView As DataView = custTable.DefaultView  
custView.Sort = "CompanyName"  
  
custView.AllowDelete = False  
  
Dim newDRV As DataRowView = custView.AddNew()  
newDRV("CustomerID") = "ABCDE"  
newDRV("CompanyName") = "ABC Products"  
newDRV.EndEdit()  
```  
  
```csharp  
DataTable custTable = custDS.Tables["Customers"];  
DataView custView = custTable.DefaultView;  
custView.Sort = "CompanyName";  
  
custView.AllowDelete = false;  
  
DataRowView newDRV = custView.AddNew();  
newDRV["CustomerID"] = "ABCDE";  
newDRV["CompanyName"] = "ABC Products";  
newDRV.EndEdit();  
```  
  
## <a name="see-also"></a><span data-ttu-id="74733-126">Viz také</span><span class="sxs-lookup"><span data-stu-id="74733-126">See Also</span></span>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataView>  
 <xref:System.Data.DataRowView>  
 [<span data-ttu-id="74733-127">DataView</span><span class="sxs-lookup"><span data-stu-id="74733-127">DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [<span data-ttu-id="74733-128">ADO.NET spravované zprostředkovatelé a středisku pro vývojáře datové sady</span><span class="sxs-lookup"><span data-stu-id="74733-128">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
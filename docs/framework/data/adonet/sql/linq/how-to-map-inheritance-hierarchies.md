---
title: "Postupy: mapování hierarchie dědičnosti"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b27c779b-9355-4dc7-b95f-7dfd504b6e48
dev_langs:
- csharp
- vb
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 6a0393d11c949c0bceb6587059cd450113c0ead2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-map-inheritance-hierarchies"></a><span data-ttu-id="2b834-102">Postupy: mapování hierarchie dědičnosti</span><span class="sxs-lookup"><span data-stu-id="2b834-102">How to: Map Inheritance Hierarchies</span></span>
<span data-ttu-id="2b834-103">K implementaci dědičnosti mapování v [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)], musíte zadat atributy a vlastností atributu na kořenová třída hierarchie dědičnosti jak je popsáno v následujících krocích.</span><span class="sxs-lookup"><span data-stu-id="2b834-103">To implement inheritance mapping in [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)], you must specify the attributes and attribute properties on the root class of the inheritance hierarchy as described in the following steps.</span></span> <span data-ttu-id="2b834-104">Vývojáře, kteří používají [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] můžete použít [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] k mapování hierarchie dědičnosti.</span><span class="sxs-lookup"><span data-stu-id="2b834-104">Developers using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to map inheritance hierarchies.</span></span> <span data-ttu-id="2b834-105">V tématu [postupy: Konfigurace dědičnosti pomocí Návrhář relací objektů](/visualstudio/data-tools/how-to-configure-inheritance-by-using-the-o-r-designer).</span><span class="sxs-lookup"><span data-stu-id="2b834-105">See [How to: Configure inheritance by using the O/R Designer](/visualstudio/data-tools/how-to-configure-inheritance-by-using-the-o-r-designer).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2b834-106">Žádné speciální atributy nebo vlastnosti je nutné podtřídách.</span><span class="sxs-lookup"><span data-stu-id="2b834-106">No special attributes or properties are required on the subclasses.</span></span> <span data-ttu-id="2b834-107">Zejména Všimněte si, že podtřídy nemají <xref:System.Data.Linq.Mapping.TableAttribute> atribut.</span><span class="sxs-lookup"><span data-stu-id="2b834-107">Note especially that subclasses do not have the <xref:System.Data.Linq.Mapping.TableAttribute> attribute.</span></span>  
  
### <a name="to-map-an-inheritance-hierarchy"></a><span data-ttu-id="2b834-108">Pro mapování hierarchie dědičnosti</span><span class="sxs-lookup"><span data-stu-id="2b834-108">To map an inheritance hierarchy</span></span>  
  
1.  <span data-ttu-id="2b834-109">Přidat <xref:System.Data.Linq.Mapping.TableAttribute> atribut kořenová třída.</span><span class="sxs-lookup"><span data-stu-id="2b834-109">Add the <xref:System.Data.Linq.Mapping.TableAttribute> attribute to the root class.</span></span>  
  
2.  <span data-ttu-id="2b834-110">Také do kořenové třídy, přidejte <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> atribut pro každou třídu ve struktuře hierarchie.</span><span class="sxs-lookup"><span data-stu-id="2b834-110">Also to the root class, add an <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> attribute for each class in the hierarchy structure.</span></span>  
  
3.  <span data-ttu-id="2b834-111">Pro každou <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> atribut, definování <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> vlastnost.</span><span class="sxs-lookup"><span data-stu-id="2b834-111">For each <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> attribute, define a <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> property.</span></span>  
  
     <span data-ttu-id="2b834-112">Tato vlastnost obsahuje hodnotu, která se zobrazí v tabulce databáze v <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A> sloupce k určení, které třídy nebo podtřídou tento řádek dat patří.</span><span class="sxs-lookup"><span data-stu-id="2b834-112">This property holds a value that appears in the database table in the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A> column to indicate which class or subclass this row of data belongs to.</span></span>  
  
4.  <span data-ttu-id="2b834-113">Pro každou <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> atribut, také přidat <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Type%2A> vlastnost.</span><span class="sxs-lookup"><span data-stu-id="2b834-113">For each <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> attribute, also add a <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Type%2A> property.</span></span>  
  
     <span data-ttu-id="2b834-114">Tato vlastnost obsahuje hodnotu, která určuje, které třídy nebo podtřídou označuje hodnotu klíče.</span><span class="sxs-lookup"><span data-stu-id="2b834-114">This property holds a value that specifies which class or subclass the key value signifies.</span></span>  
  
5.  <span data-ttu-id="2b834-115">Pouze na jednom z <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> atributy, přidejte <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.IsDefault%2A> vlastnost.</span><span class="sxs-lookup"><span data-stu-id="2b834-115">On only one of the <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> attributes, add an <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.IsDefault%2A> property.</span></span>  
  
     <span data-ttu-id="2b834-116">Tato vlastnost slouží k určení *záložní* mapování při diskriminátoru hodnotu z tabulky databáze neodpovídá žádnému <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> hodnota mapování dědičnosti.</span><span class="sxs-lookup"><span data-stu-id="2b834-116">This property serves to designate a *fallback* mapping when the discriminator value from the database table does not match any <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> value in the inheritance mappings.</span></span>  
  
6.  <span data-ttu-id="2b834-117">Přidat <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A> vlastnost <xref:System.Data.Linq.Mapping.ColumnAttribute> atribut.</span><span class="sxs-lookup"><span data-stu-id="2b834-117">Add an <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A> property for a <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
     <span data-ttu-id="2b834-118">Tato vlastnost označuje, že toto je sloupec, který obsahuje <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> hodnotu.</span><span class="sxs-lookup"><span data-stu-id="2b834-118">This property signifies that this is the column that holds the <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b834-119">Příklad</span><span class="sxs-lookup"><span data-stu-id="2b834-119">Example</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2b834-120">Pokud používáte [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)], můžete použít [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] konfigurace dědičnosti.</span><span class="sxs-lookup"><span data-stu-id="2b834-120">If you are using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)], you can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to configure inheritance.</span></span> <span data-ttu-id="2b834-121">V tématu [postupy: Konfigurace dědičnosti pomocí Návrhář relací objektů](/visualstudio/data-tools/how-to-configure-inheritance-by-using-the-o-r-designer)</span><span class="sxs-lookup"><span data-stu-id="2b834-121">See [How to: Configure inheritance by using the O/R Designer](/visualstudio/data-tools/how-to-configure-inheritance-by-using-the-o-r-designer)</span></span>  
  
 <span data-ttu-id="2b834-122">V následujícím příkladu kódu `Vehicle` je definován jako kořenová třída a provedení předchozí kroky k popisu hierarchii [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2b834-122">In the following code example, `Vehicle` is defined as the root class, and the previous steps have been implemented to describe the hierarchy for [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span></span>  
  
 [!code-csharp[DLinqCustomize#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#4)]
 [!code-vb[DLinqCustomize#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="2b834-123">Viz také</span><span class="sxs-lookup"><span data-stu-id="2b834-123">See Also</span></span>  
 [<span data-ttu-id="2b834-124">Podpora dědičnosti</span><span class="sxs-lookup"><span data-stu-id="2b834-124">Inheritance Support</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/inheritance-support.md)  
 [<span data-ttu-id="2b834-125">Postupy: přizpůsobení tříd entit pomocí editoru kódu</span><span class="sxs-lookup"><span data-stu-id="2b834-125">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
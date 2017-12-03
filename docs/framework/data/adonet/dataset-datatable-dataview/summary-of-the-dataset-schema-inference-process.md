---
title: "Souhrn procesu odvození schéma datové sady"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fd0891c8-d068-4e30-a76f-7c375f078bf7
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 15469e917129db7668df17f22fb71b166993d4fc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="summary-of-the-dataset-schema-inference-process"></a><span data-ttu-id="16802-102">Souhrn procesu odvození schéma datové sady</span><span class="sxs-lookup"><span data-stu-id="16802-102">Summary of the DataSet Schema Inference Process</span></span>
<span data-ttu-id="16802-103">Odvození proces nejdřív zjistí, z dokumentu XML prvky, které bude odvodit jako tabulky.</span><span class="sxs-lookup"><span data-stu-id="16802-103">The inference process first determines, from the XML document, which elements will be inferred as tables.</span></span> <span data-ttu-id="16802-104">Z zbývající XML určuje proces odvození sloupce pro tyto tabulky.</span><span class="sxs-lookup"><span data-stu-id="16802-104">From the remaining XML, the inference process determines the columns for those tables.</span></span> <span data-ttu-id="16802-105">Pro vnořené tabulky, proces odvození generuje vnořené <xref:System.Data.DataRelation> a <xref:System.Data.ForeignKeyConstraint> objekty.</span><span class="sxs-lookup"><span data-stu-id="16802-105">For nested tables, the inference process generates nested <xref:System.Data.DataRelation> and <xref:System.Data.ForeignKeyConstraint> objects.</span></span>  
  
 <span data-ttu-id="16802-106">Následuje stručné souhrnné informace o odvozená pravidla:</span><span class="sxs-lookup"><span data-stu-id="16802-106">Following is a brief summary of inference rules:</span></span>  
  
-   <span data-ttu-id="16802-107">Prvky, které mají atributy jsou odvodit jako tabulky.</span><span class="sxs-lookup"><span data-stu-id="16802-107">Elements that have attributes are inferred as tables.</span></span>  
  
-   <span data-ttu-id="16802-108">Prvky, které mají podřízené elementy jsou odvodit jako tabulky.</span><span class="sxs-lookup"><span data-stu-id="16802-108">Elements that have child elements are inferred as tables.</span></span>  
  
-   <span data-ttu-id="16802-109">Elementy, které se opakují jsou odvodit jako jednu tabulku.</span><span class="sxs-lookup"><span data-stu-id="16802-109">Elements that repeat are inferred as a single table.</span></span>  
  
-   <span data-ttu-id="16802-110">Pokud dokument nebo kořenová prvek nemá žádné atributy a žádné podřízené prvky, které by odvodit jako sloupce, je odvodit jako <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="16802-110">If the document, or root, element has no attributes, and no child elements that would be inferred as columns, it is inferred as a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="16802-111">Element dokumentu, jinak je odvodit jako tabulku.</span><span class="sxs-lookup"><span data-stu-id="16802-111">Otherwise, the document element is inferred as a table.</span></span>  
  
-   <span data-ttu-id="16802-112">Atributy jsou odvodit jako sloupce.</span><span class="sxs-lookup"><span data-stu-id="16802-112">Attributes are inferred as columns.</span></span>  
  
-   <span data-ttu-id="16802-113">Elementy, které mají žádné atributy nebo podřízené elementy a který neopakujte, jsou odvodit jako sloupce.</span><span class="sxs-lookup"><span data-stu-id="16802-113">Elements that have no attributes or child elements, and that do not repeat, are inferred as columns.</span></span>  
  
-   <span data-ttu-id="16802-114">U elementů, které jsou odvozené jako vnořených tabulek v rámci další prvky, které jsou také odvodit jako tabulek, vnořený **DataRelation** se vytvoří mezi dvěma tabulkami.</span><span class="sxs-lookup"><span data-stu-id="16802-114">For elements that are inferred as nested tables within other elements that are also inferred as tables, a nested **DataRelation** is created between the two tables.</span></span> <span data-ttu-id="16802-115">Sloupec nové, primární klíče s názvem **TableName_Id** je přidán do obou tabulek a použít **DataRelation**.</span><span class="sxs-lookup"><span data-stu-id="16802-115">A new, primary key column named **TableName_Id** is added to both tables and used by the **DataRelation**.</span></span> <span data-ttu-id="16802-116">A **vlastnosti ForeignKeyConstraint** se vytvoří mezi dvěma tabulkami pomocí **TableName_Id** sloupce.</span><span class="sxs-lookup"><span data-stu-id="16802-116">A **ForeignKeyConstraint** is created between the two tables using the **TableName_Id** column.</span></span>  
  
-   <span data-ttu-id="16802-117">U elementů, které jsou odvozené jako tabulky a který obsahují text, ale mít žádné podřízené prvky, nový sloupec s názvem **TableName_Text** je vytvořená pro text jednotlivých elementů.</span><span class="sxs-lookup"><span data-stu-id="16802-117">For elements that are inferred as tables and that contain text but have no child elements, a new column named **TableName_Text** is created for the text of each of the elements.</span></span> <span data-ttu-id="16802-118">Pokud element je odvodit jako tabulku a má text, ale také obsahuje podřízené elementy, je text ignoruje.</span><span class="sxs-lookup"><span data-stu-id="16802-118">If an element is inferred as a table and has text, but also has child elements, the text is ignored.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16802-119">Viz také</span><span class="sxs-lookup"><span data-stu-id="16802-119">See Also</span></span>  
 [<span data-ttu-id="16802-120">Odvození relační strukturu datové sady z XML</span><span class="sxs-lookup"><span data-stu-id="16802-120">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [<span data-ttu-id="16802-121">Načítání datové sady z XML</span><span class="sxs-lookup"><span data-stu-id="16802-121">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="16802-122">Načítání informací o schématu sady dat z XML</span><span class="sxs-lookup"><span data-stu-id="16802-122">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [<span data-ttu-id="16802-123">Pomocí XML v datové sadě</span><span class="sxs-lookup"><span data-stu-id="16802-123">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="16802-124">Datové sady, DataTables a DataView</span><span class="sxs-lookup"><span data-stu-id="16802-124">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="16802-125">ADO.NET spravované zprostředkovatelé a středisku pro vývojáře datové sady</span><span class="sxs-lookup"><span data-stu-id="16802-125">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
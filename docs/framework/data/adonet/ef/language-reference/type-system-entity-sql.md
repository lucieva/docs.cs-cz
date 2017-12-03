---
title: "Systém typů (entita SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 818a505b-a196-41dd-aaac-2ccd5f7a2f1a
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: b951a51c4a9daee44ba55aa3589900ca4cad188a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="type-system-entity-sql"></a><span data-ttu-id="03aa4-102">Systém typů (entita SQL)</span><span class="sxs-lookup"><span data-stu-id="03aa4-102">Type System (Entity SQL)</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="03aa4-103">podporuje několik typů:</span><span class="sxs-lookup"><span data-stu-id="03aa4-103"> supports a number of types:</span></span>  
  
-   <span data-ttu-id="03aa4-104">(Jednoduchý) primitivní typy, jako `Int32` a`String.`</span><span class="sxs-lookup"><span data-stu-id="03aa4-104">Primitive (simple) types such as `Int32` and `String.`</span></span>  
  
-   <span data-ttu-id="03aa4-105">Nominální typy, které jsou definované ve schématu, jako například <xref:System.Data.Metadata.Edm.EntityType>, <xref:System.Data.Metadata.Edm.ComplexType>, a <xref:System.Data.Metadata.Edm.RelationshipType>.</span><span class="sxs-lookup"><span data-stu-id="03aa4-105">Nominal types that are defined in the schema, such as <xref:System.Data.Metadata.Edm.EntityType>, <xref:System.Data.Metadata.Edm.ComplexType>, and <xref:System.Data.Metadata.Edm.RelationshipType>.</span></span>  
  
-   <span data-ttu-id="03aa4-106">Anonymní typy, které nejsou výslovně definované ve schématu: <xref:System.Data.Metadata.Edm.CollectionType>, <xref:System.Data.Metadata.Edm.RowType>, a <xref:System.Data.Metadata.Edm.RefType>.</span><span class="sxs-lookup"><span data-stu-id="03aa4-106">Anonymous types that are not defined in the schema explicitly: <xref:System.Data.Metadata.Edm.CollectionType>, <xref:System.Data.Metadata.Edm.RowType>, and <xref:System.Data.Metadata.Edm.RefType>.</span></span>  
  
 <span data-ttu-id="03aa4-107">Tato část popisuje anonymní typy, které nejsou výslovně definované ve schématu, ale podporuje [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="03aa4-107">This section discusses the anonymous types that are not defined in the schema explicitly but are supported by [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span> <span data-ttu-id="03aa4-108">Informace o typech primitivní a nominální najdete v tématu [konceptuálního modelu typy (CSDL)](http://msdn.microsoft.com/en-us/987b995f-e429-4569-9559-b4146744def4).</span><span class="sxs-lookup"><span data-stu-id="03aa4-108">For information on primitive and nominal types, see [Conceptual Model Types (CSDL)](http://msdn.microsoft.com/en-us/987b995f-e429-4569-9559-b4146744def4).</span></span>  
  
## <a name="rows"></a><span data-ttu-id="03aa4-109">Řádky</span><span class="sxs-lookup"><span data-stu-id="03aa4-109">Rows</span></span>  
 <span data-ttu-id="03aa4-110">Struktura řádku závisí na pořadí typu a s názvem členů, které se skládá z řádku.</span><span class="sxs-lookup"><span data-stu-id="03aa4-110">The structure of a row depends on the sequence of typed and named members that the row consists of.</span></span> <span data-ttu-id="03aa4-111">Typ řádku má žádná identita a nemůže být zděděno z.</span><span class="sxs-lookup"><span data-stu-id="03aa4-111">A row type has no identity and cannot be inherited from.</span></span> <span data-ttu-id="03aa4-112">Instance stejného typu řádek jsou ekvivalentní, pokud jsou členy v uvedeném pořadí ekvivalentní.</span><span class="sxs-lookup"><span data-stu-id="03aa4-112">Instances of the same row type are equivalent if the members are respectively equivalent.</span></span> <span data-ttu-id="03aa4-113">Řádky žádné chovají nad rámec jejich strukturální ekvivalenční a nemají žádný ekvivalent v modulu CLR.</span><span class="sxs-lookup"><span data-stu-id="03aa4-113">Rows have no behavior beyond their structural equivalence and have no equivalent in the common language runtime.</span></span> <span data-ttu-id="03aa4-114">Dotazy může mít za následek struktury, které obsahují řádky nebo kolekce řádků.</span><span class="sxs-lookup"><span data-stu-id="03aa4-114">Queries can result in structures that contain rows or collections of rows.</span></span> <span data-ttu-id="03aa4-115">Rozhraní API vazbu mezi [!INCLUDE[esql](../../../../../../includes/esql-md.md)] dotazy a hostitelského jazyka definuje, jak jsou realizovány řádků v dotazu, který vytváří výsledek.</span><span class="sxs-lookup"><span data-stu-id="03aa4-115">The API binding between the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries and the host language defines how rows are realized in the query that produced the result.</span></span> <span data-ttu-id="03aa4-116">Informace o tom, jak vytvořit instanci řádek najdete v tématu [vytváření typů](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="03aa4-116">For information on how to construct a row instance, see [Constructing Types](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).</span></span>  
  
## <a name="collections"></a><span data-ttu-id="03aa4-117">Kolekce</span><span class="sxs-lookup"><span data-stu-id="03aa4-117">Collections</span></span>  
 <span data-ttu-id="03aa4-118">Typy kolekcí představují nula nebo více instancí jiné objekty.</span><span class="sxs-lookup"><span data-stu-id="03aa4-118">Collection types represent zero or more instances of other objects.</span></span> <span data-ttu-id="03aa4-119">Informace o tom, jak vytvořit kolekci najdete v tématu [vytváření typů](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="03aa4-119">For information on how to construct collection, see [Constructing Types](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).</span></span>  
  
## <a name="references"></a><span data-ttu-id="03aa4-120">Odkazy</span><span class="sxs-lookup"><span data-stu-id="03aa4-120">References</span></span>  
 <span data-ttu-id="03aa4-121">Odkaz je logické ukazatel na konkrétní entity v sadě konkrétní entity.</span><span class="sxs-lookup"><span data-stu-id="03aa4-121">A reference is a logical pointer to a specific entity in a specific entity set.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="03aa4-122">podporuje následující operátory k vytváření, deconstruct a procházení odkazy:</span><span class="sxs-lookup"><span data-stu-id="03aa4-122"> supports the following operators to construct, deconstruct, and navigate through references:</span></span>  
  
-   [<span data-ttu-id="03aa4-123">REF</span><span class="sxs-lookup"><span data-stu-id="03aa4-123">REF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md)  
  
-   [<span data-ttu-id="03aa4-124">CREATEREF</span><span class="sxs-lookup"><span data-stu-id="03aa4-124">CREATEREF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)  
  
-   [<span data-ttu-id="03aa4-125">KLÍČ</span><span class="sxs-lookup"><span data-stu-id="03aa4-125">KEY</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)  
  
-   [<span data-ttu-id="03aa4-126">DEREF</span><span class="sxs-lookup"><span data-stu-id="03aa4-126">DEREF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md)  
  
 <span data-ttu-id="03aa4-127">Odkaz můžete procházet pomocí operátor přístupu (tečka) členů (`.`).</span><span class="sxs-lookup"><span data-stu-id="03aa4-127">You can navigate through a reference by using the member access (dot) operator(`.`).</span></span> <span data-ttu-id="03aa4-128">Následující fragment kódu extrahuje Vlastnost Id (pořadí) tak, že přejdete pomocí vlastnosti r (referenční dokumentace).</span><span class="sxs-lookup"><span data-stu-id="03aa4-128">The following snippet extracts the Id property (of Order) by navigating through the r (reference) property.</span></span>  
  
```  
select o2.r.Id   
from (select ref(o) as r from LOB.Orders as o) as o2   
```  
  
 <span data-ttu-id="03aa4-129">Pokud hodnota odkaz má hodnotu null, nebo pokud cíl odkazu neexistuje, výsledkem je null.</span><span class="sxs-lookup"><span data-stu-id="03aa4-129">If the reference value is null, or if the target of the reference does not exist, the result is null.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03aa4-130">Viz také</span><span class="sxs-lookup"><span data-stu-id="03aa4-130">See Also</span></span>  
 [<span data-ttu-id="03aa4-131">Přehled SQL entity</span><span class="sxs-lookup"><span data-stu-id="03aa4-131">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
 [<span data-ttu-id="03aa4-132">Odkaz na entitu SQL</span><span class="sxs-lookup"><span data-stu-id="03aa4-132">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="03aa4-133">PŘETYPOVÁNÍ</span><span class="sxs-lookup"><span data-stu-id="03aa4-133">CAST</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/cast-entity-sql.md)  
 [<span data-ttu-id="03aa4-134">CSDL, SSDL a specifikace MSL</span><span class="sxs-lookup"><span data-stu-id="03aa4-134">CSDL, SSDL, and MSL Specifications</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/csdl-ssdl-and-msl-specifications.md)
---
title: "ŘÁDEK (entita SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 06da96e8-55d7-486c-991a-4e514d837ff9
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 396b81e01d057f1d5c357f18d833a973777c07ea
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="row-entity-sql"></a><span data-ttu-id="cc5ec-102">ŘÁDEK (entita SQL)</span><span class="sxs-lookup"><span data-stu-id="cc5ec-102">ROW (Entity SQL)</span></span>
<span data-ttu-id="cc5ec-103">Vytvoří anonymní, strukturálně typové záznamů z jednoho nebo více hodnot.</span><span class="sxs-lookup"><span data-stu-id="cc5ec-103">Constructs anonymous, structurally typed records from one or more values.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc5ec-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="cc5ec-104">Syntax</span></span>  
  
```  
ROW ( expression [ AS alias ] [,...] )  
```  
  
## <a name="arguments"></a><span data-ttu-id="cc5ec-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="cc5ec-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="cc5ec-106">Libovolný platný dotaz výraz, který vrátí hodnotu, můžete vytvořit v typ řádku.</span><span class="sxs-lookup"><span data-stu-id="cc5ec-106">Any valid query expression that returns a value to construct in a row type.</span></span>  
  
 `alias`  
 <span data-ttu-id="cc5ec-107">Určuje alias z hodnoty zadané v typ řádku.</span><span class="sxs-lookup"><span data-stu-id="cc5ec-107">Specifies an alias for the value specified in a row type.</span></span> <span data-ttu-id="cc5ec-108">Pokud není k dispozici alias, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] pokusí generovat alias na základě [!INCLUDE[esql](../../../../../../includes/esql-md.md)] pravidel pro vytvoření aliasu.</span><span class="sxs-lookup"><span data-stu-id="cc5ec-108">If an alias is not provided, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tries to generate an alias based on the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] alias generation rules.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cc5ec-109">Návratová hodnota</span><span class="sxs-lookup"><span data-stu-id="cc5ec-109">Return Value</span></span>  
 <span data-ttu-id="cc5ec-110">Typ řádku.</span><span class="sxs-lookup"><span data-stu-id="cc5ec-110">A row type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cc5ec-111">Poznámky</span><span class="sxs-lookup"><span data-stu-id="cc5ec-111">Remarks</span></span>  
 <span data-ttu-id="cc5ec-112">Použití konstruktorů řádek v [!INCLUDE[esql](../../../../../../includes/esql-md.md)] vytvořit anonymní, strukturálně typové záznamů z jednoho nebo více hodnot.</span><span class="sxs-lookup"><span data-stu-id="cc5ec-112">You use row constructors in the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] to construct anonymous, structurally typed records from one or more values.</span></span> <span data-ttu-id="cc5ec-113">Výsledný typ konstruktor row je typu řádek, jehož typy polí odpovídají typům hodnot, které jste použili k vytvoření řádek.</span><span class="sxs-lookup"><span data-stu-id="cc5ec-113">The result type of a row constructor is a row type whose field types correspond to the types of the values that were used to construct the row.</span></span> <span data-ttu-id="cc5ec-114">Například následující výraz vytvoří hodnotu typu `Record(a int, b string, c int)`.</span><span class="sxs-lookup"><span data-stu-id="cc5ec-114">For example, the following expression constructs a value of type `Record(a int, b string, c int)`.</span></span>  
  
```  
ROW(1 AS a, "abc" AS b, a+34 AS c)  
```  
  
 <span data-ttu-id="cc5ec-115">Pokud nezadáte alias pro výraz v konstruktoru row, rozhraní Entity Framework se pokusí vygenerovat.</span><span class="sxs-lookup"><span data-stu-id="cc5ec-115">If you do not provide an alias for an expression in a row constructor, the Entity Framework will try to generate one.</span></span> <span data-ttu-id="cc5ec-116">Další informace najdete v části "Pravidla pro aliasy" [identifikátory](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md) tématu.</span><span class="sxs-lookup"><span data-stu-id="cc5ec-116">For more information, see the "Aliasing Rules" section of the [Identifiers](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md) topic.</span></span>  
  
 <span data-ttu-id="cc5ec-117">Následující pravidla platí při aliasy výrazu v konstruktoru řádku:</span><span class="sxs-lookup"><span data-stu-id="cc5ec-117">The following rules apply to expression aliasing in a row constructor:</span></span>  
  
-   <span data-ttu-id="cc5ec-118">Výrazy v konstruktoru row nelze odkazovat na jiné aliasy v konstruktoru stejné.</span><span class="sxs-lookup"><span data-stu-id="cc5ec-118">Expressions in a row constructor cannot refer to other aliases in the same constructor.</span></span>  
  
-   <span data-ttu-id="cc5ec-119">Dvou výrazů ve stejné konstruktor row nemůže mít stejný alias.</span><span class="sxs-lookup"><span data-stu-id="cc5ec-119">Two expressions in the same row constructor cannot have the same alias.</span></span>  
  
 <span data-ttu-id="cc5ec-120">Další informace o dotazu konstruktory najdete v tématu [vytváření typů](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="cc5ec-120">For more information about query constructors, see [Constructing Types](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc5ec-121">Příklad</span><span class="sxs-lookup"><span data-stu-id="cc5ec-121">Example</span></span>  
 <span data-ttu-id="cc5ec-122">Následující dotaz Entity SQL pomocí operátoru řádek vytvořit anonymní, strukturálně typové záznamy.</span><span class="sxs-lookup"><span data-stu-id="cc5ec-122">The following Entity SQL query uses the ROW operator to construct anonymous, structurally typed records.</span></span> <span data-ttu-id="cc5ec-123">Dotaz je založen na modelu prodej AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="cc5ec-123">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="cc5ec-124">Pro zkompilování a spuštění tohoto dotazu, postupujte takto:</span><span class="sxs-lookup"><span data-stu-id="cc5ec-124">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="cc5ec-125">Postupujte podle pokynů v [postup: provedení dotazu tohoto vrátí výsledky StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="cc5ec-125">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="cc5ec-126">Předat jako argument pro následující dotaz `ExecuteStructuralTypeQuery` metoda:</span><span class="sxs-lookup"><span data-stu-id="cc5ec-126">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ROW](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#row)]  
  
## <a name="see-also"></a><span data-ttu-id="cc5ec-127">Viz také</span><span class="sxs-lookup"><span data-stu-id="cc5ec-127">See Also</span></span>  
 [<span data-ttu-id="cc5ec-128">Vytváření typů</span><span class="sxs-lookup"><span data-stu-id="cc5ec-128">Constructing Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md)  
 [<span data-ttu-id="cc5ec-129">Odkaz na entitu SQL</span><span class="sxs-lookup"><span data-stu-id="cc5ec-129">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="cc5ec-130">Definice typů</span><span class="sxs-lookup"><span data-stu-id="cc5ec-130">Type Definitions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/type-definitions-entity-sql.md)
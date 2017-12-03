---
title: "ZPRACOVÁVAT (entita SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5b77f156-55de-4cb4-8154-87f707d4c635
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: fa7bfd2a9fffdd0cfedced76cf83f9e01630c986
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="treat-entity-sql"></a><span data-ttu-id="e0562-102">ZPRACOVÁVAT (entita SQL)</span><span class="sxs-lookup"><span data-stu-id="e0562-102">TREAT (Entity SQL)</span></span>
<span data-ttu-id="e0562-103">Objekt konkrétní základní typ zpracovává jako objekt zadaného typu odvozené.</span><span class="sxs-lookup"><span data-stu-id="e0562-103">Treats an object of a particular base type as an object of the specified derived type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0562-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="e0562-104">Syntax</span></span>  
  
```  
TREAT ( expression as type)  
```  
  
## <a name="arguments"></a><span data-ttu-id="e0562-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="e0562-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="e0562-106">Libovolný platný dotaz výraz, který vrátí entity.</span><span class="sxs-lookup"><span data-stu-id="e0562-106">Any valid query expression that returns an entity.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e0562-107">Typ zadaný výraz musí být podtypem zadaný datový typ nebo datový typ musí být podtypem typ výrazu.</span><span class="sxs-lookup"><span data-stu-id="e0562-107">The type of the specified expression must be a subtype of the specified data type, or the data type must be a subtype of the type of expression.</span></span>  
  
 `type`  
 <span data-ttu-id="e0562-108">Typ entity.</span><span class="sxs-lookup"><span data-stu-id="e0562-108">An entity type.</span></span> <span data-ttu-id="e0562-109">Typ musí být kvalifikován obor názvů.</span><span class="sxs-lookup"><span data-stu-id="e0562-109">The type must be qualified by a namespace.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e0562-110">Zadaný výraz musí být podtypem zadaný datový typ nebo datový typ musí být podtypem výraz.</span><span class="sxs-lookup"><span data-stu-id="e0562-110">The specified expression must be a subtype of the specified data type, or the data type must be a subtype of the expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e0562-111">Návratová hodnota</span><span class="sxs-lookup"><span data-stu-id="e0562-111">Return Value</span></span>  
 <span data-ttu-id="e0562-112">Hodnota zadaného datového typu.</span><span class="sxs-lookup"><span data-stu-id="e0562-112">A value of the specified data type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0562-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="e0562-113">Remarks</span></span>  
 <span data-ttu-id="e0562-114">ZPRACOVÁVAT slouží k provádění přetypování nahoru mezi související třídy.</span><span class="sxs-lookup"><span data-stu-id="e0562-114">TREAT is used to perform upcasting between related classes.</span></span> <span data-ttu-id="e0562-115">Například pokud `Employee` je odvozena z `Person` a p je typu `Person`, `TREAT(p AS NamespaceName.Employee)` upcasts a obecného `Person` instance na `Employee`; to znamená, umožňuje považovat za p `Employee`.</span><span class="sxs-lookup"><span data-stu-id="e0562-115">For example, if `Employee` derives from `Person` and p is of type `Person`, `TREAT(p AS NamespaceName.Employee)` upcasts a generic `Person` instance to `Employee`; that is, it allows you to treat p as `Employee`.</span></span>  
  
 <span data-ttu-id="e0562-116">ZPRACOVÁVAT se používá ve scénářích dědičnosti, kde můžete provést dotaz takto:</span><span class="sxs-lookup"><span data-stu-id="e0562-116">TREAT is used in inheritance scenarios where you can do a query like the following:</span></span>  
  
```  
SELECT TREAT(p AS NamespaceName.Employee)  
FROM ContainerName.Person AS p  
WHERE p IS OF (NamespaceName.Employee)   
```  
  
 <span data-ttu-id="e0562-117">Tento dotaz upcasts `Person` entity k `Employee` typu.</span><span class="sxs-lookup"><span data-stu-id="e0562-117">This query upcasts `Person` entities to the `Employee` type.</span></span> <span data-ttu-id="e0562-118">Pokud hodnota p není ve skutečnosti je typu `Employee`, výsledkem je hodnota, výraz `null`.</span><span class="sxs-lookup"><span data-stu-id="e0562-118">If the value of p is not actually of type `Employee`, the expression yields the value `null`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e0562-119">Zadaný výraz `Employee` musí být podtypem zadaný datový typ `Person`, nebo datový typ musí být podtypem výraz.</span><span class="sxs-lookup"><span data-stu-id="e0562-119">The specified expression `Employee` must be a subtype of the specified data type `Person`, or the data type must be a subtype of the expression.</span></span> <span data-ttu-id="e0562-120">Výraz, jinak bude výsledkem chyba kompilace.</span><span class="sxs-lookup"><span data-stu-id="e0562-120">Otherwise, the expression will result in a compile-time error.</span></span>  
  
 <span data-ttu-id="e0562-121">Následující tabulka uvádí chování zpracovávat přes některé typické vzory a některé méně častých vzory.</span><span class="sxs-lookup"><span data-stu-id="e0562-121">The following table shows the behavior of treat over some typical patterns and some less common patterns.</span></span> <span data-ttu-id="e0562-122">Všechny výjimky jsou vyvolány ze strany klienta předtím, než získá volá zprostředkovatele:</span><span class="sxs-lookup"><span data-stu-id="e0562-122">All exceptions are thrown from the client side before the provider gets invoked:</span></span>  
  
|<span data-ttu-id="e0562-123">Vzor</span><span class="sxs-lookup"><span data-stu-id="e0562-123">Pattern</span></span>|<span data-ttu-id="e0562-124">Chování</span><span class="sxs-lookup"><span data-stu-id="e0562-124">Behavior</span></span>|  
|-------------|--------------|  
|`TREAT (null AS EntityType)`|<span data-ttu-id="e0562-125">Vrátí `DbNull`.</span><span class="sxs-lookup"><span data-stu-id="e0562-125">Returns `DbNull`.</span></span>|  
|`TREAT (null AS ComplexType)`|<span data-ttu-id="e0562-126">Vyvolá výjimku.</span><span class="sxs-lookup"><span data-stu-id="e0562-126">Throws an exception.</span></span>|  
|`TREAT (null AS RowType)`|<span data-ttu-id="e0562-127">Vyvolá výjimku, nebo</span><span class="sxs-lookup"><span data-stu-id="e0562-127">Throws an exception/</span></span>|  
|`TREAT (EntityType AS EntityType)`|<span data-ttu-id="e0562-128">Vrátí `EntityType` nebo `null`.</span><span class="sxs-lookup"><span data-stu-id="e0562-128">Returns `EntityType` or `null`.</span></span>|  
|`TREAT (ComplexType AS ComplexType)`|<span data-ttu-id="e0562-129">Vyvolá výjimku.</span><span class="sxs-lookup"><span data-stu-id="e0562-129">Throws an exception.</span></span>|  
|`TREAT (RowType AS RowType)`|<span data-ttu-id="e0562-130">Vyvolá výjimku.</span><span class="sxs-lookup"><span data-stu-id="e0562-130">Throws an exception.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e0562-131">Příklad</span><span class="sxs-lookup"><span data-stu-id="e0562-131">Example</span></span>  
 <span data-ttu-id="e0562-132">Následující [!INCLUDE[esql](../../../../../../includes/esql-md.md)] dotaz používá operátor ZPRACOVÁVAT převést objekt typu kurzu na kolekce objektů typu OnsiteCourse.</span><span class="sxs-lookup"><span data-stu-id="e0562-132">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the TREAT operator to convert an object of the type Course to a collection of objects of the type OnsiteCourse.</span></span> <span data-ttu-id="e0562-133">Dotaz je na základě [školní modelu](http://msdn.microsoft.com/en-us/859a9587-81ea-4a45-9bc0-f8d330e1adac).</span><span class="sxs-lookup"><span data-stu-id="e0562-133">The query is based on the [School Model](http://msdn.microsoft.com/en-us/859a9587-81ea-4a45-9bc0-f8d330e1adac).</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#TREAT_ISOF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#treat_isof)]  
  
## <a name="see-also"></a><span data-ttu-id="e0562-134">Viz také</span><span class="sxs-lookup"><span data-stu-id="e0562-134">See Also</span></span>  
 [<span data-ttu-id="e0562-135">Odkaz na entitu SQL</span><span class="sxs-lookup"><span data-stu-id="e0562-135">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="e0562-136">Strukturované typy s možnou hodnotou Null</span><span class="sxs-lookup"><span data-stu-id="e0562-136">Nullable Structured Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/nullable-structured-types-entity-sql.md)
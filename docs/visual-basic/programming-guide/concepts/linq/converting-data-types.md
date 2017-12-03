---
title: "Převádění datových typů (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9b0cf1ab-de48-4c6e-9f00-05b40fade46e
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5fb0e9dfb0f1fb882116449757ed0f0bf9029b39
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="converting-data-types-visual-basic"></a><span data-ttu-id="06ff7-102">Převádění datových typů (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="06ff7-102">Converting Data Types (Visual Basic)</span></span>
<span data-ttu-id="06ff7-103">Převod metody změnit typ vstupní objektů.</span><span class="sxs-lookup"><span data-stu-id="06ff7-103">Conversion methods change the type of input objects.</span></span>  
  
 <span data-ttu-id="06ff7-104">Převod operace v dotazech LINQ jsou užitečné v různých aplikací.</span><span class="sxs-lookup"><span data-stu-id="06ff7-104">Conversion operations in LINQ queries are useful in a variety of applications.</span></span> <span data-ttu-id="06ff7-105">Následuje několik příkladů:</span><span class="sxs-lookup"><span data-stu-id="06ff7-105">Following are some examples:</span></span>  
  
-   <span data-ttu-id="06ff7-106"><xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType> Metoda slouží ke skrytí vlastní implementaci typ operátoru standardní dotaz.</span><span class="sxs-lookup"><span data-stu-id="06ff7-106">The <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType> method can be used to hide a type's custom implementation of a standard query operator.</span></span>  
  
-   <span data-ttu-id="06ff7-107"><xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType> Metoda slouží k povolení-parametry kolekce pro dotazy LINQ.</span><span class="sxs-lookup"><span data-stu-id="06ff7-107">The <xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType> method can be used to enable non-parameterized collections for LINQ querying.</span></span>  
  
-   <span data-ttu-id="06ff7-108"><xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>, A <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType> metody slouží k vynucení spuštění okamžitou dotazu místo ho odložit, dokud není dotaz zpracován.</span><span class="sxs-lookup"><span data-stu-id="06ff7-108">The <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>, and <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType> methods can be used to force immediate query execution instead of deferring it until the query is enumerated.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="06ff7-109">Metody</span><span class="sxs-lookup"><span data-stu-id="06ff7-109">Methods</span></span>  
 <span data-ttu-id="06ff7-110">Následující tabulka uvádí metody operátor standardní dotazů, které provádět převody datových typů.</span><span class="sxs-lookup"><span data-stu-id="06ff7-110">The following table lists the standard query operator methods that perform data-type conversions.</span></span>  
  
 <span data-ttu-id="06ff7-111">Převod metody v této tabulce, jejichž název začíná "Jako" změnit statický typ kolekce zdroj ale není výčet.</span><span class="sxs-lookup"><span data-stu-id="06ff7-111">The conversion methods in this table whose names start with "As" change the static type of the source collection but do not enumerate it.</span></span> <span data-ttu-id="06ff7-112">Typ metody, jejichž název začíná "Na výčet zdrojové kolekci a umístí do příslušné kolekce položek".</span><span class="sxs-lookup"><span data-stu-id="06ff7-112">The methods whose names start with "To" enumerate the source collection and put the items into the corresponding collection type.</span></span>  
  
|<span data-ttu-id="06ff7-113">Název metody</span><span class="sxs-lookup"><span data-stu-id="06ff7-113">Method Name</span></span>|<span data-ttu-id="06ff7-114">Popis</span><span class="sxs-lookup"><span data-stu-id="06ff7-114">Description</span></span>|<span data-ttu-id="06ff7-115">Syntaxe výrazu dotazu jazyka Visual Basic</span><span class="sxs-lookup"><span data-stu-id="06ff7-115">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="06ff7-116">Další informace</span><span class="sxs-lookup"><span data-stu-id="06ff7-116">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="06ff7-117">Jako výčet</span><span class="sxs-lookup"><span data-stu-id="06ff7-117">AsEnumerable</span></span>|<span data-ttu-id="06ff7-118">Vrátí zadané jako vstup <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="06ff7-118">Returns the input typed as <xref:System.Collections.Generic.IEnumerable%601>.</span></span>|<span data-ttu-id="06ff7-119">Nelze použít.</span><span class="sxs-lookup"><span data-stu-id="06ff7-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="06ff7-120">AsQueryable</span><span class="sxs-lookup"><span data-stu-id="06ff7-120">AsQueryable</span></span>|<span data-ttu-id="06ff7-121">Převede (Obecné) <xref:System.Collections.IEnumerable> k (Obecné) <xref:System.Linq.IQueryable>.</span><span class="sxs-lookup"><span data-stu-id="06ff7-121">Converts a (generic) <xref:System.Collections.IEnumerable> to a (generic) <xref:System.Linq.IQueryable>.</span></span>|<span data-ttu-id="06ff7-122">Nelze použít.</span><span class="sxs-lookup"><span data-stu-id="06ff7-122">Not applicable.</span></span>|<xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="06ff7-123">Změna typu</span><span class="sxs-lookup"><span data-stu-id="06ff7-123">Cast</span></span>|<span data-ttu-id="06ff7-124">Vrhá prvky kolekce do zadaného typu.</span><span class="sxs-lookup"><span data-stu-id="06ff7-124">Casts the elements of a collection to a specified type.</span></span>|`From … As …`|<xref:System.Linq.Enumerable.Cast%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Cast%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="06ff7-125">OfType</span><span class="sxs-lookup"><span data-stu-id="06ff7-125">OfType</span></span>|<span data-ttu-id="06ff7-126">Hodnoty, v závislosti na jejich schopnost převést na zadaný typ filtrování.</span><span class="sxs-lookup"><span data-stu-id="06ff7-126">Filters values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="06ff7-127">Nelze použít.</span><span class="sxs-lookup"><span data-stu-id="06ff7-127">Not applicable.</span></span>|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="06ff7-128">ToArray</span><span class="sxs-lookup"><span data-stu-id="06ff7-128">ToArray</span></span>|<span data-ttu-id="06ff7-129">Převede kolekci na pole.</span><span class="sxs-lookup"><span data-stu-id="06ff7-129">Converts a collection to an array.</span></span> <span data-ttu-id="06ff7-130">Tato metoda vynutí spuštění dotazu.</span><span class="sxs-lookup"><span data-stu-id="06ff7-130">This method forces query execution.</span></span>|<span data-ttu-id="06ff7-131">Nelze použít.</span><span class="sxs-lookup"><span data-stu-id="06ff7-131">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="06ff7-132">ToDictionary</span><span class="sxs-lookup"><span data-stu-id="06ff7-132">ToDictionary</span></span>|<span data-ttu-id="06ff7-133">Vloží elementy do <xref:System.Collections.Generic.Dictionary%602> podle funkce selektoru klíče.</span><span class="sxs-lookup"><span data-stu-id="06ff7-133">Puts elements into a <xref:System.Collections.Generic.Dictionary%602> based on a key selector function.</span></span> <span data-ttu-id="06ff7-134">Tato metoda vynutí spuštění dotazu.</span><span class="sxs-lookup"><span data-stu-id="06ff7-134">This method forces query execution.</span></span>|<span data-ttu-id="06ff7-135">Nelze použít.</span><span class="sxs-lookup"><span data-stu-id="06ff7-135">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="06ff7-136">ToList</span><span class="sxs-lookup"><span data-stu-id="06ff7-136">ToList</span></span>|<span data-ttu-id="06ff7-137">Převede kolekci na <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="06ff7-137">Converts a collection to a <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="06ff7-138">Tato metoda vynutí spuštění dotazu.</span><span class="sxs-lookup"><span data-stu-id="06ff7-138">This method forces query execution.</span></span>|<span data-ttu-id="06ff7-139">Nelze použít.</span><span class="sxs-lookup"><span data-stu-id="06ff7-139">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="06ff7-140">ToLookup</span><span class="sxs-lookup"><span data-stu-id="06ff7-140">ToLookup</span></span>|<span data-ttu-id="06ff7-141">Vloží elementy do <xref:System.Linq.Lookup%602> (slovník 1 n) podle funkce selektoru klíče.</span><span class="sxs-lookup"><span data-stu-id="06ff7-141">Puts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span> <span data-ttu-id="06ff7-142">Tato metoda vynutí spuštění dotazu.</span><span class="sxs-lookup"><span data-stu-id="06ff7-142">This method forces query execution.</span></span>|<span data-ttu-id="06ff7-143">Nelze použít.</span><span class="sxs-lookup"><span data-stu-id="06ff7-143">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="06ff7-144">Příklad syntaxe výrazu dotazu</span><span class="sxs-lookup"><span data-stu-id="06ff7-144">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="06ff7-145">Následující příklad kódu používá `From As` přetypovat typ k podtypem před přístupem k člena, který je dostupná jen pro dílčí klauzuli.</span><span class="sxs-lookup"><span data-stu-id="06ff7-145">The following code example uses the `From As` clause to cast a type to a subtype before accessing a member that is available only on the subtype.</span></span>  
  
```vb  
Class Plant  
    Public Property Name As String  
End Class  
  
Class CarnivorousPlant  
    Inherits Plant  
    Public Property TrapType As String  
End Class  
  
Sub Cast()  
  
    Dim plants() As Plant = {   
        New CarnivorousPlant With {.Name = "Venus Fly Trap", .TrapType = "Snap Trap"},   
        New CarnivorousPlant With {.Name = "Pitcher Plant", .TrapType = "Pitfall Trap"},   
        New CarnivorousPlant With {.Name = "Sundew", .TrapType = "Flypaper Trap"},   
        New CarnivorousPlant With {.Name = "Waterwheel Plant", .TrapType = "Snap Trap"}}  
  
    Dim query = From plant As CarnivorousPlant In plants   
                Where plant.TrapType = "Snap Trap"   
                Select plant  
  
    Dim sb As New System.Text.StringBuilder()  
    For Each plant In query  
        sb.AppendLine(plant.Name)  
    Next  
  
    ' Display the results.  
    MsgBox(sb.ToString())  
  
    ' This code produces the following output:  
  
    ' Venus Fly Trap  
    ' Waterwheel Plant  
  
End Sub  
```  
  
## <a name="see-also"></a><span data-ttu-id="06ff7-146">Viz také</span><span class="sxs-lookup"><span data-stu-id="06ff7-146">See Also</span></span>  
 <xref:System.Linq>  
 [<span data-ttu-id="06ff7-147">Přehled standardních operátorů dotazu (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="06ff7-147">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [<span data-ttu-id="06ff7-148">From – klauzule</span><span class="sxs-lookup"><span data-stu-id="06ff7-148">From Clause</span></span>](../../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="06ff7-149">Postupy: dotazu na ArrayList pomocí LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="06ff7-149">How to: Query an ArrayList with LINQ (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md)
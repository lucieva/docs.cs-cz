---
title: "Příklady syntaxe výrazu dotazu: filtrování"
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
ms.assetid: c27cb89c-1c1d-4988-9f38-950eda3cb275
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: e943dc85f46d3cf9f1f3a9032b70b17cf4a72a66
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="query-expression-syntax-examples-filtering"></a><span data-ttu-id="b485d-102">Příklady syntaxe výrazu dotazu: filtrování</span><span class="sxs-lookup"><span data-stu-id="b485d-102">Query Expression Syntax Examples: Filtering</span></span>
<span data-ttu-id="b485d-103">V příkladech v tomto tématu ukazují, jak používat `Where` a `Where…Contains` metody k dotazování [Model prodeje společnosti AdventureWorks](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832) pomocí syntaxe výrazu dotazu.</span><span class="sxs-lookup"><span data-stu-id="b485d-103">The examples in this topic demonstrate how to use the `Where` and `Where…Contains` methods to query the [AdventureWorks Sales Model](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832) using query expression syntax.</span></span> <span data-ttu-id="b485d-104">Všimněte si, kam...`Contains`</span><span class="sxs-lookup"><span data-stu-id="b485d-104">Note, Where…`Contains`</span></span> <span data-ttu-id="b485d-105">nelze použít jako součást [zkompilován dotaz](../../../../../../docs/framework/data/adonet/ef/language-reference/compiled-queries-linq-to-entities.md).</span><span class="sxs-lookup"><span data-stu-id="b485d-105">cannot be used as a part of a [compiled query](../../../../../../docs/framework/data/adonet/ef/language-reference/compiled-queries-linq-to-entities.md).</span></span>  
  
 <span data-ttu-id="b485d-106">Model prodeje společnosti AdventureWorks použít v těchto příkladech je sestaven z kontaktu, adresu, produktu, SalesOrderHeader a podrobnosti prodejní objednávky tabulky v ukázkové databázi AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="b485d-106">The AdventureWorks Sales model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="b485d-107">V příkladech v tomto tématu použijte následující `using` / `Imports` příkazy:</span><span class="sxs-lookup"><span data-stu-id="b485d-107">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="where"></a><span data-ttu-id="b485d-108">Where</span><span class="sxs-lookup"><span data-stu-id="b485d-108">Where</span></span>  
  
### <a name="example"></a><span data-ttu-id="b485d-109">Příklad</span><span class="sxs-lookup"><span data-stu-id="b485d-109">Example</span></span>  
 <span data-ttu-id="b485d-110">Následující příklad vrátí všechny online objednávky.</span><span class="sxs-lookup"><span data-stu-id="b485d-110">The following example returns all online orders.</span></span>  
  
 [!code-csharp[DP L2E Examples#Where1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#where1)]
 [!code-vb[DP L2E Examples#Where1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#where1)]  
  
### <a name="example"></a><span data-ttu-id="b485d-111">Příklad</span><span class="sxs-lookup"><span data-stu-id="b485d-111">Example</span></span>  
 <span data-ttu-id="b485d-112">Následující příklad vrátí objednávky, kde je větší než 2 a menší než 6 množství objednávky.</span><span class="sxs-lookup"><span data-stu-id="b485d-112">The following example returns the orders where the order quantity is greater than 2 and less than 6.</span></span>  
  
 [!code-csharp[DP L2E Examples#Where2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#where2)]
 [!code-vb[DP L2E Examples#Where2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#where2)]  
  
### <a name="example"></a><span data-ttu-id="b485d-113">Příklad</span><span class="sxs-lookup"><span data-stu-id="b485d-113">Example</span></span>  
 <span data-ttu-id="b485d-114">Následující příklad vrátí všechny red barevnou produkty.</span><span class="sxs-lookup"><span data-stu-id="b485d-114">The following example returns all red colored products.</span></span>  
  
 [!code-csharp[DP L2E Examples#Where3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#where3)]
 [!code-vb[DP L2E Examples#Where3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#where3)]  
  
### <a name="example"></a><span data-ttu-id="b485d-115">Příklad</span><span class="sxs-lookup"><span data-stu-id="b485d-115">Example</span></span>  
 <span data-ttu-id="b485d-116">Následující příklad používá `Where` metody k vyhledání objednávky, které byly provedeny po 1. prosince 2003, a pak používá `order.SalesOrderDetail` navigační vlastnost pro získání podrobností o pro každé pořadí.</span><span class="sxs-lookup"><span data-stu-id="b485d-116">The following example uses the `Where` method to find orders that were made after December 1, 2003, and then uses the `order.SalesOrderDetail` navigation property to get the details for each order.</span></span>  
  
 [!code-csharp[DP L2E Examples#WhereNavProperty](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#wherenavproperty)]
 [!code-vb[DP L2E Examples#WhereNavProperty](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#wherenavproperty)]  
  
## <a name="wherecontains"></a><span data-ttu-id="b485d-117">Kde... Obsahuje</span><span class="sxs-lookup"><span data-stu-id="b485d-117">Where…Contains</span></span>  
  
### <a name="example"></a><span data-ttu-id="b485d-118">Příklad</span><span class="sxs-lookup"><span data-stu-id="b485d-118">Example</span></span>  
 <span data-ttu-id="b485d-119">Následující příklad používá jako součást pole `Where…Contains` klauzule najít všechny produkty, které mají `ProductModelID` odpovídající hodnotu v poli.</span><span class="sxs-lookup"><span data-stu-id="b485d-119">The following example uses an array as part of a `Where…Contains` clause to find all products that have a `ProductModelID` that matches a value in the array.</span></span>  
  
 [!code-csharp[DP L2E ArraysAndListsInQueries#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e arraysandlistsinqueries/cs/program.cs#1)]
 [!code-vb[DP L2E ArraysAndListsInQueries#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e arraysandlistsinqueries/vb/module1.vb#1)]  
  
> [!NOTE]
>  <span data-ttu-id="b485d-120">V rámci predikátu v `Where…Contains` klauzule, můžete použít <xref:System.Array>, <xref:System.Collections.Generic.List%601>, nebo kolekci žádný typ, který implementuje <xref:System.Collections.Generic.IEnumerable%601> rozhraní.</span><span class="sxs-lookup"><span data-stu-id="b485d-120">As part of the predicate in a `Where…Contains` clause, you can use an <xref:System.Array>, a <xref:System.Collections.Generic.List%601>, or a collection of any type that implements the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="b485d-121">Můžete také deklarovat a inicializuje kolekci v dotazu LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="b485d-121">You can also declare and initialize a collection within a LINQ to Entities query.</span></span> <span data-ttu-id="b485d-122">Podívejte se na další příklad další informace.</span><span class="sxs-lookup"><span data-stu-id="b485d-122">See the next example for more information.</span></span>  
  
### <a name="example"></a><span data-ttu-id="b485d-123">Příklad</span><span class="sxs-lookup"><span data-stu-id="b485d-123">Example</span></span>  
 <span data-ttu-id="b485d-124">Následující příklad deklaruje a inicializuje pole v `Where…Contains` klauzule najít všechny produkty, které mají `ProductModelID` nebo `Size` odpovídající hodnoty v polích.</span><span class="sxs-lookup"><span data-stu-id="b485d-124">The following example declares and initializes arrays in a `Where…Contains` clause to find all products that have a `ProductModelID` or `Size` that match values in the arrays.</span></span>  
  
 [!code-csharp[DP L2E ArraysAndListsInQueries#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e arraysandlistsinqueries/cs/program.cs#2)]
 [!code-vb[DP L2E ArraysAndListsInQueries#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e arraysandlistsinqueries/vb/module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="b485d-125">Viz také</span><span class="sxs-lookup"><span data-stu-id="b485d-125">See Also</span></span>  
 [<span data-ttu-id="b485d-126">Dotazy v technologii LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="b485d-126">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
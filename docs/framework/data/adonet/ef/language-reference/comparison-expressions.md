---
title: "Výrazy porovnání"
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
ms.assetid: ec7637a9-01d5-4a95-8bb0-478311cd263b
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0ec850636433c0c7ed2c61f4f97ba578952cac21
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="comparison-expressions"></a><span data-ttu-id="a13fc-102">Výrazy porovnání</span><span class="sxs-lookup"><span data-stu-id="a13fc-102">Comparison Expressions</span></span>
<span data-ttu-id="a13fc-103">Výraz porovnání zkontroluje, zda je konstantní hodnota, hodnota vlastnosti nebo výsledek metody stejné, není rovno, větší nebo menší než jiná hodnota.</span><span class="sxs-lookup"><span data-stu-id="a13fc-103">A comparison expression checks whether a constant value, property value, or method result is equal, not equal, greater than, or less than another value.</span></span> <span data-ttu-id="a13fc-104">Pokud konkrétní porovnání není platný pro [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)], bude vyvolána výjimka.</span><span class="sxs-lookup"><span data-stu-id="a13fc-104">If a particular comparison is not valid for [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)], an exception will be thrown.</span></span> <span data-ttu-id="a13fc-105">Všechny porovnání implicitní a explicitní, vyžadují, zda jsou všechny součásti ve zdroji dat porovnatelný.</span><span class="sxs-lookup"><span data-stu-id="a13fc-105">All comparisons, both implicit and explicit, require that all components are comparable in the data source.</span></span> <span data-ttu-id="a13fc-106">Výrazy porovnání se často používají v `Where` klauzule pro omezení výsledky dotazu.</span><span class="sxs-lookup"><span data-stu-id="a13fc-106">Comparison expressions are frequently used in `Where` clauses for restricting the query results.</span></span>  
  
 <span data-ttu-id="a13fc-107">Následující příklad v syntaxe výrazu dotazu obsahuje dotaz, který vrátí výsledky, kde je rovno "SO43663" prodeje pořadové číslo:</span><span class="sxs-lookup"><span data-stu-id="a13fc-107">The following example in query expression syntax shows a query that returns results where the sales order number is equal to "SO43663":</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#RestrictionExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#restrictionexpression)]
 [!code-vb[DP L2E Conceptual Examples#RestrictionExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#restrictionexpression)]  
  
 <span data-ttu-id="a13fc-108">V syntaxi dotazu na základě metod následující příklad ukazuje dotaz, který vrátí výsledky, kde je rovno "SO43663" prodeje pořadové číslo:</span><span class="sxs-lookup"><span data-stu-id="a13fc-108">The following example in method-based query syntax shows a query that returns results where the sales order number is equal to "SO43663":</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#RestrictionExpression_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#restrictionexpression_mq)]
 [!code-vb[DP L2E Conceptual Examples#RestrictionExpression_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#restrictionexpression_mq)]  
  
 <span data-ttu-id="a13fc-109">Následující příklad v syntaxe výrazu dotazu ukazuje dotaz, který vrátí informace o objednávce prodeje, kde expedice je rovno 8 července 2001:</span><span class="sxs-lookup"><span data-stu-id="a13fc-109">The following example in query expression syntax shows a query that returns sales order information where the ship date is equal to July 8, 2001:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#DateTimeComparison](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#datetimecomparison)]
 [!code-vb[DP L2E Conceptual Examples#DateTimeComparison](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#datetimecomparison)]  
  
 <span data-ttu-id="a13fc-110">V syntaxi dotazu na základě metod následující příklad ukazuje dotaz, který vrátí informace o objednávce prodeje, kde expedice je rovno 8 července 2001:</span><span class="sxs-lookup"><span data-stu-id="a13fc-110">The following example in method-based query syntax shows a query that returns sales order information where the ship date is equal to July 8, 2001:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#DateTimeComparison_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#datetimecomparison_mq)]
 [!code-vb[DP L2E Conceptual Examples#DateTimeComparison_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#datetimecomparison_mq)]  
  
 <span data-ttu-id="a13fc-111">Výrazy, které vrací konstanta se převedou na serveru a provádí žádný pokus o provést místní vyhodnocení.</span><span class="sxs-lookup"><span data-stu-id="a13fc-111">Expressions that yield a constant are converted at the server, and no attempt to do local evaluation is performed.</span></span> <span data-ttu-id="a13fc-112">Následující příklad používá výraz v `Where` klauzuli, která vypočítá konstanta.</span><span class="sxs-lookup"><span data-stu-id="a13fc-112">The following example uses an expression in the `Where` clause that yields a constant.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#ConstantExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#constantexpression)]
 [!code-vb[DP L2E Conceptual Examples#ConstantExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#constantexpression)]  
  
 [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)]<span data-ttu-id="a13fc-113">nepodporuje použití třídy uživatele jako konstanta.</span><span class="sxs-lookup"><span data-stu-id="a13fc-113"> does not support using a user class as a constant.</span></span> <span data-ttu-id="a13fc-114">Však odkaz na vlastnost třídy uživatel se považuje za konstantu a budou převést na strom příkaz konstantní výraz a ve zdroji dat.</span><span class="sxs-lookup"><span data-stu-id="a13fc-114">However, a property reference on a user class is considered a constant, and will be converted to a command tree constant expression and executed on the data source.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#MyClass](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#myclass)]
 [!code-vb[DP L2E Conceptual Examples#MyClass](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#myclass)]  
  
 [!code-csharp[DP L2E Conceptual Examples#PropertyAsConstant](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#propertyasconstant)]
 [!code-vb[DP L2E Conceptual Examples#PropertyAsConstant](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#propertyasconstant)]  
  
 <span data-ttu-id="a13fc-115">Metody, které vracejí konstantní výraz nejsou podporovány.</span><span class="sxs-lookup"><span data-stu-id="a13fc-115">Methods that return a constant expression are not supported.</span></span> <span data-ttu-id="a13fc-116">Následující příklad obsahuje metodu v `Where` klauzuli, která vrátí konstanta.</span><span class="sxs-lookup"><span data-stu-id="a13fc-116">The following example contains a method in the `Where` clause that returns a constant.</span></span> <span data-ttu-id="a13fc-117">Tento příklad vyvolá výjimku za běhu.</span><span class="sxs-lookup"><span data-stu-id="a13fc-117">This example will throw an exception at run time.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#MethodAsConstantFails](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#methodasconstantfails)]
 [!code-vb[DP L2E Conceptual Examples#MethodAsConstantFails](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#methodasconstantfails)]  
  
## <a name="see-also"></a><span data-ttu-id="a13fc-118">Viz také</span><span class="sxs-lookup"><span data-stu-id="a13fc-118">See Also</span></span>  
 [<span data-ttu-id="a13fc-119">Výrazy v technologii LINQ to Entities dotazy</span><span class="sxs-lookup"><span data-stu-id="a13fc-119">Expressions in LINQ to Entities Queries</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/expressions-in-linq-to-entities-queries.md)
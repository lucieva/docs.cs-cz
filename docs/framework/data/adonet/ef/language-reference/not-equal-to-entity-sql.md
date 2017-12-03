---
title: "! = (Nerovná se) (entita SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3b4a02ad-ddfc-4c42-8dfa-676234461312
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: a2187e317229961b0929f1415cd40f6f65f5c593
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="-not-equal-to-entity-sql"></a><span data-ttu-id="ca0fb-102">! = (Nerovná se) (entita SQL)</span><span class="sxs-lookup"><span data-stu-id="ca0fb-102">!= (Not Equal To) (Entity SQL)</span></span>
<span data-ttu-id="ca0fb-103">Porovnává dva výrazy k určení, zda levý výraz není rovno pravý výraz.</span><span class="sxs-lookup"><span data-stu-id="ca0fb-103">Compares two expressions to determine whether the left expression is not equal to the right expression.</span></span> <span data-ttu-id="ca0fb-104">! = – Operátor (není rovno) je funkčně srovnatelný <> operátor.</span><span class="sxs-lookup"><span data-stu-id="ca0fb-104">The != (Not Equal To) operator is functionally equivalent to the <> operator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca0fb-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="ca0fb-105">Syntax</span></span>  
  
```  
expression != expression  
or  
expression <> expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="ca0fb-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="ca0fb-106">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="ca0fb-107">Jakýkoli platný výraz.</span><span class="sxs-lookup"><span data-stu-id="ca0fb-107">Any valid expression.</span></span> <span data-ttu-id="ca0fb-108">Oba výrazy musí mít implicitně převést datové typy.</span><span class="sxs-lookup"><span data-stu-id="ca0fb-108">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="ca0fb-109">Typy výsledků</span><span class="sxs-lookup"><span data-stu-id="ca0fb-109">Result Types</span></span>  
 <span data-ttu-id="ca0fb-110">`true`Pokud levý výraz není rovno pravý výraz; v opačném `false`.</span><span class="sxs-lookup"><span data-stu-id="ca0fb-110">`true` if the left expression is not equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ca0fb-111">Příklad</span><span class="sxs-lookup"><span data-stu-id="ca0fb-111">Example</span></span>  
 <span data-ttu-id="ca0fb-112">Následující dotaz Entity SQL používá! = – operátor k porovnání dvou výrazů k určení, zda levý výraz není rovno pravý výraz.</span><span class="sxs-lookup"><span data-stu-id="ca0fb-112">The following Entity SQL query uses the != operator to compare two expressions to determine whether the left expression is not equal to the right expression.</span></span> <span data-ttu-id="ca0fb-113">Dotaz je založen na modelu prodej AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="ca0fb-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="ca0fb-114">Pro zkompilování a spuštění tohoto dotazu, postupujte takto:</span><span class="sxs-lookup"><span data-stu-id="ca0fb-114">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="ca0fb-115">Postupujte podle pokynů v [postup: provedení dotazu tohoto vrátí výsledky StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="ca0fb-115">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="ca0fb-116">Předat jako argument pro následující dotaz `ExecuteStructuralTypeQuery` metoda:</span><span class="sxs-lookup"><span data-stu-id="ca0fb-116">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#NOT_EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#not_equals)]  
  
## <a name="see-also"></a><span data-ttu-id="ca0fb-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="ca0fb-117">See Also</span></span>  
 [<span data-ttu-id="ca0fb-118">Odkaz na entitu SQL</span><span class="sxs-lookup"><span data-stu-id="ca0fb-118">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
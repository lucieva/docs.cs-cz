---
title: "Vrátí sadu sjednocení dvou sekvencí"
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
ms.assetid: 8b8bd3cb-86d4-4a3b-9906-61f68726dd1f
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 865aa82ebc119a3952124a93f9042c2732e3ab48
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="return-the-set-union-of-two-sequences"></a><span data-ttu-id="b2a47-102">Vrátí sadu sjednocení dvou sekvencí</span><span class="sxs-lookup"><span data-stu-id="b2a47-102">Return the Set Union of Two Sequences</span></span>
<span data-ttu-id="b2a47-103">Použití <xref:System.Linq.Queryable.Union%2A> operátor vrátit sadu sjednocení dvou pořadí.</span><span class="sxs-lookup"><span data-stu-id="b2a47-103">Use the <xref:System.Linq.Queryable.Union%2A> operator to return the set union of two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2a47-104">Příklad</span><span class="sxs-lookup"><span data-stu-id="b2a47-104">Example</span></span>  
 <span data-ttu-id="b2a47-105">Tento příklad používá <xref:System.Linq.Queryable.Union%2A> vrátit sekvenci všech zemí, ve kterém jsou buď `Customers` nebo `Employees`.</span><span class="sxs-lookup"><span data-stu-id="b2a47-105">This example uses <xref:System.Linq.Queryable.Union%2A> to return a sequence of all countries in which there are either `Customers` or `Employees`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#43](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#43)]
 [!code-vb[DLinqQueryExamples#43](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#43)]  
  
 <span data-ttu-id="b2a47-106">V [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], <xref:System.Linq.Queryable.Union%2A> operátor je definována pro multisets jako neuspořádaný zřetězení multisets (efektivně výsledek `UNION ALL` klauzule v systému SQL).</span><span class="sxs-lookup"><span data-stu-id="b2a47-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Union%2A> operator is defined for multisets as the unordered concatenation of the multisets (effectively the result of the `UNION ALL` clause in SQL).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2a47-107">Viz také</span><span class="sxs-lookup"><span data-stu-id="b2a47-107">See Also</span></span>  
 [<span data-ttu-id="b2a47-108">Příklady dotazů</span><span class="sxs-lookup"><span data-stu-id="b2a47-108">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 [<span data-ttu-id="b2a47-109">Operátor posunutí standardní dotazu</span><span class="sxs-lookup"><span data-stu-id="b2a47-109">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
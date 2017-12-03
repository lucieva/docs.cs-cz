---
title: "Postupy: řízení, kolik související Data načtena"
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
ms.assetid: efdc203e-3da9-4477-815e-54f10c3d7c6c
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 708f972610c92aac07e06359b4f740ae6f0100be
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-control-how-much-related-data-is-retrieved"></a><span data-ttu-id="88ba2-102">Postupy: řízení, kolik související Data načtena</span><span class="sxs-lookup"><span data-stu-id="88ba2-102">How to: Control How Much Related Data Is Retrieved</span></span>
<span data-ttu-id="88ba2-103">Použití <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> metoda k určení, která data související s vaší hlavní cíl mají být načtena ve stejnou dobu.</span><span class="sxs-lookup"><span data-stu-id="88ba2-103">Use the <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> method to specify which data related to your main target should be retrieved at the same time.</span></span> <span data-ttu-id="88ba2-104">Například pokud jste si jisti, budete potřebovat informace o objednávek zákazníků, můžete použít <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> a ujistěte se, že je ve stejnou dobu jako informace o zákazníkovi načíst informace o objednávce.</span><span class="sxs-lookup"><span data-stu-id="88ba2-104">For example, if you know you will need information about customers' orders, you can use <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> to make sure that the order information is retrieved at the same time as the customer information.</span></span> <span data-ttu-id="88ba2-105">Tento přístup je výsledkem pouze jediná cesta k databázi pro obě sady informace.</span><span class="sxs-lookup"><span data-stu-id="88ba2-105">This approach results in only one trip to the database for both sets of information.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="88ba2-106">Můžete načíst data související s hlavním cílem tohoto dotazu načtením smíšený produkt jako jeden velký projekce, jako je například získávání objednávky po cíle zákazníků.</span><span class="sxs-lookup"><span data-stu-id="88ba2-106">You can retrieve data related to the main target of your query by retrieving a cross-product as one large projection, such as retrieving orders when you target customers.</span></span> <span data-ttu-id="88ba2-107">Ale tento přístup má často nevýhody.</span><span class="sxs-lookup"><span data-stu-id="88ba2-107">But this approach often has disadvantages.</span></span> <span data-ttu-id="88ba2-108">Například výsledky jsou právě projekce a není entit, které můžete změnit a ve uchováván [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="88ba2-108">For example, the results are just projections and not entities that can be changed and persisted by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="88ba2-109">A může být načítání velké množství dat, který není nutné.</span><span class="sxs-lookup"><span data-stu-id="88ba2-109">And you can be retrieving lots of data that you do not need.</span></span>  
  
## <a name="example"></a><span data-ttu-id="88ba2-110">Příklad</span><span class="sxs-lookup"><span data-stu-id="88ba2-110">Example</span></span>  
 <span data-ttu-id="88ba2-111">V následujícím příkladu všechny `Orders` pro všechny `Customers` kdo jsou umístěny v Londýně se načítají, když je proveden dotaz.</span><span class="sxs-lookup"><span data-stu-id="88ba2-111">In the following example, all the `Orders` for all the `Customers` who are located in London are retrieved when the query is executed.</span></span> <span data-ttu-id="88ba2-112">V důsledku toho následných přístup k `Orders` vlastnost `Customer` objekt neaktivuje nový databázový dotaz.</span><span class="sxs-lookup"><span data-stu-id="88ba2-112">As a result, successive access to the `Orders` property on a `Customer` object does not trigger a new database query.</span></span>  
  
 [!code-csharp[System.Data.Linq.DataLoadOptions#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.dataloadoptions/cs/program.cs#2)]
 [!code-vb[System.Data.Linq.DataLoadOptions#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.dataloadoptions/vb/module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="88ba2-113">Viz také</span><span class="sxs-lookup"><span data-stu-id="88ba2-113">See Also</span></span>  
 [<span data-ttu-id="88ba2-114">Dotaz na databázi</span><span class="sxs-lookup"><span data-stu-id="88ba2-114">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
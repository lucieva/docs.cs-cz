---
title: "Postupy: provádění dotazů služby asynchronní dat (služby WCF Data Services)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, asynchronous operations
- asynchronous operations [WCF Data Services]
ms.assetid: 902a2dc1-d0e9-4b00-90a8-becc4cb1f6a7
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a6bb3089c8796cb31cf46e006f8fd3a5fec15ef0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-execute-asynchronous-data-service-queries-wcf-data-services"></a><span data-ttu-id="a42d2-102">Postupy: provádění dotazů služby asynchronní dat (služby WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="a42d2-102">How to: Execute Asynchronous Data Service Queries (WCF Data Services)</span></span>
<span data-ttu-id="a42d2-103">Pomocí [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] klientské knihovny, můžete asynchronně provádět operace klient server, například zpracování dotazů a ukládají se změny.</span><span class="sxs-lookup"><span data-stu-id="a42d2-103">By using the [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] client library, you can asynchronously perform client-server operations, such as executing queries and saving changes.</span></span> <span data-ttu-id="a42d2-104">Další informace najdete v tématu [asynchronních operací](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="a42d2-104">For more information, see [Asynchronous Operations](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a42d2-105">V aplikaci, kde musí být volána zpětné volání na konkrétní vlákno, musí explicitně zařazování provádění <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A> metoda.</span><span class="sxs-lookup"><span data-stu-id="a42d2-105">In an application where the callback must be invoked on a specific thread, you must explicitly marshal the execution of the <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A> method.</span></span> <span data-ttu-id="a42d2-106">Další informace najdete v tématu [asynchronních operací](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="a42d2-106">For more information, see [Asynchronous Operations](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="a42d2-107">V příkladu v tomto tématu používá Northwind ukázková data služby a automaticky generovaný klienta dat služby třídy.</span><span class="sxs-lookup"><span data-stu-id="a42d2-107">The example in this topic uses the Northwind sample data service and autogenerated client data service classes.</span></span> <span data-ttu-id="a42d2-108">Tato služba a datové třídy klienta se vytvoří při dokončení [rychlého startu služby WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="a42d2-108">This service and the client data classes are created when you complete the [WCF Data Services quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a42d2-109">Příklad</span><span class="sxs-lookup"><span data-stu-id="a42d2-109">Example</span></span>  
 <span data-ttu-id="a42d2-110">Následující příklad ukazuje, jak provést asynchronní dotaz voláním <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A> metoda dotaz spustíte.</span><span class="sxs-lookup"><span data-stu-id="a42d2-110">The following example shows how to execute an asynchronous query by calling the <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A> method to start the query.</span></span> <span data-ttu-id="a42d2-111">Vložený delegovat volání <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A> metodu pro zobrazení výsledků dotazu.</span><span class="sxs-lookup"><span data-stu-id="a42d2-111">The inline delegate calls the <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A> method to display the query results.</span></span>  
  
 [!code-csharp[Astoria Northwind Client#ExecuteQueryAsync](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#executequeryasync)]
 [!code-vb[Astoria Northwind Client#ExecuteQueryAsync](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#executequeryasync)]  
  
## <a name="see-also"></a><span data-ttu-id="a42d2-112">Viz také</span><span class="sxs-lookup"><span data-stu-id="a42d2-112">See Also</span></span>  
 [<span data-ttu-id="a42d2-113">Klientská knihovna pro WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="a42d2-113">WCF Data Services Client Library</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
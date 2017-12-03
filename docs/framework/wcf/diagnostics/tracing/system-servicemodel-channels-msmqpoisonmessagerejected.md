---
title: System.ServiceModel.Channels.MsmqPoisonMessageRejected
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0e64b9bd-1f12-43df-a189-d7be3c2bace1
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 87c6cef7420976c26cd1e9027f134818339273af
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodelchannelsmsmqpoisonmessagerejected"></a><span data-ttu-id="477ed-102">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span><span class="sxs-lookup"><span data-stu-id="477ed-102">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span></span>
<span data-ttu-id="477ed-103">Poškozená zpráva byla odmítnuta.</span><span class="sxs-lookup"><span data-stu-id="477ed-103">Poison message rejected.</span></span>  
  
## <a name="description"></a><span data-ttu-id="477ed-104">Popis</span><span class="sxs-lookup"><span data-stu-id="477ed-104">Description</span></span>  
 <span data-ttu-id="477ed-105">Trasování označuje, že byl nezpracovatelná zpráva došlo a následně odmítnuto.</span><span class="sxs-lookup"><span data-stu-id="477ed-105">The trace indicates that a poison message was encountered and subsequently rejected.</span></span> <span data-ttu-id="477ed-106">K tomu dojde při `ReceiveErrorHandling` – NetMsmqBinding nebo – MsmqIntegrationBinding je nastavena na `Reject`.</span><span class="sxs-lookup"><span data-stu-id="477ed-106">This occurs when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Reject`.</span></span> <span data-ttu-id="477ed-107">Odmítnuté zprávy doručuje zpět do odesílatele [frontu nedoručených zpráv](http://go.microsoft.com/fwlink/?LinkId=99544).</span><span class="sxs-lookup"><span data-stu-id="477ed-107">A rejected message is delivered back to the sender’s [Dead-Letter Queue](http://go.microsoft.com/fwlink/?LinkId=99544).</span></span>  
  
 <span data-ttu-id="477ed-108">V tématu [zpracování zpráv Poison](http://go.microsoft.com/fwlink/?LinkId=99546) další podrobnosti o kdy začnou poškozených zpráv a postup konfigurace služby pro správně zpracovat.</span><span class="sxs-lookup"><span data-stu-id="477ed-108">See [Poison-Message Handling](http://go.microsoft.com/fwlink/?LinkId=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span> <span data-ttu-id="477ed-109">V tématu [MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkId=99548) další podrobnosti o odmítnuté zprávy znamená služby MSMQ.</span><span class="sxs-lookup"><span data-stu-id="477ed-109">See [MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkId=99548) for more details on what a rejected message means in MSMQ.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="477ed-110">Viz také</span><span class="sxs-lookup"><span data-stu-id="477ed-110">See Also</span></span>  
 [<span data-ttu-id="477ed-111">Trasování</span><span class="sxs-lookup"><span data-stu-id="477ed-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="477ed-112">Řešení potíží s vaší aplikace pomocí trasování</span><span class="sxs-lookup"><span data-stu-id="477ed-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="477ed-113">Správa a Diagnostika</span><span class="sxs-lookup"><span data-stu-id="477ed-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)  
 [<span data-ttu-id="477ed-114">Zpracování zpráv Poison</span><span class="sxs-lookup"><span data-stu-id="477ed-114">Poison-Message Handling</span></span>](http://go.microsoft.com/fwlink/?LinkId=99546)  
 [<span data-ttu-id="477ed-115">MQMarkMessageRejected</span><span class="sxs-lookup"><span data-stu-id="477ed-115">MQMarkMessageRejected</span></span>](http://go.microsoft.com/fwlink/?LinkId=99548)
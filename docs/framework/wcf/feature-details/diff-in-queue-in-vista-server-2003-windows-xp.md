---
title: "Rozdíly funkcí front zpráv v systémech Windows Vista, Windows Server 2003 a Windows XP"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: queues [WCF], differences in operating systems
ms.assetid: aa809d93-d0a3-4ae6-a726-d015cca37c04
caps.latest.revision: "21"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ac22e2e47bdbfc53f8986c2bae30d0cc0f964601
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="differences-in-queuing-features-in-windows-vista-windows-server-2003-and-windows-xp"></a><span data-ttu-id="a675b-102">Rozdíly funkcí front zpráv v systémech Windows Vista, Windows Server 2003 a Windows XP</span><span class="sxs-lookup"><span data-stu-id="a675b-102">Differences in Queuing Features in Windows Vista, Windows Server 2003, and Windows XP</span></span>
<span data-ttu-id="a675b-103">Toto téma shrnuje rozdíly v [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] fronty funkci mezi [!INCLUDE[wv](../../../../includes/wv-md.md)], [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], a [!INCLUDE[wxp](../../../../includes/wxp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a675b-103">This topic summarizes the differences in the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] queues feature between [!INCLUDE[wv](../../../../includes/wv-md.md)], [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], and [!INCLUDE[wxp](../../../../includes/wxp-md.md)].</span></span>  
  
## <a name="application-specific-dead-letter-queue"></a><span data-ttu-id="a675b-104">Fronty nedoručených zpráv specifické pro aplikaci</span><span class="sxs-lookup"><span data-stu-id="a675b-104">Application-Specific Dead-Letter Queue</span></span>  
 <span data-ttu-id="a675b-105">Zprávy ve frontě může zůstat ve frontě po neomezenou dobu Pokud přijímající aplikace nenačte je včas.</span><span class="sxs-lookup"><span data-stu-id="a675b-105">Queued messages can remain in the queue indefinitely if the receiving application does not read them in a timely fashion.</span></span> <span data-ttu-id="a675b-106">Toto chování se nedoporučuje, pokud jsou náročné na čas zprávy.</span><span class="sxs-lookup"><span data-stu-id="a675b-106">This behavior is not advisable if the messages are time-sensitive.</span></span> <span data-ttu-id="a675b-107">Zprávy náročné na čas `TimeToLive` vlastností nastavenou zařazených do fronty vazba.</span><span class="sxs-lookup"><span data-stu-id="a675b-107">Time-sensitive messages have a `TimeToLive` property set in the queued binding.</span></span> <span data-ttu-id="a675b-108">Tato vlastnost určuje, jak dlouho zprávy může být ve frontě před vypršením jejich platnosti.</span><span class="sxs-lookup"><span data-stu-id="a675b-108">This property indicates how long the messages can be in the queue before they expire.</span></span> <span data-ttu-id="a675b-109">Zprávy s vypršenou platností jsou odesílány speciální fronty s názvem frontu nedoručených zpráv.</span><span class="sxs-lookup"><span data-stu-id="a675b-109">Expired messages are sent to a special queue called the dead-letter queue.</span></span> <span data-ttu-id="a675b-110">Zprávu můžete také ukončit do fronty nedoručených zpráv z jiných důvodů, například překročení kvóty fronty nebo došlo k chybě ověřování.</span><span class="sxs-lookup"><span data-stu-id="a675b-110">A message can also end up in a dead-letter queue for other reasons, such as exceeding a queue quota or experiencing an authentication failure.</span></span>  
  
 <span data-ttu-id="a675b-111">Obvykle jediné fronty nedoručených zpráv systémové existuje pro všechny aplikace ve frontě, které sdílejí správce front.</span><span class="sxs-lookup"><span data-stu-id="a675b-111">Typically, a single system-wide dead-letter queue exists for all queued applications that share a queue manager.</span></span> <span data-ttu-id="a675b-112">Frontu nedoručených zpráv pro každou aplikaci umožňuje lepší izolace mezi aplikacemi zařazených do fronty, které sdílejí správce front tím, že se tyto aplikace zadat své vlastní frontu nedoručených zpráv pro konkrétní aplikace.</span><span class="sxs-lookup"><span data-stu-id="a675b-112">A dead-letter queue for each application enables better isolation between queued applications that share a queue manager by allowing these applications to specify their own application-specific dead-letter queue.</span></span> <span data-ttu-id="a675b-113">Procházet fronty najít zprávy, které se vztahují k němu má aplikace sdílející frontu nedoručených zpráv s jinými aplikacemi.</span><span class="sxs-lookup"><span data-stu-id="a675b-113">An application that shares a dead-letter queue with other applications has to browse the queue to find messages that are applicable to it.</span></span> <span data-ttu-id="a675b-114">S frontu nedoručených zpráv specifické pro aplikaci aplikace si být jistí, že se na něj vztahují všechny zprávy do fronty nedoručených zpráv.</span><span class="sxs-lookup"><span data-stu-id="a675b-114">With an application-specific dead-letter queue, the application can be assured that all messages in its dead-letter queue are applicable to it.</span></span>  
  
 [!INCLUDE[wv](../../../../includes/wv-md.md)]<span data-ttu-id="a675b-115">poskytuje pro fronty nedoručených zpráv specifické pro aplikaci.</span><span class="sxs-lookup"><span data-stu-id="a675b-115"> provides for application-specific dead-letter queues.</span></span> <span data-ttu-id="a675b-116">Fronty nedoručených zpráv specifické pro aplikaci nejsou k dispozici v [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] a [!INCLUDE[wxp](../../../../includes/wxp-md.md)], a aplikace, musí používat systémové fronty nedoručených zpráv.</span><span class="sxs-lookup"><span data-stu-id="a675b-116">Application-specific dead-letter queues are not available in [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] and [!INCLUDE[wxp](../../../../includes/wxp-md.md)], and applications must use the system-wide dead-letter queue.</span></span>  
  
## <a name="poison-message-handling"></a><span data-ttu-id="a675b-117">Zpracování zpráv Poison</span><span class="sxs-lookup"><span data-stu-id="a675b-117">Poison-Message Handling</span></span>  
 <span data-ttu-id="a675b-118">Nezpracovatelná zpráva je zprávu, která byla překročena maximální počet pokusů o doručení přijímající aplikaci.</span><span class="sxs-lookup"><span data-stu-id="a675b-118">A poison message is a message that has exceeded the maximum number of delivery attempts to the receiving application.</span></span> <span data-ttu-id="a675b-119">Tato situace mohou nastat při aplikaci, která čte zprávy z fronty transakcí nelze okamžitě zpracovat zprávu z důvodu chyb.</span><span class="sxs-lookup"><span data-stu-id="a675b-119">This situation can arise when an application that reads a message from a transactional queue cannot process the message immediately because of errors.</span></span> <span data-ttu-id="a675b-120">Pokud aplikace zruší transakce, ve kterém byl přijat zpráv zařazených ve frontě, vrátí zprávu do fronty.</span><span class="sxs-lookup"><span data-stu-id="a675b-120">If the application aborts the transaction in which the queued message was received, it returns the message to the queue.</span></span> <span data-ttu-id="a675b-121">Aplikace se pak pokusí se načíst zprávu znovu za novou transakci.</span><span class="sxs-lookup"><span data-stu-id="a675b-121">The application then tries to retrieve the message again in a new transaction.</span></span> <span data-ttu-id="a675b-122">Pokud není vyřešen problém, který způsobuje chybu, může být zablokován má přijímající aplikace ve smyčce přijímáním a přerušení stejná zpráva, dokud překračuje maximální počet pokusů o doručení a výsledky poškozená zpráva.</span><span class="sxs-lookup"><span data-stu-id="a675b-122">If the problem that causes the error is not corrected, the receiving application can get stuck in a loop receiving and aborting the same message until it exceeds the maximum number of delivery attempts, and a poison message results.</span></span>  
  
 <span data-ttu-id="a675b-123">Hlavní rozdíly mezi řízení front zpráv (MSMQ) na [!INCLUDE[wv](../../../../includes/wv-md.md)], [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], a [!INCLUDE[wxp](../../../../includes/wxp-md.md)] , které jsou relevantní pro zpracování poškozených patří:</span><span class="sxs-lookup"><span data-stu-id="a675b-123">The key differences between Message Queuing (MSMQ) on [!INCLUDE[wv](../../../../includes/wv-md.md)], [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], and [!INCLUDE[wxp](../../../../includes/wxp-md.md)] that are relevant to poison handling include the following:</span></span>  
  
-   <span data-ttu-id="a675b-124">Služby MSMQ v [!INCLUDE[wv](../../../../includes/wv-md.md)] podporuje podfronty, zatímco [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] a [!INCLUDE[wxp](../../../../includes/wxp-md.md)] nepodporují podfronty.</span><span class="sxs-lookup"><span data-stu-id="a675b-124">MSMQ in [!INCLUDE[wv](../../../../includes/wv-md.md)] supports subqueues, while [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] and [!INCLUDE[wxp](../../../../includes/wxp-md.md)] do not support subqueues.</span></span> <span data-ttu-id="a675b-125">Podfronty se používají při zpracování poison zpráv.</span><span class="sxs-lookup"><span data-stu-id="a675b-125">Subqueues are used in poison-message handling.</span></span> <span data-ttu-id="a675b-126">Fronty opakování a poškozených fronty jsou podfronty do fronty aplikace, která je vytvořena na základě nastavení zpracování poison zpráv.</span><span class="sxs-lookup"><span data-stu-id="a675b-126">The retry queues and the poison queue are subqueues to the application queue that is created based on the poison-message handling settings.</span></span> <span data-ttu-id="a675b-127">`MaxRetryCycles` Určuje, kolik opakujte podfronty k vytvoření.</span><span class="sxs-lookup"><span data-stu-id="a675b-127">The `MaxRetryCycles` dictates how many retry subqueues to create.</span></span> <span data-ttu-id="a675b-128">Proto při spuštění [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] nebo [!INCLUDE[wxp](../../../../includes/wxp-md.md)], `MaxRetryCycles` jsou ignorovány a `ReceiveErrorHandling.Move` není povolen.</span><span class="sxs-lookup"><span data-stu-id="a675b-128">Therefore, when running on [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] or [!INCLUDE[wxp](../../../../includes/wxp-md.md)], `MaxRetryCycles` are ignored and `ReceiveErrorHandling.Move` is not allowed.</span></span>  
  
-   <span data-ttu-id="a675b-129">Služby MSMQ v [!INCLUDE[wv](../../../../includes/wv-md.md)] podporuje zápornou potvrzení, zatímco [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] a [!INCLUDE[wxp](../../../../includes/wxp-md.md)] nepodporují.</span><span class="sxs-lookup"><span data-stu-id="a675b-129">MSMQ in [!INCLUDE[wv](../../../../includes/wv-md.md)] supports negative acknowledgment, while [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] and [!INCLUDE[wxp](../../../../includes/wxp-md.md)] do not.</span></span> <span data-ttu-id="a675b-130">Záporné potvrzení z přijímající správce front způsobí, že odesílání správce front k umístit odmítnuté zprávy do fronty nedoručených zpráv.</span><span class="sxs-lookup"><span data-stu-id="a675b-130">A negative acknowledgment from the receiving queue manager causes the sending queue manager to place the rejected message in the dead-letter queue.</span></span> <span data-ttu-id="a675b-131">Jako takový `ReceiveErrorHandling.Reject` není povolen u [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] a [!INCLUDE[wxp](../../../../includes/wxp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a675b-131">As such, `ReceiveErrorHandling.Reject` is not allowed with [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] and [!INCLUDE[wxp](../../../../includes/wxp-md.md)].</span></span>  
  
-   <span data-ttu-id="a675b-132">Služby MSMQ v [!INCLUDE[wv](../../../../includes/wv-md.md)] podporuje dojde k pokusu o vlastnosti zprávy, která udržuje počet Počet doručení zpráv.</span><span class="sxs-lookup"><span data-stu-id="a675b-132">MSMQ in [!INCLUDE[wv](../../../../includes/wv-md.md)] supports a message property that keeps count of the number of times message delivery is attempted.</span></span> <span data-ttu-id="a675b-133">Tato vlastnost počet přerušení není k dispozici na [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] a [!INCLUDE[wxp](../../../../includes/wxp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a675b-133">This abort count property is not available on [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] and [!INCLUDE[wxp](../../../../includes/wxp-md.md)].</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a675b-134">udržuje počet přerušení v paměti, takže je možné, že tato vlastnost nesmí obsahovat přesné hodnoty přečtení stejné zprávy o více než jednu [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] služby ve webové farmě.</span><span class="sxs-lookup"><span data-stu-id="a675b-134"> maintains the abort count in memory, so it is possible that this property may not contain an accurate value when the same message is read by more than one [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service in a Web farm.</span></span>  
  
## <a name="remote-transactional-read"></a><span data-ttu-id="a675b-135">Vzdálené transakcí pro čtení</span><span class="sxs-lookup"><span data-stu-id="a675b-135">Remote Transactional Read</span></span>  
 <span data-ttu-id="a675b-136">MSMQ na [!INCLUDE[wv](../../../../includes/wv-md.md)] podporuje vzdálené transakční čtení.</span><span class="sxs-lookup"><span data-stu-id="a675b-136">MSMQ on [!INCLUDE[wv](../../../../includes/wv-md.md)] supports remote transactional reads.</span></span> <span data-ttu-id="a675b-137">To umožňuje aplikaci, která je čtení z fronty pro hostování v počítači, který se liší od počítače, který je hostitelem fronty.</span><span class="sxs-lookup"><span data-stu-id="a675b-137">This allows an application that is reading from a queue to be hosted on a computer that is different from the computer on which the queue is hosted.</span></span> <span data-ttu-id="a675b-138">Tím se zajistí možnost farma služby čtení z centrální fronty, která zvyšuje celkovou propustnost systému.</span><span class="sxs-lookup"><span data-stu-id="a675b-138">This ensures the ability to have a farm of services reading from a central queue, which increases the overall throughput of the system.</span></span> <span data-ttu-id="a675b-139">Je taky zajišťuje, že pokud dojde k chybě při čtení a zpracování zprávy, transakce se vrátí zpět a zpráva zůstává ve frontě pro pozdější zpracování.</span><span class="sxs-lookup"><span data-stu-id="a675b-139">It also ensures that if a failure occurs when reading and processing the message, the transaction rolls back and the message remains in the queue for later processing.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a675b-140">Viz také</span><span class="sxs-lookup"><span data-stu-id="a675b-140">See Also</span></span>  
 [<span data-ttu-id="a675b-141">Zpracování chyb přenosu zpráv pomocí front nedoručených zpráv</span><span class="sxs-lookup"><span data-stu-id="a675b-141">Using Dead-Letter Queues to Handle Message Transfer Failures</span></span>](../../../../docs/framework/wcf/feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md)  
 [<span data-ttu-id="a675b-142">Zpracování škodlivých zpráv</span><span class="sxs-lookup"><span data-stu-id="a675b-142">Poison Message Handling</span></span>](../../../../docs/framework/wcf/feature-details/poison-message-handling.md)
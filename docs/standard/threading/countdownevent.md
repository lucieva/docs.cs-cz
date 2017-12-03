---
title: CountdownEvent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: synchronization primitives, CountdownEvent
ms.assetid: eec3812a-e20f-4ecd-bfef-6921d508b708
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9f953f6477abf1f4e0d6aaf79e67005172ff1144
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="countdownevent"></a><span data-ttu-id="58b73-102">CountdownEvent</span><span class="sxs-lookup"><span data-stu-id="58b73-102">CountdownEvent</span></span>
<span data-ttu-id="58b73-103"><xref:System.Threading.CountdownEvent?displayProperty=nameWithType>je synchronizace primitivní, který odblokuje jeho vláken čekání po jejím signalizovala stanovený počet.</span><span class="sxs-lookup"><span data-stu-id="58b73-103"><xref:System.Threading.CountdownEvent?displayProperty=nameWithType> is a synchronization primitive that unblocks its waiting threads after it has been signaled a certain number of times.</span></span> <span data-ttu-id="58b73-104"><xref:System.Threading.CountdownEvent>je určen pro scénáře, ve kterých by jinak musíte použít <xref:System.Threading.ManualResetEvent> nebo <xref:System.Threading.ManualResetEventSlim> a ručně snížení proměnné před signalizace události.</span><span class="sxs-lookup"><span data-stu-id="58b73-104"><xref:System.Threading.CountdownEvent> is designed for scenarios in which you would otherwise have to use a <xref:System.Threading.ManualResetEvent> or <xref:System.Threading.ManualResetEventSlim> and manually decrement a variable before signaling the event.</span></span> <span data-ttu-id="58b73-105">Například v případě rozvětvení/spojení právě vytvořením <xref:System.Threading.CountdownEvent> má signál počet 5, a poté spuštění pět pracovních položek ve vlákně fondu a mít každý pracovní položka volání <xref:System.Threading.CountdownEvent.Signal%2A> po dokončení operace.</span><span class="sxs-lookup"><span data-stu-id="58b73-105">For example, in a fork/join scenario, you can just create a <xref:System.Threading.CountdownEvent> that has a signal count of 5, and then start five work items on the thread pool and have each work item call <xref:System.Threading.CountdownEvent.Signal%2A> when it completes.</span></span> <span data-ttu-id="58b73-106">Každé volání <xref:System.Threading.CountdownEvent.Signal%2A> snižuje počet signál o 1.</span><span class="sxs-lookup"><span data-stu-id="58b73-106">Each call to <xref:System.Threading.CountdownEvent.Signal%2A> decrements the signal count by 1.</span></span> <span data-ttu-id="58b73-107">Na hlavní vlákno volání <xref:System.Threading.CountdownEvent.Wait%2A> se zablokuje, dokud se počet signál je nula.</span><span class="sxs-lookup"><span data-stu-id="58b73-107">On the main thread, the call to <xref:System.Threading.CountdownEvent.Wait%2A> will block until the signal count is zero.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="58b73-108">Pro kód, který nemá k interakci se starší verze rozhraní .NET Framework synchronizace rozhraní API, zvažte použití <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> objekty nebo <xref:System.Threading.Tasks.Parallel.Invoke%2A> metoda bylo ještě jednodušší způsob vyjádření paralelismus rozvětvení spojení.</span><span class="sxs-lookup"><span data-stu-id="58b73-108">For code that does not have to interact with legacy .NET Framework synchronization APIs, consider using <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> objects or the <xref:System.Threading.Tasks.Parallel.Invoke%2A> method for an even easier approach to expressing fork-join parallelism.</span></span>  
  
 <span data-ttu-id="58b73-109"><xref:System.Threading.CountdownEvent>má tyto funkce:</span><span class="sxs-lookup"><span data-stu-id="58b73-109"><xref:System.Threading.CountdownEvent> has these additional features:</span></span>  
  
-   <span data-ttu-id="58b73-110">Zrušit lze pomocí tokenů zrušení operace čekání.</span><span class="sxs-lookup"><span data-stu-id="58b73-110">The wait operation can be canceled by using cancellation tokens.</span></span>  
  
-   <span data-ttu-id="58b73-111">Po vytvoření instance se zvýší počet jeho signál.</span><span class="sxs-lookup"><span data-stu-id="58b73-111">Its signal count can be incremented after the instance is created.</span></span>  
  
-   <span data-ttu-id="58b73-112">Instance lze opětovně použít po <xref:System.Threading.CountdownEvent.Wait%2A> vrátila voláním <xref:System.Threading.CountdownEvent.Reset%2A> metoda.</span><span class="sxs-lookup"><span data-stu-id="58b73-112">Instances can be reused after <xref:System.Threading.CountdownEvent.Wait%2A> has returned by calling the <xref:System.Threading.CountdownEvent.Reset%2A> method.</span></span>  
  
-   <span data-ttu-id="58b73-113">Instance vystavit <xref:System.Threading.WaitHandle> pro integraci v rámci jiné rozhraní .NET Framework synchronizace rozhraní API, jako <xref:System.Threading.WaitHandle.WaitAll%2A>.</span><span class="sxs-lookup"><span data-stu-id="58b73-113">Instances expose a <xref:System.Threading.WaitHandle> for integration with other .NET Framework synchronization APIs such as <xref:System.Threading.WaitHandle.WaitAll%2A>.</span></span>  
  
## <a name="basic-usage"></a><span data-ttu-id="58b73-114">Základní informace o využití</span><span class="sxs-lookup"><span data-stu-id="58b73-114">Basic Usage</span></span>  
 <span data-ttu-id="58b73-115">Následující příklad ukazuje, jak používat <xref:System.Threading.CountdownEvent> s <xref:System.Threading.ThreadPool> pracovní položky.</span><span class="sxs-lookup"><span data-stu-id="58b73-115">The following example demonstrates how to use a <xref:System.Threading.CountdownEvent> with <xref:System.Threading.ThreadPool> work items.</span></span>  
  
 [!code-csharp[CDS_CountdownEvent#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_countdownevent/cs/countdownevent.cs#01)]
 [!code-vb[CDS_CountdownEvent#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_countdownevent/vb/module1.vb#01)]  
  
## <a name="countdownevent-with-cancellation"></a><span data-ttu-id="58b73-116">CountdownEvent s zrušení</span><span class="sxs-lookup"><span data-stu-id="58b73-116">CountdownEvent With Cancellation</span></span>  
 <span data-ttu-id="58b73-117">Následující příklad ukazuje, jak zrušit operace čekání na <xref:System.Threading.CountdownEvent> pomocí tokenu zrušení.</span><span class="sxs-lookup"><span data-stu-id="58b73-117">The following example shows how to cancel the wait operation on <xref:System.Threading.CountdownEvent> by using a cancellation token.</span></span> <span data-ttu-id="58b73-118">Základní vzor odpovídá modelu pro jednotné zrušení, který byl představen v [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="58b73-118">The basic pattern follows the model for unified cancellation, which is introduced in [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="58b73-119">Další informace najdete v tématu [zrušení ve spravovaných vláknech](../../../docs/standard/threading/cancellation-in-managed-threads.md).</span><span class="sxs-lookup"><span data-stu-id="58b73-119">For more information, see [Cancellation in Managed Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md).</span></span>  
  
 [!code-csharp[CDS_CountdownEvent#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_countdownevent/cs/countdownevent.cs#02)]
 [!code-vb[CDS_CountdownEvent#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_countdownevent/vb/canceleventwait.vb#02)]  
  
 <span data-ttu-id="58b73-120">Všimněte si, že operace čekání nezruší vláken, která jsou signalizace.</span><span class="sxs-lookup"><span data-stu-id="58b73-120">Note that the wait operation does not cancel the threads that are signaling it.</span></span> <span data-ttu-id="58b73-121">Obvykle zrušení se použije pro logický provoz a který může obsahovat čekání na událost, jakož i všechny pracovní položky, které se nesynchronizují čekání.</span><span class="sxs-lookup"><span data-stu-id="58b73-121">Typically, cancellation is applied to a logical operation, and that can include waiting on the event as well as all the work items that the wait is synchronizing.</span></span> <span data-ttu-id="58b73-122">V tomto příkladu je každý pracovní položka předán kopii stejný token zrušení, aby mohli odpovídat na žádost o zrušení.</span><span class="sxs-lookup"><span data-stu-id="58b73-122">In this example, each work item is passed a copy of the same cancellation token so that it can respond to the cancellation request.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58b73-123">Viz také</span><span class="sxs-lookup"><span data-stu-id="58b73-123">See Also</span></span>  
 [<span data-ttu-id="58b73-124">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span><span class="sxs-lookup"><span data-stu-id="58b73-124">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span></span>](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)
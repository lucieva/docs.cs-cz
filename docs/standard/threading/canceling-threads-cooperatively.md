---
title: "Spolupráce při rušení vláken"
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
helpviewer_keywords: threads, cancellation
ms.assetid: d2d6d5fd-e263-4fa0-847b-2fc3e0d82337
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 482f48b347af1a4f76231abcb15abc2f4dba168b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="canceling-threads-cooperatively"></a><span data-ttu-id="dbc42-102">Spolupráce při rušení vláken</span><span class="sxs-lookup"><span data-stu-id="dbc42-102">Canceling Threads Cooperatively</span></span>
<span data-ttu-id="dbc42-103">Před verzí [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], rozhraní .NET Framework poskytuje integrované způsob, jak zrušit vlákno spolupráce při po jeho spuštění.</span><span class="sxs-lookup"><span data-stu-id="dbc42-103">Prior to the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], the .NET Framework provided no built-in way to cancel a thread cooperatively after it was started.</span></span> <span data-ttu-id="dbc42-104">Ale v [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], můžete použít zrušení tokenů zrušení vláken, stejně, jako je můžete zrušit <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> objekty nebo dotazy PLINQ.</span><span class="sxs-lookup"><span data-stu-id="dbc42-104">However, in [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], you can use cancellation tokens to cancel threads, just as you can use them to cancel <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> objects or PLINQ queries.</span></span> <span data-ttu-id="dbc42-105">I když <xref:System.Threading.Thread?displayProperty=nameWithType> třída nenabízí integrovanou podporu pro zrušení tokenů, můžete předat token vlákna proceduře pomocí <xref:System.Threading.Thread> konstruktor, který přebírá <xref:System.Threading.ParameterizedThreadStart> delegovat.</span><span class="sxs-lookup"><span data-stu-id="dbc42-105">Although the <xref:System.Threading.Thread?displayProperty=nameWithType> class does not offer built-in support for cancellation tokens, you can pass a token to a thread procedure by using the <xref:System.Threading.Thread> constructor that takes a <xref:System.Threading.ParameterizedThreadStart> delegate.</span></span> <span data-ttu-id="dbc42-106">Následující příklad demonstruje, jak to udělat.</span><span class="sxs-lookup"><span data-stu-id="dbc42-106">The following example demonstrates how to do this.</span></span>  
  
 [!code-csharp[Cancellation#14](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/CooperativeThreads.cs#14)]
 [!code-vb[Cancellation#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/CooperativeThreads.vb#14)]  
  
## <a name="see-also"></a><span data-ttu-id="dbc42-107">Viz také</span><span class="sxs-lookup"><span data-stu-id="dbc42-107">See Also</span></span>  
 [<span data-ttu-id="dbc42-108">Použití vláken a dělení na vlákna</span><span class="sxs-lookup"><span data-stu-id="dbc42-108">Using Threads and Threading</span></span>](../../../docs/standard/threading/using-threads-and-threading.md)
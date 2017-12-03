---
title: System.ServiceModel.TxCompletionStatusAbortedOnSessionClose
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7e142e9d-e81b-4309-974a-02e9cc064ea0
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1e9ab5af359b833452664f534e3627f477246fa6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodeltxcompletionstatusabortedonsessionclose"></a><span data-ttu-id="15337-102">System.ServiceModel.TxCompletionStatusAbortedOnSessionClose</span><span class="sxs-lookup"><span data-stu-id="15337-102">System.ServiceModel.TxCompletionStatusAbortedOnSessionClose</span></span>
<span data-ttu-id="15337-103">Zadaný transakce byla přerušena, protože nebyla při zavření relace a TransactionAutoCompleteOnSessionClose OperationBehaviorAttribute byl nastaven na hodnotu false.</span><span class="sxs-lookup"><span data-stu-id="15337-103">The specified transaction was aborted because it was uncompleted when the session was closed and the TransactionAutoCompleteOnSessionClose OperationBehaviorAttribute was set to false.</span></span>  
  
## <a name="description"></a><span data-ttu-id="15337-104">Popis</span><span class="sxs-lookup"><span data-stu-id="15337-104">Description</span></span>  
 <span data-ttu-id="15337-105">Trasovat, pokud se aktuální aktivní relace bylo ukončeno a transakce nebyla dokončena a TransactionAutoCompleteOnSessionClose je nastaven na `false`.</span><span class="sxs-lookup"><span data-stu-id="15337-105">Traced if the current active session was closed, and the transaction was not completed, and TransactionAutoCompleteOnSessionClose is set to `false`.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="15337-106">Poradce při potížích</span><span class="sxs-lookup"><span data-stu-id="15337-106">Troubleshooting</span></span>  
 <span data-ttu-id="15337-107">Trasování označuje potenciální chybu aplikace, která by se měly prozkoumat.</span><span class="sxs-lookup"><span data-stu-id="15337-107">This trace indicates a potential application bug that should be investigated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15337-108">Viz také</span><span class="sxs-lookup"><span data-stu-id="15337-108">See Also</span></span>  
 [<span data-ttu-id="15337-109">Trasování</span><span class="sxs-lookup"><span data-stu-id="15337-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="15337-110">Řešení potíží s vaší aplikace pomocí trasování</span><span class="sxs-lookup"><span data-stu-id="15337-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="15337-111">Správa a Diagnostika</span><span class="sxs-lookup"><span data-stu-id="15337-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
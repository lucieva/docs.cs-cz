---
title: "Postupy: Určení verze zjišťování zkušebního požadavku"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b3c4e2e2-2957-4074-ae6a-776a5ca84278
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2ff5d45997456c12d0292176771ad3c332f6c043
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-todetermine-the-discovery-version-of-a-probe-request"></a><span data-ttu-id="f9a05-102">Postupy: Určení verze zjišťování zkušebního požadavku</span><span class="sxs-lookup"><span data-stu-id="f9a05-102">How to:Determine the Discovery Version of a Probe Request</span></span>
<span data-ttu-id="f9a05-103">Zjišťování proxy vystavuje několik koncových bodů zjišťování pomocí různých zjišťování verze.</span><span class="sxs-lookup"><span data-stu-id="f9a05-103">A discovery proxy may expose multiple discovery endpoints using different discovery versions.</span></span> <span data-ttu-id="f9a05-104">Když UDP, vícesměrového vysílání zkušebního požadavku dorazí na proxy server, které proxy server by měl odpovídat zprávy vícesměrového vysílání potlačení.</span><span class="sxs-lookup"><span data-stu-id="f9a05-104">When a UDP multicast Probe request arrives at the proxy the proxy should respond with a multicast suppression message.</span></span> <span data-ttu-id="f9a05-105">Pokud to chcete provést by mít vědět verze zjišťování požadavku.</span><span class="sxs-lookup"><span data-stu-id="f9a05-105">In order to do this it would have to know the discovery version of the request.</span></span>  
  
### <a name="to-determine-the-discovery-version-of-a-probe-request"></a><span data-ttu-id="f9a05-106">Určení verze zjišťování zkušebního požadavku</span><span class="sxs-lookup"><span data-stu-id="f9a05-106">To Determine the Discovery Version of a Probe Request</span></span>  
  
1.  <span data-ttu-id="f9a05-107">V metodě odpoví na žádost o test (třeba <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A>) použít statickou <xref:System.ServiceModel.OperationContext.Current%2A> vlastnost k vyhledání <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension> jak je znázorněno v následujícím kódu.</span><span class="sxs-lookup"><span data-stu-id="f9a05-107">In the method that responds to a Probe request (for example <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A>) use the static <xref:System.ServiceModel.OperationContext.Current%2A> property to search for a <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension> as shown in the following code.</span></span>  
  
    ```  
    DiscoveryOperationContextExtension doce = OperationContext.Current.Extensions.Find<DiscoveryOperationContextExtension>();  
    // Access the discovery version from the DiscoveryOperationContextExtension  
    doce.DiscoveryVersion;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f9a05-108">Viz také</span><span class="sxs-lookup"><span data-stu-id="f9a05-108">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion%2A>  
 [<span data-ttu-id="f9a05-109">Implementace Proxy zjišťování</span><span class="sxs-lookup"><span data-stu-id="f9a05-109">Implementing a Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/implementing-a-discovery-proxy.md)  
 [<span data-ttu-id="f9a05-110">Ukázka proxy serveru zjišťování</span><span class="sxs-lookup"><span data-stu-id="f9a05-110">Discovery Proxy Sample</span></span>](../../../../docs/framework/wcf/samples/discovery-proxy-sample.md)
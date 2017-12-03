---
title: "Používání vazeb NetHttpBinding"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fe134acf-ceca-49de-84a9-05a37e3841f1
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 56528078895ea7c624afaf716e9a26eabe335d69
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="using-the-nethttpbinding"></a><span data-ttu-id="224c5-102">Používání vazeb NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="224c5-102">Using the NetHttpBinding</span></span>
<span data-ttu-id="224c5-103"><xref:System.ServiceModel.NetHttpBinding>používá binární kódování ve výchozím nastavení je vazbu pro využívání služeb HTTP nebo protokolu WebSocket.</span><span class="sxs-lookup"><span data-stu-id="224c5-103"><xref:System.ServiceModel.NetHttpBinding> is a binding designed for consuming HTTP or WebSocket services and uses binary encoding by default.</span></span> <span data-ttu-id="224c5-104"><xref:System.ServiceModel.NetHttpBinding>rozpozná, jestli se používá s kontraktu požadavku a odpovědi nebo duplexního kontraktu a změnit své chování tak, aby odpovídaly – použije HTTP pro kontraktů požadavek odpověď a WebSockets pro duplexní kontrakty.</span><span class="sxs-lookup"><span data-stu-id="224c5-104"><xref:System.ServiceModel.NetHttpBinding> will detect whether it is used with a request-reply contract or duplex contract and change its behavior to match - it will use HTTP for request-reply contracts and WebSockets for duplex contracts.</span></span> <span data-ttu-id="224c5-105">Toto chování lze přepsat pomocí <!--zz <xref:System.ServiceModel.NetHttpBinding.WebSocketTransportUsage%2A> --> `WebSocketTransportUsage` nastavení:</span><span class="sxs-lookup"><span data-stu-id="224c5-105">This behavior can be overridden using the <!--zz <xref:System.ServiceModel.NetHttpBinding.WebSocketTransportUsage%2A> --> `WebSocketTransportUsage` setting:</span></span>  
  
1.  <span data-ttu-id="224c5-106">Vždy - vynutí objekty WebSockets použije i pro kontraktů požadavek odpověď.</span><span class="sxs-lookup"><span data-stu-id="224c5-106">Always - This forces WebSockets to be used even for request-reply contracts.</span></span>  
  
2.  <span data-ttu-id="224c5-107">Nikdy – to zabraňuje objekty WebSockets.</span><span class="sxs-lookup"><span data-stu-id="224c5-107">Never - This prevents WebSockets from being used.</span></span> <span data-ttu-id="224c5-108">Pokus o použití duplexního kontraktu s tímto nastavením bude mít za následek výjimku.</span><span class="sxs-lookup"><span data-stu-id="224c5-108">Attempting to use a duplex contract with this setting will result in an exception.</span></span>  
  
3.  <span data-ttu-id="224c5-109">WhenDuplex - Toto je výchozí hodnota a chová, jak je popsáno výše.</span><span class="sxs-lookup"><span data-stu-id="224c5-109">WhenDuplex - This is the default value and behaves as described above.</span></span>  
  
 <span data-ttu-id="224c5-110"><xref:System.ServiceModel.NetHttpBinding>podporuje spolehlivé relace v HTTP režimu i režimu protokolu WebSocket.</span><span class="sxs-lookup"><span data-stu-id="224c5-110"><xref:System.ServiceModel.NetHttpBinding> supports reliable sessions in both HTTP mode and WebSocket mode.</span></span> <span data-ttu-id="224c5-111">V protokolu WebSocket relace režimu jsou poskytovány přenosu.</span><span class="sxs-lookup"><span data-stu-id="224c5-111">In WebSocket mode sessions are provided by the transport.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="224c5-112">Při použití <xref:System.ServiceModel.NetHttpBinding> a TransferMode vazby nastavena na TransferMode.Streamed, velké datové proudy může způsobit zablokování a bude časový limit volání.</span><span class="sxs-lookup"><span data-stu-id="224c5-112">When using the <xref:System.ServiceModel.NetHttpBinding> and the binding’s TransferMode is set to TransferMode.Streamed, large streams may cause a deadlock and the call will timeout.</span></span> <span data-ttu-id="224c5-113">Chcete vyřešit tento problém odesílat menší zprávy nebo použít třídy TransferMode.Buffered.</span><span class="sxs-lookup"><span data-stu-id="224c5-113">To work around this issue send smaller messages or use TransferMode.Buffered.</span></span>  
  
## <a name="configuring-a-service-to-use-nethttpbinding"></a><span data-ttu-id="224c5-114">Konfigurace služby pro použití NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="224c5-114">Configuring a Service to use NetHttpBinding</span></span>  
 <span data-ttu-id="224c5-115"><xref:System.ServiceModel.NetHttpBinding> Může být nakonfigurované stejně jako jakákoli jiná vazba.</span><span class="sxs-lookup"><span data-stu-id="224c5-115">The <xref:System.ServiceModel.NetHttpBinding> can be configured the same as any other binding.</span></span> <span data-ttu-id="224c5-116">Následující fragment kódu konfigurace znázorňuje, jak nakonfigurovat služby WCF s <xref:System.ServiceModel.NetHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="224c5-116">The following configuration snippet illustrates how to configure a WCF service with <xref:System.ServiceModel.NetHttpBinding>.</span></span>  
  
```xml  
<system.serviceModel>  
    <services>  
      <service name="WcfService1.Service1">  
        <endpoint address=""  
                  binding="netHttpBinding"  
                  contract="WcfService1.IService1"/>  
        <endpoint address="mex"  
                  binding="mexHttpBinding"  
                  contract="IMetadataExchange"/>  
      </service>  
    </services>  
    <bindings>  
      <netHttpBinding>  
        <binding name="My_NetHttpBindingConfig">  
          <webSocketSettings transportUsage="WhenDuplex"/>  
        </binding>  
      </netHttpBinding>  
    </bindings>  
    <!- ... -->   
  </system.serviceModel>  
```  
  
 <span data-ttu-id="224c5-117">Následující fragment kódu ukazuje, jak přidat <xref:System.ServiceModel.NetHttpBinding> v kódu.</span><span class="sxs-lookup"><span data-stu-id="224c5-117">The following code snippet shows how to add the <xref:System.ServiceModel.NetHttpBinding> in code.</span></span>  
  
```csharp  
ServiceHost svchost = new ServiceHost(typeof(Service1), baseAddress);  
            NetHttpBinding binding = new NetHttpBinding();  
            svchost.AddServiceEndpoint(typeof(IService1), binding, address);   
        }  
```  
  
## <a name="see-also"></a><span data-ttu-id="224c5-118">Viz také</span><span class="sxs-lookup"><span data-stu-id="224c5-118">See Also</span></span>  
 [<span data-ttu-id="224c5-119">Konfigurace vazeb pro služby</span><span class="sxs-lookup"><span data-stu-id="224c5-119">Configuring Bindings for Services</span></span>](../../../../docs/framework/wcf/configuring-bindings-for-wcf-services.md)  
 [<span data-ttu-id="224c5-120">Vazby</span><span class="sxs-lookup"><span data-stu-id="224c5-120">Bindings</span></span>](../../../../docs/framework/wcf/feature-details/bindings.md)  
 [<span data-ttu-id="224c5-121">Vazby poskytované systémem</span><span class="sxs-lookup"><span data-stu-id="224c5-121">System-Provided Bindings</span></span>](../../../../docs/framework/wcf/system-provided-bindings.md)  
 [<span data-ttu-id="224c5-122">Duplexní služby</span><span class="sxs-lookup"><span data-stu-id="224c5-122">Duplex Services</span></span>](../../../../docs/framework/wcf/feature-details/duplex-services.md)
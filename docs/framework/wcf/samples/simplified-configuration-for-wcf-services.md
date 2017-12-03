---
title: "Zjednodušená konfigurace pro služby WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1e39ec25-18a3-4fdc-b6a3-9dfafbd60112
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2167b1709ed8db0be76a330eaf72d6d52445fd1b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="simplified-configuration-for-wcf-services"></a><span data-ttu-id="ec87a-102">Zjednodušená konfigurace pro služby WCF</span><span class="sxs-lookup"><span data-stu-id="ec87a-102">Simplified Configuration for WCF Services</span></span>
<span data-ttu-id="ec87a-103">Tento příklad ukazuje, jak implementovat a nastavení typické služby a klienta pomocí [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ec87a-103">This sample demonstrates how to implement and configure a typical service and client using [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span> <span data-ttu-id="ec87a-104">Tato ukázka je základem pro všechny ostatní vzorky základní technologie.</span><span class="sxs-lookup"><span data-stu-id="ec87a-104">This sample is the basis for all other basic technology samples.</span></span>  
  
 <span data-ttu-id="ec87a-105">Tato služba, která zpřístupňuje koncový bod pro komunikaci se službou, používá zjednodušená konfigurace v [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ec87a-105">This service, which exposes an endpoint for communicating with the service, uses the simplified configuration in [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)].</span></span> <span data-ttu-id="ec87a-106">Před verzí [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)], koncový bod je obvykle definováno v konfiguračním souboru (Web.config), jak je znázorněno v následujícím příkladu kódu konfigurace.</span><span class="sxs-lookup"><span data-stu-id="ec87a-106">Prior to [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)], the endpoint is typically defined in a configuration file (Web.config), as shown in the following example configuration code.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<!-- Copyright ©) Microsoft Corporation.  All Rights Reserved. -->  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="CalculatorServiceBehavior">  
          <serviceMetadata httpGetEnabled="True"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service name="Microsoft.Samples.GettingStarted.CalculatorService"  
               behaviorConfiguration="CalculatorServiceBehavior">  
        <endpoint address="" binding="basicHttpBinding" contract="ICalculator"/>  
        <endpoint address="mex" binding="mexHttpBinding" contract="IMetadataExchange"/>  
      </service>  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="ec87a-107">V [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)], `<service>` prvek je volitelný.</span><span class="sxs-lookup"><span data-stu-id="ec87a-107">In [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)], the `<service>` element is optional.</span></span> <span data-ttu-id="ec87a-108">Pokud služby nedefinuje žádné koncové body, koncový bod pro každou základní adresa a kontrakt implementována jsou přidány do služby.</span><span class="sxs-lookup"><span data-stu-id="ec87a-108">When a service does not define any endpoints, an endpoint for each base address and contract implemented are added to the service.</span></span> <span data-ttu-id="ec87a-109">Základní adresa je přidán do názvu kontraktu určit koncový bod a vazba je dáno schéma adresy.</span><span class="sxs-lookup"><span data-stu-id="ec87a-109">The base address is appended to the contract name to determine the endpoint and the binding is determined by the address scheme.</span></span> <span data-ttu-id="ec87a-110">Následující příklad kódu ukazuje zjednodušené konfigurační soubor.</span><span class="sxs-lookup"><span data-stu-id="ec87a-110">The following code example demonstrates a simplified configuration file.</span></span> <span data-ttu-id="ec87a-111">Podle konfigurace, služba je přístupná na http://localhost/servicemodelsamples/service.svc klientem na stejném počítači.</span><span class="sxs-lookup"><span data-stu-id="ec87a-111">As configured, the service can be accessed at http://localhost/servicemodelsamples/service.svc by a client on the same computer.</span></span> <span data-ttu-id="ec87a-112">Pro klienty ve vzdálených počítačích pro přístup ke službě musí zadat název plně kvalifikované domény místo localhost.</span><span class="sxs-lookup"><span data-stu-id="ec87a-112">For clients on remote computers to access the service, a fully-qualified domain name must be specified instead of localhost.</span></span> <span data-ttu-id="ec87a-113">Služba nevystavuje metadata ve výchozím nastavení.</span><span class="sxs-lookup"><span data-stu-id="ec87a-113">The service does not expose metadata by default.</span></span> <span data-ttu-id="ec87a-114">Jako takový službu Zapne <xref:System.ServiceModel.Description.ServiceMetadataBehavior> chování.</span><span class="sxs-lookup"><span data-stu-id="ec87a-114">As such, the service turns on the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> behavior.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<!-- Copyright © Microsoft Corporation.  All Rights Reserved. -->  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="">  
          <serviceMetadata httpGetEnabled="True"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
### <a name="to-use-this-sample"></a><span data-ttu-id="ec87a-115">Pro fungování této ukázky</span><span class="sxs-lookup"><span data-stu-id="ec87a-115">To use this sample</span></span>  
  
1.  <span data-ttu-id="ec87a-116">Ujistěte se, že jste provedli [jednorázové postup nastavení pro ukázky Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ec87a-116">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="ec87a-117">Sestavte řešení, postupujte podle pokynů v [vytváření ukázky Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ec87a-117">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="ec87a-118">Spusťte ukázku pomocí následujících kroků:</span><span class="sxs-lookup"><span data-stu-id="ec87a-118">Run the sample by following these steps:</span></span>  
  
    1.  <span data-ttu-id="ec87a-119">Klikněte pravým tlačítkem **služby** projektu a vyberte **nastavit jako spouštěný projekt**, stiskněte **Ctrl + F5**.</span><span class="sxs-lookup"><span data-stu-id="ec87a-119">Right click the **Service** project and select **Set as StartUp project**, then press **Ctrl+F5**.</span></span>  
  
    2.  <span data-ttu-id="ec87a-120">Počkejte, až bude výstup konzoly potvrdí, že služba nahoru a spuštěna.</span><span class="sxs-lookup"><span data-stu-id="ec87a-120">Wait for the console output confirming that the service is up and running.</span></span>  
  
    3.  <span data-ttu-id="ec87a-121">Klikněte pravým tlačítkem **klienta** projektu a vyberte **nastavit jako spouštěný projekt**, stiskněte **Ctrl + F5**.</span><span class="sxs-lookup"><span data-stu-id="ec87a-121">Right click the **Client** project and select **Set as StartUp project**, then press **Ctrl+F5**.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ec87a-122">Ukázky může být již nainstalován ve vašem počítači.</span><span class="sxs-lookup"><span data-stu-id="ec87a-122">The samples may already be installed on your computer.</span></span> <span data-ttu-id="ec87a-123">Před pokračováním zkontrolovat na následující adresář (výchozí).</span><span class="sxs-lookup"><span data-stu-id="ec87a-123">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ec87a-124">Pokud tento adresář neexistuje, přejděte na [Windows Communication Foundation (WCF) a ukázky Windows Workflow Foundation (WF) pro rozhraní .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) ke stažení všechny [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] a [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ukázky.</span><span class="sxs-lookup"><span data-stu-id="ec87a-124">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ec87a-125">Tato ukázka se nachází v následujícím adresáři.</span><span class="sxs-lookup"><span data-stu-id="ec87a-125">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigSimplificationIn40`  
  
## <a name="see-also"></a><span data-ttu-id="ec87a-126">Viz také</span><span class="sxs-lookup"><span data-stu-id="ec87a-126">See Also</span></span>  
 [<span data-ttu-id="ec87a-127">Ukázky správy AppFabric</span><span class="sxs-lookup"><span data-stu-id="ec87a-127">AppFabric Management Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193960)  
 [<span data-ttu-id="ec87a-128">Zjednodušená konfigurace</span><span class="sxs-lookup"><span data-stu-id="ec87a-128">Simplified Configuration</span></span>](../../../../docs/framework/wcf/simplified-configuration.md)
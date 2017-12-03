---
title: "Nezabezpečený internetový klient a služba"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 97a10d79-3e7d-4bd1-9a99-fd9807fd70bc
caps.latest.revision: "17"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: cd7cc9da457424dede6f62ecefca8cee0d94fb88
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="internet-unsecured-client-and-service"></a><span data-ttu-id="44ca8-102">Nezabezpečený internetový klient a služba</span><span class="sxs-lookup"><span data-stu-id="44ca8-102">Internet Unsecured Client and Service</span></span>
<span data-ttu-id="44ca8-103">Následující obrázek znázorňuje příklad veřejné, nezabezpečenou [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] klienta a služby.</span><span class="sxs-lookup"><span data-stu-id="44ca8-103">The following illustration shows an example of a public, unsecured [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] client and service.</span></span>  
  
 <span data-ttu-id="44ca8-104">![Zabezpečená scénář cleint a služby Internet](../../../../docs/framework/wcf/feature-details/media/publicunsecured.gif "publicUnsecured")</span><span class="sxs-lookup"><span data-stu-id="44ca8-104">![Unsecured Internet cleint and service scenario](../../../../docs/framework/wcf/feature-details/media/publicunsecured.gif "publicUnsecured")</span></span>  
  
|<span data-ttu-id="44ca8-105">Vlastnosti</span><span class="sxs-lookup"><span data-stu-id="44ca8-105">Characteristic</span></span>|<span data-ttu-id="44ca8-106">Popis</span><span class="sxs-lookup"><span data-stu-id="44ca8-106">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="44ca8-107">Režim zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="44ca8-107">Security Mode</span></span>|<span data-ttu-id="44ca8-108">Žádné</span><span class="sxs-lookup"><span data-stu-id="44ca8-108">None</span></span>|  
|<span data-ttu-id="44ca8-109">Přenos</span><span class="sxs-lookup"><span data-stu-id="44ca8-109">Transport</span></span>|<span data-ttu-id="44ca8-110">HTTP</span><span class="sxs-lookup"><span data-stu-id="44ca8-110">HTTP</span></span>|  
|<span data-ttu-id="44ca8-111">Vazba</span><span class="sxs-lookup"><span data-stu-id="44ca8-111">Binding</span></span>|<span data-ttu-id="44ca8-112"><xref:System.ServiceModel.BasicHttpBinding>v kódu nebo [ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) element v konfiguraci.</span><span class="sxs-lookup"><span data-stu-id="44ca8-112"><xref:System.ServiceModel.BasicHttpBinding> in code, or the [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) element in configuration.</span></span>|  
|<span data-ttu-id="44ca8-113">Interoperabilita</span><span class="sxs-lookup"><span data-stu-id="44ca8-113">Interoperability</span></span>|<span data-ttu-id="44ca8-114">S existující klienty webové služby a služby</span><span class="sxs-lookup"><span data-stu-id="44ca8-114">With existing Web service clients and services</span></span>|  
|<span data-ttu-id="44ca8-115">Ověřování</span><span class="sxs-lookup"><span data-stu-id="44ca8-115">Authentication</span></span>|<span data-ttu-id="44ca8-116">Žádné</span><span class="sxs-lookup"><span data-stu-id="44ca8-116">None</span></span>|  
|<span data-ttu-id="44ca8-117">Integrita</span><span class="sxs-lookup"><span data-stu-id="44ca8-117">Integrity</span></span>|<span data-ttu-id="44ca8-118">Žádné</span><span class="sxs-lookup"><span data-stu-id="44ca8-118">None</span></span>|  
|<span data-ttu-id="44ca8-119">Důvěrnost</span><span class="sxs-lookup"><span data-stu-id="44ca8-119">Confidentiality</span></span>|<span data-ttu-id="44ca8-120">Žádné</span><span class="sxs-lookup"><span data-stu-id="44ca8-120">None</span></span>|  
  
## <a name="service"></a><span data-ttu-id="44ca8-121">Služba</span><span class="sxs-lookup"><span data-stu-id="44ca8-121">Service</span></span>  
 <span data-ttu-id="44ca8-122">Následující kód a konfigurace jsou určená ke spuštění nezávisle.</span><span class="sxs-lookup"><span data-stu-id="44ca8-122">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="44ca8-123">Proveďte jednu z těchto akcí:</span><span class="sxs-lookup"><span data-stu-id="44ca8-123">Do one of the following:</span></span>  
  
-   <span data-ttu-id="44ca8-124">Vytvořte samostatnou službu pomocí kódu žádnou konfiguraci.</span><span class="sxs-lookup"><span data-stu-id="44ca8-124">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="44ca8-125">Vytvoření služby pomocí zadaných konfigurací, ale nejsou definovány žádné koncové body.</span><span class="sxs-lookup"><span data-stu-id="44ca8-125">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="44ca8-126">Kód</span><span class="sxs-lookup"><span data-stu-id="44ca8-126">Code</span></span>  
 <span data-ttu-id="44ca8-127">Následující kód ukazuje, jak vytvořit koncový bod se zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="44ca8-127">The following code shows how to create an endpoint with no security.</span></span> <span data-ttu-id="44ca8-128">Ve výchozím nastavení <xref:System.ServiceModel.BasicHttpBinding> má režim zabezpečení nastavený na <xref:System.ServiceModel.BasicHttpSecurityMode.None>.</span><span class="sxs-lookup"><span data-stu-id="44ca8-128">By default, the <xref:System.ServiceModel.BasicHttpBinding> has the security mode set to <xref:System.ServiceModel.BasicHttpSecurityMode.None>.</span></span>  
  
 [!code-csharp[C_UnsecuredService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredservice/cs/source.cs#1)]
 [!code-vb[C_UnsecuredService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredservice/vb/source.vb#1)]  
  
### <a name="service-configuration"></a><span data-ttu-id="44ca8-129">Konfigurace služby</span><span class="sxs-lookup"><span data-stu-id="44ca8-129">Service Configuration</span></span>  
 <span data-ttu-id="44ca8-130">Následující kód nastaví stejný koncový bod pomocí konfigurace.</span><span class="sxs-lookup"><span data-stu-id="44ca8-130">The following code sets up the same endpoint using configuration.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors />  
    <services>  
      <service behaviorConfiguration="" name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"   
                  binding="basicHttpBinding"  
                  bindingConfiguration="Basic_Unsecured"   
                  name="BasicHttp_ICalculator"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <basicHttpBinding>  
        <binding name="Basic_Unsecured" />  
      </basicHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="44ca8-131">Klient</span><span class="sxs-lookup"><span data-stu-id="44ca8-131">Client</span></span>  
 <span data-ttu-id="44ca8-132">Následující kód a konfigurace jsou určená ke spuštění nezávisle.</span><span class="sxs-lookup"><span data-stu-id="44ca8-132">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="44ca8-133">Proveďte jednu z těchto akcí:</span><span class="sxs-lookup"><span data-stu-id="44ca8-133">Do one of the following:</span></span>  
  
-   <span data-ttu-id="44ca8-134">Vytvořte samostatnou klienta pomocí kódu (a kód klienta).</span><span class="sxs-lookup"><span data-stu-id="44ca8-134">Create a stand-alone client using the code (and client code).</span></span>  
  
-   <span data-ttu-id="44ca8-135">Vytvoření klienta, které nejsou definovány žádné adresy koncových bodů.</span><span class="sxs-lookup"><span data-stu-id="44ca8-135">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="44ca8-136">Místo toho použijte konstruktor klienta, který přijímá jako argument Název konfigurace.</span><span class="sxs-lookup"><span data-stu-id="44ca8-136">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="44ca8-137">Příklad:</span><span class="sxs-lookup"><span data-stu-id="44ca8-137">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="44ca8-138">Kód</span><span class="sxs-lookup"><span data-stu-id="44ca8-138">Code</span></span>  
 <span data-ttu-id="44ca8-139">Následující kód ukazuje základní [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] klienta, který přistupuje k zabezpečená koncový bod.</span><span class="sxs-lookup"><span data-stu-id="44ca8-139">The following code shows a basic [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client that accesses an unsecured endpoint.</span></span>  
  
 [!code-csharp[C_UnsecuredClient#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredclient/cs/source.cs#1)]
 [!code-vb[C_UnsecuredClient#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredclient/vb/source.vb#1)]  
  
### <a name="client-configuration"></a><span data-ttu-id="44ca8-140">Konfigurace klienta</span><span class="sxs-lookup"><span data-stu-id="44ca8-140">Client Configuration</span></span>  
 <span data-ttu-id="44ca8-141">Následující kód konfiguruje klienta.</span><span class="sxs-lookup"><span data-stu-id="44ca8-141">The following code configures the client.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <basicHttpBinding>  
        <binding name="BasicHttpBinding_ICalculator" >  
          <security mode="None">  
          </security>  
        </binding>  
      </basicHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="http://localhost/Calculator/Unsecured"  
          binding="basicHttpBinding"   
          bindingConfiguration="BasicHttpBinding_ICalculator"  
          contract="ICalculator"   
          name="BasicHttpBinding_ICalculator" />  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="44ca8-142">Viz také</span><span class="sxs-lookup"><span data-stu-id="44ca8-142">See Also</span></span>  
 [<span data-ttu-id="44ca8-143">Běžné scénáře zabezpečení</span><span class="sxs-lookup"><span data-stu-id="44ca8-143">Common Security Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
 [<span data-ttu-id="44ca8-144">Přehled zabezpečení</span><span class="sxs-lookup"><span data-stu-id="44ca8-144">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="44ca8-145">Model zabezpečení pro Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="44ca8-145">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
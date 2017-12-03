---
title: '&lt;netPeerTcpBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: netPeerBinding element
ms.assetid: 2dd77ada-a176-47c7-a740-900b279f1aad
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 35dfb3eee5a01d5fed21bda59f1cab5eb09a1401
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/02/2017
---
# <a name="ltnetpeertcpbindinggt"></a><span data-ttu-id="a7941-102">&lt;netPeerTcpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="a7941-102">&lt;netPeerTcpBinding&gt;</span></span>
<span data-ttu-id="a7941-103">Definuje vazbu pro sdílené kanál konkrétní TCP zasílání zpráv.</span><span class="sxs-lookup"><span data-stu-id="a7941-103">Defines a binding for peer channel specific TCP messaging.</span></span>  
  
 <span data-ttu-id="a7941-104">\<systém. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="a7941-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="a7941-105">\<vazby ></span><span class="sxs-lookup"><span data-stu-id="a7941-105">\<bindings></span></span>  
<span data-ttu-id="a7941-106">\<netPeerTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="a7941-106">\<netPeerTcpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7941-107">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="a7941-107">Syntax</span></span>  
  
```xml  
<netPeerBinding>  
    <binding name="string"  
         closeTimeout="TimeSpan"  
         openTimeout="TimeSpan"   
         receiveTimeout="TimeSpan"  
         sendTimeout="TimeSpan"  
         listenIPAddress="String"  
          maxBufferPoolSize="integer"  
         maxReceiveMessageSize="Integer"   
         port="Integer"  
         <security mode="None/Transport/Message/TransportWithMessageCredential">  
            <transport credentialType="Certificate/Password" />  
        </security>  
    </binding>  
</netPeerBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a7941-108">Atributy a elementy</span><span class="sxs-lookup"><span data-stu-id="a7941-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a7941-109">Následující části popisují nadřazené elementy, atributy a podřízené elementy</span><span class="sxs-lookup"><span data-stu-id="a7941-109">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a7941-110">Atributy</span><span class="sxs-lookup"><span data-stu-id="a7941-110">Attributes</span></span>  
  
|<span data-ttu-id="a7941-111">Atribut</span><span class="sxs-lookup"><span data-stu-id="a7941-111">Attribute</span></span>|<span data-ttu-id="a7941-112">Popis</span><span class="sxs-lookup"><span data-stu-id="a7941-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a7941-113">Intervalu</span><span class="sxs-lookup"><span data-stu-id="a7941-113">closeTimeout</span></span>|<span data-ttu-id="a7941-114">A <xref:System.TimeSpan> hodnotu, která určuje interval čas zadaný pro dokončení operace uzavření.</span><span class="sxs-lookup"><span data-stu-id="a7941-114">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="a7941-115">Tato hodnota by měla být větší než nebo rovna hodnotě <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="a7941-115">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="a7941-116">Výchozí hodnota je 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="a7941-116">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="a7941-117">ListenIPAddress</span><span class="sxs-lookup"><span data-stu-id="a7941-117">listenIPAddress</span></span>|<span data-ttu-id="a7941-118">Řetězec, který určuje IP adresu, na kterém bude uzlu sdílené naslouchat zpráv TCP.</span><span class="sxs-lookup"><span data-stu-id="a7941-118">A string that specifies an IP address on which the peer node will listen for TCP messages.</span></span> <span data-ttu-id="a7941-119">Výchozí hodnota je `null`.</span><span class="sxs-lookup"><span data-stu-id="a7941-119">The default is `null`.</span></span>|  
|<span data-ttu-id="a7941-120">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="a7941-120">maxBufferPoolSize</span></span>|<span data-ttu-id="a7941-121">Celé číslo, které určuje velikost fondu maximální vyrovnávací paměti pro tuto vazbu.</span><span class="sxs-lookup"><span data-stu-id="a7941-121">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="a7941-122">Výchozí hodnota je 524,288 bajtů (512 * 1024).</span><span class="sxs-lookup"><span data-stu-id="a7941-122">The default is 524,288 bytes (512 * 1024).</span></span> <span data-ttu-id="a7941-123">Mnoho části služby Windows Communication Foundation (WCF) pomocí vyrovnávací paměti.</span><span class="sxs-lookup"><span data-stu-id="a7941-123">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="a7941-124">Vytváření a zničení pokaždé, když se používají vyrovnávací paměti je nákladné a uvolňování paměti pro vyrovnávací paměti je také nákladné.</span><span class="sxs-lookup"><span data-stu-id="a7941-124">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="a7941-125">S fondy vyrovnávací paměti můžete provést vyrovnávací paměti z fondu, ho použít a po dokončení se vraťte do fondu.</span><span class="sxs-lookup"><span data-stu-id="a7941-125">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="a7941-126">Proto je předejde režijní náklady v vytváření a zničení vyrovnávací paměti.</span><span class="sxs-lookup"><span data-stu-id="a7941-126">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="a7941-127">MaxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="a7941-127">maxReceivedMessageSize</span></span>|<span data-ttu-id="a7941-128">Kladné celé číslo, které určuje maximální velikost zprávy, v bajtech, včetně hlavičky, které můžou přijímat na kanál nakonfigurovaným s touto vazbou.</span><span class="sxs-lookup"><span data-stu-id="a7941-128">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="a7941-129">Odesílatel zprávy překročení tohoto limitu obdrží chybu protokolu SOAP.</span><span class="sxs-lookup"><span data-stu-id="a7941-129">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="a7941-130">Příjemce zahodí zprávy a vytvoří položku události v protokolu trasování.</span><span class="sxs-lookup"><span data-stu-id="a7941-130">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="a7941-131">Výchozí hodnota je 65536.</span><span class="sxs-lookup"><span data-stu-id="a7941-131">The default is 65536.</span></span>|  
|<span data-ttu-id="a7941-132">name</span><span class="sxs-lookup"><span data-stu-id="a7941-132">name</span></span>|<span data-ttu-id="a7941-133">Řetězec, který obsahuje název konfigurace vazby.</span><span class="sxs-lookup"><span data-stu-id="a7941-133">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="a7941-134">Tato hodnota musí být jedinečný, protože je používán jako identifikaci pro vazbu.</span><span class="sxs-lookup"><span data-stu-id="a7941-134">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="a7941-135">Počínaje [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], vazby a chování nemusí mít název.</span><span class="sxs-lookup"><span data-stu-id="a7941-135">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="a7941-136">Další informace o výchozí konfigurace a nameless vazby a chování najdete v tématu [zjednodušená konfigurace](../../../../../docs/framework/wcf/simplified-configuration.md) a [zjednodušená konfigurace pro služby WCF](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="a7941-136">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="a7941-137">openTimeout</span><span class="sxs-lookup"><span data-stu-id="a7941-137">openTimeout</span></span>|<span data-ttu-id="a7941-138">A <xref:System.TimeSpan> hodnotu, která určuje interval čas zadaný pro otevřete na dokončení operace.</span><span class="sxs-lookup"><span data-stu-id="a7941-138">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="a7941-139">Tato hodnota by měla být větší než nebo rovna hodnotě <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="a7941-139">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="a7941-140">Výchozí hodnota je 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="a7941-140">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="a7941-141">port</span><span class="sxs-lookup"><span data-stu-id="a7941-141">port</span></span>|<span data-ttu-id="a7941-142">Celé číslo, které určuje, na které tato vazba zpracuje rovnocenné zprávy TCP port síťového rozhraní.</span><span class="sxs-lookup"><span data-stu-id="a7941-142">An integer that specifies the network interface port on which this binding will process peer channel TCP messages.</span></span> <span data-ttu-id="a7941-143">Tato hodnota musí být mezi <xref:System.Net.IPEndPoint.MinPort> a <xref:System.Net.IPEndPoint.MaxPort>.</span><span class="sxs-lookup"><span data-stu-id="a7941-143">This value must be between <xref:System.Net.IPEndPoint.MinPort> and <xref:System.Net.IPEndPoint.MaxPort>.</span></span> <span data-ttu-id="a7941-144">Výchozí hodnota je 0.</span><span class="sxs-lookup"><span data-stu-id="a7941-144">The default is 0.</span></span>|  
|<span data-ttu-id="a7941-145">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="a7941-145">receiveTimeout</span></span>|<span data-ttu-id="a7941-146">A <xref:System.TimeSpan> hodnotu, která určuje interval čas zadaný pro na dokončení operace příjmu.</span><span class="sxs-lookup"><span data-stu-id="a7941-146">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="a7941-147">Tato hodnota by měla být větší než nebo rovna hodnotě <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="a7941-147">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="a7941-148">Výchozí hodnota je 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="a7941-148">The default is 00:10:00.</span></span>|  
|<span data-ttu-id="a7941-149">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="a7941-149">sendTimeout</span></span>|<span data-ttu-id="a7941-150">A <xref:System.TimeSpan> hodnotu, která určuje interval čas zadaný pro dokončení operace odeslání.</span><span class="sxs-lookup"><span data-stu-id="a7941-150">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="a7941-151">Tato hodnota by měla být větší než nebo rovna hodnotě <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="a7941-151">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="a7941-152">Výchozí hodnota je 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="a7941-152">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a7941-153">Podřízené elementy</span><span class="sxs-lookup"><span data-stu-id="a7941-153">Child Elements</span></span>  
  
|<span data-ttu-id="a7941-154">Prvek</span><span class="sxs-lookup"><span data-stu-id="a7941-154">Element</span></span>|<span data-ttu-id="a7941-155">Popis</span><span class="sxs-lookup"><span data-stu-id="a7941-155">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a7941-156">\<readerQuotas ></span><span class="sxs-lookup"><span data-stu-id="a7941-156">\<readerQuotas></span></span>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="a7941-157">Definuje omezení na složitosti protokolu SOAP zprávy, které lze zpracovat koncovými body, které jsou konfigurovány pomocí této vazby.</span><span class="sxs-lookup"><span data-stu-id="a7941-157">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="a7941-158">Tento element je typu <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="a7941-158">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[<span data-ttu-id="a7941-159">\<překladač ></span><span class="sxs-lookup"><span data-stu-id="a7941-159">\<resolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/resolver.md)|<span data-ttu-id="a7941-160">Určuje sdílené překladač použité v této vazbě přeložit sdílené OK ID sítě na koncový bod IP adresy uzlů v rámci sdílené OK.</span><span class="sxs-lookup"><span data-stu-id="a7941-160">Specifies a peer resolver used by this binding to resolve a peer mesh ID to the endpoint IP addresses of nodes within the peer mesh.</span></span>|  
|[<span data-ttu-id="a7941-161">\<zabezpečení ></span><span class="sxs-lookup"><span data-stu-id="a7941-161">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netpeerbinding.md)|<span data-ttu-id="a7941-162">Definuje nastavení zabezpečení pro zprávu.</span><span class="sxs-lookup"><span data-stu-id="a7941-162">Defines the security settings for the message.</span></span> <span data-ttu-id="a7941-163">Tento element je typu <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="a7941-163">This element is of type <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a7941-164">Nadřazené elementy</span><span class="sxs-lookup"><span data-stu-id="a7941-164">Parent Elements</span></span>  
  
|<span data-ttu-id="a7941-165">Prvek</span><span class="sxs-lookup"><span data-stu-id="a7941-165">Element</span></span>|<span data-ttu-id="a7941-166">Popis</span><span class="sxs-lookup"><span data-stu-id="a7941-166">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a7941-167">\<vazby ></span><span class="sxs-lookup"><span data-stu-id="a7941-167">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="a7941-168">Tento prvek obsahuje kolekci standardní a vlastní vazby.</span><span class="sxs-lookup"><span data-stu-id="a7941-168">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a7941-169">Poznámky</span><span class="sxs-lookup"><span data-stu-id="a7941-169">Remarks</span></span>  
 <span data-ttu-id="a7941-170">Tato vazba poskytuje podporu pro vytváření aplikací peer-to-peer nebo více stran použití sdílené přenosu přes protokol TCP.</span><span class="sxs-lookup"><span data-stu-id="a7941-170">This binding provides support for the creation of peer-to-peer or multiparty applications using peer transport over TCP.</span></span> <span data-ttu-id="a7941-171">Každý uzel sdílené může být hostitelem více typů komunikačních kanálů sdílené, které jsou definované s tímto typem vazby.</span><span class="sxs-lookup"><span data-stu-id="a7941-171">Each peer node can host multiple peer channels defined with this binding type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7941-172">Příklad</span><span class="sxs-lookup"><span data-stu-id="a7941-172">Example</span></span>  
 <span data-ttu-id="a7941-173">Následující příklad ukazuje použití NetPeerTcpBinding vazby, který poskytuje více stran komunikaci pomocí rovnocenného kanálu.</span><span class="sxs-lookup"><span data-stu-id="a7941-173">The following example demonstrates using the NetPeerTcpBinding binding, which provides multiparty communication using a peer channel.</span></span> <span data-ttu-id="a7941-174">Podrobné scénář použití tuto vazbu, najdete v části [Net sdílené TCP](http://msdn.microsoft.com/en-us/31f4db66-edb2-40a6-b92a-14098e92acae).</span><span class="sxs-lookup"><span data-stu-id="a7941-174">For a detailed scenario of using this binding, see [Net Peer TCP](http://msdn.microsoft.com/en-us/31f4db66-edb2-40a6-b92a-14098e92acae).</span></span>  
  
```xml  
<configuration>  
<system.ServiceModel>  
<bindings>  
<netPeerBinding>  
    <binding   
         closeTimeout="00:00:10"  
         openTimeout="00:00:20"   
         receiveTimeout="00:00:30"  
         sendTimeout="00:00:40"  
         maxBufferSize="1001"  
         maxConnections="123"   
         maxReceiveMessageSize="1000">  
        <reliableSession ordered="false"  
            inactivityTimeout="00:02:00"  
            enabled="true" />  
        <security mode="TransportWithMessageCredential">  
            <message clientCredentialType="CardSpace" />  
        </security>  
    </binding>  
</netPeerBinding>  
</bindings>  
</system.ServiceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a7941-175">Viz také</span><span class="sxs-lookup"><span data-stu-id="a7941-175">See Also</span></span>  
 <xref:System.ServiceModel.NetPeerTcpBinding>  
 <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement>  
 [<span data-ttu-id="a7941-176">Vazby</span><span class="sxs-lookup"><span data-stu-id="a7941-176">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="a7941-177">Konfigurace vazeb poskytovaných systémem</span><span class="sxs-lookup"><span data-stu-id="a7941-177">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="a7941-178">Používání vazeb ke konfiguraci služby Windows Communication Foundation a klienty</span><span class="sxs-lookup"><span data-stu-id="a7941-178">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="a7941-179">\<Vazba ></span><span class="sxs-lookup"><span data-stu-id="a7941-179">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)  
 [<span data-ttu-id="a7941-180">NET sdílené TCP</span><span class="sxs-lookup"><span data-stu-id="a7941-180">Net Peer TCP</span></span>](http://msdn.microsoft.com/en-us/31f4db66-edb2-40a6-b92a-14098e92acae)  
 [<span data-ttu-id="a7941-181">Sítě peer-to-Peer</span><span class="sxs-lookup"><span data-stu-id="a7941-181">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
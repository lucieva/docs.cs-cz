---
title: '&lt;httpsTransport&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f6ed4bc0-7e38-4348-9259-30bf61eb9435
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7b6e89c0caac2ad1d967dedeecbb83e5779f9388
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="lthttpstransportgt"></a><span data-ttu-id="8bd7e-102">&lt;httpsTransport&gt;</span><span class="sxs-lookup"><span data-stu-id="8bd7e-102">&lt;httpsTransport&gt;</span></span>
<span data-ttu-id="8bd7e-103">Určuje přenosového protokolu HTTP pro přenos protokolu SOAP zprávy pro vlastní vazby.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-103">Specifies an HTTP transport for transmitting SOAP messages for a custom binding.</span></span>  
  
 <span data-ttu-id="8bd7e-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="8bd7e-104">\<system.serviceModel></span></span>  
<span data-ttu-id="8bd7e-105">\<vazby ></span><span class="sxs-lookup"><span data-stu-id="8bd7e-105">\<bindings></span></span>  
<span data-ttu-id="8bd7e-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="8bd7e-106">\<customBinding></span></span>  
<span data-ttu-id="8bd7e-107">\<Vazba ></span><span class="sxs-lookup"><span data-stu-id="8bd7e-107">\<binding></span></span>  
<span data-ttu-id="8bd7e-108">\<httpsTransport ></span><span class="sxs-lookup"><span data-stu-id="8bd7e-108">\<httpsTransport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bd7e-109">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="8bd7e-109">Syntax</span></span>  
  
```xml  
<httpsTransport  
    allowCookies=Boolean"  
    authenticationScheme="Digest/Negotiate/Ntlm/Basic/Anonymous"  
    bypassProxyOnLocal=Boolean"  
    hostnameComparisonMode="StrongWildcard/Exact/WeakWildcard"  
    manualAddressing="Boolean"  
    maxBufferPoolSize="Integer"  
    maxBufferSize="Integer"  
    maxReceivedMessageSize="Integer"  
    proxyAddress="Uri"  
    proxyAuthenticationScheme="None/Digest/Negotiate/Ntlm/Basic/Anonymous"        realm="String"  
    requireClientCertificate=Boolean"  
    transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse"  
        unsafeConnectionNtlmAuthentication="Boolean"  
....useDefaultWebProxy="Boolean"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8bd7e-110">Atributy a elementy</span><span class="sxs-lookup"><span data-stu-id="8bd7e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8bd7e-111">Následující části popisují atributy, podřízené prvky a nadřazené prvky.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8bd7e-112">Atributy</span><span class="sxs-lookup"><span data-stu-id="8bd7e-112">Attributes</span></span>  
  
|<span data-ttu-id="8bd7e-113">Atribut</span><span class="sxs-lookup"><span data-stu-id="8bd7e-113">Attribute</span></span>|<span data-ttu-id="8bd7e-114">Popis</span><span class="sxs-lookup"><span data-stu-id="8bd7e-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8bd7e-115">allowCookies</span><span class="sxs-lookup"><span data-stu-id="8bd7e-115">allowCookies</span></span>|<span data-ttu-id="8bd7e-116">Logická hodnota, která určuje, zda klient přijímá soubory cookie a rozšiřuje je na dalších požadavků.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-116">A Boolean value that specifies whether the client accepts cookies and propagates them on future requests.</span></span> <span data-ttu-id="8bd7e-117">Výchozí hodnota je `false`.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-117">The default is `false`.</span></span><br /><br /> <span data-ttu-id="8bd7e-118">Tento atribut můžete použít při používání ASMX webové služby, které používají soubory cookie.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-118">You can use this attribute when you interact with ASMX Web services that use cookies.</span></span> <span data-ttu-id="8bd7e-119">Tímto způsobem mohou být jisti, že soubory cookie, kterou vrátil server se automaticky zkopírují do všechny budoucí požadavky pro tuto službu.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-119">In this way, you can be sure that the cookies returned from the server are automatically copied to all future client requests for that service.</span></span>|  
|<span data-ttu-id="8bd7e-120">AuthenticationScheme</span><span class="sxs-lookup"><span data-stu-id="8bd7e-120">authenticationScheme</span></span>|<span data-ttu-id="8bd7e-121">Určuje protokol, používá k ověření klientských požadavků zpracovávaných naslouchací proces protokolu HTTP.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-121">Specifies the protocol used to authenticate client requests being processed by an HTTP listener.</span></span> <span data-ttu-id="8bd7e-122">Platné hodnoty patří:</span><span class="sxs-lookup"><span data-stu-id="8bd7e-122">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="8bd7e-123">-Digest: Určuje ověřování hodnotou hash.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-123">-   Digest: Specifies digest authentication.</span></span><br /><span data-ttu-id="8bd7e-124">-Vyjednávání: Vyjedná s klientem nástroje k určení schéma ověřování.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-124">-   Negotiate: Negotiates with the client to determine the authentication scheme.</span></span> <span data-ttu-id="8bd7e-125">Pokud klient i server podporovat protokolu Kerberos, použije se; jinak se používá protokol NTLM.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-125">If both client and server support Kerberos, it is used; otherwise, NTLM is used.</span></span><br /><span data-ttu-id="8bd7e-126">– Protokol Ntlm: Určuje ověřování NTLM.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-126">-   Ntlm: Specifies NTLM authentication.</span></span><br /><span data-ttu-id="8bd7e-127">– Základní: Určuje základní ověřování.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-127">-   Basic: Specifies basic authentication.</span></span><br /><span data-ttu-id="8bd7e-128">-Anonymní: Určuje anonymní ověřování.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-128">-   Anonymous: Specifies anonymous authentication.</span></span><br /><br /> <span data-ttu-id="8bd7e-129">Výchozí hodnota je anonymní.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-129">The default is Anonymous.</span></span> <span data-ttu-id="8bd7e-130">Tento atribut je typu <xref:System.Net.AuthenticationSchemes>.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-130">This attribute is of type <xref:System.Net.AuthenticationSchemes>.</span></span> <span data-ttu-id="8bd7e-131">Tento atribut lze nastavit pouze jednou.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-131">This attribute can only be set once.</span></span>|  
|<span data-ttu-id="8bd7e-132">bypassProxyOnLocal</span><span class="sxs-lookup"><span data-stu-id="8bd7e-132">bypassProxyOnLocal</span></span>|<span data-ttu-id="8bd7e-133">Logická hodnota, která označuje, zda Nepoužívat proxy server pro místní adresy.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-133">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="8bd7e-134">Výchozí hodnota je `false`.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-134">The default is `false`.</span></span><br /><br /> <span data-ttu-id="8bd7e-135">Místní adresa je ten, který je v místní síti LAN nebo intranet.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-135">A local address is one that is on the local LAN or intranet.</span></span><br /><br /> [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<span data-ttu-id="8bd7e-136">Pokud adresu služby začíná http://localhost vždy ignoruje proxy serveru.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-136"> always ignores the proxy if the service address begins with http://localhost.</span></span><br /><br /> <span data-ttu-id="8bd7e-137">Pokud chcete klientům jít přes proxy server při posuzování ke službám ve stejném počítači, se musí používat název hostitele místo localhost.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-137">You should use the host name rather than localhost if you want clients to go through a proxy when talking to services on the same machine.</span></span>|  
|<span data-ttu-id="8bd7e-138">hostnameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="8bd7e-138">hostnameComparisonMode</span></span>|<span data-ttu-id="8bd7e-139">Určuje režim porovnání hostname HTTP použitá k analýze identifikátory URI.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-139">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="8bd7e-140">Platné hodnoty jsou,</span><span class="sxs-lookup"><span data-stu-id="8bd7e-140">Valid values are,</span></span><br /><br /> <span data-ttu-id="8bd7e-141">-StrongWildcard: ("+") odpovídá všechny možné názvy hostitelů v rámci zadané schéma, port a relativní identifikátor URI.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-141">-   StrongWildcard: ("+") matches all possible hostnames in the context of the specified scheme, port and relative URI.</span></span><br /><span data-ttu-id="8bd7e-142">-Přesnou: žádné zástupné znaky</span><span class="sxs-lookup"><span data-stu-id="8bd7e-142">-   Exact: no wildcards</span></span><br /><span data-ttu-id="8bd7e-143">-WeakWildcard: ("*") shoduje s názvem všechny možné hostitele zadané schéma, port a relativní UIR, která nejsou explicitně shoduje nebo přes mechanismus silné zástupný znak v kontextu.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-143">-   WeakWildcard: ("*") matches all possible hostname in the context of the specified scheme, port and relative UIR that have not been matched explicitly or through the strong wildcard mechanism.</span></span><br /><br /> <span data-ttu-id="8bd7e-144">Výchozí hodnota je StrongWildcard.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-144">The default is StrongWildcard.</span></span> <span data-ttu-id="8bd7e-145">Tento atribut je typu `System.ServiceModel.HostnameComparison`.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-145">This attribute is of type `System.ServiceModel.HostnameComparison`.</span></span>|  
|<span data-ttu-id="8bd7e-146">manualAddressing</span><span class="sxs-lookup"><span data-stu-id="8bd7e-146">manualAddressing</span></span>|<span data-ttu-id="8bd7e-147">Logická hodnota, která umožňuje uživatelům převzít kontrolu nad adresování zprávy.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-147">A Boolean value that enables the user to take control of message addressing.</span></span> <span data-ttu-id="8bd7e-148">Tato vlastnost se obvykle používá ve scénářích směrovače, kde aplikace určuje, které jeden z několika cílů odeslat zprávu na.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-148">This property is usually used in router scenarios, where the application determines which one of several destinations to send a message to.</span></span><br /><br /> <span data-ttu-id="8bd7e-149">Pokud nastavíte hodnotu `true`, kanál předpokládá zpráva již splněna a k němu nepřidává žádné další informace.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-149">When set to `true`, the channel assumes the message has already been addressed and does not add any additional information to it.</span></span> <span data-ttu-id="8bd7e-150">Uživatel pak může jednotlivě adres každou zprávu.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-150">The user can then address every message individually.</span></span><br /><br /> <span data-ttu-id="8bd7e-151">Pokud nastavíte hodnotu `false`, výchozího mechanismu adresování Windows Communication Foundation (WCF) automaticky vytvoří adresy pro všechny zprávy.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-151">When set to `false`, the default Windows Communication Foundation (WCF) addressing mechanism automatically creates addresses for all messages.</span></span><br /><br /> <span data-ttu-id="8bd7e-152">Výchozí hodnota je `false`.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-152">The default is `false`.</span></span>|  
|<span data-ttu-id="8bd7e-153">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="8bd7e-153">maxBufferPoolSize</span></span>|<span data-ttu-id="8bd7e-154">Kladné celé číslo, které určuje maximální velikost fondu vyrovnávací paměti.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-154">A positive integer that specifies the maximum size of the buffer pool.</span></span> <span data-ttu-id="8bd7e-155">Výchozí hodnota je 524288.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-155">The default is 524288.</span></span><br /><br /> <span data-ttu-id="8bd7e-156">Mnoho části služby WCF pomocí vyrovnávací paměti.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-156">Many parts of WCF use buffers.</span></span> <span data-ttu-id="8bd7e-157">Vytváření a zničení pokaždé, když se používají vyrovnávací paměti je nákladné a uvolňování paměti pro vyrovnávací paměti je také nákladné.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-157">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="8bd7e-158">S fondy vyrovnávací paměti můžete provést vyrovnávací paměti z fondu, ho použít a po dokončení se vraťte do fondu.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-158">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="8bd7e-159">Proto je předejde režijní náklady v vytváření a zničení vyrovnávací paměti.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-159">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="8bd7e-160">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="8bd7e-160">maxBufferSize</span></span>|<span data-ttu-id="8bd7e-161">Kladné celé číslo, které určuje maximální velikost vyrovnávací paměti.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-161">A positive integer that specifies the maximum size of the buffer.</span></span> <span data-ttu-id="8bd7e-162">Výchozí hodnota je 524288</span><span class="sxs-lookup"><span data-stu-id="8bd7e-162">The default is 524288</span></span>|  
|<span data-ttu-id="8bd7e-163">MaxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="8bd7e-163">maxReceivedMessageSize</span></span>|<span data-ttu-id="8bd7e-164">Kladné celé číslo, které určuje maximální povolená velikost zprávy, bude moci přijmout.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-164">A positive integer that specifies the maximum allowable message size that can be received.</span></span> <span data-ttu-id="8bd7e-165">Výchozí hodnota je 65536.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-165">The default is 65536.</span></span>|  
|<span data-ttu-id="8bd7e-166">proxyAddress</span><span class="sxs-lookup"><span data-stu-id="8bd7e-166">proxyAddress</span></span>|<span data-ttu-id="8bd7e-167">Identifikátor URI, který určuje adresu proxy serveru HTTP.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-167">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="8bd7e-168">Pokud `useSystemWebProxy` je `true`, toto nastavení musí být `null`.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-168">If `useSystemWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="8bd7e-169">Výchozí hodnota je `null`.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-169">The default is `null`.</span></span>|  
|<span data-ttu-id="8bd7e-170">ProxyAuthenticationScheme</span><span class="sxs-lookup"><span data-stu-id="8bd7e-170">proxyAuthenticationScheme</span></span>|<span data-ttu-id="8bd7e-171">Určuje protokol použitý pro ověřování proxy serveru HTTP zpracovává požadavky klienta.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-171">Specifies the protocol used for authenticating client requests being processed by an HTTP proxy.</span></span> <span data-ttu-id="8bd7e-172">Platné hodnoty patří:</span><span class="sxs-lookup"><span data-stu-id="8bd7e-172">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="8bd7e-173">-None: Neprobíhá žádné ověřování.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-173">-   None: No authentication is performed.</span></span><br /><span data-ttu-id="8bd7e-174">-Digest: Určuje ověřování hodnotou hash.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-174">-   Digest: Specifies digest authentication.</span></span><br /><span data-ttu-id="8bd7e-175">-Vyjednávání: Vyjedná s klientem nástroje k určení schéma ověřování.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-175">-   Negotiate: Negotiates with the client to determine the authentication scheme.</span></span> <span data-ttu-id="8bd7e-176">Pokud klient i server podporovat protokolu Kerberos, použije se; jinak se používá protokol NTLM.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-176">If both client and server support Kerberos, it is used; otherwise, NTLM is used.</span></span><br /><span data-ttu-id="8bd7e-177">– Protokol Ntlm: Určuje ověřování NTLM.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-177">-   Ntlm: Specifies NTLM authentication.</span></span><br /><span data-ttu-id="8bd7e-178">– Základní: Určuje základní ověřování.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-178">-   Basic: Specifies basic authentication.</span></span><br /><span data-ttu-id="8bd7e-179">-Anonymní: Určuje anonymní ověřování.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-179">-   Anonymous: Specifies anonymous authentication.</span></span><br /><span data-ttu-id="8bd7e-180">-IntegratedWindowsAuthentication: Určuje ověřování systému Windows.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-180">-   IntegratedWindowsAuthentication: Specifies Windows authentication.</span></span><br /><br /> <span data-ttu-id="8bd7e-181">Výchozí hodnota je anonymní.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-181">The default is Anonymous.</span></span> <span data-ttu-id="8bd7e-182">Tento atribut je typu <xref:System.Net.AuthenticationSchemes>.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-182">This attribute is of type <xref:System.Net.AuthenticationSchemes>.</span></span>|  
|<span data-ttu-id="8bd7e-183">sféry</span><span class="sxs-lookup"><span data-stu-id="8bd7e-183">realm</span></span>|<span data-ttu-id="8bd7e-184">Řetězec, který určuje sféry, použijte na proxy serveru.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-184">A string that specifies the realm to use on the proxy/server.</span></span> <span data-ttu-id="8bd7e-185">Výchozí hodnota je prázdný řetězec.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-185">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="8bd7e-186">Servery používají sfér k oddílu chráněným prostředkům.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-186">Servers use realms to partition protected resources.</span></span> <span data-ttu-id="8bd7e-187">Každý oddíl může mít svou vlastní databázi schéma nebo autorizace ověřování.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-187">Each partition can have its own authentication scheme and/or authorization database.</span></span> <span data-ttu-id="8bd7e-188">Sfér se používají pouze pro základní a ověřování algoritmem digest.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-188">Realms are used only for basic and digest authentication.</span></span> <span data-ttu-id="8bd7e-189">Jakmile klient úspěšně ověří, je platný pro všechny prostředky v dané sféry ověřování.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-189">After a client successfully authenticates, the authentication is valid for all resources in a given realm.</span></span> <span data-ttu-id="8bd7e-190">Podrobný popis sfér najdete v dokumentu RFC 2617 na http://www.ietf.org.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-190">For a detailed description of realms, see RFC 2617 at http://www.ietf.org.</span></span>|  
|<span data-ttu-id="8bd7e-191">RequireClientCertificate</span><span class="sxs-lookup"><span data-stu-id="8bd7e-191">requireClientCertificate</span></span>|<span data-ttu-id="8bd7e-192">Logická hodnota, která určuje, pokud server vyžaduje, aby klient zajistit certifikát klienta v rámci metody handshake pro protokol HTTPS.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-192">A Boolean value that specifies if the server requires the client to provide a client certificate as part of the HTTPS handshake.</span></span> <span data-ttu-id="8bd7e-193">Výchozí hodnota je `false`.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-193">The default is `false`.</span></span>|  
|<span data-ttu-id="8bd7e-194">transferMode</span><span class="sxs-lookup"><span data-stu-id="8bd7e-194">transferMode</span></span>|<span data-ttu-id="8bd7e-195">Určuje, zda jsou zprávy do vyrovnávací paměti nebo prostřednictvím datového proudu nebo požadavku nebo odpovědi.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-195">Specifies whether messages are buffered or streamed or a request or response.</span></span> <span data-ttu-id="8bd7e-196">Platné hodnoty patří:</span><span class="sxs-lookup"><span data-stu-id="8bd7e-196">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="8bd7e-197">-Uložená do vyrovnávací paměti: Zprávy požadavku a odpovědi jsou uložená do vyrovnávací paměti.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-197">-   Buffered: The request and response messages are buffered.</span></span><br /><span data-ttu-id="8bd7e-198">-Streamování: Streamovaných zprávy požadavku a odpovědi.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-198">-   Streamed: The request and response messages are streamed.</span></span><br /><span data-ttu-id="8bd7e-199">-StreamedRequest: Zprávu požadavku je streamování a zprávu odpovědi do vyrovnávací paměti.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-199">-   StreamedRequest: The request message is streamed and the response message is buffered.</span></span><br /><span data-ttu-id="8bd7e-200">-StreamedResponse: Zprávu požadavku do vyrovnávací paměti a je streamování zprávu odpovědi.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-200">-   StreamedResponse: The request message is buffered and the response message is streamed.</span></span><br /><br /> <span data-ttu-id="8bd7e-201">Výchozí hodnota je uložená do vyrovnávací paměti.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-201">The default is Buffered.</span></span> <span data-ttu-id="8bd7e-202">Tento atribut je typu <xref:System.ServiceModel.TransferMode>.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-202">This attribute is of type <xref:System.ServiceModel.TransferMode>.</span></span>|  
|<span data-ttu-id="8bd7e-203">UnsafeConnectionNtlmAuthentication</span><span class="sxs-lookup"><span data-stu-id="8bd7e-203">unsafeConnectionNtlmAuthentication</span></span>|<span data-ttu-id="8bd7e-204">Logická hodnota, která určuje, zda je na serveru povoleno Unsafe sdílení připojení.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-204">A Boolean value that specifies whether Unsafe Connection Sharing is enabled on the server.</span></span> <span data-ttu-id="8bd7e-205">Výchozí hodnota je `false`.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-205">The default is `false`.</span></span> <span data-ttu-id="8bd7e-206">Pokud je povoleno, ověřování protokolem NTLM se provádí jednou v každé připojení TCP.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-206">If enabled, NTLM authentication is performed once on each TCP connection.</span></span>|  
|<span data-ttu-id="8bd7e-207">useDefaultWebProxy</span><span class="sxs-lookup"><span data-stu-id="8bd7e-207">useDefaultWebProxy</span></span>|<span data-ttu-id="8bd7e-208">Logická hodnota, která určuje, jestli jsou nastavení proxy serveru celého systému použít místo nastavení specifická pro uživatele.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-208">A Boolean value that specifies whether the machine-wide proxy settings are used rather than the user specific settings.</span></span> <span data-ttu-id="8bd7e-209">Výchozí hodnota je `true`.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-209">The default is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8bd7e-210">Podřízené elementy</span><span class="sxs-lookup"><span data-stu-id="8bd7e-210">Child Elements</span></span>  
 <span data-ttu-id="8bd7e-211">Žádné</span><span class="sxs-lookup"><span data-stu-id="8bd7e-211">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8bd7e-212">Nadřazené elementy</span><span class="sxs-lookup"><span data-stu-id="8bd7e-212">Parent Elements</span></span>  
  
|<span data-ttu-id="8bd7e-213">Prvek</span><span class="sxs-lookup"><span data-stu-id="8bd7e-213">Element</span></span>|<span data-ttu-id="8bd7e-214">Popis</span><span class="sxs-lookup"><span data-stu-id="8bd7e-214">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8bd7e-215">\<Vazba ></span><span class="sxs-lookup"><span data-stu-id="8bd7e-215">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="8bd7e-216">Definuje všechny možnosti vazba vlastní vazby.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-216">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8bd7e-217">Poznámky</span><span class="sxs-lookup"><span data-stu-id="8bd7e-217">Remarks</span></span>  
 <span data-ttu-id="8bd7e-218">`httpsTransport` Element je výchozím bodem pro vytvoření vlastní vazby, který implementuje přenosový protokol HTTPS.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-218">The `httpsTransport` element is the starting point for creating a custom binding that implements the HTTPS transport protocol.</span></span> <span data-ttu-id="8bd7e-219">HTTPS je primární přenosu použitý pro zajištění zabezpečené spolupráce.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-219">HTTPS is the primary transport used for secure interoperability purposes.</span></span> <span data-ttu-id="8bd7e-220">Podporuje protokol HTTPS [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] zajistit interoperabilitu s dalších webových služeb zásobníky.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-220">HTTPS is supported by the [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] to ensure interoperability with other Web services stacks.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bd7e-221">Viz také</span><span class="sxs-lookup"><span data-stu-id="8bd7e-221">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HttpsTransportElement>  
 <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
 <xref:System.ServiceModel.Channels.TransportBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="8bd7e-222">Přenosy</span><span class="sxs-lookup"><span data-stu-id="8bd7e-222">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)  
 [<span data-ttu-id="8bd7e-223">Volba přenosu</span><span class="sxs-lookup"><span data-stu-id="8bd7e-223">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 [<span data-ttu-id="8bd7e-224">Vazby</span><span class="sxs-lookup"><span data-stu-id="8bd7e-224">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="8bd7e-225">Rozšiřování vazeb</span><span class="sxs-lookup"><span data-stu-id="8bd7e-225">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="8bd7e-226">Vlastní vazby</span><span class="sxs-lookup"><span data-stu-id="8bd7e-226">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="8bd7e-227">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="8bd7e-227">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
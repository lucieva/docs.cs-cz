---
title: "&lt;certificate&gt; – &lt;peer&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 48b69142-c957-4305-a042-c9d0c9a55c0e
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e8bf8cb80201f2501fb60df7c9abb5039d688dc5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/02/2017
---
# <a name="ltcertificategt-of-ltpeergt"></a><span data-ttu-id="fc1f4-102">&lt;certificate&gt; – &lt;peer&gt;</span><span class="sxs-lookup"><span data-stu-id="fc1f4-102">&lt;certificate&gt; of &lt;peer&gt;</span></span>
<span data-ttu-id="fc1f4-103">Určuje certifikát používají partnerského uzlu.</span><span class="sxs-lookup"><span data-stu-id="fc1f4-103">Specifies a certificate used by a peer.</span></span>  
  
 <span data-ttu-id="fc1f4-104">\<systém. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="fc1f4-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="fc1f4-105">\<chování ></span><span class="sxs-lookup"><span data-stu-id="fc1f4-105">\<behaviors></span></span>  
<span data-ttu-id="fc1f4-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="fc1f4-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="fc1f4-107">\<chování ></span><span class="sxs-lookup"><span data-stu-id="fc1f4-107">\<behavior></span></span>  
<span data-ttu-id="fc1f4-108">\<– serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="fc1f4-108">\<serviceCredentials></span></span>  
<span data-ttu-id="fc1f4-109">\<sdílené ></span><span class="sxs-lookup"><span data-stu-id="fc1f4-109">\<peer></span></span>  
<span data-ttu-id="fc1f4-110">\<certifikátu ></span><span class="sxs-lookup"><span data-stu-id="fc1f4-110">\<certificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc1f4-111">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="fc1f4-111">Syntax</span></span>  
  
```xml  
<certificate findValue = "String"   
storeLocation = "CurrentUser/LocalMachine"  
storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fc1f4-112">Atributy a elementy</span><span class="sxs-lookup"><span data-stu-id="fc1f4-112">Attributes and Elements</span></span>  
 <span data-ttu-id="fc1f4-113">Následující části popisují atributy, podřízené prvky a nadřazené prvky.</span><span class="sxs-lookup"><span data-stu-id="fc1f4-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fc1f4-114">Atributy</span><span class="sxs-lookup"><span data-stu-id="fc1f4-114">Attributes</span></span>  
  
|<span data-ttu-id="fc1f4-115">Atribut</span><span class="sxs-lookup"><span data-stu-id="fc1f4-115">Attribute</span></span>|<span data-ttu-id="fc1f4-116">Popis</span><span class="sxs-lookup"><span data-stu-id="fc1f4-116">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="fc1f4-117">Řetězec, který obsahuje hodnotu k vyhledání v úložišti certifikátů X.509.</span><span class="sxs-lookup"><span data-stu-id="fc1f4-117">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="fc1f4-118">Typ obsažený v atributu musí splňovat požadavky na zadané `x509FindType`.</span><span class="sxs-lookup"><span data-stu-id="fc1f4-118">The type contained in the attribute must satisfy the requirements of the specified `x509FindType`.</span></span> <span data-ttu-id="fc1f4-119">Výchozí hodnota je prázdný řetězec.</span><span class="sxs-lookup"><span data-stu-id="fc1f4-119">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="fc1f4-120">Určuje umístění úložiště certifikátů X.509, který klient používá k ověření certifikátu druhé strany proti.</span><span class="sxs-lookup"><span data-stu-id="fc1f4-120">Specifies the location of the X.509 certificate store that the client uses to validate the peer's certificate against.</span></span> <span data-ttu-id="fc1f4-121">Platné hodnoty patří:</span><span class="sxs-lookup"><span data-stu-id="fc1f4-121">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="fc1f4-122">-LocalMachine: úložiště certifikátů přiřazené k místnímu počítači.</span><span class="sxs-lookup"><span data-stu-id="fc1f4-122">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="fc1f4-123">-CurrentUser: úložiště certifikátů přiřazená aktuálnímu uživateli.</span><span class="sxs-lookup"><span data-stu-id="fc1f4-123">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="fc1f4-124">Výchozí hodnota je v místním počítači.</span><span class="sxs-lookup"><span data-stu-id="fc1f4-124">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="fc1f4-125">Určuje název úložiště certifikátu X.509 otevřete.</span><span class="sxs-lookup"><span data-stu-id="fc1f4-125">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="fc1f4-126">Platné hodnoty patří:</span><span class="sxs-lookup"><span data-stu-id="fc1f4-126">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="fc1f4-127">-Adresáře: Úložiště certifikátů pro ostatní uživatele.</span><span class="sxs-lookup"><span data-stu-id="fc1f4-127">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="fc1f4-128">-AuthRoot: Certifikát úložiště pro třetí strany certifikačních autorit (CA).</span><span class="sxs-lookup"><span data-stu-id="fc1f4-128">-   AuthRoot: Certificate store for third-party certificate authorities (CAs).</span></span><br /><span data-ttu-id="fc1f4-129">-CertificateAuthority: Úložiště certifikátů pro zprostředkující certifikační autority (CA).</span><span class="sxs-lookup"><span data-stu-id="fc1f4-129">-   CertificateAuthority: Certificate store for intermediate certificate authorities (CAs).</span></span><br /><span data-ttu-id="fc1f4-130">-Nepovolené: Certifikát úložiště pro odvolané certifikáty.</span><span class="sxs-lookup"><span data-stu-id="fc1f4-130">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="fc1f4-131">-: Úložiště certifikátů my Pro osobní certifikáty.</span><span class="sxs-lookup"><span data-stu-id="fc1f4-131">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="fc1f4-132">-Root: Úložiště certifikátů pro důvěryhodné kořenové certifikační autority (CA).</span><span class="sxs-lookup"><span data-stu-id="fc1f4-132">-   Root: Certificate store for trusted root certificate authorities (CAs).</span></span><br /><span data-ttu-id="fc1f4-133">-TrustedPeople: Úložiště certifikátů přímo důvěryhodné osoby a prostředky.</span><span class="sxs-lookup"><span data-stu-id="fc1f4-133">-   TrustedPeople: Certificate store for directly-trusted people and resources.</span></span><br /><span data-ttu-id="fc1f4-134">-TrustedPublisher: Úložiště certifikátů pro přímo důvěryhodných vydavatelů.</span><span class="sxs-lookup"><span data-stu-id="fc1f4-134">-   TrustedPublisher: Certificate store for directly-trusted publishers.</span></span><br /><br /> <span data-ttu-id="fc1f4-135">Výchozí hodnota je můj.</span><span class="sxs-lookup"><span data-stu-id="fc1f4-135">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="fc1f4-136">Definuje typ vyhledávání X.509 provést.</span><span class="sxs-lookup"><span data-stu-id="fc1f4-136">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="fc1f4-137">Platné hodnoty patří:</span><span class="sxs-lookup"><span data-stu-id="fc1f4-137">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="fc1f4-138">-FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="fc1f4-138">-   FindByThumbPrint</span></span><br /><span data-ttu-id="fc1f4-139">-FindBySubjectName.</span><span class="sxs-lookup"><span data-stu-id="fc1f4-139">-   FindBySubjectName</span></span><br /><span data-ttu-id="fc1f4-140">-FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="fc1f4-140">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="fc1f4-141">-FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="fc1f4-141">-   FindByIssuerName</span></span><br /><span data-ttu-id="fc1f4-142">-FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="fc1f4-142">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="fc1f4-143">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="fc1f4-143">-   FindBySerialNumber</span></span><br /><span data-ttu-id="fc1f4-144">-FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="fc1f4-144">-   FindByTimeValid</span></span><br /><span data-ttu-id="fc1f4-145">-FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="fc1f4-145">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="fc1f4-146">-FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="fc1f4-146">-   FindByTemplateName</span></span><br /><span data-ttu-id="fc1f4-147">-FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="fc1f4-147">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="fc1f4-148">-FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="fc1f4-148">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="fc1f4-149">-FindByExtension</span><span class="sxs-lookup"><span data-stu-id="fc1f4-149">-   FindByExtension</span></span><br /><span data-ttu-id="fc1f4-150">-FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="fc1f4-150">-   FindByKeyUsage</span></span><br /><span data-ttu-id="fc1f4-151">-FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="fc1f4-151">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="fc1f4-152">Typ obsažený v `findValue` atributu musí splňovat požadavky na zadané `X509FindType`.</span><span class="sxs-lookup"><span data-stu-id="fc1f4-152">The type contained in the `findValue` attribute must satisfy the requirements of the specified `X509FindType`.</span></span><br /><br /> <span data-ttu-id="fc1f4-153">Výchozí hodnota je FindBySubjectDistinguishedName.</span><span class="sxs-lookup"><span data-stu-id="fc1f4-153">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fc1f4-154">Podřízené elementy</span><span class="sxs-lookup"><span data-stu-id="fc1f4-154">Child Elements</span></span>  
 <span data-ttu-id="fc1f4-155">Žádné</span><span class="sxs-lookup"><span data-stu-id="fc1f4-155">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fc1f4-156">Nadřazené elementy</span><span class="sxs-lookup"><span data-stu-id="fc1f4-156">Parent Elements</span></span>  
  
|<span data-ttu-id="fc1f4-157">Prvek</span><span class="sxs-lookup"><span data-stu-id="fc1f4-157">Element</span></span>|<span data-ttu-id="fc1f4-158">Popis</span><span class="sxs-lookup"><span data-stu-id="fc1f4-158">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fc1f4-159">\<sdílené ></span><span class="sxs-lookup"><span data-stu-id="fc1f4-159">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|<span data-ttu-id="fc1f4-160">Určuje, že aktuální přihlašovací údaje pro uzel sdílené.</span><span class="sxs-lookup"><span data-stu-id="fc1f4-160">Specifies the current credentials for a peer node.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fc1f4-161">Poznámky</span><span class="sxs-lookup"><span data-stu-id="fc1f4-161">Remarks</span></span>  
 <span data-ttu-id="fc1f4-162">Tento element konfigurace obsahuje `X509Certificate2` instance používané při ověřování okolí sdílené v mřížce.</span><span class="sxs-lookup"><span data-stu-id="fc1f4-162">This configuration element contains an `X509Certificate2` instance used when authenticating neighbors in the peer mesh.</span></span>  
  
 <span data-ttu-id="fc1f4-163">Další informace o programování peer-to-peer, najdete v části [Peer-to-Peer sítě](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="fc1f4-163">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc1f4-164">Viz také</span><span class="sxs-lookup"><span data-stu-id="fc1f4-164">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.Certificate%2A>  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateElement>  
 <xref:System.ServiceModel.Security.PeerCredential.Certificate%2A>  
 <xref:System.ServiceModel.Security.PeerCredential>  
 [<span data-ttu-id="fc1f4-165">Práce s certifikáty</span><span class="sxs-lookup"><span data-stu-id="fc1f4-165">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="fc1f4-166">Sítě peer-to-Peer</span><span class="sxs-lookup"><span data-stu-id="fc1f4-166">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="fc1f4-167">Ověřování zpráv rovnocenného kanálu</span><span class="sxs-lookup"><span data-stu-id="fc1f4-167">Peer Channel Message Authentication</span></span>](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="fc1f4-168">Vlastní ověřování rovnocenného kanálu</span><span class="sxs-lookup"><span data-stu-id="fc1f4-168">Peer Channel Custom Authentication</span></span>](http://msdn.microsoft.com/en-us/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="fc1f4-169">Zabezpečení aplikací rovnocenného kanálu</span><span class="sxs-lookup"><span data-stu-id="fc1f4-169">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)  
 [<span data-ttu-id="fc1f4-170">Zabezpečení služeb a klientů</span><span class="sxs-lookup"><span data-stu-id="fc1f4-170">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
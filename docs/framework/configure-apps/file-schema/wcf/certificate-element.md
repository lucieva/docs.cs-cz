---
title: Element &lt;certificate&gt;
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9b3d9233-ef35-477a-bf5d-efd1e80a52f4
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 00f1b1f93836f3890a4c3f3797b583a15aeb599f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/02/2017
---
# <a name="ltcertificategt-element"></a><span data-ttu-id="5f567-102">Element &lt;certificate&gt;</span><span class="sxs-lookup"><span data-stu-id="5f567-102">&lt;certificate&gt; Element</span></span>
<span data-ttu-id="5f567-103">Určuje certifikát X.509, který chcete použít pro podepisování a šifrování zpráv pro klienty peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="5f567-103">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="5f567-104">\<systém. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="5f567-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="5f567-105">\<chování ></span><span class="sxs-lookup"><span data-stu-id="5f567-105">\<behaviors></span></span>  
<span data-ttu-id="5f567-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="5f567-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="5f567-107">\<chování ></span><span class="sxs-lookup"><span data-stu-id="5f567-107">\<behavior></span></span>  
<span data-ttu-id="5f567-108">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="5f567-108">\<clientCredentials></span></span>  
<span data-ttu-id="5f567-109">\<sdílené ></span><span class="sxs-lookup"><span data-stu-id="5f567-109">\<peer></span></span>  
<span data-ttu-id="5f567-110">\<certifikátu ></span><span class="sxs-lookup"><span data-stu-id="5f567-110">\<certificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f567-111">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="5f567-111">Syntax</span></span>  
  
```xml  
<certificate findValue="String"   
  
storeLocation="LocalMachine/CurrentUser"  
      storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
      X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5f567-112">Atributy a elementy</span><span class="sxs-lookup"><span data-stu-id="5f567-112">Attributes and Elements</span></span>  
 <span data-ttu-id="5f567-113">Následující části popisují atributy, podřízené prvky a nadřazené prvky.</span><span class="sxs-lookup"><span data-stu-id="5f567-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5f567-114">Atributy</span><span class="sxs-lookup"><span data-stu-id="5f567-114">Attributes</span></span>  
  
|<span data-ttu-id="5f567-115">Atribut</span><span class="sxs-lookup"><span data-stu-id="5f567-115">Attribute</span></span>|<span data-ttu-id="5f567-116">Popis</span><span class="sxs-lookup"><span data-stu-id="5f567-116">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="5f567-117">Řetězec, který obsahuje hodnotu k vyhledání v úložišti certifikátů X.509.</span><span class="sxs-lookup"><span data-stu-id="5f567-117">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="5f567-118">Typ obsažený v atributu musí splňovat požadavky na zadané `x509FindType`.</span><span class="sxs-lookup"><span data-stu-id="5f567-118">The type contained in the attribute must satisfy the requirements of the specified `x509FindType`.</span></span> <span data-ttu-id="5f567-119">Výchozí hodnota je prázdný řetězec.</span><span class="sxs-lookup"><span data-stu-id="5f567-119">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="5f567-120">Určuje umístění úložiště certifikátů X.509, který klient používá k ověření certifikátu druhé strany proti.</span><span class="sxs-lookup"><span data-stu-id="5f567-120">Specifies the location of the X.509 certificate store that the client uses to validate the peer's certificate against.</span></span> <span data-ttu-id="5f567-121">Platné hodnoty patří:</span><span class="sxs-lookup"><span data-stu-id="5f567-121">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="5f567-122">-LocalMachine: úložiště certifikátů přiřazené k místnímu počítači.</span><span class="sxs-lookup"><span data-stu-id="5f567-122">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="5f567-123">-CurrentUser: úložiště certifikátů přiřazená aktuálnímu uživateli.</span><span class="sxs-lookup"><span data-stu-id="5f567-123">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="5f567-124">Výchozí hodnota je v místním počítači.</span><span class="sxs-lookup"><span data-stu-id="5f567-124">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="5f567-125">Určuje název úložiště certifikátu X.509 otevřete.</span><span class="sxs-lookup"><span data-stu-id="5f567-125">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="5f567-126">Platné hodnoty patří:</span><span class="sxs-lookup"><span data-stu-id="5f567-126">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="5f567-127">-Adresáře: Úložiště certifikátů pro ostatní uživatele.</span><span class="sxs-lookup"><span data-stu-id="5f567-127">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="5f567-128">-AuthRoot: Certifikát úložiště pro třetí strany certifikační autority (CA).</span><span class="sxs-lookup"><span data-stu-id="5f567-128">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="5f567-129">-CertificateAuthority: Úložiště certifikátů pro zprostředkující certifikační autority (CA).</span><span class="sxs-lookup"><span data-stu-id="5f567-129">-   CertificateAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="5f567-130">-Nepovolené: Certifikát úložiště pro odvolané certifikáty.</span><span class="sxs-lookup"><span data-stu-id="5f567-130">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="5f567-131">-: Úložiště certifikátů my Pro osobní certifikáty.</span><span class="sxs-lookup"><span data-stu-id="5f567-131">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="5f567-132">-Root: Úložiště certifikátů pro důvěryhodné kořenové certifikační autority (CA).</span><span class="sxs-lookup"><span data-stu-id="5f567-132">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="5f567-133">-TrustedPeople: Úložiště certifikátů přímo důvěryhodné osoby a prostředky.</span><span class="sxs-lookup"><span data-stu-id="5f567-133">-   TrustedPeople: Certificate store for directly-trusted people and resources.</span></span><br /><span data-ttu-id="5f567-134">-TrustedPublisher: Úložiště certifikátů pro přímo důvěryhodných vydavatelů.</span><span class="sxs-lookup"><span data-stu-id="5f567-134">-   TrustedPublisher: Certificate store for directly-trusted publishers.</span></span><br /><br /> <span data-ttu-id="5f567-135">Výchozí hodnota je můj.</span><span class="sxs-lookup"><span data-stu-id="5f567-135">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="5f567-136">Definuje typ vyhledávání X.509 provést.</span><span class="sxs-lookup"><span data-stu-id="5f567-136">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="5f567-137">Platné hodnoty patří:</span><span class="sxs-lookup"><span data-stu-id="5f567-137">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="5f567-138">-FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="5f567-138">-   FindByThumbPrint</span></span><br /><span data-ttu-id="5f567-139">-FindBySubjectName.</span><span class="sxs-lookup"><span data-stu-id="5f567-139">-   FindBySubjectName</span></span><br /><span data-ttu-id="5f567-140">-FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="5f567-140">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="5f567-141">-FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="5f567-141">-   FindByIssuerName</span></span><br /><span data-ttu-id="5f567-142">-FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="5f567-142">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="5f567-143">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="5f567-143">-   FindBySerialNumber</span></span><br /><span data-ttu-id="5f567-144">-FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="5f567-144">-   FindByTimeValid</span></span><br /><span data-ttu-id="5f567-145">-FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="5f567-145">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="5f567-146">-FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="5f567-146">-   FindByTemplateName</span></span><br /><span data-ttu-id="5f567-147">-FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="5f567-147">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="5f567-148">-FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="5f567-148">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="5f567-149">-FindByExtension</span><span class="sxs-lookup"><span data-stu-id="5f567-149">-   FindByExtension</span></span><br /><span data-ttu-id="5f567-150">-FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="5f567-150">-   FindByKeyUsage</span></span><br /><span data-ttu-id="5f567-151">-FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="5f567-151">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="5f567-152">Typ obsažený v `findValue` atributu musí splňovat požadavky na zadané `X509FindType`.</span><span class="sxs-lookup"><span data-stu-id="5f567-152">The type contained in the `findValue` attribute must satisfy the requirements of the specified `X509FindType`.</span></span><br /><br /> <span data-ttu-id="5f567-153">Výchozí hodnota je FindBySubjectDistinguishedName.</span><span class="sxs-lookup"><span data-stu-id="5f567-153">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5f567-154">Podřízené elementy</span><span class="sxs-lookup"><span data-stu-id="5f567-154">Child Elements</span></span>  
 <span data-ttu-id="5f567-155">Žádné</span><span class="sxs-lookup"><span data-stu-id="5f567-155">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5f567-156">Nadřazené elementy</span><span class="sxs-lookup"><span data-stu-id="5f567-156">Parent Elements</span></span>  
  
|<span data-ttu-id="5f567-157">Prvek</span><span class="sxs-lookup"><span data-stu-id="5f567-157">Element</span></span>|<span data-ttu-id="5f567-158">Popis</span><span class="sxs-lookup"><span data-stu-id="5f567-158">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5f567-159">\<sdílené ></span><span class="sxs-lookup"><span data-stu-id="5f567-159">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|<span data-ttu-id="5f567-160">Určuje pověření použitá při ověřování klientů peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="5f567-160">Specifies credentials used when authenticating peer-to-peer clients.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5f567-161">Poznámky</span><span class="sxs-lookup"><span data-stu-id="5f567-161">Remarks</span></span>  
 <span data-ttu-id="5f567-162">Tento element konfigurace obsahuje instanci X509Certificate2 použít při ověřování okolí sdílené v mřížce.</span><span class="sxs-lookup"><span data-stu-id="5f567-162">This configuration element contains a X509Certificate2 instance used when authenticating neighbors in the peer mesh.</span></span>  
  
 <span data-ttu-id="5f567-163">Další informace o programování peer-to-peer, najdete v části [Peer-to-Peer sítě](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="5f567-163">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5f567-164">Příklad</span><span class="sxs-lookup"><span data-stu-id="5f567-164">Example</span></span>  
 <span data-ttu-id="5f567-165">Následující kód určuje, jak se najít certifikát používá ve scénáři peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="5f567-165">The following code specifies how to find the certificate used in a peer-to-peer scenario.</span></span>  
  
```xml  
<behaviors>  
 <endpointBehaviors>  
  <behavior name="MyEndpointBehavior">  
   <clientCredentials>  
    <peer>  
     <certificate findValue="www.contoso.com"   
                   storeLocation="LocalMachine"  
                   x509FindType="FindByIssuerName" />  
    </peer>  
   </clientCredentials>  
  </behavior>  
</endpointBehaviors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5f567-166">Viz také</span><span class="sxs-lookup"><span data-stu-id="5f567-166">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.Certificate%2A>  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateElement>  
 <xref:System.ServiceModel.Security.PeerCredential.Certificate%2A>  
 [<span data-ttu-id="5f567-167">Práce s certifikáty</span><span class="sxs-lookup"><span data-stu-id="5f567-167">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="5f567-168">Sítě peer-to-Peer</span><span class="sxs-lookup"><span data-stu-id="5f567-168">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="5f567-169">Ověřování zpráv rovnocenného kanálu</span><span class="sxs-lookup"><span data-stu-id="5f567-169">Peer Channel Message Authentication</span></span>](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="5f567-170">Vlastní ověřování rovnocenného kanálu</span><span class="sxs-lookup"><span data-stu-id="5f567-170">Peer Channel Custom Authentication</span></span>](http://msdn.microsoft.com/en-us/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="5f567-171">Zabezpečení aplikací rovnocenného kanálu</span><span class="sxs-lookup"><span data-stu-id="5f567-171">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
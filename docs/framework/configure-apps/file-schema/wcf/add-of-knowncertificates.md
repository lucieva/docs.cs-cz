---
title: "&lt;add&gt; – &lt;knownCertificates&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 128aaabe-3f1a-4c3b-b59f-898d0f02910f
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 30b3216842b602745ad40d1743175350aba78296
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/02/2017
---
# <a name="ltaddgt-of-ltknowncertificatesgt"></a><span data-ttu-id="637d3-102">&lt;add&gt; – &lt;knownCertificates&gt;</span><span class="sxs-lookup"><span data-stu-id="637d3-102">&lt;add&gt; of &lt;knownCertificates&gt;</span></span>
<span data-ttu-id="637d3-103">Přidá do kolekce známých certifikátů certifikát X.509.</span><span class="sxs-lookup"><span data-stu-id="637d3-103">Adds an X.509 certificate to the collection of known certificates.</span></span>  
  
 <span data-ttu-id="637d3-104">\<systém. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="637d3-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="637d3-105">\<chování ></span><span class="sxs-lookup"><span data-stu-id="637d3-105">\<behaviors></span></span>  
<span data-ttu-id="637d3-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="637d3-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="637d3-107">\<chování ></span><span class="sxs-lookup"><span data-stu-id="637d3-107">\<behavior></span></span>  
<span data-ttu-id="637d3-108">\<– serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="637d3-108">\<serviceCredentials></span></span>  
<span data-ttu-id="637d3-109">\<issuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="637d3-109">\<issuedTokenAuthentication></span></span>  
<span data-ttu-id="637d3-110">\<knownCertificates ></span><span class="sxs-lookup"><span data-stu-id="637d3-110">\<knownCertificates></span></span>  
<span data-ttu-id="637d3-111">\<Přidat ></span><span class="sxs-lookup"><span data-stu-id="637d3-111">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="637d3-112">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="637d3-112">Syntax</span></span>  
  
```xml  
<knownCertificates>   
   <add findValue="String"  
      storeLocation="CurrentUser/LocalMachine"  
      storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
      x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"/>  
</knownCertificates>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="637d3-113">Atributy a elementy</span><span class="sxs-lookup"><span data-stu-id="637d3-113">Attributes and Elements</span></span>  
 <span data-ttu-id="637d3-114">Následující části popisují atributy, podřízené prvky a nadřazené prvky.</span><span class="sxs-lookup"><span data-stu-id="637d3-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="637d3-115">Atributy</span><span class="sxs-lookup"><span data-stu-id="637d3-115">Attributes</span></span>  
  
|<span data-ttu-id="637d3-116">Atribut</span><span class="sxs-lookup"><span data-stu-id="637d3-116">Attribute</span></span>|<span data-ttu-id="637d3-117">Popis</span><span class="sxs-lookup"><span data-stu-id="637d3-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="637d3-118">findValue</span><span class="sxs-lookup"><span data-stu-id="637d3-118">findValue</span></span>|<span data-ttu-id="637d3-119">Řetězec.</span><span class="sxs-lookup"><span data-stu-id="637d3-119">String.</span></span> <span data-ttu-id="637d3-120">Hodnota, kterou chcete vyhledat.</span><span class="sxs-lookup"><span data-stu-id="637d3-120">The value to search for.</span></span>|  
|<span data-ttu-id="637d3-121">storeLocation</span><span class="sxs-lookup"><span data-stu-id="637d3-121">storeLocation</span></span>|<span data-ttu-id="637d3-122">Výčet.</span><span class="sxs-lookup"><span data-stu-id="637d3-122">Enumeration.</span></span> <span data-ttu-id="637d3-123">Jednu ze dvou ukládat prohledávaných umístění.</span><span class="sxs-lookup"><span data-stu-id="637d3-123">One of the two store locations to search.</span></span>|  
|<span data-ttu-id="637d3-124">storeName</span><span class="sxs-lookup"><span data-stu-id="637d3-124">storeName</span></span>|<span data-ttu-id="637d3-125">Výčet.</span><span class="sxs-lookup"><span data-stu-id="637d3-125">Enumeration.</span></span> <span data-ttu-id="637d3-126">Jeden z úložiště systému pro vyhledávání.</span><span class="sxs-lookup"><span data-stu-id="637d3-126">One of the system stores to search.</span></span>|  
|<span data-ttu-id="637d3-127">X509FindType</span><span class="sxs-lookup"><span data-stu-id="637d3-127">x509FindType</span></span>|<span data-ttu-id="637d3-128">Výčet.</span><span class="sxs-lookup"><span data-stu-id="637d3-128">Enumeration.</span></span> <span data-ttu-id="637d3-129">Jeden z pole certifikátu pro vyhledávání.</span><span class="sxs-lookup"><span data-stu-id="637d3-129">One of the certificate fields to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="637d3-130">findValue atribut</span><span class="sxs-lookup"><span data-stu-id="637d3-130">findValue Attribute</span></span>  
  
|<span data-ttu-id="637d3-131">Hodnota</span><span class="sxs-lookup"><span data-stu-id="637d3-131">Value</span></span>|<span data-ttu-id="637d3-132">Popis</span><span class="sxs-lookup"><span data-stu-id="637d3-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="637d3-133">String</span><span class="sxs-lookup"><span data-stu-id="637d3-133">String</span></span>|<span data-ttu-id="637d3-134">Hodnota závisí na poli (zadané v atributu X509FindType) být vyhledán.</span><span class="sxs-lookup"><span data-stu-id="637d3-134">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="637d3-135">Například pokud hledání kryptografický otisk, hodnota musí být řetězec o délce hexadecimální číslice.</span><span class="sxs-lookup"><span data-stu-id="637d3-135">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="637d3-136">Atribut x509FindType</span><span class="sxs-lookup"><span data-stu-id="637d3-136">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="637d3-137">Hodnota</span><span class="sxs-lookup"><span data-stu-id="637d3-137">Value</span></span>|<span data-ttu-id="637d3-138">Popis</span><span class="sxs-lookup"><span data-stu-id="637d3-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="637d3-139">Výčet</span><span class="sxs-lookup"><span data-stu-id="637d3-139">Enumeration</span></span>|<span data-ttu-id="637d3-140">Hodnoty patří: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="637d3-140">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="637d3-141">storeLocation atribut</span><span class="sxs-lookup"><span data-stu-id="637d3-141">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="637d3-142">Hodnota</span><span class="sxs-lookup"><span data-stu-id="637d3-142">Value</span></span>|<span data-ttu-id="637d3-143">Popis</span><span class="sxs-lookup"><span data-stu-id="637d3-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="637d3-144">Výčet</span><span class="sxs-lookup"><span data-stu-id="637d3-144">Enumeration</span></span>|<span data-ttu-id="637d3-145">CurrentUser nebo LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="637d3-145">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="637d3-146">storeName atribut</span><span class="sxs-lookup"><span data-stu-id="637d3-146">storeName Attribute</span></span>  
  
|<span data-ttu-id="637d3-147">Hodnota</span><span class="sxs-lookup"><span data-stu-id="637d3-147">Value</span></span>|<span data-ttu-id="637d3-148">Popis</span><span class="sxs-lookup"><span data-stu-id="637d3-148">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="637d3-149">Výčet</span><span class="sxs-lookup"><span data-stu-id="637d3-149">Enumeration</span></span>|<span data-ttu-id="637d3-150">Hodnoty patří: CertificateAuthority adresáře, AuthRoot, zakázané, Moje, Root, TrustedPeople a TrustedPublisher.</span><span class="sxs-lookup"><span data-stu-id="637d3-150">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="637d3-151">Podřízené elementy</span><span class="sxs-lookup"><span data-stu-id="637d3-151">Child Elements</span></span>  
 <span data-ttu-id="637d3-152">Žádné</span><span class="sxs-lookup"><span data-stu-id="637d3-152">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="637d3-153">Nadřazené elementy</span><span class="sxs-lookup"><span data-stu-id="637d3-153">Parent Elements</span></span>  
  
|<span data-ttu-id="637d3-154">Prvek</span><span class="sxs-lookup"><span data-stu-id="637d3-154">Element</span></span>|<span data-ttu-id="637d3-155">Popis</span><span class="sxs-lookup"><span data-stu-id="637d3-155">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="637d3-156">\<knownCertificates ></span><span class="sxs-lookup"><span data-stu-id="637d3-156">\<knownCertificates></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md)|<span data-ttu-id="637d3-157">Představuje kolekci certifikáty X.509, které jsou k dispozici ve zabezpečení tokenu služby (STS) pro ověřování tokenů zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="637d3-157">Represents a collection of X.509 certificates that are provided by a Security Token Service (STS) for validation of security tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="637d3-158">Poznámky</span><span class="sxs-lookup"><span data-stu-id="637d3-158">Remarks</span></span>  
 <span data-ttu-id="637d3-159">Vystavený token scénář má tři fáze.</span><span class="sxs-lookup"><span data-stu-id="637d3-159">The issued token scenario has three stages.</span></span> <span data-ttu-id="637d3-160">V první fázi se klient pokouší o přístup ke službě označuje *služby tokenů zabezpečení*.</span><span class="sxs-lookup"><span data-stu-id="637d3-160">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="637d3-161">Službu tokenů zabezpečení pak ověřuje klienta a následně vydá klienta token, obvykle token zabezpečení kontrolní výrazy Markup Language (SAML).</span><span class="sxs-lookup"><span data-stu-id="637d3-161">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="637d3-162">Klient pak vrátí ke službě pomocí tokenu.</span><span class="sxs-lookup"><span data-stu-id="637d3-162">The client then returns to the service with the token.</span></span> <span data-ttu-id="637d3-163">Služba prověří token pro data, která umožňuje službě ověření tokenu a proto klienta.</span><span class="sxs-lookup"><span data-stu-id="637d3-163">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="637d3-164">K ověření tokenu, certifikátu používá zabezpečené tokenu služby musí být známo ke službě.</span><span class="sxs-lookup"><span data-stu-id="637d3-164">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="637d3-165">[ \<IssuedTokenAuthentication >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) element slouží jako úložiště pro všechny zabezpečené služby tokenů certifikáty.</span><span class="sxs-lookup"><span data-stu-id="637d3-165">The [\<issuedTokenAuthentication>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="637d3-166">Chcete-li přidat certifikáty, použijte [ \<knownCertificates >](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="637d3-166">To add certificates, use the [\<knownCertificates>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span></span> <span data-ttu-id="637d3-167">Vložit [ \<Přidat > element \<knownCertificates > Element](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) pro každý certifikát, jak je znázorněno v následujícím příkladu.</span><span class="sxs-lookup"><span data-stu-id="637d3-167">Insert an [\<add> element \<knownCertificates> Element](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
```xml  
<issuedTokenAuthentication>  
   <knownCertificates>  
      <add findValue="www.contoso.com"   
           storeLocation="LocalMachine" storeName="My"   
           X509FindType="FindBySubjectName" />  
    </knownCertificates>  
</issuedTokenAuthentication>  
```  
  
 <span data-ttu-id="637d3-168">Ve výchozím nastavení musí získat certifikáty ze služby tokenu zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="637d3-168">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="637d3-169">Tyto "známé" certifikáty, ujistěte se, že který pouze oprávněné klientů můžete přístup ke službě.</span><span class="sxs-lookup"><span data-stu-id="637d3-169">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="637d3-170">Podmínky pro klienta k ověření pomocí federované služby a také další informace o použití tohoto elementu konfigurace najdete v tématu [postupy: Konfigurace pověření ve službě Federation](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="637d3-170">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="637d3-171">Další informace o federovaných scénářích najdete v tématu [federace a vystavené tokeny](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="637d3-171">For more information about federated scenarios, see [Federation and Issued Tokens](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="637d3-172">Příklad</span><span class="sxs-lookup"><span data-stu-id="637d3-172">Example</span></span>  
 <span data-ttu-id="637d3-173">Následující příklad přidá certifikát do úložiště pro všechny certifikáty, služby tokenů zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="637d3-173">The following example adds certificate to the repository for any STS certificates.</span></span>  
  
```xml  
<serviceBehaviors>  
 <behavior name="myServiceBehavior">  
  <serviceCredentials>  
   <issuedTokenAuthentication>  
    <knownCertificates>  
     <add findValue="www.contoso.com" storeLocation="LocalMachine"   
           storeName="CertificateAuthority"  
           x509FindType="FindByIssuerName" />  
     </knownCertificates>  
    </issuedTokenAuthentication>  
   </serviceCredentials>  
  </behavior>  
 </serviceBehaviors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="637d3-174">Viz také</span><span class="sxs-lookup"><span data-stu-id="637d3-174">See Also</span></span>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>  
 <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>  
 <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>  
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>  
 [<span data-ttu-id="637d3-175">\<knownCertificates ></span><span class="sxs-lookup"><span data-stu-id="637d3-175">\<knownCertificates></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md)  
 [<span data-ttu-id="637d3-176">Práce s certifikáty</span><span class="sxs-lookup"><span data-stu-id="637d3-176">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="637d3-177">Federace a vystavené tokeny</span><span class="sxs-lookup"><span data-stu-id="637d3-177">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="637d3-178">Postupy: Konfigurace pověření ve službě Federation</span><span class="sxs-lookup"><span data-stu-id="637d3-178">How to: Configure Credentials on a Federation Service</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)  
 [<span data-ttu-id="637d3-179">Zabezpečení služeb a klientů</span><span class="sxs-lookup"><span data-stu-id="637d3-179">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
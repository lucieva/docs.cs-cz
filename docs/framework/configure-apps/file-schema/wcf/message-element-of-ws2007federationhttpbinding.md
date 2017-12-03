---
title: "Element &lt;message&gt; – &lt;ws2007FederationHttpBinding&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 52cd941d-e230-4c82-8b29-333a7d20eca8
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 32361347665ee506b13d3be8a4257ca71e2629f0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="ltmessagegt-element-of-ltws2007federationhttpbindinggt"></a><span data-ttu-id="fe9f2-102">Element &lt;message&gt; – &lt;ws2007FederationHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="fe9f2-102">&lt;message&gt; element of &lt;ws2007FederationHttpBinding&gt;</span></span>
<span data-ttu-id="fe9f2-103">Definuje nastavení pro zprávy úroveň zabezpečení [ \<– ws2007FederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md) element.</span><span class="sxs-lookup"><span data-stu-id="fe9f2-103">Defines settings for the message-level security for the [\<ws2007FederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md) element.</span></span>  
  
 <span data-ttu-id="fe9f2-104">\<systém. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="fe9f2-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="fe9f2-105">\<vazby ></span><span class="sxs-lookup"><span data-stu-id="fe9f2-105">\<bindings></span></span>  
<span data-ttu-id="fe9f2-106">\<– ws2007FederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="fe9f2-106">\<ws2007FederationHttpBinding></span></span>  
<span data-ttu-id="fe9f2-107">\<Vazba ></span><span class="sxs-lookup"><span data-stu-id="fe9f2-107">\<binding></span></span>  
<span data-ttu-id="fe9f2-108">\<zabezpečení ></span><span class="sxs-lookup"><span data-stu-id="fe9f2-108">\<security></span></span>  
<span data-ttu-id="fe9f2-109">\<Zpráva ></span><span class="sxs-lookup"><span data-stu-id="fe9f2-109">\<message></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe9f2-110">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="fe9f2-110">Syntax</span></span>  
  
```xml  
<ws2007FederationBinding>  
   <binding >  
      <security>  
         <message   
            algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
            issuedTokenType="string"   
            issuedKeyType="SymmetricKey/PublicKey"  
            negotiateServiceCredential="Boolean" >  
            <claimTypeRequirements>  
               <add claimType="URI"  
                    isOptional="Boolean" />  
            </claimTypeRequirements>  
            <issuer address="Uri" >  
               <headers>  
                  <add name="String"  
                       namespace="String" />  
               </headers>  
               <identity>  
                  <certificate encodedValue="String"/>  
                  <certificateReference findValue="String"   
                     isChainIncluded="Boolean"  
                     storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
                     storeLocation="LocalMachine/CurrentUser"  
                     x509FindType=System.Security.Cryptography.X509certificates.X509findtype/>  
                  <dns value="String"/>  
                  <rsa value="String"/>  
                  <servicePrincipalName value="String"/>  
                  <usePrincipalName value="String"/>  
               </identity>  
            </issuer>  
            <issuerMetadata address=String" >  
               <headers>  
                  <add name="String"  
                       namespace="String" />  
               </headers>  
               <identity>  
                  <certificate encodedValue="String"/>  
                  <certificateReference findValue="String"   
                     isChainIncluded="Boolean"  
                     storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
                     storeLocation="LocalMachine/CurrentUser"  
                     X509FindType=System.Security.Cryptography.X509certificates.X509findtype/>  
                  <dns value="String"/>  
                  <rsa value="String"/>  
                  <servicePrincipalName value="String"/>  
                  <usePrincipalName value="String"/>  
               </identity>  
            </issuerMetadata>  
            <tokenRequestParameters>  
               <xmlElement>  
               </xmlElement>  
            </tokenRequestParameters>  
         </message>  
      </security>  
   </binding>  
</ws2007FederationBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fe9f2-111">Atributy a elementy</span><span class="sxs-lookup"><span data-stu-id="fe9f2-111">Attributes and Elements</span></span>  
 <span data-ttu-id="fe9f2-112">Následující části popisují atributy, podřízené prvky a nadřazené prvky.</span><span class="sxs-lookup"><span data-stu-id="fe9f2-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fe9f2-113">Atributy</span><span class="sxs-lookup"><span data-stu-id="fe9f2-113">Attributes</span></span>  
  
|<span data-ttu-id="fe9f2-114">Atribut</span><span class="sxs-lookup"><span data-stu-id="fe9f2-114">Attribute</span></span>|<span data-ttu-id="fe9f2-115">Popis</span><span class="sxs-lookup"><span data-stu-id="fe9f2-115">Description</span></span>|  
|---------------|-----------------|  
|`algorithmSuite`|<span data-ttu-id="fe9f2-116">Volitelné.</span><span class="sxs-lookup"><span data-stu-id="fe9f2-116">Optional.</span></span> <span data-ttu-id="fe9f2-117">Nastaví pro šifrování zpráv, podpisu a algoritmus klíče wrap.</span><span class="sxs-lookup"><span data-stu-id="fe9f2-117">Sets the message encryption, signature, and key-wrap algorithms.</span></span> <span data-ttu-id="fe9f2-118">Algoritmy a velikosti klíče jsou určeny <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> třídy.</span><span class="sxs-lookup"><span data-stu-id="fe9f2-118">The algorithms and the key sizes are determined by the <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> class.</span></span> <span data-ttu-id="fe9f2-119">Tyto algoritmy mapovat platformám zadaným v specifikace jazyka zásady zabezpečení (WS-SecurityPolicy).</span><span class="sxs-lookup"><span data-stu-id="fe9f2-119">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span><br /><br /> <span data-ttu-id="fe9f2-120">Najdete v následující tabulce možné hodnoty.</span><span class="sxs-lookup"><span data-stu-id="fe9f2-120">See the following table for possible values.</span></span> <span data-ttu-id="fe9f2-121">Výchozí hodnota je Basic256.</span><span class="sxs-lookup"><span data-stu-id="fe9f2-121">The default value is Basic256.</span></span>|  
|`issuedKeyType`|<span data-ttu-id="fe9f2-122">Určuje typ klíče pro vystavování.</span><span class="sxs-lookup"><span data-stu-id="fe9f2-122">Specifies the type of key to be issued.</span></span> <span data-ttu-id="fe9f2-123">Platné hodnoty patří:</span><span class="sxs-lookup"><span data-stu-id="fe9f2-123">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="fe9f2-124">-SymmetricKey</span><span class="sxs-lookup"><span data-stu-id="fe9f2-124">-   SymmetricKey</span></span><br /><span data-ttu-id="fe9f2-125">-PublicKey</span><span class="sxs-lookup"><span data-stu-id="fe9f2-125">-   PublicKey</span></span><br /><span data-ttu-id="fe9f2-126">-BearerKey</span><span class="sxs-lookup"><span data-stu-id="fe9f2-126">-   BearerKey</span></span><br /><br /> <span data-ttu-id="fe9f2-127">Výchozí hodnota je SymmetricKey.</span><span class="sxs-lookup"><span data-stu-id="fe9f2-127">The default is SymmetricKey.</span></span> <span data-ttu-id="fe9f2-128">Tento atribut je typu <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span><span class="sxs-lookup"><span data-stu-id="fe9f2-128">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|`issuedTokenType`|<span data-ttu-id="fe9f2-129">Identifikátor URI, který určuje typ token, který má být vystavené.</span><span class="sxs-lookup"><span data-stu-id="fe9f2-129">A URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="fe9f2-130">Výchozí hodnota je `null`.</span><span class="sxs-lookup"><span data-stu-id="fe9f2-130">The default is `null`.</span></span>|  
|`negotiateServiceCredential`|<span data-ttu-id="fe9f2-131">Hodnota, která určuje, zda přihlašovací údaje služby by měl být v rámci vyjednávání vyměňují nebo je k dispozici vzdálené správy.</span><span class="sxs-lookup"><span data-stu-id="fe9f2-131">A value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="fe9f2-132">Výchozí hodnota je `true`, což znamená, že je vyjednal přihlašovací údaje služby.</span><span class="sxs-lookup"><span data-stu-id="fe9f2-132">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="fe9f2-133">algorithmSuite atribut</span><span class="sxs-lookup"><span data-stu-id="fe9f2-133">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="fe9f2-134">Hodnota</span><span class="sxs-lookup"><span data-stu-id="fe9f2-134">Value</span></span>|<span data-ttu-id="fe9f2-135">Popis</span><span class="sxs-lookup"><span data-stu-id="fe9f2-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fe9f2-136">Basic128</span><span class="sxs-lookup"><span data-stu-id="fe9f2-136">Basic128</span></span>|<span data-ttu-id="fe9f2-137">Použijte šifrování pomocí algoritmu aes128 za pomoci, Sha1 pro hodnota hash a šifrování Rsa. oaep mgf1p pro zabalení klíče.</span><span class="sxs-lookup"><span data-stu-id="fe9f2-137">Use Aes128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="fe9f2-138">Basic192</span><span class="sxs-lookup"><span data-stu-id="fe9f2-138">Basic192</span></span>|<span data-ttu-id="fe9f2-139">Použijte šifrování pomocí Aes192, Sha1 pro hodnotu hash zpráv, oaep mgf1p Rsa pro zabalení klíče.</span><span class="sxs-lookup"><span data-stu-id="fe9f2-139">Use Aes192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="fe9f2-140">Basic256</span><span class="sxs-lookup"><span data-stu-id="fe9f2-140">Basic256</span></span>|<span data-ttu-id="fe9f2-141">Použijte šifrování pomocí Aes256, Sha1 pro hodnotu hash zpráv, oaep mgf1p Rsa pro zabalení klíče.</span><span class="sxs-lookup"><span data-stu-id="fe9f2-141">Use Aes256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="fe9f2-142">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="fe9f2-142">Basic256Rsa15</span></span>|<span data-ttu-id="fe9f2-143">Pomocí Aes256 pro šifrování zpráv, Sha1 pro hodnota hash a Rsa15 pro zabalení klíče.</span><span class="sxs-lookup"><span data-stu-id="fe9f2-143">Use Aes256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="fe9f2-144">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="fe9f2-144">Basic192Rsa15</span></span>|<span data-ttu-id="fe9f2-145">Použijte Aes192 pro šifrování zpráv, Sha1 pro hodnota hash a Rsa15 pro zabalení klíče.</span><span class="sxs-lookup"><span data-stu-id="fe9f2-145">Use Aes192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="fe9f2-146">TripleDes</span><span class="sxs-lookup"><span data-stu-id="fe9f2-146">TripleDes</span></span>|<span data-ttu-id="fe9f2-147">Použití šifrování TripleDes, Sha1 pro hodnotu hash zpráv, oaep mgf1p Rsa pro zabalení klíče.</span><span class="sxs-lookup"><span data-stu-id="fe9f2-147">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="fe9f2-148">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="fe9f2-148">Basic128Rsa15</span></span>|<span data-ttu-id="fe9f2-149">Pomocí algoritmu aes128 za pomoci pro šifrování zpráv, Sha1 pro hodnota hash a Rsa15 pro zabalení klíče.</span><span class="sxs-lookup"><span data-stu-id="fe9f2-149">Use Aes128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="fe9f2-150">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="fe9f2-150">TripleDesRsa15</span></span>|<span data-ttu-id="fe9f2-151">Použití šifrování TripleDes, Sha1 pro hodnota hash a Rsa15 pro zabalení klíče.</span><span class="sxs-lookup"><span data-stu-id="fe9f2-151">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="fe9f2-152">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="fe9f2-152">Basic128Sha256</span></span>|<span data-ttu-id="fe9f2-153">Pomocí Aes256 pro šifrování zpráv pro hodnota hash Sha256 a oaep mgf1p Rsa pro zabalení klíče.</span><span class="sxs-lookup"><span data-stu-id="fe9f2-153">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="fe9f2-154">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="fe9f2-154">Basic192Sha256</span></span>|<span data-ttu-id="fe9f2-155">Použijte Aes192 pro šifrování zpráv pro hodnota hash Sha256 a oaep mgf1p Rsa pro zabalení klíče.</span><span class="sxs-lookup"><span data-stu-id="fe9f2-155">Use Aes192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="fe9f2-156">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="fe9f2-156">Basic256Sha256</span></span>|<span data-ttu-id="fe9f2-157">Pomocí Aes256 pro šifrování zpráv pro hodnota hash Sha256 a oaep mgf1p Rsa pro zabalení klíče.</span><span class="sxs-lookup"><span data-stu-id="fe9f2-157">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="fe9f2-158">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="fe9f2-158">TripleDesSha256</span></span>|<span data-ttu-id="fe9f2-159">Použití šifrování TripleDes pro šifrování zpráv pro hodnota hash Sha256 a oaep mgf1p Rsa pro zabalení klíče.</span><span class="sxs-lookup"><span data-stu-id="fe9f2-159">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="fe9f2-160">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="fe9f2-160">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="fe9f2-161">Pomocí algoritmu aes128 za pomoci pro šifrování zpráv pro hodnota hash Sha256 a Rsa15 pro zabalení klíče.</span><span class="sxs-lookup"><span data-stu-id="fe9f2-161">Use Aes128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="fe9f2-162">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="fe9f2-162">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="fe9f2-163">Použijte Aes192 pro šifrování zpráv pro hodnota hash Sha256 a Rsa15 pro zabalení klíče.</span><span class="sxs-lookup"><span data-stu-id="fe9f2-163">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="fe9f2-164">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="fe9f2-164">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="fe9f2-165">Pomocí Aes256 pro šifrování zpráv pro hodnota hash Sha256 a Rsa15 pro zabalení klíče.</span><span class="sxs-lookup"><span data-stu-id="fe9f2-165">Use Aes256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="fe9f2-166">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="fe9f2-166">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="fe9f2-167">Použití šifrování TripleDes pro šifrování zpráv pro hodnota hash Sha256 a Rsa15 pro zabalení klíče.</span><span class="sxs-lookup"><span data-stu-id="fe9f2-167">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fe9f2-168">Podřízené elementy</span><span class="sxs-lookup"><span data-stu-id="fe9f2-168">Child Elements</span></span>  
  
|<span data-ttu-id="fe9f2-169">Prvek</span><span class="sxs-lookup"><span data-stu-id="fe9f2-169">Element</span></span>|<span data-ttu-id="fe9f2-170">Popis</span><span class="sxs-lookup"><span data-stu-id="fe9f2-170">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fe9f2-171">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="fe9f2-171">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-element.md)|<span data-ttu-id="fe9f2-172">Určuje kolekci typů deklarací identity pro tuto vazbu.</span><span class="sxs-lookup"><span data-stu-id="fe9f2-172">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="fe9f2-173">Každý element je typu <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="fe9f2-173">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|[<span data-ttu-id="fe9f2-174">\<Issuer ></span><span class="sxs-lookup"><span data-stu-id="fe9f2-174">\<issuer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuer.md)|<span data-ttu-id="fe9f2-175">Určuje koncový bod, který vydá token zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="fe9f2-175">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="fe9f2-176">Tento element je typu <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span><span class="sxs-lookup"><span data-stu-id="fe9f2-176">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|[<span data-ttu-id="fe9f2-177">\<issuerMetadata ></span><span class="sxs-lookup"><span data-stu-id="fe9f2-177">\<issuerMetadata></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata.md)|<span data-ttu-id="fe9f2-178">Určuje adresu koncového bodu vystavitele.</span><span class="sxs-lookup"><span data-stu-id="fe9f2-178">Specifies the endpoint address of the issuer.</span></span>|  
|[<span data-ttu-id="fe9f2-179">\<tokenRequestParameters ></span><span class="sxs-lookup"><span data-stu-id="fe9f2-179">\<tokenRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|<span data-ttu-id="fe9f2-180">Kolekce parametrů žádosti o token.</span><span class="sxs-lookup"><span data-stu-id="fe9f2-180">A collection of token request parameters.</span></span> <span data-ttu-id="fe9f2-181">Každý parametr je XML element.</span><span class="sxs-lookup"><span data-stu-id="fe9f2-181">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fe9f2-182">Nadřazené elementy</span><span class="sxs-lookup"><span data-stu-id="fe9f2-182">Parent Elements</span></span>  
  
|<span data-ttu-id="fe9f2-183">Prvek</span><span class="sxs-lookup"><span data-stu-id="fe9f2-183">Element</span></span>|<span data-ttu-id="fe9f2-184">Popis</span><span class="sxs-lookup"><span data-stu-id="fe9f2-184">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fe9f2-185">\<zabezpečení ></span><span class="sxs-lookup"><span data-stu-id="fe9f2-185">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md)|<span data-ttu-id="fe9f2-186">Definuje nastavení zabezpečení pro vazbu.</span><span class="sxs-lookup"><span data-stu-id="fe9f2-186">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fe9f2-187">Viz také</span><span class="sxs-lookup"><span data-stu-id="fe9f2-187">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>  
 <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>  
 <span data-ttu-id="fe9f2-188">`System.ServiceModel.Configuration.FederatedMessageSecurityElement`[Zabezpečení služeb a klientů](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)</span><span class="sxs-lookup"><span data-stu-id="fe9f2-188">`System.ServiceModel.Configuration.FederatedMessageSecurityElement` [Securing Services and Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)</span></span>  
 [<span data-ttu-id="fe9f2-189">Vazby</span><span class="sxs-lookup"><span data-stu-id="fe9f2-189">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="fe9f2-190">Konfigurace vazeb poskytovaných systémem</span><span class="sxs-lookup"><span data-stu-id="fe9f2-190">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="fe9f2-191">Používání vazeb ke konfiguraci služby Windows Communication Foundation a klienty</span><span class="sxs-lookup"><span data-stu-id="fe9f2-191">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="fe9f2-192">\<Vazba ></span><span class="sxs-lookup"><span data-stu-id="fe9f2-192">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
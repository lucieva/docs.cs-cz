---
title: '&lt;messageSenderAuthentication&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ea62fc06-55fb-42e0-aa2b-8867bdf4b415
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a008919cc068ca5cdd841ec67f1a7194bbffcd8c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/02/2017
---
# <a name="ltmessagesenderauthenticationgt"></a><span data-ttu-id="e5169-102">&lt;messageSenderAuthentication&gt;</span><span class="sxs-lookup"><span data-stu-id="e5169-102">&lt;messageSenderAuthentication&gt;</span></span>
<span data-ttu-id="e5169-103">Určuje nastavení ověřování pro sdílené certifikát používaný službou odesílatele zprávy.</span><span class="sxs-lookup"><span data-stu-id="e5169-103">Specifies authentication settings for peer certificate used by a message sender.</span></span>  
  
 <span data-ttu-id="e5169-104">\<systém. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="e5169-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e5169-105">\<chování ></span><span class="sxs-lookup"><span data-stu-id="e5169-105">\<behaviors></span></span>  
<span data-ttu-id="e5169-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="e5169-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="e5169-107">\<chování ></span><span class="sxs-lookup"><span data-stu-id="e5169-107">\<behavior></span></span>  
<span data-ttu-id="e5169-108">\<– serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="e5169-108">\<serviceCredentials></span></span>  
<span data-ttu-id="e5169-109">\<sdílené ></span><span class="sxs-lookup"><span data-stu-id="e5169-109">\<peer></span></span>  
<span data-ttu-id="e5169-110">\<messageSenderAuthentication ></span><span class="sxs-lookup"><span data-stu-id="e5169-110">\<messageSenderAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5169-111">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="e5169-111">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication  
   customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"  
   certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"  
   revocationMode="NoCheck/Online/Offline"  
   trustedStoreLocation="CurrentUser/LocalMachine"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e5169-112">Atributy a elementy</span><span class="sxs-lookup"><span data-stu-id="e5169-112">Attributes and Elements</span></span>  
 <span data-ttu-id="e5169-113">Následující části popisují atributy, podřízené prvky a nadřazené prvky.</span><span class="sxs-lookup"><span data-stu-id="e5169-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e5169-114">Atributy</span><span class="sxs-lookup"><span data-stu-id="e5169-114">Attributes</span></span>  
  
|<span data-ttu-id="e5169-115">Atribut</span><span class="sxs-lookup"><span data-stu-id="e5169-115">Attribute</span></span>|<span data-ttu-id="e5169-116">Popis</span><span class="sxs-lookup"><span data-stu-id="e5169-116">Description</span></span>|  
|---------------|-----------------|  
|`certificateValidationMode`|<span data-ttu-id="e5169-117">Volitelné výčtu.</span><span class="sxs-lookup"><span data-stu-id="e5169-117">Optional enumeration.</span></span> <span data-ttu-id="e5169-118">Určuje jeden z pěti režimů slouží k ověření přihlašovacích údajů.</span><span class="sxs-lookup"><span data-stu-id="e5169-118">Specifies one of five modes used to validate credentials.</span></span> <span data-ttu-id="e5169-119">Tento atribut je typu <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span><span class="sxs-lookup"><span data-stu-id="e5169-119">This attribute is of type <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span></span> <span data-ttu-id="e5169-120">Pokud nastavena na `Custom`, pak `customCertificateValidator` musí být uveden také.</span><span class="sxs-lookup"><span data-stu-id="e5169-120">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`customCertificateValidatorType`|<span data-ttu-id="e5169-121">Volitelný řetězec.</span><span class="sxs-lookup"><span data-stu-id="e5169-121">Optional string.</span></span> <span data-ttu-id="e5169-122">Určuje typ a sestavení, které slouží k ověření vlastního typu.</span><span class="sxs-lookup"><span data-stu-id="e5169-122">Specifies a type and assembly used to validate a custom type.</span></span> <span data-ttu-id="e5169-123">Tento atribut musí být nastaven při `certificateValidationMode` je nastaven na `Custom`.</span><span class="sxs-lookup"><span data-stu-id="e5169-123">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span> <span data-ttu-id="e5169-124">Tento atribut je typu <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="e5169-124">This attribute is of type <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<span data-ttu-id="e5169-125">poskytuje sdílené výchozí validátor certifikátu, který ověřuje certifikátu partnerského proti úložiště důvěryhodných osob.</span><span class="sxs-lookup"><span data-stu-id="e5169-125"> provides a default peer certificate validator that verifies the peer certificate against the trusted people store.</span></span> <span data-ttu-id="e5169-126">Také ověřuje, že certifikát řetězí platný kořenový.</span><span class="sxs-lookup"><span data-stu-id="e5169-126">It also verifies that the certificate chains up to a valid root.</span></span> <span data-ttu-id="e5169-127">Můžete implementovat vlastní validátor zadejte odlišné chování a používat tento atribut tak, aby odkazovalo na vlastní validátor.</span><span class="sxs-lookup"><span data-stu-id="e5169-127">You can implement a custom validator to specify a different behavior and use this attribute to point to the custom validator.</span></span>|  
|`revocationMode`|<span data-ttu-id="e5169-128">Volitelné výčtu.</span><span class="sxs-lookup"><span data-stu-id="e5169-128">Optional enumeration.</span></span> <span data-ttu-id="e5169-129">Určuje režim odvolání certifikátu.</span><span class="sxs-lookup"><span data-stu-id="e5169-129">Specifies the certificate revocation mode.</span></span> <span data-ttu-id="e5169-130">Tento atribut je typu <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span><span class="sxs-lookup"><span data-stu-id="e5169-130">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span></span> <span data-ttu-id="e5169-131">Systém ověří, že sdílené certifikát nebyl odvolaný podle vyhledá v seznamu odvolaných certifikátů.</span><span class="sxs-lookup"><span data-stu-id="e5169-131">The system verifies that the peer certificate has not been revoked by looking it up in the revoked certificate list.</span></span> <span data-ttu-id="e5169-132">Tato kontrola může provést kontrolou online nebo seznam odvolaných certifikátů uložené v mezipaměti.</span><span class="sxs-lookup"><span data-stu-id="e5169-132">This check can be performed either by checking online or against a cached revocation list.</span></span> <span data-ttu-id="e5169-133">Kontrola odvolání může být vypnuto nastavením tohoto atributu na hodnotu NoCheck.</span><span class="sxs-lookup"><span data-stu-id="e5169-133">Revocation checking can be turned off by setting this attribute to NoCheck.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="e5169-134">Volitelné výčtu.</span><span class="sxs-lookup"><span data-stu-id="e5169-134">Optional enumeration.</span></span> <span data-ttu-id="e5169-135">Určuje umístění důvěryhodného úložiště, kde je ověřen certifikátu partnerského [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] zabezpečení systému.</span><span class="sxs-lookup"><span data-stu-id="e5169-135">Specifies the trusted store location where the peer certificate is validated by the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] security system.</span></span> <span data-ttu-id="e5169-136">Tento atribut je typu <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span><span class="sxs-lookup"><span data-stu-id="e5169-136">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e5169-137">Podřízené elementy</span><span class="sxs-lookup"><span data-stu-id="e5169-137">Child Elements</span></span>  
 <span data-ttu-id="e5169-138">Žádné</span><span class="sxs-lookup"><span data-stu-id="e5169-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e5169-139">Nadřazené elementy</span><span class="sxs-lookup"><span data-stu-id="e5169-139">Parent Elements</span></span>  
  
|<span data-ttu-id="e5169-140">Prvek</span><span class="sxs-lookup"><span data-stu-id="e5169-140">Element</span></span>|<span data-ttu-id="e5169-141">Popis</span><span class="sxs-lookup"><span data-stu-id="e5169-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e5169-142">\<sdílené ></span><span class="sxs-lookup"><span data-stu-id="e5169-142">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|<span data-ttu-id="e5169-143">Určuje, že aktuální přihlašovací údaje pro uzel sdílené.</span><span class="sxs-lookup"><span data-stu-id="e5169-143">Specifies the current credentials for a peer node.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5169-144">Poznámky</span><span class="sxs-lookup"><span data-stu-id="e5169-144">Remarks</span></span>  
 <span data-ttu-id="e5169-145">Tento element musí být nakonfigurován, pokud je zvoleno ověřování zpráv.</span><span class="sxs-lookup"><span data-stu-id="e5169-145">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="e5169-146">Pro výstup kanály, je každá zpráva podepsaná pomocí certifikátu poskytované [ \<certifikátu >](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md).</span><span class="sxs-lookup"><span data-stu-id="e5169-146">For output channels, each message is signed using the certificate provided by [\<certificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md).</span></span> <span data-ttu-id="e5169-147">Všechny zprávy před doručí aplikaci, je zkontrolován pověřením zpráv pomocí validátor určeného `customCertificateValidatorType` atribut tohoto elementu.</span><span class="sxs-lookup"><span data-stu-id="e5169-147">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="e5169-148">Validátor můžete buď přijmout nebo odmítnout přihlašovací údaje.</span><span class="sxs-lookup"><span data-stu-id="e5169-148">The validator can either accept or reject the credential.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5169-149">Viz také</span><span class="sxs-lookup"><span data-stu-id="e5169-149">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>  
 <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>  
 <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>  
 [<span data-ttu-id="e5169-150">Práce s certifikáty</span><span class="sxs-lookup"><span data-stu-id="e5169-150">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="e5169-151">Sítě peer-to-Peer</span><span class="sxs-lookup"><span data-stu-id="e5169-151">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="e5169-152">Ověřování zpráv rovnocenného kanálu</span><span class="sxs-lookup"><span data-stu-id="e5169-152">Peer Channel Message Authentication</span></span>](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="e5169-153">Vlastní ověřování rovnocenného kanálu</span><span class="sxs-lookup"><span data-stu-id="e5169-153">Peer Channel Custom Authentication</span></span>](http://msdn.microsoft.com/en-us/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="e5169-154">Zabezpečení aplikací rovnocenného kanálu</span><span class="sxs-lookup"><span data-stu-id="e5169-154">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
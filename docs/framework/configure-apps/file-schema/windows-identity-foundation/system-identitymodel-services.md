---
title: '&lt;system.identityModel.services&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fa1624dd-2d74-4ae3-942e-498cee261ac5
caps.latest.revision: "6"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: a5f0b6b207fbd51504149fd5c245f41ef89f17f4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="ltsystemidentitymodelservicesgt"></a><span data-ttu-id="10590-102">&lt;system.identityModel.services&gt;</span><span class="sxs-lookup"><span data-stu-id="10590-102">&lt;system.identityModel.services&gt;</span></span>
<span data-ttu-id="10590-103">Konfigurační oddíl pro ověřování pomocí protokolu WS-Federation.</span><span class="sxs-lookup"><span data-stu-id="10590-103">Configuration section for authentication using the WS-Federation protocol.</span></span>  
  
 <span data-ttu-id="10590-104">\<system.identityModel.services ></span><span class="sxs-lookup"><span data-stu-id="10590-104">\<system.identityModel.services></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10590-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="10590-105">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="10590-106">Atributy a elementy</span><span class="sxs-lookup"><span data-stu-id="10590-106">Attributes and Elements</span></span>  
 <span data-ttu-id="10590-107">Následující části popisují atributy, podřízené prvky a nadřazené prvky.</span><span class="sxs-lookup"><span data-stu-id="10590-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="10590-108">Atributy</span><span class="sxs-lookup"><span data-stu-id="10590-108">Attributes</span></span>  
 <span data-ttu-id="10590-109">Žádné</span><span class="sxs-lookup"><span data-stu-id="10590-109">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="10590-110">Podřízené elementy</span><span class="sxs-lookup"><span data-stu-id="10590-110">Child Elements</span></span>  
  
|<span data-ttu-id="10590-111">Prvek</span><span class="sxs-lookup"><span data-stu-id="10590-111">Element</span></span>|<span data-ttu-id="10590-112">Popis</span><span class="sxs-lookup"><span data-stu-id="10590-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="10590-113">\<federationConfiguration ></span><span class="sxs-lookup"><span data-stu-id="10590-113">\<federationConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|<span data-ttu-id="10590-114">Obsahuje nastavení, která konfigurace <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) a <xref:System.IdentityModel.Services.SessionAuthenticationModule> modulů HTTP (SAM).</span><span class="sxs-lookup"><span data-stu-id="10590-114">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) HTTP modules.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="10590-115">Nadřazené elementy</span><span class="sxs-lookup"><span data-stu-id="10590-115">Parent Elements</span></span>  
 <span data-ttu-id="10590-116">Žádné</span><span class="sxs-lookup"><span data-stu-id="10590-116">None</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="10590-117">Poznámky</span><span class="sxs-lookup"><span data-stu-id="10590-117">Remarks</span></span>  
 <span data-ttu-id="10590-118">Přidat `<system.identityModel.services>` části do vaší aplikace konfiguračního souboru k poskytování nastavení SAM a WSFAM.</span><span class="sxs-lookup"><span data-stu-id="10590-118">Add a `<system.identityModel.services>` section to your application’s configuration file to provide settings for the SAM and WSFAM.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="10590-119">Při použití <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> nebo <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> třída k poskytování řízení přístupu na základě deklarace identity ve vašem kódu, Správce autorizací deklarace identity (<xref:System.Security.Claims.ClaimsAuthorizationManager>) a zásad, který se používá pro autorizační rozhodnutí konfigurované prostřednictvím `<identityConfiguration>` element, který je odkazován implicitně nebo explicitně z `<federationConfiguration>` elementu v této části.</span><span class="sxs-lookup"><span data-stu-id="10590-119">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the claims authorization manager (<xref:System.Security.Claims.ClaimsAuthorizationManager>) and policy that is used to make authorization decisions are configured through an `<identityConfiguration>` element that is implicitly or explicitly referenced from a `<federationConfiguration>` element in this section.</span></span> <span data-ttu-id="10590-120">Další informace najdete v tématu **poznámky** pod [ \<federationConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) element.</span><span class="sxs-lookup"><span data-stu-id="10590-120">For more information, see the **Remarks** under the [\<federationConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) element.</span></span>  
  
 <span data-ttu-id="10590-121">`<system.identityModel.services>` Část je reprezentována <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> třídy.</span><span class="sxs-lookup"><span data-stu-id="10590-121">The `<system.identityModel.services>` section is represented by the <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> class.</span></span> <span data-ttu-id="10590-122">Kolekce podřízených `<federationConfiguration>` elementy nakonfigurovali v sekci je reprezentována <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> třídy.</span><span class="sxs-lookup"><span data-stu-id="10590-122">The collection of child `<federationConfiguration>` elements configured in the section is represented by the <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="10590-123">Příklad</span><span class="sxs-lookup"><span data-stu-id="10590-123">Example</span></span>  
 <span data-ttu-id="10590-124">Následující kód XML ukazuje, jak přidat `<system.identityModel.services>` oddíl konfiguračního souboru.</span><span class="sxs-lookup"><span data-stu-id="10590-124">The following XML shows how to add a `<system.identityModel.services>` section to a configuration file.</span></span> <span data-ttu-id="10590-125">Je nutné nejdříve přidat části deklarace pro oba `<system.identityModel.services>` části a `<system.identityModel>` části.</span><span class="sxs-lookup"><span data-stu-id="10590-125">You must first add section declarations for both the `<system.identityModel.services>` section and the `<system.identityModel>` sections.</span></span> <span data-ttu-id="10590-126">(Když přidáte `<system.identityModel.services>` části, měli byste také přidat deklaraci pro `<system.identityModel>` části zajistit, aby výchozí `<identityConfiguration>` části lze vytvořit pomocí modulu runtime, v případě potřeby.) Po nebyly přidané deklarace oddílu, můžete nakonfigurovat nastavení federovaného ověřování v rámci `<system.identityModel.services>` elementu.</span><span class="sxs-lookup"><span data-stu-id="10590-126">(When you add a `<system.identityModel.services>` section, you should also add a declaration for the `<system.identityModel>` section to ensure that a default `<identityConfiguration>` section can be created by the runtime if necessary.) After the section declarations have been added, you can configure federated authentication settings under the `<system.identityModel.services>` element.</span></span>  
  
```xml  
<configuration>  
  <configSections>  
    <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
    <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
  </configSections>  
  
  <!-- Additional elements (not shown) -->  
  
  <system.identityModel.services>  
    <federationConfiguration>  
      <wsFederation passiveRedirectEnabled="true"   
        issuer="http://localhost:15839/wsFederationSTS/Issue"   
        realm="http://localhost:50969/" reply="http://localhost:50969/"   
        requireHttps="false"   
        signOutReply="http://localhost:50969/SignedOutPage.html"   
        signOutQueryString="Param1=value2&Param2=value2"   
        persistentCookiesOnPassiveRedirects="true" />  
      <cookieHandler requireSsl="false" />  
    </federationConfiguration>  
  </system.identityModel.services>  
  
</configuration>  
```
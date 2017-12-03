---
title: '&lt;identityConfiguration&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1db76253-07da-447b-9e7a-3705c7228cf4
caps.latest.revision: "13"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: b1cca286fc967631c60aa02a1318fe24120e05b0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="ltidentityconfigurationgt"></a><span data-ttu-id="3653a-102">&lt;identityConfiguration&gt;</span><span class="sxs-lookup"><span data-stu-id="3653a-102">&lt;identityConfiguration&gt;</span></span>
<span data-ttu-id="3653a-103">Určuje nastavení identity úrovně služeb.</span><span class="sxs-lookup"><span data-stu-id="3653a-103">Specifies service-level identity settings.</span></span>  
  
 <span data-ttu-id="3653a-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="3653a-104">\<system.identityModel></span></span>  
<span data-ttu-id="3653a-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="3653a-105">\<identityConfiguration></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3653a-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="3653a-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration  
      name=xs:string  
      saveBootstrapContext=xs:boolean>  
      maximumClockSkew=TimeSpan >  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3653a-107">Atributy a elementy</span><span class="sxs-lookup"><span data-stu-id="3653a-107">Attributes and Elements</span></span>  
 <span data-ttu-id="3653a-108">Následující části popisují atributy, podřízené prvky a nadřazené prvky.</span><span class="sxs-lookup"><span data-stu-id="3653a-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3653a-109">Atributy</span><span class="sxs-lookup"><span data-stu-id="3653a-109">Attributes</span></span>  
  
|<span data-ttu-id="3653a-110">Atribut</span><span class="sxs-lookup"><span data-stu-id="3653a-110">Attribute</span></span>|<span data-ttu-id="3653a-111">Popis</span><span class="sxs-lookup"><span data-stu-id="3653a-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3653a-112">name</span><span class="sxs-lookup"><span data-stu-id="3653a-112">name</span></span>|<span data-ttu-id="3653a-113">Název konfiguračního oddílu identity.</span><span class="sxs-lookup"><span data-stu-id="3653a-113">The name of the identity configuration section.</span></span> <span data-ttu-id="3653a-114">Tento název vám pomůže odkazovat na konkrétní konfigurační oddíl.</span><span class="sxs-lookup"><span data-stu-id="3653a-114">You can use this name to reference a specific configuration section.</span></span> <span data-ttu-id="3653a-115">Pokud žádné `name` zadán atribut, v části definuje výchozí konfiguraci.</span><span class="sxs-lookup"><span data-stu-id="3653a-115">If no `name` attribute is specified, the section defines the default configuration.</span></span> <span data-ttu-id="3653a-116">Výchozí konfigurace je vždy používá pro scénáře pasivní federace.</span><span class="sxs-lookup"><span data-stu-id="3653a-116">The default configuration is always used for passive federation scenarios.</span></span> <span data-ttu-id="3653a-117">Další informace najdete v tématu [ \<federationConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) element.</span><span class="sxs-lookup"><span data-stu-id="3653a-117">For more information, see the [\<federationConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) element.</span></span>|  
|<span data-ttu-id="3653a-118">saveBootstrapContext</span><span class="sxs-lookup"><span data-stu-id="3653a-118">saveBootstrapContext</span></span>|<span data-ttu-id="3653a-119">Určuje, zda bootstrap tokeny mají být zahrnuty v tokenu relace.</span><span class="sxs-lookup"><span data-stu-id="3653a-119">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="3653a-120">Hodnota může být také nastaven na kolekci obslužná rutina tokenu nastavením `saveBootstrapContext` atributu u [ \<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) element.</span><span class="sxs-lookup"><span data-stu-id="3653a-120">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<securityTokenHandlerConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) element.</span></span> <span data-ttu-id="3653a-121">Hodnota nastavení kolekce obslužná rutina tokenu přepíše hodnotu nastavit na službu.</span><span class="sxs-lookup"><span data-stu-id="3653a-121">A value set on the token handler collection overrides the value set on the service.</span></span>|  
|<span data-ttu-id="3653a-122">maximumClockSkew</span><span class="sxs-lookup"><span data-stu-id="3653a-122">maximumClockSkew</span></span>|<span data-ttu-id="3653a-123">A <xref:System.TimeSpan> , určuje zkosení maximální povolené hodiny.</span><span class="sxs-lookup"><span data-stu-id="3653a-123">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="3653a-124">Určuje maximální povolený hodiny zkosení při provádění operace náročné na čas, jako je například ověřování čas vypršení platnosti relace přihlášení.</span><span class="sxs-lookup"><span data-stu-id="3653a-124">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="3653a-125">Výchozí hodnota je 5 minut, "00: 05:00".</span><span class="sxs-lookup"><span data-stu-id="3653a-125">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="3653a-126">Další informace o tom, jak zadat <xref:System.TimeSpan> hodnoty, najdete v části [časový interval hodnoty](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="3653a-126">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="3653a-127">Maximální hodiny zkosení může být také nastaven na kolekci obslužná rutina tokenu nastavením `maximumClockSkew` atributu u [ \<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) element.</span><span class="sxs-lookup"><span data-stu-id="3653a-127">The maximum clock skew may also be set on a token handler collection by setting the `maximumClockSkew` attribute on the [\<securityTokenHandlerConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) element.</span></span> <span data-ttu-id="3653a-128">Hodnota nastavení kolekce obslužná rutina tokenu přepíše hodnotu nastavit na službu.</span><span class="sxs-lookup"><span data-stu-id="3653a-128">A value set on the token handler collection overrides the value set on the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3653a-129">Podřízené elementy</span><span class="sxs-lookup"><span data-stu-id="3653a-129">Child Elements</span></span>  
  
|<span data-ttu-id="3653a-130">Prvek</span><span class="sxs-lookup"><span data-stu-id="3653a-130">Element</span></span>|<span data-ttu-id="3653a-131">Popis</span><span class="sxs-lookup"><span data-stu-id="3653a-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3653a-132">\<ukládá do mezipaměti ></span><span class="sxs-lookup"><span data-stu-id="3653a-132">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="3653a-133">Zaregistruje mezipamětí použít pro tokeny relace a rozpoznání opětovného přehrání tokenu.</span><span class="sxs-lookup"><span data-stu-id="3653a-133">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="3653a-134">Můžete zadat na úrovni služby, nebo na kolekci obslužná rutina tokenu zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="3653a-134">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="3653a-135">Volitelné.</span><span class="sxs-lookup"><span data-stu-id="3653a-135">Optional.</span></span>|  
|[<span data-ttu-id="3653a-136">\<certificateValidation ></span><span class="sxs-lookup"><span data-stu-id="3653a-136">\<certificateValidation></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|<span data-ttu-id="3653a-137">Určuje nastavení, které tokenu obslužné rutiny používají k ověření certifikátů.</span><span class="sxs-lookup"><span data-stu-id="3653a-137">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="3653a-138">Můžete zadat na úrovni služby, nebo na kolekci obslužná rutina tokenu zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="3653a-138">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="3653a-139">Volitelné.</span><span class="sxs-lookup"><span data-stu-id="3653a-139">Optional.</span></span>|  
|[<span data-ttu-id="3653a-140">\<claimsAuthenticationManager ></span><span class="sxs-lookup"><span data-stu-id="3653a-140">\<claimsAuthenticationManager></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthenticationmanager.md)|<span data-ttu-id="3653a-141">Zaregistruje manažera ověřování deklarací identity pro příchozí deklarace identity.</span><span class="sxs-lookup"><span data-stu-id="3653a-141">Registers a claims authentication manager for the incoming claims.</span></span> <span data-ttu-id="3653a-142">Volitelné.</span><span class="sxs-lookup"><span data-stu-id="3653a-142">Optional.</span></span>|  
|[<span data-ttu-id="3653a-143">\<claimsAuthorizationManager ></span><span class="sxs-lookup"><span data-stu-id="3653a-143">\<claimsAuthorizationManager></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthorizationmanager.md)|<span data-ttu-id="3653a-144">Zaregistruje Správce autorizací příchozí deklarace identity deklarací identity.</span><span class="sxs-lookup"><span data-stu-id="3653a-144">Registers a claims authorization manager for the incoming claims.</span></span> <span data-ttu-id="3653a-145">Volitelné.</span><span class="sxs-lookup"><span data-stu-id="3653a-145">Optional.</span></span>|  
|[<span data-ttu-id="3653a-146">\<claimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="3653a-146">\<claimTypeRequired></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtyperequired.md)|<span data-ttu-id="3653a-147">Určuje sadu požadované deklarací identity pro příchozí tokeny zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="3653a-147">Specifies the set of required claims for incoming security tokens.</span></span> <span data-ttu-id="3653a-148">Volitelné.</span><span class="sxs-lookup"><span data-stu-id="3653a-148">Optional.</span></span>|  
|[<span data-ttu-id="3653a-149">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="3653a-149">\<securityTokenHandlers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|<span data-ttu-id="3653a-150">Určuje kolekci rutin tokenu zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="3653a-150">Specifies a collection of security token handlers.</span></span> <span data-ttu-id="3653a-151">Je možné zadat nula nebo více kolekcí obslužné rutiny tokenu zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="3653a-151">Zero or more collections of security token handlers can be specified.</span></span> <span data-ttu-id="3653a-152">Volitelné.</span><span class="sxs-lookup"><span data-stu-id="3653a-152">Optional.</span></span>|  
|[<span data-ttu-id="3653a-153">\<tokenReplayDetection ></span><span class="sxs-lookup"><span data-stu-id="3653a-153">\<tokenReplayDetection></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)|<span data-ttu-id="3653a-154">Umožňuje rozpoznání opětovného přehrání tokenu a určuje dobu vypršení platnosti tokenů.</span><span class="sxs-lookup"><span data-stu-id="3653a-154">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="3653a-155">Můžete zadat na úrovni služby, nebo na kolekci obslužná rutina tokenu zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="3653a-155">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="3653a-156">Volitelné.</span><span class="sxs-lookup"><span data-stu-id="3653a-156">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3653a-157">Nadřazené elementy</span><span class="sxs-lookup"><span data-stu-id="3653a-157">Parent Elements</span></span>  
  
|<span data-ttu-id="3653a-158">Prvek</span><span class="sxs-lookup"><span data-stu-id="3653a-158">Element</span></span>|<span data-ttu-id="3653a-159">Popis</span><span class="sxs-lookup"><span data-stu-id="3653a-159">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3653a-160">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="3653a-160">\<system.identityModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md)|<span data-ttu-id="3653a-161">Poskytuje konfigurace pro povolení možnosti Windows Identity Foundation (WIF) v aplikacích.</span><span class="sxs-lookup"><span data-stu-id="3653a-161">Provides configuration for enabling Windows Identity Foundation (WIF) options in applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3653a-162">Poznámky</span><span class="sxs-lookup"><span data-stu-id="3653a-162">Remarks</span></span>  
 <span data-ttu-id="3653a-163">Více identit, které se konfigurace může být definována, každý s jedinečným názvem.</span><span class="sxs-lookup"><span data-stu-id="3653a-163">Multiple identity configurations may be defined, each with a unique name.</span></span> <span data-ttu-id="3653a-164">Toto chování je následujícím způsobem:</span><span class="sxs-lookup"><span data-stu-id="3653a-164">The behavior is as follows:</span></span>  
  
1.  <span data-ttu-id="3653a-165">Pokud žádné `<identityConfiguration>` zadaný element.</span><span class="sxs-lookup"><span data-stu-id="3653a-165">If no `<identityConfiguration>` element is specified.</span></span> <span data-ttu-id="3653a-166">Výchozí konfigurace identity je vytvoří za běhu a zadat výchozí hodnoty.</span><span class="sxs-lookup"><span data-stu-id="3653a-166">A default identity configuration is created at runtime and populated with default values.</span></span>  
  
2.  <span data-ttu-id="3653a-167">Pokud jeden `<identityConfiguration>` zadaný element.</span><span class="sxs-lookup"><span data-stu-id="3653a-167">If a single `<identityConfiguration>` element is specified.</span></span> <span data-ttu-id="3653a-168">To je výchozí konfigurace identity.</span><span class="sxs-lookup"><span data-stu-id="3653a-168">It is the default identity configuration.</span></span> <span data-ttu-id="3653a-169">Nezáleží, jestli je s názvem nebo nepojmenované.</span><span class="sxs-lookup"><span data-stu-id="3653a-169">It does not matter whether it is named or unnamed.</span></span>  
  
3.  <span data-ttu-id="3653a-170">Pokud je to více `<identityConfiguration>` elementy nejsou zadány.</span><span class="sxs-lookup"><span data-stu-id="3653a-170">If multiple `<identityConfiguration>` elements are specified.</span></span> <span data-ttu-id="3653a-171">Nepojmenované element určuje výchozí konfigurace identity.</span><span class="sxs-lookup"><span data-stu-id="3653a-171">The unnamed element specifies the default identity configuration.</span></span> <span data-ttu-id="3653a-172">Dále je doporučeno při zadávání více `<identityConfiguration>` elementy, jeden z nich měli nepojmenované.</span><span class="sxs-lookup"><span data-stu-id="3653a-172">It is recommended that when you specify multiple `<identityConfiguration>` elements, one of them should be unnamed.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="3653a-173">Pokud zadáte více `<identityConfiguration>` elementy, jeden z nich měli nepojmenované.</span><span class="sxs-lookup"><span data-stu-id="3653a-173">If you specify multiple `<identityConfiguration>` elements, one of them should be unnamed.</span></span> <span data-ttu-id="3653a-174">Nepojmenované prvek bude výchozí konfigurace identity.</span><span class="sxs-lookup"><span data-stu-id="3653a-174">The unnamed element will be the default identity configuration.</span></span>  
  
 <span data-ttu-id="3653a-175">Některá nastavení zadané v `<identityConfiguration>` element lze přepsat nastavením na kolekci obslužná rutina tokenu zabezpečení nebo nastavení na jednotlivých zabezpečení tokenu obslužné rutiny.</span><span class="sxs-lookup"><span data-stu-id="3653a-175">Some of the settings specified in the `<identityConfiguration>` element can be overridden by settings on a security token handler collection or by settings on individual security token handlers.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3653a-176">Při použití <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> nebo <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> třída k poskytování řízení přístupu na základě deklarace identity ve vašem kódu konfiguraci identity, která odkazuje `<federationConfiguration>` element nakonfiguruje Správce autorizací deklarace identity a zásadu, která se používá k zajištění rozhodnutí o autorizaci.</span><span class="sxs-lookup"><span data-stu-id="3653a-176">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the identity configuration that is referenced by the `<federationConfiguration>` element configures the claims authorization manager and policy that is used to make authorization decisions.</span></span> <span data-ttu-id="3653a-177">Je to ve scénářích, které nejsou pasivní scénáře webového, například aplikace Windows Communication Foundation (WCF) nebo aplikaci, která není založené na webu.</span><span class="sxs-lookup"><span data-stu-id="3653a-177">This is true, even in scenarios that are not passive Web scenarios, for example Windows Communication Foundation (WCF) applications or an application that is not Web-based.</span></span> <span data-ttu-id="3653a-178">Pokud aplikace není pasivní webové aplikace [ \<claimsAuthorizationManager >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthorizationmanager.md) element (a jeho podřízených elementů zásad, pokud existuje) konfigurace odkazované identity jsou jenom nastavení použité.</span><span class="sxs-lookup"><span data-stu-id="3653a-178">If the application is not a passive Web application, the [\<claimsAuthorizationManager>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthorizationmanager.md) element (and its child policy elements, if present) of the referenced identity configuration are the only settings applied.</span></span> <span data-ttu-id="3653a-179">Všechna ostatní nastavení se ignorují.</span><span class="sxs-lookup"><span data-stu-id="3653a-179">All other settings are ignored.</span></span> <span data-ttu-id="3653a-180">Další informace najdete v tématu [ \<federationConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) element.</span><span class="sxs-lookup"><span data-stu-id="3653a-180">For more information, see the [\<federationConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) element.</span></span>  
  
 <span data-ttu-id="3653a-181">`<identityConfiguration>` Element je reprezentována <xref:System.IdentityModel.Configuration.IdentityConfigurationElement> třídy.</span><span class="sxs-lookup"><span data-stu-id="3653a-181">The `<identityConfiguration>` element is represented by the <xref:System.IdentityModel.Configuration.IdentityConfigurationElement> class.</span></span> <span data-ttu-id="3653a-182">Oddíl konfigurace identity je reprezentována <xref:System.IdentityModel.Configuration.IdentityConfiguration> třídy.</span><span class="sxs-lookup"><span data-stu-id="3653a-182">An identity configuration section is represented by the <xref:System.IdentityModel.Configuration.IdentityConfiguration> class.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3653a-183">Zadání následující prvky jako podřízených elementů `<identityConfiguration>` element se už nepoužívá, i když chování je stále podporováno pro zpětnou kompatibilitu.</span><span class="sxs-lookup"><span data-stu-id="3653a-183">Specifying the following elements as child elements of the `<identityConfiguration>` element has been deprecated, although the behavior is still supported for backward compatibility.</span></span> <span data-ttu-id="3653a-184">Tyto prvky měli, místo toho zadat v rámci [ \<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) element.</span><span class="sxs-lookup"><span data-stu-id="3653a-184">These elements should, instead, be specified under the [\<securityTokenHandlerConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) element.</span></span>  
>   
>  -   [<span data-ttu-id="3653a-185">\<audienceUris ></span><span class="sxs-lookup"><span data-stu-id="3653a-185">\<audienceUris></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/audienceuris.md)  
> -   [<span data-ttu-id="3653a-186">\<issuerNameRegistry ></span><span class="sxs-lookup"><span data-stu-id="3653a-186">\<issuerNameRegistry></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)  
> -   [<span data-ttu-id="3653a-187">\<issuerTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="3653a-187">\<issuerTokenResolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuertokenresolver.md)  
> -   [<span data-ttu-id="3653a-188">\<serviceTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="3653a-188">\<serviceTokenResolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicetokenresolver.md)  
  
## <a name="example"></a><span data-ttu-id="3653a-189">Příklad</span><span class="sxs-lookup"><span data-stu-id="3653a-189">Example</span></span>  
 <span data-ttu-id="3653a-190">Následující příklad vytvoří konfigurace aplikace identity s názvem "alternateConfiguration".</span><span class="sxs-lookup"><span data-stu-id="3653a-190">The following example creates an identity configuration named "alternateConfiguration".</span></span> <span data-ttu-id="3653a-191">Konfigurace identity Určuje výchozí nastavení.</span><span class="sxs-lookup"><span data-stu-id="3653a-191">The identity configuration specifies default settings.</span></span>  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="alternateConfiguration"/>  
</system.identityModel>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3653a-192">Viz také</span><span class="sxs-lookup"><span data-stu-id="3653a-192">See Also</span></span>  
 <xref:System.IdentityModel.Configuration.IdentityConfiguration>  
 <xref:System.IdentityModel.Configuration.IdentityConfigurationElement>
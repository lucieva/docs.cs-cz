---
title: '&lt;nameClaimType&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 17514d95-f0f5-4789-8e28-346640dc227c
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: e910333084aae9e47153cfe3ee4b5cd943a37f71
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="ltnameclaimtypegt"></a><span data-ttu-id="a21a8-102">&lt;nameClaimType&gt;</span><span class="sxs-lookup"><span data-stu-id="a21a8-102">&lt;nameClaimType&gt;</span></span>
<span data-ttu-id="a21a8-103">Nastaví typ deklarace identity, která určuje <xref:System.Security.Principal.IIdentity.Name%2A> vlastnost.</span><span class="sxs-lookup"><span data-stu-id="a21a8-103">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="a21a8-104">Typ deklarace identity se používá pro vyhledávání <xref:System.Security.Claims.Claim> v kolekci <xref:System.Security.Claims.ClaimsIdentity> objektů vrácený <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> metoda Tato obslužná rutina tokenu.</span><span class="sxs-lookup"><span data-stu-id="a21a8-104">The claim type is used to search for a <xref:System.Security.Claims.Claim> in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of this token handler.</span></span> <span data-ttu-id="a21a8-105">Hodnota odpovídající deklarace identity je pak nastavená na název <xref:System.Security.Principal.IIdentity> generované z této obslužné rutiny tokenu.</span><span class="sxs-lookup"><span data-stu-id="a21a8-105">The value of the matching claim is then set as the name of the <xref:System.Security.Principal.IIdentity> generated from this token handler.</span></span>  
  
 <span data-ttu-id="a21a8-106">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="a21a8-106">\<system.identityModel></span></span>  
<span data-ttu-id="a21a8-107">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="a21a8-107">\<identityConfiguration></span></span>  
<span data-ttu-id="a21a8-108">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="a21a8-108">\<securityTokenHandlers></span></span>  
<span data-ttu-id="a21a8-109">\<Přidat ></span><span class="sxs-lookup"><span data-stu-id="a21a8-109">\<add></span></span>  
<span data-ttu-id="a21a8-110">\<samlSecurityTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="a21a8-110">\<samlSecurityTokenRequirement></span></span>  
<span data-ttu-id="a21a8-111">\<nameClaimType ></span><span class="sxs-lookup"><span data-stu-id="a21a8-111">\<nameClaimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a21a8-112">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="a21a8-112">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add>  
        <samlSecurityTokenRequirement>  
          <nameClaimType value=xs:string>  
          </nameClaimType>  
        </samlSecurityTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a21a8-113">Atributy a elementy</span><span class="sxs-lookup"><span data-stu-id="a21a8-113">Attributes and Elements</span></span>  
 <span data-ttu-id="a21a8-114">Následující části popisují atributy, podřízené prvky a nadřazené prvky.</span><span class="sxs-lookup"><span data-stu-id="a21a8-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a21a8-115">Atributy</span><span class="sxs-lookup"><span data-stu-id="a21a8-115">Attributes</span></span>  
  
|<span data-ttu-id="a21a8-116">Atribut</span><span class="sxs-lookup"><span data-stu-id="a21a8-116">Attribute</span></span>|<span data-ttu-id="a21a8-117">Popis</span><span class="sxs-lookup"><span data-stu-id="a21a8-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a21a8-118">value</span><span class="sxs-lookup"><span data-stu-id="a21a8-118">value</span></span>|<span data-ttu-id="a21a8-119">Řetězec, který určuje identifikátor URI, který představuje typ deklarace identity pro deklarace identity <xref:System.Security.Principal.IIdentity.Name%2A> vlastnost.</span><span class="sxs-lookup"><span data-stu-id="a21a8-119">A string that specifies the URI that represents the claim type of the claim to use for the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="a21a8-120">Požadováno.</span><span class="sxs-lookup"><span data-stu-id="a21a8-120">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a21a8-121">Podřízené elementy</span><span class="sxs-lookup"><span data-stu-id="a21a8-121">Child Elements</span></span>  
 <span data-ttu-id="a21a8-122">Žádné</span><span class="sxs-lookup"><span data-stu-id="a21a8-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a21a8-123">Nadřazené elementy</span><span class="sxs-lookup"><span data-stu-id="a21a8-123">Parent Elements</span></span>  
  
|<span data-ttu-id="a21a8-124">Prvek</span><span class="sxs-lookup"><span data-stu-id="a21a8-124">Element</span></span>|<span data-ttu-id="a21a8-125">Popis</span><span class="sxs-lookup"><span data-stu-id="a21a8-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a21a8-126">\<samlSecurityTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="a21a8-126">\<samlSecurityTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|<span data-ttu-id="a21a8-127">Poskytuje konfigurace <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> třídy, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> , nebo odvozená třída buď z těchto tříd.</span><span class="sxs-lookup"><span data-stu-id="a21a8-127">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a21a8-128">Poznámky</span><span class="sxs-lookup"><span data-stu-id="a21a8-128">Remarks</span></span>  
 <span data-ttu-id="a21a8-129">`<nameClaimType>` Nastaví element <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> vlastnost při <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> objekt je inicializován z konfigurace.</span><span class="sxs-lookup"><span data-stu-id="a21a8-129">The `<nameClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a21a8-130">Příklad</span><span class="sxs-lookup"><span data-stu-id="a21a8-130">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a21a8-131">Viz také</span><span class="sxs-lookup"><span data-stu-id="a21a8-131">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A>
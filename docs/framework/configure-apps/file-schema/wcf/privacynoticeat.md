---
title: '&lt;privacyNoticeAt&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4cc96942-4eb9-4241-b2fd-45aa239915e8
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 63501539db4dc01d86eb675c28001dc960f1bf7f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/02/2017
---
# <a name="ltprivacynoticeatgt"></a><span data-ttu-id="6874d-102">&lt;privacyNoticeAt&gt;</span><span class="sxs-lookup"><span data-stu-id="6874d-102">&lt;privacyNoticeAt&gt;</span></span>
<span data-ttu-id="6874d-103">Reprezentuje element konfigurace, který určuje oznámení o ochraně osobních údajů použít v `wsFederationHttp` vazby.</span><span class="sxs-lookup"><span data-stu-id="6874d-103">Represents a configuration element that specifies a privacy notice used in `wsFederationHttp` binding.</span></span>  
  
 <span data-ttu-id="6874d-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="6874d-104">\<system.serviceModel></span></span>  
<span data-ttu-id="6874d-105">\<vazby ></span><span class="sxs-lookup"><span data-stu-id="6874d-105">\<bindings></span></span>  
<span data-ttu-id="6874d-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="6874d-106">\<customBinding></span></span>  
<span data-ttu-id="6874d-107">\<Vazba ></span><span class="sxs-lookup"><span data-stu-id="6874d-107">\<binding></span></span>  
<span data-ttu-id="6874d-108">\<privacyNotice ></span><span class="sxs-lookup"><span data-stu-id="6874d-108">\<privacyNotice></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6874d-109">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="6874d-109">Syntax</span></span>  
  
```xml  
<privacyNotice url="String"  
        version="Integer" />  
```  
  
## <a name="type"></a><span data-ttu-id="6874d-110">Typ</span><span class="sxs-lookup"><span data-stu-id="6874d-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6874d-111">Atributy a elementy</span><span class="sxs-lookup"><span data-stu-id="6874d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="6874d-112">Následující části popisují atributy, podřízené prvky a nadřazené prvky.</span><span class="sxs-lookup"><span data-stu-id="6874d-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6874d-113">Atributy</span><span class="sxs-lookup"><span data-stu-id="6874d-113">Attributes</span></span>  
  
|<span data-ttu-id="6874d-114">Atribut</span><span class="sxs-lookup"><span data-stu-id="6874d-114">Attribute</span></span>|<span data-ttu-id="6874d-115">Popis</span><span class="sxs-lookup"><span data-stu-id="6874d-115">Description</span></span>|  
|---------------|-----------------|  
|`url`|<span data-ttu-id="6874d-116">Řetězec, který určuje identifikátor URI, ve kterém se nachází v oznámení o ochraně osobních údajů.</span><span class="sxs-lookup"><span data-stu-id="6874d-116">A string that specifies the URI at which the privacy notice is located.</span></span>|  
|`version`|<span data-ttu-id="6874d-117">Celé číslo, které určuje verzi toto prohlášení o ochraně osobních údajů.</span><span class="sxs-lookup"><span data-stu-id="6874d-117">An integer that specifies the version of this privacy notice.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6874d-118">Podřízené elementy</span><span class="sxs-lookup"><span data-stu-id="6874d-118">Child Elements</span></span>  
 <span data-ttu-id="6874d-119">Žádné</span><span class="sxs-lookup"><span data-stu-id="6874d-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6874d-120">Nadřazené elementy</span><span class="sxs-lookup"><span data-stu-id="6874d-120">Parent Elements</span></span>  
  
|<span data-ttu-id="6874d-121">Prvek</span><span class="sxs-lookup"><span data-stu-id="6874d-121">Element</span></span>|<span data-ttu-id="6874d-122">Popis</span><span class="sxs-lookup"><span data-stu-id="6874d-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6874d-123">\<Vazba ></span><span class="sxs-lookup"><span data-stu-id="6874d-123">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="6874d-124">Definuje všechny možnosti vazba vlastní vazby.</span><span class="sxs-lookup"><span data-stu-id="6874d-124">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6874d-125">Viz také</span><span class="sxs-lookup"><span data-stu-id="6874d-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PrivacyNoticeElement>  
 <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="6874d-126">Vazby</span><span class="sxs-lookup"><span data-stu-id="6874d-126">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="6874d-127">Rozšiřování vazeb</span><span class="sxs-lookup"><span data-stu-id="6874d-127">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="6874d-128">Vlastní vazby</span><span class="sxs-lookup"><span data-stu-id="6874d-128">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="6874d-129">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="6874d-129">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
---
title: '&lt;Typ oneWay&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 00e67e0e-77c0-4695-9138-c0997b0e5f3c
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: be70abe745879b5d6f6e8cdde802a6403f90174b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/02/2017
---
# <a name="ltonewaygt"></a><span data-ttu-id="e2b9b-102">&lt;Typ oneWay&gt;</span><span class="sxs-lookup"><span data-stu-id="e2b9b-102">&lt;oneWay&gt;</span></span>
<span data-ttu-id="e2b9b-103">Umožňuje směrování paketů a použití jednosměrné metody pro vlastní vazby.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-103">Enables packet routing and the use of one-way methods for a custom binding.</span></span>  
  
 <span data-ttu-id="e2b9b-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="e2b9b-104">\<system.serviceModel></span></span>  
<span data-ttu-id="e2b9b-105">\<vazby ></span><span class="sxs-lookup"><span data-stu-id="e2b9b-105">\<bindings></span></span>  
<span data-ttu-id="e2b9b-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="e2b9b-106">\<customBinding></span></span>  
<span data-ttu-id="e2b9b-107">\<Vazba ></span><span class="sxs-lookup"><span data-stu-id="e2b9b-107">\<binding></span></span>  
<span data-ttu-id="e2b9b-108">\<Typ oneWay ></span><span class="sxs-lookup"><span data-stu-id="e2b9b-108">\<oneWay></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2b9b-109">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="e2b9b-109">Syntax</span></span>  
  
```xml  
<oneWay packetRoutable="Boolean">  
        <channelPoolSettings  
           idleTimeout"TimeSpan"  
          leaseTimeout"TimeSpan"  
          maxOutboundConnectionsPerEndpopint="Integer" />  
```  
  
```xml  
</oneWay>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e2b9b-110">Atributy a elementy</span><span class="sxs-lookup"><span data-stu-id="e2b9b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e2b9b-111">Následující části popisují atributy, podřízené prvky a nadřazené prvky.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e2b9b-112">Atributy</span><span class="sxs-lookup"><span data-stu-id="e2b9b-112">Attributes</span></span>  
  
|<span data-ttu-id="e2b9b-113">Atribut</span><span class="sxs-lookup"><span data-stu-id="e2b9b-113">Attribute</span></span>|<span data-ttu-id="e2b9b-114">Popis</span><span class="sxs-lookup"><span data-stu-id="e2b9b-114">Description</span></span>|  
|---------------|-----------------|  
|`packetRoutable`|<span data-ttu-id="e2b9b-115">Logická hodnota, která určuje, zda je povoleno směrování paketů.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-115">A Boolean value that specifies whether packet routing is enabled.</span></span> <span data-ttu-id="e2b9b-116">Výchozí hodnota je `false`.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-116">The default is `false`.</span></span>|  
|`MaxAcceptedChannels`|<span data-ttu-id="e2b9b-117">Celé číslo, které určuje maximální počet kanálů, které jsou přípustné.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-117">An integer that specifies the maximum number of channels that can be accepted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e2b9b-118">Podřízené elementy</span><span class="sxs-lookup"><span data-stu-id="e2b9b-118">Child Elements</span></span>  
  
|<span data-ttu-id="e2b9b-119">Prvek</span><span class="sxs-lookup"><span data-stu-id="e2b9b-119">Element</span></span>|<span data-ttu-id="e2b9b-120">Popis</span><span class="sxs-lookup"><span data-stu-id="e2b9b-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e2b9b-121">\<channelPoolSettings ></span><span class="sxs-lookup"><span data-stu-id="e2b9b-121">\<channelPoolSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/channelpoolsettings.md)|<span data-ttu-id="e2b9b-122">A <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> objekt, který obsahuje vlastnosti fondu kanál pro aktuální kanál.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-122">A <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> object that contains properties of the channel pool for the current channel.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e2b9b-123">Nadřazené elementy</span><span class="sxs-lookup"><span data-stu-id="e2b9b-123">Parent Elements</span></span>  
  
|<span data-ttu-id="e2b9b-124">Prvek</span><span class="sxs-lookup"><span data-stu-id="e2b9b-124">Element</span></span>|<span data-ttu-id="e2b9b-125">Popis</span><span class="sxs-lookup"><span data-stu-id="e2b9b-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e2b9b-126">\<Vazba ></span><span class="sxs-lookup"><span data-stu-id="e2b9b-126">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="e2b9b-127">Definuje všechny možnosti vazba vlastní vazby.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e2b9b-128">Poznámky</span><span class="sxs-lookup"><span data-stu-id="e2b9b-128">Remarks</span></span>  
 <span data-ttu-id="e2b9b-129">Povolit směrování paketů, jednosměrné převod vrstvy je nutné, který poskytuje tento element.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-129">To enable packet routing, a one-way conversion layer is required, which this element provides.</span></span> <span data-ttu-id="e2b9b-130">Uživatel může vytvořit vlastní vazby, který vrstvách tuto vazbu pomocí deklaracemi relace nebo požadavku a odpovědi přenosového Chcete-li paket směrovatelné.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-130">A user can create a custom binding that layers this binding over a session-aware or request-reply transport to make it packet routable.</span></span> <span data-ttu-id="e2b9b-131">Tento element je také užitečné, když chcete vystavit jednosměrné metody více nativní způsobem.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-131">This element is also useful when you want to expose one-way methods in a more native fashion.</span></span> <span data-ttu-id="e2b9b-132">Další transformace je možné použít v této vrstvě, jako je například složené duplexní a spolehlivého zasílání zpráv.</span><span class="sxs-lookup"><span data-stu-id="e2b9b-132">More transformations can be applied over this layer, such as Composite Duplex and Reliable Messaging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2b9b-133">Viz také</span><span class="sxs-lookup"><span data-stu-id="e2b9b-133">See Also</span></span>  
 <xref:System.ServiceModel.Channels.OneWayBindingElement>  
 <xref:System.ServiceModel.Configuration.OneWayElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="e2b9b-134">Vazby</span><span class="sxs-lookup"><span data-stu-id="e2b9b-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="e2b9b-135">Rozšiřování vazeb</span><span class="sxs-lookup"><span data-stu-id="e2b9b-135">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="e2b9b-136">Vlastní vazby</span><span class="sxs-lookup"><span data-stu-id="e2b9b-136">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="e2b9b-137">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="e2b9b-137">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
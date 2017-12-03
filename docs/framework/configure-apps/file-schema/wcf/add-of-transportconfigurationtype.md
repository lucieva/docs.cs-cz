---
title: "&lt;add&gt; – &lt;transportConfigurationType&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03d79db9-571d-4534-acef-d05e5467b257
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0b27994cae77ec012e0b432e702c9c2ccb1933b8
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/02/2017
---
# <a name="ltaddgt-of-lttransportconfigurationtypegt"></a><span data-ttu-id="028e6-102">&lt;add&gt; – &lt;transportConfigurationType&gt;</span><span class="sxs-lookup"><span data-stu-id="028e6-102">&lt;add&gt; of &lt;transportConfigurationType&gt;</span></span>
<span data-ttu-id="028e6-103">Tento element je dvojice klíč/hodnota, které jsou uvedeny typy konkrétního přenosu.</span><span class="sxs-lookup"><span data-stu-id="028e6-103">This element is a key/value pair, which identifies the type of a particular transport.</span></span>  
  
 <span data-ttu-id="028e6-104">\<systém. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="028e6-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="028e6-105">\<ServiceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="028e6-105">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="028e6-106">\<transportConfigurationTypes ></span><span class="sxs-lookup"><span data-stu-id="028e6-106">\<transportConfigurationTypes></span></span>  
<span data-ttu-id="028e6-107">\<Přidat ></span><span class="sxs-lookup"><span data-stu-id="028e6-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="028e6-108">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="028e6-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>   
   <transportConfigurationTypes>  
      <add name="String"  
               transportConfigurationType="String"/>   
   </transportConfigurationTypes>  
</serviceHostingEnvironment>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="028e6-109">Atributy a elementy</span><span class="sxs-lookup"><span data-stu-id="028e6-109">Attributes and Elements</span></span>  
 <span data-ttu-id="028e6-110">Následující části popisují atributy, podřízené prvky a nadřazené prvky.</span><span class="sxs-lookup"><span data-stu-id="028e6-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="028e6-111">Atributy</span><span class="sxs-lookup"><span data-stu-id="028e6-111">Attributes</span></span>  
  
|<span data-ttu-id="028e6-112">Atribut</span><span class="sxs-lookup"><span data-stu-id="028e6-112">Attribute</span></span>|<span data-ttu-id="028e6-113">Popis</span><span class="sxs-lookup"><span data-stu-id="028e6-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="028e6-114">name</span><span class="sxs-lookup"><span data-stu-id="028e6-114">name</span></span>|<span data-ttu-id="028e6-115">Požadovaný atribut řetězec.</span><span class="sxs-lookup"><span data-stu-id="028e6-115">Required String attribute.</span></span><br /><br /> <span data-ttu-id="028e6-116">Obsahuje klíč definovaný uživatelem, který jedinečně identifikuje typ přenosu.</span><span class="sxs-lookup"><span data-stu-id="028e6-116">Contains a user-defined key that uniquely identifies the transport type.</span></span>|  
|<span data-ttu-id="028e6-117">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="028e6-117">transportConfigurationType</span></span>|<span data-ttu-id="028e6-118">Řetězec, který obsahuje typ, který implementuje konkrétní přenosu.</span><span class="sxs-lookup"><span data-stu-id="028e6-118">A string that contains the type that implements the specific transport.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="028e6-119">Podřízené elementy</span><span class="sxs-lookup"><span data-stu-id="028e6-119">Child Elements</span></span>  
 <span data-ttu-id="028e6-120">Žádné</span><span class="sxs-lookup"><span data-stu-id="028e6-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="028e6-121">Nadřazené elementy</span><span class="sxs-lookup"><span data-stu-id="028e6-121">Parent Elements</span></span>  
  
|<span data-ttu-id="028e6-122">Prvek</span><span class="sxs-lookup"><span data-stu-id="028e6-122">Element</span></span>|<span data-ttu-id="028e6-123">Popis</span><span class="sxs-lookup"><span data-stu-id="028e6-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="028e6-124">\<transportConfigurationTypes ></span><span class="sxs-lookup"><span data-stu-id="028e6-124">\<transportConfigurationTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transportconfigurationtypes.md)|<span data-ttu-id="028e6-125">Kolekce typů, které implementují konkrétní přenosu.</span><span class="sxs-lookup"><span data-stu-id="028e6-125">A collection of types that implement the specific transport.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="028e6-126">Příklad</span><span class="sxs-lookup"><span data-stu-id="028e6-126">Example</span></span>  
  
```xml  
<serviceHostingEnvironment>   
   <transportConfigurationTypes>  
      <add name="net.udp"  
      transportConfigurationType="Microsoft.ServiceModel.Samples.Hosting.HostedUdpTransportConfiguration, UdpActivation, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6fa904d2da1848d6" />   
   </transportConfigurationTypes>  
</serviceHostingEnvironment>  
```  
  
## <a name="see-also"></a><span data-ttu-id="028e6-127">Viz také</span><span class="sxs-lookup"><span data-stu-id="028e6-127">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElement>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>  
 [<span data-ttu-id="028e6-128">Hostování</span><span class="sxs-lookup"><span data-stu-id="028e6-128">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
---
title: '&lt;serviceTimeouts&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ada536cf-97dc-4cd7-89ec-ed1466c1c557
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f6d2940a4c4615a922efcc74802a82adbe10267c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/02/2017
---
# <a name="ltservicetimeoutsgt"></a><span data-ttu-id="6e889-102">&lt;serviceTimeouts&gt;</span><span class="sxs-lookup"><span data-stu-id="6e889-102">&lt;serviceTimeouts&gt;</span></span>
<span data-ttu-id="6e889-103">Určuje časový limit pro službu.</span><span class="sxs-lookup"><span data-stu-id="6e889-103">Specifies the timeout for a service.</span></span>  
  
 <span data-ttu-id="6e889-104">\<systém. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="6e889-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="6e889-105">\<chování ></span><span class="sxs-lookup"><span data-stu-id="6e889-105">\<behaviors></span></span>  
<span data-ttu-id="6e889-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="6e889-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="6e889-107">\<chování ></span><span class="sxs-lookup"><span data-stu-id="6e889-107">\<behavior></span></span>  
<span data-ttu-id="6e889-108">\<serviceTimeouts ></span><span class="sxs-lookup"><span data-stu-id="6e889-108">\<serviceTimeouts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e889-109">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="6e889-109">Syntax</span></span>  
  
```xml  
<serviceTimeouts transactionTimeout="TimeSpan" />  
```  
  
## <a name="type"></a><span data-ttu-id="6e889-110">Typ</span><span class="sxs-lookup"><span data-stu-id="6e889-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6e889-111">Atributy a elementy</span><span class="sxs-lookup"><span data-stu-id="6e889-111">Attributes and Elements</span></span>  
 <span data-ttu-id="6e889-112">Následující části popisují atributy, podřízené prvky a nadřazené prvky.</span><span class="sxs-lookup"><span data-stu-id="6e889-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6e889-113">Atributy</span><span class="sxs-lookup"><span data-stu-id="6e889-113">Attributes</span></span>  
  
|<span data-ttu-id="6e889-114">Atribut</span><span class="sxs-lookup"><span data-stu-id="6e889-114">Attribute</span></span>|<span data-ttu-id="6e889-115">Popis</span><span class="sxs-lookup"><span data-stu-id="6e889-115">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="6e889-116">A <xref:System.TimeSpan> hodnotu, která určuje transakce musí procházet od klienta k serveru časový interval.</span><span class="sxs-lookup"><span data-stu-id="6e889-116">A <xref:System.TimeSpan> value that specifies the interval of time a transaction must flow from client to server.</span></span> <span data-ttu-id="6e889-117">Výchozí hodnota je "00: 00:00".</span><span class="sxs-lookup"><span data-stu-id="6e889-117">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6e889-118">Podřízené elementy</span><span class="sxs-lookup"><span data-stu-id="6e889-118">Child Elements</span></span>  
 <span data-ttu-id="6e889-119">Žádné</span><span class="sxs-lookup"><span data-stu-id="6e889-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6e889-120">Nadřazené elementy</span><span class="sxs-lookup"><span data-stu-id="6e889-120">Parent Elements</span></span>  
  
|<span data-ttu-id="6e889-121">Prvek</span><span class="sxs-lookup"><span data-stu-id="6e889-121">Element</span></span>|<span data-ttu-id="6e889-122">Popis</span><span class="sxs-lookup"><span data-stu-id="6e889-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6e889-123">\<chování ></span><span class="sxs-lookup"><span data-stu-id="6e889-123">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="6e889-124">Určuje chování element.</span><span class="sxs-lookup"><span data-stu-id="6e889-124">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6e889-125">Viz také</span><span class="sxs-lookup"><span data-stu-id="6e889-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
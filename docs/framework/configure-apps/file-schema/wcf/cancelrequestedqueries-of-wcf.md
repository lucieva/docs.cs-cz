---
title: "&lt;cancelRequestedQueries&gt; služby WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a7cc7125-9ea3-4d3f-99c0-878cdeb1258a
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: be3c02bdf0d51006d7df3b382541b704f71f2463
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/02/2017
---
# <a name="ltcancelrequestedqueriesgt-of-wcf"></a><span data-ttu-id="3b481-102">&lt;cancelRequestedQueries&gt; služby WCF</span><span class="sxs-lookup"><span data-stu-id="3b481-102">&lt;cancelRequestedQueries&gt; of WCF</span></span>
<span data-ttu-id="3b481-103">Představuje kolekci dotazů, které se používají ke sledování požadavků pro zrušení podřízené aktivity Nadřazená aktivita.</span><span class="sxs-lookup"><span data-stu-id="3b481-103">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="3b481-104">Dotaz, je nezbytné pro sledování účastníka přihlásit k odběru zrušit požadavek záznam objekty.</span><span class="sxs-lookup"><span data-stu-id="3b481-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="3b481-105">Další informace o sledování profil dotazů najdete v tématu [sledování profily](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="3b481-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="3b481-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="3b481-106">\<system.serviceModel></span></span>  
<span data-ttu-id="3b481-107">\<sledování ></span><span class="sxs-lookup"><span data-stu-id="3b481-107">\<tracking></span></span>  
<span data-ttu-id="3b481-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="3b481-108">\<trackingProfile></span></span>  
<span data-ttu-id="3b481-109">\<pracovní postup ></span><span class="sxs-lookup"><span data-stu-id="3b481-109">\<workflow></span></span>  
<span data-ttu-id="3b481-110">\<cancelRequestedQueries ></span><span class="sxs-lookup"><span data-stu-id="3b481-110">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b481-111">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="3b481-111">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <cancelRequestQueries>             <cancelRequestQuery activityName="String"                 childActivityName="String"/>          </cancelRequestQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3b481-112">Atributy a elementy</span><span class="sxs-lookup"><span data-stu-id="3b481-112">Attributes and Elements</span></span>  
 <span data-ttu-id="3b481-113">Následující části popisují atributy, podřízené prvky a nadřazené prvky.</span><span class="sxs-lookup"><span data-stu-id="3b481-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3b481-114">Atributy</span><span class="sxs-lookup"><span data-stu-id="3b481-114">Attributes</span></span>  
 <span data-ttu-id="3b481-115">Žádné</span><span class="sxs-lookup"><span data-stu-id="3b481-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3b481-116">Podřízené elementy</span><span class="sxs-lookup"><span data-stu-id="3b481-116">Child Elements</span></span>  
  
|<span data-ttu-id="3b481-117">Prvek</span><span class="sxs-lookup"><span data-stu-id="3b481-117">Element</span></span>|<span data-ttu-id="3b481-118">Popis</span><span class="sxs-lookup"><span data-stu-id="3b481-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3b481-119">\<cancelRequestedQuery ></span><span class="sxs-lookup"><span data-stu-id="3b481-119">\<cancelRequestedQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/cancelrequestedquery.md)|<span data-ttu-id="3b481-120">Dotaz, který se používá ke sledování požadavků pro zrušení podřízené aktivity Nadřazená aktivita.</span><span class="sxs-lookup"><span data-stu-id="3b481-120">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3b481-121">Nadřazené elementy</span><span class="sxs-lookup"><span data-stu-id="3b481-121">Parent Elements</span></span>  
  
|<span data-ttu-id="3b481-122">Prvek</span><span class="sxs-lookup"><span data-stu-id="3b481-122">Element</span></span>|<span data-ttu-id="3b481-123">Popis</span><span class="sxs-lookup"><span data-stu-id="3b481-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3b481-124">\<pracovní postup ></span><span class="sxs-lookup"><span data-stu-id="3b481-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="3b481-125">Konfigurace element, který obsahuje všechny dotazy týkající se konkrétního pracovního postupu identifikovaný `a HYPERLINK "http://msdn.microsoft.com/en-us/library/system.servicemodel.activities.tracking.configuration.profileworkflowelement.activitydefinitionid(VS.100).aspx" ctivityDefinitionId` vlastnost.</span><span class="sxs-lookup"><span data-stu-id="3b481-125">A configuration element that contains all queries for a specific workflow identified by the `a HYPERLINK "http://msdn.microsoft.com/en-us/library/system.servicemodel.activities.tracking.configuration.profileworkflowelement.activitydefinitionid(VS.100).aspx" ctivityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3b481-126">Viz také</span><span class="sxs-lookup"><span data-stu-id="3b481-126">See Also</span></span>  
 <xref:System.Activities.Tracking.CancelRequestedQuery>  
 [<span data-ttu-id="3b481-127">Pracovní postup sledování a trasování</span><span class="sxs-lookup"><span data-stu-id="3b481-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="3b481-128">Sledování profily</span><span class="sxs-lookup"><span data-stu-id="3b481-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
---
title: '&lt;activityScheduledQueries&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: ca6e82f1-54f2-48d6-899c-9873065b5547
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d860474c4a638a347f85c07862c330f58cc30c09
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/02/2017
---
# <a name="ltactivityscheduledqueriesgt"></a><span data-ttu-id="6285d-102">&lt;activityScheduledQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="6285d-102">&lt;activityScheduledQueries&gt;</span></span>
<span data-ttu-id="6285d-103">Představuje kolekci dotazů, které se používají ke sledování aktivitu naplánovat provedení podle aktivity jako nadřazený.</span><span class="sxs-lookup"><span data-stu-id="6285d-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="6285d-104">Dotaz, je nezbytné pro sledování účastníka přihlásit k odběru záznamů aktivit naplánována.</span><span class="sxs-lookup"><span data-stu-id="6285d-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="6285d-105">Další informace o sledování profil dotazů najdete v tématu [sledování profily](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="6285d-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="6285d-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="6285d-106">\<system.serviceModel></span></span>  
<span data-ttu-id="6285d-107">\<sledování ></span><span class="sxs-lookup"><span data-stu-id="6285d-107">\<tracking></span></span>  
<span data-ttu-id="6285d-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="6285d-108">\<trackingProfile></span></span>  
<span data-ttu-id="6285d-109">\<pracovní postup ></span><span class="sxs-lookup"><span data-stu-id="6285d-109">\<workflow></span></span>  
<span data-ttu-id="6285d-110">\<activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="6285d-110">\<activityScheduledQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6285d-111">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="6285d-111">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityScheduledQueries>
        <activityScheduledQuery activityName="String" 
                                childActivityName="String" />
      </activityScheduledQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6285d-112">Atributy a elementy</span><span class="sxs-lookup"><span data-stu-id="6285d-112">Attributes and Elements</span></span>  
 <span data-ttu-id="6285d-113">Následující části popisují atributy, podřízené prvky a nadřazené prvky.</span><span class="sxs-lookup"><span data-stu-id="6285d-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6285d-114">Atributy</span><span class="sxs-lookup"><span data-stu-id="6285d-114">Attributes</span></span>  
 <span data-ttu-id="6285d-115">Žádné</span><span class="sxs-lookup"><span data-stu-id="6285d-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6285d-116">Podřízené elementy</span><span class="sxs-lookup"><span data-stu-id="6285d-116">Child Elements</span></span>  
  
|<span data-ttu-id="6285d-117">Prvek</span><span class="sxs-lookup"><span data-stu-id="6285d-117">Element</span></span>|<span data-ttu-id="6285d-118">Popis</span><span class="sxs-lookup"><span data-stu-id="6285d-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6285d-119">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="6285d-119">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="6285d-120">Dotaz, který se používá ke sledování aktivitu naplánovat provedení podle aktivity jako nadřazený.</span><span class="sxs-lookup"><span data-stu-id="6285d-120">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6285d-121">Nadřazené elementy</span><span class="sxs-lookup"><span data-stu-id="6285d-121">Parent Elements</span></span>  
  
|<span data-ttu-id="6285d-122">Prvek</span><span class="sxs-lookup"><span data-stu-id="6285d-122">Element</span></span>|<span data-ttu-id="6285d-123">Popis</span><span class="sxs-lookup"><span data-stu-id="6285d-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6285d-124">\<pracovní postup ></span><span class="sxs-lookup"><span data-stu-id="6285d-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="6285d-125">Konfigurace elementu, který obsahuje všechny dotazy pro konkrétní pracovní tok identifikovaný **activityDefinitionId** vlastnost.</span><span class="sxs-lookup"><span data-stu-id="6285d-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6285d-126">Viz také</span><span class="sxs-lookup"><span data-stu-id="6285d-126">See Also</span></span>  
 <span data-ttu-id="6285d-127"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="6285d-127"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="6285d-128"><xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="6285d-128"><xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="6285d-129">Pracovní postup sledování a trasování</span><span class="sxs-lookup"><span data-stu-id="6285d-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="6285d-130">Sledování profily</span><span class="sxs-lookup"><span data-stu-id="6285d-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
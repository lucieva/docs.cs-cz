---
title: '&lt;argument&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: a7144d53-8023-4e90-971f-895e016fd58a
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b3625d3bf6aa415c34b9c05bebdec390bcb51f69
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/02/2017
---
# <a name="ltargumentgt"></a><span data-ttu-id="823a8-102">&lt;argument&gt;</span><span class="sxs-lookup"><span data-stu-id="823a8-102">&lt;argument&gt;</span></span>
<span data-ttu-id="823a8-103">Konfigurace element, který představuje argument přidruženého k dotazu stavu aktivity.</span><span class="sxs-lookup"><span data-stu-id="823a8-103">A configuration element that represents an argument associated with an activity state query.</span></span>  
  
 <span data-ttu-id="823a8-104">Další informace o sledování profil dotazů najdete v tématu [sledování profily](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="823a8-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="823a8-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="823a8-105">\<system.serviceModel></span></span>  
<span data-ttu-id="823a8-106">\<sledování ></span><span class="sxs-lookup"><span data-stu-id="823a8-106">\<tracking></span></span>  
<span data-ttu-id="823a8-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="823a8-107">\<trackingProfile></span></span>  
<span data-ttu-id="823a8-108">\<pracovní postup ></span><span class="sxs-lookup"><span data-stu-id="823a8-108">\<workflow></span></span>  
<span data-ttu-id="823a8-109">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="823a8-109">\<activityStateQueries></span></span>  
<span data-ttu-id="823a8-110">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="823a8-110">\<activityStateQuery></span></span>  
<span data-ttu-id="823a8-111">\<argumenty ></span><span class="sxs-lookup"><span data-stu-id="823a8-111">\<arguments></span></span>  
<span data-ttu-id="823a8-112">\<argument ></span><span class="sxs-lookup"><span data-stu-id="823a8-112">\<argument></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="823a8-113">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="823a8-113">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String"/>
        </arguments>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="823a8-114">Atributy a elementy</span><span class="sxs-lookup"><span data-stu-id="823a8-114">Attributes and Elements</span></span>  
 <span data-ttu-id="823a8-115">Následující části popisují atributy, podřízené prvky a nadřazené prvky.</span><span class="sxs-lookup"><span data-stu-id="823a8-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="823a8-116">Atributy</span><span class="sxs-lookup"><span data-stu-id="823a8-116">Attributes</span></span>  
  
|<span data-ttu-id="823a8-117">Atribut</span><span class="sxs-lookup"><span data-stu-id="823a8-117">Attribute</span></span>|<span data-ttu-id="823a8-118">Popis</span><span class="sxs-lookup"><span data-stu-id="823a8-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="823a8-119">name</span><span class="sxs-lookup"><span data-stu-id="823a8-119">name</span></span>|<span data-ttu-id="823a8-120">Řetězec, který určuje název argumentu.</span><span class="sxs-lookup"><span data-stu-id="823a8-120">A string that specifies the name of the argument.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="823a8-121">Podřízené elementy</span><span class="sxs-lookup"><span data-stu-id="823a8-121">Child Elements</span></span>  
 <span data-ttu-id="823a8-122">Žádné</span><span class="sxs-lookup"><span data-stu-id="823a8-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="823a8-123">Nadřazené elementy</span><span class="sxs-lookup"><span data-stu-id="823a8-123">Parent Elements</span></span>  
  
|<span data-ttu-id="823a8-124">Prvek</span><span class="sxs-lookup"><span data-stu-id="823a8-124">Element</span></span>|<span data-ttu-id="823a8-125">Popis</span><span class="sxs-lookup"><span data-stu-id="823a8-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="823a8-126">\<argumenty ></span><span class="sxs-lookup"><span data-stu-id="823a8-126">\<arguments></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)|<span data-ttu-id="823a8-127">Kolekce argumenty přidružené k tomuto dotazu aktivity.</span><span class="sxs-lookup"><span data-stu-id="823a8-127">A collection of arguments associated with this activity query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="823a8-128">Poznámky</span><span class="sxs-lookup"><span data-stu-id="823a8-128">Remarks</span></span>  
 <span data-ttu-id="823a8-129">Jeden jedinečné funkce ActivityStateQuery je schopnost extrahování dat při sledování provádění pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="823a8-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="823a8-130">Tímto způsobem další kontext při přístupu k sledování záznamů příspěvek provádění.</span><span class="sxs-lookup"><span data-stu-id="823a8-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="823a8-131">Můžete použít [ \<argumenty >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<stavy >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) a [ \<stavy >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elementy extrahujte všechny proměnné nebo argumentu z všechny aktivity v pracovním postupu. Následující příklad ukazuje dotaz stavu aktivity, který extrahuje proměnné a argumenty při aktivity `Closed` sledování záznamu je vygenerované.</span><span class="sxs-lookup"><span data-stu-id="823a8-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="823a8-132">Proměnné a argumenty lze extrahovat jenom s ActivityStateRecord a proto předplacené v rámci sledování profilu pomocí [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="823a8-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <variables>  
    <variable name="FromAddress"/>  
  </variables>  
  <arguments>  
    <argument name="Result"/>  
  </arguments>  
</activityStateQuery>  
```  
  
## <a name="see-also"></a><span data-ttu-id="823a8-133">Viz také</span><span class="sxs-lookup"><span data-stu-id="823a8-133">See Also</span></span>  
 <span data-ttu-id="823a8-134"><xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="823a8-134"><xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="823a8-135"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="823a8-135"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="823a8-136">Pracovní postup sledování a trasování</span><span class="sxs-lookup"><span data-stu-id="823a8-136">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="823a8-137">Sledování profily</span><span class="sxs-lookup"><span data-stu-id="823a8-137">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
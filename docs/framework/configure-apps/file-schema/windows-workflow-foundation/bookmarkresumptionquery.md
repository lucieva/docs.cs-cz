---
title: '&lt;bookmarkResumptionQuery&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 226de75d-d25c-48d5-b069-4b7d80a6852b
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bafb044d052692385e0be0f4dbb1271eca847b1a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/02/2017
---
# <a name="ltbookmarkresumptionquerygt"></a><span data-ttu-id="18d24-102">&lt;bookmarkResumptionQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="18d24-102">&lt;bookmarkResumptionQuery&gt;</span></span>
<span data-ttu-id="18d24-103">Představuje dotaz, který se používá ke sledování obnovení záložku v instanci pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="18d24-103">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="18d24-104">Dotaz, je nezbytné pro sledování účastníka přihlásit k odběru záložku obnovení záznamů.</span><span class="sxs-lookup"><span data-stu-id="18d24-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="18d24-105">Další informace o sledování profil dotazů najdete v tématu [sledování profily](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="18d24-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="18d24-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="18d24-106">\<system.serviceModel></span></span>  
<span data-ttu-id="18d24-107">\<sledování ></span><span class="sxs-lookup"><span data-stu-id="18d24-107">\<tracking></span></span>  
<span data-ttu-id="18d24-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="18d24-108">\<trackingProfile></span></span>  
<span data-ttu-id="18d24-109">\<pracovní postup ></span><span class="sxs-lookup"><span data-stu-id="18d24-109">\<workflow></span></span>  
<span data-ttu-id="18d24-110">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="18d24-110">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="18d24-111">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="18d24-111">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18d24-112">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="18d24-112">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <bookmarkResumptionQueries>
        <bookmarkResumptionQuery name="String" />
      </bookmarkResumptionQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="18d24-113">Atributy a elementy</span><span class="sxs-lookup"><span data-stu-id="18d24-113">Attributes and Elements</span></span>  
 <span data-ttu-id="18d24-114">Následující části popisují atributy, podřízené prvky a nadřazené prvky.</span><span class="sxs-lookup"><span data-stu-id="18d24-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="18d24-115">Atributy</span><span class="sxs-lookup"><span data-stu-id="18d24-115">Attributes</span></span>  
  
|<span data-ttu-id="18d24-116">Atribut</span><span class="sxs-lookup"><span data-stu-id="18d24-116">Attribute</span></span>|<span data-ttu-id="18d24-117">Popis</span><span class="sxs-lookup"><span data-stu-id="18d24-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="18d24-118">name</span><span class="sxs-lookup"><span data-stu-id="18d24-118">name</span></span>|<span data-ttu-id="18d24-119">Řetězec, který určuje název záložky záznam, který chcete-li se přihlásit k odběru.</span><span class="sxs-lookup"><span data-stu-id="18d24-119">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="18d24-120">Podřízené elementy</span><span class="sxs-lookup"><span data-stu-id="18d24-120">Child Elements</span></span>  
 <span data-ttu-id="18d24-121">Žádné</span><span class="sxs-lookup"><span data-stu-id="18d24-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="18d24-122">Nadřazené elementy</span><span class="sxs-lookup"><span data-stu-id="18d24-122">Parent Elements</span></span>  
  
|<span data-ttu-id="18d24-123">Prvek</span><span class="sxs-lookup"><span data-stu-id="18d24-123">Element</span></span>|<span data-ttu-id="18d24-124">Popis</span><span class="sxs-lookup"><span data-stu-id="18d24-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="18d24-125">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="18d24-125">\<bookmarkResumptionQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionqueries.md)|<span data-ttu-id="18d24-126">Představuje kolekci dotazů, které se používají ke sledování obnovení záložku v instanci pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="18d24-126">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="18d24-127">Viz také</span><span class="sxs-lookup"><span data-stu-id="18d24-127">See Also</span></span>  
 <span data-ttu-id="18d24-128"><xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="18d24-128"><xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="18d24-129"><xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="18d24-129"><xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="18d24-130">Pracovní postup sledování a trasování</span><span class="sxs-lookup"><span data-stu-id="18d24-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="18d24-131">Sledování profily</span><span class="sxs-lookup"><span data-stu-id="18d24-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
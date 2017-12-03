---
title: 104 - ActivityScheduledRecord
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ae202178-8fb1-4646-a3aa-18beeda8ff93
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 49c7a295c4025da2c7fdcb7d4a220e26a4971f1b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="104---activityscheduledrecord"></a><span data-ttu-id="3f511-102">104 - ActivityScheduledRecord</span><span class="sxs-lookup"><span data-stu-id="3f511-102">104 - ActivityScheduledRecord</span></span>
## <a name="properties"></a><span data-ttu-id="3f511-103">Vlastnosti</span><span class="sxs-lookup"><span data-stu-id="3f511-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3f511-104">ID</span><span class="sxs-lookup"><span data-stu-id="3f511-104">Id</span></span>|<span data-ttu-id="3f511-105">104</span><span class="sxs-lookup"><span data-stu-id="3f511-105">104</span></span>|  
|<span data-ttu-id="3f511-106">Klíčová slova</span><span class="sxs-lookup"><span data-stu-id="3f511-106">Keywords</span></span>|<span data-ttu-id="3f511-107">EndToEndMonitoring, řešení potíží, HealthMonitoring, WFTracking</span><span class="sxs-lookup"><span data-stu-id="3f511-107">EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking</span></span>|  
|<span data-ttu-id="3f511-108">úroveň</span><span class="sxs-lookup"><span data-stu-id="3f511-108">Level</span></span>|<span data-ttu-id="3f511-109">Informace o</span><span class="sxs-lookup"><span data-stu-id="3f511-109">Information</span></span>|  
|<span data-ttu-id="3f511-110">Kanál</span><span class="sxs-lookup"><span data-stu-id="3f511-110">Channel</span></span>|<span data-ttu-id="3f511-111">Aplikaci Microsoft Windows Server – aplikace nebo analytické</span><span class="sxs-lookup"><span data-stu-id="3f511-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3f511-112">Popis</span><span class="sxs-lookup"><span data-stu-id="3f511-112">Description</span></span>  
 <span data-ttu-id="3f511-113">Tato událost je vygenerované účastníkem sledování, trasování událostí pro Windows, když aktivita v rámci instance pracovního postupu vysílá ActivityScheduledRecord</span><span class="sxs-lookup"><span data-stu-id="3f511-113">This event is emitted by the ETW tracking participant when an activity within a workflow instance emits ActivityScheduledRecord</span></span>  
  
## <a name="message"></a><span data-ttu-id="3f511-114">Zpráva</span><span class="sxs-lookup"><span data-stu-id="3f511-114">Message</span></span>  
 <span data-ttu-id="3f511-115">TrackRecord = ActivityScheduledRecord, ID instance = %1, RecordNumber = %2, EventTime = %3, název = %4, ID = %5, ActivityInstanceId = %6, ActivityTypeName = %7, ChildActivityName = %8, ChildActivityId = %9, ChildActivityInstanceId = % 10, ChildActivityTypeName = % 11, poznámky = ProfileName 12, % = % 13</span><span class="sxs-lookup"><span data-stu-id="3f511-115">TrackRecord = ActivityScheduledRecord, InstanceID = %1,  RecordNumber = %2, EventTime = %3, Name = %4, ActivityId = %5, ActivityInstanceId = %6, ActivityTypeName = %7, ChildActivityName = %8, ChildActivityId = %9, ChildActivityInstanceId = %10, ChildActivityTypeName =%11, Annotations=%12, ProfileName = %13</span></span>  
  
## <a name="details"></a><span data-ttu-id="3f511-116">Podrobnosti</span><span class="sxs-lookup"><span data-stu-id="3f511-116">Details</span></span>  
  
|<span data-ttu-id="3f511-117">Název položky dat</span><span class="sxs-lookup"><span data-stu-id="3f511-117">Data Item Name</span></span>|<span data-ttu-id="3f511-118">Datová položka – Typ</span><span class="sxs-lookup"><span data-stu-id="3f511-118">Data Item Type</span></span>|<span data-ttu-id="3f511-119">Popis</span><span class="sxs-lookup"><span data-stu-id="3f511-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3f511-120">identifikátor instanceId</span><span class="sxs-lookup"><span data-stu-id="3f511-120">InstanceId</span></span>|<span data-ttu-id="3f511-121">xs:GUID</span><span class="sxs-lookup"><span data-stu-id="3f511-121">xs:GUID</span></span>|<span data-ttu-id="3f511-122">Id instance pracovního postupu</span><span class="sxs-lookup"><span data-stu-id="3f511-122">The instance id for the workflow</span></span>|  
|<span data-ttu-id="3f511-123">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="3f511-123">RecordNumber</span></span>|<span data-ttu-id="3f511-124">xs:Long</span><span class="sxs-lookup"><span data-stu-id="3f511-124">xs:long</span></span>|<span data-ttu-id="3f511-125">Pořadové číslo emitovaného záznamu</span><span class="sxs-lookup"><span data-stu-id="3f511-125">The sequence number of the emitted record</span></span>|  
|<span data-ttu-id="3f511-126">eventTime</span><span class="sxs-lookup"><span data-stu-id="3f511-126">EventTime</span></span>|<span data-ttu-id="3f511-127">xs</span><span class="sxs-lookup"><span data-stu-id="3f511-127">xs:dateTime</span></span>|<span data-ttu-id="3f511-128">Čas v UTC při byl vygenerované události</span><span class="sxs-lookup"><span data-stu-id="3f511-128">The time in UTC when the event was emitted</span></span>|  
|<span data-ttu-id="3f511-129">Název</span><span class="sxs-lookup"><span data-stu-id="3f511-129">Name</span></span>|<span data-ttu-id="3f511-130">xs:String</span><span class="sxs-lookup"><span data-stu-id="3f511-130">xs:string</span></span>|<span data-ttu-id="3f511-131">Název aktivity, která naplánované podřízené aktivity</span><span class="sxs-lookup"><span data-stu-id="3f511-131">The name of the activity that scheduled the child activity</span></span>|  
|<span data-ttu-id="3f511-132">ID aktivity</span><span class="sxs-lookup"><span data-stu-id="3f511-132">ActivityId</span></span>|<span data-ttu-id="3f511-133">xs:String</span><span class="sxs-lookup"><span data-stu-id="3f511-133">xs:string</span></span>|<span data-ttu-id="3f511-134">Id aktivity, která naplánované podřízené aktivity</span><span class="sxs-lookup"><span data-stu-id="3f511-134">The id of the activity that scheduled the child activity</span></span>|  
|<span data-ttu-id="3f511-135">ActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="3f511-135">ActivityInstanceId</span></span>|<span data-ttu-id="3f511-136">xs:String</span><span class="sxs-lookup"><span data-stu-id="3f511-136">xs:string</span></span>|<span data-ttu-id="3f511-137">Id instance aktivity, která naplánované podřízené aktivity</span><span class="sxs-lookup"><span data-stu-id="3f511-137">The instance id of the activity that scheduled the child activity</span></span>|  
|<span data-ttu-id="3f511-138">ActivityTypeName</span><span class="sxs-lookup"><span data-stu-id="3f511-138">ActivityTypeName</span></span>|<span data-ttu-id="3f511-139">xs:String</span><span class="sxs-lookup"><span data-stu-id="3f511-139">xs:string</span></span>|<span data-ttu-id="3f511-140">Typ aktivity, která požadována operace zrušení</span><span class="sxs-lookup"><span data-stu-id="3f511-140">The type of the activity that requested the cancel operation</span></span>|  
|<span data-ttu-id="3f511-141">ChildActivityName</span><span class="sxs-lookup"><span data-stu-id="3f511-141">ChildActivityName</span></span>|<span data-ttu-id="3f511-142">xs:String</span><span class="sxs-lookup"><span data-stu-id="3f511-142">xs:string</span></span>|<span data-ttu-id="3f511-143">Název naplánované aktivity</span><span class="sxs-lookup"><span data-stu-id="3f511-143">The name of the scheduled activity</span></span>|  
|<span data-ttu-id="3f511-144">ChildActivityId</span><span class="sxs-lookup"><span data-stu-id="3f511-144">ChildActivityId</span></span>|<span data-ttu-id="3f511-145">xs:String</span><span class="sxs-lookup"><span data-stu-id="3f511-145">xs:string</span></span>|<span data-ttu-id="3f511-146">Id naplánované aktivity</span><span class="sxs-lookup"><span data-stu-id="3f511-146">The id of the scheduled activity</span></span>|  
|<span data-ttu-id="3f511-147">ChildActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="3f511-147">ChildActivityInstanceId</span></span>|<span data-ttu-id="3f511-148">xs:String</span><span class="sxs-lookup"><span data-stu-id="3f511-148">xs:string</span></span>|<span data-ttu-id="3f511-149">Id instance naplánované aktivity</span><span class="sxs-lookup"><span data-stu-id="3f511-149">The instance id of the scheduled activity</span></span>|  
|<span data-ttu-id="3f511-150">ChildActivityTypeName</span><span class="sxs-lookup"><span data-stu-id="3f511-150">ChildActivityTypeName</span></span>|<span data-ttu-id="3f511-151">xs:String</span><span class="sxs-lookup"><span data-stu-id="3f511-151">xs:string</span></span>|<span data-ttu-id="3f511-152">Typ naplánované aktivity</span><span class="sxs-lookup"><span data-stu-id="3f511-152">The type of the scheduled activity</span></span>|  
|<span data-ttu-id="3f511-153">Poznámky</span><span class="sxs-lookup"><span data-stu-id="3f511-153">Annotations</span></span>|<span data-ttu-id="3f511-154">xs:String</span><span class="sxs-lookup"><span data-stu-id="3f511-154">xs:string</span></span>|<span data-ttu-id="3f511-155">Poznámky, které byly přidány k této události.</span><span class="sxs-lookup"><span data-stu-id="3f511-155">The annotations that were added to this event.</span></span>  <span data-ttu-id="3f511-156">Hodnoty jsou uloženy v elementu xml ve formátu \<položky >\< název položky = "annotationName" type="System.String" > annotationValue\</bodu > \< /položky >.</span><span class="sxs-lookup"><span data-stu-id="3f511-156">The values are stored in an xml element in the format \<items>\< item  name = "annotationName" type="System.String">annotationValue\</item>\</items>.</span></span>  <span data-ttu-id="3f511-157">Pokud nejsou zadány žádné poznámky, pak řetězec obsahuje \<položky / >.</span><span class="sxs-lookup"><span data-stu-id="3f511-157">If no annotations are specified then the string contains \<items/>.</span></span> <span data-ttu-id="3f511-158">Velikost události trasování událostí pro Windows je omezena velikost vyrovnávací paměti ETW nebo maximální datová část pro událost trasování událostí pro Windows.</span><span class="sxs-lookup"><span data-stu-id="3f511-158">The ETW event size is limited by the ETW buffer size or the max payload for an ETW event.</span></span> <span data-ttu-id="3f511-159">Pokud velikost události překročila omezení trasování událostí pro Windows, pak tato událost je rozdělená do odstranit poznámky a nahraďte hodnoty anotace s \<položky >...  \< /položky >.</span><span class="sxs-lookup"><span data-stu-id="3f511-159">If the size of the event exceeds the ETW limits, then the event is truncated by dropping the annotations and replacing the annotation value with \<items>...\</items>.</span></span>|  
|<span data-ttu-id="3f511-160">ProfileName</span><span class="sxs-lookup"><span data-stu-id="3f511-160">ProfileName</span></span>|<span data-ttu-id="3f511-161">xs:String</span><span class="sxs-lookup"><span data-stu-id="3f511-161">xs:string</span></span>|<span data-ttu-id="3f511-162">Název nebo sledování profil, který způsobil v tomto případě se vygenerované</span><span class="sxs-lookup"><span data-stu-id="3f511-162">The name or the tracking profile that resulted in this event being emitted</span></span>|  
|<span data-ttu-id="3f511-163">HostReference</span><span class="sxs-lookup"><span data-stu-id="3f511-163">HostReference</span></span>|<span data-ttu-id="3f511-164">xs:String</span><span class="sxs-lookup"><span data-stu-id="3f511-164">xs:string</span></span>|<span data-ttu-id="3f511-165">Webové hostované služby v tomto poli jednoznačně identifikuje v hierarchii webové služby.</span><span class="sxs-lookup"><span data-stu-id="3f511-165">For web hosted services, this field uniquely identifies the service in the web hierarchy.</span></span>  <span data-ttu-id="3f511-166">Formát je definovaný jako "virtuální cesta aplikace název webu &#124; Virtuální cesta služby &#124; ServiceName' Příklad: "Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService.</span><span class="sxs-lookup"><span data-stu-id="3f511-166">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName' Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'</span></span>|  
|<span data-ttu-id="3f511-167">Domény aplikace</span><span class="sxs-lookup"><span data-stu-id="3f511-167">AppDomain</span></span>|<span data-ttu-id="3f511-168">xs:String</span><span class="sxs-lookup"><span data-stu-id="3f511-168">xs:string</span></span>|<span data-ttu-id="3f511-169">Řetězec vrácený AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="3f511-169">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
---
title: "Sledování záznamů"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 51adbda3-bd8b-4892-a8ea-d343186472d2
caps.latest.revision: "20"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: bfb5c297b903909af7df08f150f3e2f507ee190d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="tracking-records"></a><span data-ttu-id="abe80-102">Sledování záznamů</span><span class="sxs-lookup"><span data-stu-id="abe80-102">Tracking Records</span></span>
<span data-ttu-id="abe80-103">Modul runtime pracovního postupu je instrumentována pro vydávání sledování záznamů sledovat provádění instance pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="abe80-103">The workflow runtime is instrumented to emit tracking records to follow the execution of a workflow instance.</span></span>  
  
## <a name="tracking-records"></a><span data-ttu-id="abe80-104">Sledování záznamů</span><span class="sxs-lookup"><span data-stu-id="abe80-104">Tracking Records</span></span>  
 <span data-ttu-id="abe80-105">V následující tabulce jsou záznamy sledování, které vysílá modulu runtime pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="abe80-105">The following table details the tracking records that the workflow runtime emits.</span></span>  
  
|<span data-ttu-id="abe80-106">Sledování záznamu</span><span class="sxs-lookup"><span data-stu-id="abe80-106">Tracking record</span></span>|<span data-ttu-id="abe80-107">Popis</span><span class="sxs-lookup"><span data-stu-id="abe80-107">Description</span></span>|  
|---------------------|-----------------|  
|<span data-ttu-id="abe80-108">Životní cyklus záznamy pracovního postupu</span><span class="sxs-lookup"><span data-stu-id="abe80-108">Workflow life cycle records</span></span>|<span data-ttu-id="abe80-109">Vygenerované různých fázích životního cyklu instance pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="abe80-109">Emitted during various stages of the life cycle of the workflow instance.</span></span> <span data-ttu-id="abe80-110">Záznam je například vygenerované při spuštění pracovního postupu nebo dokončení.</span><span class="sxs-lookup"><span data-stu-id="abe80-110">For example, a record is emitted when the workflow starts or completes.</span></span>|  
|<span data-ttu-id="abe80-111">Životní cyklus záznamů aktivit</span><span class="sxs-lookup"><span data-stu-id="abe80-111">Activity life cycle records</span></span>|<span data-ttu-id="abe80-112">Podrobnosti o provádění aktivity.</span><span class="sxs-lookup"><span data-stu-id="abe80-112">Details activity execution.</span></span> <span data-ttu-id="abe80-113">Tyto záznamy označují stav aktivity pracovního postupu, jako když bude naplánované aktivity, při dokončení aktivity, nebo když dojde k chybě.</span><span class="sxs-lookup"><span data-stu-id="abe80-113">These records indicate the state of a workflow activity such as when an activity is scheduled, when the activity completes, or when a fault occurs.</span></span>|  
|<span data-ttu-id="abe80-114">BOOKMARK – obnovení záznamů</span><span class="sxs-lookup"><span data-stu-id="abe80-114">Bookmark resumption records</span></span>|<span data-ttu-id="abe80-115">Vygenerované vždy, když je obnoveno záložku v rámci instance pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="abe80-115">Emitted whenever a bookmark within a workflow instance is resumed.</span></span>|  
|<span data-ttu-id="abe80-116">Vlastní sledování záznamů</span><span class="sxs-lookup"><span data-stu-id="abe80-116">Custom tracking records</span></span>|<span data-ttu-id="abe80-117">Autor pracovního postupu můžete vytvořit vlastní sledování záznamů a posílat je v rámci vlastní aktivity.</span><span class="sxs-lookup"><span data-stu-id="abe80-117">A workflow author can create custom tracking records and emit them within a custom activity.</span></span>|  
  
 <span data-ttu-id="abe80-118">Všechny záznamy sledování vygenerované z modulu runtime pracovního postupu odvozeny od základní třídy <xref:System.Activities.Tracking.TrackingRecord>, který obsahuje společnou sadu dat.</span><span class="sxs-lookup"><span data-stu-id="abe80-118">All tracking-related records emitted from the WF runtime derive from the base class <xref:System.Activities.Tracking.TrackingRecord>, which contains the common set of data.</span></span> <span data-ttu-id="abe80-119">Sledování záznamy zobrazit životního cyklu pro jednoduché pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="abe80-119">Tracking records show the life cycle for a simple workflow.</span></span> <span data-ttu-id="abe80-120">Každý záznam sledování obsahuje podrobnosti o události přidružené sledování, jako <xref:System.Activities.Tracking.TrackingRecord.InstanceId%2A>, <xref:System.Activities.Tracking.TrackingRecord.RecordNumber%2A>a další informace, které jsou specifické pro daný typ sledování záznamu.</span><span class="sxs-lookup"><span data-stu-id="abe80-120">Each tracking record contains details about the associated tracking event, such as the <xref:System.Activities.Tracking.TrackingRecord.InstanceId%2A>, <xref:System.Activities.Tracking.TrackingRecord.RecordNumber%2A>, and additional information specific to the type of tracking record.</span></span>  
  
 <span data-ttu-id="abe80-121">Následující typy <xref:System.Activities.Tracking.TrackingRecord> objekty jsou vygenerované modulem runtime pracovního postupu:</span><span class="sxs-lookup"><span data-stu-id="abe80-121">The following types of <xref:System.Activities.Tracking.TrackingRecord> objects are emitted by the workflow runtime:</span></span>  
  
-   <span data-ttu-id="abe80-122">**WorkflowInstanceRecord** – toto <xref:System.Activities.Tracking.TrackingRecord> popisuje životní cyklus k instanci pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="abe80-122">**WorkflowInstanceRecord** - This <xref:System.Activities.Tracking.TrackingRecord> describes the life cycle of the workflow instance.</span></span> <span data-ttu-id="abe80-123">Záznam je například vygenerované, když se pracovní postup spustí nebo dokončí a obsahuje informace o stavu instance pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="abe80-123">For example, a record is emitted when the workflow starts or completes, and contains the state of the workflow instance.</span></span> <span data-ttu-id="abe80-124">Podrobnosti o tento záznam naleznete na adrese <xref:System.Activities.Tracking.WorkflowInstanceRecord>.</span><span class="sxs-lookup"><span data-stu-id="abe80-124">The details of this record can be found at <xref:System.Activities.Tracking.WorkflowInstanceRecord>.</span></span>  
  
-   <span data-ttu-id="abe80-125">**WorkflowInstanceAbortedRecord** – toto <xref:System.Activities.Tracking.TrackingRecord> je vygenerované při zrušení instance pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="abe80-125">**WorkflowInstanceAbortedRecord** - This <xref:System.Activities.Tracking.TrackingRecord> is emitted when a workflow instance aborts.</span></span> <span data-ttu-id="abe80-126">Záznam obsahuje důvod k instanci pracovního postupu přerušení.</span><span class="sxs-lookup"><span data-stu-id="abe80-126">The record contains the reason for the workflow instance being aborted.</span></span> <span data-ttu-id="abe80-127">Podrobnosti o tento záznam naleznete na adrese <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>.</span><span class="sxs-lookup"><span data-stu-id="abe80-127">The details of this record can be found at <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>.</span></span>  
  
-   <span data-ttu-id="abe80-128">**WorkflowInstanceUnhandledExceptionRecord** – toto <xref:System.Activities.Tracking.TrackingRecord> jsou vydávány, pokud k výjimce dojde v instanci pracovního postupu a nejsou zpracovávány pomocí žádné aktivity.</span><span class="sxs-lookup"><span data-stu-id="abe80-128">**WorkflowInstanceUnhandledExceptionRecord** - This <xref:System.Activities.Tracking.TrackingRecord> is emitted if an exception occurs in the workflow instance and is not handled by any activity.</span></span> <span data-ttu-id="abe80-129">Záznam obsahuje podrobnosti o výjimce.</span><span class="sxs-lookup"><span data-stu-id="abe80-129">The record contains the exception details.</span></span> <span data-ttu-id="abe80-130">Podrobnosti o tento záznam naleznete na adrese <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>.</span><span class="sxs-lookup"><span data-stu-id="abe80-130">The details of this record can be found at <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>.</span></span>  
  
-   <span data-ttu-id="abe80-131">**WorkflowInstanceSuspendedRecord** – toto <xref:System.Activities.Tracking.TrackingRecord> je vygenerované vždy, když je pozastaveno instanci pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="abe80-131">**WorkflowInstanceSuspendedRecord** - This <xref:System.Activities.Tracking.TrackingRecord> is emitted whenever a workflow instance is suspended.</span></span> <span data-ttu-id="abe80-132">Záznam obsahuje důvod k instanci pracovního postupu se pozastaví.</span><span class="sxs-lookup"><span data-stu-id="abe80-132">The record contains the reason for the workflow instance being suspended.</span></span> <span data-ttu-id="abe80-133">Podrobnosti o tento záznam naleznete na adrese <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>.</span><span class="sxs-lookup"><span data-stu-id="abe80-133">The details of this record can be found at <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>.</span></span>  
  
-   <span data-ttu-id="abe80-134">**WorkflowInstanceTerminatedRecord** – toto <xref:System.Activities.Tracking.TrackingRecord> je vygenerované vždy, když je ukončen instanci pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="abe80-134">**WorkflowInstanceTerminatedRecord** - This <xref:System.Activities.Tracking.TrackingRecord> is emitted whenever a workflow instance is terminated.</span></span> <span data-ttu-id="abe80-135">Záznam obsahuje důvod k instanci pracovního postupu bude ukončen.</span><span class="sxs-lookup"><span data-stu-id="abe80-135">The record contains the reason for the workflow instance being terminated.</span></span> <span data-ttu-id="abe80-136">Podrobnosti o tento záznam naleznete na adrese <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>.</span><span class="sxs-lookup"><span data-stu-id="abe80-136">The details of this record can be found at <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>.</span></span>  
  
-   <span data-ttu-id="abe80-137">**ActivityStateRecord** – toto <xref:System.Activities.Tracking.TrackingRecord> je vygenerované při spustí aktivita v rámci pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="abe80-137">**ActivityStateRecord** - This <xref:System.Activities.Tracking.TrackingRecord> is emitted when an activity within a workflow executes.</span></span> <span data-ttu-id="abe80-138">Tyto záznamy označují stav aktivity v rámci instance pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="abe80-138">These records indicate the state of the activity within the workflow instance.</span></span> <span data-ttu-id="abe80-139">Podrobnosti o tento záznam naleznete na adrese <xref:System.Activities.Tracking.ActivityStateRecord>.</span><span class="sxs-lookup"><span data-stu-id="abe80-139">The details of this record can be found at <xref:System.Activities.Tracking.ActivityStateRecord>.</span></span>  
  
-   <span data-ttu-id="abe80-140">**ActivityScheduledRecord** – toto <xref:System.Activities.Tracking.TrackingRecord> je vygenerované při aktivitě plány podřízené aktivity.</span><span class="sxs-lookup"><span data-stu-id="abe80-140">**ActivityScheduledRecord** - This <xref:System.Activities.Tracking.TrackingRecord> is emitted when an activity schedules a child activity.</span></span> <span data-ttu-id="abe80-141">Tento záznam obsahuje podrobnosti o nadřazené aktivity (plánování aktivit) a plánovaných podřízené aktivity.</span><span class="sxs-lookup"><span data-stu-id="abe80-141">This record contains details for both the parent activity (scheduling activity) and the scheduled child activity.</span></span> <span data-ttu-id="abe80-142">Podrobnosti o tento záznam naleznete na adrese <xref:System.Activities.Tracking.ActivityScheduledRecord>.</span><span class="sxs-lookup"><span data-stu-id="abe80-142">The details of this record can be found at <xref:System.Activities.Tracking.ActivityScheduledRecord>.</span></span>  
  
-   <span data-ttu-id="abe80-143">**FaultPropagationRecord** – toto <xref:System.Activities.Tracking.TrackingRecord> je vygenerované pro každou obslužnou rutinu, která vypadá na záznam, dokud není zpracována.</span><span class="sxs-lookup"><span data-stu-id="abe80-143">**FaultPropagationRecord** - This <xref:System.Activities.Tracking.TrackingRecord> is emitted for each handler that looks at the record until it is handled.</span></span> <span data-ttu-id="abe80-144">Slouží k označení cestu, kterou trvalo chybu v rámci instance pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="abe80-144">It is used to denote the path a fault took within the workflow instance.</span></span> <span data-ttu-id="abe80-145">Podrobnosti o tento záznam naleznete na adrese <xref:System.Activities.Tracking.FaultPropagationRecord>.</span><span class="sxs-lookup"><span data-stu-id="abe80-145">The details of this record can be found at <xref:System.Activities.Tracking.FaultPropagationRecord>.</span></span>  
  
-   <span data-ttu-id="abe80-146">**CancelRequestedRecord** – toto <xref:System.Activities.Tracking.TrackingRecord> je vygenerované vždy, když aktivita pokusí zrušení podřízené aktivity.</span><span class="sxs-lookup"><span data-stu-id="abe80-146">**CancelRequestedRecord** - This <xref:System.Activities.Tracking.TrackingRecord> is emitted whenever an activity tries to cancel a child activity.</span></span> <span data-ttu-id="abe80-147">Tento záznam obsahuje podrobnosti o aktivity nadřazené a podřízené aktivity, která probíhá její zrušení.</span><span class="sxs-lookup"><span data-stu-id="abe80-147">This record contains details for both the parent activity and the child activity that is being canceled.</span></span> <span data-ttu-id="abe80-148">Podrobnosti o tento záznam naleznete na adrese <xref:System.Activities.Tracking.CancelRequestedRecord>.</span><span class="sxs-lookup"><span data-stu-id="abe80-148">The details of this record can be found at <xref:System.Activities.Tracking.CancelRequestedRecord>.</span></span>  
  
-   <span data-ttu-id="abe80-149">**BookmarkResumptionRecord** – toto <xref:System.Activities.Tracking.TrackingRecord> sleduje všechny záložku, na kterou je byl úspěšně obnoven.</span><span class="sxs-lookup"><span data-stu-id="abe80-149">**BookmarkResumptionRecord** - This <xref:System.Activities.Tracking.TrackingRecord> tracks any bookmark that is successfully resumed.</span></span> <span data-ttu-id="abe80-150">Podrobnosti o tento záznam naleznete na adrese <xref:System.Activities.Tracking.BookmarkResumptionRecord>.</span><span class="sxs-lookup"><span data-stu-id="abe80-150">The details of this record can be found at <xref:System.Activities.Tracking.BookmarkResumptionRecord>.</span></span>  
  
-   <span data-ttu-id="abe80-151">**CustomTrackingRecord** – toto <xref:System.Activities.Tracking.TrackingRecord> se vytvoří a vygenerované autorem pracovního postupu uvnitř pracovního postupu vlastní aktivity.</span><span class="sxs-lookup"><span data-stu-id="abe80-151">**CustomTrackingRecord** - This <xref:System.Activities.Tracking.TrackingRecord> is created and emitted by a workflow author within a custom workflow activity.</span></span> <span data-ttu-id="abe80-152">Vlastní sledování záznamů je možné importovat s daty pro vypuštění společně s záznamy.</span><span class="sxs-lookup"><span data-stu-id="abe80-152">Custom tracking records can be populated with data to be emitted along with the records.</span></span> <span data-ttu-id="abe80-153">Podrobnosti o tento záznam naleznete na adrese <xref:System.Activities.Tracking.CustomTrackingRecord>.</span><span class="sxs-lookup"><span data-stu-id="abe80-153">The details of this record can be found at <xref:System.Activities.Tracking.CustomTrackingRecord>.</span></span>  
  
 <span data-ttu-id="abe80-154">Například může být ke jednoduchou <xref:System.Activities.Statements.Sequence> aktivity, která obsahuje <xref:System.Activities.Statements.WriteLine> operaci s sledování záznamy vygenerované v následujícím pořadí:</span><span class="sxs-lookup"><span data-stu-id="abe80-154">For example, there could be a simple <xref:System.Activities.Statements.Sequence> activity that contains a <xref:System.Activities.Statements.WriteLine> operation with tracking records emitted in the following order:</span></span>  
  
1.  <span data-ttu-id="abe80-155"><xref:System.Activities.Tracking.WorkflowInstanceRecord>Označuje, že se spouští pracovní postup.</span><span class="sxs-lookup"><span data-stu-id="abe80-155"><xref:System.Activities.Tracking.WorkflowInstanceRecord> indicates that the workflow is starting.</span></span>  
  
2.  <span data-ttu-id="abe80-156"><xref:System.Activities.Tracking.ActivityScheduledRecord>Označuje, že bylo naplánováno aktivitu.</span><span class="sxs-lookup"><span data-stu-id="abe80-156"><xref:System.Activities.Tracking.ActivityScheduledRecord> indicates that an activity has been scheduled.</span></span> <span data-ttu-id="abe80-157">V takovém případě je <xref:System.Activities.Statements.Sequence> aktivity.</span><span class="sxs-lookup"><span data-stu-id="abe80-157">In this case it is a <xref:System.Activities.Statements.Sequence> activity.</span></span>  
  
3.  <span data-ttu-id="abe80-158"><xref:System.Activities.Tracking.ActivityScheduledRecord>představuje <xref:System.Activities.Statements.WriteLine> aktivity.</span><span class="sxs-lookup"><span data-stu-id="abe80-158"><xref:System.Activities.Tracking.ActivityScheduledRecord> represents the <xref:System.Activities.Statements.WriteLine> activity.</span></span>  
  
4.  <span data-ttu-id="abe80-159">Existují dva <xref:System.Activities.Tracking.ActivityStateRecord> záznamy, které představují dvě aktivity dokončení.</span><span class="sxs-lookup"><span data-stu-id="abe80-159">There are two <xref:System.Activities.Tracking.ActivityStateRecord> records that represent the two activities completing.</span></span>  
  
5.  <span data-ttu-id="abe80-160"><xref:System.Activities.Tracking.WorkflowInstanceRecord>Označuje, že je dokončení pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="abe80-160"><xref:System.Activities.Tracking.WorkflowInstanceRecord> indicates that the workflow is completing.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abe80-161">Viz také</span><span class="sxs-lookup"><span data-stu-id="abe80-161">See Also</span></span>  
 [<span data-ttu-id="abe80-162">Windows Server App Fabric monitorování</span><span class="sxs-lookup"><span data-stu-id="abe80-162">Windows Server App Fabric Monitoring</span></span>](http://go.microsoft.com/fwlink/?LinkId=201273)  
 [<span data-ttu-id="abe80-163">Monitorování aplikací pomocí App Fabric</span><span class="sxs-lookup"><span data-stu-id="abe80-163">Monitoring Applications with App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkId=201275)
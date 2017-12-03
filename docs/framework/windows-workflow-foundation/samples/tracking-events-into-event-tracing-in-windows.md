---
title: "Sledování událostí do událostí trasování v systému Windows"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f812659b-0943-45ff-9430-4defa733182b
caps.latest.revision: "19"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 03fe4d3805d79188777404de201316441b3f8831
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="tracking-events-into-event-tracing-in-windows"></a><span data-ttu-id="b4696-102">Sledování událostí do událostí trasování v systému Windows</span><span class="sxs-lookup"><span data-stu-id="b4696-102">Tracking Events into Event Tracing in Windows</span></span>
<span data-ttu-id="b4696-103">Tento příklad ukazuje, jak povolit [!INCLUDE[wf](../../../../includes/wf-md.md)] sledování v rámci pracovního postupu služby a emitování sledování událostí v trasování událostí pro Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="b4696-103">This sample demonstrates how to enable [!INCLUDE[wf](../../../../includes/wf-md.md)] tracking on a workflow service and emit the tracking events in Event Tracing for Windows (ETW).</span></span> <span data-ttu-id="b4696-104">Pro vydávání pracovní postup sledování záznamů do trasování událostí pro Windows, používá ukázku účastník sledování ETW (<xref:System.Activities.Tracking.EtwTrackingParticipant>).</span><span class="sxs-lookup"><span data-stu-id="b4696-104">To emit workflow tracking records into ETW, the sample uses the ETW tracking participant (<xref:System.Activities.Tracking.EtwTrackingParticipant>).</span></span>  
  
 <span data-ttu-id="b4696-105">Pracovní postup v ukázce přijme požadavek, přiřadí vzájemné vstupních dat vstupní proměnné a vrátí vzájemných zpět klientovi.</span><span class="sxs-lookup"><span data-stu-id="b4696-105">The workflow in the sample receives a request, assigns the reciprocal of the input data to the input variable and returns the reciprocal back to the client.</span></span> <span data-ttu-id="b4696-106">Když jsou vstupní data 0, dělení nulové výjimkou výskytu, která je neošetřená, dojde k přerušení pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="b4696-106">When the input data is 0, a divide by zero exception occurs that is unhandled that causes the workflow to abort.</span></span> <span data-ttu-id="b4696-107">S povoleno sledování, je sledovat záznam chyby vygenerované do trasování událostí pro Windows, které mohou pomoci při odstraňování chyba později.</span><span class="sxs-lookup"><span data-stu-id="b4696-107">With tracking enabled, the error track record is emitted to ETW, which can help troubleshoot the error later.</span></span> <span data-ttu-id="b4696-108">Trasování událostí pro Windows Sledování účastník je nakonfigurovaný s profil sledování k odběru sledování záznamů.</span><span class="sxs-lookup"><span data-stu-id="b4696-108">The ETW tracking participant is configured with a tracking profile to subscribe to tracking records.</span></span> <span data-ttu-id="b4696-109">Profil sledování je definován v souboru Web.config a zadat jako parametr konfigurace sledování účastníkům trasování událostí pro Windows.</span><span class="sxs-lookup"><span data-stu-id="b4696-109">The tracking profile is defined in the Web.config file and provided as a configuration parameter to the ETW tracking participant.</span></span> <span data-ttu-id="b4696-110">Trasování událostí pro Windows Sledování účastník je nakonfigurovaný v souboru Web.config služby pracovního postupu a jsou použity pro službu jako chování služby.</span><span class="sxs-lookup"><span data-stu-id="b4696-110">The ETW tracking participant is configured in the Web.config file of the workflow service and is applied to the service as a service behavior.</span></span> <span data-ttu-id="b4696-111">V této ukázce zobrazit události sledování v protokolu událostí pomocí prohlížeče událostí.</span><span class="sxs-lookup"><span data-stu-id="b4696-111">In this sample, you view the tracking events in the event log using Event Viewer.</span></span>  
  
## <a name="workflow-tracking-details"></a><span data-ttu-id="b4696-112">Podrobnosti sledování pracovního postupu</span><span class="sxs-lookup"><span data-stu-id="b4696-112">Workflow Tracking Details</span></span>  
 [!INCLUDE[wf2](../../../../includes/wf2-md.md)]<span data-ttu-id="b4696-113">poskytuje sledování infrastruktury ke sledování provádění instanci pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="b4696-113"> provides a tracking infrastructure to track the execution of a workflow instance.</span></span> <span data-ttu-id="b4696-114">Modul runtime sledování vytvoří instanci pracovního postupu pro vydávání události související s životního cyklu pracovního postupu, události z aktivit pracovního postupu a vlastních událostí.</span><span class="sxs-lookup"><span data-stu-id="b4696-114">The tracking runtime creates a workflow instance to emit events related to the workflow lifecycle, events from workflow activities and custom events.</span></span> <span data-ttu-id="b4696-115">V následující tabulce jsou primární součásti sledování infrastruktury.</span><span class="sxs-lookup"><span data-stu-id="b4696-115">The following table details the primary components of the tracking infrastructure.</span></span>  
  
|<span data-ttu-id="b4696-116">Součást</span><span class="sxs-lookup"><span data-stu-id="b4696-116">Component</span></span>|<span data-ttu-id="b4696-117">Popis</span><span class="sxs-lookup"><span data-stu-id="b4696-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b4696-118">Sledování runtime</span><span class="sxs-lookup"><span data-stu-id="b4696-118">Tracking runtime</span></span>|<span data-ttu-id="b4696-119">Poskytuje infrastrukturu pro vydávání sledování záznamů.</span><span class="sxs-lookup"><span data-stu-id="b4696-119">Provides the infrastructure to emit tracking records.</span></span>|  
|<span data-ttu-id="b4696-120">Sledování účastníků</span><span class="sxs-lookup"><span data-stu-id="b4696-120">Tracking participants</span></span>|<span data-ttu-id="b4696-121">Přistupuje ke sledování záznamů.</span><span class="sxs-lookup"><span data-stu-id="b4696-121">Accesses the tracking records.</span></span> [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)]<span data-ttu-id="b4696-122">se dodává s účastníkem sledování, která zapisuje sledování záznamů jako události trasování událostí pro Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="b4696-122"> ships with a tracking participant that writes tracking records as Event Tracing for Windows (ETW) events.</span></span>|  
|<span data-ttu-id="b4696-123">Sledování profilu</span><span class="sxs-lookup"><span data-stu-id="b4696-123">Tracking profile</span></span>|<span data-ttu-id="b4696-124">Filtrační mechanismus, který umožňuje účastníkem sledování k odběru pro podmnožinu sledování záznamy vygenerované z instance pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="b4696-124">A filtering mechanism that allows a tracking participant to subscribe for a subset of the tracking records emitted from a workflow instance.</span></span>|  
  
 <span data-ttu-id="b4696-125">V následující tabulce jsou záznamy sledování, které vysílá modulu runtime pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="b4696-125">The following table details the tracking records that the workflow runtime emits.</span></span>  
  
|<span data-ttu-id="b4696-126">Sledování záznamu</span><span class="sxs-lookup"><span data-stu-id="b4696-126">Tracking record</span></span>|<span data-ttu-id="b4696-127">Popis</span><span class="sxs-lookup"><span data-stu-id="b4696-127">Description</span></span>|  
|---------------------|-----------------|  
|<span data-ttu-id="b4696-128">Záznamy sledování instance pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="b4696-128">Workflow instance tracking records.</span></span>|<span data-ttu-id="b4696-129">Popisuje životní cyklus k instanci pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="b4696-129">Describes the lifecycle of the workflow instance.</span></span> <span data-ttu-id="b4696-130">Například je záznam instance vygenerované při spuštění pracovního postupu nebo dokončení.</span><span class="sxs-lookup"><span data-stu-id="b4696-130">For example, an instance record is emitted when the workflow starts or completes.</span></span>|  
|<span data-ttu-id="b4696-131">Záznamy o sledování stavu aktivity.</span><span class="sxs-lookup"><span data-stu-id="b4696-131">Activity state tracking records.</span></span>|<span data-ttu-id="b4696-132">Podrobnosti o provádění aktivity.</span><span class="sxs-lookup"><span data-stu-id="b4696-132">Details activity execution.</span></span> <span data-ttu-id="b4696-133">Tyto záznamy označují stav aktivity pracovního postupu, jako je například naplánovaného aktivitu nebo po dokončení aktivity nebo když je vyvolána chybu.</span><span class="sxs-lookup"><span data-stu-id="b4696-133">These records indicate the state of a workflow activity such as when an activity is scheduled or when the activity completes or when a fault is thrown.</span></span>|  
|<span data-ttu-id="b4696-134">BOOKMARK – obnovení záznamu.</span><span class="sxs-lookup"><span data-stu-id="b4696-134">Bookmark resumption record.</span></span>|<span data-ttu-id="b4696-135">Vygenerované vždy, když je obnoveno záložku v rámci instance pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="b4696-135">Emitted whenever a bookmark within a workflow instance is resumed.</span></span>|  
|<span data-ttu-id="b4696-136">Vlastní sledování záznamy.</span><span class="sxs-lookup"><span data-stu-id="b4696-136">Custom tracking records.</span></span>|<span data-ttu-id="b4696-137">Autor pracovního postupu můžete vytvořit vlastní sledování záznamů a posílat je v rámci vlastní aktivity.</span><span class="sxs-lookup"><span data-stu-id="b4696-137">A workflow author can create custom tracking records and emit them within the custom activity.</span></span>|  
|<xref:System.Activities.Tracking.ActivityScheduledRecord>|<span data-ttu-id="b4696-138">Tento záznam je vygenerované při aktivitu plány jiné aktivity.</span><span class="sxs-lookup"><span data-stu-id="b4696-138">This record is emitted when an activity schedules another activity.</span></span>|  
|<xref:System.Activities.Tracking.FaultPropagationRecord>|<span data-ttu-id="b4696-139">Tento záznam je vygenerované při šíření chybu z aktivity.</span><span class="sxs-lookup"><span data-stu-id="b4696-139">This record is emitted when a fault is propagated from an activity.</span></span>|  
|<xref:System.Activities.Tracking.CancelRequestedRecord>|<span data-ttu-id="b4696-140">Tento záznam jsou vydávány, když aktivita je zrušeno pomocí jiné aktivity.</span><span class="sxs-lookup"><span data-stu-id="b4696-140">This record is emitted when an activity is canceled by another activity.</span></span>|  
  
 <span data-ttu-id="b4696-141">Sledování účastník odběratel pro podmnožinu záznamy emitovaného sledování pomocí sledování profilů.</span><span class="sxs-lookup"><span data-stu-id="b4696-141">The tracking participant subscribes for a subset of the emitted tracking records using tracking profiles.</span></span> <span data-ttu-id="b4696-142">Profil sledování obsahuje dotazy pro sledování, které umožňují přihlášení k odběru pro typ záznamu konkrétní sledování.</span><span class="sxs-lookup"><span data-stu-id="b4696-142">A tracking profile contains tracking queries that allow subscribing for a particular tracking record type.</span></span> <span data-ttu-id="b4696-143">Sledování profily mohou být zadané v kódu nebo v konfiguraci.</span><span class="sxs-lookup"><span data-stu-id="b4696-143">Tracking profiles can be specified in code or in configuration.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="b4696-144">Pro fungování této ukázky</span><span class="sxs-lookup"><span data-stu-id="b4696-144">To use this sample</span></span>  
  
1.  <span data-ttu-id="b4696-145">Pomocí [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], otevřete soubor řešení EtwTrackingParticipantSample.sln.</span><span class="sxs-lookup"><span data-stu-id="b4696-145">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the EtwTrackingParticipantSample.sln solution file.</span></span>  
  
2.  <span data-ttu-id="b4696-146">Sestavte řešení, stiskněte CTRL + SHIFT + B.</span><span class="sxs-lookup"><span data-stu-id="b4696-146">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="b4696-147">Pokud chcete spustit řešení, stisknutím klávesy F5.</span><span class="sxs-lookup"><span data-stu-id="b4696-147">To run the solution, press F5.</span></span>  
  
     <span data-ttu-id="b4696-148">Ve výchozím nastavení služba naslouchá na portu 53797 (http://localhost:53797/SampleWorkflowService.xamlx).</span><span class="sxs-lookup"><span data-stu-id="b4696-148">By default, the service is listening on port 53797 (http://localhost:53797/SampleWorkflowService.xamlx).</span></span>  
  
4.  <span data-ttu-id="b4696-149">Pomocí [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], otevřete testovacího klienta WCF.</span><span class="sxs-lookup"><span data-stu-id="b4696-149">Using [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], open the WCF test client.</span></span>  
  
     <span data-ttu-id="b4696-150">Testovacího klienta WCF (WcfTestClient.exe) se nachází v \< [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] instalační složka > \Common7\IDE\ složky.</span><span class="sxs-lookup"><span data-stu-id="b4696-150">The WCF test client (WcfTestClient.exe) is located in the \<[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] installation folder>\Common7\IDE\ folder.</span></span>  
  
     <span data-ttu-id="b4696-151">Výchozí hodnota [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] instalační složka je C:\Program Files\Microsoft Visual Studio 10.0.</span><span class="sxs-lookup"><span data-stu-id="b4696-151">The default [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] installation folder is C:\Program Files\Microsoft Visual Studio 10.0.</span></span>  
  
5.  <span data-ttu-id="b4696-152">V testu klienta WCF, vyberte **přidat službu** z **souboru** nabídky.</span><span class="sxs-lookup"><span data-stu-id="b4696-152">In WCF test client, select **Add Service** from the **File** menu.</span></span>  
  
     <span data-ttu-id="b4696-153">Přidáte adresa koncového bodu do vstupního pole.</span><span class="sxs-lookup"><span data-stu-id="b4696-153">Add the endpoint address in the input box.</span></span> <span data-ttu-id="b4696-154">Výchozí hodnota je http://localhost:53797/SampleWorkflowService.xamlx.</span><span class="sxs-lookup"><span data-stu-id="b4696-154">The default is http://localhost:53797/SampleWorkflowService.xamlx.</span></span>  
  
6.  <span data-ttu-id="b4696-155">Otevřete Prohlížeč událostí aplikace.</span><span class="sxs-lookup"><span data-stu-id="b4696-155">Open the Event Viewer application.</span></span>  
  
     <span data-ttu-id="b4696-156">Před vyvoláním služby, spusťte Prohlížeč událostí z **spustit** nabídce vyberte možnost **spustit** a zadejte `eventvwr.exe`.</span><span class="sxs-lookup"><span data-stu-id="b4696-156">Before invoking the service, start Event Viewer from the **Start** menu, select **Run** and type in `eventvwr.exe`.</span></span> <span data-ttu-id="b4696-157">Ujistěte se, že v protokolu událostí naslouchá pro sledování události vygenerované ze služby pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="b4696-157">Ensure that the event log is listening for tracking events emitted from the workflow service.</span></span>  
  
7.  <span data-ttu-id="b4696-158">Ve stromovém zobrazení prohlížeče událostí, přejděte na **Prohlížeč událostí**, **protokoly aplikací a služeb**, a **Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="b4696-158">In the tree view of the Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, and **Microsoft**.</span></span> <span data-ttu-id="b4696-159">Klikněte pravým tlačítkem na **Microsoft** a vyberte **zobrazení** a potom **zobrazit protokoly pro ladění a** povolit analýzy a protokoly pro ladění</span><span class="sxs-lookup"><span data-stu-id="b4696-159">Right-click **Microsoft** and select **View** and then **Show Analytic and Debug Logs** to enable the analytic and debug logs</span></span>  
  
     <span data-ttu-id="b4696-160">Ujistěte se, že **zobrazit protokoly pro ladění a** zaškrtnutá možnost.</span><span class="sxs-lookup"><span data-stu-id="b4696-160">Ensure that the **Show Analytic and Debug Logs** option is checked.</span></span>  
  
8.  <span data-ttu-id="b4696-161">Ve stromovém zobrazení v prohlížeči událostí, přejděte na **Prohlížeč událostí**, **protokoly aplikací a služeb**, **Microsoft**, **Windows**,  **Aplikace serveru – aplikace**.</span><span class="sxs-lookup"><span data-stu-id="b4696-161">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="b4696-162">Klikněte pravým tlačítkem na **analytické** a vyberte **povolit protokol** povolit **analytické** protokolu.</span><span class="sxs-lookup"><span data-stu-id="b4696-162">Right-click **Analytic** and select **Enable Log** to enable the **Analytic** log.</span></span>  
  
9. <span data-ttu-id="b4696-163">Testování služby pomocí testovacího klienta WCF dvojitým kliknutím na soubor `GetData`.</span><span class="sxs-lookup"><span data-stu-id="b4696-163">Test the service using the WCF test client by double-clicking `GetData`.</span></span>  
  
     <span data-ttu-id="b4696-164">Tím se otevře `GetData` metoda.</span><span class="sxs-lookup"><span data-stu-id="b4696-164">This opens the `GetData` method.</span></span> <span data-ttu-id="b4696-165">Požadavek přijímá jeden parametr a zajišťuje, že hodnota 0, který je výchozí.</span><span class="sxs-lookup"><span data-stu-id="b4696-165">The request accepts one parameter and ensures that the value is 0, which is the default.</span></span>  
  
     <span data-ttu-id="b4696-166">Klikněte na tlačítko **vyvolání**.</span><span class="sxs-lookup"><span data-stu-id="b4696-166">Click **Invoke**.</span></span>  
  
10. <span data-ttu-id="b4696-167">Pozorovat, jaké události vygenerované z pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="b4696-167">Observe the events emitted from the workflow.</span></span>  
  
     <span data-ttu-id="b4696-168">Přepněte zpět do prohlížeče událostí a přejděte do **Prohlížeč událostí**, **protokoly aplikací a služeb**, **Microsoft**, **Windows**,  **Aplikace serveru – aplikace**.</span><span class="sxs-lookup"><span data-stu-id="b4696-168">Switch back to Event Viewer and navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="b4696-169">Klikněte pravým tlačítkem na **analytické** a vyberte **aktualizovat**.</span><span class="sxs-lookup"><span data-stu-id="b4696-169">Right-click **Analytic** and select **Refresh**.</span></span>  
  
     <span data-ttu-id="b4696-170">Pracovní postup události se zobrazí v prohlížeči událostí.</span><span class="sxs-lookup"><span data-stu-id="b4696-170">The workflow events are displayed in the event viewer.</span></span> <span data-ttu-id="b4696-171">Všimněte si, že se zobrazují události spuštění pracovního postupu a že jeden z nich je nezpracovanou výjimku, která odpovídá na chybu v pracovním postupu.</span><span class="sxs-lookup"><span data-stu-id="b4696-171">Notice that workflow execution events are displayed and that one of them is an unhandled exception that corresponds to the error in workflow.</span></span> <span data-ttu-id="b4696-172">Navíc upozorňovací událost nevydává aktivita pracovního postupu, který označuje, že je aktivity vyvolání chybu.</span><span class="sxs-lookup"><span data-stu-id="b4696-172">Also, a warning event is emitted from the workflow activity, which indicates that the activity is throwing a fault.</span></span>  
  
11. <span data-ttu-id="b4696-173">Opakujte kroky 9 a 10 se vstupem dat než 0, tak, aby se žádná chyba.</span><span class="sxs-lookup"><span data-stu-id="b4696-173">Repeat steps 9 and 10 with an input of data other than 0, so that no error is thrown.</span></span>  
  
 <span data-ttu-id="b4696-174">Sledování profily umožňují přihlásit k odběru událostí, které jsou při změně stavu instance pracovního postupu vygenerované modulem runtime.</span><span class="sxs-lookup"><span data-stu-id="b4696-174">Tracking profiles allow you to subscribe to events that are emitted by the runtime when the state of a workflow instance changes.</span></span> <span data-ttu-id="b4696-175">V závislosti na vašich požadavků na monitorování, můžete vytvořit profil, který je velmi hrubým, který jako odběratel u malého podrobný stav změn v pracovním postupu.</span><span class="sxs-lookup"><span data-stu-id="b4696-175">Depending on your monitoring requirements, you can create a profile that is very coarse, which subscribes to a small set of high-level state changes on a workflow.</span></span> <span data-ttu-id="b4696-176">Na druhé straně můžete vytvořit profil velmi přesná, jejíž výstup je dostatečně bohaté k rekonstrukci spuštění později.</span><span class="sxs-lookup"><span data-stu-id="b4696-176">On the other hand, you can create a very precise profile whose output is rich enough to reconstruct the execution later.</span></span> <span data-ttu-id="b4696-177">Ukázka ukazuje události vygenerované z modulu runtime pracovního postupu pomocí trasování událostí pro Windows `HealthMonitoring Tracking Profile`, který vysílá malého událostí.</span><span class="sxs-lookup"><span data-stu-id="b4696-177">The sample demonstrates the events emitted from the workflow runtime to ETW using the `HealthMonitoring Tracking Profile`, which emits a small set of events.</span></span> <span data-ttu-id="b4696-178">Jiný profil, který vysílá další pracovního postupu pro sledování událostí je také součástí souboru Web.config, který je pojmenován `Troubleshooting Tracking Profile`.</span><span class="sxs-lookup"><span data-stu-id="b4696-178">A different profile that emits more workflow tracking events is also provided in the Web.config that is named `Troubleshooting Tracking Profile`.</span></span> <span data-ttu-id="b4696-179">Když [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] je nainstalovaná, výchozí profil s prázdným názvem je nakonfigurován v souboru Machine.config.</span><span class="sxs-lookup"><span data-stu-id="b4696-179">When the [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] is installed, a default profile with an empty name is configured in the Machine.config file.</span></span> <span data-ttu-id="b4696-180">Tento profil je používán trasování událostí pro Windows sledování Konfigurace chování, když je zadán žádný název profilu nebo název prázdný profil.</span><span class="sxs-lookup"><span data-stu-id="b4696-180">This profile is used by the ETW tracking behavior configuration when no profile name or an empty profile name is specified.</span></span>  
  
 <span data-ttu-id="b4696-181">Sledování profil sledování stavu vysílá záznamy instance pracovního postupu a záznamy šíření selhání aktivity.</span><span class="sxs-lookup"><span data-stu-id="b4696-181">The health monitoring tracking profile emits workflow instance records and activity fault propagation records.</span></span> <span data-ttu-id="b4696-182">Tento profil se vytváří přidáním následující profil sledování do konfiguračního souboru Web.config.</span><span class="sxs-lookup"><span data-stu-id="b4696-182">This profile is created by adding the following tracking profile to a Web.config configuration file.</span></span>  
  
```xml  
<<tracking>  
      <profiles>  
        <trackingProfile name="HealthMonitoring Tracking Profile">  
          <workflow activityDefinitionId="*">  
            <workflowInstanceQueries>  
              <workflowInstanceQuery>  
                <states>  
                  <state name="Started"/>  
                  <state name="Completed"/>  
                  <state name="Aborted"/>  
                  <state name="UnhandledException"/>  
                </states>  
            </workflowInstanceQuery>  
           </workflowInstanceQueries>  
            <faultPropagationQueries>  
              <faultPropagationQuery faultSourceActivityName ="*" faultHandlerActivityName="*"/>  
            </faultPropagationQueries>  
          </workflow>  
        </trackingProfile>  
       </profiles>  
</tracking>  
```  
  
 <span data-ttu-id="b4696-183">Profil můžete změnit změnou `EtwTrackingParticipant` konfigurace pro následující.</span><span class="sxs-lookup"><span data-stu-id="b4696-183">The profile can be changed by changing the `EtwTrackingParticipant` configuration to the following.</span></span>  
  
```xml  
<behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <etwTracking profileName="HealthMonitoring Tracking Profile"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
```  
  
#### <a name="to-clean-up-optional"></a><span data-ttu-id="b4696-184">Vyčistěte (volitelné)</span><span class="sxs-lookup"><span data-stu-id="b4696-184">To clean up (Optional)</span></span>  
  
1.  <span data-ttu-id="b4696-185">Otevřete Prohlížeč událostí.</span><span class="sxs-lookup"><span data-stu-id="b4696-185">Open Event Viewer.</span></span>  
  
2.  <span data-ttu-id="b4696-186">Přejděte na **Prohlížeč událostí**, **protokoly aplikací a služeb**, **Microsoft**, **Windows**, **aplikace Aplikace serveru**.</span><span class="sxs-lookup"><span data-stu-id="b4696-186">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="b4696-187">Klikněte pravým tlačítkem na **analytické** a vyberte **zakázat protokol**.</span><span class="sxs-lookup"><span data-stu-id="b4696-187">Right-click **Analytic** and select **Disable Log**.</span></span>  
  
3.  <span data-ttu-id="b4696-188">Přejděte na **Prohlížeč událostí**, **protokoly aplikací a služeb**, **Microsoft**, **Windows**, **aplikace Aplikace serveru**.</span><span class="sxs-lookup"><span data-stu-id="b4696-188">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="b4696-189">Klikněte pravým tlačítkem na **analytické** a vyberte **vymazat protokol**.</span><span class="sxs-lookup"><span data-stu-id="b4696-189">Right-click **Analytic** and select **Clear Log**.</span></span>  
  
4.  <span data-ttu-id="b4696-190">Vyberte **vymazat** možnost Vymazat události.</span><span class="sxs-lookup"><span data-stu-id="b4696-190">Choose the **Clear** option to clear the events.</span></span>  
  
## <a name="known-issue"></a><span data-ttu-id="b4696-191">Známý problém</span><span class="sxs-lookup"><span data-stu-id="b4696-191">Known Issue</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b4696-192">V prohlížeči událostí, kde může dojít k selhání dekódovat události trasování událostí není známý problém.</span><span class="sxs-lookup"><span data-stu-id="b4696-192">There is a known issue in the Event Viewer where it may fail to decode ETW events.</span></span> <span data-ttu-id="b4696-193">Může zobrazit chybovou zprávu, která vypadá takto.</span><span class="sxs-lookup"><span data-stu-id="b4696-193">You may see an error message that looks like the following.</span></span>  
>   
>  <span data-ttu-id="b4696-194">Popis k ID události \<id > ze zdroje aplikaci Microsoft Windows Server – aplikace nebyla nalezena.</span><span class="sxs-lookup"><span data-stu-id="b4696-194">The description for Event ID \<id> from source Microsoft-Windows-Application Server-Applications cannot be found.</span></span> <span data-ttu-id="b4696-195">Buď není nainstalována součást, který vyvolává tuto událost v místním počítači nebo je poškozená instalace.</span><span class="sxs-lookup"><span data-stu-id="b4696-195">Either the component that raises this event is not installed on your local computer or the installation is corrupted.</span></span> <span data-ttu-id="b4696-196">Můžete nainstalovat nebo opravit součásti v místním počítači.</span><span class="sxs-lookup"><span data-stu-id="b4696-196">You can install or repair the component on the local computer.</span></span>  
>   
>  <span data-ttu-id="b4696-197">Pokud dojde k této chybě, klikněte na tlačítko Aktualizovat v podokně Akce.</span><span class="sxs-lookup"><span data-stu-id="b4696-197">If you encounter this error, click refresh in the actions pane.</span></span> <span data-ttu-id="b4696-198">Události by měl nyní dekódovat správně.</span><span class="sxs-lookup"><span data-stu-id="b4696-198">The event should now decode properly.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b4696-199">Ukázky může být již nainstalován ve vašem počítači.</span><span class="sxs-lookup"><span data-stu-id="b4696-199">The samples may already be installed on your computer.</span></span> <span data-ttu-id="b4696-200">Před pokračováním zkontrolovat na následující adresář (výchozí).</span><span class="sxs-lookup"><span data-stu-id="b4696-200">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="b4696-201">Pokud tento adresář neexistuje, přejděte na [Windows Communication Foundation (WCF) a ukázky Windows Workflow Foundation (WF) pro rozhraní .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) ke stažení všechny [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] a [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ukázky.</span><span class="sxs-lookup"><span data-stu-id="b4696-201">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b4696-202">Tato ukázka se nachází v následujícím adresáři.</span><span class="sxs-lookup"><span data-stu-id="b4696-202">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\EtwTracking`  
  
## <a name="see-also"></a><span data-ttu-id="b4696-203">Viz také</span><span class="sxs-lookup"><span data-stu-id="b4696-203">See Also</span></span>  
 [<span data-ttu-id="b4696-204">Ukázky monitorování AppFabric</span><span class="sxs-lookup"><span data-stu-id="b4696-204">AppFabric Monitoring Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193959)
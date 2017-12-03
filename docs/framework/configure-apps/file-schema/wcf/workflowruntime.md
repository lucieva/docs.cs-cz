---
title: "&lt;modul runtime pracovního postupu&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 304c70fa-78d1-4d0f-b89f-0ca23d734c6f
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: db891e9d967f4471e2b0a3778db433adb62e121c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/02/2017
---
# <a name="ltworkflowruntimegt"></a><span data-ttu-id="46a59-102">&lt;modul runtime pracovního postupu&gt;</span><span class="sxs-lookup"><span data-stu-id="46a59-102">&lt;workflowRuntime&gt;</span></span>
<span data-ttu-id="46a59-103">Určuje nastavení pro instanci <xref:System.Workflow.Runtime.WorkflowRuntime> pro hostování založené na pracovním postupu [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] služby.</span><span class="sxs-lookup"><span data-stu-id="46a59-103">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] services.</span></span>  
  
 <span data-ttu-id="46a59-104">\<systém. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="46a59-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="46a59-105">\<chování ></span><span class="sxs-lookup"><span data-stu-id="46a59-105">\<behaviors></span></span>  
<span data-ttu-id="46a59-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="46a59-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="46a59-107">\<chování ></span><span class="sxs-lookup"><span data-stu-id="46a59-107">\<behavior></span></span>  
<span data-ttu-id="46a59-108">\<modul runtime pracovního postupu ></span><span class="sxs-lookup"><span data-stu-id="46a59-108">\<workflowRuntime></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46a59-109">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="46a59-109">Syntax</span></span>  
  
```xml  
<workflowRuntime cachedInstanceExpiration="TimeSpan"  
                                  enablePerformanceCounters="Boolean"  
                                  name="String"  
                                  validateOnCreate="Boolean">  
                 <commonParameters>  
                    <add name="String" value="String" />  
                 </commonParameters>  
                 <services>  
                    <add type="String"/>  
                 </services>  
</workflowRuntime>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="46a59-110">Atributy a elementy</span><span class="sxs-lookup"><span data-stu-id="46a59-110">Attributes and Elements</span></span>  
 <span data-ttu-id="46a59-111">Následující části popisují atributy, podřízené prvky a nadřazené prvky.</span><span class="sxs-lookup"><span data-stu-id="46a59-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="46a59-112">Atributy</span><span class="sxs-lookup"><span data-stu-id="46a59-112">Attributes</span></span>  
  
|<span data-ttu-id="46a59-113">Atribut</span><span class="sxs-lookup"><span data-stu-id="46a59-113">Attribute</span></span>|<span data-ttu-id="46a59-114">Popis</span><span class="sxs-lookup"><span data-stu-id="46a59-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="46a59-115">cachedInstanceExpiration</span><span class="sxs-lookup"><span data-stu-id="46a59-115">cachedInstanceExpiration</span></span>|<span data-ttu-id="46a59-116">Volitelný <xref:System.TimeSpan> hodnotu, která určuje maximální dobu trvání instanci pracovního postupu můžete zůstat v paměti ve stavu nečinnosti, než je vynuceně odpojeno nebo přerušena.</span><span class="sxs-lookup"><span data-stu-id="46a59-116">An optional <xref:System.TimeSpan> value that specifies the maximum duration a workflow instance can stay in-memory in idle state before it is forcefully unloaded or aborted.</span></span> <span data-ttu-id="46a59-117">Pokud modul runtime pracovního postupu má `PersistenceService` která provede unloadOnIdle, tento atribut je ignorován.</span><span class="sxs-lookup"><span data-stu-id="46a59-117">If the workflowruntime has `PersistenceService` which performs unloadOnIdle, this attribute is ignored.</span></span>|  
|<span data-ttu-id="46a59-118">enablePerformanceCounters</span><span class="sxs-lookup"><span data-stu-id="46a59-118">enablePerformanceCounters</span></span>|<span data-ttu-id="46a59-119">Volitelné logická hodnota, která určuje, zda jsou povoleny čítače výkonu.</span><span class="sxs-lookup"><span data-stu-id="46a59-119">An optional Boolean value that specifies whether performance counters are enabled.</span></span> <span data-ttu-id="46a59-120">Čítače výkonu poskytují informace o různé statistické údaje související s pracovního postupu, ale mohou způsobit snížení výkonu při spuštění modulu runtime pracovního postupu, a když jsou spuštěné instance pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="46a59-120">Performance counters provide information on various workflow-related statistics, but they cause a performance penalty when the workflow runtime engine starts, and when workflow instances are running.</span></span> <span data-ttu-id="46a59-121">Výchozí hodnota je `true`.</span><span class="sxs-lookup"><span data-stu-id="46a59-121">The default value is `true`.</span></span>|  
|<span data-ttu-id="46a59-122">name</span><span class="sxs-lookup"><span data-stu-id="46a59-122">name</span></span>|<span data-ttu-id="46a59-123">Řetězec, který obsahuje název modulu runtime pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="46a59-123">A string containing the name of the workflow runtime engine.</span></span> <span data-ttu-id="46a59-124">Název se používá ve výstupu k rozlišení tento modul runtime z jiné moduly runtime, který může běžet na systému, například ve čítače výkonu.</span><span class="sxs-lookup"><span data-stu-id="46a59-124">The name is used in output to distinguish this runtime from other runtimes that may be running on the system, for example, in performance counters.</span></span><br /><br /> <span data-ttu-id="46a59-125">Výchozí hodnota je prázdný řetězec.</span><span class="sxs-lookup"><span data-stu-id="46a59-125">The default is an empty string.</span></span>|  
|<span data-ttu-id="46a59-126">validateOnCreate</span><span class="sxs-lookup"><span data-stu-id="46a59-126">validateOnCreate</span></span>|<span data-ttu-id="46a59-127">Volitelné logická hodnota, která určuje, zda ověření definice pracovního postupu se stane, když je otevřen hostitele služby pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="46a59-127">An optional Boolean value that specifies whether validation of workflow definition will occur when the WorkflowServiceHost is opened.</span></span>  <span data-ttu-id="46a59-128">Když tento atribut je nastaven na `true`, ověření pracovního postupu se spustí pokaždé, když `WorkflowServiceHost.Open` je volána.</span><span class="sxs-lookup"><span data-stu-id="46a59-128">When this attribute is set to `true`, the workflow validation is executed every time `WorkflowServiceHost.Open` is called.</span></span> <span data-ttu-id="46a59-129">Pokud jsou zjištěny chyby ověřování, <xref:System.Workflow.ComponentModel.Compiler.WorkflowValidationFailedException> , je vržena chyba.</span><span class="sxs-lookup"><span data-stu-id="46a59-129">If validation errors are found, a <xref:System.Workflow.ComponentModel.Compiler.WorkflowValidationFailedException> error is thrown.</span></span><br /><br /> <span data-ttu-id="46a59-130">Pokud je tato vlastnost nastavená na `false`, se stane žádné ověření definice pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="46a59-130">When this property is set to `false`, no Workflow definition validation will happen.</span></span><br /><br /> <span data-ttu-id="46a59-131">Výchozí hodnota pro tuto vlastnost je `true`.</span><span class="sxs-lookup"><span data-stu-id="46a59-131">The default value for this property is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="46a59-132">Podřízené elementy</span><span class="sxs-lookup"><span data-stu-id="46a59-132">Child Elements</span></span>  
  
|<span data-ttu-id="46a59-133">Prvek</span><span class="sxs-lookup"><span data-stu-id="46a59-133">Element</span></span>|<span data-ttu-id="46a59-134">Popis</span><span class="sxs-lookup"><span data-stu-id="46a59-134">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="46a59-135">commonParameters</span><span class="sxs-lookup"><span data-stu-id="46a59-135">commonParameters</span></span>|<span data-ttu-id="46a59-136">Kolekce společných parametrů, které jsou používané službami.</span><span class="sxs-lookup"><span data-stu-id="46a59-136">A collection of common parameters used by services.</span></span> <span data-ttu-id="46a59-137">Tato kolekce bude obvykle obsahovat připojovací řetězec databáze, který může být sdílen trvalé služby.</span><span class="sxs-lookup"><span data-stu-id="46a59-137">This collection will typically include the database connection string that might be shared by durable services.</span></span>|  
|<span data-ttu-id="46a59-138">služby</span><span class="sxs-lookup"><span data-stu-id="46a59-138">services</span></span>|<span data-ttu-id="46a59-139">Kolekce služeb, které budou přidány do <xref:System.Workflow.Runtime.WorkflowRuntime> modul.</span><span class="sxs-lookup"><span data-stu-id="46a59-139">A collection of services that will be added to the <xref:System.Workflow.Runtime.WorkflowRuntime> engine.</span></span> <span data-ttu-id="46a59-140">Elementy jsou typu <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="46a59-140">The elements are of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  <span data-ttu-id="46a59-141">Služby uvedené v kolekci se inicializovat modul runtime pracovního postupu a přidat do jeho služby při odpovídající <xref:System.Workflow.Runtime.WorkflowRuntime> volání konstruktoru.</span><span class="sxs-lookup"><span data-stu-id="46a59-141">The services specified in the collection will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="46a59-142">Proto služby uvedené v kolekci musí následovat určitá pravidla o signatur jejich konstruktory.</span><span class="sxs-lookup"><span data-stu-id="46a59-142">Therefore, the services specified in the collection must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="46a59-143">Další informace naleznete v tématu <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="46a59-143">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="46a59-144">Nadřazené elementy</span><span class="sxs-lookup"><span data-stu-id="46a59-144">Parent Elements</span></span>  
  
|<span data-ttu-id="46a59-145">Prvek</span><span class="sxs-lookup"><span data-stu-id="46a59-145">Element</span></span>|<span data-ttu-id="46a59-146">Popis</span><span class="sxs-lookup"><span data-stu-id="46a59-146">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="46a59-147">\<chování ></span><span class="sxs-lookup"><span data-stu-id="46a59-147">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="46a59-148">Určuje chování element.</span><span class="sxs-lookup"><span data-stu-id="46a59-148">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="46a59-149">Poznámky</span><span class="sxs-lookup"><span data-stu-id="46a59-149">Remarks</span></span>  
 <span data-ttu-id="46a59-150">Další informace o použití konfiguračního souboru pro řízení chování <xref:System.Workflow.Runtime.WorkflowRuntime> objekt hostitele aplikace Windows Workflow Foundation, najdete v části [konfigurační soubory pracovního postupu](http://msdn.microsoft.com/en-us/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909).</span><span class="sxs-lookup"><span data-stu-id="46a59-150">For more information on using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](http://msdn.microsoft.com/en-us/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909).</span></span>  
  
## <a name="example"></a><span data-ttu-id="46a59-151">Příklad</span><span class="sxs-lookup"><span data-stu-id="46a59-151">Example</span></span>  
  
```xml  
<serviceBehaviors>  
   <behavior name="ServiceBehavior">  
      <workflowRuntime name="WorkflowServiceHostRuntime"  
                       validateOnCreate="true"  
                       enablePerformanceCounters="true">  
         <commonParameters>  
            <add name="ConnectionString" value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />  
            <add name="EnableRetries" value="True" />  
         </commonParameters>  
         <services>  
             <add type="NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common.TestPersistenceService.FilePersistenceService, NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common"/>  
         </services>  
      </workflowRuntime>  
   </behavior>  
</serviceBehaviors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="46a59-152">Viz také</span><span class="sxs-lookup"><span data-stu-id="46a59-152">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>  
 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>  
 <xref:System.Workflow.Runtime.WorkflowRuntime>  
 [<span data-ttu-id="46a59-153">Konfigurační soubory pracovního postupu</span><span class="sxs-lookup"><span data-stu-id="46a59-153">Workflow Configuration Files</span></span>](http://msdn.microsoft.com/en-us/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909)
---
title: "Události Trasování událostí pro Windows metod"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ETW, method events (CLR)
- method events [.NET Framework]
ms.assetid: 167a4459-bb6e-476c-9046-7920880f2bb5
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 353ae034381ab29787aba1c1c362f4c6fc57da7e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="method-etw-events"></a><span data-ttu-id="4feb2-102">Události Trasování událostí pro Windows metod</span><span class="sxs-lookup"><span data-stu-id="4feb2-102">Method ETW Events</span></span>
<span data-ttu-id="4feb2-103"><a name="top"></a>Tyto události shromažďovat informace, které jsou specifické pro metody.</span><span class="sxs-lookup"><span data-stu-id="4feb2-103"><a name="top"></a> These events collect information that is specific to methods.</span></span> <span data-ttu-id="4feb2-104">Datová část tyto události je vyžadována pro symbol řešení.</span><span class="sxs-lookup"><span data-stu-id="4feb2-104">The payload of these events is required for symbol resolution.</span></span> <span data-ttu-id="4feb2-105">Kromě toho tyto události poskytují užitečné informace, jako je počet pokusů, že byla volána metoda.</span><span class="sxs-lookup"><span data-stu-id="4feb2-105">In addition, these events provide helpful information such as the number of times a method was called.</span></span>  
  
 <span data-ttu-id="4feb2-106">Všechny události metoda mají úroveň "Informační (4)".</span><span class="sxs-lookup"><span data-stu-id="4feb2-106">All method events have a level of "Informational (4)".</span></span> <span data-ttu-id="4feb2-107">Všechny události podrobné metoda mít úrovní "Verbose (5)".</span><span class="sxs-lookup"><span data-stu-id="4feb2-107">All method verbose events have a level of "Verbose (5)".</span></span>  
  
 <span data-ttu-id="4feb2-108">Všechny události metod jsou vydané `JITKeyword` – klíčové slovo (0x10) nebo `NGenKeyword` – klíčové slovo (0x20) v rámci zprostředkovatele runtime, nebo `JitRundownKeyword` (0x10) nebo `NGENRundownKeyword` (0x20) v rámci sekvence daneho zprostředkovatele.</span><span class="sxs-lookup"><span data-stu-id="4feb2-108">All method events are raised by the `JITKeyword` (0x10) keyword or the `NGenKeyword` (0x20) keyword under the runtime provider, or `JitRundownKeyword` (0x10) or `NGENRundownKeyword` (0x20) under the rundown provider.</span></span>  
  
 <span data-ttu-id="4feb2-109">Události metod CLR dále dělí na následující:</span><span class="sxs-lookup"><span data-stu-id="4feb2-109">CLR method events are further subdivided into the following:</span></span>  
  
-   [<span data-ttu-id="4feb2-110">Události metod CLR</span><span class="sxs-lookup"><span data-stu-id="4feb2-110">CLR Method Events</span></span>](#clr_method_events)  
  
-   [<span data-ttu-id="4feb2-111">CLR – metoda značky události</span><span class="sxs-lookup"><span data-stu-id="4feb2-111">CLR Method Marker Events</span></span>](#clr_method_marker_events)  
  
-   [<span data-ttu-id="4feb2-112">Podrobné události CLR – metoda</span><span class="sxs-lookup"><span data-stu-id="4feb2-112">CLR Method Verbose Events</span></span>](#clr_method_verbose_events)  
  
-   [<span data-ttu-id="4feb2-113">MethodJittingStarted událostí</span><span class="sxs-lookup"><span data-stu-id="4feb2-113">MethodJittingStarted Event</span></span>](#methodjittingstarted_event)  
  
<a name="clr_method_events"></a>   
## <a name="clr-method-events"></a><span data-ttu-id="4feb2-114">Události metod CLR</span><span class="sxs-lookup"><span data-stu-id="4feb2-114">CLR Method Events</span></span>  
 <span data-ttu-id="4feb2-115">V následující tabulce jsou uvedeny – klíčové slovo a úroveň.</span><span class="sxs-lookup"><span data-stu-id="4feb2-115">The following table shows the keyword and level.</span></span> <span data-ttu-id="4feb2-116">(Další informace najdete v tématu [CLR ETW – klíčová slova a úrovně](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="4feb2-116">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="4feb2-117">– Klíčové slovo za vyvolání události</span><span class="sxs-lookup"><span data-stu-id="4feb2-117">Keyword for raising the event</span></span>|<span data-ttu-id="4feb2-118">úroveň</span><span class="sxs-lookup"><span data-stu-id="4feb2-118">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="4feb2-119">`JITKeyword`Poskytovatel modulu runtime (0x10)</span><span class="sxs-lookup"><span data-stu-id="4feb2-119">`JITKeyword` (0x10) runtime provider</span></span>|<span data-ttu-id="4feb2-120">Informativní (4)</span><span class="sxs-lookup"><span data-stu-id="4feb2-120">Informational (4)</span></span>|  
|<span data-ttu-id="4feb2-121">`NGenKeyword`Poskytovatel modulu runtime (0x20)</span><span class="sxs-lookup"><span data-stu-id="4feb2-121">`NGenKeyword` (0x20) runtime provider</span></span>|<span data-ttu-id="4feb2-122">Informativní (4)</span><span class="sxs-lookup"><span data-stu-id="4feb2-122">Informational (4)</span></span>|  
|<span data-ttu-id="4feb2-123">`JitRundownKeyword`sekvence daneho zprostředkovatele (0x10)</span><span class="sxs-lookup"><span data-stu-id="4feb2-123">`JitRundownKeyword` (0x10) rundown provider</span></span>|<span data-ttu-id="4feb2-124">Informativní (4)</span><span class="sxs-lookup"><span data-stu-id="4feb2-124">Informational (4)</span></span>|  
|<span data-ttu-id="4feb2-125">`NGENRundownKeyword`sekvence daneho zprostředkovatele (0x20)</span><span class="sxs-lookup"><span data-stu-id="4feb2-125">`NGENRundownKeyword` (0x20) rundown provider</span></span>|<span data-ttu-id="4feb2-126">Informativní (4)</span><span class="sxs-lookup"><span data-stu-id="4feb2-126">Informational (4)</span></span>|  
  
 <span data-ttu-id="4feb2-127">V následující tabulce jsou uvedeny informace o události.</span><span class="sxs-lookup"><span data-stu-id="4feb2-127">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="4feb2-128">Událost</span><span class="sxs-lookup"><span data-stu-id="4feb2-128">Event</span></span>|<span data-ttu-id="4feb2-129">ID události</span><span class="sxs-lookup"><span data-stu-id="4feb2-129">Event ID</span></span>|<span data-ttu-id="4feb2-130">Popis</span><span class="sxs-lookup"><span data-stu-id="4feb2-130">Description</span></span>|  
|-----------|--------------|-----------------|  
|`MethodLoad_V1`|<span data-ttu-id="4feb2-131">136</span><span class="sxs-lookup"><span data-stu-id="4feb2-131">136</span></span>|<span data-ttu-id="4feb2-132">Vyvolá, když metoda je v běhu načíst (JIT načíst) nebo bitovou kopii NGEN je načtena.</span><span class="sxs-lookup"><span data-stu-id="4feb2-132">Raised when a method is just-in-time loaded (JIT-loaded) or an NGEN image is loaded.</span></span> <span data-ttu-id="4feb2-133">Dynamické a obecné metody pro zatížení metoda nepoužívejte tuto verzi.</span><span class="sxs-lookup"><span data-stu-id="4feb2-133">Dynamic and generic methods do not use this version for method loads.</span></span> <span data-ttu-id="4feb2-134">Pomocníci JIT nikdy nepoužívejte tuto verzi.</span><span class="sxs-lookup"><span data-stu-id="4feb2-134">JIT helpers never use this version.</span></span>|  
|`MethodUnLoad_V1`|<span data-ttu-id="4feb2-135">137</span><span class="sxs-lookup"><span data-stu-id="4feb2-135">137</span></span>|<span data-ttu-id="4feb2-136">Vyvolá, když modul je odpojen nebo zničena domény aplikace.</span><span class="sxs-lookup"><span data-stu-id="4feb2-136">Raised when a module is unloaded, or an application domain is destroyed.</span></span> <span data-ttu-id="4feb2-137">Dynamické metody pro metoda uvolní nikdy nepoužívejte tuto verzi.</span><span class="sxs-lookup"><span data-stu-id="4feb2-137">Dynamic methods never use this version for method unloads.</span></span>|  
|`MethodDCStart_V1`|<span data-ttu-id="4feb2-138">137</span><span class="sxs-lookup"><span data-stu-id="4feb2-138">137</span></span>|<span data-ttu-id="4feb2-139">Vytvoří výčet metody během spuštění rundown.</span><span class="sxs-lookup"><span data-stu-id="4feb2-139">Enumerates methods during a start rundown.</span></span>|  
|`MethodDCEnd_V1`|<span data-ttu-id="4feb2-140">138</span><span class="sxs-lookup"><span data-stu-id="4feb2-140">138</span></span>|<span data-ttu-id="4feb2-141">Vytvoří výčet metod během rundown end.</span><span class="sxs-lookup"><span data-stu-id="4feb2-141">Enumerates methods during an end rundown.</span></span>|  
  
 <span data-ttu-id="4feb2-142">Následující tabulka zobrazuje data událostí.</span><span class="sxs-lookup"><span data-stu-id="4feb2-142">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="4feb2-143">Název pole</span><span class="sxs-lookup"><span data-stu-id="4feb2-143">Field name</span></span>|<span data-ttu-id="4feb2-144">Datový typ</span><span class="sxs-lookup"><span data-stu-id="4feb2-144">Data type</span></span>|<span data-ttu-id="4feb2-145">Popis</span><span class="sxs-lookup"><span data-stu-id="4feb2-145">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="4feb2-146">MethodID</span><span class="sxs-lookup"><span data-stu-id="4feb2-146">MethodID</span></span>|<span data-ttu-id="4feb2-147">Win: UInt64</span><span class="sxs-lookup"><span data-stu-id="4feb2-147">win:UInt64</span></span>|<span data-ttu-id="4feb2-148">Jedinečný identifikátor metody.</span><span class="sxs-lookup"><span data-stu-id="4feb2-148">Unique identifier of a method.</span></span> <span data-ttu-id="4feb2-149">Pro JIT pomocné metody je nastavena na adresu spuštění metody.</span><span class="sxs-lookup"><span data-stu-id="4feb2-149">For JIT helper methods, this is set to the start address of the method.</span></span>|  
|<span data-ttu-id="4feb2-150">ID modulu</span><span class="sxs-lookup"><span data-stu-id="4feb2-150">ModuleID</span></span>|<span data-ttu-id="4feb2-151">Win: UInt64</span><span class="sxs-lookup"><span data-stu-id="4feb2-151">win:UInt64</span></span>|<span data-ttu-id="4feb2-152">Identifikátor modulu, do které patří tato metoda (0 = Pomocníci JIT).</span><span class="sxs-lookup"><span data-stu-id="4feb2-152">Identifier of the module to which this method belongs (0 for JIT helpers).</span></span>|  
|<span data-ttu-id="4feb2-153">MethodStartAddress</span><span class="sxs-lookup"><span data-stu-id="4feb2-153">MethodStartAddress</span></span>|<span data-ttu-id="4feb2-154">Win: UInt64</span><span class="sxs-lookup"><span data-stu-id="4feb2-154">win:UInt64</span></span>|<span data-ttu-id="4feb2-155">Počáteční adresa metody.</span><span class="sxs-lookup"><span data-stu-id="4feb2-155">Start address of the method.</span></span>|  
|<span data-ttu-id="4feb2-156">MethodSize</span><span class="sxs-lookup"><span data-stu-id="4feb2-156">MethodSize</span></span>|<span data-ttu-id="4feb2-157">Win: UInt32</span><span class="sxs-lookup"><span data-stu-id="4feb2-157">win:UInt32</span></span>|<span data-ttu-id="4feb2-158">Velikost metody.</span><span class="sxs-lookup"><span data-stu-id="4feb2-158">Size of the method.</span></span>|  
|<span data-ttu-id="4feb2-159">MethodToken</span><span class="sxs-lookup"><span data-stu-id="4feb2-159">MethodToken</span></span>|<span data-ttu-id="4feb2-160">Win: UInt32</span><span class="sxs-lookup"><span data-stu-id="4feb2-160">win:UInt32</span></span>|<span data-ttu-id="4feb2-161">0 pro dynamických metod a JIT pomocné rutiny.</span><span class="sxs-lookup"><span data-stu-id="4feb2-161">0 for dynamic methods and JIT helpers.</span></span>|  
|<span data-ttu-id="4feb2-162">MethodFlags</span><span class="sxs-lookup"><span data-stu-id="4feb2-162">MethodFlags</span></span>|<span data-ttu-id="4feb2-163">Win: UInt32</span><span class="sxs-lookup"><span data-stu-id="4feb2-163">win:UInt32</span></span>|<span data-ttu-id="4feb2-164">0x1: dynamické metoda.</span><span class="sxs-lookup"><span data-stu-id="4feb2-164">0x1: Dynamic method.</span></span><br /><br /> <span data-ttu-id="4feb2-165">0x2: Obecné metody.</span><span class="sxs-lookup"><span data-stu-id="4feb2-165">0x2: Generic method.</span></span><br /><br /> <span data-ttu-id="4feb2-166">0x4: kompilována code – metoda (jinak NGEN nativních bitových kopií kód).</span><span class="sxs-lookup"><span data-stu-id="4feb2-166">0x4: JIT-compiled code method (otherwise NGEN native image code).</span></span><br /><br /> <span data-ttu-id="4feb2-167">0x8: Pomocná metoda.</span><span class="sxs-lookup"><span data-stu-id="4feb2-167">0x8: Helper method.</span></span>|  
|<span data-ttu-id="4feb2-168">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="4feb2-168">ClrInstanceID</span></span>|<span data-ttu-id="4feb2-169">Win: UInt16</span><span class="sxs-lookup"><span data-stu-id="4feb2-169">win:UInt16</span></span>|<span data-ttu-id="4feb2-170">Jedinečné ID pro instanci CLR nebo CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="4feb2-170">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="4feb2-171">Zpět na začátek</span><span class="sxs-lookup"><span data-stu-id="4feb2-171">Back to top</span></span>](#top)  
  
<a name="clr_method_marker_events"></a>   
## <a name="clr-method-marker-events"></a><span data-ttu-id="4feb2-172">CLR – metoda značky události</span><span class="sxs-lookup"><span data-stu-id="4feb2-172">CLR Method Marker Events</span></span>  
 <span data-ttu-id="4feb2-173">Tyto události jsou vyvolány pouze v rámci sekvence daneho zprostředkovatele.</span><span class="sxs-lookup"><span data-stu-id="4feb2-173">These events are raised only under the rundown provider.</span></span> <span data-ttu-id="4feb2-174">Jsou označují konec metoda výčtu při spuštění nebo ukončení rundown.</span><span class="sxs-lookup"><span data-stu-id="4feb2-174">They signify the end of method enumeration during a start or end rundown.</span></span> <span data-ttu-id="4feb2-175">(To znamená, že jsou vyvolány při `NGENRundownKeyword`, `JitRundownKeyword`, `LoaderRundownKeyword`, nebo `AppDomainResourceManagementRundownKeyword` – klíčové slovo je povolená.)</span><span class="sxs-lookup"><span data-stu-id="4feb2-175">(That is, they are raised when the `NGENRundownKeyword`, `JitRundownKeyword`, `LoaderRundownKeyword`, or `AppDomainResourceManagementRundownKeyword` keyword is enabled.)</span></span>  
  
 <span data-ttu-id="4feb2-176">V následující tabulce jsou uvedeny – klíčové slovo a úroveň.</span><span class="sxs-lookup"><span data-stu-id="4feb2-176">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="4feb2-177">– Klíčové slovo za vyvolání události</span><span class="sxs-lookup"><span data-stu-id="4feb2-177">Keyword for raising the event</span></span>|<span data-ttu-id="4feb2-178">úroveň</span><span class="sxs-lookup"><span data-stu-id="4feb2-178">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="4feb2-179">`AppDomainResourceManagementRundownKeyword`sekvence daneho zprostředkovatele (0x800)</span><span class="sxs-lookup"><span data-stu-id="4feb2-179">`AppDomainResourceManagementRundownKeyword` (0x800) rundown provider</span></span>|<span data-ttu-id="4feb2-180">Informativní (4)</span><span class="sxs-lookup"><span data-stu-id="4feb2-180">Informational (4)</span></span>|  
|<span data-ttu-id="4feb2-181">`JitRundownKeyword`sekvence daneho zprostředkovatele (0x10)</span><span class="sxs-lookup"><span data-stu-id="4feb2-181">`JitRundownKeyword` (0x10) rundown provider</span></span>|<span data-ttu-id="4feb2-182">Informativní (4)</span><span class="sxs-lookup"><span data-stu-id="4feb2-182">Informational (4)</span></span>|  
|<span data-ttu-id="4feb2-183">`NGENRundownKeyword`sekvence daneho zprostředkovatele (0x20)</span><span class="sxs-lookup"><span data-stu-id="4feb2-183">`NGENRundownKeyword` (0x20) rundown provider</span></span>|<span data-ttu-id="4feb2-184">Informativní (4)</span><span class="sxs-lookup"><span data-stu-id="4feb2-184">Informational (4)</span></span>|  
  
 <span data-ttu-id="4feb2-185">V následující tabulce jsou uvedeny informace o události.</span><span class="sxs-lookup"><span data-stu-id="4feb2-185">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="4feb2-186">Událost</span><span class="sxs-lookup"><span data-stu-id="4feb2-186">Event</span></span>|<span data-ttu-id="4feb2-187">ID události</span><span class="sxs-lookup"><span data-stu-id="4feb2-187">Event ID</span></span>|<span data-ttu-id="4feb2-188">Popis</span><span class="sxs-lookup"><span data-stu-id="4feb2-188">Desciption</span></span>|  
|-----------|--------------|----------------|  
|`DCStartInit_V1`|<span data-ttu-id="4feb2-189">147</span><span class="sxs-lookup"><span data-stu-id="4feb2-189">147</span></span>|<span data-ttu-id="4feb2-190">Odesílat před začátek výčtu během spuštění rundown.</span><span class="sxs-lookup"><span data-stu-id="4feb2-190">Sent before the start of the enumeration during a start rundown.</span></span>|  
|`DCStartComplete_V1`|<span data-ttu-id="4feb2-191">145</span><span class="sxs-lookup"><span data-stu-id="4feb2-191">145</span></span>|<span data-ttu-id="4feb2-192">Odeslat na konci výčtu během spuštění rundown.</span><span class="sxs-lookup"><span data-stu-id="4feb2-192">Sent at the end of the enumeration during a start rundown.</span></span>|  
|`DCEndInit_V1`|<span data-ttu-id="4feb2-193">148</span><span class="sxs-lookup"><span data-stu-id="4feb2-193">148</span></span>|<span data-ttu-id="4feb2-194">Odesílat před začátek výčtu během rundown end.</span><span class="sxs-lookup"><span data-stu-id="4feb2-194">Sent before the start of the enumeration during an end rundown.</span></span>|  
|`DCEndComplete_V1`|<span data-ttu-id="4feb2-195">146</span><span class="sxs-lookup"><span data-stu-id="4feb2-195">146</span></span>|<span data-ttu-id="4feb2-196">Odeslat na konci výčtu během rundown end.</span><span class="sxs-lookup"><span data-stu-id="4feb2-196">Sent at the end of the enumeration during an end rundown.</span></span>|  
  
 <span data-ttu-id="4feb2-197">Následující tabulka zobrazuje data událostí.</span><span class="sxs-lookup"><span data-stu-id="4feb2-197">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="4feb2-198">Název pole</span><span class="sxs-lookup"><span data-stu-id="4feb2-198">Field name</span></span>|<span data-ttu-id="4feb2-199">Datový typ</span><span class="sxs-lookup"><span data-stu-id="4feb2-199">Data type</span></span>|<span data-ttu-id="4feb2-200">Popis</span><span class="sxs-lookup"><span data-stu-id="4feb2-200">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="4feb2-201">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="4feb2-201">ClrInstanceID</span></span>|<span data-ttu-id="4feb2-202">Win: UInt16</span><span class="sxs-lookup"><span data-stu-id="4feb2-202">win:UInt16</span></span>|<span data-ttu-id="4feb2-203">Jedinečné ID pro instanci CLR nebo CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="4feb2-203">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="4feb2-204">Zpět na začátek</span><span class="sxs-lookup"><span data-stu-id="4feb2-204">Back to top</span></span>](#top)  
  
<a name="clr_method_verbose_events"></a>   
## <a name="clr-method-verbose-events"></a><span data-ttu-id="4feb2-205">Podrobné události CLR – metoda</span><span class="sxs-lookup"><span data-stu-id="4feb2-205">CLR Method Verbose Events</span></span>  
 <span data-ttu-id="4feb2-206">V následující tabulce jsou uvedeny – klíčové slovo a úroveň.</span><span class="sxs-lookup"><span data-stu-id="4feb2-206">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="4feb2-207">– Klíčové slovo za vyvolání události</span><span class="sxs-lookup"><span data-stu-id="4feb2-207">Keyword for raising the event</span></span>|<span data-ttu-id="4feb2-208">úroveň</span><span class="sxs-lookup"><span data-stu-id="4feb2-208">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="4feb2-209">`JITKeyword`Poskytovatel modulu runtime (0x10)</span><span class="sxs-lookup"><span data-stu-id="4feb2-209">`JITKeyword` (0x10) runtime provider</span></span>|<span data-ttu-id="4feb2-210">Verbose (5)</span><span class="sxs-lookup"><span data-stu-id="4feb2-210">Verbose (5)</span></span>|  
|<span data-ttu-id="4feb2-211">`NGenKeyword`Poskytovatel modulu runtime (0x20)</span><span class="sxs-lookup"><span data-stu-id="4feb2-211">`NGenKeyword` (0x20) runtime provider</span></span>|<span data-ttu-id="4feb2-212">Verbose (5)</span><span class="sxs-lookup"><span data-stu-id="4feb2-212">Verbose (5)</span></span>|  
|<span data-ttu-id="4feb2-213">`JitRundownKeyword`sekvence daneho zprostředkovatele (0x10)</span><span class="sxs-lookup"><span data-stu-id="4feb2-213">`JitRundownKeyword` (0x10) rundown provider</span></span>|<span data-ttu-id="4feb2-214">Verbose (5)</span><span class="sxs-lookup"><span data-stu-id="4feb2-214">Verbose (5)</span></span>|  
|<span data-ttu-id="4feb2-215">`NGENRundownKeyword`sekvence daneho zprostředkovatele (0x20)</span><span class="sxs-lookup"><span data-stu-id="4feb2-215">`NGENRundownKeyword` (0x20) rundown provider</span></span>|<span data-ttu-id="4feb2-216">Verbose (5)</span><span class="sxs-lookup"><span data-stu-id="4feb2-216">Verbose (5)</span></span>|  
  
 <span data-ttu-id="4feb2-217">V následující tabulce jsou uvedeny informace o události.</span><span class="sxs-lookup"><span data-stu-id="4feb2-217">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="4feb2-218">Událost</span><span class="sxs-lookup"><span data-stu-id="4feb2-218">Event</span></span>|<span data-ttu-id="4feb2-219">ID události</span><span class="sxs-lookup"><span data-stu-id="4feb2-219">Event ID</span></span>|<span data-ttu-id="4feb2-220">Popis</span><span class="sxs-lookup"><span data-stu-id="4feb2-220">Description</span></span>|  
|-----------|--------------|-----------------|  
|`MethodLoadVerbose_V1`|<span data-ttu-id="4feb2-221">143</span><span class="sxs-lookup"><span data-stu-id="4feb2-221">143</span></span>|<span data-ttu-id="4feb2-222">Vyvolá, když je metoda JIT načíst nebo bitovou kopii NGEN je načtena.</span><span class="sxs-lookup"><span data-stu-id="4feb2-222">Raised when a method is JIT-loaded or an NGEN image is loaded.</span></span> <span data-ttu-id="4feb2-223">Dynamické a obecné metody vždy v této verzi metoda zatížení.</span><span class="sxs-lookup"><span data-stu-id="4feb2-223">Dynamic and generic methods always use this version for method loads.</span></span> <span data-ttu-id="4feb2-224">Pomocníci JIT vždy používají tuto verzi.</span><span class="sxs-lookup"><span data-stu-id="4feb2-224">JIT helpers always use this version.</span></span>|  
|`MethodUnLoadVerbose_V1`|<span data-ttu-id="4feb2-225">144</span><span class="sxs-lookup"><span data-stu-id="4feb2-225">144</span></span>|<span data-ttu-id="4feb2-226">Vyvolá, když je zničen dynamické metody, modul je odpojen nebo zničena domény aplikace.</span><span class="sxs-lookup"><span data-stu-id="4feb2-226">Raised when a dynamic method is destroyed, a module is unloaded, or an application domain is destroyed.</span></span> <span data-ttu-id="4feb2-227">Dynamické metody vždy v této verzi metoda uvolní.</span><span class="sxs-lookup"><span data-stu-id="4feb2-227">Dynamic methods always use this version for method unloads.</span></span>|  
|`MethodDCStartVerbose_V1`|<span data-ttu-id="4feb2-228">141</span><span class="sxs-lookup"><span data-stu-id="4feb2-228">141</span></span>|<span data-ttu-id="4feb2-229">Vytvoří výčet metody během spuštění rundown.</span><span class="sxs-lookup"><span data-stu-id="4feb2-229">Enumerates methods during a start rundown.</span></span>|  
|`MethodDCEndVerbose_V1`|<span data-ttu-id="4feb2-230">142</span><span class="sxs-lookup"><span data-stu-id="4feb2-230">142</span></span>|<span data-ttu-id="4feb2-231">Vytvoří výčet metod během rundown end.</span><span class="sxs-lookup"><span data-stu-id="4feb2-231">Enumerates methods during an end rundown.</span></span>|  
  
 <span data-ttu-id="4feb2-232">Následující tabulka zobrazuje data událostí.</span><span class="sxs-lookup"><span data-stu-id="4feb2-232">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="4feb2-233">Název pole</span><span class="sxs-lookup"><span data-stu-id="4feb2-233">Field name</span></span>|<span data-ttu-id="4feb2-234">Datový typ</span><span class="sxs-lookup"><span data-stu-id="4feb2-234">Data type</span></span>|<span data-ttu-id="4feb2-235">Popis</span><span class="sxs-lookup"><span data-stu-id="4feb2-235">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="4feb2-236">MethodID</span><span class="sxs-lookup"><span data-stu-id="4feb2-236">MethodID</span></span>|<span data-ttu-id="4feb2-237">Win: UInt64</span><span class="sxs-lookup"><span data-stu-id="4feb2-237">win:UInt64</span></span>|<span data-ttu-id="4feb2-238">Jedinečný identifikátor metody.</span><span class="sxs-lookup"><span data-stu-id="4feb2-238">Unique identifier of the method.</span></span> <span data-ttu-id="4feb2-239">U metody helper JIT nastavte počáteční adresa metody.</span><span class="sxs-lookup"><span data-stu-id="4feb2-239">For JIT helper methods, set to the start address of the method.</span></span>|  
|<span data-ttu-id="4feb2-240">ID modulu</span><span class="sxs-lookup"><span data-stu-id="4feb2-240">ModuleID</span></span>|<span data-ttu-id="4feb2-241">Win: UInt64</span><span class="sxs-lookup"><span data-stu-id="4feb2-241">win:UInt64</span></span>|<span data-ttu-id="4feb2-242">Identifikátor modulu, do které patří tato metoda (0 = Pomocníci JIT).</span><span class="sxs-lookup"><span data-stu-id="4feb2-242">Identifier of the module to which this method belongs (0 for JIT helpers).</span></span>|  
|<span data-ttu-id="4feb2-243">MethodStartAddress</span><span class="sxs-lookup"><span data-stu-id="4feb2-243">MethodStartAddress</span></span>|<span data-ttu-id="4feb2-244">Win: UInt64</span><span class="sxs-lookup"><span data-stu-id="4feb2-244">win:UInt64</span></span>|<span data-ttu-id="4feb2-245">Počáteční adresa.</span><span class="sxs-lookup"><span data-stu-id="4feb2-245">Start address.</span></span>|  
|<span data-ttu-id="4feb2-246">MethodSize</span><span class="sxs-lookup"><span data-stu-id="4feb2-246">MethodSize</span></span>|<span data-ttu-id="4feb2-247">Win: UInt32</span><span class="sxs-lookup"><span data-stu-id="4feb2-247">win:UInt32</span></span>|<span data-ttu-id="4feb2-248">Metoda délka.</span><span class="sxs-lookup"><span data-stu-id="4feb2-248">Method length.</span></span>|  
|<span data-ttu-id="4feb2-249">MethodToken</span><span class="sxs-lookup"><span data-stu-id="4feb2-249">MethodToken</span></span>|<span data-ttu-id="4feb2-250">Win: UInt32</span><span class="sxs-lookup"><span data-stu-id="4feb2-250">win:UInt32</span></span>|<span data-ttu-id="4feb2-251">0 pro dynamických metod a JIT pomocné rutiny.</span><span class="sxs-lookup"><span data-stu-id="4feb2-251">0 for dynamic methods and JIT helpers.</span></span>|  
|<span data-ttu-id="4feb2-252">MethodFlags</span><span class="sxs-lookup"><span data-stu-id="4feb2-252">MethodFlags</span></span>|<span data-ttu-id="4feb2-253">Win: UInt32</span><span class="sxs-lookup"><span data-stu-id="4feb2-253">win:UInt32</span></span>|<span data-ttu-id="4feb2-254">0x1: dynamické metoda.</span><span class="sxs-lookup"><span data-stu-id="4feb2-254">0x1: Dynamic method.</span></span><br /><br /> <span data-ttu-id="4feb2-255">0x2: Obecné metody.</span><span class="sxs-lookup"><span data-stu-id="4feb2-255">0x2: Generic method.</span></span><br /><br /> <span data-ttu-id="4feb2-256">0x4: metoda kompilována (jinak, generovaný nástrojem NGen.exe)</span><span class="sxs-lookup"><span data-stu-id="4feb2-256">0x4: JIT-compiled method (otherwise, generated by NGen.exe)</span></span><br /><br /> <span data-ttu-id="4feb2-257">0x8: Pomocná metoda.</span><span class="sxs-lookup"><span data-stu-id="4feb2-257">0x8: Helper method.</span></span>|  
|<span data-ttu-id="4feb2-258">MethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="4feb2-258">MethodNameSpace</span></span>|<span data-ttu-id="4feb2-259">Win: UnicodeString</span><span class="sxs-lookup"><span data-stu-id="4feb2-259">win:UnicodeString</span></span>|<span data-ttu-id="4feb2-260">Název úplné oboru názvů přidružené k metodě.</span><span class="sxs-lookup"><span data-stu-id="4feb2-260">Full namespace name associated with the method.</span></span>|  
|<span data-ttu-id="4feb2-261">MethodName</span><span class="sxs-lookup"><span data-stu-id="4feb2-261">MethodName</span></span>|<span data-ttu-id="4feb2-262">Win: UnicodeString</span><span class="sxs-lookup"><span data-stu-id="4feb2-262">win:UnicodeString</span></span>|<span data-ttu-id="4feb2-263">Název úplné třídy přidružené k metodě.</span><span class="sxs-lookup"><span data-stu-id="4feb2-263">Full class name associated with the method.</span></span>|  
|<span data-ttu-id="4feb2-264">MethodSignature</span><span class="sxs-lookup"><span data-stu-id="4feb2-264">MethodSignature</span></span>|<span data-ttu-id="4feb2-265">Win: UnicodeString</span><span class="sxs-lookup"><span data-stu-id="4feb2-265">win:UnicodeString</span></span>|<span data-ttu-id="4feb2-266">Podpis metody (čárkami oddělený seznam názvů typu).</span><span class="sxs-lookup"><span data-stu-id="4feb2-266">Signature of the method (comma-separated list of type names).</span></span>|  
|<span data-ttu-id="4feb2-267">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="4feb2-267">ClrInstanceID</span></span>|<span data-ttu-id="4feb2-268">Win: UInt16</span><span class="sxs-lookup"><span data-stu-id="4feb2-268">win:UInt16</span></span>|<span data-ttu-id="4feb2-269">Jedinečné ID pro instanci CLR nebo CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="4feb2-269">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="4feb2-270">Zpět na začátek</span><span class="sxs-lookup"><span data-stu-id="4feb2-270">Back to top</span></span>](#top)  
  
<a name="methodjittingstarted_event"></a>   
## <a name="methodjittingstarted-event"></a><span data-ttu-id="4feb2-271">MethodJittingStarted událostí</span><span class="sxs-lookup"><span data-stu-id="4feb2-271">MethodJittingStarted Event</span></span>  
 <span data-ttu-id="4feb2-272">V následující tabulce jsou uvedeny – klíčové slovo a úroveň.</span><span class="sxs-lookup"><span data-stu-id="4feb2-272">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="4feb2-273">– Klíčové slovo za vyvolání události</span><span class="sxs-lookup"><span data-stu-id="4feb2-273">Keyword for raising the event</span></span>|<span data-ttu-id="4feb2-274">úroveň</span><span class="sxs-lookup"><span data-stu-id="4feb2-274">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="4feb2-275">`JITKeyword`Poskytovatel modulu runtime (0x10)</span><span class="sxs-lookup"><span data-stu-id="4feb2-275">`JITKeyword` (0x10) runtime provider</span></span>|<span data-ttu-id="4feb2-276">Verbose (5)</span><span class="sxs-lookup"><span data-stu-id="4feb2-276">Verbose (5)</span></span>|  
|<span data-ttu-id="4feb2-277">`NGenKeyword`Poskytovatel modulu runtime (0x20)</span><span class="sxs-lookup"><span data-stu-id="4feb2-277">`NGenKeyword` (0x20) runtime provider</span></span>|<span data-ttu-id="4feb2-278">Verbose (5)</span><span class="sxs-lookup"><span data-stu-id="4feb2-278">Verbose (5)</span></span>|  
|<span data-ttu-id="4feb2-279">`JitRundownKeyword`sekvence daneho zprostředkovatele (0x10)</span><span class="sxs-lookup"><span data-stu-id="4feb2-279">`JitRundownKeyword` (0x10) rundown provider</span></span>|<span data-ttu-id="4feb2-280">Verbose (5)</span><span class="sxs-lookup"><span data-stu-id="4feb2-280">Verbose (5)</span></span>|  
|<span data-ttu-id="4feb2-281">`NGENRundownKeyword`sekvence daneho zprostředkovatele (0x20)</span><span class="sxs-lookup"><span data-stu-id="4feb2-281">`NGENRundownKeyword` (0x20) rundown provider</span></span>|<span data-ttu-id="4feb2-282">Verbose (5)</span><span class="sxs-lookup"><span data-stu-id="4feb2-282">Verbose (5)</span></span>|  
  
 <span data-ttu-id="4feb2-283">V následující tabulce jsou uvedeny informace o události.</span><span class="sxs-lookup"><span data-stu-id="4feb2-283">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="4feb2-284">Událost</span><span class="sxs-lookup"><span data-stu-id="4feb2-284">Event</span></span>|<span data-ttu-id="4feb2-285">ID události</span><span class="sxs-lookup"><span data-stu-id="4feb2-285">Event ID</span></span>|<span data-ttu-id="4feb2-286">Popis</span><span class="sxs-lookup"><span data-stu-id="4feb2-286">Description</span></span>|  
|-----------|--------------|-----------------|  
|`MethodJittingStarted`|<span data-ttu-id="4feb2-287">145</span><span class="sxs-lookup"><span data-stu-id="4feb2-287">145</span></span>|<span data-ttu-id="4feb2-288">Vyvolá, když metoda, která má být kompilována.</span><span class="sxs-lookup"><span data-stu-id="4feb2-288">Raised when a method is being JIT-compiled.</span></span>|  
  
 <span data-ttu-id="4feb2-289">Následující tabulka zobrazuje data událostí.</span><span class="sxs-lookup"><span data-stu-id="4feb2-289">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="4feb2-290">Název pole</span><span class="sxs-lookup"><span data-stu-id="4feb2-290">Field name</span></span>|<span data-ttu-id="4feb2-291">Datový typ</span><span class="sxs-lookup"><span data-stu-id="4feb2-291">Data type</span></span>|<span data-ttu-id="4feb2-292">Popis</span><span class="sxs-lookup"><span data-stu-id="4feb2-292">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="4feb2-293">MethodID</span><span class="sxs-lookup"><span data-stu-id="4feb2-293">MethodID</span></span>|<span data-ttu-id="4feb2-294">Win: UInt64</span><span class="sxs-lookup"><span data-stu-id="4feb2-294">win:UInt64</span></span>|<span data-ttu-id="4feb2-295">Jedinečný identifikátor metody.</span><span class="sxs-lookup"><span data-stu-id="4feb2-295">Unique identifier of the method.</span></span>|  
|<span data-ttu-id="4feb2-296">ID modulu</span><span class="sxs-lookup"><span data-stu-id="4feb2-296">ModuleID</span></span>|<span data-ttu-id="4feb2-297">Win: UInt64</span><span class="sxs-lookup"><span data-stu-id="4feb2-297">win:UInt64</span></span>|<span data-ttu-id="4feb2-298">Identifikátor modulu, do které patří tato metoda.</span><span class="sxs-lookup"><span data-stu-id="4feb2-298">Identifier of the module to which this method belongs.</span></span>|  
|<span data-ttu-id="4feb2-299">MethodToken</span><span class="sxs-lookup"><span data-stu-id="4feb2-299">MethodToken</span></span>|<span data-ttu-id="4feb2-300">Win: UInt32</span><span class="sxs-lookup"><span data-stu-id="4feb2-300">win:UInt32</span></span>|<span data-ttu-id="4feb2-301">0 pro dynamických metod a JIT pomocné rutiny.</span><span class="sxs-lookup"><span data-stu-id="4feb2-301">0 for dynamic methods and JIT helpers.</span></span>|  
|<span data-ttu-id="4feb2-302">MethodILSize</span><span class="sxs-lookup"><span data-stu-id="4feb2-302">MethodILSize</span></span>|<span data-ttu-id="4feb2-303">Win: UInt32</span><span class="sxs-lookup"><span data-stu-id="4feb2-303">win:UInt32</span></span>|<span data-ttu-id="4feb2-304">Velikost Microsoft (MSIL intermediate language) pro metodu, která se kompilována.</span><span class="sxs-lookup"><span data-stu-id="4feb2-304">The size of the Microsoft intermediate language (MSIL) for the method that is being JIT-compiled.</span></span>|  
|<span data-ttu-id="4feb2-305">MethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="4feb2-305">MethodNameSpace</span></span>|<span data-ttu-id="4feb2-306">Win: UnicodeString</span><span class="sxs-lookup"><span data-stu-id="4feb2-306">win:UnicodeString</span></span>|<span data-ttu-id="4feb2-307">Název úplné třídy přidružené k metodě.</span><span class="sxs-lookup"><span data-stu-id="4feb2-307">Full class name associated with the method.</span></span>|  
|<span data-ttu-id="4feb2-308">MethodName</span><span class="sxs-lookup"><span data-stu-id="4feb2-308">MethodName</span></span>|<span data-ttu-id="4feb2-309">Win: UnicodeString</span><span class="sxs-lookup"><span data-stu-id="4feb2-309">win:UnicodeString</span></span>|<span data-ttu-id="4feb2-310">Název metody.</span><span class="sxs-lookup"><span data-stu-id="4feb2-310">Name of the method.</span></span>|  
|<span data-ttu-id="4feb2-311">MethodSignature</span><span class="sxs-lookup"><span data-stu-id="4feb2-311">MethodSignature</span></span>|<span data-ttu-id="4feb2-312">Win: UnicodeString</span><span class="sxs-lookup"><span data-stu-id="4feb2-312">win:UnicodeString</span></span>|<span data-ttu-id="4feb2-313">Podpis metody (čárkami oddělený seznam názvů typu).</span><span class="sxs-lookup"><span data-stu-id="4feb2-313">Signature of the method (comma-separated list of type names).</span></span>|  
|<span data-ttu-id="4feb2-314">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="4feb2-314">ClrInstanceID</span></span>|<span data-ttu-id="4feb2-315">Win: UInt16</span><span class="sxs-lookup"><span data-stu-id="4feb2-315">win:UInt16</span></span>|<span data-ttu-id="4feb2-316">Jedinečné ID pro instanci CLR nebo CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="4feb2-316">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4feb2-317">Viz také</span><span class="sxs-lookup"><span data-stu-id="4feb2-317">See Also</span></span>  
 [<span data-ttu-id="4feb2-318">CLR ETW – události</span><span class="sxs-lookup"><span data-stu-id="4feb2-318">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
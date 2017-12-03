---
title: "Latentní režimy"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- garbage collection, intrusiveness
- garbage collection, latency modes
ms.assetid: 96278bb7-6eab-4612-8594-ceebfc887d81
caps.latest.revision: "41"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 439fdd8fe78a0c0f0fda4ac7e759a4a780bb9b58
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="latency-modes"></a><span data-ttu-id="3e36c-102">Latentní režimy</span><span class="sxs-lookup"><span data-stu-id="3e36c-102">Latency Modes</span></span>
<span data-ttu-id="3e36c-103">Uvolnění objektů, musí uvolňování zastavení všech spuštěných vláken v aplikaci.</span><span class="sxs-lookup"><span data-stu-id="3e36c-103">To reclaim objects, the garbage collector must stop all the executing threads in an application.</span></span> <span data-ttu-id="3e36c-104">V některých situacích, například pokud aplikace načte data nebo se zobrazí obsah můžete na kritické čas úplné uvolnění paměti a mít dopad na výkon.</span><span class="sxs-lookup"><span data-stu-id="3e36c-104">In some situations, such as when an application retrieves data or displays content, a full garbage collection can occur at a critical time and impede performance.</span></span> <span data-ttu-id="3e36c-105">Míra interakce systému uvolňování můžete upravit podle nastavení <xref:System.Runtime.GCSettings.LatencyMode%2A?displayProperty=nameWithType> vlastnost na jednu z <xref:System.Runtime.GCLatencyMode?displayProperty=nameWithType> hodnoty.</span><span class="sxs-lookup"><span data-stu-id="3e36c-105">You can adjust the intrusiveness of the garbage collector by setting the <xref:System.Runtime.GCSettings.LatencyMode%2A?displayProperty=nameWithType> property to one of the <xref:System.Runtime.GCLatencyMode?displayProperty=nameWithType> values.</span></span>  
  
 <span data-ttu-id="3e36c-106">Latence odkazuje na čas, který má systém uvolňování intrudes ve vaší aplikaci.</span><span class="sxs-lookup"><span data-stu-id="3e36c-106">Latency refers to the time that the garbage collector intrudes in your application.</span></span> <span data-ttu-id="3e36c-107">Uvolňování paměti během období s nízkou latencí, je více konzervativní a šetrnější v opětovného získání objekty.</span><span class="sxs-lookup"><span data-stu-id="3e36c-107">During low latency periods, the garbage collector is more conservative and less intrusive in reclaiming objects.</span></span> <span data-ttu-id="3e36c-108"><xref:System.Runtime.GCLatencyMode?displayProperty=nameWithType> Výčtu poskytuje dvě nastavení s nízkou latencí:</span><span class="sxs-lookup"><span data-stu-id="3e36c-108">The <xref:System.Runtime.GCLatencyMode?displayProperty=nameWithType> enumeration provides two low latency settings:</span></span>  
  
-   <span data-ttu-id="3e36c-109"><xref:System.Runtime.GCLatencyMode.LowLatency>Potlačí 2. generace kolekce a provádí pouze kolekce, generace 0 a 1.</span><span class="sxs-lookup"><span data-stu-id="3e36c-109"><xref:System.Runtime.GCLatencyMode.LowLatency> suppresses generation 2 collections and performs only generation 0 and 1 collections.</span></span> <span data-ttu-id="3e36c-110">Lze pouze na krátkou dobu.</span><span class="sxs-lookup"><span data-stu-id="3e36c-110">It can be used only for short periods of time.</span></span> <span data-ttu-id="3e36c-111">Delší období Pokud systém je přetížena paměť, aktivují garbage collector v kolekci, která můžete stručně pozastavit aplikace a přerušit kritický pro čas operace.</span><span class="sxs-lookup"><span data-stu-id="3e36c-111">Over longer periods, if the system is under memory pressure, the garbage collector will trigger a collection, which can briefly pause the application and disrupt a time-critical operation.</span></span> <span data-ttu-id="3e36c-112">Toto nastavení je dostupné pouze pro uvolňování paměti pracovních stanic.</span><span class="sxs-lookup"><span data-stu-id="3e36c-112">This setting is available only for workstation garbage collection.</span></span>  
  
-   <span data-ttu-id="3e36c-113"><xref:System.Runtime.GCLatencyMode.SustainedLowLatency>Potlačí popředí 2. generace kolekce a provede jenom generace 0, 1, 2. generace kolekce pozadí.</span><span class="sxs-lookup"><span data-stu-id="3e36c-113"><xref:System.Runtime.GCLatencyMode.SustainedLowLatency> suppresses foreground generation 2 collections and performs only generation 0, 1, and background generation 2 collections.</span></span> <span data-ttu-id="3e36c-114">Lze použít pro delší časové období a je k dispozici pro uvolňování paměti serveru a pracovní stanice.</span><span class="sxs-lookup"><span data-stu-id="3e36c-114">It can be used for longer periods of time, and is available for both workstation and server garbage collection.</span></span> <span data-ttu-id="3e36c-115">Toto nastavení nelze použít, pokud [souběžné uvolňování](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) je zakázána.</span><span class="sxs-lookup"><span data-stu-id="3e36c-115">This setting cannot be used if [concurrent garbage collection](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) is disabled.</span></span>  
  
 <span data-ttu-id="3e36c-116">Během období s nízkou latencí jsou potlačovány 2. generace kolekce, pokud dojde k následujícímu:</span><span class="sxs-lookup"><span data-stu-id="3e36c-116">During low latency periods, generation 2 collections are suppressed unless the following occurs:</span></span>  
  
-   <span data-ttu-id="3e36c-117">Systém obdrží upozornění na nedostatek paměti z operačního systému.</span><span class="sxs-lookup"><span data-stu-id="3e36c-117">The system receives a low memory notification from the operating system.</span></span>  
  
-   <span data-ttu-id="3e36c-118">Kód aplikace indukuje kolekce voláním <xref:System.GC.Collect%2A?displayProperty=nameWithType> metoda a zadání 2 pro `generation` parametr.</span><span class="sxs-lookup"><span data-stu-id="3e36c-118">Your application code induces a collection by calling the <xref:System.GC.Collect%2A?displayProperty=nameWithType> method and specifying 2 for the `generation` parameter.</span></span>  
  
 <span data-ttu-id="3e36c-119">Následující tabulka uvádí scénáře aplikací pro použití <xref:System.Runtime.GCLatencyMode> hodnoty.</span><span class="sxs-lookup"><span data-stu-id="3e36c-119">The following table lists the application scenarios for using the <xref:System.Runtime.GCLatencyMode> values.</span></span>  
  
|<span data-ttu-id="3e36c-120">Latence režimu</span><span class="sxs-lookup"><span data-stu-id="3e36c-120">Latency mode</span></span>|<span data-ttu-id="3e36c-121">Scénáře aplikací</span><span class="sxs-lookup"><span data-stu-id="3e36c-121">Application scenarios</span></span>|  
|------------------|---------------------------|  
|<xref:System.Runtime.GCLatencyMode.Batch>|<span data-ttu-id="3e36c-122">Pro aplikace, které mají žádné uživatelské rozhraní nebo operací na straně serveru.</span><span class="sxs-lookup"><span data-stu-id="3e36c-122">For applications that have no UI or server-side operations.</span></span><br /><br /> <span data-ttu-id="3e36c-123">Toto je výchozí režim při [souběžné uvolňování](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) je zakázána.</span><span class="sxs-lookup"><span data-stu-id="3e36c-123">This is the default mode when [concurrent garbage collection](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) is disabled.</span></span>|  
|<xref:System.Runtime.GCLatencyMode.Interactive>|<span data-ttu-id="3e36c-124">Pro většinu aplikací, které mají uživatelského rozhraní.</span><span class="sxs-lookup"><span data-stu-id="3e36c-124">For most applications that have a UI.</span></span><br /><br /> <span data-ttu-id="3e36c-125">Toto je výchozí režim při [souběžné uvolňování](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) je povoleno.</span><span class="sxs-lookup"><span data-stu-id="3e36c-125">This is the default mode when [concurrent garbage collection](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) is enabled.</span></span>|  
|<xref:System.Runtime.GCLatencyMode.LowLatency>|<span data-ttu-id="3e36c-126">Pro aplikace, které mají krátkodobé může být rušivý operace citlivé na čas, během které přerušení z uvolňování paměti.</span><span class="sxs-lookup"><span data-stu-id="3e36c-126">For applications that have short-term, time-sensitive operations during which interruptions from the garbage collector could be disruptive.</span></span> <span data-ttu-id="3e36c-127">Například aplikace, které provádějí animace funkce pořízení vykreslování nebo data.</span><span class="sxs-lookup"><span data-stu-id="3e36c-127">For example, applications that do animation rendering or data acquisition functions.</span></span>|  
|<xref:System.Runtime.GCLatencyMode.SustainedLowLatency>|<span data-ttu-id="3e36c-128">Pro aplikace, které mají operace náročné na čas pro dobu trvání obsažené ale potenciálně delší dobu, během kterého může být rušivý přerušení z uvolňování paměti.</span><span class="sxs-lookup"><span data-stu-id="3e36c-128">For applications that have time-sensitive operations for a contained but potentially longer duration of time during which interruptions from the garbage collector could be disruptive.</span></span> <span data-ttu-id="3e36c-129">Například aplikace, které potřebují rychlý odezvy jako změny dat trhu obchodním dobu.</span><span class="sxs-lookup"><span data-stu-id="3e36c-129">For example, applications that need quick response times as market data changes during trading hours.</span></span><br /><br /> <span data-ttu-id="3e36c-130">Tento režim za následek větší velikost spravovaná halda než jiné režimy.</span><span class="sxs-lookup"><span data-stu-id="3e36c-130">This mode results in a larger managed heap size than other modes.</span></span> <span data-ttu-id="3e36c-131">Protože je komprimovat není spravovaná halda, je možné vyšší fragmentace.</span><span class="sxs-lookup"><span data-stu-id="3e36c-131">Because it does not compact the managed heap, higher fragmentation is possible.</span></span> <span data-ttu-id="3e36c-132">Ujistěte se, že je k dispozici dostatek paměti.</span><span class="sxs-lookup"><span data-stu-id="3e36c-132">Ensure that sufficient memory is available.</span></span>|  
  
## <a name="guidelines-for-using-low-latency"></a><span data-ttu-id="3e36c-133">Pokyny k používání s nízkou latencí</span><span class="sxs-lookup"><span data-stu-id="3e36c-133">Guidelines for Using Low Latency</span></span>  
 <span data-ttu-id="3e36c-134">Při použití <xref:System.Runtime.GCLatencyMode.LowLatency> režimu, vezměte v úvahu následující skutečnosti:</span><span class="sxs-lookup"><span data-stu-id="3e36c-134">When you use <xref:System.Runtime.GCLatencyMode.LowLatency> mode, consider the following guidelines:</span></span>  
  
-   <span data-ttu-id="3e36c-135">Doba, mějte s nízkou latencí co nejkratší.</span><span class="sxs-lookup"><span data-stu-id="3e36c-135">Keep the period of time in low latency as short as possible.</span></span>  
  
-   <span data-ttu-id="3e36c-136">Vyhněte se přidělování vysoké objemy paměti během období s nízkou latencí.</span><span class="sxs-lookup"><span data-stu-id="3e36c-136">Avoid allocating high amounts of memory during low latency periods.</span></span> <span data-ttu-id="3e36c-137">Nedostatek paměti oznámení může dojít, protože uvolňování paměti získá méně objektů.</span><span class="sxs-lookup"><span data-stu-id="3e36c-137">Low memory notifications can occur because garbage collection reclaims fewer objects.</span></span>  
  
-   <span data-ttu-id="3e36c-138">V režimu s nízkou latencí, Minimalizujte počet přidělení, které provedete v konkrétní přidělení do velkého objektu haldy a definovaného objekty.</span><span class="sxs-lookup"><span data-stu-id="3e36c-138">While in the low latency mode, minimize the number of allocations you make, in particular allocations onto the Large Object Heap and pinned objects.</span></span>  
  
-   <span data-ttu-id="3e36c-139">Uvědomte si, vláken, která by mohla být přidělení.</span><span class="sxs-lookup"><span data-stu-id="3e36c-139">Be aware of threads that could be allocating.</span></span> <span data-ttu-id="3e36c-140">Protože <xref:System.Runtime.GCSettings.LatencyMode%2A> je nastavení vlastnosti procesy, může způsobit <xref:System.OutOfMemoryException> na jakékoli vlákno, které může být přidělení.</span><span class="sxs-lookup"><span data-stu-id="3e36c-140">Because the <xref:System.Runtime.GCSettings.LatencyMode%2A> property setting is process-wide, you could generate an <xref:System.OutOfMemoryException> on any thread that may be allocating.</span></span>  
  
-   <span data-ttu-id="3e36c-141">Zalomení kód s nízkou latencí v omezené oblasti provádění (Další informace najdete v tématu [omezené oblasti provádění](../../../docs/framework/performance/constrained-execution-regions.md)).</span><span class="sxs-lookup"><span data-stu-id="3e36c-141">Wrap the low latency code in constrained execution regions (for more information, see [Constrained Execution Regions](../../../docs/framework/performance/constrained-execution-regions.md)).</span></span>  
  
-   <span data-ttu-id="3e36c-142">2. generace kolekce můžete vynutit během období s nízkou latencí při volání <xref:System.GC.Collect%28System.Int32%2CSystem.GCCollectionMode%29?displayProperty=nameWithType> metoda.</span><span class="sxs-lookup"><span data-stu-id="3e36c-142">You can force generation 2 collections during a low latency period by calling the <xref:System.GC.Collect%28System.Int32%2CSystem.GCCollectionMode%29?displayProperty=nameWithType> method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e36c-143">Viz také</span><span class="sxs-lookup"><span data-stu-id="3e36c-143">See Also</span></span>  
 <xref:System.GC?displayProperty=nameWithType>  
 [<span data-ttu-id="3e36c-144">Vyvolané kolekce</span><span class="sxs-lookup"><span data-stu-id="3e36c-144">Induced Collections</span></span>](../../../docs/standard/garbage-collection/induced.md)  
 [<span data-ttu-id="3e36c-145">Uvolňování paměti</span><span class="sxs-lookup"><span data-stu-id="3e36c-145">Garbage Collection</span></span>](../../../docs/standard/garbage-collection/index.md)
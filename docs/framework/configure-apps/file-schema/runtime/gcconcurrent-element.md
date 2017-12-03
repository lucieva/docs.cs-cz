---
title: "&lt;gcconcurrent –&gt; – Element"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcConcurrent
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcConcurrent
helpviewer_keywords:
- container tags, <gcConcurrent> element
- gcConcurrent element
- <gcConcurrent> element
ms.assetid: 503f55ba-26ed-45ac-a2ea-caf994da04cd
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c7ab16546ae85d1161f9e1323d74f17253edb7e5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="ltgcconcurrentgt-element"></a><span data-ttu-id="80180-102">&lt;gcconcurrent –&gt; – Element</span><span class="sxs-lookup"><span data-stu-id="80180-102">&lt;gcConcurrent&gt; Element</span></span>
<span data-ttu-id="80180-103">Určuje, zda modul common language runtime spuštěna uvolňování paměti na samostatné vlákno.</span><span class="sxs-lookup"><span data-stu-id="80180-103">Specifies whether the common language runtime runs garbage collection on a separate thread.</span></span>  
  
 <span data-ttu-id="80180-104">\<Konfigurace ></span><span class="sxs-lookup"><span data-stu-id="80180-104">\<configuration></span></span>  
<span data-ttu-id="80180-105">\<modul runtime ></span><span class="sxs-lookup"><span data-stu-id="80180-105">\<runtime></span></span>  
<span data-ttu-id="80180-106">\<gcconcurrent – ></span><span class="sxs-lookup"><span data-stu-id="80180-106">\<gcConcurrent></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80180-107">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="80180-107">Syntax</span></span>  
  
```xml  
<gcConcurrent    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="80180-108">Atributy a elementy</span><span class="sxs-lookup"><span data-stu-id="80180-108">Attributes and Elements</span></span>  
 <span data-ttu-id="80180-109">Následující části popisují atributy, podřízené prvky a nadřazené prvky.</span><span class="sxs-lookup"><span data-stu-id="80180-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="80180-110">Atributy</span><span class="sxs-lookup"><span data-stu-id="80180-110">Attributes</span></span>  
  
|<span data-ttu-id="80180-111">Atribut</span><span class="sxs-lookup"><span data-stu-id="80180-111">Attribute</span></span>|<span data-ttu-id="80180-112">Popis</span><span class="sxs-lookup"><span data-stu-id="80180-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="80180-113">Požadovaný atribut.</span><span class="sxs-lookup"><span data-stu-id="80180-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="80180-114">Určuje, zda modul runtime běží souběžně uvolňování paměti.</span><span class="sxs-lookup"><span data-stu-id="80180-114">Specifies whether the runtime runs garbage collection concurrently.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="80180-115">Atribut enabled</span><span class="sxs-lookup"><span data-stu-id="80180-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="80180-116">Hodnota</span><span class="sxs-lookup"><span data-stu-id="80180-116">Value</span></span>|<span data-ttu-id="80180-117">Popis</span><span class="sxs-lookup"><span data-stu-id="80180-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="80180-118">Současně nespouští uvolňování paměti.</span><span class="sxs-lookup"><span data-stu-id="80180-118">Does not run garbage collection concurrently.</span></span>|  
|`true`|<span data-ttu-id="80180-119">Uvolňování paměti běží souběžně.</span><span class="sxs-lookup"><span data-stu-id="80180-119">Runs garbage collection concurrently.</span></span> <span data-ttu-id="80180-120">Toto nastavení je výchozí.</span><span class="sxs-lookup"><span data-stu-id="80180-120">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="80180-121">Podřízené elementy</span><span class="sxs-lookup"><span data-stu-id="80180-121">Child Elements</span></span>  
 <span data-ttu-id="80180-122">Žádné</span><span class="sxs-lookup"><span data-stu-id="80180-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="80180-123">Nadřazené elementy</span><span class="sxs-lookup"><span data-stu-id="80180-123">Parent Elements</span></span>  
  
|<span data-ttu-id="80180-124">Prvek</span><span class="sxs-lookup"><span data-stu-id="80180-124">Element</span></span>|<span data-ttu-id="80180-125">Popis</span><span class="sxs-lookup"><span data-stu-id="80180-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="80180-126">Kořenový prvek v každém konfiguračním souboru, který je používán modulem Common Language Runtime (CLR) a aplikacemi rozhraní .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="80180-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="80180-127">Obsahuje informace o vazbách sestavení a uvolnění paměti.</span><span class="sxs-lookup"><span data-stu-id="80180-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="80180-128">Poznámky</span><span class="sxs-lookup"><span data-stu-id="80180-128">Remarks</span></span>  
 <span data-ttu-id="80180-129">Uvolňování paměti pracovních stanic před rozhraní .NET Framework 4 podporováno souběžné uvolňování paměti, která provádí uvolňování paměti na pozadí na samostatné vlákno.</span><span class="sxs-lookup"><span data-stu-id="80180-129">Prior to the .NET Framework 4, workstation garbage collection supported concurrent garbage collection, which performed garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="80180-130">V rozhraní .NET Framework 4 souběžné uvolňování nahradily pozadí globální Katalog, který také provádí uvolňování paměti na pozadí na samostatné vlákno.</span><span class="sxs-lookup"><span data-stu-id="80180-130">In the .NET Framework 4, concurrent garbage collection was replaced by background GC, which also performs garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="80180-131">Od verze rozhraní .NET Framework 4.5, pozadí kolekce jsou k dispozici v kolekce paměti na serveru.</span><span class="sxs-lookup"><span data-stu-id="80180-131">Starting with the .NET Framework 4.5, background collection became available in server garbage collection.</span></span> <span data-ttu-id="80180-132">`<gcConcurrent>` Element řídí, zda modul runtime provádí buď souběžných nebo na pozadí uvolňování paměti, pokud je k dispozici, nebo zda vykonává uvolňování paměti v popředí.</span><span class="sxs-lookup"><span data-stu-id="80180-132">The `<gcConcurrent>` element controls whether the runtime performs either concurrent or background garbage collection, if it is available, or whether it performs garbage collection in the foreground.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="80180-133">Počínaje rozhraním .NET Framework 4 je souběžné uvolňování paměti nahrazeno uvolňováním paměti na pozadí.</span><span class="sxs-lookup"><span data-stu-id="80180-133">Starting with the .NET Framework 4, concurrent garbage collection is replaced by background garbage collection.</span></span> <span data-ttu-id="80180-134">Podmínky *souběžných* a *pozadí* se zcela zaměnitelným významem používají v dokumentaci k rozhraní .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="80180-134">The terms *concurrent* and *background* are used interchangeably in the .NET Framework documentation.</span></span> <span data-ttu-id="80180-135">Chcete-li zakázat kolekce paměti na pozadí, použijte `<gcConcurrent>` elementu, jak je popsáno v tomto článku.</span><span class="sxs-lookup"><span data-stu-id="80180-135">To disable background garbage collection, use the `<gcConcurrent>` element, as discussed in this article.</span></span>  
  
 <span data-ttu-id="80180-136">Ve výchozím nastavení používá modul runtime souběžných nebo kolekce paměti na pozadí, která je optimalizovaná pro latenci.</span><span class="sxs-lookup"><span data-stu-id="80180-136">By default, the runtime uses concurrent or background garbage collection, which is optimized for latency.</span></span> <span data-ttu-id="80180-137">Pokud vaše aplikace zahrnuje interakce velkou uživatele, ponechejte souběžné uvolňování povoleno minimalizovat čas pozastavení aplikace k provedení uvolňování paměti.</span><span class="sxs-lookup"><span data-stu-id="80180-137">If your application involves heavy user interaction, leave concurrent garbage collection enabled to minimize the application's pause time to perform garbage collection.</span></span> <span data-ttu-id="80180-138">Pokud nastavíte `enabled` atribut `<gcConcurrent>` element `false`, modul runtime používá nesouběžného uvolňování paměti, která je optimalizovaná pro propustnost.</span><span class="sxs-lookup"><span data-stu-id="80180-138">If you set the `enabled` attribute of the `<gcConcurrent>` element to `false`, the runtime uses non-concurrent garbage collection, which is optimized for throughput.</span></span> <span data-ttu-id="80180-139">Následující konfigurační soubor zakáže kolekce paměti na pozadí.</span><span class="sxs-lookup"><span data-stu-id="80180-139">The following configuration file disables background garbage collection.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <gcConcurrent enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="80180-140">Pokud dojde `<gcConcurrentSetting>` nastavení v konfiguračním souboru počítače, definuje výchozí hodnota pro všechny aplikace rozhraní .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="80180-140">If there is a `<gcConcurrentSetting>` setting in the machine configuration file, it defines the default value for all .NET Framework applications.</span></span> <span data-ttu-id="80180-141">Nastavení počítače konfiguračního souboru přepíše nastavení konfiguračního souboru aplikace.</span><span class="sxs-lookup"><span data-stu-id="80180-141">The machine configuration file setting overrides the application configuration file setting.</span></span>  
  
 <span data-ttu-id="80180-142">Další informace o souběžných a kolekce paměti na pozadí, najdete v části "souběžné uvolňování paměti" v [základy uvolnění paměti](../../../../../docs/standard/garbage-collection/fundamentals.md) tématu.</span><span class="sxs-lookup"><span data-stu-id="80180-142">For more information on concurrent and background garbage collection, see the "Concurrent garbage collection" section in the [Fundamentals of Garbage Collection](../../../../../docs/standard/garbage-collection/fundamentals.md) topic.</span></span>  
  
## <a name="example"></a><span data-ttu-id="80180-143">Příklad</span><span class="sxs-lookup"><span data-stu-id="80180-143">Example</span></span>  
 <span data-ttu-id="80180-144">Následující příklad umožňuje souběžné uvolňování paměti.</span><span class="sxs-lookup"><span data-stu-id="80180-144">The following example enables concurrent garbage collection.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <gcConcurrent enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="80180-145">Viz také</span><span class="sxs-lookup"><span data-stu-id="80180-145">See Also</span></span>  
 [<span data-ttu-id="80180-146">Schéma nastavení běhového prostředí</span><span class="sxs-lookup"><span data-stu-id="80180-146">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="80180-147">Schéma konfiguračního souboru</span><span class="sxs-lookup"><span data-stu-id="80180-147">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="80180-148">Základy kolekce paměti</span><span class="sxs-lookup"><span data-stu-id="80180-148">Fundamentals of Garbage Collection</span></span>](../../../../../docs/standard/garbage-collection/fundamentals.md)
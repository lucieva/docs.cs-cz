---
title: "&lt;namedCaches&gt; – Element (nastavení mezipaměti)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- namedCaches element
- caching [.NET Framework], configuration
- <namedCaches> element
ms.assetid: 6bd4fbc5-55a6-4dc4-998b-cdcc7e023330
caps.latest.revision: "14"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: bdafddcb05dd50f059c9f6804573beec085a4a2a
ms.sourcegitcommit: d0f7646d67db5809cf43ff1d27b399a4020e8ee2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/25/2017
---
# <a name="ltnamedcachesgt-element-cache-settings"></a><span data-ttu-id="5cd18-102">&lt;namedCaches&gt; – Element (nastavení mezipaměti)</span><span class="sxs-lookup"><span data-stu-id="5cd18-102">&lt;namedCaches&gt; Element (Cache Settings)</span></span>
<span data-ttu-id="5cd18-103">Určuje kolekci nastavení konfigurace pro pojmenované <xref:System.Runtime.Caching.MemoryCache> instance.</span><span class="sxs-lookup"><span data-stu-id="5cd18-103">Specifies a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span> <span data-ttu-id="5cd18-104"><xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> Odkazuje vlastnost kolekce nastavení konfigurace z jedné nebo více `namedCaches` elementy konfiguračního souboru.</span><span class="sxs-lookup"><span data-stu-id="5cd18-104">The <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> property references the collection of configuration settings from one or more `namedCaches` elements of the configuration file.</span></span>  
  
 <span data-ttu-id="5cd18-105">\<Konfigurace ></span><span class="sxs-lookup"><span data-stu-id="5cd18-105">\<configuration></span></span>  
<span data-ttu-id="5cd18-106">\<System.Runtime.Caching – ></span><span class="sxs-lookup"><span data-stu-id="5cd18-106">\< system.runtime.caching></span></span>  
<span data-ttu-id="5cd18-107">\<memoryCache ></span><span class="sxs-lookup"><span data-stu-id="5cd18-107">\<memoryCache></span></span>  
<span data-ttu-id="5cd18-108">\<namedCaches ></span><span class="sxs-lookup"><span data-stu-id="5cd18-108">\<namedCaches></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cd18-109">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="5cd18-109">Syntax</span></span>  
  
```xml  
<namedCaches>  
  <add name="default"/>   
</namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="5cd18-110">Typ</span><span class="sxs-lookup"><span data-stu-id="5cd18-110">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5cd18-111">Atributy a elementy</span><span class="sxs-lookup"><span data-stu-id="5cd18-111">Attributes and Elements</span></span>  
 <span data-ttu-id="5cd18-112">Následující části popisují atributy, podřízené prvky a nadřazené prvky.</span><span class="sxs-lookup"><span data-stu-id="5cd18-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5cd18-113">Atributy</span><span class="sxs-lookup"><span data-stu-id="5cd18-113">Attributes</span></span>  
  
|<span data-ttu-id="5cd18-114">Atribut</span><span class="sxs-lookup"><span data-stu-id="5cd18-114">Attribute</span></span>|<span data-ttu-id="5cd18-115">Popis</span><span class="sxs-lookup"><span data-stu-id="5cd18-115">Description</span></span>|  
|---------------|-----------------|  
|`cacheMemoryLimitMegabytes`|<span data-ttu-id="5cd18-116">Celočíselná hodnota, která určuje maximální povolenou velikost v megabajtech, která instance <xref:System.Runtime.Caching.MemoryCache> můžete dosáhnout.</span><span class="sxs-lookup"><span data-stu-id="5cd18-116">An integer value that specifies the maximum allowable size, in megabytes, that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="5cd18-117">Výchozí hodnota je 0, což znamená, že heuristiky Automatická změna velikosti z <xref:System.Runtime.Caching.MemoryCache> třída se používá ve výchozím nastavení.</span><span class="sxs-lookup"><span data-stu-id="5cd18-117">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`name`|<span data-ttu-id="5cd18-118">Název mezipaměti.</span><span class="sxs-lookup"><span data-stu-id="5cd18-118">The name of the cache.</span></span>|  
|`physicalMemoryLimitPercentage`|<span data-ttu-id="5cd18-119">Celočíselná hodnota mezi 0 a 100 určující maximální procento paměti fyzicky nainstalovaném počítači, která mohou být spotřebovávána mezipaměti.</span><span class="sxs-lookup"><span data-stu-id="5cd18-119">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="5cd18-120">Výchozí hodnota je 0, což znamená, že heuristiky Automatická změna velikosti z <xref:System.Runtime.Caching.MemoryCache> třída se používá ve výchozím nastavení.</span><span class="sxs-lookup"><span data-stu-id="5cd18-120">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`pollingInterval`|<span data-ttu-id="5cd18-121">Hodnota, která určuje časový interval, po jejímž uplynutí implementace mezipaměti porovná aktuální zatížení paměti do paměti absolutní a na základě procenta omezení, které jsou nastavené pro instanci mezipaměti.</span><span class="sxs-lookup"><span data-stu-id="5cd18-121">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="5cd18-122">Tato hodnota je uvedeno ve formátu hh: mm".</span><span class="sxs-lookup"><span data-stu-id="5cd18-122">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5cd18-123">Podřízené elementy</span><span class="sxs-lookup"><span data-stu-id="5cd18-123">Child Elements</span></span>  
  
|<span data-ttu-id="5cd18-124">Prvek</span><span class="sxs-lookup"><span data-stu-id="5cd18-124">Element</span></span>|<span data-ttu-id="5cd18-125">Popis</span><span class="sxs-lookup"><span data-stu-id="5cd18-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5cd18-126">\<Přidat ></span><span class="sxs-lookup"><span data-stu-id="5cd18-126">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/add-element-for-namedcaches.md)|<span data-ttu-id="5cd18-127">Přidá pojmenované mezipaměti, aby `namedCaches` kolekci pro mezipaměť.</span><span class="sxs-lookup"><span data-stu-id="5cd18-127">Adds a named cache to the `namedCaches` collection for a memory cache.</span></span>|  
|[<span data-ttu-id="5cd18-128">\<Clear ></span><span class="sxs-lookup"><span data-stu-id="5cd18-128">\<clear></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md)|<span data-ttu-id="5cd18-129">Vymaže `namedCaches` kolekci pro mezipaměť.</span><span class="sxs-lookup"><span data-stu-id="5cd18-129">Clears the `namedCaches` collection for a memory cache.</span></span>|  
|[<span data-ttu-id="5cd18-130">\<Odebrat ></span><span class="sxs-lookup"><span data-stu-id="5cd18-130">\<remove></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/remove-element-for-namedcaches.md)|<span data-ttu-id="5cd18-131">Odebere položku s názvem mezipaměti z `namedCaches` kolekci pro mezipaměť.</span><span class="sxs-lookup"><span data-stu-id="5cd18-131">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5cd18-132">Nadřazené elementy</span><span class="sxs-lookup"><span data-stu-id="5cd18-132">Parent Elements</span></span>  
  
|<span data-ttu-id="5cd18-133">Prvek</span><span class="sxs-lookup"><span data-stu-id="5cd18-133">Element</span></span>|<span data-ttu-id="5cd18-134">Popis</span><span class="sxs-lookup"><span data-stu-id="5cd18-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5cd18-135">\<memoryCache ></span><span class="sxs-lookup"><span data-stu-id="5cd18-135">\<memoryCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)|<span data-ttu-id="5cd18-136">Definuje element, který slouží ke konfiguraci mezipaměti, který je založen na <xref:System.Runtime.Caching.MemoryCache> třídy.</span><span class="sxs-lookup"><span data-stu-id="5cd18-136">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5cd18-137">Poznámky</span><span class="sxs-lookup"><span data-stu-id="5cd18-137">Remarks</span></span>  
 <span data-ttu-id="5cd18-138">Oddíl konfigurace mezipaměti paměti souboru Web.config může obsahovat `add`, `remove`, a `clear` atributy pro `namedCaches` kolekce.</span><span class="sxs-lookup"><span data-stu-id="5cd18-138">The memory cache configuration section of the Web.config file can contain `add`, `remove`, and `clear` attributes for the `namedCaches` collection.</span></span> <span data-ttu-id="5cd18-139">Každý `namedCaches` položka je jedinečně identifikovaný `name` atribut.</span><span class="sxs-lookup"><span data-stu-id="5cd18-139">Each `namedCaches` entry is uniquely identified by the `name` attribute.</span></span>  
  
 <span data-ttu-id="5cd18-140">Instance položky mezipaměti paměti můžete načíst tak, že odkazy na informace v konfigurační soubory aplikace.</span><span class="sxs-lookup"><span data-stu-id="5cd18-140">You can retrieve instances of memory cache entries by referencing the information in the application configuration files.</span></span> <span data-ttu-id="5cd18-141">Ve výchozím nastavení pouze výchozí instance mezipaměti má záznam v konfiguračním souboru.</span><span class="sxs-lookup"><span data-stu-id="5cd18-141">By default, only the default cache instance has an entry in the configuration file.</span></span> <span data-ttu-id="5cd18-142">Výchozí instance mezipaměti je instanci, která je vrácena z <xref:System.Runtime.Caching.MemoryCache.Default%2A> vlastnost.</span><span class="sxs-lookup"><span data-stu-id="5cd18-142">The default cache instance is the instance that is returned from the <xref:System.Runtime.Caching.MemoryCache.Default%2A> property.</span></span>  
  
 <span data-ttu-id="5cd18-143">Pokud jste nastavili atribut názvu "Výchozí", element používá výchozí instanci mezipaměti paměti.</span><span class="sxs-lookup"><span data-stu-id="5cd18-143">If you set the name attribute to "default", the element uses the default memory cache instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5cd18-144">Příklad</span><span class="sxs-lookup"><span data-stu-id="5cd18-144">Example</span></span>  
 <span data-ttu-id="5cd18-145">Následující příklad ukazuje, jak nastavit název mezipaměti na výchozí název položky mezipaměti nastavením `name` atribut "Výchozí".</span><span class="sxs-lookup"><span data-stu-id="5cd18-145">The following example shows how to set the name of the cache to the default cache entry name by setting the `name` attribute to "default".</span></span>  
  
 <span data-ttu-id="5cd18-146">`cacheMemoryLimitMegabytes` Atribut a `physicalMemoryPercentage` atribut nastaveny na nulu.</span><span class="sxs-lookup"><span data-stu-id="5cd18-146">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryPercentage` attribute are set to zero.</span></span> <span data-ttu-id="5cd18-147">Nastavení těchto atributů na hodnotu nula znamená, že heuristiky Automatická změna velikosti z <xref:System.Runtime.Caching.MemoryCache> třída se používá.</span><span class="sxs-lookup"><span data-stu-id="5cd18-147">Setting these attributes to zero means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used.</span></span> <span data-ttu-id="5cd18-148">Implementace mezipaměti porovná aktuální zatížení paměti do paměti absolutní a na základě procenta omezení každé dvě minuty.</span><span class="sxs-lookup"><span data-stu-id="5cd18-148">The cache implementation compares the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
```xml  
<configuration>  
  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="default"   
               cacheMemoryLimitMegabytes="0"   
               physicalMemoryPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5cd18-149">Viz také</span><span class="sxs-lookup"><span data-stu-id="5cd18-149">See Also</span></span>  
 [<span data-ttu-id="5cd18-150">\<memoryCache > – Element (nastavení mezipaměti)</span><span class="sxs-lookup"><span data-stu-id="5cd18-150">\<memoryCache> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)
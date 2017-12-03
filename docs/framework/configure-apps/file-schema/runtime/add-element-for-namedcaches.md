---
title: "&lt;Přidat&gt; Element pro &lt;namedCaches&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- add element for <namedCaches>
- <add> element for <namedCaches>
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 0baafcb53bf79a25618dad56c2dcf1412e48624b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="ltaddgt-element-for-ltnamedcachesgt"></a><span data-ttu-id="12d3d-102">&lt;Přidat&gt; Element pro &lt;namedCaches&gt;</span><span class="sxs-lookup"><span data-stu-id="12d3d-102">&lt;add&gt; Element for &lt;namedCaches&gt;</span></span>
<span data-ttu-id="12d3d-103">Přidá `namedCache` položku s `namedCaches` kolekci pro mezipaměť.</span><span class="sxs-lookup"><span data-stu-id="12d3d-103">Adds a `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="12d3d-104">\<System.Runtime.Caching – ></span><span class="sxs-lookup"><span data-stu-id="12d3d-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="12d3d-105">\<memoryCache ></span><span class="sxs-lookup"><span data-stu-id="12d3d-105">\<memoryCache></span></span>  
<span data-ttu-id="12d3d-106">\<namedCaches ></span><span class="sxs-lookup"><span data-stu-id="12d3d-106">\<namedCaches></span></span>  
<span data-ttu-id="12d3d-107">\<Přidat ></span><span class="sxs-lookup"><span data-stu-id="12d3d-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12d3d-108">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="12d3d-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <add name="default" />  
      <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="12d3d-109">Typ</span><span class="sxs-lookup"><span data-stu-id="12d3d-109">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="12d3d-110">Atributy a elementy</span><span class="sxs-lookup"><span data-stu-id="12d3d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="12d3d-111">Následující části popisují atributy, podřízené prvky a nadřazené prvky.</span><span class="sxs-lookup"><span data-stu-id="12d3d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="12d3d-112">Atributy</span><span class="sxs-lookup"><span data-stu-id="12d3d-112">Attributes</span></span>  
  
|<span data-ttu-id="12d3d-113">Atribut</span><span class="sxs-lookup"><span data-stu-id="12d3d-113">Attribute</span></span>|<span data-ttu-id="12d3d-114">Popis</span><span class="sxs-lookup"><span data-stu-id="12d3d-114">Description</span></span>|  
|-|-|  
|`CacheMemoryLimitMegabytes`|<span data-ttu-id="12d3d-115">Celočíselná hodnota, která určuje maximální povolená velikost (v megabajtech), instanci <xref:System.Runtime.Caching.MemoryCache> můžete dosáhnout.</span><span class="sxs-lookup"><span data-stu-id="12d3d-115">An integer value that specifies the maximum allowed size (in megabytes) that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="12d3d-116">Výchozí hodnota je 0, což znamená, že <xref:System.Runtime.Caching.MemoryCache> heuristiky Automatická změna velikosti třídy se používají ve výchozím nastavení.</span><span class="sxs-lookup"><span data-stu-id="12d3d-116">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`Name`|<span data-ttu-id="12d3d-117">Název mezipaměti.</span><span class="sxs-lookup"><span data-stu-id="12d3d-117">The name of the cache.</span></span>|  
|`PhysicalMemoryLimitPercentage`|<span data-ttu-id="12d3d-118">Celočíselná hodnota mezi 0 a 100 určující maximální procento paměti fyzicky nainstalovaném počítači, která mohou být spotřebovávána mezipaměti.</span><span class="sxs-lookup"><span data-stu-id="12d3d-118">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="12d3d-119">Výchozí hodnota je 0, což znamená, že <xref:System.Runtime.Caching.MemoryCache> heuristiky Automatická změna velikosti třídy se používají ve výchozím nastavení.</span><span class="sxs-lookup"><span data-stu-id="12d3d-119">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`PollingInterval`|<span data-ttu-id="12d3d-120">Hodnota, která určuje časový interval, po jejímž uplynutí implementace mezipaměti porovná aktuální zatížení paměti do paměti absolutní a na základě procenta omezení, které jsou nastavené pro instanci mezipaměti.</span><span class="sxs-lookup"><span data-stu-id="12d3d-120">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="12d3d-121">Tato hodnota je uvedeno ve formátu hh: mm".</span><span class="sxs-lookup"><span data-stu-id="12d3d-121">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="12d3d-122">Podřízené elementy</span><span class="sxs-lookup"><span data-stu-id="12d3d-122">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="12d3d-123">Nadřazené elementy</span><span class="sxs-lookup"><span data-stu-id="12d3d-123">Parent Elements</span></span>  
  
|<span data-ttu-id="12d3d-124">Prvek</span><span class="sxs-lookup"><span data-stu-id="12d3d-124">Element</span></span>|<span data-ttu-id="12d3d-125">Popis</span><span class="sxs-lookup"><span data-stu-id="12d3d-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="12d3d-126">\<namedCaches ></span><span class="sxs-lookup"><span data-stu-id="12d3d-126">\<namedCaches></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|<span data-ttu-id="12d3d-127">Obsahuje kolekci nastavení konfigurace pro pojmenované <xref:System.Runtime.Caching.MemoryCache> instance.</span><span class="sxs-lookup"><span data-stu-id="12d3d-127">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="12d3d-128">Poznámky</span><span class="sxs-lookup"><span data-stu-id="12d3d-128">Remarks</span></span>  
 <span data-ttu-id="12d3d-129">`add` Element přidá položku do `namedCaches` kolekci pro mezipaměť.</span><span class="sxs-lookup"><span data-stu-id="12d3d-129">The `add` element adds an entry to the `namedCaches` collection for a memory cache.</span></span> <span data-ttu-id="12d3d-130">Můžete použít [vymazat](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md) element před použitím `add` elementu, který chcete být jisti, že neexistují žádné další s názvem mezipaměti v kolekci.</span><span class="sxs-lookup"><span data-stu-id="12d3d-130">You can use the [clear](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md) element before you use the `add` element to be certain that there are no other named caches in the collection.</span></span> <span data-ttu-id="12d3d-131">Tento element lze použít v souboru machine.config a v souboru Web.config.</span><span class="sxs-lookup"><span data-stu-id="12d3d-131">This element can be used in the machine.config file and in the Web.config file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="12d3d-132">Příklad</span><span class="sxs-lookup"><span data-stu-id="12d3d-132">Example</span></span>  
 <span data-ttu-id="12d3d-133">Následující příklad ukazuje, jak definovat nastavení pro výchozí `namedCache` položku na `namedCaches` kolekci pro mezipaměť.</span><span class="sxs-lookup"><span data-stu-id="12d3d-133">The following example shows how to define settings for the default `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="12d3d-134">Viz také</span><span class="sxs-lookup"><span data-stu-id="12d3d-134">See Also</span></span>  
 [<span data-ttu-id="12d3d-135">\<namedCaches > – Element (nastavení mezipaměti)</span><span class="sxs-lookup"><span data-stu-id="12d3d-135">\<namedCaches> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
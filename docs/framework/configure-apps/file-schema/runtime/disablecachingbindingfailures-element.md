---
title: "&lt;disablecachingbindingfailures –&gt; – Element"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#disableCachingBindingFailures
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/disableCachingBindingFailures
helpviewer_keywords:
- assemblies [.NET Framework],caching binding failures
- caching assembly binding failures
- <disableCachingBindingFailures> element
- disableCachingBindingFailures element
ms.assetid: bf598873-83b7-48de-8955-00b0504fbad0
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 25d504afd7945718f08dd5f2bf92d7ea33037a11
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="ltdisablecachingbindingfailuresgt-element"></a><span data-ttu-id="fa4c7-102">&lt;disablecachingbindingfailures –&gt; – Element</span><span class="sxs-lookup"><span data-stu-id="fa4c7-102">&lt;disableCachingBindingFailures&gt; Element</span></span>
<span data-ttu-id="fa4c7-103">Určuje, jestli chcete zakázat ukládání do mezipaměti vazby, ke kterým dochází, protože sestavení nebyl nalezen ve zjišťování.</span><span class="sxs-lookup"><span data-stu-id="fa4c7-103">Specifies whether to disable the caching of binding failures that occur because the assembly was not found by probing.</span></span>  
  
 <span data-ttu-id="fa4c7-104">\<Konfigurace > elementu</span><span class="sxs-lookup"><span data-stu-id="fa4c7-104">\<configuration> Element</span></span>  
<span data-ttu-id="fa4c7-105">\<modul runtime > elementu</span><span class="sxs-lookup"><span data-stu-id="fa4c7-105">\<runtime> Element</span></span>  
<span data-ttu-id="fa4c7-106">\<disablecachingbindingfailures – ></span><span class="sxs-lookup"><span data-stu-id="fa4c7-106">\<disableCachingBindingFailures></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa4c7-107">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="fa4c7-107">Syntax</span></span>  
  
```xml  
<disableCachingBindingFailures enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fa4c7-108">Atributy a elementy</span><span class="sxs-lookup"><span data-stu-id="fa4c7-108">Attributes and Elements</span></span>  
 <span data-ttu-id="fa4c7-109">Následující části popisují atributy, podřízené prvky a nadřazené prvky.</span><span class="sxs-lookup"><span data-stu-id="fa4c7-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fa4c7-110">Atributy</span><span class="sxs-lookup"><span data-stu-id="fa4c7-110">Attributes</span></span>  
  
|<span data-ttu-id="fa4c7-111">Atribut</span><span class="sxs-lookup"><span data-stu-id="fa4c7-111">Attribute</span></span>|<span data-ttu-id="fa4c7-112">Popis</span><span class="sxs-lookup"><span data-stu-id="fa4c7-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fa4c7-113">povoleno</span><span class="sxs-lookup"><span data-stu-id="fa4c7-113">enabled</span></span>|<span data-ttu-id="fa4c7-114">Požadovaný atribut.</span><span class="sxs-lookup"><span data-stu-id="fa4c7-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="fa4c7-115">Určuje, jestli chcete zakázat ukládání do mezipaměti vazby, ke kterým dochází, protože sestavení nebyl nalezen ve zjišťování.</span><span class="sxs-lookup"><span data-stu-id="fa4c7-115">Specifies whether to disable the caching of binding failures that occur because the assembly was not found by probing.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="fa4c7-116">Atribut enabled</span><span class="sxs-lookup"><span data-stu-id="fa4c7-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="fa4c7-117">Hodnota</span><span class="sxs-lookup"><span data-stu-id="fa4c7-117">Value</span></span>|<span data-ttu-id="fa4c7-118">Popis</span><span class="sxs-lookup"><span data-stu-id="fa4c7-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fa4c7-119">0</span><span class="sxs-lookup"><span data-stu-id="fa4c7-119">0</span></span>|<span data-ttu-id="fa4c7-120">Nezakazujte ukládání do mezipaměti vazby, ke kterým dochází, protože sestavení nebyl nalezen pomocí zjišťování.</span><span class="sxs-lookup"><span data-stu-id="fa4c7-120">Do not disable the caching of binding failures that occur because the assembly was not found by probing.</span></span> <span data-ttu-id="fa4c7-121">Toto je výchozí chování vazby od verze rozhraní .NET Framework verze 2.0.</span><span class="sxs-lookup"><span data-stu-id="fa4c7-121">This is the default binding behavior starting with the .NET Framework version 2.0.</span></span>|  
|<span data-ttu-id="fa4c7-122">1</span><span class="sxs-lookup"><span data-stu-id="fa4c7-122">1</span></span>|<span data-ttu-id="fa4c7-123">Zakážete ukládání do mezipaměti vazby, ke kterým dochází, protože sestavení nebyl nalezen pomocí zjišťování.</span><span class="sxs-lookup"><span data-stu-id="fa4c7-123">Disable the caching of binding failures that occur because the assembly was not found by probing.</span></span> <span data-ttu-id="fa4c7-124">Toto nastavení se vrátí do chování vazby rozhraní .NET Framework verze 1.1.</span><span class="sxs-lookup"><span data-stu-id="fa4c7-124">This setting reverts to the binding behavior of the .NET Framework version 1.1.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fa4c7-125">Podřízené elementy</span><span class="sxs-lookup"><span data-stu-id="fa4c7-125">Child Elements</span></span>  
 <span data-ttu-id="fa4c7-126">Žádné</span><span class="sxs-lookup"><span data-stu-id="fa4c7-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fa4c7-127">Nadřazené elementy</span><span class="sxs-lookup"><span data-stu-id="fa4c7-127">Parent Elements</span></span>  
  
|<span data-ttu-id="fa4c7-128">Prvek</span><span class="sxs-lookup"><span data-stu-id="fa4c7-128">Element</span></span>|<span data-ttu-id="fa4c7-129">Popis</span><span class="sxs-lookup"><span data-stu-id="fa4c7-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="fa4c7-130">Kořenový prvek v každém konfiguračním souboru, který je používán modulem Common Language Runtime (CLR) a aplikacemi rozhraní .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fa4c7-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="fa4c7-131">Obsahuje informace o vazbách sestavení a uvolnění paměti.</span><span class="sxs-lookup"><span data-stu-id="fa4c7-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa4c7-132">Poznámky</span><span class="sxs-lookup"><span data-stu-id="fa4c7-132">Remarks</span></span>  
 <span data-ttu-id="fa4c7-133">Od verze rozhraní .NET Framework verze 2.0, je výchozí chování pro načtení sestavení do mezipaměti všechny vazby a načítání selhání.</span><span class="sxs-lookup"><span data-stu-id="fa4c7-133">Starting with the .NET Framework version 2.0, the default behavior for loading assemblies is to cache all binding and loading failures.</span></span> <span data-ttu-id="fa4c7-134">To znamená pokud se nezdaří pokus o načtení sestavení, další žádost o načtení do stejného sestavení nezdaří okamžitě, bez jakékoli pokus o vyhledání sestavení.</span><span class="sxs-lookup"><span data-stu-id="fa4c7-134">That is, if an attempt to load an assembly fails, subsequent requests to load the same assembly fail immediately, without any attempt to locate the assembly.</span></span> <span data-ttu-id="fa4c7-135">Tento element zakáže výchozí chování pro vazby, ke kterým dochází, protože sestavení nebyl nalezen v cestě k testování.</span><span class="sxs-lookup"><span data-stu-id="fa4c7-135">This element disables that default behavior for binding failures that occur because the assembly could not be found in the probing path.</span></span> <span data-ttu-id="fa4c7-136">Throw – selhání <xref:System.IO.FileNotFoundException>.</span><span class="sxs-lookup"><span data-stu-id="fa4c7-136">These failures throw <xref:System.IO.FileNotFoundException>.</span></span>  
  
 <span data-ttu-id="fa4c7-137">Některé vazby a načítání selhání nemá vliv tohoto elementu a vždy v mezipaměti.</span><span class="sxs-lookup"><span data-stu-id="fa4c7-137">Some binding and loading failures are not affected by this element, and are always cached.</span></span> <span data-ttu-id="fa4c7-138">Selhání dojít, protože sestavení nebyl nalezen, ale nebylo možné načíst.</span><span class="sxs-lookup"><span data-stu-id="fa4c7-138">These failures occur because the assembly was found but could not be loaded.</span></span> <span data-ttu-id="fa4c7-139">Vyvolají <xref:System.BadImageFormatException> nebo <xref:System.IO.FileLoadException>.</span><span class="sxs-lookup"><span data-stu-id="fa4c7-139">They throw <xref:System.BadImageFormatException> or <xref:System.IO.FileLoadException>.</span></span> <span data-ttu-id="fa4c7-140">Následující seznam obsahuje některé příklady takových selhání.</span><span class="sxs-lookup"><span data-stu-id="fa4c7-140">The following list includes some examples of such failures.</span></span>  
  
-   <span data-ttu-id="fa4c7-141">Když se pokusí načíst soubor není platným sestavením, následných pokusů o načtení sestavení selže i v případě chybného souboru se nahradí správná sestavení.</span><span class="sxs-lookup"><span data-stu-id="fa4c7-141">If you attempt to load a file is not a valid assembly, subsequent attempts to load the assembly will fail even if the bad file is replaced with the correct assembly.</span></span>  
  
-   <span data-ttu-id="fa4c7-142">Při pokusu o načtení sestavení, které je uzamčený systému souborů následné pokusy o načtení sestavení selže i po vydání sestavení pomocí systému souborů.</span><span class="sxs-lookup"><span data-stu-id="fa4c7-142">If you attempt to load an assembly that is locked by the file system, subsequent attempts to load the assembly will fail even after the assembly is released by the file system.</span></span>  
  
-   <span data-ttu-id="fa4c7-143">Pokud je jeden nebo více verzí sestavení, které se pokoušíte načíst v cestě k testování, ale není mezi nimi konkrétní verzi, kterou jste požádali, následné pokusy o spouštění této verze selže i v případě správnou verzi přesunete do testování cestu.</span><span class="sxs-lookup"><span data-stu-id="fa4c7-143">If one or more versions of the assembly that you are attempting to load is in the probing path, but the specific version you are requesting is not among them, subsequent attempts to load that version will fail even if the correct version is moved into the probing path.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa4c7-144">Příklad</span><span class="sxs-lookup"><span data-stu-id="fa4c7-144">Example</span></span>  
 <span data-ttu-id="fa4c7-145">Následující příklad ukazuje, jak zakázat ukládání do mezipaměti selhání vazby sestavení, ke kterým dochází, protože sestavení nebyl nalezen pomocí zjišťování.</span><span class="sxs-lookup"><span data-stu-id="fa4c7-145">The following example shows how to disable the caching of assembly binding failures that occur because the assembly was not found by probing.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableCachingBindingFailures enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fa4c7-146">Viz také</span><span class="sxs-lookup"><span data-stu-id="fa4c7-146">See Also</span></span>  
 [<span data-ttu-id="fa4c7-147">Schéma nastavení běhového prostředí</span><span class="sxs-lookup"><span data-stu-id="fa4c7-147">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="fa4c7-148">Schéma konfiguračního souboru</span><span class="sxs-lookup"><span data-stu-id="fa4c7-148">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="fa4c7-149">Jak běhové prostředí vyhledává sestavení</span><span class="sxs-lookup"><span data-stu-id="fa4c7-149">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
---
title: "&lt;assemblybinding –&gt; Element pro &lt;modulu runtime&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding
helpviewer_keywords:
- <assemblyBinding> element
- assemblyBinding element
- container tags, <assemblyBinding> element
ms.assetid: 964cbb35-ab49-4498-8471-209689e5dada
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fdf2bc90c496c9906b5d31bad0065e01bdb47942
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="ltassemblybindinggt-element-for-ltruntimegt"></a><span data-ttu-id="a8e9d-102">&lt;assemblybinding –&gt; Element pro &lt;modulu runtime&gt;</span><span class="sxs-lookup"><span data-stu-id="a8e9d-102">&lt;assemblyBinding&gt; Element for &lt;runtime&gt;</span></span>
<span data-ttu-id="a8e9d-103">Obsahuje informace o přesměrování verze sestavení a umístění sestavení.</span><span class="sxs-lookup"><span data-stu-id="a8e9d-103">Contains information about assembly version redirection and the locations of assemblies.</span></span>  
  
 <span data-ttu-id="a8e9d-104">\<Konfigurace ></span><span class="sxs-lookup"><span data-stu-id="a8e9d-104">\<configuration></span></span>  
<span data-ttu-id="a8e9d-105">\<modul runtime ></span><span class="sxs-lookup"><span data-stu-id="a8e9d-105">\<runtime></span></span>  
<span data-ttu-id="a8e9d-106">\<assemblybinding – ></span><span class="sxs-lookup"><span data-stu-id="a8e9d-106">\<assemblyBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8e9d-107">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="a8e9d-107">Syntax</span></span>  
  
```xml  
      <assemblyBinding    
   xmlns="urn:schemas-microsoft-com:asm.v1" appliesTo="v1.0.3705">  
</assemblyBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a8e9d-108">Atributy a elementy</span><span class="sxs-lookup"><span data-stu-id="a8e9d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a8e9d-109">Následující části popisují atributy, podřízené prvky a nadřazené prvky.</span><span class="sxs-lookup"><span data-stu-id="a8e9d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a8e9d-110">Atributy</span><span class="sxs-lookup"><span data-stu-id="a8e9d-110">Attributes</span></span>  
  
|<span data-ttu-id="a8e9d-111">Atribut</span><span class="sxs-lookup"><span data-stu-id="a8e9d-111">Attribute</span></span>|<span data-ttu-id="a8e9d-112">Popis</span><span class="sxs-lookup"><span data-stu-id="a8e9d-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a8e9d-113">**atribut xmlns**</span><span class="sxs-lookup"><span data-stu-id="a8e9d-113">**xmlns**</span></span>|<span data-ttu-id="a8e9d-114">Požadovaný atribut.</span><span class="sxs-lookup"><span data-stu-id="a8e9d-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="a8e9d-115">Určuje obor názvů XML, které jsou potřebné pro sestavení – vazby.</span><span class="sxs-lookup"><span data-stu-id="a8e9d-115">Specifies the XML namespace required for assembly binding.</span></span> <span data-ttu-id="a8e9d-116">Použít řetězec "urn: schémata-microsoft-com:asm.v1" jako hodnotu.</span><span class="sxs-lookup"><span data-stu-id="a8e9d-116">Use the string "urn:schemas-microsoft-com:asm.v1" as the value.</span></span>|  
|<span data-ttu-id="a8e9d-117">**AppliesTo –**</span><span class="sxs-lookup"><span data-stu-id="a8e9d-117">**appliesTo**</span></span>|<span data-ttu-id="a8e9d-118">Určuje přesměrování sestavení rozhraní .NET Framework se vztahuje na verzi modulu runtime.</span><span class="sxs-lookup"><span data-stu-id="a8e9d-118">Specifies the runtime version the .NET Framework assembly redirection applies to.</span></span> <span data-ttu-id="a8e9d-119">Tento volitelný atribut používá označíte, jaká verze se vztahuje na číslo verze rozhraní .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a8e9d-119">This optional attribute uses a .NET Framework version number to indicate what version it applies to.</span></span> <span data-ttu-id="a8e9d-120">Pokud žádné **AppliesTo –** atribut zadán,  **\<assemblybinding – >** element platí pro všechny verze rozhraní .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a8e9d-120">If no **appliesTo** attribute is specified, the **\<assemblyBinding>** element applies to all versions of the .NET Framework.</span></span> <span data-ttu-id="a8e9d-121">**AppliesTo –** atribut byla zavedena v rozhraní .NET Framework verze 1.1; je ignorován v rozhraní .NET Framework verze 1.0.</span><span class="sxs-lookup"><span data-stu-id="a8e9d-121">The **appliesTo** attribute was introduced in .NET Framework version 1.1; it is ignored by the .NET Framework version 1.0.</span></span> <span data-ttu-id="a8e9d-122">To znamená, že všechny  **\<assemblybinding – >** prvky se použijí při použití rozhraní .NET Framework verze 1.0, i když **AppliesTo –** zadán atribut.</span><span class="sxs-lookup"><span data-stu-id="a8e9d-122">This means that all **\<assemblyBinding>** elements are applied when using the .NET Framework version 1.0, even if an **appliesTo** attribute is specified.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a8e9d-123">Podřízené elementy</span><span class="sxs-lookup"><span data-stu-id="a8e9d-123">Child Elements</span></span>  
  
|<span data-ttu-id="a8e9d-124">Prvek</span><span class="sxs-lookup"><span data-stu-id="a8e9d-124">Element</span></span>|<span data-ttu-id="a8e9d-125">Popis</span><span class="sxs-lookup"><span data-stu-id="a8e9d-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a8e9d-126">\<dependentAssembly ></span><span class="sxs-lookup"><span data-stu-id="a8e9d-126">\<dependentAssembly></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/dependentassembly-element.md)|<span data-ttu-id="a8e9d-127">Zapouzdří vazby zásady a sestavení umístění pro sestavení.</span><span class="sxs-lookup"><span data-stu-id="a8e9d-127">Encapsulates binding policy and assembly location for an assembly.</span></span> <span data-ttu-id="a8e9d-128">Použijte jednu  **\<dependentAssembly >** značky pro každé sestavení.</span><span class="sxs-lookup"><span data-stu-id="a8e9d-128">Use one **\<dependentAssembly>** tag for each assembly.</span></span>|  
|[<span data-ttu-id="a8e9d-129">\<Zkušební fáze ></span><span class="sxs-lookup"><span data-stu-id="a8e9d-129">\<probing></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md)|<span data-ttu-id="a8e9d-130">Určuje podadresáře modul common language runtime vyhledá při načítání sestavení.</span><span class="sxs-lookup"><span data-stu-id="a8e9d-130">Specifies subdirectories the common language runtime searches when loading assemblies.</span></span>|  
|[<span data-ttu-id="a8e9d-131">\<publisherPolicy ></span><span class="sxs-lookup"><span data-stu-id="a8e9d-131">\<publisherPolicy></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md)|<span data-ttu-id="a8e9d-132">Určuje, zda modul runtime aplikuje zásady vydavatele.</span><span class="sxs-lookup"><span data-stu-id="a8e9d-132">Specifies whether the runtime applies publisher policy.</span></span>|  
|[<span data-ttu-id="a8e9d-133">\<qualifyassembly – ></span><span class="sxs-lookup"><span data-stu-id="a8e9d-133">\<qualifyAssembly></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/qualifyassembly-element.md)|<span data-ttu-id="a8e9d-134">Určuje úplný název sestavení, které by měl být dynamicky načíst, pokud je použít částečný název.</span><span class="sxs-lookup"><span data-stu-id="a8e9d-134">Specifies the full name of the assembly that should be dynamically loaded when a partial name is used.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a8e9d-135">Nadřazené elementy</span><span class="sxs-lookup"><span data-stu-id="a8e9d-135">Parent Elements</span></span>  
  
|<span data-ttu-id="a8e9d-136">Prvek</span><span class="sxs-lookup"><span data-stu-id="a8e9d-136">Element</span></span>|<span data-ttu-id="a8e9d-137">Popis</span><span class="sxs-lookup"><span data-stu-id="a8e9d-137">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a8e9d-138">Kořenový prvek v každém konfiguračním souboru, který je používán modulem Common Language Runtime (CLR) a aplikacemi rozhraní .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a8e9d-138">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="a8e9d-139">Obsahuje informace o vazbách sestavení a uvolnění paměti.</span><span class="sxs-lookup"><span data-stu-id="a8e9d-139">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a8e9d-140">Příklad</span><span class="sxs-lookup"><span data-stu-id="a8e9d-140">Example</span></span>  
 <span data-ttu-id="a8e9d-141">Následující příklad ukazuje, jak k přesměrování jednu verzi sestavení do druhého a poskytují základu kódu.</span><span class="sxs-lookup"><span data-stu-id="a8e9d-141">The following example shows how to redirect one assembly version to another and provide a codebase.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <bindingRedirect oldVersion="1.0.0.0"  
                             newVersion="2.0.0.0"/>  
            <codeBase version="2.0.0.0"  
                      href="http://www.litwareinc.com/myAssembly.dll"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="a8e9d-142">Následující příklad ukazuje, jak používat **AppliesTo –** atribut přesměrování vazby sestavení rozhraní .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a8e9d-142">The following example shows how to use the **appliesTo** attribute to redirect binding of a .NET Framework assembly.</span></span>  
  
```xml  
<runtime>  
   <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1" appliesTo="v1.0.3705">  
      <dependentAssembly>   
         <assemblyIdentity name="mscorcfg" publicKeyToken="b03f5f7f11d50a3a" culture=""/>  
         <bindingRedirect oldVersion="0.0.0.0-65535.65535.65535.65535" newVersion="1.0.3300.0"/>  
      </dependentAssembly>  
   </assemblyBinding>  
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a8e9d-143">Viz také</span><span class="sxs-lookup"><span data-stu-id="a8e9d-143">See Also</span></span>  
 [<span data-ttu-id="a8e9d-144">Schéma nastavení běhového prostředí</span><span class="sxs-lookup"><span data-stu-id="a8e9d-144">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="a8e9d-145">Schéma konfiguračního souboru</span><span class="sxs-lookup"><span data-stu-id="a8e9d-145">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="a8e9d-146">Přesměrování verzí sestavení</span><span class="sxs-lookup"><span data-stu-id="a8e9d-146">Redirecting Assembly Versions</span></span>](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)
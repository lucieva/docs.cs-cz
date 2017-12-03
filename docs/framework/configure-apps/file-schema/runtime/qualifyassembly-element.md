---
title: "&lt;qualifyassembly –&gt; – Element"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#qualifyAssembly
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/qualifyAssembly
helpviewer_keywords:
- container tags, <qualifyAssembly> element
- <qualifyAssembly> element
- qualifyAssembly element
ms.assetid: ad6442f6-1a9d-43b6-b733-04ac1b7f9b82
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 521bbccd83f224cc824dae41309715d65472454e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="ltqualifyassemblygt-element"></a><span data-ttu-id="ca1ab-102">&lt;qualifyassembly –&gt; – Element</span><span class="sxs-lookup"><span data-stu-id="ca1ab-102">&lt;qualifyAssembly&gt; Element</span></span>
<span data-ttu-id="ca1ab-103">Určuje úplný název sestavení, které by měl být dynamicky načíst, pokud je použít částečný název.</span><span class="sxs-lookup"><span data-stu-id="ca1ab-103">Specifies the full name of the assembly that should be dynamically loaded when a partial name is used.</span></span>  
  
 <span data-ttu-id="ca1ab-104">\<Konfigurace ></span><span class="sxs-lookup"><span data-stu-id="ca1ab-104">\<configuration></span></span>  
<span data-ttu-id="ca1ab-105">\<modul runtime ></span><span class="sxs-lookup"><span data-stu-id="ca1ab-105">\<runtime></span></span>  
<span data-ttu-id="ca1ab-106">\<assemblybinding – ></span><span class="sxs-lookup"><span data-stu-id="ca1ab-106">\<assemblyBinding></span></span>  
<span data-ttu-id="ca1ab-107">\<qualifyassembly – ></span><span class="sxs-lookup"><span data-stu-id="ca1ab-107">\<qualifyAssembly></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca1ab-108">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="ca1ab-108">Syntax</span></span>  
  
```xml  
      <qualifyAssembly partialName=  
      "PartialAssemblyName"  
                 fullName="FullAssemblyName"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ca1ab-109">Atributy a elementy</span><span class="sxs-lookup"><span data-stu-id="ca1ab-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ca1ab-110">Následující části popisují atributy, podřízené prvky a nadřazené prvky.</span><span class="sxs-lookup"><span data-stu-id="ca1ab-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ca1ab-111">Atributy</span><span class="sxs-lookup"><span data-stu-id="ca1ab-111">Attributes</span></span>  
  
|<span data-ttu-id="ca1ab-112">Atribut</span><span class="sxs-lookup"><span data-stu-id="ca1ab-112">Attribute</span></span>|<span data-ttu-id="ca1ab-113">Popis</span><span class="sxs-lookup"><span data-stu-id="ca1ab-113">Description</span></span>|  
|---------------|-----------------|  
|`partialName`|<span data-ttu-id="ca1ab-114">Požadovaný atribut.</span><span class="sxs-lookup"><span data-stu-id="ca1ab-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="ca1ab-115">Určuje částečné název sestavení, jak se objevuje v kódu.</span><span class="sxs-lookup"><span data-stu-id="ca1ab-115">Specifies the partial name of the assembly as it appears in the code.</span></span>|  
|`fullName`|<span data-ttu-id="ca1ab-116">Požadovaný atribut.</span><span class="sxs-lookup"><span data-stu-id="ca1ab-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="ca1ab-117">Úplný název sestavení, určuje, jak se objevuje v globální mezipaměti sestavení.</span><span class="sxs-lookup"><span data-stu-id="ca1ab-117">Specifies the full name of the assembly as it appears in the global assembly cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ca1ab-118">Podřízené elementy</span><span class="sxs-lookup"><span data-stu-id="ca1ab-118">Child Elements</span></span>  
 <span data-ttu-id="ca1ab-119">Žádné</span><span class="sxs-lookup"><span data-stu-id="ca1ab-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ca1ab-120">Nadřazené elementy</span><span class="sxs-lookup"><span data-stu-id="ca1ab-120">Parent Elements</span></span>  
  
|<span data-ttu-id="ca1ab-121">Prvek</span><span class="sxs-lookup"><span data-stu-id="ca1ab-121">Element</span></span>|<span data-ttu-id="ca1ab-122">Popis</span><span class="sxs-lookup"><span data-stu-id="ca1ab-122">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="ca1ab-123">Obsahuje informace o přesměrování verze sestavení a umístění sestavení.</span><span class="sxs-lookup"><span data-stu-id="ca1ab-123">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="ca1ab-124">Kořenový prvek v každém konfiguračním souboru, který je používán modulem Common Language Runtime (CLR) a aplikacemi rozhraní .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ca1ab-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="ca1ab-125">Obsahuje informace o vazbách sestavení a uvolnění paměti.</span><span class="sxs-lookup"><span data-stu-id="ca1ab-125">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca1ab-126">Poznámky</span><span class="sxs-lookup"><span data-stu-id="ca1ab-126">Remarks</span></span>  
 <span data-ttu-id="ca1ab-127">Volání <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> metoda pomocí názvů částečného sestavení způsobí, že modul common language runtime a hledat sestavení pouze v adresáři základní aplikace.</span><span class="sxs-lookup"><span data-stu-id="ca1ab-127">Calling the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method using partial assembly names causes the common language runtime to look for the assembly only in the application base directory.</span></span> <span data-ttu-id="ca1ab-128">Použití  **\<qualifyassembly – >** element v konfiguračním souboru aplikace k poskytování informací o úplné sestavení (název, verzi, token veřejného klíče a jazykovou verzi) a způsobit, že modul common language runtime pro vyhledávání pro sestavení v globální mezipaměti sestavení.</span><span class="sxs-lookup"><span data-stu-id="ca1ab-128">Use the **\<qualifyAssembly>** element in your application configuration file to provide the full assembly information (name, version, public key token, and culture) and cause the common language runtime to search for the assembly in the global assembly cache.</span></span>  
  
 <span data-ttu-id="ca1ab-129">**FullName** atributu musí obsahovat čtyři pole identity sestavení: název, verzi, token veřejného klíče a jazykovou verzi.</span><span class="sxs-lookup"><span data-stu-id="ca1ab-129">The **fullName** attribute must include the four fields of assembly identity: name, version, public key token, and culture.</span></span> <span data-ttu-id="ca1ab-130">**PartialName** atributu musí odkazovat částečně sestavení.</span><span class="sxs-lookup"><span data-stu-id="ca1ab-130">The **partialName** attribute must partially reference an assembly.</span></span> <span data-ttu-id="ca1ab-131">Musíte zadat alespoň název sestavení text (v případě nejběžnějších)), ale může také obsahovat verzi, token veřejného klíče, nebo jazykovou verzi (nebo libovolnou kombinaci čtyři, ale ne všechny čtyři).</span><span class="sxs-lookup"><span data-stu-id="ca1ab-131">You must specify at least the assembly's text name (the most common case), but you can also include version, public key token, or culture (or any combination of the four, but not all four).</span></span> <span data-ttu-id="ca1ab-132">**PartialName** musí odpovídat názvu zadaná v volání.</span><span class="sxs-lookup"><span data-stu-id="ca1ab-132">The **partialName** must match the name specified in your call.</span></span> <span data-ttu-id="ca1ab-133">Například nelze zadat `"math"` jako **partialName** atribut v konfiguračním souboru a volání `Assembly.Load("math, Version=3.3.3.3")` v kódu.</span><span class="sxs-lookup"><span data-stu-id="ca1ab-133">For example, you cannot specify `"math"` as the **partialName** attribute in your configuration file and call `Assembly.Load("math, Version=3.3.3.3")` in your code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ca1ab-134">Příklad</span><span class="sxs-lookup"><span data-stu-id="ca1ab-134">Example</span></span>  
 <span data-ttu-id="ca1ab-135">Následující příklad změní logicky volání `Assembly.Load("math")` do `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`.</span><span class="sxs-lookup"><span data-stu-id="ca1ab-135">The following example logically turns the call `Assembly.Load("math")` into `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <qualifyAssembly partialName="math"   
                         fullName=  
"math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ca1ab-136">Viz také</span><span class="sxs-lookup"><span data-stu-id="ca1ab-136">See Also</span></span>  
 [<span data-ttu-id="ca1ab-137">Schéma nastavení běhového prostředí</span><span class="sxs-lookup"><span data-stu-id="ca1ab-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="ca1ab-138">Jak běhové prostředí vyhledává sestavení</span><span class="sxs-lookup"><span data-stu-id="ca1ab-138">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [<span data-ttu-id="ca1ab-139">NIB: Částečné odkazy na sestavení</span><span class="sxs-lookup"><span data-stu-id="ca1ab-139">NIB: Partial Assembly References</span></span>](http://msdn.microsoft.com/en-us/ec90f07a-398c-4306-9401-0fc5ff9cb59f)
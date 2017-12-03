---
title: "Vystavení komponent COM pro rozhraní .NET Framework"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- exposing COM components to .NET Framework
- interoperation with unmanaged code, exposing COM components
- COM interop, exposing COM components
ms.assetid: e78b14f1-e487-43cd-9c6d-1a07483f1730
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 26efd43a05252e657626063d7dd04b1020dace18
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="exposing-com-components-to-the-net-framework"></a><span data-ttu-id="93445-102">Vystavení komponent COM pro rozhraní .NET Framework</span><span class="sxs-lookup"><span data-stu-id="93445-102">Exposing COM Components to the .NET Framework</span></span>
<span data-ttu-id="93445-103">Tento oddíl shrnuje proces nutný k zpřístupnění existující součást COM do spravovaného kódu.</span><span class="sxs-lookup"><span data-stu-id="93445-103">This section summarizes the process needed to expose an existing COM component to managed code.</span></span> <span data-ttu-id="93445-104">Podrobnosti o zápis servery COM, která úzce integrovat s rozhraním .NET Framework, najdete v části [aspekty návrhu pro spolupráci](http://msdn.microsoft.com/en-us/b59637f6-fe35-40d6-ae72-901e7a707689).</span><span class="sxs-lookup"><span data-stu-id="93445-104">For details about writing COM servers that tightly integrate with the .NET Framework, see [Design Considerations for Interoperation](http://msdn.microsoft.com/en-us/b59637f6-fe35-40d6-ae72-901e7a707689).</span></span>  
  
 <span data-ttu-id="93445-105">Existující součásti COM jsou cenné prostředky ve spravovaném kódu jako střední vrstvu obchodní aplikace nebo jako izolované funkce.</span><span class="sxs-lookup"><span data-stu-id="93445-105">Existing COM components are valuable resources in managed code as middle-tier business applications or as isolated functionality.</span></span> <span data-ttu-id="93445-106">Ideální součást má primární spolupracující sestavení a úzce vyhovuje standardům programovací způsobené COM.</span><span class="sxs-lookup"><span data-stu-id="93445-106">An ideal component has a primary interop assembly and conforms tightly to the programming standards imposed by COM.</span></span>  
  
#### <a name="to-expose-com-components-to-the-net-framework"></a><span data-ttu-id="93445-107">K vystavení součástí COM v rozhraní .NET Framework</span><span class="sxs-lookup"><span data-stu-id="93445-107">To expose COM components to the .NET Framework</span></span>  
  
1.  <span data-ttu-id="93445-108">[Import knihovny typů jako sestavení](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="93445-108">[Import a type library as an assembly](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md).</span></span>  
  
     <span data-ttu-id="93445-109">Modul common language runtime požaduje metadata pro všechny typy, včetně typy modelu COM.</span><span class="sxs-lookup"><span data-stu-id="93445-109">The common language runtime requires metadata for all types, including COM types.</span></span> <span data-ttu-id="93445-110">Existuje několik způsobů, jak získat sestavení obsahující typy modelu COM importován jako metadata.</span><span class="sxs-lookup"><span data-stu-id="93445-110">There are several ways to obtain an assembly containing COM types imported as metadata.</span></span>  
  
2.  <span data-ttu-id="93445-111">[Vytvoření typů COM ve spravovaném kódu](http://msdn.microsoft.com/en-us/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66).</span><span class="sxs-lookup"><span data-stu-id="93445-111">[Create COM types in managed Code](http://msdn.microsoft.com/en-us/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66).</span></span>  
  
     <span data-ttu-id="93445-112">Můžete zkontrolovat typy modelu COM, aktivovat instancí a vyvolání metody pro objekt COM stejným způsobem jako u jakékoli spravovaného typu.</span><span class="sxs-lookup"><span data-stu-id="93445-112">You can inspect COM types, activate instances, and invoke methods on the COM object the same way you do for any managed type.</span></span>  
  
3.  <span data-ttu-id="93445-113">[Kompilace projektu interoperability](../../../docs/framework/interop/compiling-an-interop-project.md).</span><span class="sxs-lookup"><span data-stu-id="93445-113">[Compile an interop project](../../../docs/framework/interop/compiling-an-interop-project.md).</span></span>  
  
     <span data-ttu-id="93445-114">[!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] Poskytuje kompilátory pro několik jazyků kompatibilní s specifikace CLS (Common Language), včetně [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C# a C++.</span><span class="sxs-lookup"><span data-stu-id="93445-114">The [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] provides compilers for several languages compliant with the Common Language Specification (CLS), including [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C#, and C++.</span></span>  
  
4.  <span data-ttu-id="93445-115">[Nasazení aplikace spolupráce](../../../docs/framework/interop/deploying-an-interop-application.md).</span><span class="sxs-lookup"><span data-stu-id="93445-115">[Deploy an interop application](../../../docs/framework/interop/deploying-an-interop-application.md).</span></span>  
  
     <span data-ttu-id="93445-116">Spolupráce – aplikace nejlépe nasazených jako [silným názvem](../../../docs/framework/app-domains/strong-named-assemblies.md), podepsané sestavení v globální mezipaměti sestavení.</span><span class="sxs-lookup"><span data-stu-id="93445-116">Interop applications are best deployed as [strong-named](../../../docs/framework/app-domains/strong-named-assemblies.md), signed assemblies in the global assembly cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93445-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="93445-117">See Also</span></span>  
 [<span data-ttu-id="93445-118">Spolupráce s nespravovaným kódem</span><span class="sxs-lookup"><span data-stu-id="93445-118">Interoperating with Unmanaged Code</span></span>](../../../docs/framework/interop/index.md)  
 [<span data-ttu-id="93445-119">Aspekty návrhu pro spolupráci</span><span class="sxs-lookup"><span data-stu-id="93445-119">Design Considerations for Interoperation</span></span>](http://msdn.microsoft.com/en-us/b59637f6-fe35-40d6-ae72-901e7a707689)  
 [<span data-ttu-id="93445-120">Ukázka zprostředkovatele komunikace s objekty COM: Klient .NET a COM Server</span><span class="sxs-lookup"><span data-stu-id="93445-120">COM Interop Sample: .NET Client and COM Server</span></span>](../../../docs/framework/interop/com-interop-sample-net-client-and-com-server.md)  
 [<span data-ttu-id="93445-121">Jazyková nezávislost a jazykově nezávislé komponenty</span><span class="sxs-lookup"><span data-stu-id="93445-121">Language Independence and Language-Independent Components</span></span>](../../../docs/standard/language-independence-and-language-independent-components.md)  
 [<span data-ttu-id="93445-122">Gacutil.exe (nástroj globální mezipaměti sestavení)</span><span class="sxs-lookup"><span data-stu-id="93445-122">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../../../docs/framework/tools/gacutil-exe-gac-tool.md)
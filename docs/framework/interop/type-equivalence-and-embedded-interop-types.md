---
title: "Ekvivalence typů a vestavěné typy spolupráce"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- type equivalence
- embedded interop types
- primary interop assemblies,not necessary in CLR version 4
- NoPIA
ms.assetid: 78892eba-2a58-4165-b4b1-0250ee2f41dc
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4b29ed1c3659b1705640888ded5fe21432dc6ada
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="type-equivalence-and-embedded-interop-types"></a><span data-ttu-id="800f4-102">Ekvivalence typů a vestavěné typy spolupráce</span><span class="sxs-lookup"><span data-stu-id="800f4-102">Type Equivalence and Embedded Interop Types</span></span>
<span data-ttu-id="800f4-103">Od verze [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], běžné podporuje runtime jazyka vložení informací o typu pro typy modelu COM přímo do spravované sestavení, místo aby spravované sestavení, které chcete získat informace o typu pro typy modelu COM z spolupráce – sestavení.</span><span class="sxs-lookup"><span data-stu-id="800f4-103">Beginning with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], the common language runtime supports embedding type information for COM types directly into managed assemblies, instead of requiring the managed assemblies to obtain type information for COM types from interop assemblies.</span></span> <span data-ttu-id="800f4-104">Informace o vložených typu zahrnuje jenom typy a členy, které jsou spravované sestavení. ve skutečnosti používány, a proto může mít dva spravované sestavení velmi různá zobrazení stejného typu COM.</span><span class="sxs-lookup"><span data-stu-id="800f4-104">Because the embedded type information includes only the types and members that are actually used by a managed assembly, two managed assemblies might have very different views of the same COM type.</span></span> <span data-ttu-id="800f4-105">Každé spravované sestavení má jiné <xref:System.Type> objekt představující jeho zobrazení typu modelu COM.</span><span class="sxs-lookup"><span data-stu-id="800f4-105">Each managed assembly has a different <xref:System.Type> object to represent its view of the COM type.</span></span> <span data-ttu-id="800f4-106">Modul common language runtime podporuje ekvivalence typů mezi tyto různá zobrazení pro rozhraní, struktury, výčty a delegáti.</span><span class="sxs-lookup"><span data-stu-id="800f4-106">The common language runtime supports type equivalence between these different views for interfaces, structures, enumerations, and delegates.</span></span>  
  
 <span data-ttu-id="800f4-107">Ekvivalence typů znamená, že objekt modelu COM, který je předán z jedné spravované sestavení do jiného lze převést na odpovídající typ v přijímající sestavení spravované.</span><span class="sxs-lookup"><span data-stu-id="800f4-107">Type equivalence means that a COM object that is passed from one managed assembly to another can be cast to the appropriate managed type in the receiving assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="800f4-108">Ekvivalence typů a vestavěné typy spolupráce zjednodušit nasazení aplikace a doplňky, které používají komponenty modelu COM, protože to není nezbytné pro nasazení sestavení vzájemné spolupráce s aplikacemi.</span><span class="sxs-lookup"><span data-stu-id="800f4-108">Type equivalence and embedded interop types simplify the deployment of applications and add-ins that use COM components, because it is not necessary to deploy interop assemblies with the applications.</span></span> <span data-ttu-id="800f4-109">Vývojáři sdílené komponenty modelu COM ještě vytvořit primární spolupracující sestavení (PIA), pokud chtějí jejich součásti použije ve starších verzích rozhraní .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="800f4-109">Developers of shared COM components still have to create primary interop assemblies (PIAs) if they want their components to be used by earlier versions of the .NET Framework.</span></span>  
  
## <a name="type-equivalence"></a><span data-ttu-id="800f4-110">Ekvivalence typů</span><span class="sxs-lookup"><span data-stu-id="800f4-110">Type Equivalence</span></span>  
 <span data-ttu-id="800f4-111">Ekvivalence typů COM je podporován pro rozhraní, struktury, výčty a delegáti.</span><span class="sxs-lookup"><span data-stu-id="800f4-111">Equivalence of COM types is supported for interfaces, structures, enumerations, and delegates.</span></span> <span data-ttu-id="800f4-112">Typy modelu COM kvalifikaci jako ekvivalentní, pokud jsou splněny všechny z následujících akcí:</span><span class="sxs-lookup"><span data-stu-id="800f4-112">COM types qualify as equivalent if all of the following are true:</span></span>  
  
-   <span data-ttu-id="800f4-113">Typy jsou obě rozhraní, nebo jak struktur, nebo jak výčty nebo oba delegáti.</span><span class="sxs-lookup"><span data-stu-id="800f4-113">The types are both interfaces, or both structures, or both enumerations, or both delegates.</span></span>  
  
-   <span data-ttu-id="800f4-114">Typy mít stejnou identitu, jak je popsáno v následující části.</span><span class="sxs-lookup"><span data-stu-id="800f4-114">The types have the same identity, as described in the next section.</span></span>  
  
-   <span data-ttu-id="800f4-115">Oba typy jsou způsobilé pro ekvivalence typů, jak je popsáno v [označení typy modelu COM pro ekvivalence typů](#type_equiv) části.</span><span class="sxs-lookup"><span data-stu-id="800f4-115">Both types are eligible for type equivalence, as described in the [Marking COM Types for Type Equivalence](#type_equiv) section.</span></span>  
  
### <a name="type-identity"></a><span data-ttu-id="800f4-116">Typ Identity</span><span class="sxs-lookup"><span data-stu-id="800f4-116">Type Identity</span></span>  
 <span data-ttu-id="800f4-117">Dva typy, které jsou určeny k mít stejnou identitu při jejich obory a identity odpovídat jinými slovy, pokud každá má <xref:System.Runtime.InteropServices.TypeIdentifierAttribute> atribut a dva atributy mají odpovídající <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Scope%2A> a <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Identifier%2A> vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="800f4-117">Two types are determined to have the same identity when their scopes and identities match, in other words, if they each have the <xref:System.Runtime.InteropServices.TypeIdentifierAttribute> attribute, and the two attributes have matching <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Scope%2A> and <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Identifier%2A> properties.</span></span> <span data-ttu-id="800f4-118">Porovnání pro <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Scope%2A> je velká a malá písmena.</span><span class="sxs-lookup"><span data-stu-id="800f4-118">The comparison for <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Scope%2A> is case-insensitive.</span></span>  
  
 <span data-ttu-id="800f4-119">Pokud typ nemá <xref:System.Runtime.InteropServices.TypeIdentifierAttribute> atribut, nebo pokud nemá <xref:System.Runtime.InteropServices.TypeIdentifierAttribute> atribut, který není uveden oboru a identifikátor, typ lze i nadále považovat za pro ekvivalenční následujícím způsobem:</span><span class="sxs-lookup"><span data-stu-id="800f4-119">If a type does not have the <xref:System.Runtime.InteropServices.TypeIdentifierAttribute> attribute, or if it has a <xref:System.Runtime.InteropServices.TypeIdentifierAttribute> attribute that does not specify scope and identifier, the type can still be considered for equivalence as follows:</span></span>  
  
-   <span data-ttu-id="800f4-120">Pro rozhraní, hodnota <xref:System.Runtime.InteropServices.GuidAttribute> se používá místo <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Scope%2A?displayProperty=nameWithType> vlastnost a <xref:System.Type.FullName%2A?displayProperty=nameWithType> vlastnost (to znamená, že název typu včetně oboru názvů) se používá namísto <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Identifier%2A?displayProperty=nameWithType> vlastnost.</span><span class="sxs-lookup"><span data-stu-id="800f4-120">For interfaces, the value of the <xref:System.Runtime.InteropServices.GuidAttribute> is used instead of the <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Scope%2A?displayProperty=nameWithType> property, and the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property (that is, the type name, including the namespace) is used instead of the <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Identifier%2A?displayProperty=nameWithType> property.</span></span>  
  
-   <span data-ttu-id="800f4-121">Struktury, výčty a delegáti <xref:System.Runtime.InteropServices.GuidAttribute> obsahující sestavení, které se používá namísto <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Scope%2A> vlastnost a <xref:System.Type.FullName%2A?displayProperty=nameWithType> vlastnost se používá namísto <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Identifier%2A> vlastnost.</span><span class="sxs-lookup"><span data-stu-id="800f4-121">For structures, enumerations, and delegates, the <xref:System.Runtime.InteropServices.GuidAttribute> of the containing assembly is used instead of the <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Scope%2A> property, and the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property is used instead of the <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Identifier%2A> property.</span></span>  
  
<a name="type_equiv"></a>   
### <a name="marking-com-types-for-type-equivalence"></a><span data-ttu-id="800f4-122">Označení typy modelu COM pro ekvivalence typů</span><span class="sxs-lookup"><span data-stu-id="800f4-122">Marking COM Types for Type Equivalence</span></span>  
 <span data-ttu-id="800f4-123">Můžete označit typu jako vhodné pro ekvivalence typů dvěma způsoby:</span><span class="sxs-lookup"><span data-stu-id="800f4-123">You can mark a type as eligible for type equivalence in two ways:</span></span>  
  
-   <span data-ttu-id="800f4-124">Použít <xref:System.Runtime.InteropServices.TypeIdentifierAttribute> atributu typu.</span><span class="sxs-lookup"><span data-stu-id="800f4-124">Apply the <xref:System.Runtime.InteropServices.TypeIdentifierAttribute> attribute to the type.</span></span>  
  
-   <span data-ttu-id="800f4-125">Ujistěte se, typ typ importu COM.</span><span class="sxs-lookup"><span data-stu-id="800f4-125">Make the type a COM import type.</span></span> <span data-ttu-id="800f4-126">Rozhraní je typ importu COM, pokud má <xref:System.Runtime.InteropServices.ComImportAttribute> atribut.</span><span class="sxs-lookup"><span data-stu-id="800f4-126">An interface is a COM import type if it has the <xref:System.Runtime.InteropServices.ComImportAttribute> attribute.</span></span> <span data-ttu-id="800f4-127">Rozhraní, struktura, výčet nebo delegáta je typ importu COM, pokud má sestavení, ve kterém je definovaný <xref:System.Runtime.InteropServices.ImportedFromTypeLibAttribute> atribut.</span><span class="sxs-lookup"><span data-stu-id="800f4-127">An interface, structure, enumeration, or delegate is a COM import type if the assembly in which it is defined has the <xref:System.Runtime.InteropServices.ImportedFromTypeLibAttribute> attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="800f4-128">Viz také</span><span class="sxs-lookup"><span data-stu-id="800f4-128">See Also</span></span>  
 <xref:System.Type.IsEquivalentTo%2A>  
 [<span data-ttu-id="800f4-129">Použití typy modelu COM ve spravovaném kódu</span><span class="sxs-lookup"><span data-stu-id="800f4-129">Using COM Types in Managed Code</span></span>](http://msdn.microsoft.com/en-us/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66)  
 [<span data-ttu-id="800f4-130">Import knihovny typů jako sestavení</span><span class="sxs-lookup"><span data-stu-id="800f4-130">Importing a Type Library as an Assembly</span></span>](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md)
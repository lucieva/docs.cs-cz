---
title: "CorTypeAttr – výčet"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorTypeAttr
api_location: mscoree.dll
api_type: COM
f1_keywords: CorTypeAttr
helpviewer_keywords: CorTypeAttr enumeration [.NET Framework metadata]
ms.assetid: 9bede0ec-5fdf-42a2-b5b7-bee64056acb6
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ab9ce555406dfeb16f99601e6b88af2395c91ae0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="cortypeattr-enumeration"></a><span data-ttu-id="16a21-102">CorTypeAttr – výčet</span><span class="sxs-lookup"><span data-stu-id="16a21-102">CorTypeAttr Enumeration</span></span>
<span data-ttu-id="16a21-103">Obsahuje hodnoty, které označují typ metadat.</span><span class="sxs-lookup"><span data-stu-id="16a21-103">Contains values that indicate type metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16a21-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="16a21-104">Syntax</span></span>  
  
```  
typedef enum CorTypeAttr {  
  
    tdVisibilityMask        =   0x00000007,  
    tdNotPublic             =   0x00000000,  
    tdPublic                =   0x00000001,  
    tdNestedPublic          =   0x00000002,  
    tdNestedPrivate         =   0x00000003,  
    tdNestedFamily          =   0x00000004,  
    tdNestedAssembly        =   0x00000005,  
    tdNestedFamANDAssem     =   0x00000006,  
    tdNestedFamORAssem      =   0x00000007,  
  
    tdLayoutMask            =   0x00000018,  
    tdAutoLayout            =   0x00000000,  
    tdSequentialLayout      =   0x00000008,  
    tdExplicitLayout        =   0x00000010,  
  
    tdClassSemanticsMask    =   0x00000020,  
    tdClass                 =   0x00000000,  
    tdInterface             =   0x00000020,  
  
    tdAbstract              =   0x00000080,  
    tdSealed                =   0x00000100,  
    tdSpecialName           =   0x00000400,  
  
    tdImport                =   0x00001000,  
    tdSerializable          =   0x00002000,  
    tdWindowsRuntime        =   0x00004000,  
  
    tdStringFormatMask      =   0x00030000,  
    tdAnsiClass             =   0x00000000,  
    tdUnicodeClass          =   0x00010000,  
    tdAutoClass             =   0x00020000,  
    tdCustomFormatClass     =   0x00030000,  
    tdCustomFormatMask      =   0x00C00000,  
  
    tdBeforeFieldInit       =   0x00100000,  
    tdForwarder             =   0x00200000,  
  
    tdReservedMask          =   0x00040800,  
    tdRTSpecialName         =   0x00000800,  
    tdHasSecurity           =   0x00040000,  
  
} CorTypeAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="16a21-105">Členové</span><span class="sxs-lookup"><span data-stu-id="16a21-105">Members</span></span>  
  
|<span data-ttu-id="16a21-106">Člen</span><span class="sxs-lookup"><span data-stu-id="16a21-106">Member</span></span>|<span data-ttu-id="16a21-107">Popis</span><span class="sxs-lookup"><span data-stu-id="16a21-107">Description</span></span>|  
|------------|-----------------|  
|`tdVisibilityMask`|<span data-ttu-id="16a21-108">Používá pro informace o typu viditelnosti.</span><span class="sxs-lookup"><span data-stu-id="16a21-108">Used for type visibility information.</span></span>|  
|`tdNotPublic`|<span data-ttu-id="16a21-109">Určuje, že typ není v oboru veřejné.</span><span class="sxs-lookup"><span data-stu-id="16a21-109">Specifies that the type is not in public scope.</span></span>|  
|`tdPublic`|<span data-ttu-id="16a21-110">Určuje, že typ je v veřejné oboru.</span><span class="sxs-lookup"><span data-stu-id="16a21-110">Specifies that the type is in public scope.</span></span>|  
|`tdNestedPublic`|<span data-ttu-id="16a21-111">Určuje, že je typ vnořené veřejné Přehled.</span><span class="sxs-lookup"><span data-stu-id="16a21-111">Specifies that the type is nested with public visibility.</span></span>|  
|`tdNestedPrivate`|<span data-ttu-id="16a21-112">Určuje, zda je typ vnořené s privátní viditelnost.</span><span class="sxs-lookup"><span data-stu-id="16a21-112">Specifies that the type is nested with private visibility.</span></span>|  
|`tdNestedFamily`|<span data-ttu-id="16a21-113">Určuje, že je typ vnořené rodiny Přehled.</span><span class="sxs-lookup"><span data-stu-id="16a21-113">Specifies that the type is nested with family visibility.</span></span>|  
|`tdNestedAssembly`|<span data-ttu-id="16a21-114">Určuje, zda je typ vnořené s viditelnosti sestavení.</span><span class="sxs-lookup"><span data-stu-id="16a21-114">Specifies that the type is nested with assembly visibility.</span></span>|  
|`tdNestedFamANDAssem`|<span data-ttu-id="16a21-115">Určuje, že je typ vnořené s viditelnost rodiny a sestavení.</span><span class="sxs-lookup"><span data-stu-id="16a21-115">Specifies that the type is nested with family and assembly visibility.</span></span>|  
|`tdNestedFamORAssem`|<span data-ttu-id="16a21-116">Určuje, že je typ vnořené s viditelnost třídu nebo sestavení.</span><span class="sxs-lookup"><span data-stu-id="16a21-116">Specifies that the type is nested with family or assembly visibility.</span></span>|  
|`tdLayoutMask`|<span data-ttu-id="16a21-117">Získá informace o typu rozložení.</span><span class="sxs-lookup"><span data-stu-id="16a21-117">Gets layout information for the type.</span></span>|  
|`tdAutoLayout`|<span data-ttu-id="16a21-118">Určuje, že pole tohoto typu jsou nastíněny automaticky.</span><span class="sxs-lookup"><span data-stu-id="16a21-118">Specifies that the fields of this type are laid out automatically.</span></span>|  
|`tdSequentialLayout`|<span data-ttu-id="16a21-119">Určuje, že pole tohoto typu jsou nastíněny postupně.</span><span class="sxs-lookup"><span data-stu-id="16a21-119">Specifies that the fields of this type are laid out sequentially.</span></span>|  
|`tdExplicitLayout`|<span data-ttu-id="16a21-120">Určuje, že je explicitně zadat rozložení tohoto pole.</span><span class="sxs-lookup"><span data-stu-id="16a21-120">Specifies that field layout is supplied explicitly.</span></span>|  
|`tdClassSemanticsMask`|<span data-ttu-id="16a21-121">Získá sémantické informace o typu.</span><span class="sxs-lookup"><span data-stu-id="16a21-121">Gets semantic information about the type.</span></span>|  
|`tdClass`|<span data-ttu-id="16a21-122">Určuje, že je typ třídy.</span><span class="sxs-lookup"><span data-stu-id="16a21-122">Specifies that the type is a class.</span></span>|  
|`tdInterface`|<span data-ttu-id="16a21-123">Určuje, že typ je rozhraní.</span><span class="sxs-lookup"><span data-stu-id="16a21-123">Specifies that the type is an interface.</span></span>|  
|`tdAbstract`|<span data-ttu-id="16a21-124">Určuje, že typ je abstraktní.</span><span class="sxs-lookup"><span data-stu-id="16a21-124">Specifies that the type is abstract.</span></span>|  
|`tdSealed`|<span data-ttu-id="16a21-125">Určuje, že typ nelze rozšířit.</span><span class="sxs-lookup"><span data-stu-id="16a21-125">Specifies that the type cannot be extended.</span></span>|  
|`tdSpecialName`|<span data-ttu-id="16a21-126">Určuje, zda název třídy je speciální.</span><span class="sxs-lookup"><span data-stu-id="16a21-126">Specifies that the class name is special.</span></span> <span data-ttu-id="16a21-127">Popisuje, jeho název jak.</span><span class="sxs-lookup"><span data-stu-id="16a21-127">Its name describes how.</span></span>|  
|`tdImport`|<span data-ttu-id="16a21-128">Určuje, zda je typ naimportovány.</span><span class="sxs-lookup"><span data-stu-id="16a21-128">Specifies that the type is imported.</span></span>|  
|`tdSerializable`|<span data-ttu-id="16a21-129">Určuje, že typ je serializovatelný.</span><span class="sxs-lookup"><span data-stu-id="16a21-129">Specifies that the type is serializable.</span></span>|  
|`tdWindowsRuntime`|<span data-ttu-id="16a21-130">Určuje, že je tento typ [!INCLUDE[wrt](../../../../includes/wrt-md.md)] typu.</span><span class="sxs-lookup"><span data-stu-id="16a21-130">Specifies that this type is a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] type.</span></span>|  
|`tdStringFormatMask`|<span data-ttu-id="16a21-131">Získá informace o tom, jak jsou řetězců kódování a formátu.</span><span class="sxs-lookup"><span data-stu-id="16a21-131">Gets information about how strings are encoded and formatted.</span></span>|  
|`tdAnsiClass`|<span data-ttu-id="16a21-132">Určuje, že tento typ interpretuje LPTSTR jako ANSI.</span><span class="sxs-lookup"><span data-stu-id="16a21-132">Specifies that this type interprets an LPTSTR as ANSI.</span></span>|  
|`tdUnicodeClass`|<span data-ttu-id="16a21-133">Určuje, že tento typ interpretuje LPTSTR jako kódování Unicode.</span><span class="sxs-lookup"><span data-stu-id="16a21-133">Specifies that this type interprets an LPTSTR as Unicode.</span></span>|  
|`tdAutoClass`|<span data-ttu-id="16a21-134">Určuje, že tento typ interpretuje LPTSTR automaticky.</span><span class="sxs-lookup"><span data-stu-id="16a21-134">Specifies that this type interprets an LPTSTR automatically.</span></span>|  
|`tdCustomFormatClass`|<span data-ttu-id="16a21-135">Určuje, že typ má nestandardní kódování, jak je stanoveno `CustomFormatMask`.</span><span class="sxs-lookup"><span data-stu-id="16a21-135">Specifies that the type has a non-standard encoding, as specified by `CustomFormatMask`.</span></span>|  
|`tdCustomFormatMask`|<span data-ttu-id="16a21-136">Tato maska slouží k získání nestandardní kódování informací pro nativní zprostředkovatel komunikace s objekty.</span><span class="sxs-lookup"><span data-stu-id="16a21-136">Use this mask to get non-standard encoding information for native interop.</span></span> <span data-ttu-id="16a21-137">Význam hodnot těchto dvou BITS není zadáno.</span><span class="sxs-lookup"><span data-stu-id="16a21-137">The meaning of the values of these two bits is unspecified.</span></span>|  
|`tdBeforeFieldInit`|<span data-ttu-id="16a21-138">Určuje, že typ se musí inicializovat před první pokus o přístup k statické pole.</span><span class="sxs-lookup"><span data-stu-id="16a21-138">Specifies that the type must be initialized before the first attempt to access a static field.</span></span>|  
|`tdForwarder`|<span data-ttu-id="16a21-139">Určuje, že je typ exportovány a typ předávání.</span><span class="sxs-lookup"><span data-stu-id="16a21-139">Specifies that the type is exported, and a type forwarder.</span></span>|  
|`tdReservedMask`|<span data-ttu-id="16a21-140">Tento příznak a níže uvedené značky se používá interně modul common language runtime.</span><span class="sxs-lookup"><span data-stu-id="16a21-140">This flag and the flags below are used internally by the common language runtime.</span></span>|  
|`tdRTSpecialName`|<span data-ttu-id="16a21-141">Určuje, že by měl modul common language runtime kontrolovat kódování názvu.</span><span class="sxs-lookup"><span data-stu-id="16a21-141">Specifies that the common language runtime should check the name encoding.</span></span>|  
|`tdHasSecurity`|<span data-ttu-id="16a21-142">Určuje, zda má tento typ zabezpečení s ním spojená.</span><span class="sxs-lookup"><span data-stu-id="16a21-142">Specifies that the type has security associated with it.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="16a21-143">Požadavky</span><span class="sxs-lookup"><span data-stu-id="16a21-143">Requirements</span></span>  
 <span data-ttu-id="16a21-144">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16a21-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16a21-145">**Záhlaví:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="16a21-145">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="16a21-146">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16a21-146">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16a21-147">Viz také</span><span class="sxs-lookup"><span data-stu-id="16a21-147">See Also</span></span>  
 [<span data-ttu-id="16a21-148">Výčty metadat</span><span class="sxs-lookup"><span data-stu-id="16a21-148">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
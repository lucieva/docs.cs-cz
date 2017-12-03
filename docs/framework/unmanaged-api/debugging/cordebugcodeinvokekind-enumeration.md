---
title: "Výčet CorDebugCodeInvokeKind"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugCodeInvokeKind
api_location: mscordbi.dll
api_type: COM
ms.assetid: e795e6a2-1008-4a81-af88-d777888e942e
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d46a47c7c655a960224bb836be0ea37cd07c8038
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="cordebugcodeinvokekind-enumeration"></a><span data-ttu-id="b0865-102">Výčet CorDebugCodeInvokeKind</span><span class="sxs-lookup"><span data-stu-id="b0865-102">CorDebugCodeInvokeKind Enumeration</span></span>
<span data-ttu-id="b0865-103">Popisuje, jak exportované funkce vyvolá spravovaného kódu.</span><span class="sxs-lookup"><span data-stu-id="b0865-103">Describes how an exported function invokes managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0865-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="b0865-104">Syntax</span></span>  
  
```  
typedef enum CorDebugCodeInvokeKind  
{  
    CODE_INVOKE_KIND_NONE,       
    CODE_INVOKE_KIND_RETURN,     
    CODE_INVOKE_KIND_TAILCALL,   
} CorDebugCodeInvokeKind;  
```  
  
## <a name="members"></a><span data-ttu-id="b0865-105">Členové</span><span class="sxs-lookup"><span data-stu-id="b0865-105">Members</span></span>  
  
|<span data-ttu-id="b0865-106">Člen</span><span class="sxs-lookup"><span data-stu-id="b0865-106">Member</span></span>|<span data-ttu-id="b0865-107">Popis</span><span class="sxs-lookup"><span data-stu-id="b0865-107">Description</span></span>|  
|------------|-----------------|  
|`CODE_INVOKE_KIND_NONE`|<span data-ttu-id="b0865-108">Pokud je spravovaný kód je vyvolána touto metodou, bude mít umístěné explicitní události nebo zarážky později.</span><span class="sxs-lookup"><span data-stu-id="b0865-108">If any managed code is invoked by this method, it will have to be located by explicit events or breakpoints later.</span></span><br /><br /> <span data-ttu-id="b0865-109">--nebo--</span><span class="sxs-lookup"><span data-stu-id="b0865-109">--or--</span></span><br /><br /> <span data-ttu-id="b0865-110">Právě jsme může neproběhly některé spravovaného kódu, který tato metoda volá, protože neexistuje žádný snadný způsob, jak zastavit v něm.</span><span class="sxs-lookup"><span data-stu-id="b0865-110">We may just miss some of the managed code this method calls because there is no easy way to stop on it.</span></span><br /><br /> <span data-ttu-id="b0865-111">--nebo--</span><span class="sxs-lookup"><span data-stu-id="b0865-111">--or--</span></span><br /><br /> <span data-ttu-id="b0865-112">Metoda může vyvolat nikdy spravovaného kódu.</span><span class="sxs-lookup"><span data-stu-id="b0865-112">The method may never invoke managed code.</span></span>|  
|`CODE_INVOKE_KIND_RETURN`|<span data-ttu-id="b0865-113">Tato metoda vyvolá spravovaného kódu pomocí návratový instrukcí.</span><span class="sxs-lookup"><span data-stu-id="b0865-113">This method will invoke managed code via a return instruction.</span></span> <span data-ttu-id="b0865-114">Krokování s by měl přicházejí na další spravovaného kódu.</span><span class="sxs-lookup"><span data-stu-id="b0865-114">Stepping out should arrive at the next managed code.</span></span>|  
|`CODE_INVOKE_KIND_TAILCALL`|<span data-ttu-id="b0865-115">Tato metoda vyvolá spravovaného kódu pomocí volání funkce tail.</span><span class="sxs-lookup"><span data-stu-id="b0865-115">This method will invoke managed code via a tail-call.</span></span> <span data-ttu-id="b0865-116">Krokování s jedním a zanoříte se některé pokyny volání měli přicházejí na spravovaný kód.</span><span class="sxs-lookup"><span data-stu-id="b0865-116">Single-stepping and stepping over any call instructions should arrive at managed code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b0865-117">Poznámky</span><span class="sxs-lookup"><span data-stu-id="b0865-117">Remarks</span></span>  
 <span data-ttu-id="b0865-118">Tento výčet je používán [icordebugprocess6::getexportstepinfo –](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md) metoda s informacemi o procházení spravovaného kódu.</span><span class="sxs-lookup"><span data-stu-id="b0865-118">This enumeration is used by the [ICorDebugProcess6::GetExportStepInfo](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md) method to provide information about stepping through managed code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b0865-119">Tento výčet je určena pro použití v rozhraní .NET nativní ladění pouze scénáře.</span><span class="sxs-lookup"><span data-stu-id="b0865-119">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0865-120">Požadavky</span><span class="sxs-lookup"><span data-stu-id="b0865-120">Requirements</span></span>  
 <span data-ttu-id="b0865-121">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0865-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0865-122">**Záhlaví:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b0865-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b0865-123">**Knihovna:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0865-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b0865-124">**Verze rozhraní .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0865-124">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0865-125">Viz také</span><span class="sxs-lookup"><span data-stu-id="b0865-125">See Also</span></span>  
 [<span data-ttu-id="b0865-126">Ladění výčtů</span><span class="sxs-lookup"><span data-stu-id="b0865-126">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [<span data-ttu-id="b0865-127">Ladění</span><span class="sxs-lookup"><span data-stu-id="b0865-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
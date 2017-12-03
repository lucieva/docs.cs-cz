---
title: "CorDebugIntercept – výčet"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugIntercept
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugIntercept
helpviewer_keywords: CorDebugIntercept enumeration [.NET Framework debugging]
ms.assetid: 3d5b642e-7ef2-428b-a5ae-509c35ed461a
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b7d34b5f1bdff7a7089d780645b91503a8464849
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="cordebugintercept-enumeration"></a><span data-ttu-id="f5ac8-102">CorDebugIntercept – výčet</span><span class="sxs-lookup"><span data-stu-id="f5ac8-102">CorDebugIntercept Enumeration</span></span>
<span data-ttu-id="f5ac8-103">Určuje typy kód, který mohou být zachyceny (které se do stupeň).</span><span class="sxs-lookup"><span data-stu-id="f5ac8-103">Indicates the types of code that can be intercepted (that is, stepped into).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5ac8-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="f5ac8-104">Syntax</span></span>  
  
```  
typedef enum CorDebugIntercept {  
    INTERCEPT_NONE                = 0x0,  
    INTERCEPT_CLASS_INIT          = 0x01,  
    INTERCEPT_EXCEPTION_FILTER    = 0x02,  
    INTERCEPT_SECURITY            = 0x04,  
    INTERCEPT_CONTEXT_POLICY      = 0x08,  
    INTERCEPT_INTERCEPTION        = 0x10,  
    INTERCEPT_ALL                 = 0xffff  
} CorDebugIntercept;  
```  
  
## <a name="members"></a><span data-ttu-id="f5ac8-105">Členové</span><span class="sxs-lookup"><span data-stu-id="f5ac8-105">Members</span></span>  
  
|<span data-ttu-id="f5ac8-106">Člen</span><span class="sxs-lookup"><span data-stu-id="f5ac8-106">Member</span></span>|<span data-ttu-id="f5ac8-107">Popis</span><span class="sxs-lookup"><span data-stu-id="f5ac8-107">Description</span></span>|  
|------------|-----------------|  
|`INTERCEPT_NONE`|<span data-ttu-id="f5ac8-108">Mohou být zachyceny žádný kód.</span><span class="sxs-lookup"><span data-stu-id="f5ac8-108">No code can be intercepted.</span></span>|  
|`INTERCEPT_CLASS_INIT`|<span data-ttu-id="f5ac8-109">Mohou být zachyceny konstruktor.</span><span class="sxs-lookup"><span data-stu-id="f5ac8-109">A constructor can be intercepted.</span></span>|  
|`INTERCEPT_EXCEPTION_FILTER`|<span data-ttu-id="f5ac8-110">Mohou být zachyceny filtru výjimek.</span><span class="sxs-lookup"><span data-stu-id="f5ac8-110">An exception filter can be intercepted.</span></span>|  
|`INTERCEPT_SECURITY`|<span data-ttu-id="f5ac8-111">Kód, který vynucuje zabezpečení mohou být zachyceny.</span><span class="sxs-lookup"><span data-stu-id="f5ac8-111">Code that enforces security can be intercepted.</span></span>|  
|`INTERCEPT_CONTEXT_POLICY`|<span data-ttu-id="f5ac8-112">Mohou být zachyceny zásadu kontextu.</span><span class="sxs-lookup"><span data-stu-id="f5ac8-112">A context policy can be intercepted.</span></span>|  
|`INTERCEPT_INTERCEPTION`|<span data-ttu-id="f5ac8-113">Nepoužívá se.</span><span class="sxs-lookup"><span data-stu-id="f5ac8-113">Not used.</span></span>|  
|`INTERCEPT_ALL`|<span data-ttu-id="f5ac8-114">Mohou být zachyceny veškerý kód.</span><span class="sxs-lookup"><span data-stu-id="f5ac8-114">All code can be intercepted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f5ac8-115">Poznámky</span><span class="sxs-lookup"><span data-stu-id="f5ac8-115">Remarks</span></span>  
 <span data-ttu-id="f5ac8-116">Použití [icordebugstepper::setinterceptmask –](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setinterceptmask-method.md) metodu pro vytvoření typy kód, který může být zachycen.</span><span class="sxs-lookup"><span data-stu-id="f5ac8-116">Use the [ICorDebugStepper::SetInterceptMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setinterceptmask-method.md) method to establish the types of code that can be intercepted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5ac8-117">Požadavky</span><span class="sxs-lookup"><span data-stu-id="f5ac8-117">Requirements</span></span>  
 <span data-ttu-id="f5ac8-118">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5ac8-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5ac8-119">**Záhlaví:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f5ac8-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f5ac8-120">**Knihovna:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f5ac8-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f5ac8-121">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5ac8-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5ac8-122">Viz také</span><span class="sxs-lookup"><span data-stu-id="f5ac8-122">See Also</span></span>  
 [<span data-ttu-id="f5ac8-123">Ladění výčtů</span><span class="sxs-lookup"><span data-stu-id="f5ac8-123">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
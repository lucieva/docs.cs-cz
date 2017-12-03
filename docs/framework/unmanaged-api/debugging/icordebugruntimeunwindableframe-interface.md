---
title: "ICorDebugRuntimeUnwindableFrame – rozhraní"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugUnwindableFrame
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugUnwindableFrame
helpviewer_keywords: ICorDebugUnwindableFrame interface [.NET Framework debugging]
ms.assetid: cd6a3982-6ed3-4909-808d-a66055e813e0
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 003bbab399a9ad0ffe2f1d761aea18ff71ba1834
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugruntimeunwindableframe-interface"></a><span data-ttu-id="5e406-102">ICorDebugRuntimeUnwindableFrame – rozhraní</span><span class="sxs-lookup"><span data-stu-id="5e406-102">ICorDebugRuntimeUnwindableFrame Interface</span></span>
<span data-ttu-id="5e406-103">Poskytuje podporu pro nespravované metody, které vyžadují modul CLR k uvolnění rámce.</span><span class="sxs-lookup"><span data-stu-id="5e406-103">Provides support for unmanaged methods that require the common language runtime (CLR) to unwind a frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5e406-104">Poznámky</span><span class="sxs-lookup"><span data-stu-id="5e406-104">Remarks</span></span>  
 <span data-ttu-id="5e406-105">`ICorDebugRuntimeUnwindableFrame`je specializovanou verzi rozhraní ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="5e406-105">`ICorDebugRuntimeUnwindableFrame` is a specialized version of the ICorDebugFrame interface.</span></span> <span data-ttu-id="5e406-106">Používá se nespravované metody, které vyžadují modulu runtime unwind rámce v aktuální zásobníku.</span><span class="sxs-lookup"><span data-stu-id="5e406-106">It is used by unmanaged methods that require the runtime to unwind a frame on the current stack.</span></span> <span data-ttu-id="5e406-107">Existující unwinding konvence nefungují, protože nepoužívají kompilována kódu.</span><span class="sxs-lookup"><span data-stu-id="5e406-107">Existing unwinding conventions do not work, because they do not use JIT-compiled code.</span></span> <span data-ttu-id="5e406-108">Když ladicí program zobrazí unwindable rámečku, měla by používat [icordebugstackwalk::Next –](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md) metodu unwind ji, ale měli provést kontroly sám sebe.</span><span class="sxs-lookup"><span data-stu-id="5e406-108">When the debugger sees an unwindable frame, it should use the [ICorDebugStackWalk::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md) method to unwind it, but it should perform inspection itself.</span></span> <span data-ttu-id="5e406-109">Když obdrží ladicí program `ICorDebugRuntimeUnwindableFrame`, může zavolat [icordebugstackwalk::getcontext –](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) metoda pro načtení kontextu rámce.</span><span class="sxs-lookup"><span data-stu-id="5e406-109">When the debugger receives an `ICorDebugRuntimeUnwindableFrame`, it can call the [ICorDebugStackWalk::GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) method to retrieve the context of the frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e406-110">Požadavky</span><span class="sxs-lookup"><span data-stu-id="5e406-110">Requirements</span></span>  
 <span data-ttu-id="5e406-111">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e406-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e406-112">**Záhlaví:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5e406-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5e406-113">**Knihovna:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e406-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e406-114">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e406-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e406-115">Viz také</span><span class="sxs-lookup"><span data-stu-id="5e406-115">See Also</span></span>  
 [<span data-ttu-id="5e406-116">Ladění v rozhraní</span><span class="sxs-lookup"><span data-stu-id="5e406-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="5e406-117">Ladění</span><span class="sxs-lookup"><span data-stu-id="5e406-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
---
title: "ICorDebugMutableDataTarget::SetThreadContext – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 8c0d01d5-67e5-4522-9ccf-c8f3a78cb4fd
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8c43ef5405ed582cc55af69d7f41887c0615965f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmutabledatatargetsetthreadcontext-method"></a><span data-ttu-id="f3ac6-102">ICorDebugMutableDataTarget::SetThreadContext – metoda</span><span class="sxs-lookup"><span data-stu-id="f3ac6-102">ICorDebugMutableDataTarget::SetThreadContext Method</span></span>
<span data-ttu-id="f3ac6-103">Nastaví kontext (hodnot registru) vlákna.</span><span class="sxs-lookup"><span data-stu-id="f3ac6-103">Sets the context (register values) for a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3ac6-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="f3ac6-104">Syntax</span></span>  
  
```  
HRESULT SetThreadContext(  
   [in] DWORD dwThreadID,  
   [in] ULONG32 contextSize,   [in, size_is(contextSize)] const BYTE * pContext);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f3ac6-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="f3ac6-105">Parameters</span></span>  
 `dwThreadID`  
 <span data-ttu-id="f3ac6-106">[v] Identifikátor vlákno definované operačního systému.</span><span class="sxs-lookup"><span data-stu-id="f3ac6-106">[in] The operating system-defined thread identifier.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="f3ac6-107">[v] Velikost `pContext` vyrovnávací paměť k zapsání.</span><span class="sxs-lookup"><span data-stu-id="f3ac6-107">[in] The size of the `pContext` buffer to be written.</span></span>  
  
 `pContext`  
 <span data-ttu-id="f3ac6-108">[v] Ukazatel na bajtů, které mají být zapsána.</span><span class="sxs-lookup"><span data-stu-id="f3ac6-108">[in] A pointer to the bytes to be written.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f3ac6-109">Poznámky</span><span class="sxs-lookup"><span data-stu-id="f3ac6-109">Remarks</span></span>  
 <span data-ttu-id="f3ac6-110">`SetThreadContext` Metoda aktualizuje aktuální kontext pro vlákno určeného operačního systému definovaná `dwThreadID` argument.</span><span class="sxs-lookup"><span data-stu-id="f3ac6-110">The `SetThreadContext` method updates the current context for the thread specified by the operating system-defined `dwThreadID` argument.</span></span> <span data-ttu-id="f3ac6-111">Formát kontextu záznamu je určen podle platformy indikován [icordebugdatatarget::getplatform –](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) metoda.</span><span class="sxs-lookup"><span data-stu-id="f3ac6-111">The format of the context record is determined by the platform indicated by the [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) method.</span></span> <span data-ttu-id="f3ac6-112">V systému Windows, [kontextu](http://msdn.microsoft.com/library/windows/desktop/ms679284.aspx) struktura.</span><span class="sxs-lookup"><span data-stu-id="f3ac6-112">On Windows, this is a [CONTEXT](http://msdn.microsoft.com/library/windows/desktop/ms679284.aspx) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3ac6-113">Požadavky</span><span class="sxs-lookup"><span data-stu-id="f3ac6-113">Requirements</span></span>  
 <span data-ttu-id="f3ac6-114">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3ac6-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3ac6-115">**Záhlaví:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f3ac6-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f3ac6-116">**Knihovna:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f3ac6-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f3ac6-117">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3ac6-117">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3ac6-118">Viz také</span><span class="sxs-lookup"><span data-stu-id="f3ac6-118">See Also</span></span>  
 [<span data-ttu-id="f3ac6-119">ICorDebugMutableDataTarget rozhraní</span><span class="sxs-lookup"><span data-stu-id="f3ac6-119">ICorDebugMutableDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)  
 [<span data-ttu-id="f3ac6-120">Ladění v rozhraní</span><span class="sxs-lookup"><span data-stu-id="f3ac6-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
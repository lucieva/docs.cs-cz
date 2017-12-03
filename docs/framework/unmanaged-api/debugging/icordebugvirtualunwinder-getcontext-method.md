---
title: "ICorDebugVirtualUnwinder::GetContext – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: fe502a76-3068-47e5-a0a0-85ccb72dfac3
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 45a914005e84d33b39d72fce96679e275b921d3c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvirtualunwindergetcontext-method"></a><span data-ttu-id="2cd80-102">ICorDebugVirtualUnwinder::GetContext – metoda</span><span class="sxs-lookup"><span data-stu-id="2cd80-102">ICorDebugVirtualUnwinder::GetContext Method</span></span>
<span data-ttu-id="2cd80-103">Získá aktuální kontext tento unwinder.</span><span class="sxs-lookup"><span data-stu-id="2cd80-103">Gets the current context of this unwinder.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cd80-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="2cd80-104">Syntax</span></span>  
  
```  
HRESULT GetContext(  
   [in] ULONG32 contextFlags,  
   [in] ULONG32 cbContextBuf,  
   [out] ULONG32* contextSize,  
   [out, size_is(cbContextBuf)] BYTE contextBuf[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2cd80-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="2cd80-105">Parameters</span></span>  
 `contextFlags`  
 <span data-ttu-id="2cd80-106">[v] Příznaky, které určují, které části kontext, který má vrátit (definované v souboru WinNT.h).</span><span class="sxs-lookup"><span data-stu-id="2cd80-106">[in] Flags that specify which parts of the context to return (defined in WinNT.h).</span></span>  
  
 `cbContextBuf`  
 <span data-ttu-id="2cd80-107">[v] Počet bajtů v `contextBuf`.</span><span class="sxs-lookup"><span data-stu-id="2cd80-107">[in] The number of bytes in `contextBuf`.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="2cd80-108">[out] Ukazatel na počet bajtů ve skutečnosti zapsána do `contextBuf`.</span><span class="sxs-lookup"><span data-stu-id="2cd80-108">[out] A pointer to the number of bytes actually written to `contextBuf`.</span></span>  
  
 `contextBuf`  
 <span data-ttu-id="2cd80-109">[out] Bajtové pole, která obsahuje aktuální kontext tento unwinder.</span><span class="sxs-lookup"><span data-stu-id="2cd80-109">[out] A byte array that contains the current context of this unwinder.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2cd80-110">Návratová hodnota</span><span class="sxs-lookup"><span data-stu-id="2cd80-110">Return Value</span></span>  
 <span data-ttu-id="2cd80-111">Všechny selhání hodnota HRESULT přijatých mscordbi považuje za závažné a způsobí, že rozhraní API ICorDebug vrátit `CORDBG_E_DATA_TARGET_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="2cd80-111">Any failing HRESULT value received by mscordbi is considered fatal and will cause ICorDebug APIs to return `CORDBG_E_DATA_TARGET_ERROR`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2cd80-112">Poznámky</span><span class="sxs-lookup"><span data-stu-id="2cd80-112">Remarks</span></span>  
 <span data-ttu-id="2cd80-113">Nastavit počáteční hodnotu `contextBuf` argument do vyrovnávací paměti kontextu vrácený volání [icordebugstackwalk::getcontext –](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) metoda.</span><span class="sxs-lookup"><span data-stu-id="2cd80-113">You set the initial value of the `contextBuf` argument to the context buffer returned by calling the [ICorDebugStackWalk::GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2cd80-114">Tato metoda je k dispozici s .NET Native jenom.</span><span class="sxs-lookup"><span data-stu-id="2cd80-114">This method is available with .NET Native only.</span></span>  
  
 <span data-ttu-id="2cd80-115">Protože unwinding může pouze obnovení a podmnožina registrů, jako je například stálé zaregistruje pouze, kontext nemusí přesně odpovídat stav registrace v době volání skutečné metody.</span><span class="sxs-lookup"><span data-stu-id="2cd80-115">Because unwinding may only restore a subset of the registers, such as the non-volatile registers only, the context may not exactly match the register state at the time of the actual method call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2cd80-116">Požadavky</span><span class="sxs-lookup"><span data-stu-id="2cd80-116">Requirements</span></span>  
 <span data-ttu-id="2cd80-117">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2cd80-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2cd80-118">**Záhlaví:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2cd80-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2cd80-119">**Knihovna:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2cd80-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2cd80-120">**Verze rozhraní .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2cd80-120">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cd80-121">Viz také</span><span class="sxs-lookup"><span data-stu-id="2cd80-121">See Also</span></span>  
 [<span data-ttu-id="2cd80-122">ICorDebugMemoryBuffer rozhraní</span><span class="sxs-lookup"><span data-stu-id="2cd80-122">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)  
 [<span data-ttu-id="2cd80-123">Ladění v rozhraní</span><span class="sxs-lookup"><span data-stu-id="2cd80-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
---
title: "ICorDebugInternalFrame2::IsCloserToLeaf – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugInternalFrame2.IsCloserToLeaf Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugInternalFrame2::IsCloserToLeaf
helpviewer_keywords:
- ICorDebugInternalFrame2::IsCloserToLeaf method [.NET Framework debugging]
- IsCloserToLeaf method [.NET Framework debugging]
ms.assetid: c1d3d1eb-8370-4f25-8297-3bd262b4740a
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 60e63800ade5fb0d4a222d80ebfe43c3d84c2815
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="icordebuginternalframe2isclosertoleaf-method"></a><span data-ttu-id="4cfff-102">ICorDebugInternalFrame2::IsCloserToLeaf – metoda</span><span class="sxs-lookup"><span data-stu-id="4cfff-102">ICorDebugInternalFrame2::IsCloserToLeaf Method</span></span>
<span data-ttu-id="4cfff-103">Kontroluje, zda `this` interní rámečku je blíž ke listu než zadaný objekt ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="4cfff-103">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cfff-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="4cfff-104">Syntax</span></span>  
  
```  
HRESULT IsCloserToLeaf([in] ICorDebugFrame * pFrameToCompare,  
                       [out] BOOL * pIsCloser);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4cfff-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="4cfff-105">Parameters</span></span>  
 `pFrameToCompare`  
 <span data-ttu-id="4cfff-106">[v] Ukazatel na porovnání `ICorDebugFrame` objektu.</span><span class="sxs-lookup"><span data-stu-id="4cfff-106">[in] A pointer to the comparison `ICorDebugFrame` object.</span></span>  
  
 `pIsCloser`  
 <span data-ttu-id="4cfff-107">[out] `true` Pokud `this` interní rámečku je blíž ke listu než rámečku určeného `pFrameToCompare`, jinak hodnota `false`.</span><span class="sxs-lookup"><span data-stu-id="4cfff-107">[out] `true` if the `this` internal frame is closer to the leaf than the frame specified by `pFrameToCompare`; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4cfff-108">Návratová hodnota</span><span class="sxs-lookup"><span data-stu-id="4cfff-108">Return Value</span></span>  
 <span data-ttu-id="4cfff-109">Tato metoda vrátí následující konkrétní hodnoty HRESULT a také HRESULT chyby, které označují selhání metoda.</span><span class="sxs-lookup"><span data-stu-id="4cfff-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="4cfff-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4cfff-110">HRESULT</span></span>|<span data-ttu-id="4cfff-111">Popis</span><span class="sxs-lookup"><span data-stu-id="4cfff-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4cfff-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="4cfff-112">S_OK</span></span>|<span data-ttu-id="4cfff-113">Porovnání se úspěšně provedla.</span><span class="sxs-lookup"><span data-stu-id="4cfff-113">The comparison was successfully performed.</span></span>|  
|<span data-ttu-id="4cfff-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4cfff-114">E_FAIL</span></span>|<span data-ttu-id="4cfff-115">Nelze provést porovnání.</span><span class="sxs-lookup"><span data-stu-id="4cfff-115">The comparison could not be performed.</span></span>|  
|<span data-ttu-id="4cfff-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="4cfff-116">E_INVALIDARG</span></span>|<span data-ttu-id="4cfff-117">`pFrameToCompare`nebo `pIsCloser` má hodnotu null.</span><span class="sxs-lookup"><span data-stu-id="4cfff-117">`pFrameToCompare` or `pIsCloser` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4cfff-118">Poznámky</span><span class="sxs-lookup"><span data-stu-id="4cfff-118">Remarks</span></span>  
 <span data-ttu-id="4cfff-119">`IsCloserToLeaf`slouží k implementaci zásad pro prokládání interní rámce s jiné rámce v zásobníku.</span><span class="sxs-lookup"><span data-stu-id="4cfff-119">`IsCloserToLeaf` can be used to implement a policy for interleaving internal frames with other frames on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4cfff-120">Požadavky</span><span class="sxs-lookup"><span data-stu-id="4cfff-120">Requirements</span></span>  
 <span data-ttu-id="4cfff-121">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4cfff-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4cfff-122">**Záhlaví:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4cfff-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4cfff-123">**Knihovna:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4cfff-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4cfff-124">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4cfff-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cfff-125">Viz také</span><span class="sxs-lookup"><span data-stu-id="4cfff-125">See Also</span></span>  
 [<span data-ttu-id="4cfff-126">Icordebuginternalframe2 – rozhraní</span><span class="sxs-lookup"><span data-stu-id="4cfff-126">ICorDebugInternalFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)  
 [<span data-ttu-id="4cfff-127">Ladění v rozhraní</span><span class="sxs-lookup"><span data-stu-id="4cfff-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="4cfff-128">Ladění</span><span class="sxs-lookup"><span data-stu-id="4cfff-128">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
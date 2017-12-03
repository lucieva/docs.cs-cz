---
title: "ICorDebugILCode2::GetInstrumentedILMap – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICorDebugILCode2.GetInstrumentedILMap
api_location: mscordbi.dll
api_type: COM
ms.assetid: 7a4e3085-8f95-40ef-a4be-7d6146f47ce2
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9b740f378b4fd15fe6bf4a9832348869878e2a4c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugilcode2getinstrumentedilmap-method"></a><span data-ttu-id="201b1-102">ICorDebugILCode2::GetInstrumentedILMap – metoda</span><span class="sxs-lookup"><span data-stu-id="201b1-102">ICorDebugILCode2::GetInstrumentedILMap Method</span></span>
<span data-ttu-id="201b1-103">[Podporované v rozhraní .NET Framework 4.5.2 a novějších verzích]</span><span class="sxs-lookup"><span data-stu-id="201b1-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="201b1-104">Vrátí mapu od posuny instrumentovány profileru převodní jazyk (IL) do původního metoda IL posunutí pro tuto instanci.</span><span class="sxs-lookup"><span data-stu-id="201b1-104">Returns a map from profiler-instrumented intermediate language (IL) offsets to original method IL offsets for this instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="201b1-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="201b1-105">Syntax</span></span>  
  
```cpp
HRESULT GetInstrumentedILMap(  
   [in] ULONG32 cMap,  
   [out] ULONG32 *pcMap,  
   [out, size_is(cMap), length_is(*pcMap)] COR_IL_MAP map[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="201b1-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="201b1-106">Parameters</span></span>  
 <span data-ttu-id="201b1-107">cMap</span><span class="sxs-lookup"><span data-stu-id="201b1-107">cMap</span></span>  
 <span data-ttu-id="201b1-108">[v] Úložnou kapacitu `map` pole.</span><span class="sxs-lookup"><span data-stu-id="201b1-108">[in] The storage capacity of the `map` array.</span></span> <span data-ttu-id="201b1-109">Další informace naleznete v části Poznámky.</span><span class="sxs-lookup"><span data-stu-id="201b1-109">See the Remarks section for more information.</span></span>  
  
 <span data-ttu-id="201b1-110">pcMap</span><span class="sxs-lookup"><span data-stu-id="201b1-110">pcMap</span></span>  
 <span data-ttu-id="201b1-111">[out] Počet hodnot cor_il_map – zapsána do pole mapy.</span><span class="sxs-lookup"><span data-stu-id="201b1-111">[out] The number of COR_IL_MAP values written to the map array.</span></span>  
  
 <span data-ttu-id="201b1-112">map</span><span class="sxs-lookup"><span data-stu-id="201b1-112">map</span></span>  
 <span data-ttu-id="201b1-113">[out] Pole cor_il_map – hodnoty, které poskytují informace o mapování z instrumentovány profileru IL IL původní metody.</span><span class="sxs-lookup"><span data-stu-id="201b1-113">[out] An array of COR_IL_MAP values that provide information on mappings from profiler-instrumented IL to the IL of the original method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="201b1-114">Poznámky</span><span class="sxs-lookup"><span data-stu-id="201b1-114">Remarks</span></span>  
 <span data-ttu-id="201b1-115">Pokud je profileru nastaví mapování voláním [icorprofilerinfo::setilinstrumentedcodemap –](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) metody ladicího programu můžete volat tuto metodu pro načtení mapování a mapování interně při výpočtu IL posune pro zásobníku trasování a proměnné životnosti.</span><span class="sxs-lookup"><span data-stu-id="201b1-115">If the profiler sets the mapping by calling the [ICorProfilerInfo::SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) method, the debugger can call this method to retrieve the mapping and to use the mapping internally when calculating IL offsets for stack traces and variable lifetimes.</span></span>  
  
 <span data-ttu-id="201b1-116">Pokud `cMap` je 0 a `pcMap` jinou hodnotu než**null**, `pcMap` je nastaven na počet dostupných hodnot cor_il_map –.</span><span class="sxs-lookup"><span data-stu-id="201b1-116">If `cMap` is 0 and `pcMap` is non-**null**, `pcMap` is set to the number of available COR_IL_MAP values.</span></span> <span data-ttu-id="201b1-117">Pokud `cMap` je nulová, představuje kapacitu úložiště `map` pole.</span><span class="sxs-lookup"><span data-stu-id="201b1-117">If `cMap` is non-zero, it represents the storage capacity of the `map` array.</span></span> <span data-ttu-id="201b1-118">Po návratu metody `map` obsahuje maximálně `cMap` položky, a `pcMap` je nastaven na počet hodnot cor_il_map – ve skutečnosti zapsána do `map` pole.</span><span class="sxs-lookup"><span data-stu-id="201b1-118">When the method returns, `map` contains a maximum of `cMap` items, and `pcMap` is set to the number of COR_IL_MAP values actually written to the `map` array.</span></span>  
  
 <span data-ttu-id="201b1-119">Pokud IL nebyla byly instrumentovány nebo mapování nebyl poskytované profileru, tato metoda vrátí hodnotu `S_OK` a nastaví `pcMap` na hodnotu 0.</span><span class="sxs-lookup"><span data-stu-id="201b1-119">If the IL hasn't been instrumented or the mapping wasn't provided by a profiler, this method returns `S_OK` and sets `pcMap` to 0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="201b1-120">Požadavky</span><span class="sxs-lookup"><span data-stu-id="201b1-120">Requirements</span></span>  
 <span data-ttu-id="201b1-121">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="201b1-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="201b1-122">**Záhlaví:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="201b1-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="201b1-123">**Knihovna:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="201b1-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="201b1-124">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="201b1-124">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="201b1-125">Viz také</span><span class="sxs-lookup"><span data-stu-id="201b1-125">See Also</span></span>  
 [<span data-ttu-id="201b1-126">Icorprofilerinfo::setilinstrumentedcodemap –</span><span class="sxs-lookup"><span data-stu-id="201b1-126">ICorProfilerInfo::SetILInstrumentedCodeMap</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md)  
 [<span data-ttu-id="201b1-127">Rozhraní ICorDebugILCode2</span><span class="sxs-lookup"><span data-stu-id="201b1-127">ICorDebugILCode2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-interface.md)  
 [<span data-ttu-id="201b1-128">Ladění v rozhraní</span><span class="sxs-lookup"><span data-stu-id="201b1-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
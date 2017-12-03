---
title: "ICorProfilerInfo5::GetEventMask2 – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICorProfilerInfo5.GetEventMask2
api_location: mscorwks.dll
api_type: COM
ms.assetid: f854b68f-009c-4ffb-89cd-ca874d1c0fb7
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: da1c4c11adaac21e9769330ee24beceff64e020b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo5geteventmask2-method"></a><span data-ttu-id="27f1f-102">ICorProfilerInfo5::GetEventMask2 – metoda</span><span class="sxs-lookup"><span data-stu-id="27f1f-102">ICorProfilerInfo5::GetEventMask2 Method</span></span>
<span data-ttu-id="27f1f-103">[Podporované v rozhraní .NET Framework 4.5.2 a novějších verzích]</span><span class="sxs-lookup"><span data-stu-id="27f1f-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="27f1f-104">Získá aktuální kategorií událostí, pro které profileru chce dostávat oznámení, modul CLR (CLR).</span><span class="sxs-lookup"><span data-stu-id="27f1f-104">Gets the current event categories for which the profiler wants to receive notifications from the common language runtime (CLR).</span></span>  <span data-ttu-id="27f1f-105">Nabízí funkce není poskytovaný [icorprofilerinfo::geteventmask –](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) metoda.</span><span class="sxs-lookup"><span data-stu-id="27f1f-105">It provides functionality not provided by the [ICorProfilerInfo::GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27f1f-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="27f1f-106">Syntax</span></span>  
  
```cpp
HRESULT GetEventMask2(  
        [out] DWORD* pdwEventsLow,  
        [out] DWORD* pdwEventsHigh  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="27f1f-107">Parametry</span><span class="sxs-lookup"><span data-stu-id="27f1f-107">Parameters</span></span>  
 `pdwEventsLow`  
 <span data-ttu-id="27f1f-108">[out] Ukazatel na hodnotu 4 bajtů, která určuje kategorie události.</span><span class="sxs-lookup"><span data-stu-id="27f1f-108">[out] A pointer to a 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="27f1f-109">Každý bit řídí jinou možnost, chování nebo typ události.</span><span class="sxs-lookup"><span data-stu-id="27f1f-109">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="27f1f-110">Službu bits, jsou popsané v [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) výčtu.</span><span class="sxs-lookup"><span data-stu-id="27f1f-110">The bits are described in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 `pdwEventsHigh`  
 <span data-ttu-id="27f1f-111">[out] Ukazatel na hodnotu 4 bajtů, která určuje kategorie události.</span><span class="sxs-lookup"><span data-stu-id="27f1f-111">[out] A pointer to a 4-byte value that specifies the categories of events.</span></span>  <span data-ttu-id="27f1f-112">Každý bit řídí jinou možnost, chování nebo typ události.</span><span class="sxs-lookup"><span data-stu-id="27f1f-112">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="27f1f-113">Službu bits, jsou popsané v [COR_PRF_HIGH_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) výčtu.</span><span class="sxs-lookup"><span data-stu-id="27f1f-113">The bits are described in the [COR_PRF_HIGH_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="27f1f-114">Poznámky</span><span class="sxs-lookup"><span data-stu-id="27f1f-114">Remarks</span></span>  
 <span data-ttu-id="27f1f-115">`GetEventMask2` Metoda se používá k určení které zpětná volání profileru přihlásí k odběru.</span><span class="sxs-lookup"><span data-stu-id="27f1f-115">The `GetEventMask2` method is used to determine which callbacks the profiler has subscribed to.</span></span> <span data-ttu-id="27f1f-116">Obvykle je provést logickou funkcí nebo `pdwEventsLow` a `pdwEventsHigh` hodnoty a všechny nové bitů, které chcete nastavit a pak zavolají [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) metoda.</span><span class="sxs-lookup"><span data-stu-id="27f1f-116">Typically, you perform a logical OR of the `pdwEventsLow` and `pdwEventsHigh` values and any new bits you want to set, and then call the [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method.</span></span>  
  
 <span data-ttu-id="27f1f-117">Tato metoda je Doporučená alternativa k [geteventmask –](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) metoda.</span><span class="sxs-lookup"><span data-stu-id="27f1f-117">This method is the recommended alternative to the [GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27f1f-118">Požadavky</span><span class="sxs-lookup"><span data-stu-id="27f1f-118">Requirements</span></span>  
 <span data-ttu-id="27f1f-119">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27f1f-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27f1f-120">**Záhlaví:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="27f1f-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="27f1f-121">**Knihovna:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="27f1f-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="27f1f-122">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27f1f-122">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27f1f-123">Viz také</span><span class="sxs-lookup"><span data-stu-id="27f1f-123">See Also</span></span>  
 [<span data-ttu-id="27f1f-124">Rozhraní ICorProfilerInfo5</span><span class="sxs-lookup"><span data-stu-id="27f1f-124">ICorProfilerInfo5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)  
 [<span data-ttu-id="27f1f-125">Metoda SetEventMask2</span><span class="sxs-lookup"><span data-stu-id="27f1f-125">SetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)
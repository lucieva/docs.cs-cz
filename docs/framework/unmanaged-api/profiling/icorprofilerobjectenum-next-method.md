---
title: "ICorProfilerObjectEnum::Next – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerObjectEnum.Next
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerObjectEnum::Next
helpviewer_keywords:
- Next method, ICorProfilerObjectEnum interface [.NET Framework profiling]
- ICorProfilerObjectEnum::Next method [.NET Framework profiling]
ms.assetid: b420433c-5ebe-4986-bba1-97902e6db819
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a82a3c6c3de012db6f187bdd7ea3b9e2eebb86b3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerobjectenumnext-method"></a><span data-ttu-id="ae58b-102">ICorProfilerObjectEnum::Next – metoda</span><span class="sxs-lookup"><span data-stu-id="ae58b-102">ICorProfilerObjectEnum::Next Method</span></span>
<span data-ttu-id="ae58b-103">Získá zadaný počet souvislý objektů z sekvenční kolekcí objektů, počínaje na enumerátor na aktuální pozici v pořadí.</span><span class="sxs-lookup"><span data-stu-id="ae58b-103">Gets the specified number of contiguous objects from a sequential collection of objects, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae58b-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="ae58b-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG                    celt,  
    [out, size_is(celt), length_is(*pceltFetched)]    
        ObjectID                  objects[],  
    [out] ULONG                   *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ae58b-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="ae58b-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="ae58b-106">[v] Počet objektů, které mají být načteny.</span><span class="sxs-lookup"><span data-stu-id="ae58b-106">[in] The number of objects to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="ae58b-107">[out] Pole `ObjectID` hodnoty, z nichž každý představuje načtený objekt.</span><span class="sxs-lookup"><span data-stu-id="ae58b-107">[out] An array of `ObjectID` values, each of which represents a retrieved object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="ae58b-108">[out] Ukazatel na počet elementů ve skutečnosti, vrátí se v `objects` pole.</span><span class="sxs-lookup"><span data-stu-id="ae58b-108">[out] A pointer to the number of elements actually returned in the `objects` array.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae58b-109">Požadavky</span><span class="sxs-lookup"><span data-stu-id="ae58b-109">Requirements</span></span>  
 <span data-ttu-id="ae58b-110">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ae58b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae58b-111">**Záhlaví:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ae58b-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ae58b-112">**Knihovna:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae58b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae58b-113">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae58b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae58b-114">Viz také</span><span class="sxs-lookup"><span data-stu-id="ae58b-114">See Also</span></span>  
 [<span data-ttu-id="ae58b-115">Icorprofilerobjectenum – rozhraní</span><span class="sxs-lookup"><span data-stu-id="ae58b-115">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)
---
title: "COR_PRF_TRANSITION_REASON – výčet"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_TRANSITION_REASON
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_TRANSITION_REASON
helpviewer_keywords: COR_PRF_TRANSITION_REASON enumeration [.NET Framework profiling]
ms.assetid: da941118-01b7-4197-ae5b-9f2f8adcd623
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9f11b5fb5409ee30b0456e0c562545718ed46bb6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="corprftransitionreason-enumeration"></a><span data-ttu-id="27738-102">COR_PRF_TRANSITION_REASON – výčet</span><span class="sxs-lookup"><span data-stu-id="27738-102">COR_PRF_TRANSITION_REASON Enumeration</span></span>
<span data-ttu-id="27738-103">Označuje důvod pro přechod ze spravovaného na nespravovaný kód nebo naopak.</span><span class="sxs-lookup"><span data-stu-id="27738-103">Indicates the reason for a transition from managed to unmanaged code, or vice versa.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27738-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="27738-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_TRANSITION_CALL,  
    COR_PRF_TRANSITION_RETURN  
} COR_PRF_TRANSITION_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="27738-105">Členové</span><span class="sxs-lookup"><span data-stu-id="27738-105">Members</span></span>  
  
|<span data-ttu-id="27738-106">Člen</span><span class="sxs-lookup"><span data-stu-id="27738-106">Member</span></span>|<span data-ttu-id="27738-107">Popis</span><span class="sxs-lookup"><span data-stu-id="27738-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_TRANSITION_CALL`|<span data-ttu-id="27738-108">Přechod je z důvodu volání do funkce.</span><span class="sxs-lookup"><span data-stu-id="27738-108">The transition is due to a call into a function.</span></span>|  
|`COR_PRF_TRANSITION_RETURN`|<span data-ttu-id="27738-109">Přechod je z důvodu vrátit z funkce.</span><span class="sxs-lookup"><span data-stu-id="27738-109">The transition is due to a return from a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="27738-110">Poznámky</span><span class="sxs-lookup"><span data-stu-id="27738-110">Remarks</span></span>  
 <span data-ttu-id="27738-111">Když dojde k přechodu, obdrží profileru [icorprofilercallback::managedtounmanagedtransition –](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md) nebo [icorprofilercallback::unmanagedtomanagedtransition –](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md) zpětné volání, buď z nich poskytuje hodnotu `COR_PRF_TRANSITION_REASON` výčtu k označení důvodu přechodu.</span><span class="sxs-lookup"><span data-stu-id="27738-111">When a transition occurs, the profiler receives an [ICorProfilerCallback::ManagedToUnmanagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md) or [ICorProfilerCallback::UnmanagedToManagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md) callback, either of which provides a value of the `COR_PRF_TRANSITION_REASON` enumeration to indicate the reason for the transition.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27738-112">Požadavky</span><span class="sxs-lookup"><span data-stu-id="27738-112">Requirements</span></span>  
 <span data-ttu-id="27738-113">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27738-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27738-114">**Záhlaví:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="27738-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="27738-115">**Knihovna:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="27738-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="27738-116">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27738-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
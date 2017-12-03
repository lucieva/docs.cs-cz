---
title: "COR_TYPEID – struktura"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_TYPEID
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_TYPEID
helpviewer_keywords: COR_TYPEID structure [.NET Framework debugging]
ms.assetid: 1e172b14-ee22-4943-b3b8-3740e7bdcd2e
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 795dea77ac8dac1e1d22574c23f1e1c13344a71a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="cortypeid-structure"></a><span data-ttu-id="b2b05-102">COR_TYPEID – struktura</span><span class="sxs-lookup"><span data-stu-id="b2b05-102">COR_TYPEID Structure</span></span>
<span data-ttu-id="b2b05-103">Obsahuje identifikátor typu.</span><span class="sxs-lookup"><span data-stu-id="b2b05-103">Contains a type identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2b05-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="b2b05-104">Syntax</span></span>  
  
```  
typedef struct COR_TYPEID{  
    UINT64 token1;  
    UINT64 token2;  
} COR_TYPEID;  
```  
  
## <a name="members"></a><span data-ttu-id="b2b05-105">Členové</span><span class="sxs-lookup"><span data-stu-id="b2b05-105">Members</span></span>  
  
|<span data-ttu-id="b2b05-106">Člen</span><span class="sxs-lookup"><span data-stu-id="b2b05-106">Member</span></span>|<span data-ttu-id="b2b05-107">Popis</span><span class="sxs-lookup"><span data-stu-id="b2b05-107">Description</span></span>|  
|------------|-----------------|  
|`token1`|<span data-ttu-id="b2b05-108">První token.</span><span class="sxs-lookup"><span data-stu-id="b2b05-108">The first token.</span></span>|  
|`token2`|<span data-ttu-id="b2b05-109">Druhý token.</span><span class="sxs-lookup"><span data-stu-id="b2b05-109">The second token.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b2b05-110">Poznámky</span><span class="sxs-lookup"><span data-stu-id="b2b05-110">Remarks</span></span>  
 <span data-ttu-id="b2b05-111">`COR_TYPEID` Struktura je vrácen počet ladění metody, které obsahují informace o objektech být uvolňování paměti.</span><span class="sxs-lookup"><span data-stu-id="b2b05-111">The `COR_TYPEID` structure is returned by a number of debugging methods that provide information about objects to be garbage-collected.</span></span> <span data-ttu-id="b2b05-112">Ho můžete poté předat jako argument jiné ladění metody, které poskytují další informace o této položce.</span><span class="sxs-lookup"><span data-stu-id="b2b05-112">It can then be passed as an argument to other debugging methods that provide additional information about that item.</span></span> <span data-ttu-id="b2b05-113">Například vytyčením [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) objekt, je možné získat jednotlivé [cor_heapobject –](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objekty, které představují jednotlivé objekty na spravované haldě.</span><span class="sxs-lookup"><span data-stu-id="b2b05-113">For example, by enumerating an [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) object, you can retrieve individual [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects that represent individual objects on the managed heap.</span></span> <span data-ttu-id="b2b05-114">Potom můžete předat `COR_TYPEID` z hodnoty `COR_HEAPOBJECT.type` do [icordebugprocess5::gettypefortypeid –](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) metoda pro načtení ICorDebugType objektu, který obsahuje informace o typu o objektu.</span><span class="sxs-lookup"><span data-stu-id="b2b05-114">You can then pass the `COR_TYPEID` value from the `COR_HEAPOBJECT.type` field to the [ICorDebugProcess5::GetTypeForTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) method to retrieve an ICorDebugType object that provides type information about the object.</span></span>  
  
 <span data-ttu-id="b2b05-115">A `COR_TYPEID` objekt má být neprůhledné.</span><span class="sxs-lookup"><span data-stu-id="b2b05-115">A `COR_TYPEID` object is intended to be opaque.</span></span> <span data-ttu-id="b2b05-116">Jeho jednotlivých polí by neměly přístup ani s nimi manipulovat.</span><span class="sxs-lookup"><span data-stu-id="b2b05-116">Its individual fields should not be accessed or manipulated.</span></span> <span data-ttu-id="b2b05-117">Jeho jedinou použijte je jako identifikátor, který je k dispozici jako `out` parametr ve volání metody a který může být naopak předaný do jiné metody, které poskytují další informace.</span><span class="sxs-lookup"><span data-stu-id="b2b05-117">Its sole use is as an identifier that is provided as an `out` parameter in a method call and that can, in turn, be passed to other methods to provide additional information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2b05-118">Požadavky</span><span class="sxs-lookup"><span data-stu-id="b2b05-118">Requirements</span></span>  
 <span data-ttu-id="b2b05-119">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2b05-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2b05-120">**Záhlaví:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b2b05-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b2b05-121">**Knihovna:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2b05-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2b05-122">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2b05-122">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2b05-123">Viz také</span><span class="sxs-lookup"><span data-stu-id="b2b05-123">See Also</span></span>  
 [<span data-ttu-id="b2b05-124">Struktury pro ladění</span><span class="sxs-lookup"><span data-stu-id="b2b05-124">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="b2b05-125">Ladění</span><span class="sxs-lookup"><span data-stu-id="b2b05-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
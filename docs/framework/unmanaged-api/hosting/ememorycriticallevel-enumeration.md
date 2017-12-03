---
title: "EMemoryCriticalLevel – výčet"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EMemoryCriticalLevel
api_location: mscoree.dll
api_type: COM
f1_keywords: EMemoryCriticalLevel
helpviewer_keywords: EMemoryCriticalLevel enumeration [.NET Framework hosting]
ms.assetid: 2ca8a7a2-7b54-4ba3-8e73-277c7df485f3
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b15a6786cb99a64d441d7e05fb91cd8ff0f3af92
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="ememorycriticallevel-enumeration"></a><span data-ttu-id="1d7fd-102">EMemoryCriticalLevel – výčet</span><span class="sxs-lookup"><span data-stu-id="1d7fd-102">EMemoryCriticalLevel Enumeration</span></span>
<span data-ttu-id="1d7fd-103">Obsahuje hodnoty, které označují dopad selhání při přidělování konkrétní paměti bylo vyzváno, ale nemůže být splněna.</span><span class="sxs-lookup"><span data-stu-id="1d7fd-103">Contains values that indicate the impact of a failure when a specific memory allocation has been requested but cannot be satisfied.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d7fd-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="1d7fd-104">Syntax</span></span>  
  
```  
typedef enum {  
    eTaskCritical      = 0,  
    eAppDomainCritical = 1,  
    eProcessCritical   = 2  
} EMemoryCriticalLevel;  
```  
  
## <a name="members"></a><span data-ttu-id="1d7fd-105">Členové</span><span class="sxs-lookup"><span data-stu-id="1d7fd-105">Members</span></span>  
  
|<span data-ttu-id="1d7fd-106">Člen</span><span class="sxs-lookup"><span data-stu-id="1d7fd-106">Member</span></span>|<span data-ttu-id="1d7fd-107">Popis</span><span class="sxs-lookup"><span data-stu-id="1d7fd-107">Description</span></span>|  
|------------|-----------------|  
|`eAppDomainCritical`|<span data-ttu-id="1d7fd-108">Označuje, že je velmi důležitá pro provádění spravovaného kódu v doméně, která vyžaduje přidělení přidělení.</span><span class="sxs-lookup"><span data-stu-id="1d7fd-108">Indicates that the allocation is critical for executing managed code in the domain that has requested the allocation.</span></span> <span data-ttu-id="1d7fd-109">Pokud nelze přidělit paměť, modul CLR nemůže zaručit, že doména je stále možné použít.</span><span class="sxs-lookup"><span data-stu-id="1d7fd-109">If memory cannot be allocated, the CLR cannot guarantee that the domain is still usable.</span></span> <span data-ttu-id="1d7fd-110">Hostitel rozhodne, jaká opatření se mají při přidělování nelze uspokojit.</span><span class="sxs-lookup"><span data-stu-id="1d7fd-110">The host decides what action to take when the allocation cannot be satisfied.</span></span> <span data-ttu-id="1d7fd-111">Ho můžete určit, aby CLR k přerušení `AppDomain` automaticky, nebo umožněte její běžet voláním metod v [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="1d7fd-111">It can instruct the CLR to abort the `AppDomain` automatically, or allow it to keep running by calling methods on [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md).</span></span>|  
|`eProcessCritical`|<span data-ttu-id="1d7fd-112">Označuje, že je důležité pro spuštění spravovaného kódu v procesu přidělení.</span><span class="sxs-lookup"><span data-stu-id="1d7fd-112">Indicates that the allocation is critical to the execution of managed code in the process.</span></span> <span data-ttu-id="1d7fd-113">Tato hodnota se používá během spuštění a při spuštění finalizační metody.</span><span class="sxs-lookup"><span data-stu-id="1d7fd-113">This value is used during startup and when running finalizers.</span></span> <span data-ttu-id="1d7fd-114">Pokud nelze přidělit paměť, modul CLR nemůže pracovat v procesu.</span><span class="sxs-lookup"><span data-stu-id="1d7fd-114">If memory cannot be allocated, the CLR cannot operate in the process.</span></span> <span data-ttu-id="1d7fd-115">V případě selhání přidělení vypnutá efektivně modulu CLR.</span><span class="sxs-lookup"><span data-stu-id="1d7fd-115">If the allocation fails, the CLR is effectively disabled.</span></span> <span data-ttu-id="1d7fd-116">Všechny následující volání do modulu CLR nezdaří s HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="1d7fd-116">All subsequent calls into the CLR fail with HOST_E_CLRNOTAVAILABLE.</span></span>|  
|`eTaskCritical`|<span data-ttu-id="1d7fd-117">Označuje, že je důležité pro spuštění úlohy, která vyžaduje přidělení přidělení.</span><span class="sxs-lookup"><span data-stu-id="1d7fd-117">Indicates that the allocation is critical to running the task that has requested the allocation.</span></span> <span data-ttu-id="1d7fd-118">Pokud nelze přidělit paměť, modul CLR nemůže zaručit, že úlohu můžete spustit.</span><span class="sxs-lookup"><span data-stu-id="1d7fd-118">If memory cannot be allocated, the CLR cannot guarantee that the task can be executed.</span></span> <span data-ttu-id="1d7fd-119">V případě selhání, vyvolá modulu CLR <xref:System.Threading.ThreadAbortException> ve vlákně systému fyzické operaci.</span><span class="sxs-lookup"><span data-stu-id="1d7fd-119">In the event of failure, the CLR raises a <xref:System.Threading.ThreadAbortException> on the physical operation system thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1d7fd-120">Poznámky</span><span class="sxs-lookup"><span data-stu-id="1d7fd-120">Remarks</span></span>  
 <span data-ttu-id="1d7fd-121">Přidělení paměti metody definované v [ihostmemorymanager –](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md) a [ihostmalloc –](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) rozhraní přebírají parametr tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="1d7fd-121">The memory allocation methods defined in the [IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md) and [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) interfaces take a parameter of this type.</span></span> <span data-ttu-id="1d7fd-122">V závislosti na závažnosti selhání se hostitel může rozhodnout, zda selhání požadavek na přidělení okamžitě, nebo počkejte, dokud ho už může obsloužit.</span><span class="sxs-lookup"><span data-stu-id="1d7fd-122">Depending upon the severity of a failure, a host can decide whether to fail the allocation request immediately or to wait until it can be satisfied.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d7fd-123">Požadavky</span><span class="sxs-lookup"><span data-stu-id="1d7fd-123">Requirements</span></span>  
 <span data-ttu-id="1d7fd-124">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d7fd-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d7fd-125">**Záhlaví:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1d7fd-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1d7fd-126">**Knihovna:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1d7fd-126">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1d7fd-127">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d7fd-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d7fd-128">Viz také</span><span class="sxs-lookup"><span data-stu-id="1d7fd-128">See Also</span></span>  
 [<span data-ttu-id="1d7fd-129">Iclrmemorynotificationcallback – rozhraní</span><span class="sxs-lookup"><span data-stu-id="1d7fd-129">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)  
 [<span data-ttu-id="1d7fd-130">Výčty hostování</span><span class="sxs-lookup"><span data-stu-id="1d7fd-130">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
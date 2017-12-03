---
title: "ICLRTask::LocksHeld – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask.LocksHeld
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask::LocksHeld
helpviewer_keywords:
- LocksHeld method [.NET Framework hosting]
- ICLRTask::LocksHeld method [.NET Framework hosting]
ms.assetid: e88a4dc3-02cc-4703-a474-292b71c40657
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2d51fded9f2e475759f2912aea659d272ce08855
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="iclrtasklocksheld-method"></a><span data-ttu-id="637d1-102">ICLRTask::LocksHeld – metoda</span><span class="sxs-lookup"><span data-stu-id="637d1-102">ICLRTask::LocksHeld Method</span></span>
<span data-ttu-id="637d1-103">Získá počet uzamčení aktuálně uchovávat v úloze.</span><span class="sxs-lookup"><span data-stu-id="637d1-103">Gets the number of locks currently held on the task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="637d1-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="637d1-104">Syntax</span></span>  
  
```  
HRESULT LocksHeld (  
    [out] SIZE_T *pLockCount  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="637d1-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="637d1-105">Parameters</span></span>  
 `pLockCount`  
 <span data-ttu-id="637d1-106">[out] Počet uzamčení uchovávat v úloze při volání metody.</span><span class="sxs-lookup"><span data-stu-id="637d1-106">[out] The number of locks held on the task at the time of the method call.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="637d1-107">Návratová hodnota</span><span class="sxs-lookup"><span data-stu-id="637d1-107">Return Value</span></span>  
  
|<span data-ttu-id="637d1-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="637d1-108">HRESULT</span></span>|<span data-ttu-id="637d1-109">Popis</span><span class="sxs-lookup"><span data-stu-id="637d1-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="637d1-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="637d1-110">S_OK</span></span>|<span data-ttu-id="637d1-111">`LocksHeld`úspěšně vrácena.</span><span class="sxs-lookup"><span data-stu-id="637d1-111">`LocksHeld` returned successfully.</span></span>|  
|<span data-ttu-id="637d1-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="637d1-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="637d1-113">Modul CLR (CLR) nebyla načtena do procesu nebo CLR je ve stavu, ve kterém nemůže běžet spravovaného kódu nebo úspěšně zpracovat volání.</span><span class="sxs-lookup"><span data-stu-id="637d1-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="637d1-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="637d1-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="637d1-115">Vypršel časový limit volání.</span><span class="sxs-lookup"><span data-stu-id="637d1-115">The call timed out.</span></span>|  
|<span data-ttu-id="637d1-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="637d1-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="637d1-117">Volající není vlastníkem zámek.</span><span class="sxs-lookup"><span data-stu-id="637d1-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="637d1-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="637d1-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="637d1-119">Událost byla zrušena při blokované vlákna nebo fiber čekal na něm.</span><span class="sxs-lookup"><span data-stu-id="637d1-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="637d1-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="637d1-120">E_FAIL</span></span>|<span data-ttu-id="637d1-121">Došlo k neznámému závažné selhání.</span><span class="sxs-lookup"><span data-stu-id="637d1-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="637d1-122">Po návratu metody E_FAIL modulu CLR již není použitelné v rámci procesu.</span><span class="sxs-lookup"><span data-stu-id="637d1-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="637d1-123">Následující volání hostování metody vrací HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="637d1-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="637d1-124">Požadavky</span><span class="sxs-lookup"><span data-stu-id="637d1-124">Requirements</span></span>  
 <span data-ttu-id="637d1-125">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="637d1-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="637d1-126">**Záhlaví:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="637d1-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="637d1-127">**Knihovna:** zahrnuty jako prostředek v MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="637d1-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="637d1-128">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="637d1-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="637d1-129">Viz také</span><span class="sxs-lookup"><span data-stu-id="637d1-129">See Also</span></span>  
 [<span data-ttu-id="637d1-130">Iclrtask – rozhraní</span><span class="sxs-lookup"><span data-stu-id="637d1-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="637d1-131">Iclrtaskmanager – rozhraní</span><span class="sxs-lookup"><span data-stu-id="637d1-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="637d1-132">Ihosttask – rozhraní</span><span class="sxs-lookup"><span data-stu-id="637d1-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="637d1-133">Ihosttaskmanager – rozhraní</span><span class="sxs-lookup"><span data-stu-id="637d1-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
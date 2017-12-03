---
title: "ICLRRuntimeInfo::IsLoadable – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo.IsLoadable
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo::IsLoadable
helpviewer_keywords:
- IsLoadable method [.NET Framework hosting]
- ICLRRuntimeInfo::IsLoadable method [.NET Framework hosting]
ms.assetid: 205ca53b-e78e-49b2-9a46-2a7823e96b8c
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ada33942af97f476de25c2ea3243818808e2dc9d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimeinfoisloadable-method"></a><span data-ttu-id="07079-102">ICLRRuntimeInfo::IsLoadable – metoda</span><span class="sxs-lookup"><span data-stu-id="07079-102">ICLRRuntimeInfo::IsLoadable Method</span></span>
<span data-ttu-id="07079-103">Určuje, zda modul runtime přidružené toto rozhraní je možné načíst do aktuální proces, vezme v úvahu další moduly runtime, který může být již načtena do procesu.</span><span class="sxs-lookup"><span data-stu-id="07079-103">Indicates whether the runtime associated with this interface can be loaded into the current process, taking into account other runtimes that might already be loaded into the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07079-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="07079-104">Syntax</span></span>  
  
```  
HRESULT IsLoadable(  
        [out, retval] BOOL *pbLoadable);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="07079-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="07079-105">Parameters</span></span>  
 `pbLoadable`  
 <span data-ttu-id="07079-106">[out] `true` Pokud tento modul runtime by mohla být načtena do aktuální proces, jinak hodnota `false`.</span><span class="sxs-lookup"><span data-stu-id="07079-106">[out] `true` if this runtime could be loaded into the current process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="07079-107">Návratová hodnota</span><span class="sxs-lookup"><span data-stu-id="07079-107">Return Value</span></span>  
 <span data-ttu-id="07079-108">Tato metoda vrátí následující konkrétní hodnoty HRESULT a také HRESULT chyby, které označují selhání metoda.</span><span class="sxs-lookup"><span data-stu-id="07079-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="07079-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="07079-109">HRESULT</span></span>|<span data-ttu-id="07079-110">Popis</span><span class="sxs-lookup"><span data-stu-id="07079-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="07079-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="07079-111">S_OK</span></span>|<span data-ttu-id="07079-112">Metoda byla úspěšně dokončena.</span><span class="sxs-lookup"><span data-stu-id="07079-112">The method completed successfully.</span></span>|  
|<span data-ttu-id="07079-113">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="07079-113">E_POINTER</span></span>|<span data-ttu-id="07079-114">`pbLoadable`má hodnotu null.</span><span class="sxs-lookup"><span data-stu-id="07079-114">`pbLoadable` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="07079-115">Poznámky</span><span class="sxs-lookup"><span data-stu-id="07079-115">Remarks</span></span>  
 <span data-ttu-id="07079-116">Pokud jiný modul runtime je již načtena do procesu a v procesu spuštění vedle sebe, mohou být načteny runtime spojené s tímto rozhraním `pbLoadable` vrátí `true`.</span><span class="sxs-lookup"><span data-stu-id="07079-116">If another runtime is already loaded into the process and the runtime associated with this interface can be loaded for in-process side-by-side execution, `pbLoadable` returns `true`.</span></span> <span data-ttu-id="07079-117">Pokud dva moduly Runtime nelze spustit vedle sebe v rámci procesu, `pbLoadable` vrátí `false`.</span><span class="sxs-lookup"><span data-stu-id="07079-117">If the two runtimes cannot run side-by-side in-process, `pbLoadable` returns `false`.</span></span> <span data-ttu-id="07079-118">Modul CLR (CLR) verze 4 můžete například spustit-souběžného v rámci jednoho procesu s CLR verze 2.0 nebo CLR verze 1.1.</span><span class="sxs-lookup"><span data-stu-id="07079-118">For example, the common language runtime (CLR) version 4 can run side-by-side in the same process with CLR version 2.0 or CLR version 1.1.</span></span> <span data-ttu-id="07079-119">Modul CLR verze 1.1 a verze modulu CLR 2.0 však nelze spustit vedle sebe v procesu.</span><span class="sxs-lookup"><span data-stu-id="07079-119">However, CLR version 1.1 and CLR version 2.0 cannot run side-by-side in-process.</span></span>  
  
 <span data-ttu-id="07079-120">Pokud jsou načteny žádné moduly runtime do procesu, tato metoda vždy vrátí `true`.</span><span class="sxs-lookup"><span data-stu-id="07079-120">If no runtimes are loaded into the process, this method always returns `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07079-121">Požadavky</span><span class="sxs-lookup"><span data-stu-id="07079-121">Requirements</span></span>  
 <span data-ttu-id="07079-122">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="07079-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07079-123">**Záhlaví:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="07079-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="07079-124">**Knihovna:** zahrnuty jako prostředek v MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="07079-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="07079-125">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07079-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07079-126">Viz také</span><span class="sxs-lookup"><span data-stu-id="07079-126">See Also</span></span>  
 [<span data-ttu-id="07079-127">Iclrruntimeinfo – rozhraní</span><span class="sxs-lookup"><span data-stu-id="07079-127">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="07079-128">Rozhraní hostování</span><span class="sxs-lookup"><span data-stu-id="07079-128">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="07079-129">Hostování</span><span class="sxs-lookup"><span data-stu-id="07079-129">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
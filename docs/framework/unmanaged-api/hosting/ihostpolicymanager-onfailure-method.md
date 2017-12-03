---
title: "IHostPolicyManager::OnFailure – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostPolicyManager.OnFailure
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostPolicyManager::OnFailure
helpviewer_keywords:
- OnFailure method [.NET Framework hosting]
- IHostPolicyManager::OnFailure method [.NET Framework hosting]
ms.assetid: 77d3f31e-9a53-4349-9c02-610a71736d42
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: dd8c5e071eca6b287b570006f33d7a1a43c1def9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="ihostpolicymanageronfailure-method"></a><span data-ttu-id="b22fd-102">IHostPolicyManager::OnFailure – metoda</span><span class="sxs-lookup"><span data-stu-id="b22fd-102">IHostPolicyManager::OnFailure Method</span></span>
<span data-ttu-id="b22fd-103">Upozorní na hostitele, modul CLR (CLR) se chystá provést akci určenou volání [iclrpolicymanager::setactiononfailure –](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) metoda v reakci na selhání přidělení nebo recyklaci prostředku.</span><span class="sxs-lookup"><span data-stu-id="b22fd-103">Notifies the host that the common language runtime (CLR) is about to take the action specified by a call to the [ICLRPolicyManager::SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) method in response to a resource allocation or reclamation failure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b22fd-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="b22fd-104">Syntax</span></span>  
  
```  
HRESULT OnFailure(  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b22fd-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="b22fd-105">Parameters</span></span>  
 `failure`  
 <span data-ttu-id="b22fd-106">[v] Jeden z [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) hodnoty, která určuje typ selhání, ke kterému modulu CLR odpovídá.</span><span class="sxs-lookup"><span data-stu-id="b22fd-106">[in] One of the [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) values, indicating the kind of failure to which the CLR is responding.</span></span>  
  
 `action`  
 <span data-ttu-id="b22fd-107">[v] Jeden z [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) hodnoty, který udává akci modulu CLR trvá v reakci na `failure`.</span><span class="sxs-lookup"><span data-stu-id="b22fd-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action the CLR is taking in response to `failure`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b22fd-108">Návratová hodnota</span><span class="sxs-lookup"><span data-stu-id="b22fd-108">Return Value</span></span>  
  
|<span data-ttu-id="b22fd-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b22fd-109">HRESULT</span></span>|<span data-ttu-id="b22fd-110">Popis</span><span class="sxs-lookup"><span data-stu-id="b22fd-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b22fd-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="b22fd-111">S_OK</span></span>|<span data-ttu-id="b22fd-112">`OnFailure`úspěšně vrácena.</span><span class="sxs-lookup"><span data-stu-id="b22fd-112">`OnFailure` returned successfully.</span></span>|  
|<span data-ttu-id="b22fd-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b22fd-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b22fd-114">Modul CLR nebyla načtena do procesu nebo CLR je ve stavu, ve kterém nemůže běžet spravovaného kódu nebo úspěšně zpracovat volání.</span><span class="sxs-lookup"><span data-stu-id="b22fd-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b22fd-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b22fd-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b22fd-116">Vypršel časový limit volání.</span><span class="sxs-lookup"><span data-stu-id="b22fd-116">The call timed out.</span></span>|  
|<span data-ttu-id="b22fd-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b22fd-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b22fd-118">Volající není vlastníkem zámek.</span><span class="sxs-lookup"><span data-stu-id="b22fd-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b22fd-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b22fd-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b22fd-120">Událost byla zrušena při blokované vlákna nebo fiber čekal na něm.</span><span class="sxs-lookup"><span data-stu-id="b22fd-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b22fd-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b22fd-121">E_FAIL</span></span>|<span data-ttu-id="b22fd-122">Došlo k neznámému závažné selhání.</span><span class="sxs-lookup"><span data-stu-id="b22fd-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b22fd-123">Po návratu metody E_FAIL modulu CLR již není použitelné v rámci procesu.</span><span class="sxs-lookup"><span data-stu-id="b22fd-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b22fd-124">Následující volání hostování metody vrací HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b22fd-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b22fd-125">Požadavky</span><span class="sxs-lookup"><span data-stu-id="b22fd-125">Requirements</span></span>  
 <span data-ttu-id="b22fd-126">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b22fd-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b22fd-127">**Záhlaví:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b22fd-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b22fd-128">**Knihovna:** zahrnuty jako prostředek v MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b22fd-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b22fd-129">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b22fd-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b22fd-130">Viz také</span><span class="sxs-lookup"><span data-stu-id="b22fd-130">See Also</span></span>  
 [<span data-ttu-id="b22fd-131">EClrFailure – výčet</span><span class="sxs-lookup"><span data-stu-id="b22fd-131">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [<span data-ttu-id="b22fd-132">EPolicyAction – výčet</span><span class="sxs-lookup"><span data-stu-id="b22fd-132">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [<span data-ttu-id="b22fd-133">ICLRPolicyManager – rozhraní</span><span class="sxs-lookup"><span data-stu-id="b22fd-133">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [<span data-ttu-id="b22fd-134">Ihostpolicymanager – rozhraní</span><span class="sxs-lookup"><span data-stu-id="b22fd-134">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
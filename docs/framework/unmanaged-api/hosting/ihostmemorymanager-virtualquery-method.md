---
title: "IHostMemoryManager::VirtualQuery – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMemoryManager.VirtualQuery
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMemoryManager::VirtualQuery
helpviewer_keywords:
- IHostMemoryManager::VirtualQuery method [.NET Framework hosting]
- VirtualQuery method [.NET Framework hosting]
ms.assetid: 757af1e6-b9e8-49e7-b5db-342be3aa205f
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 82c76ce908dd73fba0a2a0039894f51790b46583
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="ihostmemorymanagervirtualquery-method"></a><span data-ttu-id="1383e-102">IHostMemoryManager::VirtualQuery – metoda</span><span class="sxs-lookup"><span data-stu-id="1383e-102">IHostMemoryManager::VirtualQuery Method</span></span>
<span data-ttu-id="1383e-103">Slouží jako logické obálku pro odpovídající funkci Win32.</span><span class="sxs-lookup"><span data-stu-id="1383e-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="1383e-104">Implementace Win32 `VirtualQuery` načte informace o rozsahu stránek ve virtuálním adresním prostoru procesu volání.</span><span class="sxs-lookup"><span data-stu-id="1383e-104">The Win32 implementation of `VirtualQuery` retrieves information about a range of pages in the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1383e-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="1383e-105">Syntax</span></span>  
  
```  
HRESULT VirtualQuery (  
    [in]  void*    lpAddress,  
    [out] void*    lpBuffer,  
    [in]  SIZE_T   dwLength,  
    [out] SIZE_T*  pResult  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1383e-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="1383e-106">Parameters</span></span>  
 `lpAddress`  
 <span data-ttu-id="1383e-107">[v] Ukazatel na adresu ve virtuální paměti, které má být dotazován.</span><span class="sxs-lookup"><span data-stu-id="1383e-107">[in] A pointer to the address in virtual memory to be queried.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="1383e-108">[out] Ukazatel na strukturu, která obsahuje informace o určenou oblast paměti.</span><span class="sxs-lookup"><span data-stu-id="1383e-108">[out] A pointer to a structure that contains information about the specified memory region.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="1383e-109">[v] Velikost v bajtech vyrovnávací paměti, `lpBuffer` odkazuje na.</span><span class="sxs-lookup"><span data-stu-id="1383e-109">[in] The size, in bytes, of the buffer that `lpBuffer` points to.</span></span>  
  
 `pResult`  
 <span data-ttu-id="1383e-110">[out] Ukazatel na počet bajtů vrácený informace vyrovnávací paměti.</span><span class="sxs-lookup"><span data-stu-id="1383e-110">[out] A pointer to the number of bytes returned by the information buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1383e-111">Návratová hodnota</span><span class="sxs-lookup"><span data-stu-id="1383e-111">Return Value</span></span>  
  
|<span data-ttu-id="1383e-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1383e-112">HRESULT</span></span>|<span data-ttu-id="1383e-113">Popis</span><span class="sxs-lookup"><span data-stu-id="1383e-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1383e-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="1383e-114">S_OK</span></span>|<span data-ttu-id="1383e-115">`VirtualQuery`úspěšně vrácena.</span><span class="sxs-lookup"><span data-stu-id="1383e-115">`VirtualQuery` returned successfully.</span></span>|  
|<span data-ttu-id="1383e-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1383e-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1383e-117">Modul CLR (CLR) nebyla načtena do procesu nebo CLR je ve stavu, ve kterém nemůže běžet spravovaného kódu nebo úspěšně zpracovat volání.</span><span class="sxs-lookup"><span data-stu-id="1383e-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1383e-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1383e-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1383e-119">Vypršel časový limit volání.</span><span class="sxs-lookup"><span data-stu-id="1383e-119">The call timed out.</span></span>|  
|<span data-ttu-id="1383e-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1383e-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1383e-121">Volající není vlastníkem zámek.</span><span class="sxs-lookup"><span data-stu-id="1383e-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1383e-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1383e-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1383e-123">Událost byla zrušena při blokované vlákna nebo fiber čekal na něm.</span><span class="sxs-lookup"><span data-stu-id="1383e-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1383e-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1383e-124">E_FAIL</span></span>|<span data-ttu-id="1383e-125">Došlo k neznámému závažné selhání.</span><span class="sxs-lookup"><span data-stu-id="1383e-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1383e-126">Po návratu metody E_FAIL modulu CLR již není použitelné v rámci procesu.</span><span class="sxs-lookup"><span data-stu-id="1383e-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1383e-127">Následující volání hostování metody vrací HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="1383e-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1383e-128">Poznámky</span><span class="sxs-lookup"><span data-stu-id="1383e-128">Remarks</span></span>  
 <span data-ttu-id="1383e-129">`VirtualQuery`poskytuje informace o rozsahu stránek ve virtuálním adresním prostoru procesu volání.</span><span class="sxs-lookup"><span data-stu-id="1383e-129">`VirtualQuery` provides information about a range of pages in the virtual address space of the calling process.</span></span> <span data-ttu-id="1383e-130">Tato implementace nastaví hodnotu `pResult` parametru počet bajtů ve vyrovnávací paměti informace vrátí a vrací hodnotu HRESULT.</span><span class="sxs-lookup"><span data-stu-id="1383e-130">This implementation sets the value of the `pResult` parameter to the number of bytes returned in the information buffer, and returns an HRESULT value.</span></span> <span data-ttu-id="1383e-131">V Win32 `VirtualQuery` velikost vyrovnávací paměti je funkce, návratovou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="1383e-131">In the Win32 `VirtualQuery` function, the return value is the buffer size.</span></span> <span data-ttu-id="1383e-132">Další informace najdete v dokumentaci k platformě Windows.</span><span class="sxs-lookup"><span data-stu-id="1383e-132">For more information, see the Windows Platform documentation.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1383e-133">Operační systém implementace `VirtualQuery` nedojde zablokování a na dokončení můžete spustit s náhodných vláken pozastavenou uživatelského kódu.</span><span class="sxs-lookup"><span data-stu-id="1383e-133">The operating system's implementation of `VirtualQuery` does not incur deadlock and can run to completion with random threads suspended in user code.</span></span> <span data-ttu-id="1383e-134">Použijte opatrní při implementaci hostované verze této metody.</span><span class="sxs-lookup"><span data-stu-id="1383e-134">Use great caution when implementing a hosted version of this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1383e-135">Požadavky</span><span class="sxs-lookup"><span data-stu-id="1383e-135">Requirements</span></span>  
 <span data-ttu-id="1383e-136">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1383e-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1383e-137">**Záhlaví:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1383e-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1383e-138">**Knihovna:** zahrnuty jako prostředek v MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1383e-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1383e-139">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1383e-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1383e-140">Viz také</span><span class="sxs-lookup"><span data-stu-id="1383e-140">See Also</span></span>  
 [<span data-ttu-id="1383e-141">Ihostmemorymanager – rozhraní</span><span class="sxs-lookup"><span data-stu-id="1383e-141">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
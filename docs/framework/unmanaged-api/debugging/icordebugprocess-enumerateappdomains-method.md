---
title: "ICorDebugProcess::EnumerateAppDomains – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess.EnumerateAppDomains
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess::EnumerateAppDomains
helpviewer_keywords:
- ICorDebugProcess::EnumerateAppDomains method [.NET Framework debugging]
- EnumerateAppDomains method [.NET Framework debugging]
ms.assetid: d508981f-e2b2-445b-a649-69951c22702d
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5233dd80750afb82a2e2a8e9675867f6decfa8f4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugprocessenumerateappdomains-method"></a><span data-ttu-id="f9141-102">ICorDebugProcess::EnumerateAppDomains – metoda</span><span class="sxs-lookup"><span data-stu-id="f9141-102">ICorDebugProcess::EnumerateAppDomains Method</span></span>
<span data-ttu-id="f9141-103">Zobrazí všechny domény aplikace v tomto procesu.</span><span class="sxs-lookup"><span data-stu-id="f9141-103">Enumerates all the application domains in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9141-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="f9141-104">Syntax</span></span>  
  
```  
HRESULT EnumerateAppDomains(  
    [out] ICorDebugAppDomainEnum **ppAppDomains);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f9141-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="f9141-105">Parameters</span></span>  
 `ppAppDomains`  
 <span data-ttu-id="f9141-106">[out] Ukazatel na adresu [ICorDebugAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-interface.md) tedy enumerátor pro aplikační domény v tomto procesu.</span><span class="sxs-lookup"><span data-stu-id="f9141-106">[out] A pointer to the address of an [ICorDebugAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-interface.md) that is an enumerator for the application domains in this process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f9141-107">Poznámky</span><span class="sxs-lookup"><span data-stu-id="f9141-107">Remarks</span></span>  
 <span data-ttu-id="f9141-108">Tuto metodu můžete použít před [icordebugmanagedcallback::CreateProcess –](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) zpětného volání.</span><span class="sxs-lookup"><span data-stu-id="f9141-108">This method can be used before the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9141-109">Požadavky</span><span class="sxs-lookup"><span data-stu-id="f9141-109">Requirements</span></span>  
 <span data-ttu-id="f9141-110">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9141-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9141-111">**Záhlaví:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f9141-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f9141-112">**Knihovna:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f9141-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f9141-113">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9141-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
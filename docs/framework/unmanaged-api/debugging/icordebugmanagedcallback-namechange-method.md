---
title: "ICorDebugManagedCallback::NameChange – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.NameChange
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::NameChange
helpviewer_keywords:
- ICorDebugManagedCallback::NameChange method [.NET Framework debugging]
- NameChange method [.NET Framework debugging]
ms.assetid: a7018a0e-880e-4b68-b52a-1cd22c7aad62
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f9ce32a68354c6bef43dfb55395cb6f9bb136dca
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmanagedcallbacknamechange-method"></a><span data-ttu-id="0aa9d-102">ICorDebugManagedCallback::NameChange – metoda</span><span class="sxs-lookup"><span data-stu-id="0aa9d-102">ICorDebugManagedCallback::NameChange Method</span></span>
<span data-ttu-id="0aa9d-103">Upozorní ladicí program, že došlo ke změně názvu domény aplikace nebo vlákna.</span><span class="sxs-lookup"><span data-stu-id="0aa9d-103">Notifies the debugger that the name of either an application domain or a thread has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0aa9d-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="0aa9d-104">Syntax</span></span>  
  
```  
HRESULT NameChange (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0aa9d-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="0aa9d-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="0aa9d-106">[v] Ukazatel na ICorDebugAppDomain objekt, který reprezentuje doméně aplikace, která buď měl změnu názvu nebo který obsahuje vláken, která měla změnit název.</span><span class="sxs-lookup"><span data-stu-id="0aa9d-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that either had a name change or that contains the thread that had a name change.</span></span>  
  
 `pThread`  
 <span data-ttu-id="0aa9d-107">[v] Ukazatel na ICorDebugThread objekt, který reprezentuje vláken, která měla změnit název.</span><span class="sxs-lookup"><span data-stu-id="0aa9d-107">[in] A pointer to an ICorDebugThread object that represents the thread that had a name change.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0aa9d-108">Požadavky</span><span class="sxs-lookup"><span data-stu-id="0aa9d-108">Requirements</span></span>  
 <span data-ttu-id="0aa9d-109">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0aa9d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0aa9d-110">**Záhlaví:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0aa9d-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0aa9d-111">**Knihovna:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0aa9d-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0aa9d-112">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0aa9d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0aa9d-113">Viz také</span><span class="sxs-lookup"><span data-stu-id="0aa9d-113">See Also</span></span>  
 [<span data-ttu-id="0aa9d-114">ICorDebugManagedCallback – rozhraní rozhraní</span><span class="sxs-lookup"><span data-stu-id="0aa9d-114">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
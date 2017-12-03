---
title: "ICorDebugManagedCallback::LoadModule – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.LoadModule
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::LoadModule
helpviewer_keywords:
- ICorDebugManagedCallback::LoadModule method [.NET Framework debugging]
- LoadModule method [.NET Framework debugging]
ms.assetid: 66ec04e9-87cb-42ce-9720-81522abb5d5a
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7d133bffdf98306c17bb223dc25e84d6bf9e2ce2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmanagedcallbackloadmodule-method"></a><span data-ttu-id="77877-102">ICorDebugManagedCallback::LoadModule – metoda</span><span class="sxs-lookup"><span data-stu-id="77877-102">ICorDebugManagedCallback::LoadModule Method</span></span>
<span data-ttu-id="77877-103">Upozorní ladicí program úspěšně načtena společný modul runtime (CLR) jazyk.</span><span class="sxs-lookup"><span data-stu-id="77877-103">Notifies the debugger that a common language runtime (CLR) module has been successfully loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77877-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="77877-104">Syntax</span></span>  
  
```  
HRESULT LoadModule (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugModule    *pModule  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="77877-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="77877-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="77877-106">[v] Ukazatel na ICorDebugAppDomain objekt, který představuje doménu aplikace, do kterého se načetl modul.</span><span class="sxs-lookup"><span data-stu-id="77877-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the module has been loaded.</span></span>  
  
 `pModule`  
 <span data-ttu-id="77877-107">[v] Ukazatel na ICorDebugModule objekt, který reprezentuje modulu CLR.</span><span class="sxs-lookup"><span data-stu-id="77877-107">[in] A pointer to an ICorDebugModule object that represents the CLR module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="77877-108">Poznámky</span><span class="sxs-lookup"><span data-stu-id="77877-108">Remarks</span></span>  
 <span data-ttu-id="77877-109">`LoadModule` Zpětné volání poskytuje příslušnou dobu prozkoumat metadata pro modul, nastavte příznaky kompilátoru za běhu (JIT), nebo povolit nebo zakázat třídy načítání zpětných volání pro modul.</span><span class="sxs-lookup"><span data-stu-id="77877-109">The `LoadModule` callback provides an appropriate time to examine metadata for the module, set just-in-time (JIT) compiler flags, or enable or disable class loading callbacks for the module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77877-110">Požadavky</span><span class="sxs-lookup"><span data-stu-id="77877-110">Requirements</span></span>  
 <span data-ttu-id="77877-111">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77877-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77877-112">**Záhlaví:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="77877-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="77877-113">**Knihovna:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="77877-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="77877-114">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77877-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77877-115">Viz také</span><span class="sxs-lookup"><span data-stu-id="77877-115">See Also</span></span>  
 [<span data-ttu-id="77877-116">Unloadmodule – metoda</span><span class="sxs-lookup"><span data-stu-id="77877-116">UnloadModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadmodule-method.md)  
 [<span data-ttu-id="77877-117">ICorDebugManagedCallback – rozhraní rozhraní</span><span class="sxs-lookup"><span data-stu-id="77877-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
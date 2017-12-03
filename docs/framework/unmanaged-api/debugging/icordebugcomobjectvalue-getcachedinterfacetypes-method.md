---
title: "ICorDebugComObjectValue::GetCachedInterfaceTypes – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugComObjectValue::GetCachedInterfaceTypes
api_location: mscordbi.dll
f1_keywords: ICorDebugComObjectValue::GetCachedInterfaceTypes
helpviewer_keywords:
- GetCachedInterface method, ICorDebugComObjectValue interface [.NET Framework debugging]
- ICorDebugComObjectValue::GetCachedInterface method [.NET Framework debugging]
ms.assetid: d492284f-d3c5-4614-adb8-d718d5042500
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2150e75b5b9f09424f08c29345d5d139c1673afa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugcomobjectvaluegetcachedinterfacetypes-method"></a><span data-ttu-id="44bdf-102">ICorDebugComObjectValue::GetCachedInterfaceTypes – metoda</span><span class="sxs-lookup"><span data-stu-id="44bdf-102">ICorDebugComObjectValue::GetCachedInterfaceTypes Method</span></span>
<span data-ttu-id="44bdf-103">Poskytuje enumerátor pro typy rozhraní, že byla přetypovat nebo použít jako aktuální objekt.</span><span class="sxs-lookup"><span data-stu-id="44bdf-103">Provides an enumerator for the interface types that the current object has been cast to or used as.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44bdf-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="44bdf-104">Syntax</span></span>  
  
```  
HRESULT GetCachedInterfaceTypes(  
    [in] BOOL bIInspectableOnly,  
    [out] ICorDebugTypeEnum **ppInterfacesEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="44bdf-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="44bdf-105">Parameters</span></span>  
 `bIInspectableOnly`  
 <span data-ttu-id="44bdf-106">[v] Hodnotu, která určuje, zda metoda vrátí pouze [!INCLUDE[wrt](../../../../includes/wrt-md.md)] rozhraní (`IInspectable` rozhraní) nebo všech rozhraní COM mezipaměti obálka volatelná za běhu (RCW).</span><span class="sxs-lookup"><span data-stu-id="44bdf-106">[in] A value that indicates whether the method returns only [!INCLUDE[wrt](../../../../includes/wrt-md.md)] interfaces (`IInspectable` interfaces) or all COM interfaces cached by the runtime callable wrapper (RCW).</span></span>  
  
 `ppInterfacesEnum`  
 <span data-ttu-id="44bdf-107">[out] Ukazatel na adresu enumerátor ICorDebugTypeEnum, který poskytuje přístup k objektům ICorDebugType, které reprezentují typy v mezipaměti rozhraní filtrovaná podle `bIInspectableOnly`.</span><span class="sxs-lookup"><span data-stu-id="44bdf-107">[out] A pointer to the address of an ICorDebugTypeEnum enumerator that provides access to ICorDebugType objects that represent cached interface types filtered according to `bIInspectableOnly`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44bdf-108">Poznámky</span><span class="sxs-lookup"><span data-stu-id="44bdf-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44bdf-109">Požadavky</span><span class="sxs-lookup"><span data-stu-id="44bdf-109">Requirements</span></span>  
 <span data-ttu-id="44bdf-110">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44bdf-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44bdf-111">**Záhlaví:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="44bdf-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="44bdf-112">**Knihovna:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="44bdf-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="44bdf-113">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44bdf-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44bdf-114">Viz také</span><span class="sxs-lookup"><span data-stu-id="44bdf-114">See Also</span></span>  
 [<span data-ttu-id="44bdf-115">ICorDebugComObjectValue – rozhraní rozhraní</span><span class="sxs-lookup"><span data-stu-id="44bdf-115">ICorDebugComObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-interface.md)  
 [<span data-ttu-id="44bdf-116">Ladění v rozhraní</span><span class="sxs-lookup"><span data-stu-id="44bdf-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
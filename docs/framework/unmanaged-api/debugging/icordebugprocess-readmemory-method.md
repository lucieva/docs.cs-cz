---
title: "ICorDebugProcess::ReadMemory – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess.ReadMemory
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess::ReadMemory
helpviewer_keywords:
- ReadMemory method [.NET Framework debugging]
- ICorDebugProcess::ReadMemory method [.NET Framework debugging]
ms.assetid: 28e4b2f6-9589-445c-be24-24a3306795e7
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 33345ada6606bc1a43a630340251d3ba1404b2f2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugprocessreadmemory-method"></a><span data-ttu-id="32d7a-102">ICorDebugProcess::ReadMemory – metoda</span><span class="sxs-lookup"><span data-stu-id="32d7a-102">ICorDebugProcess::ReadMemory Method</span></span>
<span data-ttu-id="32d7a-103">Přečte zadaný oblasti paměti pro tento proces.</span><span class="sxs-lookup"><span data-stu-id="32d7a-103">Reads a specified area of memory for this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32d7a-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="32d7a-104">Syntax</span></span>  
  
```  
HRESULT ReadMemory(  
    [in]  CORDB_ADDRESS address,   
    [in]  DWORD size,  
    [out, size_is(size), length_is(size)] BYTE buffer[],  
    [out] SIZE_T *read);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="32d7a-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="32d7a-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="32d7a-106">[v] A `CORDB_ADDRESS` hodnotu, která určuje základní adresu paměti čtení.</span><span class="sxs-lookup"><span data-stu-id="32d7a-106">[in] A `CORDB_ADDRESS` value that specifies the base address of the memory to be read.</span></span>  
  
 `size`  
 <span data-ttu-id="32d7a-107">[v] Počet bajtů ke čtení z paměti.</span><span class="sxs-lookup"><span data-stu-id="32d7a-107">[in] The number of bytes to be read from memory.</span></span>  
  
 `buffer`  
 <span data-ttu-id="32d7a-108">[out] Vyrovnávací paměť, která přijímá obsah paměti.</span><span class="sxs-lookup"><span data-stu-id="32d7a-108">[out] A buffer that receives the contents of the memory.</span></span>  
  
 `read`  
 <span data-ttu-id="32d7a-109">[out] Ukazatel na počet bajtů přenesených do zadané vyrovnávací paměti.</span><span class="sxs-lookup"><span data-stu-id="32d7a-109">[out] A pointer to the number of bytes transferred into the specified buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="32d7a-110">Poznámky</span><span class="sxs-lookup"><span data-stu-id="32d7a-110">Remarks</span></span>  
 <span data-ttu-id="32d7a-111">`ReadMemory` Metoda je primárně určen pro použití pomocí zprostředkovatele komunikace s objekty ladění kontrola oblasti paměti, které jsou používány nespravované část ladění.</span><span class="sxs-lookup"><span data-stu-id="32d7a-111">The `ReadMemory` method is primarily intended to be used by interop debugging to inspect memory regions that are being used by the unmanaged portion of the debuggee.</span></span> <span data-ttu-id="32d7a-112">Tuto metodu můžete také použít ke čtení kód Microsoft intermediate language (MSIL) a nativní kód kompilována.</span><span class="sxs-lookup"><span data-stu-id="32d7a-112">This method can also be used to read Microsoft intermediate language (MSIL) code and native JIT-compiled code.</span></span>  
  
 <span data-ttu-id="32d7a-113">Všechny spravované zarážky se odebere z data, která je vrácena v `buffer` parametr.</span><span class="sxs-lookup"><span data-stu-id="32d7a-113">Any managed breakpoints will be removed from the data that is returned in the `buffer` parameter.</span></span> <span data-ttu-id="32d7a-114">Bez úprav budou provedeny pro nativní zarážky nastaven [icordebugprocess2::setunmanagedbreakpoint –](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).</span><span class="sxs-lookup"><span data-stu-id="32d7a-114">No adjustments will be made for native breakpoints set by [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).</span></span>  
  
 <span data-ttu-id="32d7a-115">Neprobíhá žádná ukládání do mezipaměti v paměti procesu.</span><span class="sxs-lookup"><span data-stu-id="32d7a-115">No caching of process memory is performed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32d7a-116">Požadavky</span><span class="sxs-lookup"><span data-stu-id="32d7a-116">Requirements</span></span>  
 <span data-ttu-id="32d7a-117">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="32d7a-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32d7a-118">**Záhlaví:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="32d7a-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="32d7a-119">**Knihovna:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="32d7a-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="32d7a-120">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32d7a-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
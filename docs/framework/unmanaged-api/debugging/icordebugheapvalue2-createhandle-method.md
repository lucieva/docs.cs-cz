---
title: "ICorDebugHeapValue2::CreateHandle – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugHeapValue2.CreateHandle
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugHeapValue2::CreateHandle
helpviewer_keywords:
- CreateHandle method [.NET Framework debugging]
- ICorDebugHeapValue2::CreateHandle method [.NET Framework debugging]
ms.assetid: fbc418e8-fa22-420d-84ec-e0e1800db041
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7feef9af174a63976729f91b5a0b4967fea55b23
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugheapvalue2createhandle-method"></a><span data-ttu-id="b11b3-102">ICorDebugHeapValue2::CreateHandle – metoda</span><span class="sxs-lookup"><span data-stu-id="b11b3-102">ICorDebugHeapValue2::CreateHandle Method</span></span>
<span data-ttu-id="b11b3-103">Vytvoří zadaného typu pro hodnotu halda představuje tento objekt icordebugheapvalue2 – popisovač.</span><span class="sxs-lookup"><span data-stu-id="b11b3-103">Creates a handle of the specified type for the heap value represented by this ICorDebugHeapValue2 object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b11b3-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="b11b3-104">Syntax</span></span>  
  
```  
HRESULT CreateHandle (  
    [in] CorDebugHandleType      type,   
    [out] ICorDebugHandleValue   **ppHandle  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b11b3-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="b11b3-105">Parameters</span></span>  
 `type`  
 <span data-ttu-id="b11b3-106">[v] Hodnota CorDebugHandleType – výčet, který určuje typ popisovače, který se má vytvořit.</span><span class="sxs-lookup"><span data-stu-id="b11b3-106">[in] A value of the CorDebugHandleType enumeration that specifies the type of handle to be created.</span></span>  
  
 `ppHandle`  
 <span data-ttu-id="b11b3-107">[out] Ukazatel na adresu icordebughandlevalue – objekt, který představuje nový popisovač pro tuto hodnotu haldy.</span><span class="sxs-lookup"><span data-stu-id="b11b3-107">[out] A pointer to the address of an ICorDebugHandleValue object that represents the new handle for this heap value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b11b3-108">Poznámky</span><span class="sxs-lookup"><span data-stu-id="b11b3-108">Remarks</span></span>  
 <span data-ttu-id="b11b3-109">Popisovač budou vytvořeny v doméně aplikace, která je přidružená hodnota haldy a se zneplatní. Pokud doménu aplikace získá odpojen.</span><span class="sxs-lookup"><span data-stu-id="b11b3-109">The handle will be created in the application domain that is associated with the heap value, and will become invalid if the application domain gets unloaded.</span></span>  
  
 <span data-ttu-id="b11b3-110">Více volání této funkce pro stejnou hodnotu haldy vytvoří více obslužných rutin.</span><span class="sxs-lookup"><span data-stu-id="b11b3-110">Multiple calls to this function for the same heap value will create multiple handles.</span></span> <span data-ttu-id="b11b3-111">Protože popisovače vliv na výkon systému uvolňování paměti, měli omezit ladicího programu samotné relativně malý počet popisovače (o 256), které jsou aktivní v čase.</span><span class="sxs-lookup"><span data-stu-id="b11b3-111">Because handles affect the performance of the garbage collector, the debugger should limit itself to a relatively small number of handles (about 256) that are active at a time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b11b3-112">Požadavky</span><span class="sxs-lookup"><span data-stu-id="b11b3-112">Requirements</span></span>  
 <span data-ttu-id="b11b3-113">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b11b3-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b11b3-114">**Záhlaví:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b11b3-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b11b3-115">**Knihovna:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b11b3-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b11b3-116">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b11b3-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
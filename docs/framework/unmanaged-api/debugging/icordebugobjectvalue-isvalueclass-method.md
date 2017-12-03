---
title: "ICorDebugObjectValue::IsValueClass – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugObjectValue.IsValueClass
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugObjectValue::IsValueClass
helpviewer_keywords:
- ICorDebugObjectValue::IsValueClass method [.NET Framework debugging]
- IsValueClass method [.NET Framework debugging]
ms.assetid: 13d89a4a-5d9d-4a79-9600-5e2a98c3d166
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b504a9fe28ee72ae8a394359f1f1ef51e7d9d3af
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugobjectvalueisvalueclass-method"></a><span data-ttu-id="42dd6-102">ICorDebugObjectValue::IsValueClass – metoda</span><span class="sxs-lookup"><span data-stu-id="42dd6-102">ICorDebugObjectValue::IsValueClass Method</span></span>
<span data-ttu-id="42dd6-103">Získá hodnotu, která určuje, zda hodnota tohoto objektu je typ hodnoty.</span><span class="sxs-lookup"><span data-stu-id="42dd6-103">Gets a value that indicates whether this object value is a value type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42dd6-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="42dd6-104">Syntax</span></span>  
  
```  
HRESULT IsValueClass (  
    [out] BOOL               *pbIsValueClass  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="42dd6-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="42dd6-105">Parameters</span></span>  
 `pbIsValueClass`  
 <span data-ttu-id="42dd6-106">[out] Ukazatel na logickou hodnotu, která je `true` Pokud hodnoty objektu, která je reprezentována tento "ICorDebugObjectValue", je hodnota typu místo odkazového typu; v opačném `pbIsValueClass` je `false`.</span><span class="sxs-lookup"><span data-stu-id="42dd6-106">[out] A pointer to a Boolean value that is `true` if the object value, represented by this "ICorDebugObjectValue", is a value type rather than a reference type; otherwise, `pbIsValueClass` is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42dd6-107">Požadavky</span><span class="sxs-lookup"><span data-stu-id="42dd6-107">Requirements</span></span>  
 <span data-ttu-id="42dd6-108">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42dd6-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42dd6-109">**Záhlaví:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="42dd6-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="42dd6-110">**Knihovna:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="42dd6-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="42dd6-111">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42dd6-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42dd6-112">Viz také</span><span class="sxs-lookup"><span data-stu-id="42dd6-112">See Also</span></span>  
    
 
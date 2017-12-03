---
title: "ICLRDataTarget::GetTLSValue – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataTarget.GetTLSValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataTarget::GetTLSValue
helpviewer_keywords:
- GetTLSValue method [.NET Framework debugging]
- ICLRDataTarget::GetTLSValue method [.NET Framework debugging]
ms.assetid: 0d8a7730-edc9-4728-898f-41b219cf5a28
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a820ec7c0a00306266be432a8aceacb3d30d1b4f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="iclrdatatargetgettlsvalue-method"></a><span data-ttu-id="0a498-102">ICLRDataTarget::GetTLSValue – metoda</span><span class="sxs-lookup"><span data-stu-id="0a498-102">ICLRDataTarget::GetTLSValue Method</span></span>
<span data-ttu-id="0a498-103">Získá hodnotu z úložiště thread local (TLS) zadaný vlákna v tento cílový proces.</span><span class="sxs-lookup"><span data-stu-id="0a498-103">Gets a value from the thread local storage (TLS) of the specified thread in the target process.</span></span> <span data-ttu-id="0a498-104">Tato metoda je volána běžné data přístupu služby modulu runtime (CLR) jazyk.</span><span class="sxs-lookup"><span data-stu-id="0a498-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a498-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="0a498-105">Syntax</span></span>  
  
```  
HRESULT GetTLSValue (  
    [in] ULONG32            threadID,  
    [in] ULONG32            index,  
    [out] CLRDATA_ADDRESS   *value  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0a498-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="0a498-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="0a498-107">[v] Identifikátor operačního systému vlákna v tento cílový proces.</span><span class="sxs-lookup"><span data-stu-id="0a498-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `index`  
 <span data-ttu-id="0a498-108">[v] Index umístění.</span><span class="sxs-lookup"><span data-stu-id="0a498-108">[in] The index of the location.</span></span> <span data-ttu-id="0a498-109">Tato hodnota musí být platný index v místním úložišti zadaný vlákno.</span><span class="sxs-lookup"><span data-stu-id="0a498-109">This value must be a valid index in the local store of the specified thread.</span></span>  
  
 `value`  
 <span data-ttu-id="0a498-110">[out] Ukazatel na `CLRDATA_ADDRESS` hodnotu, která určuje hodnota vrácená z daného umístění TLS.</span><span class="sxs-lookup"><span data-stu-id="0a498-110">[out] A pointer to a `CLRDATA_ADDRESS` value that specifies the value returned from the given TLS location.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0a498-111">Poznámky</span><span class="sxs-lookup"><span data-stu-id="0a498-111">Remarks</span></span>  
 <span data-ttu-id="0a498-112">Tato metoda je implementována zapisovačem ladění aplikace.</span><span class="sxs-lookup"><span data-stu-id="0a498-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a498-113">Požadavky</span><span class="sxs-lookup"><span data-stu-id="0a498-113">Requirements</span></span>  
 <span data-ttu-id="0a498-114">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0a498-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a498-115">**Záhlaví:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="0a498-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="0a498-116">**Knihovna:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0a498-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0a498-117">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a498-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a498-118">Viz také</span><span class="sxs-lookup"><span data-stu-id="0a498-118">See Also</span></span>  
 [<span data-ttu-id="0a498-119">ICLRDataTarget – rozhraní rozhraní</span><span class="sxs-lookup"><span data-stu-id="0a498-119">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
---
title: "ICLRDataEnumMemoryRegionsCallback – rozhraní"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataEnumMemoryRegionsCallback
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataEnumMemoryRegionsCallback
helpviewer_keywords: ICLRDataEnumMemoryRegionsCallback interface [.NET Framework debugging]
ms.assetid: 3f1af8b0-8478-48e0-a7ec-3e90e0b97649
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 40e51bfc176d8be6b008bc4274c0933253d7be3a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="iclrdataenummemoryregionscallback-interface"></a><span data-ttu-id="50999-102">ICLRDataEnumMemoryRegionsCallback – rozhraní</span><span class="sxs-lookup"><span data-stu-id="50999-102">ICLRDataEnumMemoryRegionsCallback Interface</span></span>
<span data-ttu-id="50999-103">Poskytuje metody zpětného volání pro [iclrdataenummemoryregions::enummemoryregions –](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) tak, aby odesílaly ladicího programu výsledek pokusu o zobrazení výčtu zadané oblasti paměti.</span><span class="sxs-lookup"><span data-stu-id="50999-103">Provides a callback method for [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="50999-104">Metody</span><span class="sxs-lookup"><span data-stu-id="50999-104">Methods</span></span>  
  
|<span data-ttu-id="50999-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="50999-105">Method</span></span>|<span data-ttu-id="50999-106">Popis</span><span class="sxs-lookup"><span data-stu-id="50999-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="50999-107">Enummemoryregion – metoda</span><span class="sxs-lookup"><span data-stu-id="50999-107">EnumMemoryRegion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-enummemoryregion-method.md)|<span data-ttu-id="50999-108">Voláno rozhraním `ICLRDataEnumMemoryRegions::EnumMemoryRegions` tak, aby odesílaly ladicího programu výsledek pokusu o zobrazení výčtu zadané oblasti paměti.</span><span class="sxs-lookup"><span data-stu-id="50999-108">Called by `ICLRDataEnumMemoryRegions::EnumMemoryRegions` to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="50999-109">Požadavky</span><span class="sxs-lookup"><span data-stu-id="50999-109">Requirements</span></span>  
 <span data-ttu-id="50999-110">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50999-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50999-111">**Záhlaví:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="50999-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="50999-112">**Knihovna:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="50999-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="50999-113">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50999-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50999-114">Viz také</span><span class="sxs-lookup"><span data-stu-id="50999-114">See Also</span></span>  
 [<span data-ttu-id="50999-115">Ladění v rozhraní</span><span class="sxs-lookup"><span data-stu-id="50999-115">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
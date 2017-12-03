---
title: "IMetaDataTables::GetNextBlob – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables.GetNextBlob
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables::GetNextBlob
helpviewer_keywords:
- IMetaDataTables::GetNextBlob method [.NET Framework metadata]
- GetNextBlob method [.NET Framework metadata]
ms.assetid: 017c8ab4-4c09-4754-9935-5b0b49cabecb
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 151fdf06f6203eabf2fc3e37bd30399b52394124
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatatablesgetnextblob-method"></a><span data-ttu-id="86e24-102">IMetaDataTables::GetNextBlob – metoda</span><span class="sxs-lookup"><span data-stu-id="86e24-102">IMetaDataTables::GetNextBlob Method</span></span>
<span data-ttu-id="86e24-103">Získá index další binární rozsáhlý objekt (binární rozsáhlý OBJEKT) v tabulce.</span><span class="sxs-lookup"><span data-stu-id="86e24-103">Gets the index of the next binary large object (BLOB) in the table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86e24-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="86e24-104">Syntax</span></span>  
  
```  
HRESULT GetNextBlob (  
    [in]  ULONG   ixBlob,  
    [out] ULONG   *pNext  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="86e24-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="86e24-105">Parameters</span></span>  
 `ixBlob`  
 <span data-ttu-id="86e24-106">[v] Index, jak ho vrátila ze sloupce objektů BLOB.</span><span class="sxs-lookup"><span data-stu-id="86e24-106">[in] The index, as returned from a column of BLOBs.</span></span>  
  
 `pNext`  
 <span data-ttu-id="86e24-107">[out] Ukazatel na index další objekt BLOB.</span><span class="sxs-lookup"><span data-stu-id="86e24-107">[out] A pointer to the index of the next BLOB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86e24-108">Požadavky</span><span class="sxs-lookup"><span data-stu-id="86e24-108">Requirements</span></span>  
 <span data-ttu-id="86e24-109">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86e24-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86e24-110">**Záhlaví:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="86e24-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="86e24-111">**Knihovna:** používat jako prostředek v MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="86e24-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="86e24-112">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86e24-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86e24-113">Viz také</span><span class="sxs-lookup"><span data-stu-id="86e24-113">See Also</span></span>  
 [<span data-ttu-id="86e24-114">Imetadatatables – rozhraní</span><span class="sxs-lookup"><span data-stu-id="86e24-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="86e24-115">Imetadatatables2 – rozhraní</span><span class="sxs-lookup"><span data-stu-id="86e24-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
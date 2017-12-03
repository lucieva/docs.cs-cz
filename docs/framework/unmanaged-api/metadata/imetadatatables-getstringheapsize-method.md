---
title: "IMetaDataTables::GetStringHeapSize – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables.GetStringHeapSize
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables::GetStringHeapSize
helpviewer_keywords:
- IMetaDataTables::GetStringHeapSize method [.NET Framework metadata]
- GetStringHeapSize method [.NET Framework metadata]
ms.assetid: ed8f6335-81f5-4c09-81a9-2a909fc530c9
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a0e664192ac39dd12085346738dbc283a11d3381
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatatablesgetstringheapsize-method"></a><span data-ttu-id="f58a3-102">IMetaDataTables::GetStringHeapSize – metoda</span><span class="sxs-lookup"><span data-stu-id="f58a3-102">IMetaDataTables::GetStringHeapSize Method</span></span>
<span data-ttu-id="f58a3-103">Získá velikost v bajtech haldy řetězce.</span><span class="sxs-lookup"><span data-stu-id="f58a3-103">Gets the size, in bytes, of the string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f58a3-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="f58a3-104">Syntax</span></span>  
  
```  
HRESULT GetStringHeapSize (  
    [out] ULONG   *pcbStrings  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f58a3-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="f58a3-105">Parameters</span></span>  
 `pcbStrings`  
 <span data-ttu-id="f58a3-106">[out] Ukazatel na velikost v bajtech haldy řetězce.</span><span class="sxs-lookup"><span data-stu-id="f58a3-106">[out] A pointer to the size, in bytes, of the string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f58a3-107">Požadavky</span><span class="sxs-lookup"><span data-stu-id="f58a3-107">Requirements</span></span>  
 <span data-ttu-id="f58a3-108">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f58a3-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f58a3-109">**Záhlaví:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f58a3-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f58a3-110">**Knihovna:** používat jako prostředek v MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f58a3-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f58a3-111">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f58a3-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f58a3-112">Viz také</span><span class="sxs-lookup"><span data-stu-id="f58a3-112">See Also</span></span>  
 [<span data-ttu-id="f58a3-113">Imetadatatables – rozhraní</span><span class="sxs-lookup"><span data-stu-id="f58a3-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="f58a3-114">Imetadatatables2 – rozhraní</span><span class="sxs-lookup"><span data-stu-id="f58a3-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
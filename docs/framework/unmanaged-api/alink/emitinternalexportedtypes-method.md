---
title: "EmitInternalExportedTypes – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- EmitInternalExportedTypes
- IALink2.EmitInternalExportedTypes
api_location: alink.dll
api_type: COM
f1_keywords: EmitInternalExportedTypes
helpviewer_keywords: EmitInternalExportedTypes method
ms.assetid: 28c8b00d-2c14-40b4-aed5-a1db0e2428eb
topic_type: apiref
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f354058e0de944bbce9d128d3f4baa9b941fda08
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="emitinternalexportedtypes-method"></a><span data-ttu-id="b4679-102">EmitInternalExportedTypes – metoda</span><span class="sxs-lookup"><span data-stu-id="b4679-102">EmitInternalExportedTypes Method</span></span>
<span data-ttu-id="b4679-103">Vysílá typy, které jsou přidány do sestavení.</span><span class="sxs-lookup"><span data-stu-id="b4679-103">Emits types added to the assembly.</span></span> <span data-ttu-id="b4679-104">Volejte tuto metodu po označuje, že byly přidány interní typy.</span><span class="sxs-lookup"><span data-stu-id="b4679-104">Call this method after known internal types have been added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4679-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="b4679-105">Syntax</span></span>  
  
```  
HRESULT EmitInternalExportedTypes(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b4679-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="b4679-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="b4679-107">ID sestavení.</span><span class="sxs-lookup"><span data-stu-id="b4679-107">ID of assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b4679-108">Návratová hodnota</span><span class="sxs-lookup"><span data-stu-id="b4679-108">Return Value</span></span>  
 <span data-ttu-id="b4679-109">Vrátí S_OK, pokud metoda bude úspěšná.</span><span class="sxs-lookup"><span data-stu-id="b4679-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4679-110">Požadavky</span><span class="sxs-lookup"><span data-stu-id="b4679-110">Requirements</span></span>  
 <span data-ttu-id="b4679-111">Vyžaduje alink.h</span><span class="sxs-lookup"><span data-stu-id="b4679-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4679-112">Viz také</span><span class="sxs-lookup"><span data-stu-id="b4679-112">See Also</span></span>  
 [<span data-ttu-id="b4679-113">Ialink2 – rozhraní</span><span class="sxs-lookup"><span data-stu-id="b4679-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="b4679-114">Ialink – rozhraní</span><span class="sxs-lookup"><span data-stu-id="b4679-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="b4679-115">Rozhraní API ALink</span><span class="sxs-lookup"><span data-stu-id="b4679-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
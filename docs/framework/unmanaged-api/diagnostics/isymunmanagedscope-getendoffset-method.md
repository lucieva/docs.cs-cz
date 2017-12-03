---
title: "ISymUnmanagedScope::GetEndOffset – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedScope.GetEndOffset
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedScope::GetEndOffset
helpviewer_keywords:
- ISymUnmanagedScope::GetEndOffset method [.NET Framework debugging]
- GetEndOffset method, ISymUnmanagedScope interface [.NET Framework debugging]
ms.assetid: 1d0b15c9-8059-435f-9fce-346a08b9bd36
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: dd3b7c78c3a43109c3508487aa34650f0f16d196
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedscopegetendoffset-method"></a><span data-ttu-id="d9e11-102">ISymUnmanagedScope::GetEndOffset – metoda</span><span class="sxs-lookup"><span data-stu-id="d9e11-102">ISymUnmanagedScope::GetEndOffset Method</span></span>
<span data-ttu-id="d9e11-103">Získá posun end pro tento obor.</span><span class="sxs-lookup"><span data-stu-id="d9e11-103">Gets the end offset for this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9e11-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="d9e11-104">Syntax</span></span>  
  
```  
HRESULT GetEndOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d9e11-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="d9e11-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="d9e11-106">[out] Ukazatel na `ULONG32` která přijme posun end.</span><span class="sxs-lookup"><span data-stu-id="d9e11-106">[out] A pointer to a `ULONG32` that receives the end offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d9e11-107">Návratová hodnota</span><span class="sxs-lookup"><span data-stu-id="d9e11-107">Return Value</span></span>  
 <span data-ttu-id="d9e11-108">S_OK, pokud metoda úspěšně. v opačném E_FAIL nebo jiný kód chyby.</span><span class="sxs-lookup"><span data-stu-id="d9e11-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9e11-109">Požadavky</span><span class="sxs-lookup"><span data-stu-id="d9e11-109">Requirements</span></span>  
 <span data-ttu-id="d9e11-110">**Záhlaví:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d9e11-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9e11-111">Viz také</span><span class="sxs-lookup"><span data-stu-id="d9e11-111">See Also</span></span>  
 [<span data-ttu-id="d9e11-112">ISymUnmanagedScope – rozhraní</span><span class="sxs-lookup"><span data-stu-id="d9e11-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)  
 [<span data-ttu-id="d9e11-113">Getstartoffset – metoda</span><span class="sxs-lookup"><span data-stu-id="d9e11-113">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getstartoffset-method.md)
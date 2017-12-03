---
title: "GetHashFromAssemblyFileW – funkce"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetHashFromAssemblyFileW
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: GetHashFromAssemblyFileW
helpviewer_keywords: GetHashFromAssemblyFileW function [.NET Framework strong naming]
ms.assetid: d1b2b172-5353-42af-a877-cf653c68ece0
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: aa88de90f831e1faaca2624a77a556d6a2b566c2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="gethashfromassemblyfilew-function"></a><span data-ttu-id="cfa1a-102">GetHashFromAssemblyFileW – funkce</span><span class="sxs-lookup"><span data-stu-id="cfa1a-102">GetHashFromAssemblyFileW Function</span></span>
<span data-ttu-id="cfa1a-103">Získá hodnotu hash souboru zadaného sestavení pomocí zadaný algoritmus hash.</span><span class="sxs-lookup"><span data-stu-id="cfa1a-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span> <span data-ttu-id="cfa1a-104">Cesta k souboru sestavení musí být zadán jako řetězec znaků Unicode.</span><span class="sxs-lookup"><span data-stu-id="cfa1a-104">The path to the assembly file must be specified as a Unicode string.</span></span>  
  
 <span data-ttu-id="cfa1a-105">Tato funkce je zastaralá.</span><span class="sxs-lookup"><span data-stu-id="cfa1a-105">This function has been deprecated.</span></span> <span data-ttu-id="cfa1a-106">Použití [iclrstrongname::gethashfromassemblyfilew –](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md) metoda místo.</span><span class="sxs-lookup"><span data-stu-id="cfa1a-106">Use the [ICLRStrongName::GetHashFromAssemblyFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfa1a-107">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="cfa1a-107">Syntax</span></span>  
  
```  
HRESULT GetHashFromAssemblyFileW (  
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cfa1a-108">Parametry</span><span class="sxs-lookup"><span data-stu-id="cfa1a-108">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="cfa1a-109">[v] Cesta k souboru, který se použít algoritmus hash.</span><span class="sxs-lookup"><span data-stu-id="cfa1a-109">[in] The path to the file to be hashed.</span></span> <span data-ttu-id="cfa1a-110">Tento parametr musí být řetězec znaků Unicode.</span><span class="sxs-lookup"><span data-stu-id="cfa1a-110">This parameter must be a Unicode string.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="cfa1a-111">[ve out] Konstanta, která určuje algoritmus hash.</span><span class="sxs-lookup"><span data-stu-id="cfa1a-111">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="cfa1a-112">Používejte nula pro výchozí algoritmus hash.</span><span class="sxs-lookup"><span data-stu-id="cfa1a-112">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="cfa1a-113">[out] Vrácená hodnota hash vyrovnávací paměti.</span><span class="sxs-lookup"><span data-stu-id="cfa1a-113">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="cfa1a-114">[v] Požadovaný maximální velikost `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="cfa1a-114">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="cfa1a-115">[out] Vrácen velikost v bajtech, z `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="cfa1a-115">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cfa1a-116">Požadavky</span><span class="sxs-lookup"><span data-stu-id="cfa1a-116">Requirements</span></span>  
 <span data-ttu-id="cfa1a-117">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cfa1a-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cfa1a-118">**Záhlaví:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="cfa1a-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="cfa1a-119">**Knihovna:** zahrnuty jako prostředek v MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cfa1a-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cfa1a-120">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfa1a-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfa1a-121">Viz také</span><span class="sxs-lookup"><span data-stu-id="cfa1a-121">See Also</span></span>  
 [<span data-ttu-id="cfa1a-122">Gethashfromassemblyfilew – metoda</span><span class="sxs-lookup"><span data-stu-id="cfa1a-122">GetHashFromAssemblyFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)  
 [<span data-ttu-id="cfa1a-123">Gethashfromassemblyfile – metoda</span><span class="sxs-lookup"><span data-stu-id="cfa1a-123">GetHashFromAssemblyFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)  
 [<span data-ttu-id="cfa1a-124">Iclrstrongname – rozhraní</span><span class="sxs-lookup"><span data-stu-id="cfa1a-124">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
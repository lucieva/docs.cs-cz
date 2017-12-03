---
title: "ICeeGen::GetSectionCreate – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICeeGen.GetSectionCreate
api_location: mscoree.dll
api_type: COM
f1_keywords: ICeeGen::GetSectionCreate
helpviewer_keywords:
- ICeeGen::GetSectionCreate method [.NET Framework metadata]
- GetSectionCreate method [.NET Framework metadata]
ms.assetid: 154b2460-59ce-4874-a9f2-1b3353486ac5
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2ea9cb20b62e1b1fa8e726ba0c49c5e24202530c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="iceegengetsectioncreate-method"></a><span data-ttu-id="7779e-102">ICeeGen::GetSectionCreate – metoda</span><span class="sxs-lookup"><span data-stu-id="7779e-102">ICeeGen::GetSectionCreate Method</span></span>
<span data-ttu-id="7779e-103">Generuje a získá oddíl kód pomocí zadaného názvu a hodnoty příznaku.</span><span class="sxs-lookup"><span data-stu-id="7779e-103">Generates and gets a code section using the specified name and flag values.</span></span>  
  
 <span data-ttu-id="7779e-104">Tato metoda je zastaralá a by se neměla používat.</span><span class="sxs-lookup"><span data-stu-id="7779e-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7779e-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="7779e-105">Syntax</span></span>  
  
```  
HRESULT GetSectionCreate (  
    [in]  const char     *name,  
    [in]  DWORD          flags,  
    [out] HCEESECTION    *section  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7779e-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="7779e-106">Parameters</span></span>  
 `name`  
 <span data-ttu-id="7779e-107">[v] Ukazatel na řetězec, který určuje název oddílu, který má být vytvořen.</span><span class="sxs-lookup"><span data-stu-id="7779e-107">[in] A pointer to a string that specifies the name of the section to be created.</span></span>  
  
 `flags`  
 <span data-ttu-id="7779e-108">[v] Příznaky, které určují možnosti.</span><span class="sxs-lookup"><span data-stu-id="7779e-108">[in] Flags that specify options.</span></span>  
  
 `section`  
 <span data-ttu-id="7779e-109">[out] Ukazatel na nově vytvořený kód části.</span><span class="sxs-lookup"><span data-stu-id="7779e-109">[out] A pointer to the newly created code section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7779e-110">Poznámky</span><span class="sxs-lookup"><span data-stu-id="7779e-110">Remarks</span></span>  
 <span data-ttu-id="7779e-111">Volání `GetSectionCreate` pouze v případě, že máte speciální části požadavky, které nejsou zpracovány jinými metodami.</span><span class="sxs-lookup"><span data-stu-id="7779e-111">Call `GetSectionCreate` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7779e-112">Požadavky</span><span class="sxs-lookup"><span data-stu-id="7779e-112">Requirements</span></span>  
 <span data-ttu-id="7779e-113">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7779e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7779e-114">**Záhlaví:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7779e-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7779e-115">**Knihovna:** používat jako prostředek v MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7779e-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7779e-116">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7779e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7779e-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="7779e-117">See Also</span></span>  
 [<span data-ttu-id="7779e-118">Iceegen – rozhraní</span><span class="sxs-lookup"><span data-stu-id="7779e-118">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
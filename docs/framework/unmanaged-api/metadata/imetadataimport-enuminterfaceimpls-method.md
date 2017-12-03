---
title: "IMetaDataImport::EnumInterfaceImpls – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumInterfaceImpls
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumInterfaceImpls
helpviewer_keywords:
- IMetaDataImport::EnumInterfaceImpls method [.NET Framework metadata]
- EnumInterfaceImpls method [.NET Framework metadata]
ms.assetid: ba6e178f-128b-4e47-a13c-b4be73eb106c
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1d9f2883c32daafd8938bd1c80c035a3527cc6a1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenuminterfaceimpls-method"></a><span data-ttu-id="b5bdc-102">IMetaDataImport::EnumInterfaceImpls – metoda</span><span class="sxs-lookup"><span data-stu-id="b5bdc-102">IMetaDataImport::EnumInterfaceImpls Method</span></span>
<span data-ttu-id="b5bdc-103">Vytvoří výčet MethodDef tokeny představující implementace rozhraní.</span><span class="sxs-lookup"><span data-stu-id="b5bdc-103">Enumerates MethodDef tokens representing interface implementations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5bdc-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="b5bdc-104">Syntax</span></span>  
  
```  
HRESULT EnumInterfaceImpls (  
   [in, out]  HCORENUM       *phEnum,   
   [in]   mdTypeDef          td,  
   [out]  mdInterfaceImpl    rImpls[],   
   [in]   ULONG              cMax,  
   [out]  ULONG*             pcImpls  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b5bdc-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="b5bdc-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="b5bdc-106">[ve out] Ukazatel na enumerátor.</span><span class="sxs-lookup"><span data-stu-id="b5bdc-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="b5bdc-107">[v] Token TypeDef, jejichž MethodDef tokeny představující implementace rozhraní jsou výčet.</span><span class="sxs-lookup"><span data-stu-id="b5bdc-107">[in] The token of the TypeDef whose MethodDef tokens representing interface implementations are to be enumerated.</span></span>  
  
 `rImpls`  
 <span data-ttu-id="b5bdc-108">[out] Pole používá k ukládání MethodDef tokenů.</span><span class="sxs-lookup"><span data-stu-id="b5bdc-108">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="b5bdc-109">[v] Maximální velikost `rImpls` pole.</span><span class="sxs-lookup"><span data-stu-id="b5bdc-109">[in] The maximum size of the `rImpls` array.</span></span>  
  
 `pcImpls`  
 <span data-ttu-id="b5bdc-110">[out] Skutečný počet tokeny, vrátí se v `rImpls`.</span><span class="sxs-lookup"><span data-stu-id="b5bdc-110">[out] The actual number of tokens returned in `rImpls`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b5bdc-111">Návratová hodnota</span><span class="sxs-lookup"><span data-stu-id="b5bdc-111">Return Value</span></span>  
  
|<span data-ttu-id="b5bdc-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b5bdc-112">HRESULT</span></span>|<span data-ttu-id="b5bdc-113">Popis</span><span class="sxs-lookup"><span data-stu-id="b5bdc-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="b5bdc-114">`EnumInterfaceImpls`úspěšně vrácena.</span><span class="sxs-lookup"><span data-stu-id="b5bdc-114">`EnumInterfaceImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="b5bdc-115">Neexistují žádné MethodDef tokenů pro zobrazení výčtu.</span><span class="sxs-lookup"><span data-stu-id="b5bdc-115">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="b5bdc-116">V takovém případě `pcImpls` je nastaven na hodnotu nula.</span><span class="sxs-lookup"><span data-stu-id="b5bdc-116">In that case, `pcImpls` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b5bdc-117">Požadavky</span><span class="sxs-lookup"><span data-stu-id="b5bdc-117">Requirements</span></span>  
 <span data-ttu-id="b5bdc-118">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5bdc-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5bdc-119">**Záhlaví:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b5bdc-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b5bdc-120">**Knihovna:** zahrnuty jako prostředek v MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b5bdc-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b5bdc-121">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5bdc-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5bdc-122">Viz také</span><span class="sxs-lookup"><span data-stu-id="b5bdc-122">See Also</span></span>  
 [<span data-ttu-id="b5bdc-123">Imetadataimport – rozhraní</span><span class="sxs-lookup"><span data-stu-id="b5bdc-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="b5bdc-124">Imetadataimport2 – rozhraní</span><span class="sxs-lookup"><span data-stu-id="b5bdc-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
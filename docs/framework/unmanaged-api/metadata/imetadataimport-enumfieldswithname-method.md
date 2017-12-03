---
title: "IMetaDataImport::EnumFieldsWithName – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumFieldsWithName
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumFieldsWithName
helpviewer_keywords:
- IMetaDataImport::EnumFieldsWithName method [.NET Framework metadata]
- EnumFieldsWithName method [.NET Framework metadata]
ms.assetid: 42145e8d-000f-4d0b-ae43-c08201190fa2
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2f6104f287350a9ac2f0eb5b82c05422a18a48a2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenumfieldswithname-method"></a><span data-ttu-id="02d18-102">IMetaDataImport::EnumFieldsWithName – metoda</span><span class="sxs-lookup"><span data-stu-id="02d18-102">IMetaDataImport::EnumFieldsWithName Method</span></span>
<span data-ttu-id="02d18-103">Vytvoří výčet FieldDef tokeny zadaného typu se zadaným názvem.</span><span class="sxs-lookup"><span data-stu-id="02d18-103">Enumerates FieldDef tokens of the specified type with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02d18-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="02d18-104">Syntax</span></span>  
  
```  
HRESULT EnumFieldsWithName (  
   [in, out] HCORENUM    *phEnum,   
   [in]  mdTypeDef       cl,   
   [in]  LPCWSTR         szName,   
   [out] mdFieldDef      rFields[],   
   [in]  ULONG           cMax,   
   [out] ULONG           *pcTokens   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="02d18-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="02d18-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="02d18-106">[ve out] Ukazatel na enumerátor.</span><span class="sxs-lookup"><span data-stu-id="02d18-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="02d18-107">[v] Token typu, jehož pole jsou na vytvoření výčtu.</span><span class="sxs-lookup"><span data-stu-id="02d18-107">[in] The token of the type whose fields are to be enumerated.</span></span>  
  
 `szName`  
 <span data-ttu-id="02d18-108">[v] Název pole, která omezuje obor výčtu.</span><span class="sxs-lookup"><span data-stu-id="02d18-108">[in] The field name that limits the scope of the enumeration.</span></span>  
  
 `rFields`  
 <span data-ttu-id="02d18-109">[out] Pole používá k ukládání FieldDef tokenů.</span><span class="sxs-lookup"><span data-stu-id="02d18-109">[out] Array used to store the FieldDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="02d18-110">[v] Maximální velikost `rFields` pole.</span><span class="sxs-lookup"><span data-stu-id="02d18-110">[in] The maximum size of the `rFields` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="02d18-111">[out] Skutečný počet FieldDef tokeny, vrátí se v `rFields`.</span><span class="sxs-lookup"><span data-stu-id="02d18-111">[out] The actual number of FieldDef tokens returned in `rFields`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="02d18-112">Poznámky</span><span class="sxs-lookup"><span data-stu-id="02d18-112">Remarks</span></span>  
 <span data-ttu-id="02d18-113">Na rozdíl od [imetadataimport::enumfields –](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumfields-method.md), `EnumFieldsWithName` zahodí všechny tokeny pole, které nemají zadaný název.</span><span class="sxs-lookup"><span data-stu-id="02d18-113">Unlike [IMetaDataImport::EnumFields](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumfields-method.md), `EnumFieldsWithName` discards all field tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="02d18-114">Návratová hodnota</span><span class="sxs-lookup"><span data-stu-id="02d18-114">Return Value</span></span>  
  
|<span data-ttu-id="02d18-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="02d18-115">HRESULT</span></span>|<span data-ttu-id="02d18-116">Popis</span><span class="sxs-lookup"><span data-stu-id="02d18-116">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="02d18-117">`EnumFieldsWithName`úspěšně vrácena.</span><span class="sxs-lookup"><span data-stu-id="02d18-117">`EnumFieldsWithName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="02d18-118">Neexistují žádná pole pro vytvoření výčtu.</span><span class="sxs-lookup"><span data-stu-id="02d18-118">There are no fields to enumerate.</span></span> <span data-ttu-id="02d18-119">V takovém případě `pcTokens` je nulová.</span><span class="sxs-lookup"><span data-stu-id="02d18-119">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="02d18-120">Požadavky</span><span class="sxs-lookup"><span data-stu-id="02d18-120">Requirements</span></span>  
 <span data-ttu-id="02d18-121">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02d18-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02d18-122">**Záhlaví:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="02d18-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="02d18-123">**Knihovna:** zahrnuty jako prostředek v MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="02d18-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="02d18-124">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02d18-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02d18-125">Viz také</span><span class="sxs-lookup"><span data-stu-id="02d18-125">See Also</span></span>  
 [<span data-ttu-id="02d18-126">Imetadataimport – rozhraní</span><span class="sxs-lookup"><span data-stu-id="02d18-126">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="02d18-127">Imetadataimport2 – rozhraní</span><span class="sxs-lookup"><span data-stu-id="02d18-127">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
---
title: "ICLRErrorReportingManager::GetBucketParametersForCurrentException – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRErrorReportingManager.GetBucketParametersForCurrentException
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRErrorReportingManager::GetBucketParametersForCurrentException
helpviewer_keywords:
- ICLRErrorReportingManager::GetBucketParametersForCurrentException method [.NET Framework hosting]
- GetBucketParametersForCurrentException method [.NET Framework hosting]
ms.assetid: a13ec8a6-8e18-4acb-8054-77f5b1a0e0b9
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 80bf3e9b1cee9f19534f985dccf4508467dbe26e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="iclrerrorreportingmanagergetbucketparametersforcurrentexception-method"></a><span data-ttu-id="f9800-102">ICLRErrorReportingManager::GetBucketParametersForCurrentException – metoda</span><span class="sxs-lookup"><span data-stu-id="f9800-102">ICLRErrorReportingManager::GetBucketParametersForCurrentException Method</span></span>
<span data-ttu-id="f9800-103">Získá Watson sady pro aktuální výjimky na volající vlákno.</span><span class="sxs-lookup"><span data-stu-id="f9800-103">Gets the Watson bucket for the current exception on the calling thread.</span></span>  
  
 <span data-ttu-id="f9800-104">A *sady* je kolekce dat chyby, která souvisí se stejnou vadou kódu.</span><span class="sxs-lookup"><span data-stu-id="f9800-104">A *bucket* is a collection of error data that is related to the same code defect.</span></span> <span data-ttu-id="f9800-105">*Watson* odkazuje na sadu technologií pro shromažďování a analýzy dat, který je přidružen k výjimce.</span><span class="sxs-lookup"><span data-stu-id="f9800-105">*Watson* refers to a set of technologies for collecting and analyzing data that is associated with an exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9800-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="f9800-106">Syntax</span></span>  
  
```  
HRESULT GetBucketParametersForCurrentException(  
    [out] BucketParameters *pParams  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f9800-107">Parametry</span><span class="sxs-lookup"><span data-stu-id="f9800-107">Parameters</span></span>  
 `pParams`  
 <span data-ttu-id="f9800-108">[out] Ukazatel [bucketparameters –](../../../../docs/framework/unmanaged-api/hosting/bucketparameters-structure.md) struktura, která obsahuje data o chybách pro výjimku.</span><span class="sxs-lookup"><span data-stu-id="f9800-108">[out] A pointer to a [BucketParameters](../../../../docs/framework/unmanaged-api/hosting/bucketparameters-structure.md) structure that contains error data for the exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9800-109">Požadavky</span><span class="sxs-lookup"><span data-stu-id="f9800-109">Requirements</span></span>  
 <span data-ttu-id="f9800-110">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9800-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9800-111">**Záhlaví:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f9800-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f9800-112">**Knihovna:** zahrnuty jako prostředek v MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f9800-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f9800-113">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9800-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9800-114">Viz také</span><span class="sxs-lookup"><span data-stu-id="f9800-114">See Also</span></span>  
 [<span data-ttu-id="f9800-115">Iclrerrorreportingmanager – rozhraní</span><span class="sxs-lookup"><span data-stu-id="f9800-115">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
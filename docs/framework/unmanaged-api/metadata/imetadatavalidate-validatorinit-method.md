---
title: IMetaDataValidate::ValidatorInit – metoda
ms.date: 03/30/2017
api_name:
- IMetaDataValidate.ValidatorInit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataValidate::ValidatorInit
helpviewer_keywords:
- IMetaDataValidate::ValidatorInit method [.NET Framework metadata]
- ValidatorInit method [.NET Framework metadata]
ms.assetid: 6bafd75a-e2d0-4aea-aed1-074374d5dff6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 053c94bc540b130510f155506b6fad32f032a475
ms.sourcegitcommit: a474397fd4de822f0d878d86d907e49763872b0b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/14/2018
ms.locfileid: "33449543"
---
# <a name="imetadatavalidatevalidatorinit-method"></a>IMetaDataValidate::ValidatorInit – metoda
Nastaví příznak, který určuje typ modulu v aktuálním oboru metadata a zaregistruje zadaná metoda zpětného volání pro chyby ověření.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT ValidatorInit (  
   [in] DWORD       dwModuleType,  
   [in] IUnknown    *pUnk  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dwModule`  
 [in] Hodnota [corvalidatormoduletype –](../../../../docs/framework/unmanaged-api/metadata/corvalidatormoduletype-enumeration.md) výčet, který určuje typ modulu v aktuálním oboru metadat.  
  
 `pUnk`  
 [in] Ukazatel [IUnknown](/cpp/atl/iunknown) instanci, která slouží jako funkce zpětného volání pro chyby ověření.  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** naleznete v tématu [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** Cor.h  
  
 **Knihovna:** použit jako prostředek v MsCorEE.dll  
  
 **Verze rozhraní .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [IMetaDataValidate – rozhraní](../../../../docs/framework/unmanaged-api/metadata/imetadatavalidate-interface.md)

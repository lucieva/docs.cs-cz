---
title: ICorDebugGenericValue Interface1
ms.date: 03/30/2017
api_name:
- ICorDebugGenericValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGenericValue
helpviewer_keywords:
- ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: bc14f408-b359-4c8c-ade2-888ccdf7261b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0081f020da673023e2c35f9599e9682215e2c9d4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415061"
---
# <a name="icordebuggenericvalue-interface1"></a>ICorDebugGenericValue Interface1
Podtřídou třídy "ICorDebugValue", která se použije pro všechny hodnoty. Toto rozhraní poskytuje metody Get a Set pro hodnotu.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetValue – metoda](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-getvalue-method.md)|Hodnotu se zkopíruje do zadané vyrovnávací paměti.|  
|[SetValue – metoda](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md)|Zkopíruje novou hodnotu ze zadaného vyrovnávací paměti.|  
  
## <a name="remarks"></a>Poznámky  
 `ICorDebugGenericValue` je dílčí rozhraní, protože je jiný učinit vzdáleným.  
  
 U typů odkazu hodnota je odkaz na spíše než odkaz na obsah.  
  
 Toto rozhraní nepodporuje volané vzdáleně, mezi počítači nebo mezi procesy.  
  
> [!NOTE]
>  Toto rozhraní nepodporuje volané vzdáleně, mezi počítači nebo mezi procesy.  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** CorDebug.idl, CorDebug.h  
  
 **Knihovna:** CorGuids.lib  
  
 **Verze rozhraní .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Viz také  
    
 [Rozhraní pro ladění](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

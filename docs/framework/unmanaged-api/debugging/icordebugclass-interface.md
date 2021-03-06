---
title: ICorDebugClass Interface1
ms.date: 03/30/2017
api_name:
- ICorDebugClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass
helpviewer_keywords:
- ICorDebugClass interface [.NET Framework debugging]
ms.assetid: 03a6facb-f12f-49be-9839-e73b9c791cd5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bec35babec96da5ca5d527b19f853b4ce1c384e8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/04/2018
ms.locfileid: "33406933"
---
# <a name="icordebugclass-interface1"></a>ICorDebugClass Interface1
Představuje typ, který může být základní nebo komplexní (tj. definovaný uživatelem). Pokud je typ Obecné, `ICorDebugClass` představuje bez instancí obecného typu.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetModule – metoda](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getmodule-method.md)|Získá modul, který definuje tuto třídu.|  
|[GetStaticFieldValue – metoda](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md)|Získá hodnotu zadaného pole statické.|  
|[GetToken – metoda](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-gettoken-method.md)|Získá `TypeDef` token metadata pro tuto třídu.|  
  
## <a name="remarks"></a>Poznámky  
 `ICorDebugClass` Rozhraní představuje bez instancí obecného typu. ICorDebugType rozhraní představuje instanci obecného typu. Například `Hashtable<K, V>` by být reprezentovaná `ICorDebugClass`, zatímco `Hashtable<Int32, String>` by být reprezentovaná `ICorDebugType`.  
  
 Jak jsou reprezentována non obecné typy `ICorDebugClass` a `ICorDebugType`. Rozhraní pozdější byla zavedena v rozhraní .NET Framework verze 2.0, jak nakládat s vytvoření instance typu.  
  
> [!NOTE]
>  Toto rozhraní nepodporuje volané vzdáleně, mezi počítači nebo mezi procesy.  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** CorDebug.idl, CorDebug.h  
  
 **Knihovna:** CorGuids.lib  
  
 **Verze rozhraní .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní pro ladění](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

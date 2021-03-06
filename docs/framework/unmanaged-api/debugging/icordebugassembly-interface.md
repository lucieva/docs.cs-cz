---
title: ICorDebugAssembly Interface1
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly
helpviewer_keywords:
- ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: 9d657a28-6984-4c5e-8a54-89d20080baff
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 88134fb7854091bb60e8084a6d776bdec922c7e1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/04/2018
ms.locfileid: "33406367"
---
# <a name="icordebugassembly-interface1"></a>ICorDebugAssembly Interface1
Představuje sestavení.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Popis|  
|------------|-----------------|  
|[EnumerateModules – metoda](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-enumeratemodules-method.md)|Získá enumerátor pro moduly obsažený v sestavení.|  
|[GetAppDomain – metoda](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getappdomain-method.md)|Získá ukazatele rozhraní k doméně aplikace, která obsahuje toto `ICorDebugAssembly` instance.|  
|[GetCodeBase – metoda](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getcodebase-method.md)|Není implementováno v aktuální verzi rozhraní .NET Framework.|  
|[GetName – metoda](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getname-method.md)|Získá název sestavení.|  
|[GetProcess – metoda](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getprocess-method.md)|Získá instanci ICorDebugProcess, ve kterém je spuštěna sestavení.|  
  
## <a name="remarks"></a>Poznámky  
  
> [!NOTE]
>  Toto rozhraní nepodporuje volané vzdáleně, mezi počítači nebo mezi procesy.  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** CorDebug.idl, CorDebug.h  
  
 **Knihovna:** CorGuids.lib  
  
 **Verze rozhraní .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní pro ladění](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

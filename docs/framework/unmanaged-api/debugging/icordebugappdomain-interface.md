---
title: ICorDebugAppDomain Interface1
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain
api_location:
- corguids.lib
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain
helpviewer_keywords:
- ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: be7ae711-1217-4a44-be40-166e29641b77
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 84a11b6264ac0e241c1975eea5626edbdddce206
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/04/2018
ms.locfileid: "33406874"
---
# <a name="icordebugappdomain-interface1"></a>ICorDebugAppDomain Interface1
Poskytuje metody pro ladění domén aplikace. Toto rozhraní je podtřídou třídy ICorDebugController.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Attach – metoda](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-attach-method.md)|Připojí ladicí program do domény aplikace.|  
|[EnumerateAssemblies – metoda](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumerateassemblies-method.md)|Získá enumerátor pro sestavení v doméně aplikace.|  
|[EnumerateBreakpoints – metoda](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumeratebreakpoints-method.md)|Získá enumerátor pro všechny aktivní zarážky v doméně aplikace.|  
|[EnumerateSteppers – metoda](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumeratesteppers-method.md)|Získá enumerátor pro všechny aktivní steppers v doméně aplikace.|  
|[GetId – metoda](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getid-method.md)|Získá jedinečné ID domény aplikace.|  
|[GetModuleFromMetaDataInterface – metoda](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getmodulefrommetadatainterface-method.md)|Získá objekt ICorDebugModule s rozhraním daná metadata.|  
|[GetName – metoda](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getname-method.md)|Získá název domény aplikace.|  
|[GetObject – metoda](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getobject-method.md)|Získá ukazatele rozhraní pro běžné domény aplikace language runtime (CLR).|  
|[GetProcess – metoda](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-getprocess-method.md)|Získá proces obsahující domény aplikace.|  
|[IsAttached – metoda](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-isattached-method.md)|Určuje, zda je ladicí program připojen do domény aplikace.|  
  
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

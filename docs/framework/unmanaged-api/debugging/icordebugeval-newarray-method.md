---
title: ICorDebugEval::NewArray – metoda
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewArray
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewArray
helpviewer_keywords:
- NewArray method [.NET Framework debugging]
- ICorDebugEval::NewArray method [.NET Framework debugging]
ms.assetid: cc79a67d-5368-434d-a943-209db90491b9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 38b00d903fdd7301415a8df7642e12366178fd10
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413937"
---
# <a name="icordebugevalnewarray-method"></a>ICorDebugEval::NewArray – metoda
Přiděluje nový pole typu zadaného elementu a dimenze.  
  
 Tato metoda je zastaralé v rozhraní .NET Framework verze 2.0. Použití [icordebugeval2::newparameterizedarray –](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md) místo.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT NewArray (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [in] ULONG32            rank,  
    [in, size_is(rank)] ULONG32 dims[],  
    [in, size_is(rank)] ULONG32 lowBounds[]  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `elementType`  
 [v] Hodnota CorElementType – výčet, který určuje typ elementu pole.  
  
 `pElementClass`  
 [v] Ukazatel na ICorDebugClass objekt, který určuje třída elementu. Tato hodnota může mít hodnotu null, pokud je typ elementu primitivního typu.  
  
 `rank`  
 [v] Počet rozměrů pole. V rozhraní .NET Framework 2.0 tato hodnota musí být 1.  
  
 `dims`  
 [v] Velikost v bajtech, každá dimenze pole.  
  
 `lowBounds`  
 [v] Volitelný parametr. Dolní mez Každá dimenze pole. Pokud tato hodnota je vynechán, předpokládá se, že dolní mez 0 je pro každou dimenzi.  
  
## <a name="remarks"></a>Poznámky  
 Toto pole je vytvořen vždy v doméně aplikace, ve kterém je aktuálně spuštěných vlákno.  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** CorDebug.idl, CorDebug.h  
  
 **Knihovna:** CorGuids.lib  
  
 **Verze rozhraní .NET framework:** 1.1, 1.0

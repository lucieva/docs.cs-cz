---
title: COR_GC_STATS – struktura
ms.date: 03/30/2017
api_name:
- COR_GC_STATS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_GC_STATS
helpviewer_keywords:
- COR_GC_STATS structure [.NET Framework hosting]
ms.assetid: 8d4ff73e-739b-40f6-9349-359fbc99c2f9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 009f1482de6e1daea21766300b4fb6a3ab0ffc8c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/04/2018
ms.locfileid: "33432285"
---
# <a name="corgcstats-structure"></a>COR_GC_STATS – struktura
Poskytuje statistiky o mechanismus kolekce paměti common language runtime (CLR).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef struct _COR_GC_STATS {  
    ULONG   Flags;   
    SIZE_T  ExplicitGCCount;  
    SIZE_T  GenCollectionsTaken[3];  
    SIZE_T  CommittedKBytes;   
    SIZE_T  ReservedKBytes;  
    SIZE_T  Gen0HeapSizeKBytes;  
    SIZE_T  Gen1HeapSizeKBytes;  
    SIZE_T  Gen2HeapSizeKBytes;  
    SIZE_T  LargeObjectHeapSizeKBytes;  
    SIZE_T  KBytesPromotedFromGen0;  
    SIZE_T  KBytesPromotedFromGen1;  
} COR_GC_STATS;  
```  
  
## <a name="members"></a>Členové  
  
|Člen|Popis|  
|------------|-----------------|  
|`Flags`|Určuje pole hodnot, které by mělo být vypočtena a vrátil.|  
|`ExplicitGCCount`|Označuje počet kolekce paměti, které byly vynutit externí požadavek.|  
|`GenCollectionsTaken`|Označuje počet provést pro každou generaci kolekce.|  
|`CommittedKBytes`|Celkový počet kilobajtů potvrzené ve všech haldách|  
|`ReservedKBytes`|Celkový počet kilobajtů vyhrazené ve všech haldách|  
|`Gen0HeapSizeKBytes`|Velikost v kilobajtech haldě generování než nula.|  
|`Gen1HeapSizeKBytes`|Velikost v kilobajtech haldy 1. generace.|  
|`Gen2HeapSizeKBytes`|Velikost v kilobajtech haldě generování dva.|  
|`LargeObjectHeapSizeKBytes`|Velikost v kilobajtech haldě velkého objektu.|  
|`KBytesPromotedFromGen0`|Velikost v kilobajtech objekty povýší z generování nula generace jeden.|  
|`KBytesPromotedFromGen1`|Velikost v kilobajtech povýší z generace, jedna generace dva objekty.|  
  
## <a name="remarks"></a>Poznámky  
 [Iclrgcmanager::getstats –](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) metoda vyžaduje, `Flags` pole z `COR_GC_STATS` struktura bude nastaven na jeden nebo více hodnot [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) výčtu k určete, které statistiky se nastavit.  
  
 Následující tabulka mapuje statistiky poskytované tuto strukturu pro dvě [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) hodnoty výčtu, `COR_GC_COUNTS` a `COR_GC_MEMORYUSAGE`.  
  
|Určeného COR_GC_COUNTS|Určeného COR_GC_MEMORYUSAGE|  
|----------------------------------|---------------------------------------|  
|`ExplicitGCCount`<br /><br /> `GenCollectionsTaken`|`CommittedKBytes`<br /><br /> `ReservedKBytes`<br /><br /> `Gen0HeapSizeKBytes`<br /><br /> `Gen1HeapSizeKBytes`<br /><br /> `Gen2HeapSizeKBytes`<br /><br /> `LargeObjectHeapSizeKBytes`<br /><br /> `KBytesPromotedFromGen0`<br /><br /> `KBytesPromotedFromGen1`|  
  
 Příklad použití je následující:  
  
```  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** GCHost.idl  
  
 **Knihovna:** zahrnuty jako prostředek v MSCorEE.dll  
  
 **Verze rozhraní .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Struktury pro hostování](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
 [Automatická správa paměti](../../../../docs/standard/automatic-memory-management.md)  
 [Uvolňování paměti](../../../../docs/standard/garbage-collection/index.md)

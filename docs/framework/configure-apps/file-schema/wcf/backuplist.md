---
title: '&lt;backupList&gt;'
ms.date: 03/30/2017
ms.assetid: a3d9d1f9-4a53-45e9-a880-86c8bee0b833
ms.openlocfilehash: 6684dcc485ef1ee2c3e5501f2fbc43898e172958
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/03/2018
ms.locfileid: "32747291"
---
# <a name="ltbackuplistgt"></a>&lt;backupList&gt;
Představuje konfigurační oddíl pro definování zálohování seznamu, který se zobrazí sada koncových bodů, které byste chtěli směrovací služby používat v případě, že primární koncový bod není dostupný. Pokud první koncový bod v seznamu je vypnutý, směrovací služby bude automaticky selhání na další stránku v seznamu.  To vám dává rychlý způsob, jak přidat spolehlivost k vaší aplikaci bez nutnosti naučit klientskou aplikaci, jak bude zpracováván komplexní vzory nebo všech služeb, kde jsou nasazeny.  
  
 \<system.serviceModel>  
\<směrování >  
\<backupLists >  
\<backupList >  
  
## <a name="syntax"></a>Syntaxe  
  
```xml 
   <routing>  <backupLists>    <backupList name="String">      <add endpointName="String" />    </backupList>    </backupLists></routing>  
```

## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|name|Řetězec, který určuje název sloužící k identifikaci tento seznam koncových bodů.|  
  
### <a name="child-elements"></a>Podřízené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[\<Filtr >](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md)||  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[\<směrování >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|Seznam koncových bodů zálohování.|  
  
## <a name="remarks"></a>Poznámky  
 Tato část obsahuje uspořádanou kolekci koncových bodů, které zprávy budou předány v případě výjimky komunikace při odesílání na primární koncový bod.  
  
 Pokud odeslání primární koncový bod uvedený v `endpointName` atribut [ \<Přidat >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-entries.md) selže s výjimkou komunikace, směrovací služby pokusí odeslat zprávu na první koncový bod v tomto konfigurační oddíl. Pokud se to nezdaří ani s výjimkou komunikace, se pokusí odeslat zprávu na další zprávu obsažené v této části, dokud nebude pokusu o odeslání úspěšné, vrátí selhání než výjimka komunikaci nebo všechny koncové body ve směrovací služby kolekce mají vrátila chybu.  
  
 V následujícím příkladu Pokud odeslání primární koncový bod s názvem "Cílové" vrátí komunikace výjimky, službu pokusí odeslat zprávu do "alternateServiceQueue". Pokud tento pokus také vrátí hodnotu výjimka komunikace, směrovací služby pokusí odeslat zprávu na další koncový bod v kolekci.  
  
```xml  
<filterTables>  
     <filterTable name="filterTable1">  
          <add filterName="MatchAllFilter1" endpointName="Destination" backupList="backupEndpointList"/>  
     </filterTable>  
</filterTables>  
<backupLists>  
     <backupList name="backupEndpointList">  
          <add endpointName="backupServiceQueue" />  
          <add endpointName="alternateServiceQueue" />  
     </backupList>  
</backupLists>  
```  
  
## <a name="see-also"></a>Viz také  
 <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>    

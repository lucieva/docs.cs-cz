---
title: '&lt;System.Diagnostics&gt; – Element'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.diagnostics
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics
helpviewer_keywords:
- <system.diagnostics> element
- system.diagnostics element
ms.assetid: 3f348f42-fa72-4ff2-aa1c-bb9eecad4bb2
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 35fe167beb53c27aa511e08507415a26b1749ca2
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/02/2018
ms.locfileid: "48029435"
---
# <a name="ltsystemdiagnosticsgt-element"></a>&lt;System.Diagnostics&gt; – Element
Určuje, kteří shromažďování, ukládání a směrovat zprávy a úroveň, kde je nastaven přepínač trasování.  
  
 \<Konfigurace >  
\<System.Diagnostics >  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<system.diagnostics>   
</system.diagnostics>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
 Žádné  
  
### <a name="child-elements"></a>Podřízené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[\<vyhodnocení >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/assert-element.md)|Určuje, jestli se má zobrazit okno se zprávou, když zavoláte <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> metoda; také určuje název souboru pro zápis zpráv do.|  
|[\<čítače výkonu >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/performancecounters-element.md)|Určuje velikost globální paměť sdílenou čítače výkonu.|  
|[\<sharedListeners >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md)|Obsahuje moduly pro naslouchání, které všechny zdroje nebo trasování – element může odkazovat. Naslouchací procesy, které jsou identifikovány jako sdílené moduly pro naslouchání lze přidat do zdroje nebo trasování podle názvu.|  
|[\<zdroje >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sources-element.md)|Určuje zdrojů trasování, které se zahájí trasovací zprávy.|  
|[\<přepínače >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/switches-element.md)|Obsahuje přepínače trasování a úrovně, ve kterém jsou nastavené přepínačů trasování.|  
|[\<trasování >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md)|Obsahuje moduly pro naslouchání, které shromažďování, ukládání a směrovat trasovací zprávy.|  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|`configuration`|Kořenový prvek v každém konfiguračním souboru, který je používán modulem Common Language Runtime (CLR) a aplikacemi rozhraní .NET Framework.|  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje postup vložení přepínače trasování a posluchače trasování uvnitř  **\<system.diagnostics >** elementu. `General` Trasování přepínač nastavený na <xref:System.Diagnostics.TraceLevel> úroveň. Naslouchací proces trasování `myListener` vytvoří soubor s názvem `MyListener.log` a zapíše výstup do souboru.  
  
> [!NOTE]
>  V rozhraní .NET Framework verze 2.0 můžete zadat hodnotu pro přepínač text. Například můžete zadat `true` pro <xref:System.Diagnostics.BooleanSwitch> nebo textů představující hodnotu výčtu, jako `Error` pro <xref:System.Diagnostics.TraceSwitch>. Na řádku `<add name="myTraceSwitch" value="Error" />` je ekvivalentní `<add name="myTraceSwitch" value="1" />`.  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <switches>  
         <add name="General" value="4" />  
      </switches>  
      <trace autoflush="true" indentsize="2">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, System, Version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="MyListener.log" traceOutputOptions="ProcessId, LogicalOperationStack, Timestamp, ThreadId, Callstack, DateTime" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Diagnostics.Trace>  
 <xref:System.Diagnostics.Debug>  
 [Trasování a ladění schématu nastavení](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)

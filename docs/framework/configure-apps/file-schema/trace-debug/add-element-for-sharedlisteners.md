---
title: '&lt;Přidat&gt; – Element pro &lt;sharedListeners&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <sharedListeners>
- add element for <sharedListeners>
ms.assetid: 1595e1bc-2492-421f-8384-7f382eb8eb57
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 93fdb548882422634e1d2456b4d37f434b278f8d
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/06/2018
ms.locfileid: "48845369"
---
# <a name="ltaddgt-element-for-ltsharedlistenersgt"></a>&lt;Přidat&gt; – Element pro &lt;sharedListeners&gt;
Přidá naslouchací proces pro `sharedListeners` kolekce. `sharedListeners` je kolekce naslouchacích procesů, aby každá [ \<zdroj >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md) nebo [ \<trasování >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md) můžete odkazovat.  Ve výchozím nastavení, moduly pro naslouchání v `sharedListeners` kolekce nejsou umístěny v `Listeners` kolekce. Musí se přidat název, který [ \<zdroj >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md) nebo [ \<trasování >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md). Není možné získat naslouchacím procesům `sharedListeners` kolekce v kódu v době běhu.  
  
 \<Konfigurace >  
\<System.Diagnostics >  
\<sharedListeners > – Element  
\<add>  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<add name="name"   
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`name`|Požadovaný atribut.<br /><br /> Určuje název, který se používá k přidání sdílené naslouchací proces pro naslouchací proces `Listeners` kolekce.|  
|`type`|Požadovaný atribut.<br /><br /> Určuje typ naslouchací proces. Je nutné použít řetězec, který splňuje požadavky uvedené v [zadání plně kvalifikované názvy typů](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|`initializeData`|Nepovinný atribut.<br /><br /> Řetězec předaný konstruktoru pro zadanou třídu.|  
  
### <a name="child-elements"></a>Podřízené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[\<Filtr >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-sharedlisteners.md)|Přidá filtr do naslouchacího procesu v `sharedListeners` kolekce.|  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|`configuration`|Kořenový prvek v každém konfiguračním souboru, který je používán modulem Common Language Runtime (CLR) a aplikacemi rozhraní .NET Framework.|  
|`system.diagnostics`|Určuje, kteří shromažďování, ukládání a směrovat zprávy a úroveň, kde je nastaven přepínač trasování.|  
|`sharedListeners`|Kolekce naslouchacích procesů, které všechny zdroje nebo trasování – element může odkazovat.|  
  
## <a name="remarks"></a>Poznámky  
 Naslouchací proces třídy součástí rozhraní .NET Framework jsou odvozeny od <xref:System.Diagnostics.TraceListener> třídy. Hodnota `name` atribut se používá k přidání sdílené naslouchací proces pro `Listeners` kolekce pro trasování nebo zdroje trasování. Hodnota `initializeData` atributu závisí na typu naslouchacího procesu vytvoříte. Ne všechny moduly pro naslouchání trasování vyžadují, abyste určili `initializeData`.  
  
> [!NOTE]
>  Při použití `initializeData` atributu, může se zobrazit kompilátoru upozornění "není deklarovaný atribut"initializeData"." K tomuto upozornění dochází, protože nastavení konfigurace se ověří proti abstraktní základní třída <xref:System.Diagnostics.TraceListener>, které nebylo rozpoznáno `initializeData` atribut. Obvykle můžete ignorovat toto upozornění pro implementace naslouchací proces trasování, které mají konstruktor, který přijímá parametr.  
  
 Následující tabulka uvádí naslouchacích procesů trasování, které jsou součástí rozhraní .NET Framework a popisuje výhody jejich `initializeData` atributy.  
  
|Třída naslouchací proces trasování|Hodnota atributu initializeData|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener>|`useErrorStream` Hodnota <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> konstruktoru.  Nastavte `initializeData` atribut "`true`"zápis trasování a ladění výstupu na standardní chybový proud; nastavte ho na"`false`" k zápisu do standardního výstupního datového proudu.|  
|<xref:System.Diagnostics.DelimitedListTraceListener>|Název souboru <xref:System.Diagnostics.DelimitedListTraceListener> zapíše do.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|Název existující zdroj protokolu událostí.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|Název souboru, který <xref:System.Diagnostics.EventSchemaTraceListener> zapíše do.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|Název souboru, který <xref:System.Diagnostics.TextWriterTraceListener> zapíše do.|  
|<xref:System.Diagnostics.XmlWriterTraceListener>|Název souboru, který <xref:System.Diagnostics.XmlWriterTraceListener> zapíše do.|  
  
## <a name="configuration-file"></a>Konfigurační soubor  
 Tento element lze použít v konfiguračním souboru počítače (Machine.config) a konfigurační soubor aplikace.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak používat `<add>` prvky pro přidání <xref:System.Diagnostics.TextWriterTraceListener> `textListener` k `sharedListeners` kolekce.   `textListener` název, který přidává `Listeners` kolekce pro zdroj trasování `TraceSourceApp`. `textListener` Naslouchacího procesu zapisuje do souboru myListener.log výstupu trasování.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="TraceSourceApp" switchName="sourceSwitch"   
        switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <add name="console"   
            type="System.Diagnostics.ConsoleTraceListener"/>  
          <add name="textListener"/>  
          <remove name="Default"/>  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="textListener"   
        type="System.Diagnostics.TextWriterTraceListener"   
        initializeData="myListener.log"/>  
    </sharedListeners>  
    <switches>  
      <add name="sourceSwitch" value="Warning"/>  
    </switches>  
  </system.diagnostics>  
</configuration>   
```  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Diagnostics.TraceSource>  
 <xref:System.Diagnostics.TraceListener>  
 [Trasování a ladění schématu nastavení](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [Moduly naslouchání trasování](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)

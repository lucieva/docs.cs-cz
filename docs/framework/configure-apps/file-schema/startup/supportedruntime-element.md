---
title: '&lt;supportedRuntime&gt; – Element'
ms.date: 04/10/2018
ms.custom: updateeachrelease
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#supportedRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/supportedRuntime
helpviewer_keywords:
- supportedRuntime element
- <supportedRuntime> element
ms.assetid: 1ae16e23-afbe-4de4-b413-bc457f37b69f
author: mcleblanc
ms.author: markl
ms.openlocfilehash: b86ffdd242a95a0c5c34efb3f38b3501f3f2ba6c
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/26/2018
ms.locfileid: "47197796"
---
# <a name="ltsupportedruntimegt-element"></a>&lt;supportedRuntime&gt; – Element

Určuje, kterou verzi modulu Common Language Runtime (CLR) aplikace podporuje. Tento prvek by měl být použit všemi aplikacemi sestavenými pomocí rozhraní .NET Framework 1.1 a staršími verzemi.  
  
[\<Konfigurace >](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
&nbsp;&nbsp;[\<Po spuštění >](../../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<supportedRuntime >**  
  
## <a name="syntax"></a>Syntaxe
  
```xml  
<supportedRuntime version="runtime version" sku="sku id"/>  
```  
  
## <a name="attributes"></a>Atributy
  
|Atribut|Popis|  
|---------------|-----------------|  
|**Verze**|Nepovinný atribut.<br /><br /> Hodnota řetězce, která určuje verzi modulu Common Language Runtime (CLR), který aplikace podporuje. Pro platné hodnoty `version` atributu naleznete v tématu [hodnoty "verze modulu runtime"](#version) oddílu. **Poznámka:** prostřednictvím rozhraní .NET Framework 3.5 "*verze modulu runtime*" hodnota má podobu *hlavní*. *vedlejší*. *sestavení*. Počínaje [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], pouze požadované číslo hlavní verze a podverze (tedy "v4.0" místo "v4.0.30319"). Je doporučen kratší řetězec.|  
|**sku**|Nepovinný atribut.<br /><br /> Řetězcová hodnota, která určuje skladové jednotky (SKU), která zase Určuje, jaké verze rozhraní .NET Framework podporuje tuto aplikaci.<br /><br /> Od verze rozhraní .NET Framework 4.0, použití `sku` atribut se doporučuje.  Pokud je přítomen, určuje verzi rozhraní .NET Framework, který aplikace cílí.<br /><br /> Platné hodnoty atributu sku najdete v článku [hodnoty "sku id"](#sku) oddílu.|  
  
## <a name="remarks"></a>Poznámky

Pokud  **\<supportedRuntime >** prvek není k dispozici v konfiguračním souboru aplikace, je použita verze modulu runtime používá k sestavení aplikace.  

**\<SupportedRuntime >** element by měl být použit všemi aplikacemi sestavenými pomocí verze 1.1 nebo novější modul runtime. Aplikace sestavené s podporou pouze verze 1.0 modulu runtime musí použít [ \<requiredRuntime >](../../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md) elementu.  
  
> [!NOTE]
>  Pokud používáte [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md) funkce zadejte konfigurační soubor, je nutné použít `<requiredRuntime>` – element pro všechny verze modulu runtime. `<supportedRuntime>` Prvek je ignorován při použití [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md).  
  
U aplikací podporujících verze modulu runtime v rozhraní .NET Framework 1.1 až 3.5, když se podporují více verzí modulu runtime, první prvek měl specifikovat nejvíce preferovanou verzi modulu runtime a poslední prvek měl specifikovat nejméně preferovanou verzi. Pro aplikace, které podporují rozhraní .NET Framework 4.0 nebo novější verze `version` atribut označuje verzi CLR, která je společná pro rozhraní .NET Framework 4 a novější verze, a `sku` atribut označuje jednu verzi rozhraní .NET Framework, která aplikace cíle.  
  
> [!NOTE]
>  Pokud vaše aplikace používá starší verzi aktivační cesty, jako [CorBindToRuntimeEx – funkce](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), a chcete, aby tyto cesty k aktivaci místo starší verzi modulu CLR verze 4 nebo pokud je vaše aplikace je sestavena pomocí [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], ale má závislost na sestavení ve smíšeném režimu, vytvořené ve starší verzi rozhraní .NET Framework, nestačí k určení [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] v seznamu podporovaných modulů runtime. Kromě toho v [ \<spuštění > element](../../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) v konfiguračním souboru, je nutné nastavit `useLegacyV2RuntimeActivationPolicy` atribut `true`. Však nastavení tohoto atributu na `true` znamená, že všechny komponenty sestavené v předchozích verzích rozhraní .NET Framework budou spuštěny pomocí [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] namísto modulů runtime, kterými byly vytvořeny.  
  
Doporučujeme aplikaci otestovat se všemi verzemi .NET Framework, na kterých by měla být spuštěna.  
  
<a name="version"></a>   
## <a name="runtime-version-values"></a>hodnoty "verze modulu runtime"  
`runtime` Atribut určuje verzi Common Language Runtime (CLR), která je požadována pro danou aplikaci. Všimněte si, že všechny verze rozhraní .NET Framework v4.x zadejte `v4.0` CLR. V následující tabulce jsou uvedeny platné hodnoty pro *verze modulu runtime* hodnotu `version` atribut.  

|Verze rozhraní .NET Framework|`version` Atribut|  
|----------------------------|-------------------------|  
|1.0|"v1.0.3705"|  
|1.1|"v1.1.4322"|  
|2.0|"v2.0.50727"|  
|3.0|"v2.0.50727"|  
|3.5|"v2.0.50727"|  
|4.0 4.7.2|"v4.0"|  

<a name="sku"></a>   
## <a name="sku-id-values"></a>"sku id" hodnot

`sku` Atribut používá moniker cílového rozhraní (TFM) k označení verze rozhraní .NET Framework, zaměřuje a vyžaduje ke spuštění aplikace. V následující tabulce jsou uvedeny platné hodnoty, které jsou podporovány `sku` atribut od verze rozhraní .NET Framework 4.
  
|Verze rozhraní .NET Framework|`sku` Atribut|  
|----------------------------|---------------------|  
|4.0|". NETFramework, verze = v4.0 "|  
|4.0 client Profile|". NETFramework, verze = v4.0 profilu klienta = "|  
|4.0, aktualizace platformy 1|.NETFramework,Version=v4.0.1|  
|4.0 client Profile, aktualizace 1|.NETFramework,Version=v4.0.1,Profile=Client|  
|4.0, aktualizace platformy 2|.NETFramework,Version=v4.0.2|  
|4.0 client Profile update 2|.NETFramework,Version=v4.0.2,Profile=Client|  
|4.0, aktualizace platformy 3|.NETFramework,Version=v4.0.3|  
|4.0 client Profile update 3|.NETFramework,Version=v4.0.3,Profile=Client|  
|4.5|". NETFramework, verze = v4.5 "|  
|4.5.1|". NETFramework, verze = v4.5.1 "|  
|4.5.2|". NETFramework, verze = v4.5.2 "|  
|4.6|". NETFramework, verze = v4.6 "|  
|4.6.1|". NETFramework, verze = v4.6.1 "|  
|4.6.2|". NETFramework, verze = v4.6.2 "|  
|4.7|". NETFramework, verze = v4.7 "|
|4.7.1|". NETFramework, verze = v4.7.1 "|
|4.7.2|". NETFramework, verze = v4.7.2 "|

## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak určit verzi podporovaného modulu runtime v konfiguračním souboru. Konfigurační soubor označuje, že aplikace cílí na rozhraní .NET Framework 4.7.  
  
```xml  
<configuration>  
   <startup>  
      <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.7" />  
   </startup>  
</configuration>  
```  
  
## <a name="configuration-file"></a>Konfigurační soubor

Tento element lze použít v konfiguračním souboru aplikace.

## <a name="see-also"></a>Viz také:

 [Schéma nastavení spouštění](../../../../../docs/framework/configure-apps/file-schema/startup/index.md)  
 [Schéma konfiguračního souboru](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [Vnitroprocesové souběžné provádění](../../../../../docs/framework/deployment/in-process-side-by-side-execution.md)  

---
title: fatalExecutionEngineError – pomocník spravovaného ladění (MDA)
ms.date: 03/30/2017
helpviewer_keywords:
- corrupted CLR
- fatal execution error
- terminated processes
- unexpected terminations
- fatal errors
- MDAs (managed debugging assistants), fatal errors
- process termination
- FatalExecutionEngineError MDA
- managed debugging assistants (MDAs), fatal errors
ms.assetid: 8b559e44-2393-4e4e-8160-7558d37a4a89
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f12b94198b88111d559cfe372c28bdbf4b37e3fe
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/05/2018
ms.locfileid: "43742641"
---
# <a name="fatalexecutionengineerror-mda"></a>fatalExecutionEngineError – pomocník spravovaného ladění (MDA)
`fatalExecutionEngineError` Pomocníka spravovaného ladění (MDA) se aktivuje, když byla zjištěna závažná chyba v modulu common language runtime (CLR). Proces bude ukončen.  
  
## <a name="symptoms"></a>Příznaky  
 Ukončení procesu pro neočekávané. Další příznaky nelze určit, protože může dojít k selhání modulu CLR pro celou řadu důvodů.  
  
## <a name="cause"></a>příčina  
 Modul CLR byl fatálně poškozen. To je často způsobeno poškození dat, která může být způsobeno různé problémy, jako například volání na poškozené platformu vyvolání funkce a předáním neplatná data modulu CLR.  
  
## <a name="resolution"></a>Rozlišení  
 Povolení dalších mda mohou pomoci při identifikaci problému. Následující mda může být zvláště užitečné při diagnostice problému:  
  
-   [invalidOverlappedToPinvoke](../../../docs/framework/debug-trace-profile/invalidoverlappedtopinvoke-mda.md)  
  
-   [overlappedFreeError](../../../docs/framework/debug-trace-profile/overlappedfreeerror-mda.md)  
  
-   [pInvokeStackImbalance](../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md)  
  
-   [gcUnmanagedToManaged](../../../docs/framework/debug-trace-profile/gcunmanagedtomanaged-mda.md)  
  
-   [gcManagedToUnmanaged](../../../docs/framework/debug-trace-profile/gcmanagedtounmanaged-mda.md)  
  
-   [callbackOnCollectedDelegate](../../../docs/framework/debug-trace-profile/callbackoncollecteddelegate-mda.md)  
  
-   [reportAvOnComRelease](../../../docs/framework/debug-trace-profile/reportavoncomrelease-mda.md)  
  
-   [invalidVariant](../../../docs/framework/debug-trace-profile/invalidvariant-mda.md)  
  
-   [invalidIUnknown](../../../docs/framework/debug-trace-profile/invalidiunknown-mda.md)  
  
-   [raceOnRCWCleanup](../../../docs/framework/debug-trace-profile/raceonrcwcleanup-mda.md)  
  
-   [invalidFunctionPointerInDelegate](../../../docs/framework/debug-trace-profile/invalidfunctionpointerindelegate-mda.md)  
  
-   [invalidGCHandleCookie](../../../docs/framework/debug-trace-profile/invalidgchandlecookie-mda.md)  
  
## <a name="effect-on-the-runtime"></a>Vliv na modul Runtime  
 Toto MDA nemá žádný vliv na chování modulu runtime.  
  
## <a name="output"></a>Výstup  
 Adresa funkce modulu CLR, která způsobila závažná chyba a ID vlákna, kde došlo k chybě, kód chyby.  
  
## <a name="configuration"></a>Konfigurace  
  
```xml  
<mdaConfig>  
  <assistants>  
    <fatalExecutionEngineError />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>  
 <xref:System.Runtime.ConstrainedExecution.Cer>  
 [Diagnostikování chyb pomocí asistentů spravovaného ladění](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)

---
title: Práce s vlákny funkce a objekty
ms.date: 10/01/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], features
- managed threading
ms.assetid: 239b2e8d-581b-4ca3-992b-0e8525b9321c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1ba47ece16c74555b58780733e14de9833718c33
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/08/2018
ms.locfileid: "48873304"
---
# <a name="threading-objects-and-features"></a>Práce s vlákny funkce a objekty

Spolu s <xref:System.Threading.Thread?displayProperty=nameWithType> třídy .NET poskytuje několik tříd, které umožňují vývoj aplikací s více vlákny. Následující články poskytují přehled těchto tříd:

|Název|Popis|  
|-----------|-----------------|  
|[Spravovaný fond vláken](the-managed-thread-pool.md)|Popisuje <xref:System.Threading.ThreadPool?displayProperty=nameWithType> třídu, která poskytuje fondu pracovních vláken, které se spravují přes rozhraní .NET.|  
|[Časovače](timers.md)|Popisuje .NET časovače, které lze použít v prostředí s více vlákny.|
|[Přehled primitiv synchronizace](overview-of-synchronization-primitives.md)|Popisuje typy, které slouží k synchronizaci přístupu k sdíleného prostředku nebo vlákna interakce ovládacího prvku.|
|[EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)|Popisuje obslužné rutiny čekání spravované události, které se používají k synchronizaci aktivity vláken signalizace a čeká na signál.|
|[Mutex – třídy](mutexes.md)|Popisuje <xref:System.Threading.Mutex?displayProperty=nameWithType>, která uděluje exkluzivní přístup ke sdíleným prostředkům.|
|[Propojené operace](interlocked-operations.md)|Popisuje <xref:System.Threading.Interlocked?displayProperty=nameWithType> třídu, která poskytuje atomických operací pro proměnné, které jsou sdíleny více vlákny.|
|[Zámky modulů pro čtení a zápis](reader-writer-locks.md)|Popisuje <xref:System.Threading.ReaderWriterLockSlim?displayProperty=nameWithType> třídu, která poskytuje jeden – zapisovač/více čtečky přístup ke sdíleným prostředkům.|
|[Semaphore a SemaphoreSlim](semaphore-and-semaphoreslim.md)|Popisuje <xref:System.Threading.Semaphore?displayProperty=nameWithType> třídu, která omezuje počet vláken, které můžete přístup ke sdílenému prostředku nebo fond prostředků současně.|
|[Barrier](barrier.md)|Popisuje <xref:System.Threading.Barrier?displayProperty=nameWithType> třídu, která implementuje vzor barrier koordinace vláken v postupné operacích.|
|[SpinLock](spinlock.md)|Popisuje <xref:System.Threading.SpinLock?displayProperty=nameWithType> strukturu, která představuje jednoduché alternativa <xref:System.Threading.Monitor?displayProperty=nameWithType> třídy pro určité scénáře nízké úrovně zamykání.|
|[SpinWait](spinwait.md)|Popisuje <xref:System.Threading.SpinWait?displayProperty=nameWithType> strukturu, která poskytuje podporu pro čekání na základě typu číselník.|

## <a name="see-also"></a>Viz také:

- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.WaitHandle?displayProperty=nameWithType>
- <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>
- [Použití vláken a dělení na vlákna](using-threads-and-threading.md)
- [Asynchronní vstupně-výstupní operace se soubory](../io/asynchronous-file-i-o.md)
- [Paralelní programování](../parallel-programming/index.md)
- [Task Parallel Library (TPL)](../parallel-programming/task-parallel-library-tpl.md)

---
title: Dotazování na stav asynchronní operace
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- asynchronous programming, status polling
- polling asynchronous operation status
- status information [.NET Framework], asynchronous operations
ms.assetid: b541af31-dacb-4e20-8847-1b1ff7c35363
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d380e369d9620fc0fc87a2c443be318083174882
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/18/2018
ms.locfileid: "45991396"
---
# <a name="polling-for-the-status-of-an-asynchronous-operation"></a>Dotazování na stav asynchronní operace
Aplikace, které můžete provádět další operace při čekání na výsledcích asynchronní operace by neměly blokovat čekání, až do dokončení operace. Má pokračovat provedením pokyny při čekání na dokončení asynchronní operace, použijte jednu z následujících možností:  
  
-   Použití <xref:System.IAsyncResult.IsCompleted%2A> vlastnost <xref:System.IAsyncResult> vrácený asynchronní operace **začít *** OperationName* metodou ke zjištění, zda operace byla dokončena. Tento postup se označuje jako cyklického dotazování a je ukázáno v tomto tématu.  
  
-   Použití <xref:System.AsyncCallback> delegáta ke zpracování výsledků asynchronních operací v samostatném vlákně. Příklad, který ukazuje tento přístup, najdete v části [použití delegáta AsyncCallback k ukončení asynchronní operace](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje použití asynchronních metod v <xref:System.Net.Dns> třídy načíst informace o systému názvů domény pro počítače zadané uživatelem. Tento příklad spustí asynchronní operaci a potom zobrazí období (".") v konzole až do dokončení operace. Všimněte si, že **null** (**nic** v jazyce Visual Basic) je předán <xref:System.Net.Dns.BeginGetHostByName%2A> <xref:System.AsyncCallback> a <xref:System.Object> parametry vzhledem k tomu, že tyto argumenty nejsou vyžadovány, při použití tohoto přístupu.  
  
 [!code-csharp[AsyncDesignPattern#3](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_Poll.cs#3)]
 [!code-vb[AsyncDesignPattern#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_Poll.vb#3)]  
  
## <a name="see-also"></a>Viz také:

- [Asynchronní vzor založený na událostech (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
- [Přehled asynchronních vzorů založených na událostech](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)

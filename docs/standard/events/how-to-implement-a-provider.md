---
title: 'Postupy: Implementace poskytovatele'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- observer design pattern [.NET Framework], implementing providers
- providers [.NET Framework], in observer design pattern
- observables [.NET Framework], in observer design pattern
ms.assetid: 790b5d8b-d546-40a6-beeb-151b574e5ee5
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b9d8f96de8cb3d13568e755f1d5e885e0474d891
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-a-provider"></a><span data-ttu-id="60b86-102">Postupy: Implementace poskytovatele</span><span class="sxs-lookup"><span data-stu-id="60b86-102">How to: Implement a Provider</span></span>
<span data-ttu-id="60b86-103">Návrhový vzor pozorovatel vyžaduje rozdělení zprostředkovatele, který monitoruje data a odešle oznámení, a jeden nebo více pozorovatelů, které dostávat oznámení (zpětná volání) od zprostředkovatele.</span><span class="sxs-lookup"><span data-stu-id="60b86-103">The observer design pattern requires a division between a provider, which monitors data and sends notifications, and one or more observers, which receive notifications (callbacks) from the provider.</span></span> <span data-ttu-id="60b86-104">Toto téma popisuje postup vytvoření poskytovatele.</span><span class="sxs-lookup"><span data-stu-id="60b86-104">This topic discusses how to create a provider.</span></span> <span data-ttu-id="60b86-105">Související téma, [postupy: implementace pozorovatele](../../../docs/standard/events/how-to-implement-an-observer.md), popisuje, jak vytvořit pozorovatele.</span><span class="sxs-lookup"><span data-stu-id="60b86-105">A related topic, [How to: Implement an Observer](../../../docs/standard/events/how-to-implement-an-observer.md), discusses how to create an observer.</span></span>  
  
### <a name="to-create-a-provider"></a><span data-ttu-id="60b86-106">Chcete-li vytvořit poskytovatele</span><span class="sxs-lookup"><span data-stu-id="60b86-106">To create a provider</span></span>  
  
1.  <span data-ttu-id="60b86-107">Zadejte data, která je odpovědná za zasílání pozorovatelů zprostředkovatele.</span><span class="sxs-lookup"><span data-stu-id="60b86-107">Define the data that the provider is responsible for sending to observers.</span></span> <span data-ttu-id="60b86-108">I když mezi poskytovatelem a data, která odešle pozorovatelů může být jeden typ, jsou obecně reprezentované pomocí různých typů.</span><span class="sxs-lookup"><span data-stu-id="60b86-108">Although the provider and the data that it sends to observers can be a single type, they are generally represented by different types.</span></span> <span data-ttu-id="60b86-109">Například v teplotě monitorování aplikace `Temperature` struktura definují data, která zprostředkovatele (která je reprezentována `TemperatureMonitor` třídy definované v dalším kroku) monitoruje a do které pozorovatelů přihlášení k odběru.</span><span class="sxs-lookup"><span data-stu-id="60b86-109">For example, in a temperature monitoring application, the `Temperature` structure defines the data that the provider (which is represented by the `TemperatureMonitor` class defined in the next step) monitors and to which observers subscribe.</span></span>  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/data.cs#1)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/data.vb#1)]  
  
2.  <span data-ttu-id="60b86-110">Zadejte poskytovatele dat, který je typ, který implementuje <xref:System.IObservable%601?displayProperty=nameWithType> rozhraní.</span><span class="sxs-lookup"><span data-stu-id="60b86-110">Define the data provider, which is a type that implements the <xref:System.IObservable%601?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="60b86-111">Argument obecného typu poskytovatele je typ, který odešle zprostředkovatel pozorovatelů.</span><span class="sxs-lookup"><span data-stu-id="60b86-111">The provider's generic type argument is the type that the provider sends to observers.</span></span> <span data-ttu-id="60b86-112">V následujícím příkladu definuje `TemperatureMonitor` třída, která je vytvořený <xref:System.IObservable%601?displayProperty=nameWithType> implementace s argumentem obecného typu ve `Temperature`.</span><span class="sxs-lookup"><span data-stu-id="60b86-112">The following example defines a `TemperatureMonitor` class, which is a constructed <xref:System.IObservable%601?displayProperty=nameWithType> implementation with a generic type argument of `Temperature`.</span></span>  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#2)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#2)]  
  
3.  <span data-ttu-id="60b86-113">Zjistěte, jak se zprostředkovatel uloží odkazy na pozorovatelů tak, aby každý pozorovatel může být upozorněni, když je to vhodné.</span><span class="sxs-lookup"><span data-stu-id="60b86-113">Determine how the provider will store references to observers so that each observer can be notified when appropriate.</span></span> <span data-ttu-id="60b86-114">Nejčastěji objekt kolekce například obecný <xref:System.Collections.Generic.List%601> objekt se používá pro tento účel.</span><span class="sxs-lookup"><span data-stu-id="60b86-114">Most commonly, a collection object such as a generic <xref:System.Collections.Generic.List%601> object is used for this purpose.</span></span> <span data-ttu-id="60b86-115">V následujícím příkladu definuje privátního <xref:System.Collections.Generic.List%601> objekt, který je v instanci `TemperatureMonitor` konstruktoru třídy.</span><span class="sxs-lookup"><span data-stu-id="60b86-115">The following example defines a private <xref:System.Collections.Generic.List%601> object that is instantiated in the `TemperatureMonitor` class constructor.</span></span>  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#3)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#3)]  
  
4.  <span data-ttu-id="60b86-116">Definování <xref:System.IDisposable> implementace, která může poskytovatel tak, aby se může zastavit příjem oznámení kdykoli vrátit odběratelům.</span><span class="sxs-lookup"><span data-stu-id="60b86-116">Define an <xref:System.IDisposable> implementation that the provider can return to subscribers so that they can stop receiving notifications at any time.</span></span> <span data-ttu-id="60b86-117">V následujícím příkladu definuje vnořený `Unsubscriber` třídu, která byla předána odkaz na kolekci odběratele a k odběrateli, při vytváření instance třídy.</span><span class="sxs-lookup"><span data-stu-id="60b86-117">The following example defines a nested `Unsubscriber` class that is passed a reference to the subscribers collection and to the subscriber when the class is instantiated.</span></span> <span data-ttu-id="60b86-118">Tento kód umožňuje odběratele pro volání objektu <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> implementace do kolekce odběratele.</span><span class="sxs-lookup"><span data-stu-id="60b86-118">This code enables the subscriber to call the object's <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> implementation to remove itself from the subscribers collection.</span></span>  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#4)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#4)]  
  
5.  <span data-ttu-id="60b86-119">Implementace <xref:System.IObservable%601.Subscribe%2A?displayProperty=nameWithType> metoda.</span><span class="sxs-lookup"><span data-stu-id="60b86-119">Implement the <xref:System.IObservable%601.Subscribe%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="60b86-120">Metodě se předává odkaz na <xref:System.IObserver%601?displayProperty=nameWithType> rozhraní a by měly být uložené v objektu určený pro tento účel v kroku 3.</span><span class="sxs-lookup"><span data-stu-id="60b86-120">The method is passed a reference to the <xref:System.IObserver%601?displayProperty=nameWithType> interface and should be stored in the object designed for that purpose in step 3.</span></span> <span data-ttu-id="60b86-121">Metoda by měla pak se vraťte <xref:System.IDisposable> implementace vyvinuté v kroku 4.</span><span class="sxs-lookup"><span data-stu-id="60b86-121">The method should then return the <xref:System.IDisposable> implementation developed in step 4.</span></span> <span data-ttu-id="60b86-122">Následující příklad ukazuje implementaci <xref:System.IObservable%601.Subscribe%2A> metoda v `TemperatureMonitor` třídy.</span><span class="sxs-lookup"><span data-stu-id="60b86-122">The following example shows the implementation of the <xref:System.IObservable%601.Subscribe%2A> method in the `TemperatureMonitor` class.</span></span>  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#5)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#5)]  
  
6.  <span data-ttu-id="60b86-123">Oznámit pozorovatelů podle potřeby voláním jejich <xref:System.IObserver%601.OnNext%2A?displayProperty=nameWithType>, <xref:System.IObserver%601.OnError%2A?displayProperty=nameWithType>, a <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> implementace.</span><span class="sxs-lookup"><span data-stu-id="60b86-123">Notify observers as appropriate by calling their <xref:System.IObserver%601.OnNext%2A?displayProperty=nameWithType>, <xref:System.IObserver%601.OnError%2A?displayProperty=nameWithType>, and <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> implementations.</span></span> <span data-ttu-id="60b86-124">V některých případech nemusí volání zprostředkovatele <xref:System.IObserver%601.OnError%2A> metoda, když dojde k chybě.</span><span class="sxs-lookup"><span data-stu-id="60b86-124">In some cases, a provider may not call the <xref:System.IObserver%601.OnError%2A> method when an error occurs.</span></span> <span data-ttu-id="60b86-125">Například následující `GetTemperature` metoda simuluje monitorování, který čte data teploty každých pět sekund a pozorovatelů upozorní, pokud teplota došlo ke změně v alespoň.1 úhlu od předchozí čtení.</span><span class="sxs-lookup"><span data-stu-id="60b86-125">For example, the following `GetTemperature` method simulates a monitor that reads temperature data every five seconds and notifies observers if the temperature has changed by at least .1 degree since the previous reading.</span></span> <span data-ttu-id="60b86-126">Pokud zařízení nevytváří sestavu teplotě (to znamená, pokud je jeho hodnota null), zprostředkovatele oznámí pozorovatelů, přenos je dokončena.</span><span class="sxs-lookup"><span data-stu-id="60b86-126">If the device does not report a temperature (that is, if its value is null), the provider notifies observers that the transmission is complete.</span></span> <span data-ttu-id="60b86-127">Všimněte si, že, kromě volání každý pozorovatel <xref:System.IObserver%601.OnCompleted%2A> metody `GetTemperature` metoda vymaže <xref:System.Collections.Generic.List%601> kolekce.</span><span class="sxs-lookup"><span data-stu-id="60b86-127">Note that, in addition to calling each observer's <xref:System.IObserver%601.OnCompleted%2A> method, the `GetTemperature` method clears the <xref:System.Collections.Generic.List%601> collection.</span></span> <span data-ttu-id="60b86-128">V takovém případě zprostředkovatele provádí žádné volání na <xref:System.IObserver%601.OnError%2A> metoda jeho pozorovatelů.</span><span class="sxs-lookup"><span data-stu-id="60b86-128">In this case, the provider makes no calls to the <xref:System.IObserver%601.OnError%2A> method of its observers.</span></span>  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#6)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="60b86-129">Příklad</span><span class="sxs-lookup"><span data-stu-id="60b86-129">Example</span></span>  
 <span data-ttu-id="60b86-130">Následující příklad obsahuje kompletní zdrojový kód pro definování <xref:System.IObservable%601> implementace teplotě monitorování aplikace.</span><span class="sxs-lookup"><span data-stu-id="60b86-130">The following example contains the complete source code for defining an <xref:System.IObservable%601> implementation for a temperature monitoring application.</span></span> <span data-ttu-id="60b86-131">Obsahuje `Temperature` struktura, což je dat odesílaných pozorovatelů, a `TemperatureMonitor` třída, která je <xref:System.IObservable%601> implementace.</span><span class="sxs-lookup"><span data-stu-id="60b86-131">It includes the `Temperature` structure, which is the data sent to observers, and the `TemperatureMonitor` class, which is the <xref:System.IObservable%601> implementation.</span></span>  
  
 [!code-csharp[Conceptual.ObserverDesign.HowTo#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#7)]
 [!code-vb[Conceptual.ObserverDesign.HowTo#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="60b86-132">Viz také</span><span class="sxs-lookup"><span data-stu-id="60b86-132">See Also</span></span>  
 <xref:System.IObservable%601>  
 [<span data-ttu-id="60b86-133">Návrhový vzor pozorovatel</span><span class="sxs-lookup"><span data-stu-id="60b86-133">Observer Design Pattern</span></span>](../../../docs/standard/events/observer-design-pattern.md)  
 [<span data-ttu-id="60b86-134">Postupy: implementace pozorovatele</span><span class="sxs-lookup"><span data-stu-id="60b86-134">How to: Implement an Observer</span></span>](../../../docs/standard/events/how-to-implement-an-observer.md)  
 [<span data-ttu-id="60b86-135">Pozorovatel osvědčené postupy pro návrhový vzor</span><span class="sxs-lookup"><span data-stu-id="60b86-135">Observer Design Pattern Best Practices</span></span>](../../../docs/standard/events/observer-design-pattern-best-practices.md)
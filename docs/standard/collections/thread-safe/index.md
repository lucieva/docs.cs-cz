---
title: "Kolekce se zabezpečenými vlákny"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: thread-safe collections, overview
ms.assetid: 2e7ca21f-786c-4367-96be-0cf3f3dcc6bd
caps.latest.revision: "24"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b5394cd2e9c9fa2b0cacb93ddf2cf05b33fabc71
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="thread-safe-collections"></a><span data-ttu-id="5812e-102">Kolekce se zabezpečenými vlákny</span><span class="sxs-lookup"><span data-stu-id="5812e-102">Thread-Safe Collections</span></span>
<span data-ttu-id="5812e-103">[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] Zavádí <xref:System.Collections.Concurrent?displayProperty=nameWithType> názvů, který zahrnuje několik tříd kolekcí, které jsou bezpečné pro přístup z více vláken a škálovatelné.</span><span class="sxs-lookup"><span data-stu-id="5812e-103">The [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] introduces the <xref:System.Collections.Concurrent?displayProperty=nameWithType> namespace, which includes several collection classes that are both thread-safe and scalable.</span></span> <span data-ttu-id="5812e-104">Více vláken může bezpečně a efektivně přidat nebo odebrat položky z těchto kolekcí, bez nutnosti další synchronizace v uživatelském kódu.</span><span class="sxs-lookup"><span data-stu-id="5812e-104">Multiple threads can safely and efficiently add or remove items from these collections, without requiring additional synchronization in user code.</span></span> <span data-ttu-id="5812e-105">Když píšete nový kód, pomocí třídy souběžných kolekce vždy, když kolekce se zápis do více vláken současně.</span><span class="sxs-lookup"><span data-stu-id="5812e-105">When you write new code, use the concurrent collection classes whenever the collection will be writing to multiple threads concurrently.</span></span> <span data-ttu-id="5812e-106">Pokud jsou pouze čtení ze sdílené kolekce, pak můžete použít třídy v <xref:System.Collections.Generic?displayProperty=nameWithType> oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="5812e-106">If you are only reading from a shared collection, then you can use the classes in the <xref:System.Collections.Generic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="5812e-107">Doporučujeme, abyste provedli třídy kolekcí verze 1.0, pokud není vyžadováno cílit na rozhraní .NET Framework 1.1 nebo starší modul runtime.</span><span class="sxs-lookup"><span data-stu-id="5812e-107">We recommend that you do not use 1.0 collection classes unless you are required to target the .NET Framework 1.1 or earlier runtime.</span></span>  
  
## <a name="thread-synchronization-in-the-net-framework-10-and-20-collections"></a><span data-ttu-id="5812e-108">Synchronizace vláken v rozhraní .NET Framework 1.0 a 2.0 kolekce</span><span class="sxs-lookup"><span data-stu-id="5812e-108">Thread Synchronization in the .NET Framework 1.0 and 2.0 Collections</span></span>  
 <span data-ttu-id="5812e-109">Kolekce zavedené v rozhraní .NET Framework 1.0 se nacházejí v <xref:System.Collections?displayProperty=nameWithType> oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="5812e-109">The collections introduced in the .NET Framework 1.0 are found in the <xref:System.Collections?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="5812e-110">Tyto kolekce, které zahrnují běžně používané <xref:System.Collections.ArrayList> a <xref:System.Collections.Hashtable>, poskytovat některé vláken prostřednictvím `Synchronized` vlastnosti, která vrátí obálku kolem kolekce bezpečné pro přístup z více vláken.</span><span class="sxs-lookup"><span data-stu-id="5812e-110">These collections, which include the commonly used <xref:System.Collections.ArrayList> and <xref:System.Collections.Hashtable>, provide some thread-safety through the `Synchronized` property, which returns a thread-safe wrapper around the collection.</span></span> <span data-ttu-id="5812e-111">Obálku funguje tak, že na každé operace přidat nebo odebrat zamykání celou kolekci.</span><span class="sxs-lookup"><span data-stu-id="5812e-111">The wrapper works by locking the entire collection on every add or remove operation.</span></span> <span data-ttu-id="5812e-112">Proto musí každý podproces, který se pokouší získat přístup ke kolekci čekat následně provést jeden zámek.</span><span class="sxs-lookup"><span data-stu-id="5812e-112">Therefore, each thread that is attempting to access the collection must wait for its turn to take the one lock.</span></span> <span data-ttu-id="5812e-113">Toto není škálovatelné a může způsobit významné snížení výkonu u rozsáhlých kolekcí.</span><span class="sxs-lookup"><span data-stu-id="5812e-113">This is not scalable and can cause significant performance degradation for large collections.</span></span> <span data-ttu-id="5812e-114">Návrh navíc není úplně chráněn před časování.</span><span class="sxs-lookup"><span data-stu-id="5812e-114">Also, the design is not completely protected from race conditions.</span></span> <span data-ttu-id="5812e-115">Další informace najdete v tématu [synchronizace v obecné kolekce](http://go.microsoft.com/fwlink/?LinkID=161130) na webu MSDN.</span><span class="sxs-lookup"><span data-stu-id="5812e-115">For more information, see [Synchronization in Generic Collections](http://go.microsoft.com/fwlink/?LinkID=161130) on the MSDN Web site.</span></span>  
  
 <span data-ttu-id="5812e-116">Třídy kolekcí zavedené v rozhraní .NET Framework 2.0, které se nacházejí v <xref:System.Collections.Generic?displayProperty=nameWithType> oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="5812e-116">The collection classes introduced in the .NET Framework 2.0 are found in the <xref:System.Collections.Generic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="5812e-117">Mezi ně patří <xref:System.Collections.Generic.List%601>, <xref:System.Collections.Generic.Dictionary%602>a tak dále.</span><span class="sxs-lookup"><span data-stu-id="5812e-117">These include <xref:System.Collections.Generic.List%601>, <xref:System.Collections.Generic.Dictionary%602>, and so on.</span></span> <span data-ttu-id="5812e-118">Tyto třídy poskytují lepší typu zabezpečení a výkonu ve srovnání s třídy rozhraní .NET Framework 1.0.</span><span class="sxs-lookup"><span data-stu-id="5812e-118">These classes provide improved type safety and performance compared to the .NET Framework 1.0 classes.</span></span> <span data-ttu-id="5812e-119">Kolekce tříd rozhraní .NET Framework 2.0 však neposkytuje žádnou synchronizaci vláken; Při přidávání nebo odebírání ve více vláknech souběžně položky, musíte zadat uživatelský kód veškeré synchronizaci.</span><span class="sxs-lookup"><span data-stu-id="5812e-119">However, the .NET Framework 2.0 collection classes do not provide any thread synchronization; user code must provide all synchronization when items are added or removed on multiple threads concurrently.</span></span>  
  
 <span data-ttu-id="5812e-120">Doporučujeme třídy souběžných kolekcí v [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] protože poskytují nejenom bezpečnost typů kolekce tříd rozhraní .NET Framework 2.0, ale také efektivnější a podrobnější zabezpečení vlákna, než [!INCLUDE[net_v10_short](../../../../includes/net-v10-short-md.md)] kolekce poskytují.</span><span class="sxs-lookup"><span data-stu-id="5812e-120">We recommend the concurrent collections classes in the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] because they provide not only the type safety of the .NET Framework 2.0 collection classes, but also more efficient and more complete thread safety than the [!INCLUDE[net_v10_short](../../../../includes/net-v10-short-md.md)] collections provide.</span></span>  
  
## <a name="fine-grained-locking-and-lock-free-mechanisms"></a><span data-ttu-id="5812e-121">Jemně odstupňovaných zamykání a uvolnění zámku mechanismy</span><span class="sxs-lookup"><span data-stu-id="5812e-121">Fine-Grained Locking and Lock-Free Mechanisms</span></span>  
 <span data-ttu-id="5812e-122">Některé typy souběžných kolekcí používají mechanismy zjednodušené synchronizace, jako <xref:System.Threading.SpinLock>, <xref:System.Threading.SpinWait>, <xref:System.Threading.SemaphoreSlim>, a <xref:System.Threading.CountdownEvent>, které jsou v nové [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5812e-122">Some of the concurrent collection types use lightweight synchronization mechanisms such as <xref:System.Threading.SpinLock>, <xref:System.Threading.SpinWait>, <xref:System.Threading.SemaphoreSlim>, and <xref:System.Threading.CountdownEvent>, which are new in the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span> <span data-ttu-id="5812e-123">Tyto typy synchronizace obvykle používají *zaneprázdnění* po krátkou dobu před jejich vlákno true stavu čekání.</span><span class="sxs-lookup"><span data-stu-id="5812e-123">These synchronization types typically use *busy spinning* for brief periods before they put the thread into a true Wait state.</span></span> <span data-ttu-id="5812e-124">Když se měl velmi krátké doby čekání, roztočený je mnohem méně výpočetně náročné než čekání, které zahrnuje nákladný přechod jádra.</span><span class="sxs-lookup"><span data-stu-id="5812e-124">When wait times are expected to be very short, spinning is far less computationally expensive than waiting, which involves an expensive kernel transition.</span></span> <span data-ttu-id="5812e-125">Pro třídy kolekce, které používají zaneprázdnění této efektivity znamená, že můžete přidávat a odebírat položky velmi vysokou rychlostí více vláken.</span><span class="sxs-lookup"><span data-stu-id="5812e-125">For collection classes that use spinning, this efficiency means that multiple threads can add and remove items at a very high rate.</span></span> <span data-ttu-id="5812e-126">Další informace o roztočený oproti blokování najdete v tématu [SpinLock](../../../../docs/standard/threading/spinlock.md) a [objektu SpinWait](../../../../docs/standard/threading/spinwait.md).</span><span class="sxs-lookup"><span data-stu-id="5812e-126">For more information about spinning vs. blocking, see [SpinLock](../../../../docs/standard/threading/spinlock.md) and [SpinWait](../../../../docs/standard/threading/spinwait.md).</span></span>  
  
 <span data-ttu-id="5812e-127"><xref:System.Collections.Concurrent.ConcurrentQueue%601> a <xref:System.Collections.Concurrent.ConcurrentStack%601> třídy nepoužívejte zámky vůbec.</span><span class="sxs-lookup"><span data-stu-id="5812e-127">The <xref:System.Collections.Concurrent.ConcurrentQueue%601> and <xref:System.Collections.Concurrent.ConcurrentStack%601> classes do not use locks at all.</span></span> <span data-ttu-id="5812e-128">Místo toho spoléhají na <xref:System.Threading.Interlocked> operace pro dosažení vláken.</span><span class="sxs-lookup"><span data-stu-id="5812e-128">Instead, they rely on <xref:System.Threading.Interlocked> operations to achieve thread-safety.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5812e-129">Protože třídy souběžných kolekcí podporují <xref:System.Collections.ICollection>, poskytují implementace pro <xref:System.Collections.ICollection.IsSynchronized%2A> a <xref:System.Collections.ICollection.SyncRoot%2A> vlastnosti, i když tyto vlastnosti nejsou relevantní.</span><span class="sxs-lookup"><span data-stu-id="5812e-129">Because the concurrent collections classes support <xref:System.Collections.ICollection>, they provide implementations for the <xref:System.Collections.ICollection.IsSynchronized%2A> and <xref:System.Collections.ICollection.SyncRoot%2A> properties, even though these properties are irrelevant.</span></span> <span data-ttu-id="5812e-130">`IsSynchronized`vždy vrátí hodnotu `false` a `SyncRoot` je vždy `null` (`Nothing` v jazyce Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="5812e-130">`IsSynchronized` always returns `false` and `SyncRoot` is always `null` (`Nothing` in Visual Basic).</span></span>  
  
 <span data-ttu-id="5812e-131">Následující tabulka uvádí typy kolekcí v <xref:System.Collections.Concurrent?displayProperty=nameWithType> oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="5812e-131">The following table lists the collection types in the <xref:System.Collections.Concurrent?displayProperty=nameWithType> namespace.</span></span>  
  
|<span data-ttu-id="5812e-132">Typ</span><span class="sxs-lookup"><span data-stu-id="5812e-132">Type</span></span>|<span data-ttu-id="5812e-133">Popis</span><span class="sxs-lookup"><span data-stu-id="5812e-133">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Collections.Concurrent.BlockingCollection%601>|<span data-ttu-id="5812e-134">Poskytuje funkcí ohraničování a blokování pro žádný typ, který implementuje <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>.</span><span class="sxs-lookup"><span data-stu-id="5812e-134">Provides bounding and blocking functionality for any type that implements <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>.</span></span> <span data-ttu-id="5812e-135">Další informace najdete v tématu [BlockingCollection – přehled](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md).</span><span class="sxs-lookup"><span data-stu-id="5812e-135">For more information, see [BlockingCollection Overview](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md).</span></span>|  
|<xref:System.Collections.Concurrent.ConcurrentDictionary%602>|<span data-ttu-id="5812e-136">Implementace bezpečné pro přístup z více vláken slovník páry klíč hodnota.</span><span class="sxs-lookup"><span data-stu-id="5812e-136">Thread-safe implementation of a dictionary of key-value pairs.</span></span>|  
|<xref:System.Collections.Concurrent.ConcurrentQueue%601>|<span data-ttu-id="5812e-137">Implementace bezpečné pro přístup z více vláken fronty FIFO (first in, první ven).</span><span class="sxs-lookup"><span data-stu-id="5812e-137">Thread-safe implementation of a FIFO (first-in, first-out) queue.</span></span>|  
|<xref:System.Collections.Concurrent.ConcurrentStack%601>|<span data-ttu-id="5812e-138">Implementace bezpečné pro přístup z více vláken zásobníku LIFO (last-in první ven).</span><span class="sxs-lookup"><span data-stu-id="5812e-138">Thread-safe implementation of a LIFO (last-in, first-out) stack.</span></span>|  
|<xref:System.Collections.Concurrent.ConcurrentBag%601>|<span data-ttu-id="5812e-139">Implementace bezpečné pro přístup z více vláken neuspořádaný kolekci elementů.</span><span class="sxs-lookup"><span data-stu-id="5812e-139">Thread-safe implementation of an unordered collection of elements.</span></span>|  
|<xref:System.Collections.Concurrent.IProducerConsumerCollection%601>|<span data-ttu-id="5812e-140">Rozhraní, které musí typ implementovat, který se má použít v `BlockingCollection`.</span><span class="sxs-lookup"><span data-stu-id="5812e-140">The interface that a type must implement to be used in a `BlockingCollection`.</span></span>|  
  
## <a name="related-topics"></a><span data-ttu-id="5812e-141">Související témata</span><span class="sxs-lookup"><span data-stu-id="5812e-141">Related Topics</span></span>  
  
|<span data-ttu-id="5812e-142">Název</span><span class="sxs-lookup"><span data-stu-id="5812e-142">Title</span></span>|<span data-ttu-id="5812e-143">Popis</span><span class="sxs-lookup"><span data-stu-id="5812e-143">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="5812e-144">BlockingCollection – přehled</span><span class="sxs-lookup"><span data-stu-id="5812e-144">BlockingCollection Overview</span></span>](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md)|<span data-ttu-id="5812e-145">Popisuje funkce poskytované službou <xref:System.Collections.Concurrent.BlockingCollection%601> typu.</span><span class="sxs-lookup"><span data-stu-id="5812e-145">Describes the functionality provided by the <xref:System.Collections.Concurrent.BlockingCollection%601> type.</span></span>|  
|[<span data-ttu-id="5812e-146">Postupy: Přidání a odebrání položek v ConcurrentDictionary</span><span class="sxs-lookup"><span data-stu-id="5812e-146">How to: Add and Remove Items from a ConcurrentDictionary</span></span>](../../../../docs/standard/collections/thread-safe/how-to-add-and-remove-items.md)|<span data-ttu-id="5812e-147">Popisuje, jak přidávat a odebírat elementů od<xref:System.Collections.Concurrent.ConcurrentDictionary%602></span><span class="sxs-lookup"><span data-stu-id="5812e-147">Describes how to add and remove elements from a <xref:System.Collections.Concurrent.ConcurrentDictionary%602></span></span>|  
|[<span data-ttu-id="5812e-148">Postupy: Přidání a odebírání jednotlivých položek v BlockingCollection</span><span class="sxs-lookup"><span data-stu-id="5812e-148">How to: Add and Take Items Individually from a BlockingCollection</span></span>](../../../../docs/standard/collections/thread-safe/how-to-add-and-take-items.md)|<span data-ttu-id="5812e-149">Popisuje, jak přidat a načítat položky z blokující kolekce bez použití enumerátor jen pro čtení.</span><span class="sxs-lookup"><span data-stu-id="5812e-149">Describes how to add and retrieve items from a blocking collection without using the read-only enumerator.</span></span>|  
|[<span data-ttu-id="5812e-150">Postupy: přidání funkcí ohraničování a blokování do kolekce</span><span class="sxs-lookup"><span data-stu-id="5812e-150">How to: Add Bounding and Blocking Functionality to a Collection</span></span>](../../../../docs/standard/collections/thread-safe/how-to-add-bounding-and-blocking.md)|<span data-ttu-id="5812e-151">Popisuje, jak chcete použít jako základní mechanismus úložiště pro všechny třídy kolekce <xref:System.Collections.Concurrent.IProducerConsumerCollection%601> kolekce.</span><span class="sxs-lookup"><span data-stu-id="5812e-151">Describes how to use any collection class as the underlying storage mechanism for an <xref:System.Collections.Concurrent.IProducerConsumerCollection%601> collection.</span></span>|  
|[<span data-ttu-id="5812e-152">Postupy: použití příkazu ForEach k odebrání položek v kolekci BlockingCollection</span><span class="sxs-lookup"><span data-stu-id="5812e-152">How to: Use ForEach to Remove Items in a BlockingCollection</span></span>](../../../../docs/standard/collections/thread-safe/how-to-use-foreach-to-remove.md)|<span data-ttu-id="5812e-153">Popisuje způsob použití `foreach`, (`For Each` v jazyce Visual Basic) Chcete-li odebrat všechny položky v kolekci blokování.</span><span class="sxs-lookup"><span data-stu-id="5812e-153">Describes how to use `foreach`, (`For Each` in Visual Basic) to remove all items in a blocking collection.</span></span>|  
|[<span data-ttu-id="5812e-154">Postupy: použití polí blokujících kolekcí v datovém kanálu</span><span class="sxs-lookup"><span data-stu-id="5812e-154">How to: Use Arrays of Blocking Collections in a Pipeline</span></span>](../../../../docs/standard/collections/thread-safe/how-to-use-arrays-of-blockingcollections.md)|<span data-ttu-id="5812e-155">Popisuje, jak používat více blokující kolekce ve stejnou dobu implementace kanálu.</span><span class="sxs-lookup"><span data-stu-id="5812e-155">Describes how to use multiple blocking collections at the same time to implement a pipeline.</span></span>|  
|[<span data-ttu-id="5812e-156">Postupy: vytvoření fondu objektů pomocí ConcurrentBag</span><span class="sxs-lookup"><span data-stu-id="5812e-156">How to: Create an Object Pool by Using a ConcurrentBag</span></span>](../../../../docs/standard/collections/thread-safe/how-to-create-an-object-pool.md)|<span data-ttu-id="5812e-157">Zobrazuje způsob používání souběžného kontejneru za účelem zlepšení výkonu v situacích, kdy je možné namísto neustálého vytváření nových objektů opětovně používat stávající objekty.</span><span class="sxs-lookup"><span data-stu-id="5812e-157">Shows how to use a concurrent bag to improve performance in scenarios where you can reuse objects instead of continually creating new ones.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="5812e-158">Odkaz</span><span class="sxs-lookup"><span data-stu-id="5812e-158">Reference</span></span>  
 <xref:System.Collections.Concurrent?displayProperty=nameWithType>
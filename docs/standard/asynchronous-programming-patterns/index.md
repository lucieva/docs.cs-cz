---
title: "Vzory asynchronního programování"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- asynchronous design patterns, .NET Framework
- .NET Framework, asynchronous design patterns
ms.assetid: 4ece5c0b-f8fe-4114-9862-ac02cfe5a5d7
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a527824ba11928d59bc700f253c5a4d77056abf0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="asynchronous-programming-patterns"></a><span data-ttu-id="5d8d2-102">Vzory asynchronního programování</span><span class="sxs-lookup"><span data-stu-id="5d8d2-102">Asynchronous Programming Patterns</span></span>

<span data-ttu-id="5d8d2-103">Rozhraní .NET Framework poskytuje tři vzory pro provádění asynchronní operace:</span><span class="sxs-lookup"><span data-stu-id="5d8d2-103">The .NET Framework provides three patterns for performing asynchronous operations:</span></span>  
  
- <span data-ttu-id="5d8d2-104">Asynchronní vzor programovací Model (APM) (také nazývané <xref:System.IAsyncResult> vzor), které vyžadují asynchronních operací `Begin` a `End` metody (například `BeginWrite` a `EndWrite` pro operace asynchronní zápis).</span><span class="sxs-lookup"><span data-stu-id="5d8d2-104">Asynchronous Programming Model (APM) pattern (also called the <xref:System.IAsyncResult> pattern), where asynchronous operations require `Begin` and `End` methods (for example, `BeginWrite` and `EndWrite` for asynchronous write operations).</span></span> <span data-ttu-id="5d8d2-105">Tento vzor již není doporučeno pro nový vývoj.</span><span class="sxs-lookup"><span data-stu-id="5d8d2-105">This pattern is no longer recommended for new development.</span></span> <span data-ttu-id="5d8d2-106">Další informace najdete v tématu [asynchronní programování modelu (APM)](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md).</span><span class="sxs-lookup"><span data-stu-id="5d8d2-106">For more information, see [Asynchronous Programming Model (APM)](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md).</span></span>  
  
- <span data-ttu-id="5d8d2-107">Na základě událostí asynchronní vzor (EAP), který vyžaduje metodu, která má `Async` přípona a také vyžaduje jeden nebo více událostí, typy delegáta obslužných rutin událostí, a `EventArg`-odvozených typů.</span><span class="sxs-lookup"><span data-stu-id="5d8d2-107">Event-based Asynchronous Pattern (EAP), which requires a method that has the `Async` suffix, and also requires one or more events, event handler delegate types, and `EventArg`-derived types.</span></span> <span data-ttu-id="5d8d2-108">EAP byla zavedena v rozhraní .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="5d8d2-108">EAP was introduced in the .NET Framework 2.0.</span></span> <span data-ttu-id="5d8d2-109">Doporučuje se už pro nový vývoj.</span><span class="sxs-lookup"><span data-stu-id="5d8d2-109">It is no longer recommended for new development.</span></span> <span data-ttu-id="5d8d2-110">Další informace najdete v tématu [na základě událostí asynchronní vzor (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md).</span><span class="sxs-lookup"><span data-stu-id="5d8d2-110">For more information, see [Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md).</span></span>  
  
- <span data-ttu-id="5d8d2-111">Založený na úlohách asynchronní vzor (TAP), který používá jedinou metodu k reprezentaci na zahájení a ukončení asynchronní operace.</span><span class="sxs-lookup"><span data-stu-id="5d8d2-111">Task-based Asynchronous Pattern (TAP), which uses a single method to represent the initiation and completion of an asynchronous operation.</span></span> <span data-ttu-id="5d8d2-112">Klepněte na byla zavedena v rozhraní .NET Framework 4 a je doporučeným přístupem k asynchronní programování v rozhraní .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5d8d2-112">TAP was introduced in the .NET Framework 4 and is the recommended approach to asynchronous programming in the .NET Framework.</span></span> <span data-ttu-id="5d8d2-113">[Asynchronní](~/docs/csharp/language-reference/keywords/async.md) a [await](~/docs/csharp/language-reference/keywords/await.md) klíčová slova v jazyce C# a [asynchronní](~/docs/visual-basic/language-reference/modifiers/async.md) a [Await](~/docs/visual-basic/language-reference/operators/await-operator.md) jazyková podpora pro klepněte na přidat operátory v jazyce Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="5d8d2-113">The [async](~/docs/csharp/language-reference/keywords/async.md) and [await](~/docs/csharp/language-reference/keywords/await.md) keywords in C# and the [Async](~/docs/visual-basic/language-reference/modifiers/async.md) and [Await](~/docs/visual-basic/language-reference/operators/await-operator.md) operators in Visual Basic Language add language support for TAP.</span></span> <span data-ttu-id="5d8d2-114">Další informace najdete v tématu [založený na úlohách asynchronní vzor (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md).</span><span class="sxs-lookup"><span data-stu-id="5d8d2-114">For more information, see [Task-based Asynchronous Pattern (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md).</span></span>  
  
## <a name="comparing-patterns"></a><span data-ttu-id="5d8d2-115">Porovnávání vzorů</span><span class="sxs-lookup"><span data-stu-id="5d8d2-115">Comparing Patterns</span></span>  

<span data-ttu-id="5d8d2-116">Rychlé porovnání jak jsou tři vzory modelu asynchronních operací, vezměte v úvahu `Read` metoda, která načte zadaného množství dat do zadané začínající na zadaný posun vyrovnávací paměti:</span><span class="sxs-lookup"><span data-stu-id="5d8d2-116">For a quick comparison of how the three patterns model asynchronous operations, consider a `Read` method that reads a specified amount of data into a provided buffer starting at a specified offset:</span></span>  
  
```csharp  
public class MyClass  
{  
    public int Read(byte [] buffer, int offset, int count);  
}  
```  
  
<span data-ttu-id="5d8d2-117">APM protějšku této metody by vystavit `BeginRead` a `EndRead` metody:</span><span class="sxs-lookup"><span data-stu-id="5d8d2-117">The APM counterpart of this method would expose the `BeginRead` and `EndRead` methods:</span></span>  
  
```csharp  
public class MyClass  
{  
    public IAsyncResult BeginRead(  
        byte [] buffer, int offset, int count,   
        AsyncCallback callback, object state);  
    public int EndRead(IAsyncResult asyncResult);  
}  
```  
  
<span data-ttu-id="5d8d2-118">EAP protějšku by vystavit následující sadu typy a členy:</span><span class="sxs-lookup"><span data-stu-id="5d8d2-118">The EAP counterpart would expose the following set of types and members:</span></span>  
  
```csharp  
public class MyClass  
{  
    public void ReadAsync(byte [] buffer, int offset, int count);  
    public event ReadCompletedEventHandler ReadCompleted;  
}  
```  
  
<span data-ttu-id="5d8d2-119">Klepněte na protějšku by vystavit následující jedním `ReadAsync` metoda:</span><span class="sxs-lookup"><span data-stu-id="5d8d2-119">The TAP counterpart would expose the following single `ReadAsync` method:</span></span>  
  
```csharp  
public class MyClass  
{  
    public Task<int> ReadAsync(byte [] buffer, int offset, int count);  
}  
```  
  
<span data-ttu-id="5d8d2-120">Komplexní diskuzi o klepněte na APM a EAP najdete v části odkazů uvedených v následující části.</span><span class="sxs-lookup"><span data-stu-id="5d8d2-120">For a comprehensive discussion of TAP, APM, and EAP, see the links provided in the next section.</span></span>  
  
## <a name="related-topics"></a><span data-ttu-id="5d8d2-121">Související témata</span><span class="sxs-lookup"><span data-stu-id="5d8d2-121">Related topics</span></span>

| <span data-ttu-id="5d8d2-122">Název</span><span class="sxs-lookup"><span data-stu-id="5d8d2-122">Title</span></span> | <span data-ttu-id="5d8d2-123">Popis</span><span class="sxs-lookup"><span data-stu-id="5d8d2-123">Description</span></span> |
| ----- | ----------- |
| [<span data-ttu-id="5d8d2-124">Model asynchronního programování (APM)</span><span class="sxs-lookup"><span data-stu-id="5d8d2-124">Asynchronous Programming Model (APM)</span></span>](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md) | <span data-ttu-id="5d8d2-125">Popisuje starší model, který používá <xref:System.IAsyncResult> rozhraní zajistit asynchronní chování.</span><span class="sxs-lookup"><span data-stu-id="5d8d2-125">Describes the legacy model that uses the <xref:System.IAsyncResult> interface to provide asynchronous behavior.</span></span> <span data-ttu-id="5d8d2-126">Tento model již není doporučeno pro nový vývoj.</span><span class="sxs-lookup"><span data-stu-id="5d8d2-126">This model is no longer recommended for new development.</span></span> |
| [<span data-ttu-id="5d8d2-127">Asynchronní vzor založený na událostech (EAP)</span><span class="sxs-lookup"><span data-stu-id="5d8d2-127">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) | <span data-ttu-id="5d8d2-128">Popisuje starší verze modelu pro zajištění asynchronní chování na základě událostí.</span><span class="sxs-lookup"><span data-stu-id="5d8d2-128">Describes the event-based legacy model for providing asynchronous behavior.</span></span> <span data-ttu-id="5d8d2-129">Tento model již není doporučeno pro nový vývoj.</span><span class="sxs-lookup"><span data-stu-id="5d8d2-129">This model is no longer recommended for new development.</span></span> |
| [<span data-ttu-id="5d8d2-130">Asynchronní vzor založený na úlohách (TAP)</span><span class="sxs-lookup"><span data-stu-id="5d8d2-130">Task-based Asynchronous Pattern (TAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) | <span data-ttu-id="5d8d2-131">Popisuje nové asynchronní vzor na základě <xref:System.Threading.Tasks> oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="5d8d2-131">Describes the new asynchronous pattern based on the <xref:System.Threading.Tasks> namespace.</span></span> <span data-ttu-id="5d8d2-132">Tento model je doporučeným přístupem k asynchronní programování v rozhraní .NET Framework 4 a novější verze.</span><span class="sxs-lookup"><span data-stu-id="5d8d2-132">This model is the recommended approach to asynchronous programming in the .NET Framework 4 and later versions.</span></span> |

## <a name="see-also"></a><span data-ttu-id="5d8d2-133">Viz také</span><span class="sxs-lookup"><span data-stu-id="5d8d2-133">See also</span></span>

<span data-ttu-id="5d8d2-134">[Asynchronní programování v jazyce C#](~/docs/csharp/async.md) </span><span class="sxs-lookup"><span data-stu-id="5d8d2-134">[Asynchronous programming in C#](~/docs/csharp/async.md) </span></span>  
<span data-ttu-id="5d8d2-135">[Asynchronní programování v F #](~/docs/fsharp/tutorials/asynchronous-and-concurrent-programming/async.md) </span><span class="sxs-lookup"><span data-stu-id="5d8d2-135">[Async Programming in F#](~/docs/fsharp/tutorials/asynchronous-and-concurrent-programming/async.md) </span></span>  
[<span data-ttu-id="5d8d2-136">Asynchronní programování pomocí modifikátoru Async a operátoru Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5d8d2-136">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](~/docs/visual-basic/programming-guide/concepts/async/index.md)
---
title: "Deklarace a vyvolávání událostí (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declarations [Visual Basic], events
- events [Visual Basic], walkthroughs
- declaring events [Visual Basic], walkthroughs
- events [Visual Basic], declaring
- events [Visual Basic], raising
- raising events [Visual Basic], walkthroughs
ms.assetid: 8ffb3be8-097d-4d3c-b71e-04555ebda2a2
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0bf75cfba5102be5d837af385e2d3578f78a03c0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-declaring-and-raising-events-visual-basic"></a><span data-ttu-id="07e6c-102">Návod: Deklarace a vyvolávání událostí (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="07e6c-102">Walkthrough: Declaring and Raising Events (Visual Basic)</span></span>
<span data-ttu-id="07e6c-103">Tento návod ukazuje, jak deklarace a vyvolávání událostí třídy s názvem `Widget`.</span><span class="sxs-lookup"><span data-stu-id="07e6c-103">This walkthrough demonstrates how to declare and raise events for a class named `Widget`.</span></span> <span data-ttu-id="07e6c-104">Po dokončení kroků, můžete chtít přečíst téma doprovodné [návod: zpracování událostí](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md), který ukazuje způsob použití události z `Widget` objekty, které chcete poskytnout informace o stavu v aplikaci.</span><span class="sxs-lookup"><span data-stu-id="07e6c-104">After you complete the steps, you might want to read the companion topic, [Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md), which shows how to use events from `Widget` objects to provide status information in an application.</span></span>  
  
## <a name="the-widget-class"></a><span data-ttu-id="07e6c-105">Pomůcka – třída</span><span class="sxs-lookup"><span data-stu-id="07e6c-105">The Widget Class</span></span>  
 <span data-ttu-id="07e6c-106">Předpokládejme, ke které máte nyní `Widget` třídy.</span><span class="sxs-lookup"><span data-stu-id="07e6c-106">Assume for the moment that you have a `Widget` class.</span></span> <span data-ttu-id="07e6c-107">Vaše `Widget` třída obsahuje metody, která může trvat dlouhou dobu spuštění a má vaše aplikace moci uvést do určitého druhu dokončení indikátoru.</span><span class="sxs-lookup"><span data-stu-id="07e6c-107">Your `Widget` class has a method that can take a long time to execute, and you want your application to be able to put up some kind of completion indicator.</span></span>  
  
 <span data-ttu-id="07e6c-108">Samozřejmě můžete dokonce vytvářet `Widget` objekt zobrazit procento dokončení dialogové okno, ale pak můžete by zablokuje se toto okno zobrazené v každém projektu, ve které jste použili `Widget` třídy.</span><span class="sxs-lookup"><span data-stu-id="07e6c-108">Of course, you could make the `Widget` object show a percent-complete dialog box, but then you would be stuck with that dialog box in every project in which you used the `Widget` class.</span></span> <span data-ttu-id="07e6c-109">Dobrý Princip návrhu objektu je umožnit aplikaci, která používá popisovač objektu uživatelské rozhraní – Pokud celý účelem objektu je spravovat pole formuláře nebo dialogového okna.</span><span class="sxs-lookup"><span data-stu-id="07e6c-109">A good principle of object design is to let the application that uses an object handle the user interface—unless the whole purpose of the object is to manage a form or dialog box.</span></span>  
  
 <span data-ttu-id="07e6c-110">Účelem `Widget` je provést další úlohy, proto je lepší pro přidání `PercentDone` událostí a umožňují procedury, která volá `Widget`je metody zpracování, že stav události a zobrazení aktualizací.</span><span class="sxs-lookup"><span data-stu-id="07e6c-110">The purpose of `Widget` is to perform other tasks, so it is better to add a `PercentDone` event and let the procedure that calls `Widget`'s methods handle that event and display status updates.</span></span> <span data-ttu-id="07e6c-111">`PercentDone` Událost můžete také poskytují mechanismus pro zrušení úlohy.</span><span class="sxs-lookup"><span data-stu-id="07e6c-111">The `PercentDone` event can also provide a mechanism for canceling the task.</span></span>  
  
#### <a name="to-build-the-code-example-for-this-topic"></a><span data-ttu-id="07e6c-112">K vytvoření příklad kódu pro toto téma</span><span class="sxs-lookup"><span data-stu-id="07e6c-112">To build the code example for this topic</span></span>  
  
1.  <span data-ttu-id="07e6c-113">Otevřete nový [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] aplikace Windows projektu a vytvořte formulář s názvem `Form1`.</span><span class="sxs-lookup"><span data-stu-id="07e6c-113">Open a new [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Windows Application project and create a form named `Form1`.</span></span>  
  
2.  <span data-ttu-id="07e6c-114">Přidat dvě tlačítka a štítek pro `Form1`.</span><span class="sxs-lookup"><span data-stu-id="07e6c-114">Add two buttons and a label to `Form1`.</span></span>  
  
3.  <span data-ttu-id="07e6c-115">Název objekty, jak je znázorněno v následující tabulce.</span><span class="sxs-lookup"><span data-stu-id="07e6c-115">Name the objects as shown in the following table.</span></span>  
  
    |<span data-ttu-id="07e6c-116">Objekt</span><span class="sxs-lookup"><span data-stu-id="07e6c-116">Object</span></span>|<span data-ttu-id="07e6c-117">Vlastnost</span><span class="sxs-lookup"><span data-stu-id="07e6c-117">Property</span></span>|<span data-ttu-id="07e6c-118">Nastavení</span><span class="sxs-lookup"><span data-stu-id="07e6c-118">Setting</span></span>|  
    |------------|--------------|-------------|  
    |`Button1`|`Text`|<span data-ttu-id="07e6c-119">Spouštěcí úkol</span><span class="sxs-lookup"><span data-stu-id="07e6c-119">Start Task</span></span>|  
    |`Button2`|`Text`|<span data-ttu-id="07e6c-120">Zrušit</span><span class="sxs-lookup"><span data-stu-id="07e6c-120">Cancel</span></span>|  
    |`Label`|<span data-ttu-id="07e6c-121">`(Name)`, `Text`</span><span class="sxs-lookup"><span data-stu-id="07e6c-121">`(Name)`, `Text`</span></span>|<span data-ttu-id="07e6c-122">lblPercentDone, 0</span><span class="sxs-lookup"><span data-stu-id="07e6c-122">lblPercentDone, 0</span></span>|  
  
4.  <span data-ttu-id="07e6c-123">Na **projektu** nabídce zvolte **přidat třídu** přidat třídu s názvem `Widget.vb` do projektu.</span><span class="sxs-lookup"><span data-stu-id="07e6c-123">On the **Project** menu, choose **Add Class** to add a class named `Widget.vb` to the project.</span></span>  
  
#### <a name="to-declare-an-event-for-the-widget-class"></a><span data-ttu-id="07e6c-124">Deklarovat událost pro pomůcky – třída</span><span class="sxs-lookup"><span data-stu-id="07e6c-124">To declare an event for the Widget class</span></span>  
  
-   <span data-ttu-id="07e6c-125">Použití `Event` – klíčové slovo deklarovat událost v `Widget` třídy.</span><span class="sxs-lookup"><span data-stu-id="07e6c-125">Use the `Event` keyword to declare an event in the `Widget` class.</span></span> <span data-ttu-id="07e6c-126">Všimněte si, že událost může mít `ByVal` a `ByRef` argumenty, jako `Widget`na `PercentDone` ukazuje událostí:</span><span class="sxs-lookup"><span data-stu-id="07e6c-126">Note that an event can have `ByVal` and `ByRef` arguments, as `Widget`'s `PercentDone` event demonstrates:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#1](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_1.vb)]  
  
 <span data-ttu-id="07e6c-127">Při volání objektu obdrží `PercentDone` událostí, `Percent` argument obsahuje procento dokončení úkolu.</span><span class="sxs-lookup"><span data-stu-id="07e6c-127">When the calling object receives a `PercentDone` event, the `Percent` argument contains the percentage of the task that is complete.</span></span> <span data-ttu-id="07e6c-128">`Cancel` Argument může být nastaven na `True` zrušit metodu, která se vyvolá událost.</span><span class="sxs-lookup"><span data-stu-id="07e6c-128">The `Cancel` argument can be set to `True` to cancel the method that raised the event.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="07e6c-129">Argumenty událostí můžou deklarovat, stejným způsobem jako argumenty procedur, s následujícími výjimkami: události nemůže mít `Optional` nebo `ParamArray` argumentů a události nemají návratové hodnoty.</span><span class="sxs-lookup"><span data-stu-id="07e6c-129">You can declare event arguments just as you do arguments of procedures, with the following exceptions: Events cannot have `Optional` or `ParamArray` arguments, and events do not have return values.</span></span>  
  
 <span data-ttu-id="07e6c-130">`PercentDone` Událost vyvolána pomocí `LongTask` metodu `Widget` třídy.</span><span class="sxs-lookup"><span data-stu-id="07e6c-130">The `PercentDone` event is raised by the `LongTask` method of the `Widget` class.</span></span> <span data-ttu-id="07e6c-131">`LongTask`přebírá dva argumenty: doba metodu předstírá, že by práci a minimální časový interval před `LongTask` pozastaví zvýšit `PercentDone` událostí.</span><span class="sxs-lookup"><span data-stu-id="07e6c-131">`LongTask` takes two arguments: the length of time the method pretends to be doing work, and the minimum time interval before `LongTask` pauses to raise the `PercentDone` event.</span></span>  
  
#### <a name="to-raise-the-percentdone-event"></a><span data-ttu-id="07e6c-132">Pro vyvolání události PercentDone</span><span class="sxs-lookup"><span data-stu-id="07e6c-132">To raise the PercentDone event</span></span>  
  
1.  <span data-ttu-id="07e6c-133">Zjednodušení přístupu k `Timer` vlastnost použitou touto třídou, přidejte `Imports` příkaz do horní části deklarace modulů tříd výše `Class Widget` příkaz.</span><span class="sxs-lookup"><span data-stu-id="07e6c-133">To simplify access to the `Timer` property used by this class, add an `Imports` statement to the top of the declarations section of your class module, above the `Class Widget` statement.</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#2](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_2.vb)]  
  
2.  <span data-ttu-id="07e6c-134">Přidejte následující kód, který `Widget` třídy:</span><span class="sxs-lookup"><span data-stu-id="07e6c-134">Add the following code to the `Widget` class:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#3](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_3.vb)]  
  
 <span data-ttu-id="07e6c-135">Pokud aplikace zavolá `LongTask` metody `Widget` třídy vyvolá `PercentDone` událostí každých `MinimumInterval` sekund.</span><span class="sxs-lookup"><span data-stu-id="07e6c-135">When your application calls the `LongTask` method, the `Widget` class raises the `PercentDone` event every `MinimumInterval` seconds.</span></span> <span data-ttu-id="07e6c-136">Po návratu událost `LongTask` kontroluje, pokud `Cancel` argument byl nastaven na hodnotu `True`.</span><span class="sxs-lookup"><span data-stu-id="07e6c-136">When the event returns, `LongTask` checks to see if the `Cancel` argument was set to `True`.</span></span>  
  
 <span data-ttu-id="07e6c-137">Tady jsou nezbytné několik omezení.</span><span class="sxs-lookup"><span data-stu-id="07e6c-137">A few disclaimers are necessary here.</span></span> <span data-ttu-id="07e6c-138">Pro jednoduchost `LongTask` postupu se předpokládá můžete předem vědět, jak dlouho bude trvat úlohu.</span><span class="sxs-lookup"><span data-stu-id="07e6c-138">For simplicity, the `LongTask` procedure assumes you know in advance how long the task will take.</span></span> <span data-ttu-id="07e6c-139">Toto je téměř žádné případu.</span><span class="sxs-lookup"><span data-stu-id="07e6c-139">This is almost never the case.</span></span> <span data-ttu-id="07e6c-140">Rozdělení úloh do bloků i velikost může být složité a často nejdůležitějším uživatelům je jednoduše množství času, který uplyne, než získají jako ukazatel toho, že se něco děje.</span><span class="sxs-lookup"><span data-stu-id="07e6c-140">Dividing tasks into chunks of even size can be difficult, and often what matters most to users is simply the amount of time that passes before they get an indication that something is happening.</span></span>  
  
 <span data-ttu-id="07e6c-141">Může mít další vadou nanese v této ukázce.</span><span class="sxs-lookup"><span data-stu-id="07e6c-141">You may have spotted another flaw in this sample.</span></span> <span data-ttu-id="07e6c-142">`Timer` Vlastnost vrátí počet sekund, které uplynuly od půlnoci; proto aplikaci vázne, pokud je spuštěno těsně před půlnoci.</span><span class="sxs-lookup"><span data-stu-id="07e6c-142">The `Timer` property returns the number of seconds that have passed since midnight; therefore, the application gets stuck if it is started just before midnight.</span></span> <span data-ttu-id="07e6c-143">Více pečlivě přístup k měření doby by podmínky hranice například to v úvahu, nebo zabránění jejímu provedení je zcela, pomocí vlastnosti, jako třeba `Now`.</span><span class="sxs-lookup"><span data-stu-id="07e6c-143">A more careful approach to measuring time would take boundary conditions such as this into consideration, or avoid them altogether, using properties such as `Now`.</span></span>  
  
 <span data-ttu-id="07e6c-144">Teď, když `Widget` třídy můžete vyvolávání událostí, můžete přesunout na další návod.</span><span class="sxs-lookup"><span data-stu-id="07e6c-144">Now that the `Widget` class can raise events, you can move to the next walkthrough.</span></span> <span data-ttu-id="07e6c-145">[Návod: Zpracování událostí](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) ukazuje, jak používat `WithEvents` přidružit obslužné rutiny události s `PercentDone` událostí.</span><span class="sxs-lookup"><span data-stu-id="07e6c-145">[Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) demonstrates how to use `WithEvents` to associate an event handler with the `PercentDone` event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07e6c-146">Viz také</span><span class="sxs-lookup"><span data-stu-id="07e6c-146">See Also</span></span>  
 <xref:Microsoft.VisualBasic.DateAndTime.Timer%2A>  
 <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>  
 [<span data-ttu-id="07e6c-147">Návod: Zpracování událostí</span><span class="sxs-lookup"><span data-stu-id="07e6c-147">Walkthrough: Handling Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)  
 [<span data-ttu-id="07e6c-148">Události</span><span class="sxs-lookup"><span data-stu-id="07e6c-148">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
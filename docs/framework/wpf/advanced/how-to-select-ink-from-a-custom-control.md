---
title: "Postupy: Výběr inkoustu pomocí vlastního ovládacího prvku"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], ink selection
- ink [WPF], selecting from custom control
- custom controls [WPF], ink selection
ms.assetid: 5f3a45c6-6d40-4017-9b47-933f134ceba3
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: dd9693209cc35ecd3c0473133b7c21639a239ff5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-select-ink-from-a-custom-control"></a><span data-ttu-id="ab2b0-102">Postupy: Výběr inkoustu pomocí vlastního ovládacího prvku</span><span class="sxs-lookup"><span data-stu-id="ab2b0-102">How to: Select Ink from a Custom Control</span></span>
<span data-ttu-id="ab2b0-103">Přidáním <xref:System.Windows.Ink.IncrementalLassoHitTester> do vlastního ovládacího prvku, můžete povolit vlastního ovládacího prvku tak, aby uživatel může vybrat rukopisu s nástrojem laso, podobně jako <xref:System.Windows.Controls.InkCanvas> vybere rukopisu s nepravidelné oblasti.</span><span class="sxs-lookup"><span data-stu-id="ab2b0-103">By adding an <xref:System.Windows.Ink.IncrementalLassoHitTester> to your custom control, you can enable your control so that a user can select ink with a lasso tool, similar to the way the <xref:System.Windows.Controls.InkCanvas> selects ink with a lasso.</span></span>  
  
 <span data-ttu-id="ab2b0-104">Tento příklad předpokládá, že jste obeznámeni s vytvoření vlastního ovládacího prvku rukopisu povolena.</span><span class="sxs-lookup"><span data-stu-id="ab2b0-104">This example assumes you are familiar with creating an ink-enabled custom control.</span></span>  <span data-ttu-id="ab2b0-105">Pokud chcete vytvořit vlastní ovládací prvek, který přijímá vstup rukopisu, najdete v části [vytváření rukopisu vstupního ovládacího prvku](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md).</span><span class="sxs-lookup"><span data-stu-id="ab2b0-105">To create a custom control that accepts ink input, see [Creating an Ink Input Control](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ab2b0-106">Příklad</span><span class="sxs-lookup"><span data-stu-id="ab2b0-106">Example</span></span>  
 <span data-ttu-id="ab2b0-107">Když uživatel nakreslí nepravidelné oblasti, <xref:System.Windows.Ink.IncrementalLassoHitTester> předpovídá, které tahy bude v rámci hranice laso cesta po dokončení laso uživatele.</span><span class="sxs-lookup"><span data-stu-id="ab2b0-107">When the user draws a lasso, the <xref:System.Windows.Ink.IncrementalLassoHitTester> predicts which strokes will be within the lasso path's boundaries after the user completes the lasso.</span></span>  <span data-ttu-id="ab2b0-108">Tahy, která jsou určena jako v rámci hranice laso cestu můžete představit jako vybraná.</span><span class="sxs-lookup"><span data-stu-id="ab2b0-108">Strokes that are determined to be within the lasso path's boundaries can be thought of as being selected.</span></span>  <span data-ttu-id="ab2b0-109">Vybrané tahy se může stát také nezaškrtnuté.</span><span class="sxs-lookup"><span data-stu-id="ab2b0-109">Selected strokes can also become unselected.</span></span>  <span data-ttu-id="ab2b0-110">Pokud uživatel otočí směr při vykreslování laso, například <xref:System.Windows.Ink.IncrementalLassoHitTester> může zrušit výběr některé tahy.</span><span class="sxs-lookup"><span data-stu-id="ab2b0-110">For example, if the user reverses direction while drawing the lasso, the <xref:System.Windows.Ink.IncrementalLassoHitTester> may unselect some strokes.</span></span>  
  
 <span data-ttu-id="ab2b0-111"><xref:System.Windows.Ink.IncrementalLassoHitTester> Vyvolá <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> událost, která umožňuje vlastního ovládacího prvku reagovat, když uživatel je kreslení laso.</span><span class="sxs-lookup"><span data-stu-id="ab2b0-111">The <xref:System.Windows.Ink.IncrementalLassoHitTester> raises the <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> event, which enables your custom control to respond while the user is drawing the lasso.</span></span>  <span data-ttu-id="ab2b0-112">Můžete například změnit vzhled tahy, se uživatel vybere a zruší výběr nakresleného je.</span><span class="sxs-lookup"><span data-stu-id="ab2b0-112">For example, you can change the appearance of strokes as the user selects and unselects them.</span></span>  
  
## <a name="managing-the-ink-mode"></a><span data-ttu-id="ab2b0-113">Správa režimu rukopisu</span><span class="sxs-lookup"><span data-stu-id="ab2b0-113">Managing the Ink Mode</span></span>  
 <span data-ttu-id="ab2b0-114">Je užitečné pro uživatele Pokud jinak než rukopisu ve vlastní ovládací prvek se zobrazuje laso.</span><span class="sxs-lookup"><span data-stu-id="ab2b0-114">It is helpful to the user if the lasso appears differently than the ink on your control.</span></span> <span data-ttu-id="ab2b0-115">K tomu, vlastní ovládací prvek musí udržovat přehled o zda uživatel je zápis nebo výběr rukopisu.</span><span class="sxs-lookup"><span data-stu-id="ab2b0-115">To accomplish this, your custom control must keep track of whether the user is writing or selecting ink.</span></span> <span data-ttu-id="ab2b0-116">Nejjednodušším způsobem je deklarace výčtů se dvěma hodnotami: jeden k označení, že uživatel je zápis rukopisu a jeden, který označuje, že uživatel je výběr rukopisu.</span><span class="sxs-lookup"><span data-stu-id="ab2b0-116">The easiest way to do this is to declare an enumeration with two values: one to indicate that the user is writing ink and one to indicate that the user is selecting ink.</span></span>  
  
 [!code-csharp[HowToSelectInk#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#2)]
 [!code-vb[HowToSelectInk#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#2)]  
  
 <span data-ttu-id="ab2b0-117">Dál přidejte dva <xref:System.Windows.Ink.DrawingAttributes> pro třídu: jednu použijte, pokud uživatel zapíše rukopisu, jednu pro použijte, pokud uživatel vybere rukopisu.</span><span class="sxs-lookup"><span data-stu-id="ab2b0-117">Next, add two <xref:System.Windows.Ink.DrawingAttributes> to the class: one to use when the user writes ink, one to use when the user selects ink.</span></span>  <span data-ttu-id="ab2b0-118">V konstruktoru, inicializovat <xref:System.Windows.Ink.DrawingAttributes> a připojte oba <xref:System.Windows.Ink.DrawingAttributes.AttributeChanged> události, které mají stejné obslužné rutiny události.</span><span class="sxs-lookup"><span data-stu-id="ab2b0-118">In the constructor, initialize the <xref:System.Windows.Ink.DrawingAttributes> and attach both <xref:System.Windows.Ink.DrawingAttributes.AttributeChanged> events to the same event handler.</span></span> <span data-ttu-id="ab2b0-119">Nastavte <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A> vlastnost <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> k rukopisu <xref:System.Windows.Ink.DrawingAttributes>.</span><span class="sxs-lookup"><span data-stu-id="ab2b0-119">Then set the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A> property of the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> to the ink <xref:System.Windows.Ink.DrawingAttributes>.</span></span>  
  
 [!code-csharp[HowToSelectInk#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#3)]
 [!code-vb[HowToSelectInk#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#3)]  
[!code-csharp[HowToSelectInk#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#4)]
[!code-vb[HowToSelectInk#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#4)]  
  
 <span data-ttu-id="ab2b0-120">Přidáte vlastnost, která zveřejňuje režim výběru.</span><span class="sxs-lookup"><span data-stu-id="ab2b0-120">Add a property that exposes the selection mode.</span></span> <span data-ttu-id="ab2b0-121">Když uživatel změní režim výběru, nastavte <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A> vlastnost <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> na příslušné <xref:System.Windows.Ink.DrawingAttributes> objektu a znovu připojte <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> vlastnost, která má <xref:System.Windows.Controls.InkPresenter>.</span><span class="sxs-lookup"><span data-stu-id="ab2b0-121">When the user changes the selection mode, set the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A> property of the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> to the appropriate <xref:System.Windows.Ink.DrawingAttributes> object and then reattach the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> Property to the <xref:System.Windows.Controls.InkPresenter>.</span></span>  
  
 [!code-csharp[HowToSelectInk#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#5)]
 [!code-vb[HowToSelectInk#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#5)]  
  
 <span data-ttu-id="ab2b0-122">Vystavení <xref:System.Windows.Ink.DrawingAttributes> jako vlastnosti, takže aplikace můžete určit vzhled tahy a výběr tahy.</span><span class="sxs-lookup"><span data-stu-id="ab2b0-122">Expose the <xref:System.Windows.Ink.DrawingAttributes> as properties so applications can determine the appearance of the ink strokes and selection strokes.</span></span>  
  
 [!code-csharp[HowToSelectInk#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#6)]
 [!code-vb[HowToSelectInk#6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#6)]  
  
 <span data-ttu-id="ab2b0-123">Pokud vlastnost <xref:System.Windows.Ink.DrawingAttributes> objektu změny, <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> musí být znovu připojit ke <xref:System.Windows.Controls.InkPresenter>.</span><span class="sxs-lookup"><span data-stu-id="ab2b0-123">When a property of a <xref:System.Windows.Ink.DrawingAttributes> object changes, the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> must be reattached to the <xref:System.Windows.Controls.InkPresenter>.</span></span>  <span data-ttu-id="ab2b0-124">V obslužné rutiny události pro <xref:System.Windows.Ink.DrawingAttributes.AttributeChanged> událostí, připojte <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> k <xref:System.Windows.Controls.InkPresenter>.</span><span class="sxs-lookup"><span data-stu-id="ab2b0-124">In the event handler for the <xref:System.Windows.Ink.DrawingAttributes.AttributeChanged> event, reattach the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> to the <xref:System.Windows.Controls.InkPresenter>.</span></span>  
  
 [!code-csharp[HowToSelectInk#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#7)]
 [!code-vb[HowToSelectInk#7](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#7)]  
  
## <a name="using-the-incrementallassohittester"></a><span data-ttu-id="ab2b0-125">Pomocí IncrementalLassoHitTester</span><span class="sxs-lookup"><span data-stu-id="ab2b0-125">Using the IncrementalLassoHitTester</span></span>  
 <span data-ttu-id="ab2b0-126">Vytvoření a inicializace <xref:System.Windows.Ink.StrokeCollection> obsahující vybrané tahy.</span><span class="sxs-lookup"><span data-stu-id="ab2b0-126">Create and initialize a <xref:System.Windows.Ink.StrokeCollection> that contains the selected strokes.</span></span>  
  
 [!code-csharp[HowToSelectInk#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#8)]
 [!code-vb[HowToSelectInk#8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#8)]  
  
 <span data-ttu-id="ab2b0-127">Když uživatel spustí kreslení tahu, barvou nebo laso, zrušte výběr všechny vybrané tahy.</span><span class="sxs-lookup"><span data-stu-id="ab2b0-127">When the user starts to draw a stroke, either ink or the lasso, unselect any selected strokes.</span></span> <span data-ttu-id="ab2b0-128">Poté, pokud uživatel je kreslení nepravidelné oblasti, vytvořte <xref:System.Windows.Ink.IncrementalLassoHitTester> voláním <xref:System.Windows.Ink.StrokeCollection.GetIncrementalLassoHitTester%2A>, přihlášení k odběru <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> událostí a volání <xref:System.Windows.Ink.IncrementalHitTester.AddPoints%2A>.</span><span class="sxs-lookup"><span data-stu-id="ab2b0-128">Then, if the user is drawing a lasso, create an <xref:System.Windows.Ink.IncrementalLassoHitTester> by calling <xref:System.Windows.Ink.StrokeCollection.GetIncrementalLassoHitTester%2A>, subscribe to the <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> event, and call <xref:System.Windows.Ink.IncrementalHitTester.AddPoints%2A>.</span></span> <span data-ttu-id="ab2b0-129">Tento kód může být samostatné metodě a volat z <xref:System.Windows.UIElement.OnStylusDown%2A> a <xref:System.Windows.UIElement.OnMouseDown%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="ab2b0-129">This code can be a separate method and called from the <xref:System.Windows.UIElement.OnStylusDown%2A> and <xref:System.Windows.UIElement.OnMouseDown%2A> methods.</span></span>  
  
 [!code-csharp[HowToSelectInk#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#9)]
 [!code-vb[HowToSelectInk#9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#9)]  
  
 <span data-ttu-id="ab2b0-130">Přidání bodů pera k <xref:System.Windows.Ink.IncrementalLassoHitTester> při uživatele nevykresluje laso.</span><span class="sxs-lookup"><span data-stu-id="ab2b0-130">Add the stylus points to the <xref:System.Windows.Ink.IncrementalLassoHitTester> while the user draws the lasso.</span></span>  <span data-ttu-id="ab2b0-131">Volejte metodu z <xref:System.Windows.UIElement.OnStylusMove%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, <xref:System.Windows.UIElement.OnMouseMove%2A>, a <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="ab2b0-131">Call the following method from the <xref:System.Windows.UIElement.OnStylusMove%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, <xref:System.Windows.UIElement.OnMouseMove%2A>, and <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A> methods.</span></span>  
  
 [!code-csharp[HowToSelectInk#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#10)]
 [!code-vb[HowToSelectInk#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#10)]  
  
 <span data-ttu-id="ab2b0-132">Zpracování <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged?displayProperty=nameWithType> událostí reagovat, když uživatel vybere a zruší výběr nakresleného tahy.</span><span class="sxs-lookup"><span data-stu-id="ab2b0-132">Handle the <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged?displayProperty=nameWithType> event to respond when the user selects and unselects strokes.</span></span>  <span data-ttu-id="ab2b0-133"><xref:System.Windows.Ink.LassoSelectionChangedEventArgs> Třída má <xref:System.Windows.Ink.LassoSelectionChangedEventArgs.SelectedStrokes%2A> a <xref:System.Windows.Ink.LassoSelectionChangedEventArgs.DeselectedStrokes%2A> vlastnosti, které získají tahy, které byly vybrány a zrušit, v uvedeném pořadí.</span><span class="sxs-lookup"><span data-stu-id="ab2b0-133">The <xref:System.Windows.Ink.LassoSelectionChangedEventArgs> class has the <xref:System.Windows.Ink.LassoSelectionChangedEventArgs.SelectedStrokes%2A> and <xref:System.Windows.Ink.LassoSelectionChangedEventArgs.DeselectedStrokes%2A> properties that get the strokes that were selected and unselected, respectively.</span></span>  
  
 [!code-csharp[HowToSelectInk#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#11)]
 [!code-vb[HowToSelectInk#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#11)]  
  
 <span data-ttu-id="ab2b0-134">Po dokončení kreslení laso uživatele odhlášení odběru <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> událostí a volání <xref:System.Windows.Ink.IncrementalHitTester.EndHitTesting%2A>.</span><span class="sxs-lookup"><span data-stu-id="ab2b0-134">When the user finishes drawing the lasso, unsubscribe from the <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> event and call <xref:System.Windows.Ink.IncrementalHitTester.EndHitTesting%2A>.</span></span>  
  
 [!code-csharp[HowToSelectInk#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#12)]
 [!code-vb[HowToSelectInk#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#12)]  
  
## <a name="putting-it-all-together"></a><span data-ttu-id="ab2b0-135">Všechny připravuje umístění.</span><span class="sxs-lookup"><span data-stu-id="ab2b0-135">Putting it All Together.</span></span>  
 <span data-ttu-id="ab2b0-136">V následujícím příkladu je vlastní ovládací prvek, který umožňuje uživateli vybrat rukopisu s nepravidelné oblasti.</span><span class="sxs-lookup"><span data-stu-id="ab2b0-136">The following example is a custom control that enables a user to select ink with a lasso.</span></span>  
  
 [!code-csharp[HowToSelectInk#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#1)]
 [!code-vb[HowToSelectInk#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="ab2b0-137">Viz také</span><span class="sxs-lookup"><span data-stu-id="ab2b0-137">See Also</span></span>  
 <xref:System.Windows.Ink.IncrementalLassoHitTester>  
 <xref:System.Windows.Ink.StrokeCollection>  
 <xref:System.Windows.Input.StylusPointCollection>  
 [<span data-ttu-id="ab2b0-138">Vytváření rukopisu vstupního ovládacího prvku</span><span class="sxs-lookup"><span data-stu-id="ab2b0-138">Creating an Ink Input Control</span></span>](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md)
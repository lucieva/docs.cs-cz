---
title: "ScrollViewer – přehled"
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
- cpp
helpviewer_keywords:
- controls [WPF], ScrollViewer
- ScrollViewer control [WPF], about ScrollViewer control
ms.assetid: 94a13b94-cfdf-4b12-a1aa-90cb50c6e9b9
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f6398e4a40a1d4a83bc0ae080321112fb6d9fcd6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="scrollviewer-overview"></a><span data-ttu-id="7d188-102">ScrollViewer – přehled</span><span class="sxs-lookup"><span data-stu-id="7d188-102">ScrollViewer Overview</span></span>
<span data-ttu-id="7d188-103">Často je větší než oblasti obrazovky počítače zobrazení obsahu v uživatelském rozhraní.</span><span class="sxs-lookup"><span data-stu-id="7d188-103">Content within a user interface is often larger than a computer screen's display area.</span></span> <span data-ttu-id="7d188-104"><xref:System.Windows.Controls.ScrollViewer> Řízení nabízí pohodlný způsob, jak povolit posouvání obsahu v [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] aplikace.</span><span class="sxs-lookup"><span data-stu-id="7d188-104">The <xref:System.Windows.Controls.ScrollViewer> control provides a convenient way to enable scrolling of content in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] applications.</span></span> <span data-ttu-id="7d188-105">Toto téma představuje <xref:System.Windows.Controls.ScrollViewer> elementu a poskytuje několik příkladů použití.</span><span class="sxs-lookup"><span data-stu-id="7d188-105">This topic introduces the <xref:System.Windows.Controls.ScrollViewer> element and provides several usage examples.</span></span>  
  
<a name="what_is_a_scrollviewer_element"></a>   
## <a name="the-scrollviewer-control"></a><span data-ttu-id="7d188-106">Ovládací prvek ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="7d188-106">The ScrollViewer Control</span></span>  
 <span data-ttu-id="7d188-107">Existují dva předdefinované elementy, které umožňují posouvání v [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplikace: <xref:System.Windows.Controls.Primitives.ScrollBar> a <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="7d188-107">There are two predefined elements that enable scrolling in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications: <xref:System.Windows.Controls.Primitives.ScrollBar> and <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="7d188-108"><xref:System.Windows.Controls.ScrollViewer> Ovládací prvek zapouzdřuje vodorovně a svisle <xref:System.Windows.Controls.Primitives.ScrollBar> elementy a obsahu kontejneru (například <xref:System.Windows.Controls.Panel> element) aby bylo možné zobrazit další prvky viditelné v posouvatelného oblasti.</span><span class="sxs-lookup"><span data-stu-id="7d188-108">The <xref:System.Windows.Controls.ScrollViewer> control encapsulates horizontal and vertical <xref:System.Windows.Controls.Primitives.ScrollBar> elements and a content container (such as a <xref:System.Windows.Controls.Panel> element) in order to display other visible elements in a scrollable area.</span></span> <span data-ttu-id="7d188-109">Chcete-li použít musíte sestavit vlastní objekt <xref:System.Windows.Controls.Primitives.ScrollBar> element pro posouvání obsahu.</span><span class="sxs-lookup"><span data-stu-id="7d188-109">You must build a custom object in order to use the <xref:System.Windows.Controls.Primitives.ScrollBar> element for content scrolling.</span></span> <span data-ttu-id="7d188-110">Můžete však použít <xref:System.Windows.Controls.ScrollViewer> element samostatně, protože je složené řídit, která zapouzdřuje <xref:System.Windows.Controls.Primitives.ScrollBar> funkce.</span><span class="sxs-lookup"><span data-stu-id="7d188-110">However, you can use the <xref:System.Windows.Controls.ScrollViewer> element by itself because it is a composite control that encapsulates <xref:System.Windows.Controls.Primitives.ScrollBar> functionality.</span></span>  
  
 <span data-ttu-id="7d188-111"><xref:System.Windows.Controls.ScrollViewer> Řízení reaguje na příkazy myši a klávesnice a definuje množství metody, které má být posuňte obsah se po předem určenou přírůstcích.</span><span class="sxs-lookup"><span data-stu-id="7d188-111">The <xref:System.Windows.Controls.ScrollViewer> control responds to both mouse and keyboard commands, and defines numerous methods with which to scroll content by predetermined increments.</span></span> <span data-ttu-id="7d188-112">Můžete použít <xref:System.Windows.Controls.ScrollViewer.ScrollChanged> událostí ke zjištění změnu <xref:System.Windows.Controls.ScrollViewer> stavu.</span><span class="sxs-lookup"><span data-stu-id="7d188-112">You can use the <xref:System.Windows.Controls.ScrollViewer.ScrollChanged> event to detect a change in a <xref:System.Windows.Controls.ScrollViewer> state.</span></span>  
  
 <span data-ttu-id="7d188-113">A <xref:System.Windows.Controls.ScrollViewer> může mít pouze jednu podřízenou, obvykle <xref:System.Windows.Controls.Panel> element, který může hostovat <xref:System.Windows.Controls.Panel.Children%2A> kolekci elementů.</span><span class="sxs-lookup"><span data-stu-id="7d188-113">A <xref:System.Windows.Controls.ScrollViewer> can only have one child, typically a <xref:System.Windows.Controls.Panel> element that can host a <xref:System.Windows.Controls.Panel.Children%2A> collection of elements.</span></span> <span data-ttu-id="7d188-114"><xref:System.Windows.Controls.ContentPresenter.Content%2A> Vlastnost definuje jedinou podřízeným <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="7d188-114">The <xref:System.Windows.Controls.ContentPresenter.Content%2A> property defines the sole child of the <xref:System.Windows.Controls.ScrollViewer>.</span></span>  
  
<a name="scrollviewer_physical_vs_logical"></a>   
## <a name="physical-vs-logical-scrolling"></a><span data-ttu-id="7d188-115">Fyzické vs. Logické posouvání</span><span class="sxs-lookup"><span data-stu-id="7d188-115">Physical vs. Logical Scrolling</span></span>  
 <span data-ttu-id="7d188-116">Fyzické posouvání slouží posouvat obsah o předem určený fyzické krok obvykle hodnotu, která je deklarován v pixelech.</span><span class="sxs-lookup"><span data-stu-id="7d188-116">Physical scrolling is used to scroll content by a predetermined physical increment, typically by a value that is declared in pixels.</span></span> <span data-ttu-id="7d188-117">Logické posouvání se používá k přesunutí na další položku v logickém stromu.</span><span class="sxs-lookup"><span data-stu-id="7d188-117">Logical scrolling is used to scroll to the next item in the logical tree.</span></span> <span data-ttu-id="7d188-118">Fyzické posouvání je výchozí chování posuv pro většinu <xref:System.Windows.Controls.Panel> elementy.</span><span class="sxs-lookup"><span data-stu-id="7d188-118">Physical scrolling is the default scroll behavior for most <xref:System.Windows.Controls.Panel> elements.</span></span> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="7d188-119">podporuje oba typy posouvání.</span><span class="sxs-lookup"><span data-stu-id="7d188-119"> supports both types of scrolling.</span></span>  
  
#### <a name="the-iscrollinfo-interface"></a><span data-ttu-id="7d188-120">Rozhraní IScrollInfo</span><span class="sxs-lookup"><span data-stu-id="7d188-120">The IScrollInfo Interface</span></span>  
 <span data-ttu-id="7d188-121"><xref:System.Windows.Controls.Primitives.IScrollInfo> Rozhraní představuje hlavní posouvání oblast v rámci <xref:System.Windows.Controls.ScrollViewer> nebo odvozené ovládací prvek.</span><span class="sxs-lookup"><span data-stu-id="7d188-121">The <xref:System.Windows.Controls.Primitives.IScrollInfo> interface represents the main scrolling region within a <xref:System.Windows.Controls.ScrollViewer> or derived control.</span></span> <span data-ttu-id="7d188-122">Definuje rozhraní posouvání vlastnosti a metody, které může být implementována <xref:System.Windows.Controls.Panel> elementy, které vyžadují posouvání logické jednotky, nikoli fyzické přírůstku.</span><span class="sxs-lookup"><span data-stu-id="7d188-122">The interface defines scrolling properties and methods that can be implemented by <xref:System.Windows.Controls.Panel> elements that require scrolling by logical unit, rather than by a physical increment.</span></span> <span data-ttu-id="7d188-123">Přetypování instanci <xref:System.Windows.Controls.Primitives.IScrollInfo> pro odvozený <xref:System.Windows.Controls.Panel> a pak jeho metodami posouvání poskytuje vhodný způsob, jak přejděte k další logické jednotky v podřízené kolekce, nikoli přírůstek pixelů.</span><span class="sxs-lookup"><span data-stu-id="7d188-123">Casting an instance of <xref:System.Windows.Controls.Primitives.IScrollInfo> to a derived <xref:System.Windows.Controls.Panel> and then using its scrolling methods provides a useful way to scroll to the next logical unit in a child collection, rather than by pixel increment.</span></span> <span data-ttu-id="7d188-124">Ve výchozím nastavení <xref:System.Windows.Controls.ScrollViewer> řízení podporuje posouvání ve fyzické jednotky.</span><span class="sxs-lookup"><span data-stu-id="7d188-124">By default, the <xref:System.Windows.Controls.ScrollViewer> control supports scrolling by physical units.</span></span>  
  
 <span data-ttu-id="7d188-125"><xref:System.Windows.Controls.StackPanel>a <xref:System.Windows.Controls.VirtualizingStackPanel> obě implementovat <xref:System.Windows.Controls.Primitives.IScrollInfo> a nativně podporují logické posouvání.</span><span class="sxs-lookup"><span data-stu-id="7d188-125"><xref:System.Windows.Controls.StackPanel> and <xref:System.Windows.Controls.VirtualizingStackPanel> both implement <xref:System.Windows.Controls.Primitives.IScrollInfo> and natively support logical scrolling.</span></span> <span data-ttu-id="7d188-126">Pro rozložení určuje, že nativně podporu logické posouvání, můžete stále dosáhnout fyzické posouvání nástrojem pro zabalení hostitele <xref:System.Windows.Controls.Panel> element v <xref:System.Windows.Controls.ScrollViewer> a nastavení <xref:System.Windows.Controls.ScrollViewer.CanContentScroll%2A> vlastnost `false`.</span><span class="sxs-lookup"><span data-stu-id="7d188-126">For layout controls that natively support logical scrolling, you can still achieve physical scrolling by wrapping the host <xref:System.Windows.Controls.Panel> element in a <xref:System.Windows.Controls.ScrollViewer> and setting the <xref:System.Windows.Controls.ScrollViewer.CanContentScroll%2A> property to `false`.</span></span>  
  
 <span data-ttu-id="7d188-127">Následující příklad kódu ukazuje, jak převést instanci <xref:System.Windows.Controls.Primitives.IScrollInfo> k <xref:System.Windows.Controls.StackPanel> a použít obsahu posouvání metody (<xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> a <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A>) definované rozhraní.</span><span class="sxs-lookup"><span data-stu-id="7d188-127">The following code example demonstrates how to cast an instance of <xref:System.Windows.Controls.Primitives.IScrollInfo> to a <xref:System.Windows.Controls.StackPanel> and use content scrolling methods (<xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> and <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A>) defined by the interface.</span></span>  
  
 [!code-csharp[IScrollInfoMethods#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml.cs#3)]
 [!code-vb[IScrollInfoMethods#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/IScrollInfoMethods/VisualBasic/Window1.xaml.vb#3)]  
  
<a name="scrollviewer_markup_syntax_and_sample"></a>   
## <a name="defining-and-using-a-scrollviewer-element"></a><span data-ttu-id="7d188-128">Definování a pomocí ScrollViewer elementu.</span><span class="sxs-lookup"><span data-stu-id="7d188-128">Defining and Using a ScrollViewer Element</span></span>  
 <span data-ttu-id="7d188-129">Následující příklad vytvoří <xref:System.Windows.Controls.ScrollViewer> v okně, které obsahuje část textu a obdélníku.</span><span class="sxs-lookup"><span data-stu-id="7d188-129">The following example creates a <xref:System.Windows.Controls.ScrollViewer> in a window that contains some text and a rectangle.</span></span> <span data-ttu-id="7d188-130"><xref:System.Windows.Controls.Primitives.ScrollBar>prvky se zobrazí, jenom když jsou zapotřebí.</span><span class="sxs-lookup"><span data-stu-id="7d188-130"><xref:System.Windows.Controls.Primitives.ScrollBar> elements appear only when they are necessary.</span></span> <span data-ttu-id="7d188-131">Když změníte velikost okna, <xref:System.Windows.Controls.Primitives.ScrollBar> prvky zobrazí a zmizí z důvodu aktualizované hodnoty <xref:System.Windows.Controls.ScrollViewer.ComputedHorizontalScrollBarVisibility%2A> a <xref:System.Windows.Controls.ScrollViewer.ComputedVerticalScrollBarVisibility%2A> vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="7d188-131">When you resize the window, the <xref:System.Windows.Controls.Primitives.ScrollBar> elements appear and disappear, due to updated values of the <xref:System.Windows.Controls.ScrollViewer.ComputedHorizontalScrollBarVisibility%2A> and <xref:System.Windows.Controls.ScrollViewer.ComputedVerticalScrollBarVisibility%2A> properties.</span></span>  
  
 [!code-cpp[ScrollViewer#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/ScrollViewer/CPP/ScrollViewer_wcp.cpp#1)]
 [!code-csharp[ScrollViewer#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewer/CSharp/ScrollViewer_wcp.cs#1)]
 [!code-vb[ScrollViewer#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ScrollViewer/VisualBasic/ScrollViewer.vb#1)]
 [!code-xaml[ScrollViewer#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/ScrollViewer/XAML/Pane1.xaml#1)]  
  
<a name="scrollviewer_styling_scrollviewer"></a>   
## <a name="styling-a-scrollviewer"></a><span data-ttu-id="7d188-132">Práce se styly ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="7d188-132">Styling a ScrollViewer</span></span>  
 <span data-ttu-id="7d188-133">Stejně jako všechny ovládací prvky v systému Windows Presentation Foundation <xref:System.Windows.Controls.ScrollViewer> můžete navržen tak, aby bylo možné změnit výchozí chování vykreslování ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="7d188-133">Like all controls in Windows Presentation Foundation, the <xref:System.Windows.Controls.ScrollViewer> can be styled in order to change the default rendering behavior of the control.</span></span> <span data-ttu-id="7d188-134">Další informace o řízení stylů, najdete v části [stylů a ukázka](../../../../docs/framework/wpf/controls/styling-and-templating.md).</span><span class="sxs-lookup"><span data-stu-id="7d188-134">For additional information on control styling, see [Styling and Templating](../../../../docs/framework/wpf/controls/styling-and-templating.md).</span></span>  
  
<a name="scrollviewer_scroll_vs_paginate"></a>   
## <a name="paginating-documents"></a><span data-ttu-id="7d188-135">Přestránkování dokumentů</span><span class="sxs-lookup"><span data-stu-id="7d188-135">Paginating Documents</span></span>  
 <span data-ttu-id="7d188-136">Pro obsah dokumentu je alternativa k procházení vyberte kontejner dokumentu, který podporuje stránkování.</span><span class="sxs-lookup"><span data-stu-id="7d188-136">For document content, an alternative to scrolling is to choose a document container that supports pagination.</span></span> <span data-ttu-id="7d188-137"><xref:System.Windows.Documents.FlowDocument>je pro dokumenty, které mají být hostované v rámci ovládacího prvku zobrazení, jako je například <xref:System.Windows.Controls.FlowDocumentPageViewer>, podporující přestránkování obsah na více stránkách, brání potřebu posouvání.</span><span class="sxs-lookup"><span data-stu-id="7d188-137"><xref:System.Windows.Documents.FlowDocument> is for documents that are designed to be hosted within a viewing control, such as <xref:System.Windows.Controls.FlowDocumentPageViewer>, that supports paginating content across multiple pages, preventing the need for scrolling.</span></span> <span data-ttu-id="7d188-138"><xref:System.Windows.Controls.DocumentViewer>nabízí řešení pro zobrazení <xref:System.Windows.Documents.FixedDocument> obsah, který používá tradiční posouvání pro zobrazení obsahu mimo sféru oblasti zobrazení.</span><span class="sxs-lookup"><span data-stu-id="7d188-138"><xref:System.Windows.Controls.DocumentViewer> provides a solution for viewing <xref:System.Windows.Documents.FixedDocument> content, which uses traditional scrolling to display content outside the realm of the display area.</span></span>  
  
 <span data-ttu-id="7d188-139">Další informace o formátech dokumentu a možnosti prezentace najdete v tématu [dokumenty v grafickém subsystému WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="7d188-139">For additional information about document formats and presentation options, see [Documents in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d188-140">Viz také</span><span class="sxs-lookup"><span data-stu-id="7d188-140">See Also</span></span>  
 <xref:System.Windows.Controls.ScrollViewer>  
 <xref:System.Windows.Controls.Primitives.ScrollBar>  
 <xref:System.Windows.Controls.Primitives.IScrollInfo>  
 [<span data-ttu-id="7d188-141">Vytvoření prohlížeče přejděte</span><span class="sxs-lookup"><span data-stu-id="7d188-141">Create a Scroll Viewer</span></span>](http://msdn.microsoft.com/en-us/c8e46af7-b417-441b-aa30-791cbdbd43ef)  
 [<span data-ttu-id="7d188-142">Dokumenty v grafickém subsystému WPF</span><span class="sxs-lookup"><span data-stu-id="7d188-142">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [<span data-ttu-id="7d188-143">ScrollBar – styly a šablony</span><span class="sxs-lookup"><span data-stu-id="7d188-143">ScrollBar Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/scrollbar-styles-and-templates.md)  
 [<span data-ttu-id="7d188-144">Ovládací prvky</span><span class="sxs-lookup"><span data-stu-id="7d188-144">Controls</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)
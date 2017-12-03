---
title: "Implementace vzoru ovládacích prvků posuv pro automatizaci uživatelského rozhraní"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UI Automation, Scroll control pattern
- control patterns, Scroll
- Scroll control pattern
ms.assetid: 73d64242-6cbb-424c-92dd-dc69530b7899
caps.latest.revision: "23"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: b9f38bbe185013c498a7ecf98bbf915b35c2d791
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="implementing-the-ui-automation-scroll-control-pattern"></a><span data-ttu-id="8d93f-102">Implementace vzoru ovládacích prvků posuv pro automatizaci uživatelského rozhraní</span><span class="sxs-lookup"><span data-stu-id="8d93f-102">Implementing the UI Automation Scroll Control Pattern</span></span>
> [!NOTE]
>  <span data-ttu-id="8d93f-103">Tato dokumentace je určena pro rozhraní .NET Framework vývojáře, kteří chtějí používat spravovanou [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] třídy definované v <xref:System.Windows.Automation> oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="8d93f-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="8d93f-104">Nejnovější informace o [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], najdete v části [rozhraní API systému Windows automatizace: automatizace uživatelského rozhraní](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="8d93f-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="8d93f-105">Toto téma představuje pokyny a konvence pro implementaci <xref:System.Windows.Automation.Provider.IScrollProvider>, včetně informací o události a vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="8d93f-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IScrollProvider>, including information about events and properties.</span></span> <span data-ttu-id="8d93f-106">Na konci tohoto tématu jsou uvedeny odkazy na další odkazy.</span><span class="sxs-lookup"><span data-stu-id="8d93f-106">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="8d93f-107"><xref:System.Windows.Automation.ScrollPattern> – Vzor ovládacích prvků se používá pro podporu ovládacího prvku, který funguje jako posuvný kontejner pro kolekci podřízených objektů.</span><span class="sxs-lookup"><span data-stu-id="8d93f-107">The <xref:System.Windows.Automation.ScrollPattern> control pattern is used to support a control that acts as a scrollable container for a collection of child objects.</span></span> <span data-ttu-id="8d93f-108">Ovládací prvek není nutné používat posuvníky pro podporu posouvání funkcí, i když běžně nemá.</span><span class="sxs-lookup"><span data-stu-id="8d93f-108">The control is not required to use scrollbars to support the scrolling functionality, although it commonly does.</span></span>  
  
 <span data-ttu-id="8d93f-109">![Posuňte se ovládací prvek bez posuvníky. ] (../../../docs/framework/ui-automation/media/uia-scrollpattern-without-scrollbars.PNG "UIA_ScrollPattern_Without_Scrollbars")</span><span class="sxs-lookup"><span data-stu-id="8d93f-109">![Scroll control without scrollbars.](../../../docs/framework/ui-automation/media/uia-scrollpattern-without-scrollbars.PNG "UIA_ScrollPattern_Without_Scrollbars")</span></span>  
<span data-ttu-id="8d93f-110">Příklad posouvání ovládací prvek, který nepoužívá posuvníky</span><span class="sxs-lookup"><span data-stu-id="8d93f-110">Example of a Scrolling Control that Does Not Use Scrollbars</span></span>  
  
 <span data-ttu-id="8d93f-111">Příklady ovládacích prvků, které implementují tento ovládací prvek najdete v tématu [řízení vzor mapování pro klienty automatizace uživatelského rozhraní](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="8d93f-111">For examples of controls that implement this control, see [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="8d93f-112">Postup implementace a konvence</span><span class="sxs-lookup"><span data-stu-id="8d93f-112">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="8d93f-113">Když implementace vzoru ovládacích prvků posuv, poznamenejte si následující pokyny a konvence:</span><span class="sxs-lookup"><span data-stu-id="8d93f-113">When implementing the Scroll control pattern, note the following guidelines and conventions:</span></span>  
  
-   <span data-ttu-id="8d93f-114">Musí implementovat podřízené objekty tohoto ovládacího prvku <xref:System.Windows.Automation.Provider.IScrollItemProvider>.</span><span class="sxs-lookup"><span data-stu-id="8d93f-114">The children of this control must implement <xref:System.Windows.Automation.Provider.IScrollItemProvider>.</span></span>  
  
-   <span data-ttu-id="8d93f-115">Posuvníky ovládacího prvku kontejner nepodporují <xref:System.Windows.Automation.ScrollPattern> – vzor ovládacích prvků.</span><span class="sxs-lookup"><span data-stu-id="8d93f-115">The scrollbars of a container control do not support the <xref:System.Windows.Automation.ScrollPattern> control pattern.</span></span> <span data-ttu-id="8d93f-116">Musí podporovat <xref:System.Windows.Automation.RangeValuePattern> řízení vzor místo.</span><span class="sxs-lookup"><span data-stu-id="8d93f-116">They must support the <xref:System.Windows.Automation.RangeValuePattern> control pattern instead.</span></span>  
  
-   <span data-ttu-id="8d93f-117">Při posouvání se měří v procentech, všechny hodnoty nebo objemy související s posun odstupňování musí být normalizovány na rozsahu od 0 do 100.</span><span class="sxs-lookup"><span data-stu-id="8d93f-117">When scrolling is measured in percentages, all values or amounts related to scroll graduation must be normalized to a range of 0 to 100.</span></span>  
  
-   <span data-ttu-id="8d93f-118"><xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontallyScrollableProperty>a <xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticallyScrollableProperty> jsou nezávislé <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty>.</span><span class="sxs-lookup"><span data-stu-id="8d93f-118"><xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontallyScrollableProperty> and <xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticallyScrollableProperty> are independent of the <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty>.</span></span>  
  
-   <span data-ttu-id="8d93f-119">Pokud <xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontallyScrollableProperty>  =  `false` pak <xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalViewSizeProperty> musí být nastavena na 100 % a <xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalScrollPercentProperty> musí být nastavena na <xref:System.Windows.Automation.ScrollPatternIdentifiers.NoScroll>.</span><span class="sxs-lookup"><span data-stu-id="8d93f-119">If <xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontallyScrollableProperty> = `false` then <xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalViewSizeProperty> should be set to 100% and <xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalScrollPercentProperty> should be set to <xref:System.Windows.Automation.ScrollPatternIdentifiers.NoScroll>.</span></span> <span data-ttu-id="8d93f-120">Podobně pokud <xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticallyScrollableProperty>  =  `false` pak <xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalViewSizeProperty> musí být nastavena na 100 procent a <xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalScrollPercentProperty> musí být nastavena na <xref:System.Windows.Automation.ScrollPatternIdentifiers.NoScroll>.</span><span class="sxs-lookup"><span data-stu-id="8d93f-120">Likewise, if <xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticallyScrollableProperty> = `false` then <xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalViewSizeProperty> should be set to 100 percent and <xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalScrollPercentProperty> should be set to <xref:System.Windows.Automation.ScrollPatternIdentifiers.NoScroll>.</span></span> <span data-ttu-id="8d93f-121">To umožňuje automatizace uživatelského rozhraní klienta pro použití v rámci hodnoty těchto vlastností <xref:System.Windows.Automation.ScrollPattern.SetScrollPercent%2A> metoda při vyloučení [soupeřit podmínku](http://support.microsoft.com/default.aspx?scid=kb;en-us;317723) Pokud směrem k klient není zájem o posouvání, dojde k aktivaci.</span><span class="sxs-lookup"><span data-stu-id="8d93f-121">This allows a UI Automation client to use these property values within the <xref:System.Windows.Automation.ScrollPattern.SetScrollPercent%2A> method while avoiding a [race condition](http://support.microsoft.com/default.aspx?scid=kb;en-us;317723) if a direction the client is not interested in scrolling becomes activated.</span></span>  
  
-   <span data-ttu-id="8d93f-122"><xref:System.Windows.Automation.Provider.IScrollProvider.HorizontalScrollPercent%2A>je specifická pro národní prostředí.</span><span class="sxs-lookup"><span data-stu-id="8d93f-122"><xref:System.Windows.Automation.Provider.IScrollProvider.HorizontalScrollPercent%2A> is locale-specific.</span></span> <span data-ttu-id="8d93f-123">Nastavení HorizontalScrollPercent = 100.0 musí nastavit posouvání umístění ovládacího prvku na ekvivalent nejvíce vpravo pozici pro jazyky, jako je angličtina, který čtení zleva doprava.</span><span class="sxs-lookup"><span data-stu-id="8d93f-123">Setting HorizontalScrollPercent = 100.0 must set the scrolling location of the control to the equivalent of its rightmost position for languages such as English that read left to right.</span></span> <span data-ttu-id="8d93f-124">Alternativně pro jazyky, jako je například arabština, který číst přímo na levé straně nastavení HorizontalScrollPercent = 100.0 musí nastavte umístění, přejděte na levou krajní pozici.</span><span class="sxs-lookup"><span data-stu-id="8d93f-124">Alternately, for languages such as Arabic that read right to left, setting HorizontalScrollPercent = 100.0 must set the scroll location to the leftmost position.</span></span>  
  
<a name="Required_Members_for_IScrollProvider"></a>   
## <a name="required-members-for-iscrollprovider"></a><span data-ttu-id="8d93f-125">Požadované členy pro IScrollProvider</span><span class="sxs-lookup"><span data-stu-id="8d93f-125">Required Members for IScrollProvider</span></span>  
 <span data-ttu-id="8d93f-126">Následující vlastnosti a metody jsou požadovány pro implementaci <xref:System.Windows.Automation.Provider.IScrollProvider>.</span><span class="sxs-lookup"><span data-stu-id="8d93f-126">The following properties and methods are required for implementing <xref:System.Windows.Automation.Provider.IScrollProvider>.</span></span>  
  
|<span data-ttu-id="8d93f-127">Povinný člen</span><span class="sxs-lookup"><span data-stu-id="8d93f-127">Required member</span></span>|<span data-ttu-id="8d93f-128">Typ člena</span><span class="sxs-lookup"><span data-stu-id="8d93f-128">Member type</span></span>|<span data-ttu-id="8d93f-129">Poznámky</span><span class="sxs-lookup"><span data-stu-id="8d93f-129">Notes</span></span>|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IScrollProvider.HorizontalScrollPercent%2A>|<span data-ttu-id="8d93f-130">Vlastnost</span><span class="sxs-lookup"><span data-stu-id="8d93f-130">Property</span></span>|<span data-ttu-id="8d93f-131">Žádné</span><span class="sxs-lookup"><span data-stu-id="8d93f-131">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IScrollProvider.VerticalScrollPercent%2A>|<span data-ttu-id="8d93f-132">Vlastnost</span><span class="sxs-lookup"><span data-stu-id="8d93f-132">Property</span></span>|<span data-ttu-id="8d93f-133">Žádné</span><span class="sxs-lookup"><span data-stu-id="8d93f-133">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IScrollProvider.HorizontalViewSize%2A>|<span data-ttu-id="8d93f-134">Vlastnost</span><span class="sxs-lookup"><span data-stu-id="8d93f-134">Property</span></span>|<span data-ttu-id="8d93f-135">Žádné</span><span class="sxs-lookup"><span data-stu-id="8d93f-135">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IScrollProvider.VerticalViewSize%2A>|<span data-ttu-id="8d93f-136">Vlastnost</span><span class="sxs-lookup"><span data-stu-id="8d93f-136">Property</span></span>|<span data-ttu-id="8d93f-137">Žádné</span><span class="sxs-lookup"><span data-stu-id="8d93f-137">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IScrollProvider.HorizontallyScrollable%2A>|<span data-ttu-id="8d93f-138">Vlastnost</span><span class="sxs-lookup"><span data-stu-id="8d93f-138">Property</span></span>|<span data-ttu-id="8d93f-139">Žádné</span><span class="sxs-lookup"><span data-stu-id="8d93f-139">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IScrollProvider.VerticallyScrollable%2A>|<span data-ttu-id="8d93f-140">Vlastnost</span><span class="sxs-lookup"><span data-stu-id="8d93f-140">Property</span></span>|<span data-ttu-id="8d93f-141">Žádné</span><span class="sxs-lookup"><span data-stu-id="8d93f-141">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IScrollProvider.Scroll%2A>|<span data-ttu-id="8d93f-142">Metoda</span><span class="sxs-lookup"><span data-stu-id="8d93f-142">Method</span></span>|<span data-ttu-id="8d93f-143">Žádné</span><span class="sxs-lookup"><span data-stu-id="8d93f-143">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IScrollProvider.SetScrollPercent%2A>|<span data-ttu-id="8d93f-144">Metoda</span><span class="sxs-lookup"><span data-stu-id="8d93f-144">Method</span></span>|<span data-ttu-id="8d93f-145">Žádné</span><span class="sxs-lookup"><span data-stu-id="8d93f-145">None</span></span>|  
  
 <span data-ttu-id="8d93f-146">Tento vzor ovládacích prvků nemá žádné přidružené události.</span><span class="sxs-lookup"><span data-stu-id="8d93f-146">This control pattern has no associated events.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="8d93f-147">Výjimky</span><span class="sxs-lookup"><span data-stu-id="8d93f-147">Exceptions</span></span>  
 <span data-ttu-id="8d93f-148">Zprostředkovatelé musí throw následující výjimky.</span><span class="sxs-lookup"><span data-stu-id="8d93f-148">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="8d93f-149">Typ výjimky</span><span class="sxs-lookup"><span data-stu-id="8d93f-149">Exception Type</span></span>|<span data-ttu-id="8d93f-150">Podmínka</span><span class="sxs-lookup"><span data-stu-id="8d93f-150">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|<span data-ttu-id="8d93f-151"><xref:System.Windows.Automation.Provider.IScrollProvider.Scroll%2A>vyvolá výjimku, pokud podporuje ovládacího prvku <xref:System.Windows.Automation.ScrollAmount.SmallIncrement> hodnoty výhradně pro vodorovné nebo svislé posouvání, ale <xref:System.Windows.Automation.ScrollAmount.LargeIncrement> je předána hodnota.</span><span class="sxs-lookup"><span data-stu-id="8d93f-151"><xref:System.Windows.Automation.Provider.IScrollProvider.Scroll%2A> throws this exception if a control supports <xref:System.Windows.Automation.ScrollAmount.SmallIncrement> values exclusively for horizontal or vertical scrolling, but a <xref:System.Windows.Automation.ScrollAmount.LargeIncrement> value is passed in.</span></span>|  
|<xref:System.ArgumentException>|<span data-ttu-id="8d93f-152"><xref:System.Windows.Automation.Provider.IScrollProvider.SetScrollPercent%2A>Pokud je předaná hodnota, která nelze převést na datový typ double, vyvolá výjimku.</span><span class="sxs-lookup"><span data-stu-id="8d93f-152"><xref:System.Windows.Automation.Provider.IScrollProvider.SetScrollPercent%2A> throws this exception when a value that cannot be converted to a double is passed in.</span></span>|  
|<xref:System.ArgumentOutOfRangeException>|<span data-ttu-id="8d93f-153"><xref:System.Windows.Automation.Provider.IScrollProvider.SetScrollPercent%2A>vyvolá výjimku, pokud je předaná hodnota vyšší než 100 nebo menší než 0 (s výjimkou -1, která je ekvivalentní <xref:System.Windows.Automation.ScrollPatternIdentifiers.NoScroll>).</span><span class="sxs-lookup"><span data-stu-id="8d93f-153"><xref:System.Windows.Automation.Provider.IScrollProvider.SetScrollPercent%2A> throws this exception when a value greater than 100 or less than 0 is passed in (except -1 which is equivalent to <xref:System.Windows.Automation.ScrollPatternIdentifiers.NoScroll>).</span></span>|  
|<xref:System.InvalidOperationException>|<span data-ttu-id="8d93f-154">Obě <xref:System.Windows.Automation.Provider.IScrollProvider.Scroll%2A> a <xref:System.Windows.Automation.Provider.IScrollProvider.SetScrollPercent%2A> výjimku výjimku při pokusu o přejděte v nepodporované směru.</span><span class="sxs-lookup"><span data-stu-id="8d93f-154">Both <xref:System.Windows.Automation.Provider.IScrollProvider.Scroll%2A> and <xref:System.Windows.Automation.Provider.IScrollProvider.SetScrollPercent%2A> throw this exception when an attempt is made to scroll in an unsupported direction.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8d93f-155">Viz také</span><span class="sxs-lookup"><span data-stu-id="8d93f-155">See Also</span></span>  
 [<span data-ttu-id="8d93f-156">Přehled vzorů ovládacích prvků automatizace uživatelského rozhraní</span><span class="sxs-lookup"><span data-stu-id="8d93f-156">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [<span data-ttu-id="8d93f-157">Podpora vzorů ovládacích prvků u zprostředkovatele automatizace uživatelského rozhraní</span><span class="sxs-lookup"><span data-stu-id="8d93f-157">Support Control Patterns in a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)  
 [<span data-ttu-id="8d93f-158">Vzory ovládacího prvku automatizace uživatelského rozhraní pro klienty</span><span class="sxs-lookup"><span data-stu-id="8d93f-158">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [<span data-ttu-id="8d93f-159">Přehled stromu automatizace uživatelského rozhraní</span><span class="sxs-lookup"><span data-stu-id="8d93f-159">UI Automation Tree Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
 [<span data-ttu-id="8d93f-160">Použití mezipaměti při automatizaci uživatelského rozhraní</span><span class="sxs-lookup"><span data-stu-id="8d93f-160">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
---
title: "Podpora automatizace uživatelského rozhraní pro typ ovládacího prvku ToolTip"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UI Automation, ToolTip control type
- ToolTip control type
- control types, ToolTip
ms.assetid: c3779d78-3164-43ae-8dae-bfaeafffdd65
caps.latest.revision: "22"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 2040020ba32aed97c613260948f0772355c1287f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="ui-automation-support-for-the-tooltip-control-type"></a><span data-ttu-id="dafd2-102">Podpora automatizace uživatelského rozhraní pro typ ovládacího prvku ToolTip</span><span class="sxs-lookup"><span data-stu-id="dafd2-102">UI Automation Support for the ToolTip Control Type</span></span>
> [!NOTE]
>  <span data-ttu-id="dafd2-103">Tato dokumentace je určena pro rozhraní .NET Framework vývojáře, kteří chtějí používat spravovanou [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] třídy definované v <xref:System.Windows.Automation> oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="dafd2-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="dafd2-104">Nejnovější informace o [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], najdete v části [rozhraní API systému Windows automatizace: automatizace uživatelského rozhraní](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="dafd2-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="dafd2-105">Toto téma obsahuje informace o [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] podporu pro typ ovládacího prvku popisek.</span><span class="sxs-lookup"><span data-stu-id="dafd2-105">This topic provides information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] support for the ToolTip control type.</span></span> <span data-ttu-id="dafd2-106">V [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], typ ovládacího prvku je sadu podmínek, které ovládacího prvku musí splnit, aby bylo možné používat <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> vlastnost.</span><span class="sxs-lookup"><span data-stu-id="dafd2-106">In [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], a control type is a set of conditions that a control must meet in order to use the <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> property.</span></span> <span data-ttu-id="dafd2-107">Podmínky zahrnují konkrétní pokyny pro [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] stromové struktury, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] hodnoty vlastností a vzory ovládacích prvků.</span><span class="sxs-lookup"><span data-stu-id="dafd2-107">The conditions include specific guidelines for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree structure, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] property values and control patterns.</span></span>  
  
 <span data-ttu-id="dafd2-108">Ovládací prvky popisek tlačítek jsou automaticky otevíraná okna, které obsahují text.</span><span class="sxs-lookup"><span data-stu-id="dafd2-108">Tool tip controls are pop-up windows that contain text.</span></span>  
  
 <span data-ttu-id="dafd2-109">Následující části zadejte požadované [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] stromové struktury, vlastnosti, vzory ovládacích prvků a události pro typ ovládacího prvku popisek.</span><span class="sxs-lookup"><span data-stu-id="dafd2-109">The following sections define the required [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree structure, properties, control patterns, and events for the ToolTip control type.</span></span> <span data-ttu-id="dafd2-110">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Požadavky platí pro všechny ovládací prvky popisek tlačítek, zda [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], nebo [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dafd2-110">The [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] requirements apply to all tool tip controls, whether [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], or [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)].</span></span>  
  
<a name="Required_UI_Automation_Tree_Structure"></a>   
## <a name="required-ui-automation-tree-structure"></a><span data-ttu-id="dafd2-111">Struktura stromu automatizace požadované uživatelského rozhraní</span><span class="sxs-lookup"><span data-stu-id="dafd2-111">Required UI Automation Tree Structure</span></span>  
 <span data-ttu-id="dafd2-112">Následující tabulka znázorňuje zobrazení ovládacího prvku a zobrazení obsahu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] stromové struktury, která se vztahují na nástroj tip ovládací prvky a popisuje, co může být obsažený v každém zobrazení.</span><span class="sxs-lookup"><span data-stu-id="dafd2-112">The following table depicts the control view and the content view of the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree that pertains to tool tip controls and describes what can be contained in each view.</span></span> <span data-ttu-id="dafd2-113">Další informace o [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] stromu najdete v tématu [Přehled stromu automatizace uživatelského rozhraní](../../../docs/framework/ui-automation/ui-automation-tree-overview.md).</span><span class="sxs-lookup"><span data-stu-id="dafd2-113">For more information on the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree, see [UI Automation Tree Overview](../../../docs/framework/ui-automation/ui-automation-tree-overview.md).</span></span>  
  
|<span data-ttu-id="dafd2-114">Zobrazení ovládacího prvku</span><span class="sxs-lookup"><span data-stu-id="dafd2-114">Control View</span></span>|<span data-ttu-id="dafd2-115">Zobrazení obsahu</span><span class="sxs-lookup"><span data-stu-id="dafd2-115">Content View</span></span>|  
|------------------|------------------|  
|<span data-ttu-id="dafd2-116">Popisy tlačítek</span><span class="sxs-lookup"><span data-stu-id="dafd2-116">ToolTip</span></span><br /><br /> <span data-ttu-id="dafd2-117">-Text (0 nebo více)</span><span class="sxs-lookup"><span data-stu-id="dafd2-117">-   Text (0 or more)</span></span><br /><span data-ttu-id="dafd2-118">-Image (0 nebo více)</span><span class="sxs-lookup"><span data-stu-id="dafd2-118">-   Image (0 or more)</span></span>|<span data-ttu-id="dafd2-119">Popisy tlačítek</span><span class="sxs-lookup"><span data-stu-id="dafd2-119">ToolTip</span></span>|  
  
 <span data-ttu-id="dafd2-120">Ovládací prvky popisek tlačítek objeví jenom v zobrazení obsahu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] stromu, pokud obdrží fokus klávesnice.</span><span class="sxs-lookup"><span data-stu-id="dafd2-120">Tool tip controls appear only in the Content View of the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree if they can receive keyboard focus.</span></span> <span data-ttu-id="dafd2-121">Jinak, všechny informace tip nástroje má k dispozici `HelpTextProperty` na [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] element, který odkazuje popis tlačítka na.</span><span class="sxs-lookup"><span data-stu-id="dafd2-121">Otherwise, all of the tool tip's information is available from the `HelpTextProperty` on the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] element that the tool tip is referring to.</span></span>  
  
 <span data-ttu-id="dafd2-122">Popisy tlačítek, měl by být pod ovládací prvek, který odkazuje na své informace.</span><span class="sxs-lookup"><span data-stu-id="dafd2-122">Tool tips should appear beneath the control that their information is referring to.</span></span> <span data-ttu-id="dafd2-123">Klienti musí naslouchat `ToolTipOpenedEvent` zajistit, že konzistentně získat informace obsažené v popisy.</span><span class="sxs-lookup"><span data-stu-id="dafd2-123">Clients must listen for the `ToolTipOpenedEvent` to ensure that they consistently obtain information contained in tool tips.</span></span>  
  
<a name="Required_UI_Automation_Properties"></a>   
## <a name="required-ui-automation-properties"></a><span data-ttu-id="dafd2-124">Vlastnosti automatizace požadované uživatelského rozhraní</span><span class="sxs-lookup"><span data-stu-id="dafd2-124">Required UI Automation Properties</span></span>  
 <span data-ttu-id="dafd2-125">Následující tabulka uvádí [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] vlastnosti, jehož hodnota nebo definice je obzvláště důležité pro ovládací prvky popisek tlačítek.</span><span class="sxs-lookup"><span data-stu-id="dafd2-125">The following table lists the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] properties whose value or definition is especially relevant to tool tip controls.</span></span> <span data-ttu-id="dafd2-126">Další informace o [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] najdete v části vlastnosti, [vlastnosti automatizace uživatelského rozhraní pro klienty](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md).</span><span class="sxs-lookup"><span data-stu-id="dafd2-126">For more information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] properties, see [UI Automation Properties for Clients](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md).</span></span>  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]<span data-ttu-id="dafd2-127">Vlastnost</span><span class="sxs-lookup"><span data-stu-id="dafd2-127"> Property</span></span>|<span data-ttu-id="dafd2-128">Hodnota</span><span class="sxs-lookup"><span data-stu-id="dafd2-128">Value</span></span>|<span data-ttu-id="dafd2-129">Poznámky</span><span class="sxs-lookup"><span data-stu-id="dafd2-129">Notes</span></span>|  
|------------------------------------------------------------------------------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|<span data-ttu-id="dafd2-130">V části poznámky.</span><span class="sxs-lookup"><span data-stu-id="dafd2-130">See notes.</span></span>|<span data-ttu-id="dafd2-131">Hodnota této vlastnosti musí být jedinečný v rámci všech ovládacích prvků v aplikaci.</span><span class="sxs-lookup"><span data-stu-id="dafd2-131">The value of this property needs to be unique across all controls in an application.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|<span data-ttu-id="dafd2-132">V části poznámky.</span><span class="sxs-lookup"><span data-stu-id="dafd2-132">See notes.</span></span>|<span data-ttu-id="dafd2-133">Nejkrajnější obdélníku, který obsahuje celý ovládací prvek.</span><span class="sxs-lookup"><span data-stu-id="dafd2-133">The outermost rectangle that contains the whole control.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|<span data-ttu-id="dafd2-134">V části poznámky.</span><span class="sxs-lookup"><span data-stu-id="dafd2-134">See notes.</span></span>|<span data-ttu-id="dafd2-135">Můžete kliknout bodu musí být součástí tip nástroj, který bude zavření ovládací prvek.</span><span class="sxs-lookup"><span data-stu-id="dafd2-135">The clickable point should be the part of the tool tip that will dismiss the control.</span></span> <span data-ttu-id="dafd2-136">Některé popisy není tato možnost a nebudou mít k dispozici prokliknutelný bod.</span><span class="sxs-lookup"><span data-stu-id="dafd2-136">Some tool tips do not have this ability and will not have a clickable point.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|<span data-ttu-id="dafd2-137">V části poznámky.</span><span class="sxs-lookup"><span data-stu-id="dafd2-137">See notes.</span></span>|<span data-ttu-id="dafd2-138">Pokud ovládací prvek může přijímat fokus klávesnice, musí podporovat tuto vlastnost.</span><span class="sxs-lookup"><span data-stu-id="dafd2-138">If the control can receive keyboard focus, it must support this property.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|<span data-ttu-id="dafd2-139">V části poznámky.</span><span class="sxs-lookup"><span data-stu-id="dafd2-139">See notes.</span></span>|<span data-ttu-id="dafd2-140">Název ovládacím prvkem popis tlačítka je text, který se zobrazí v rámci popis tlačítka.</span><span class="sxs-lookup"><span data-stu-id="dafd2-140">The name of the tool tip control is the text that is displayed within the tool tip.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|`Null`|<span data-ttu-id="dafd2-141">Ovládací prvky popisek tlačítek jsou vždy samoobslužné označeny jejich obsah.</span><span class="sxs-lookup"><span data-stu-id="dafd2-141">Tool tip controls are always self-labeled by their contents.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|<span data-ttu-id="dafd2-142">Popisy tlačítek</span><span class="sxs-lookup"><span data-stu-id="dafd2-142">ToolTip</span></span>|<span data-ttu-id="dafd2-143">Tato hodnota je stejný pro všechny rozhraní uživatelského rozhraní.</span><span class="sxs-lookup"><span data-stu-id="dafd2-143">This value is the same for all UI frameworks.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|<span data-ttu-id="dafd2-144">"Popis tlačítka"</span><span class="sxs-lookup"><span data-stu-id="dafd2-144">"tool tip"</span></span>|<span data-ttu-id="dafd2-145">Lokalizovaný řetězec odpovídající typ ovládacího prvku popisek.</span><span class="sxs-lookup"><span data-stu-id="dafd2-145">Localized string corresponding to the ToolTip control type.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|<span data-ttu-id="dafd2-146">Závisí</span><span class="sxs-lookup"><span data-stu-id="dafd2-146">Depends</span></span>|<span data-ttu-id="dafd2-147">Pokud ovládacím prvkem popis tlačítka mohou získat fokus klávesnice, musí být v zobrazení obsahu stromu.</span><span class="sxs-lookup"><span data-stu-id="dafd2-147">If the tool tip control can receive keyboard focus, it must be in the Content View of the tree.</span></span> <span data-ttu-id="dafd2-148">Pokud se jedná pouze text, je k dispozici jako HelpTextProperty z ovládacího prvku, která je vyvolána.</span><span class="sxs-lookup"><span data-stu-id="dafd2-148">If it is text only, then it is available as the HelpTextProperty from the control that raised it.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|<span data-ttu-id="dafd2-149">Hodnota TRUE</span><span class="sxs-lookup"><span data-stu-id="dafd2-149">True</span></span>|<span data-ttu-id="dafd2-150">Ovládacím prvkem popis tlačítka musí být vždy ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="dafd2-150">The tool tip control must always be a control.</span></span>|  
  
<a name="Required_UI_Automation_Control_Patterns"></a>   
## <a name="required-ui-automation-control-patterns"></a><span data-ttu-id="dafd2-151">Vzory ovládacích prvků automatizace uživatelského rozhraní požadované</span><span class="sxs-lookup"><span data-stu-id="dafd2-151">Required UI Automation Control Patterns</span></span>  
 <span data-ttu-id="dafd2-152">Následující tabulka uvádí [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] řízení vzory potřeba podporovat ovládací prvky popisek tlačítek.</span><span class="sxs-lookup"><span data-stu-id="dafd2-152">The following table lists the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] control patterns required to be supported by tool tip controls.</span></span> <span data-ttu-id="dafd2-153">Další informace o vzory ovládacích prvků, najdete v části [přehled vzorů ovládacích prvků automatizace uživatelského rozhraní](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md).</span><span class="sxs-lookup"><span data-stu-id="dafd2-153">For more information on control patterns, see [UI Automation Control Patterns Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md).</span></span>  
  
|<span data-ttu-id="dafd2-154">Vzor ovládacích prvků</span><span class="sxs-lookup"><span data-stu-id="dafd2-154">Control Pattern</span></span>|<span data-ttu-id="dafd2-155">Podpora</span><span class="sxs-lookup"><span data-stu-id="dafd2-155">Support</span></span>|<span data-ttu-id="dafd2-156">Poznámky</span><span class="sxs-lookup"><span data-stu-id="dafd2-156">Notes</span></span>|  
|---------------------|-------------|-----------|  
|<xref:System.Windows.Automation.Provider.IWindowProvider>|<span data-ttu-id="dafd2-157">Závisí</span><span class="sxs-lookup"><span data-stu-id="dafd2-157">Depends</span></span>|<span data-ttu-id="dafd2-158">Typy nástrojů, které je možné uzavřít kliknutím na položku uživatelského rozhraní musí podporovat WindowPattern tak, aby se automaticky uzavřeny.</span><span class="sxs-lookup"><span data-stu-id="dafd2-158">Tool tips that can be closed by clicking a UI item must support WindowPattern so that they can closed automatically.</span></span>|  
|<xref:System.Windows.Automation.Provider.ITextProvider>|<span data-ttu-id="dafd2-159">Závisí</span><span class="sxs-lookup"><span data-stu-id="dafd2-159">Depends</span></span>|<span data-ttu-id="dafd2-160">Pro lepší usnadnění prvkem popis tlačítka může podporovat vzor ovládacích prvků textu, i když není potřeba.</span><span class="sxs-lookup"><span data-stu-id="dafd2-160">For better accessibility, a tool tip control can support the Text control pattern, although it is not required.</span></span> <span data-ttu-id="dafd2-161">Vzor ovládacích prvků textu je užitečné, když text má bohaté styl a atributy (například barvy, tučné písmo a italics).</span><span class="sxs-lookup"><span data-stu-id="dafd2-161">The Text control pattern is useful when the text has rich style and attributes (for example, color, bold, and italics).</span></span>|  
  
<a name="Required_UI_Automation_Events"></a>   
## <a name="required-ui-automation-events"></a><span data-ttu-id="dafd2-162">Události automatizace požadované uživatelského rozhraní</span><span class="sxs-lookup"><span data-stu-id="dafd2-162">Required UI Automation Events</span></span>  
 <span data-ttu-id="dafd2-163">Ovládací prvky popisek tlačítek musíte zvýšit `ToolTipOpenedEvent` Jakmile se zobrazí na obrazovce.</span><span class="sxs-lookup"><span data-stu-id="dafd2-163">Tool tip controls must raise the `ToolTipOpenedEvent` when they appear on the screen.</span></span> <span data-ttu-id="dafd2-164">Události bude obsahovat odkaz na [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] prvek popis tlačítka, sám sebe.</span><span class="sxs-lookup"><span data-stu-id="dafd2-164">The event will include a reference to the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] element of the tool tip itself.</span></span>  
  
 <span data-ttu-id="dafd2-165">Následující tabulka uvádí [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] události potřeba podporovat všechny ovládací prvky popisek tlačítek.</span><span class="sxs-lookup"><span data-stu-id="dafd2-165">The following table lists the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] events required to be supported by all tool tip controls.</span></span> <span data-ttu-id="dafd2-166">Další informace o událostech najdete v tématu [Přehled událostí automatizace uživatelského rozhraní](../../../docs/framework/ui-automation/ui-automation-events-overview.md).</span><span class="sxs-lookup"><span data-stu-id="dafd2-166">For more information about events, see [UI Automation Events Overview](../../../docs/framework/ui-automation/ui-automation-events-overview.md).</span></span>  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]<span data-ttu-id="dafd2-167">Události</span><span class="sxs-lookup"><span data-stu-id="dafd2-167"> Event</span></span>|<span data-ttu-id="dafd2-168">Podpora</span><span class="sxs-lookup"><span data-stu-id="dafd2-168">Support</span></span>|<span data-ttu-id="dafd2-169">Poznámky</span><span class="sxs-lookup"><span data-stu-id="dafd2-169">Notes</span></span>|  
|---------------------------------------------------------------------------------|-------------|-----------|  
|<xref:System.Windows.Automation.TextPatternIdentifiers.TextSelectionChangedEvent>|<span data-ttu-id="dafd2-170">Závisí</span><span class="sxs-lookup"><span data-stu-id="dafd2-170">Depends</span></span>|<span data-ttu-id="dafd2-171">Žádné</span><span class="sxs-lookup"><span data-stu-id="dafd2-171">None</span></span>|  
|<xref:System.Windows.Automation.TextPatternIdentifiers.TextChangedEvent>|<span data-ttu-id="dafd2-172">Závisí</span><span class="sxs-lookup"><span data-stu-id="dafd2-172">Depends</span></span>|<span data-ttu-id="dafd2-173">Žádné</span><span class="sxs-lookup"><span data-stu-id="dafd2-173">None</span></span>|  
|<xref:System.Windows.Automation.WindowPatternIdentifiers.WindowClosedEvent>|<span data-ttu-id="dafd2-174">Závisí</span><span class="sxs-lookup"><span data-stu-id="dafd2-174">Depends</span></span>|<span data-ttu-id="dafd2-175">Žádné</span><span class="sxs-lookup"><span data-stu-id="dafd2-175">None</span></span>|  
|<xref:System.Windows.Automation.WindowPatternIdentifiers.WindowOpenedEvent>|<span data-ttu-id="dafd2-176">Závisí</span><span class="sxs-lookup"><span data-stu-id="dafd2-176">Depends</span></span>|<span data-ttu-id="dafd2-177">Žádné</span><span class="sxs-lookup"><span data-stu-id="dafd2-177">None</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ToolTipOpenedEvent>|<span data-ttu-id="dafd2-178">Požadováno</span><span class="sxs-lookup"><span data-stu-id="dafd2-178">Required</span></span>|<span data-ttu-id="dafd2-179">Žádné</span><span class="sxs-lookup"><span data-stu-id="dafd2-179">None</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ToolTipClosedEvent>|<span data-ttu-id="dafd2-180">Požadováno</span><span class="sxs-lookup"><span data-stu-id="dafd2-180">Required</span></span>|<span data-ttu-id="dafd2-181">Žádné</span><span class="sxs-lookup"><span data-stu-id="dafd2-181">None</span></span>|  
|<span data-ttu-id="dafd2-182"><xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>událost změny vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="dafd2-182"><xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> property-changed event.</span></span>|<span data-ttu-id="dafd2-183">Požadováno</span><span class="sxs-lookup"><span data-stu-id="dafd2-183">Required</span></span>|<span data-ttu-id="dafd2-184">Žádné</span><span class="sxs-lookup"><span data-stu-id="dafd2-184">None</span></span>|  
|<span data-ttu-id="dafd2-185"><xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty>událost změny vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="dafd2-185"><xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> property-changed event.</span></span>|<span data-ttu-id="dafd2-186">Požadováno</span><span class="sxs-lookup"><span data-stu-id="dafd2-186">Required</span></span>|<span data-ttu-id="dafd2-187">Žádné</span><span class="sxs-lookup"><span data-stu-id="dafd2-187">None</span></span>|  
|<span data-ttu-id="dafd2-188"><xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty>událost změny vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="dafd2-188"><xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> property-changed event.</span></span>|<span data-ttu-id="dafd2-189">Požadováno</span><span class="sxs-lookup"><span data-stu-id="dafd2-189">Required</span></span>|<span data-ttu-id="dafd2-190">Žádné</span><span class="sxs-lookup"><span data-stu-id="dafd2-190">None</span></span>|  
|<span data-ttu-id="dafd2-191"><xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>událost změny vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="dafd2-191"><xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty> property-changed event.</span></span>|<span data-ttu-id="dafd2-192">Požadováno</span><span class="sxs-lookup"><span data-stu-id="dafd2-192">Required</span></span>|<span data-ttu-id="dafd2-193">Žádné</span><span class="sxs-lookup"><span data-stu-id="dafd2-193">None</span></span>|  
|<span data-ttu-id="dafd2-194"><xref:System.Windows.Automation.WindowPatternIdentifiers.WindowVisualStateProperty>událost změny vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="dafd2-194"><xref:System.Windows.Automation.WindowPatternIdentifiers.WindowVisualStateProperty> property-changed event.</span></span>|<span data-ttu-id="dafd2-195">Závisí</span><span class="sxs-lookup"><span data-stu-id="dafd2-195">Depends</span></span>|<span data-ttu-id="dafd2-196">Žádné</span><span class="sxs-lookup"><span data-stu-id="dafd2-196">None</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|<span data-ttu-id="dafd2-197">Požadováno</span><span class="sxs-lookup"><span data-stu-id="dafd2-197">Required</span></span>|<span data-ttu-id="dafd2-198">Žádné</span><span class="sxs-lookup"><span data-stu-id="dafd2-198">None</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|<span data-ttu-id="dafd2-199">Požadováno</span><span class="sxs-lookup"><span data-stu-id="dafd2-199">Required</span></span>|<span data-ttu-id="dafd2-200">Žádné</span><span class="sxs-lookup"><span data-stu-id="dafd2-200">None</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dafd2-201">Viz také</span><span class="sxs-lookup"><span data-stu-id="dafd2-201">See Also</span></span>  
 <xref:System.Windows.Automation.ControlType.ToolTip>  
 [<span data-ttu-id="dafd2-202">Přehled typů ovládacích prvků automatizace uživatelského rozhraní</span><span class="sxs-lookup"><span data-stu-id="dafd2-202">UI Automation Control Types Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-types-overview.md)  
 [<span data-ttu-id="dafd2-203">Přehled automatizace uživatelského rozhraní</span><span class="sxs-lookup"><span data-stu-id="dafd2-203">UI Automation Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-overview.md)
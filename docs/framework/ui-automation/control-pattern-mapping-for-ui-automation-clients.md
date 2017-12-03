---
title: "Mapování vzorů ovládacích prvků pro klienty automatizace uživatelského rozhraní"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- control patterns, for UI Automation clients
- UI Automation, clients, control patterns for
ms.assetid: 8b81645b-8be3-4e26-9c98-4fb0fceca06b
caps.latest.revision: "18"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 31beb7ab9a978f5bb379a3c1d61c90c19c26ca6b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="control-pattern-mapping-for-ui-automation-clients"></a><span data-ttu-id="f7bf0-102">Mapování vzorů ovládacích prvků pro klienty automatizace uživatelského rozhraní</span><span class="sxs-lookup"><span data-stu-id="f7bf0-102">Control Pattern Mapping for UI Automation Clients</span></span>
> [!NOTE]
>  <span data-ttu-id="f7bf0-103">Tato dokumentace je určena pro rozhraní .NET Framework vývojáře, kteří chtějí používat spravovanou [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] třídy definované v <xref:System.Windows.Automation> oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="f7bf0-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="f7bf0-104">Nejnovější informace o [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], najdete v části [rozhraní API systému Windows automatizace: automatizace uživatelského rozhraní](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="f7bf0-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="f7bf0-105">Toto téma uvádí typy ovládacích prvků a jejich vzory přidružených ovládacích prvků.</span><span class="sxs-lookup"><span data-stu-id="f7bf0-105">This topic lists control types and their associated control patterns.</span></span>  
  
 <span data-ttu-id="f7bf0-106">V následující tabulce slouží k uspořádání vzory ovládacích prvků do následujících kategorií:</span><span class="sxs-lookup"><span data-stu-id="f7bf0-106">The following table organizes the control patterns into the following categories:</span></span>  
  
-   <span data-ttu-id="f7bf0-107">Podporováno.</span><span class="sxs-lookup"><span data-stu-id="f7bf0-107">Supported.</span></span> <span data-ttu-id="f7bf0-108">Ovládací prvek musí podporovat tento vzor ovládacích prvků.</span><span class="sxs-lookup"><span data-stu-id="f7bf0-108">The control must support this control pattern.</span></span>  
  
-   <span data-ttu-id="f7bf0-109">Podpora podmíněného.</span><span class="sxs-lookup"><span data-stu-id="f7bf0-109">Conditional support.</span></span> <span data-ttu-id="f7bf0-110">Ovládací prvek může podporovat tento vzor ovládacích prvků v závislosti na stavu ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="f7bf0-110">The control may support this control pattern depending on the state of the control.</span></span>  
  
-   <span data-ttu-id="f7bf0-111">Není podporováno.</span><span class="sxs-lookup"><span data-stu-id="f7bf0-111">Not supported.</span></span> <span data-ttu-id="f7bf0-112">Ovládací prvek nepodporuje tento – vzor ovládacích prvků; vlastní ovládací prvky může podporovat tento vzor ovládacích prvků.</span><span class="sxs-lookup"><span data-stu-id="f7bf0-112">The control does not support this control pattern; custom controls may support this control pattern.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f7bf0-113">Některé ovládací prvky mít podmíněného podporu pro několik vzorů ovládacích prvků v závislosti na funkci ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="f7bf0-113">Some controls have conditional support for several control patterns depending on the functionality of the control.</span></span> <span data-ttu-id="f7bf0-114">Například ovládací prvek položky nabídky má podmíněného podpora <xref:System.Windows.Automation.InvokePattern>, <xref:System.Windows.Automation.ExpandCollapsePattern>, <xref:System.Windows.Automation.TogglePattern>, nebo <xref:System.Windows.Automation.SelectionItemPattern> – vzor ovládacích prvků, v závislosti na jeho funkce v ovládacím prvku nabídky.</span><span class="sxs-lookup"><span data-stu-id="f7bf0-114">For example, the menu item control has conditional support for the <xref:System.Windows.Automation.InvokePattern>, <xref:System.Windows.Automation.ExpandCollapsePattern>, <xref:System.Windows.Automation.TogglePattern>, or <xref:System.Windows.Automation.SelectionItemPattern> control pattern, depending on its function in the menu control.</span></span>  
  
<a name="control_mapping_clients"></a>   
## <a name="ui-automation-control-patterns-for-clients"></a><span data-ttu-id="f7bf0-115">Vzory ovládacích prvků automatizace uživatelského rozhraní pro klienty</span><span class="sxs-lookup"><span data-stu-id="f7bf0-115">UI Automation Control Patterns for Clients</span></span>  
  
|<span data-ttu-id="f7bf0-116">– Typ ovládacího prvku</span><span class="sxs-lookup"><span data-stu-id="f7bf0-116">Control Type</span></span>|<span data-ttu-id="f7bf0-117">Podporováno</span><span class="sxs-lookup"><span data-stu-id="f7bf0-117">Supported</span></span>|<span data-ttu-id="f7bf0-118">Podpora podmíněného</span><span class="sxs-lookup"><span data-stu-id="f7bf0-118">Conditional Support</span></span>|<span data-ttu-id="f7bf0-119">Nepodporováno</span><span class="sxs-lookup"><span data-stu-id="f7bf0-119">Not Supported</span></span>|  
|------------------|---------------|-------------------------|-------------------|  
|<span data-ttu-id="f7bf0-120">Tlačítko</span><span class="sxs-lookup"><span data-stu-id="f7bf0-120">Button</span></span>|<span data-ttu-id="f7bf0-121">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-121">None</span></span>|<span data-ttu-id="f7bf0-122">Vyvolání přepnutí, rozbalte položku sbalit</span><span class="sxs-lookup"><span data-stu-id="f7bf0-122">Invoke, Toggle, Expand Collapse</span></span>|<span data-ttu-id="f7bf0-123">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-123">None</span></span>|  
|<span data-ttu-id="f7bf0-124">Kalendář</span><span class="sxs-lookup"><span data-stu-id="f7bf0-124">Calendar</span></span>|<span data-ttu-id="f7bf0-125">Mřížky, tabulka</span><span class="sxs-lookup"><span data-stu-id="f7bf0-125">Grid, Table</span></span>|<span data-ttu-id="f7bf0-126">Výběr, posuňte</span><span class="sxs-lookup"><span data-stu-id="f7bf0-126">Selection, Scroll</span></span>|<span data-ttu-id="f7bf0-127">Hodnota</span><span class="sxs-lookup"><span data-stu-id="f7bf0-127">Value</span></span>|  
|<span data-ttu-id="f7bf0-128">Zaškrtávací políčko</span><span class="sxs-lookup"><span data-stu-id="f7bf0-128">Check Box</span></span>|<span data-ttu-id="f7bf0-129">Přepnout</span><span class="sxs-lookup"><span data-stu-id="f7bf0-129">Toggle</span></span>|<span data-ttu-id="f7bf0-130">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-130">None</span></span>|<span data-ttu-id="f7bf0-131">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-131">None</span></span>|  
|<span data-ttu-id="f7bf0-132">Pole se seznamem</span><span class="sxs-lookup"><span data-stu-id="f7bf0-132">Combo Box</span></span>|<span data-ttu-id="f7bf0-133">Rozbalte položku sbalit</span><span class="sxs-lookup"><span data-stu-id="f7bf0-133">Expand Collapse</span></span>|<span data-ttu-id="f7bf0-134">Výběr, hodnota</span><span class="sxs-lookup"><span data-stu-id="f7bf0-134">Selection, Value</span></span>|<span data-ttu-id="f7bf0-135">Posuv</span><span class="sxs-lookup"><span data-stu-id="f7bf0-135">Scroll</span></span>|  
|<span data-ttu-id="f7bf0-136">Datová mřížka</span><span class="sxs-lookup"><span data-stu-id="f7bf0-136">Data Grid</span></span>|<span data-ttu-id="f7bf0-137">Mřížka</span><span class="sxs-lookup"><span data-stu-id="f7bf0-137">Grid</span></span>|<span data-ttu-id="f7bf0-138">Posuv, výběr, tabulka</span><span class="sxs-lookup"><span data-stu-id="f7bf0-138">Scroll, Selection, Table</span></span>|<span data-ttu-id="f7bf0-139">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-139">None</span></span>|  
|<span data-ttu-id="f7bf0-140">Datová položka</span><span class="sxs-lookup"><span data-stu-id="f7bf0-140">Data Item</span></span>|<span data-ttu-id="f7bf0-141">Položka výběru</span><span class="sxs-lookup"><span data-stu-id="f7bf0-141">Selection Item</span></span>|<span data-ttu-id="f7bf0-142">Rozbalte položku sbalit, položky v mřížce, Scroll položky, tabulku, přepínač, hodnota</span><span class="sxs-lookup"><span data-stu-id="f7bf0-142">Expand Collapse, Grid Item, Scroll Item, Table, Toggle, Value</span></span>|<span data-ttu-id="f7bf0-143">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-143">None</span></span>|  
|<span data-ttu-id="f7bf0-144">Dokument</span><span class="sxs-lookup"><span data-stu-id="f7bf0-144">Document</span></span>|<span data-ttu-id="f7bf0-145">Text</span><span class="sxs-lookup"><span data-stu-id="f7bf0-145">Text</span></span>|<span data-ttu-id="f7bf0-146">Posuv, hodnota</span><span class="sxs-lookup"><span data-stu-id="f7bf0-146">Scroll, Value</span></span>|<span data-ttu-id="f7bf0-147">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-147">None</span></span>|  
|<span data-ttu-id="f7bf0-148">Upravit</span><span class="sxs-lookup"><span data-stu-id="f7bf0-148">Edit</span></span>|<span data-ttu-id="f7bf0-149">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-149">None</span></span>|<span data-ttu-id="f7bf0-150">Hodnota text, hodnotu rozsahu</span><span class="sxs-lookup"><span data-stu-id="f7bf0-150">Text, Range Value, Value</span></span>|<span data-ttu-id="f7bf0-151">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-151">None</span></span>|  
|<span data-ttu-id="f7bf0-152">Skupina</span><span class="sxs-lookup"><span data-stu-id="f7bf0-152">Group</span></span>|<span data-ttu-id="f7bf0-153">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-153">None</span></span>|<span data-ttu-id="f7bf0-154">Rozbalte položku sbalit</span><span class="sxs-lookup"><span data-stu-id="f7bf0-154">Expand Collapse</span></span>|<span data-ttu-id="f7bf0-155">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-155">None</span></span>|  
|<span data-ttu-id="f7bf0-156">Záhlaví</span><span class="sxs-lookup"><span data-stu-id="f7bf0-156">Header</span></span>|<span data-ttu-id="f7bf0-157">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-157">None</span></span>|<span data-ttu-id="f7bf0-158">Transformace</span><span class="sxs-lookup"><span data-stu-id="f7bf0-158">Transform</span></span>|<span data-ttu-id="f7bf0-159">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-159">None</span></span>|  
|<span data-ttu-id="f7bf0-160">Položka hlavičky</span><span class="sxs-lookup"><span data-stu-id="f7bf0-160">Header Item</span></span>|<span data-ttu-id="f7bf0-161">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-161">None</span></span>|<span data-ttu-id="f7bf0-162">Transformace, vyvolání</span><span class="sxs-lookup"><span data-stu-id="f7bf0-162">Transform, Invoke</span></span>|<span data-ttu-id="f7bf0-163">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-163">None</span></span>|  
|<span data-ttu-id="f7bf0-164">Hypertextový odkaz</span><span class="sxs-lookup"><span data-stu-id="f7bf0-164">Hyperlink</span></span>|<span data-ttu-id="f7bf0-165">Vyvolat</span><span class="sxs-lookup"><span data-stu-id="f7bf0-165">Invoke</span></span>|<span data-ttu-id="f7bf0-166">Hodnota</span><span class="sxs-lookup"><span data-stu-id="f7bf0-166">Value</span></span>|<span data-ttu-id="f7bf0-167">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-167">None</span></span>|  
|<span data-ttu-id="f7bf0-168">Image</span><span class="sxs-lookup"><span data-stu-id="f7bf0-168">Image</span></span>|<span data-ttu-id="f7bf0-169">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-169">None</span></span>|<span data-ttu-id="f7bf0-170">Položky v mřížce, položka tabulky</span><span class="sxs-lookup"><span data-stu-id="f7bf0-170">Grid Item, Table Item</span></span>|<span data-ttu-id="f7bf0-171">Vyvolání, výběr položky</span><span class="sxs-lookup"><span data-stu-id="f7bf0-171">Invoke, Selection Item</span></span>|  
|<span data-ttu-id="f7bf0-172">Seznam</span><span class="sxs-lookup"><span data-stu-id="f7bf0-172">List</span></span>|<span data-ttu-id="f7bf0-173">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-173">None</span></span>|<span data-ttu-id="f7bf0-174">Posuv mřížky, více zobrazení, výběr</span><span class="sxs-lookup"><span data-stu-id="f7bf0-174">Grid, Multiple View, Scroll, Selection</span></span>|<span data-ttu-id="f7bf0-175">Tabulka</span><span class="sxs-lookup"><span data-stu-id="f7bf0-175">Table</span></span>|  
|<span data-ttu-id="f7bf0-176">Položky seznamu</span><span class="sxs-lookup"><span data-stu-id="f7bf0-176">List Item</span></span>|<span data-ttu-id="f7bf0-177">Položka výběru</span><span class="sxs-lookup"><span data-stu-id="f7bf0-177">Selection Item</span></span>|<span data-ttu-id="f7bf0-178">Rozbalte položku sbalit, položky v mřížce, vyvolání, posuňte se položky, přepněte, hodnota</span><span class="sxs-lookup"><span data-stu-id="f7bf0-178">Expand Collapse, Grid Item, Invoke, Scroll Item, Toggle, Value</span></span>|<span data-ttu-id="f7bf0-179">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-179">None</span></span>|  
|<span data-ttu-id="f7bf0-180">Nabídka</span><span class="sxs-lookup"><span data-stu-id="f7bf0-180">Menu</span></span>|<span data-ttu-id="f7bf0-181">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-181">None</span></span>|<span data-ttu-id="f7bf0-182">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-182">None</span></span>|<span data-ttu-id="f7bf0-183">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-183">None</span></span>|  
|<span data-ttu-id="f7bf0-184">Řádek nabídek</span><span class="sxs-lookup"><span data-stu-id="f7bf0-184">Menu Bar</span></span>|<span data-ttu-id="f7bf0-185">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-185">None</span></span>|<span data-ttu-id="f7bf0-186">Rozbalte položku sbalit, ukotvení, transformace</span><span class="sxs-lookup"><span data-stu-id="f7bf0-186">Expand Collapse, Dock, Transform</span></span>|<span data-ttu-id="f7bf0-187">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-187">None</span></span>|  
|<span data-ttu-id="f7bf0-188">Položka nabídky</span><span class="sxs-lookup"><span data-stu-id="f7bf0-188">Menu Item</span></span>|<span data-ttu-id="f7bf0-189">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-189">None</span></span>|<span data-ttu-id="f7bf0-190">Rozbalte sbalit, vyvolání, položka výběru přepnutí</span><span class="sxs-lookup"><span data-stu-id="f7bf0-190">Expand Collapse, Invoke, Selection Item, Toggle</span></span>|<span data-ttu-id="f7bf0-191">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-191">None</span></span>|  
|<span data-ttu-id="f7bf0-192">Podokno</span><span class="sxs-lookup"><span data-stu-id="f7bf0-192">Pane</span></span>|<span data-ttu-id="f7bf0-193">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-193">None</span></span>|<span data-ttu-id="f7bf0-194">Ukotvení.</span><span class="sxs-lookup"><span data-stu-id="f7bf0-194">Dock.</span></span> <span data-ttu-id="f7bf0-195">Posuňte, transformace</span><span class="sxs-lookup"><span data-stu-id="f7bf0-195">Scroll, Transform</span></span>|<span data-ttu-id="f7bf0-196">Okno</span><span class="sxs-lookup"><span data-stu-id="f7bf0-196">Window</span></span>|  
|<span data-ttu-id="f7bf0-197">Indikátor průběhu</span><span class="sxs-lookup"><span data-stu-id="f7bf0-197">Progress Bar</span></span>|<span data-ttu-id="f7bf0-198">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-198">None</span></span>|<span data-ttu-id="f7bf0-199">Hodnotu rozsahu, hodnota</span><span class="sxs-lookup"><span data-stu-id="f7bf0-199">Range Value, Value</span></span>|<span data-ttu-id="f7bf0-200">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-200">None</span></span>|  
|<span data-ttu-id="f7bf0-201">Přepínač</span><span class="sxs-lookup"><span data-stu-id="f7bf0-201">Radio Button</span></span>|<span data-ttu-id="f7bf0-202">Položka výběru</span><span class="sxs-lookup"><span data-stu-id="f7bf0-202">Selection Item</span></span>|<span data-ttu-id="f7bf0-203">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-203">None</span></span>|<span data-ttu-id="f7bf0-204">Přepnout</span><span class="sxs-lookup"><span data-stu-id="f7bf0-204">Toggle</span></span>|  
|<span data-ttu-id="f7bf0-205">Posuvník</span><span class="sxs-lookup"><span data-stu-id="f7bf0-205">Scroll Bar</span></span>|<span data-ttu-id="f7bf0-206">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-206">None</span></span>|<span data-ttu-id="f7bf0-207">Hodnota v rozsahu</span><span class="sxs-lookup"><span data-stu-id="f7bf0-207">Range Value</span></span>|<span data-ttu-id="f7bf0-208">Posuv</span><span class="sxs-lookup"><span data-stu-id="f7bf0-208">Scroll</span></span>|  
|<span data-ttu-id="f7bf0-209">Oddělovač</span><span class="sxs-lookup"><span data-stu-id="f7bf0-209">Separator</span></span>|<span data-ttu-id="f7bf0-210">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-210">None</span></span>|<span data-ttu-id="f7bf0-211">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-211">None</span></span>|<span data-ttu-id="f7bf0-212">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-212">None</span></span>|  
|<span data-ttu-id="f7bf0-213">Posuvník</span><span class="sxs-lookup"><span data-stu-id="f7bf0-213">Slider</span></span>|<span data-ttu-id="f7bf0-214">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-214">None</span></span>|<span data-ttu-id="f7bf0-215">Hodnota, výběr, hodnota rozsahu</span><span class="sxs-lookup"><span data-stu-id="f7bf0-215">Range Value, Selection, Value</span></span>|<span data-ttu-id="f7bf0-216">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-216">None</span></span>|  
|<span data-ttu-id="f7bf0-217">Číselník</span><span class="sxs-lookup"><span data-stu-id="f7bf0-217">Spinner</span></span>|<span data-ttu-id="f7bf0-218">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-218">None</span></span>|<span data-ttu-id="f7bf0-219">Hodnota, výběr, hodnota rozsahu</span><span class="sxs-lookup"><span data-stu-id="f7bf0-219">Range Value, Selection, Value</span></span>|<span data-ttu-id="f7bf0-220">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-220">None</span></span>|  
|<span data-ttu-id="f7bf0-221">Tlačítko rozdělení</span><span class="sxs-lookup"><span data-stu-id="f7bf0-221">Split Button</span></span>|<span data-ttu-id="f7bf0-222">Vyvolání, rozbalte položku sbalit</span><span class="sxs-lookup"><span data-stu-id="f7bf0-222">Invoke, Expand Collapse</span></span>|<span data-ttu-id="f7bf0-223">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-223">None</span></span>|<span data-ttu-id="f7bf0-224">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-224">None</span></span>|  
|<span data-ttu-id="f7bf0-225">Stavový řádek</span><span class="sxs-lookup"><span data-stu-id="f7bf0-225">Status Bar</span></span>|<span data-ttu-id="f7bf0-226">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-226">None</span></span>|<span data-ttu-id="f7bf0-227">Mřížka</span><span class="sxs-lookup"><span data-stu-id="f7bf0-227">Grid</span></span>|<span data-ttu-id="f7bf0-228">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-228">None</span></span>|  
|<span data-ttu-id="f7bf0-229">Tabulátor</span><span class="sxs-lookup"><span data-stu-id="f7bf0-229">Tab</span></span>|<span data-ttu-id="f7bf0-230">Výběr</span><span class="sxs-lookup"><span data-stu-id="f7bf0-230">Selection</span></span>|<span data-ttu-id="f7bf0-231">Posuv</span><span class="sxs-lookup"><span data-stu-id="f7bf0-231">Scroll</span></span>|<span data-ttu-id="f7bf0-232">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-232">None</span></span>|  
|<span data-ttu-id="f7bf0-233">Položka tabulátoru</span><span class="sxs-lookup"><span data-stu-id="f7bf0-233">Tab Item</span></span>|<span data-ttu-id="f7bf0-234">Položka výběru</span><span class="sxs-lookup"><span data-stu-id="f7bf0-234">Selection Item</span></span>|<span data-ttu-id="f7bf0-235">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-235">None</span></span>|<span data-ttu-id="f7bf0-236">Vyvolat</span><span class="sxs-lookup"><span data-stu-id="f7bf0-236">Invoke</span></span>|  
|<span data-ttu-id="f7bf0-237">Tabulka</span><span class="sxs-lookup"><span data-stu-id="f7bf0-237">Table</span></span>|<span data-ttu-id="f7bf0-238">Mřížky, položky v mřížce, tabulce, tabulka položek</span><span class="sxs-lookup"><span data-stu-id="f7bf0-238">Grid, Grid Item, Table, Table Item</span></span>|<span data-ttu-id="f7bf0-239">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-239">None</span></span>|<span data-ttu-id="f7bf0-240">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-240">None</span></span>|  
|<span data-ttu-id="f7bf0-241">Text</span><span class="sxs-lookup"><span data-stu-id="f7bf0-241">Text</span></span>|<span data-ttu-id="f7bf0-242">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-242">None</span></span>|<span data-ttu-id="f7bf0-243">Text položky, položka tabulky mřížky</span><span class="sxs-lookup"><span data-stu-id="f7bf0-243">Grid Item, Table Item, Text</span></span>|<span data-ttu-id="f7bf0-244">Hodnota</span><span class="sxs-lookup"><span data-stu-id="f7bf0-244">Value</span></span>|  
|<span data-ttu-id="f7bf0-245">Jezdec</span><span class="sxs-lookup"><span data-stu-id="f7bf0-245">Thumb</span></span>|<span data-ttu-id="f7bf0-246">Transformace</span><span class="sxs-lookup"><span data-stu-id="f7bf0-246">Transform</span></span>|<span data-ttu-id="f7bf0-247">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-247">None</span></span>|<span data-ttu-id="f7bf0-248">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-248">None</span></span>|  
|<span data-ttu-id="f7bf0-249">Záhlaví</span><span class="sxs-lookup"><span data-stu-id="f7bf0-249">Title Bar</span></span>|<span data-ttu-id="f7bf0-250">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-250">None</span></span>|<span data-ttu-id="f7bf0-251">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-251">None</span></span>|<span data-ttu-id="f7bf0-252">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-252">None</span></span>|  
|<span data-ttu-id="f7bf0-253">Panel nástrojů</span><span class="sxs-lookup"><span data-stu-id="f7bf0-253">Tool Bar</span></span>|<span data-ttu-id="f7bf0-254">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-254">None</span></span>|<span data-ttu-id="f7bf0-255">Ukotvení, rozbalte položku sbalit, transformace</span><span class="sxs-lookup"><span data-stu-id="f7bf0-255">Dock, Expand Collapse, Transform</span></span>|<span data-ttu-id="f7bf0-256">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-256">None</span></span>|  
|<span data-ttu-id="f7bf0-257">Popis tlačítka</span><span class="sxs-lookup"><span data-stu-id="f7bf0-257">Tool Tip</span></span>|<span data-ttu-id="f7bf0-258">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-258">None</span></span>|<span data-ttu-id="f7bf0-259">Text, okno</span><span class="sxs-lookup"><span data-stu-id="f7bf0-259">Text, Window</span></span>|<span data-ttu-id="f7bf0-260">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-260">None</span></span>|  
|<span data-ttu-id="f7bf0-261">Strom</span><span class="sxs-lookup"><span data-stu-id="f7bf0-261">Tree</span></span>|<span data-ttu-id="f7bf0-262">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-262">None</span></span>|<span data-ttu-id="f7bf0-263">Posun výběru</span><span class="sxs-lookup"><span data-stu-id="f7bf0-263">Scroll, Selection</span></span>|<span data-ttu-id="f7bf0-264">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-264">None</span></span>|  
|<span data-ttu-id="f7bf0-265">Položka stromu</span><span class="sxs-lookup"><span data-stu-id="f7bf0-265">Tree Item</span></span>|<span data-ttu-id="f7bf0-266">Rozbalte položku sbalit</span><span class="sxs-lookup"><span data-stu-id="f7bf0-266">Expand Collapse</span></span>|<span data-ttu-id="f7bf0-267">Vyvolání, posuňte položky, položka výběru, přepínač</span><span class="sxs-lookup"><span data-stu-id="f7bf0-267">Invoke, Scroll Item, Selection Item, Toggle</span></span>|<span data-ttu-id="f7bf0-268">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-268">None</span></span>|  
|<span data-ttu-id="f7bf0-269">Okno</span><span class="sxs-lookup"><span data-stu-id="f7bf0-269">Window</span></span>|<span data-ttu-id="f7bf0-270">Transformace, okno</span><span class="sxs-lookup"><span data-stu-id="f7bf0-270">Transform, Window</span></span>|<span data-ttu-id="f7bf0-271">Ukotvení</span><span class="sxs-lookup"><span data-stu-id="f7bf0-271">Dock</span></span>|<span data-ttu-id="f7bf0-272">Žádné</span><span class="sxs-lookup"><span data-stu-id="f7bf0-272">None</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="f7bf0-273">Pokud typ ovládacího prvku nemá žádné podporované řízení vzorce uvedené, ale má jeden nebo více podmíněně podporovaných vzorů ovládacích prvků, potom jeden z těchto vzory podmíněného ovládacích prvků budou podporovány ve všech případech.</span><span class="sxs-lookup"><span data-stu-id="f7bf0-273">If a control type has no supported control patterns listed but has one or more conditionally-supported control patterns, then one of those conditional control patterns will be supported at all times.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7bf0-274">Viz také</span><span class="sxs-lookup"><span data-stu-id="f7bf0-274">See Also</span></span>  
 [<span data-ttu-id="f7bf0-275">Přehled automatizace uživatelského rozhraní</span><span class="sxs-lookup"><span data-stu-id="f7bf0-275">UI Automation Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-overview.md)
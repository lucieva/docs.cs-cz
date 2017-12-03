---
title: "Podpora automatizace uživatelského rozhraní pro typ ovládacího prvku ProgressBar"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- control types, Progress Bar
- ProgressBar control type
- UI Automation, Progress Bar control type
ms.assetid: 302e778c-24b0-4789-814a-c8d37cf53a5f
caps.latest.revision: "21"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 84ff5d1d59204fec4bbddd43dd834d1c9b22406d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="ui-automation-support-for-the-progressbar-control-type"></a><span data-ttu-id="5bc3d-102">Podpora automatizace uživatelského rozhraní pro typ ovládacího prvku ProgressBar</span><span class="sxs-lookup"><span data-stu-id="5bc3d-102">UI Automation Support for the ProgressBar Control Type</span></span>
> [!NOTE]
>  <span data-ttu-id="5bc3d-103">Tato dokumentace je určena pro rozhraní .NET Framework vývojáře, kteří chtějí používat spravovanou [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] třídy definované v <xref:System.Windows.Automation> oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="5bc3d-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="5bc3d-104">Nejnovější informace o [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], najdete v části [rozhraní API systému Windows automatizace: automatizace uživatelského rozhraní](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="5bc3d-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="5bc3d-105">Toto téma obsahuje informace o [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] podporu pro typ ovládacího prvku ProgressBar.</span><span class="sxs-lookup"><span data-stu-id="5bc3d-105">This topic provides information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] support for the ProgressBar control type.</span></span> <span data-ttu-id="5bc3d-106">V [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], typ ovládacího prvku je sadu podmínek, které ovládacího prvku musí splnit, aby bylo možné používat <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> vlastnost.</span><span class="sxs-lookup"><span data-stu-id="5bc3d-106">In [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], a control type is a set of conditions that a control must meet in order to use the <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> property.</span></span> <span data-ttu-id="5bc3d-107">Podmínky zahrnují konkrétní pokyny pro [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] stromové struktury, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] hodnoty vlastností, vzory ovládacích prvků a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] události.</span><span class="sxs-lookup"><span data-stu-id="5bc3d-107">The conditions include specific guidelines for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree structure, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] property values, control patterns, and [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] events.</span></span>  
  
 <span data-ttu-id="5bc3d-108">Ovládací prvky panelu průběhu jsou příklady ovládacích prvků, které implementují typ ovládacího prvku ProgressBar.</span><span class="sxs-lookup"><span data-stu-id="5bc3d-108">Progress bar controls are an example of controls that implement the ProgressBar control type.</span></span> <span data-ttu-id="5bc3d-109">Ovládací prvky panelu průběhu slouží k určení průběhu časově náročná operace.</span><span class="sxs-lookup"><span data-stu-id="5bc3d-109">Progress bar controls are used to indicate the progress of a lengthy operation.</span></span> <span data-ttu-id="5bc3d-110">Ovládací prvek se skládá z obdélníku, která postupně, naplní se barva zvýraznění systému v průběhu operace.</span><span class="sxs-lookup"><span data-stu-id="5bc3d-110">The control consists of a rectangle that is gradually filled with the system highlight color as an operation progresses.</span></span>  
  
 <span data-ttu-id="5bc3d-111">Následující části zadejte požadované [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] stromové struktury, vlastnosti, vzory ovládacích prvků a události pro typ ovládacího prvku ProgressBar.</span><span class="sxs-lookup"><span data-stu-id="5bc3d-111">The following sections define the required [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree structure, properties, control patterns, and events for the ProgressBar control type.</span></span> <span data-ttu-id="5bc3d-112">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Požadavky platí pro všechny ovládací prvky seznamu, zda [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], nebo [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5bc3d-112">The [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] requirements apply to all list controls, whether [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], or [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)].</span></span>  
  
<a name="Required_UI_Automation_Tree_Structure"></a>   
## <a name="required-ui-automation-tree-structure"></a><span data-ttu-id="5bc3d-113">Struktura stromu automatizace požadované uživatelského rozhraní</span><span class="sxs-lookup"><span data-stu-id="5bc3d-113">Required UI Automation Tree Structure</span></span>  
 <span data-ttu-id="5bc3d-114">Následující tabulka znázorňuje zobrazení ovládacího prvku a zobrazení obsahu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] stromové struktury, která se vztahují na indikátor průběhu ovládací prvky a popisuje, co může být obsažený v každém zobrazení.</span><span class="sxs-lookup"><span data-stu-id="5bc3d-114">The following table depicts the control view and the content view of the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree that pertains to progress bar controls and describes what can be contained in each view.</span></span> <span data-ttu-id="5bc3d-115">Další informace o [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] stromu najdete v tématu [Přehled stromu automatizace uživatelského rozhraní](../../../docs/framework/ui-automation/ui-automation-tree-overview.md).</span><span class="sxs-lookup"><span data-stu-id="5bc3d-115">For more information on the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree, see [UI Automation Tree Overview](../../../docs/framework/ui-automation/ui-automation-tree-overview.md).</span></span>  
  
|<span data-ttu-id="5bc3d-116">Zobrazení ovládacího prvku</span><span class="sxs-lookup"><span data-stu-id="5bc3d-116">Control View</span></span>|<span data-ttu-id="5bc3d-117">Zobrazení obsahu</span><span class="sxs-lookup"><span data-stu-id="5bc3d-117">Content View</span></span>|  
|------------------|------------------|  
|<span data-ttu-id="5bc3d-118">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="5bc3d-118">ProgressBar</span></span>|<span data-ttu-id="5bc3d-119">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="5bc3d-119">ProgressBar</span></span>|  
  
 <span data-ttu-id="5bc3d-120">Ovládací prvky panelu průběhu nemají žádné podřízené položky v zobrazení obsahu nebo ovládací prvek [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] stromu.</span><span class="sxs-lookup"><span data-stu-id="5bc3d-120">The progress bar controls do not have any children in the control or content view of the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree.</span></span>  
  
<a name="Required_UI_Automation_Properties"></a>   
## <a name="required-ui-automation-properties"></a><span data-ttu-id="5bc3d-121">Vlastnosti automatizace požadované uživatelského rozhraní</span><span class="sxs-lookup"><span data-stu-id="5bc3d-121">Required UI Automation Properties</span></span>  
 <span data-ttu-id="5bc3d-122">Následující tabulka uvádí [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] vlastnosti, jehož hodnota nebo definice je obzvláště důležité pro ovládací prvky panelu průběhu.</span><span class="sxs-lookup"><span data-stu-id="5bc3d-122">The following table lists the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] properties whose value or definition is especially relevant to progress bar controls.</span></span> <span data-ttu-id="5bc3d-123">Další informace o [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] najdete v části vlastnosti, [vlastnosti automatizace uživatelského rozhraní pro klienty](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md).</span><span class="sxs-lookup"><span data-stu-id="5bc3d-123">For more information on [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] properties, see [UI Automation Properties for Clients](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md).</span></span>  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]<span data-ttu-id="5bc3d-124">Vlastnost</span><span class="sxs-lookup"><span data-stu-id="5bc3d-124"> Property</span></span>|<span data-ttu-id="5bc3d-125">Hodnota</span><span class="sxs-lookup"><span data-stu-id="5bc3d-125">Value</span></span>|<span data-ttu-id="5bc3d-126">Poznámky</span><span class="sxs-lookup"><span data-stu-id="5bc3d-126">Notes</span></span>|  
|------------------------------------------------------------------------------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|<span data-ttu-id="5bc3d-127">V části poznámky.</span><span class="sxs-lookup"><span data-stu-id="5bc3d-127">See notes.</span></span>|<span data-ttu-id="5bc3d-128">Hodnota této vlastnosti musí být jedinečný v rámci všech ovládacích prvků v aplikaci.</span><span class="sxs-lookup"><span data-stu-id="5bc3d-128">The value of this property needs to be unique across all controls in an application.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|<span data-ttu-id="5bc3d-129">V části poznámky.</span><span class="sxs-lookup"><span data-stu-id="5bc3d-129">See notes.</span></span>|<span data-ttu-id="5bc3d-130">Nejkrajnější obdélníku, který obsahuje celý ovládací prvek.</span><span class="sxs-lookup"><span data-stu-id="5bc3d-130">The outermost rectangle that contains the whole control.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|<span data-ttu-id="5bc3d-131">V části poznámky.</span><span class="sxs-lookup"><span data-stu-id="5bc3d-131">See notes.</span></span>|<span data-ttu-id="5bc3d-132">Podporováno, pokud je ohraničující obdélník.</span><span class="sxs-lookup"><span data-stu-id="5bc3d-132">Supported if there is a bounding rectangle.</span></span> <span data-ttu-id="5bc3d-133">Není-li každého bodu v rámci ohraničující obdélník je můžete kliknout a provést specializované přístupů testování, přepsání a nabízí bod můžete kliknout.</span><span class="sxs-lookup"><span data-stu-id="5bc3d-133">If not every point within the bounding rectangle is clickable, and you perform specialized hit testing, then override and provide a clickable point.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|<span data-ttu-id="5bc3d-134">V části poznámky.</span><span class="sxs-lookup"><span data-stu-id="5bc3d-134">See notes.</span></span>|<span data-ttu-id="5bc3d-135">Pokud ovládací prvek může přijímat fokus klávesnice, musí podporovat tuto vlastnost.</span><span class="sxs-lookup"><span data-stu-id="5bc3d-135">If the control can receive keyboard focus, it must support this property.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|<span data-ttu-id="5bc3d-136">V části poznámky.</span><span class="sxs-lookup"><span data-stu-id="5bc3d-136">See notes.</span></span>|<span data-ttu-id="5bc3d-137">Ovládací panel prvek průběh obvykle získá její název ze statického textu popisku.</span><span class="sxs-lookup"><span data-stu-id="5bc3d-137">The progress bar control typically gets its name from a static text label.</span></span> <span data-ttu-id="5bc3d-138">Pokud není k dispozici statický text popisku vývojář aplikace musí vystavit hodnotu `Name` vlastnost.</span><span class="sxs-lookup"><span data-stu-id="5bc3d-138">If there is not a static text label the application developer must expose a value for the `Name` property.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|<span data-ttu-id="5bc3d-139">V části poznámky.</span><span class="sxs-lookup"><span data-stu-id="5bc3d-139">See notes.</span></span>|<span data-ttu-id="5bc3d-140">Pokud je statický text popisku této vlastnosti musí vystavit odkaz u daného ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="5bc3d-140">If there is a static text label then this property must expose a reference to that control.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|<span data-ttu-id="5bc3d-141">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="5bc3d-141">ProgressBar</span></span>|<span data-ttu-id="5bc3d-142">Tato hodnota je stejný pro všechny rozhraní uživatelského rozhraní.</span><span class="sxs-lookup"><span data-stu-id="5bc3d-142">This value is the same for all UI frameworks.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|<span data-ttu-id="5bc3d-143">"indikátor průběhu"</span><span class="sxs-lookup"><span data-stu-id="5bc3d-143">"progress bar"</span></span>|<span data-ttu-id="5bc3d-144">Lokalizovaný řetězec odpovídající typ ovládacího prvku ProgressBar.</span><span class="sxs-lookup"><span data-stu-id="5bc3d-144">Localized string corresponding to the ProgressBar control type.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|<span data-ttu-id="5bc3d-145">Hodnota TRUE</span><span class="sxs-lookup"><span data-stu-id="5bc3d-145">True</span></span>|<span data-ttu-id="5bc3d-146">Ovládací prvek průběh panelu je vždy součástí obsahu zobrazení [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] stromu.</span><span class="sxs-lookup"><span data-stu-id="5bc3d-146">The progress bar control is always included in the content view of the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|<span data-ttu-id="5bc3d-147">Hodnota TRUE</span><span class="sxs-lookup"><span data-stu-id="5bc3d-147">True</span></span>|<span data-ttu-id="5bc3d-148">Ovládací prvek průběh panelu je vždy součástí zobrazení ovládacího prvku [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] stromu.</span><span class="sxs-lookup"><span data-stu-id="5bc3d-148">The progress bar control is always included in the control view of the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree.</span></span>|  
  
<a name="Required_UI_Automation_Control_Patterns_and_Properties"></a>   
## <a name="required-ui-automation-control-patterns-and-properties"></a><span data-ttu-id="5bc3d-149">Požadované vlastnosti a vzory ovládacích prvků automatizace uživatelského rozhraní</span><span class="sxs-lookup"><span data-stu-id="5bc3d-149">Required UI Automation Control Patterns and Properties</span></span>  
 <span data-ttu-id="5bc3d-150">Následující tabulka uvádí [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] řízení vzorů, které jsou potřeba ovládací prvky panelu průběhu podporovat.</span><span class="sxs-lookup"><span data-stu-id="5bc3d-150">The following table lists the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] control patterns required to be supported by progress bar controls.</span></span> <span data-ttu-id="5bc3d-151">Další informace o vzory ovládacích prvků, najdete v části [přehled vzorů ovládacích prvků automatizace uživatelského rozhraní](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md).</span><span class="sxs-lookup"><span data-stu-id="5bc3d-151">For more information on control patterns, see [UI Automation Control Patterns Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md).</span></span>  
  
|<span data-ttu-id="5bc3d-152">Vlastnost vzor nebo vzor ovládacího prvku</span><span class="sxs-lookup"><span data-stu-id="5bc3d-152">Control Pattern/Pattern Property</span></span>|<span data-ttu-id="5bc3d-153">Podpora – hodnota</span><span class="sxs-lookup"><span data-stu-id="5bc3d-153">Support/Value</span></span>|<span data-ttu-id="5bc3d-154">Poznámky</span><span class="sxs-lookup"><span data-stu-id="5bc3d-154">Notes</span></span>|  
|---------------------------------------|--------------------|-----------|  
|<xref:System.Windows.Automation.Provider.IValueProvider>|<span data-ttu-id="5bc3d-155">Závisí</span><span class="sxs-lookup"><span data-stu-id="5bc3d-155">Depends</span></span>|<span data-ttu-id="5bc3d-156">Indikátor průběhu prvky, které umožňují textové informace o průběhu musí implementovat <xref:System.Windows.Automation.Provider.IValueProvider>.</span><span class="sxs-lookup"><span data-stu-id="5bc3d-156">Progress bar controls that give a textual indication of progress must implement <xref:System.Windows.Automation.Provider.IValueProvider>.</span></span>|  
|<xref:System.Windows.Automation.Provider.IValueProvider.IsReadOnly%2A>|<span data-ttu-id="5bc3d-157">Hodnota TRUE</span><span class="sxs-lookup"><span data-stu-id="5bc3d-157">True</span></span>|<span data-ttu-id="5bc3d-158">Hodnota této vlastnosti je vždy hodnotu True.</span><span class="sxs-lookup"><span data-stu-id="5bc3d-158">The value for this property is always True.</span></span>|  
|<xref:System.Windows.Automation.Provider.IValueProvider.Value%2A>|<span data-ttu-id="5bc3d-159">V části poznámky.</span><span class="sxs-lookup"><span data-stu-id="5bc3d-159">See notes.</span></span>|<span data-ttu-id="5bc3d-160">Tato vlastnost zpřístupní textovou průběh ovládací prvek panelu průběhu.</span><span class="sxs-lookup"><span data-stu-id="5bc3d-160">This property exposes textual progress of a progress bar control.</span></span>|  
|<xref:System.Windows.Automation.Provider.IRangeValueProvider>|<span data-ttu-id="5bc3d-161">Závisí</span><span class="sxs-lookup"><span data-stu-id="5bc3d-161">Depends</span></span>|<span data-ttu-id="5bc3d-162">Ovládací prvky panelu průběhu, které provést číselný rozsah musí implementovat.<xref:System.Windows.Automation.Provider.IRangeValueProvider></span><span class="sxs-lookup"><span data-stu-id="5bc3d-162">Progress bar controls that take a numeric range must implement <xref:System.Windows.Automation.Provider.IRangeValueProvider></span></span>|  
|<xref:System.Windows.Automation.Provider.IRangeValueProvider.Minimum%2A>|<span data-ttu-id="5bc3d-163">0.0</span><span class="sxs-lookup"><span data-stu-id="5bc3d-163">0.0</span></span>|<span data-ttu-id="5bc3d-164">Hodnota této vlastnosti je nejmenší hodnotu, která ovládací prvek může být nastaven na.</span><span class="sxs-lookup"><span data-stu-id="5bc3d-164">The value of this property is the smallest value that the control can be set to.</span></span>|  
|<xref:System.Windows.Automation.Provider.IRangeValueProvider.Maximum%2A>|<span data-ttu-id="5bc3d-165">100.0</span><span class="sxs-lookup"><span data-stu-id="5bc3d-165">100.0</span></span>|<span data-ttu-id="5bc3d-166">Hodnota této vlastnosti je největší hodnotu, která ovládací prvek může být nastaven na.</span><span class="sxs-lookup"><span data-stu-id="5bc3d-166">The value of this property is the largest value that the control can be set to.</span></span>|  
|<xref:System.Windows.Automation.Provider.IRangeValueProvider.SmallChange%2A>|<span data-ttu-id="5bc3d-167">NaN</span><span class="sxs-lookup"><span data-stu-id="5bc3d-167">NaN</span></span>|<span data-ttu-id="5bc3d-168">Tato vlastnost není požadovaná, protože ovládací prvky panelu průběhu jsou jen pro čtení.</span><span class="sxs-lookup"><span data-stu-id="5bc3d-168">This property is not required because progress bar controls are read-only.</span></span>|  
|<xref:System.Windows.Automation.Provider.IRangeValueProvider.LargeChange%2A>|<span data-ttu-id="5bc3d-169">NaN</span><span class="sxs-lookup"><span data-stu-id="5bc3d-169">NaN</span></span>|<span data-ttu-id="5bc3d-170">Tato vlastnost není požadovaná, protože ovládací prvky panelu průběhu jsou jen pro čtení.</span><span class="sxs-lookup"><span data-stu-id="5bc3d-170">This property is not required because progress bar controls are read-only.</span></span>|  
  
<a name="Required_UI_Automation_Events"></a>   
## <a name="required-ui-automation-events"></a><span data-ttu-id="5bc3d-171">Události automatizace požadované uživatelského rozhraní</span><span class="sxs-lookup"><span data-stu-id="5bc3d-171">Required UI Automation Events</span></span>  
 <span data-ttu-id="5bc3d-172">Následující tabulka uvádí [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] události potřeba podporovat všechny ovládací prvky panelu průběhu.</span><span class="sxs-lookup"><span data-stu-id="5bc3d-172">The following table lists the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] events required to be supported by all progress bar controls.</span></span> <span data-ttu-id="5bc3d-173">Další informace o událostech najdete v tématu [Přehled událostí automatizace uživatelského rozhraní](../../../docs/framework/ui-automation/ui-automation-events-overview.md).</span><span class="sxs-lookup"><span data-stu-id="5bc3d-173">For more information on events, see [UI Automation Events Overview](../../../docs/framework/ui-automation/ui-automation-events-overview.md).</span></span>  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]<span data-ttu-id="5bc3d-174">Události</span><span class="sxs-lookup"><span data-stu-id="5bc3d-174"> Event</span></span>|<span data-ttu-id="5bc3d-175">Podpora</span><span class="sxs-lookup"><span data-stu-id="5bc3d-175">Support</span></span>|<span data-ttu-id="5bc3d-176">Poznámky</span><span class="sxs-lookup"><span data-stu-id="5bc3d-176">Notes</span></span>|  
|---------------------------------------------------------------------------------|-------------|-----------|  
|<span data-ttu-id="5bc3d-177"><xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>událost změny vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="5bc3d-177"><xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> property-changed event.</span></span>|<span data-ttu-id="5bc3d-178">Požadováno</span><span class="sxs-lookup"><span data-stu-id="5bc3d-178">Required</span></span>|<span data-ttu-id="5bc3d-179">Žádné</span><span class="sxs-lookup"><span data-stu-id="5bc3d-179">None</span></span>|  
|<span data-ttu-id="5bc3d-180"><xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty>událost změny vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="5bc3d-180"><xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> property-changed event.</span></span>|<span data-ttu-id="5bc3d-181">Požadováno</span><span class="sxs-lookup"><span data-stu-id="5bc3d-181">Required</span></span>|<span data-ttu-id="5bc3d-182">Žádné</span><span class="sxs-lookup"><span data-stu-id="5bc3d-182">None</span></span>|  
|<span data-ttu-id="5bc3d-183"><xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty>událost změny vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="5bc3d-183"><xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> property-changed event.</span></span>|<span data-ttu-id="5bc3d-184">Požadováno</span><span class="sxs-lookup"><span data-stu-id="5bc3d-184">Required</span></span>|<span data-ttu-id="5bc3d-185">Žádné</span><span class="sxs-lookup"><span data-stu-id="5bc3d-185">None</span></span>|  
|<span data-ttu-id="5bc3d-186"><xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>událost změny vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="5bc3d-186"><xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty> property-changed event.</span></span>|<span data-ttu-id="5bc3d-187">Požadováno</span><span class="sxs-lookup"><span data-stu-id="5bc3d-187">Required</span></span>|<span data-ttu-id="5bc3d-188">Žádné</span><span class="sxs-lookup"><span data-stu-id="5bc3d-188">None</span></span>|  
|<span data-ttu-id="5bc3d-189"><xref:System.Windows.Automation.ValuePatternIdentifiers.ValueProperty>událost změny vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="5bc3d-189"><xref:System.Windows.Automation.ValuePatternIdentifiers.ValueProperty> property-changed event.</span></span>|<span data-ttu-id="5bc3d-190">Závisí</span><span class="sxs-lookup"><span data-stu-id="5bc3d-190">Depends</span></span>|<span data-ttu-id="5bc3d-191">Žádné</span><span class="sxs-lookup"><span data-stu-id="5bc3d-191">None</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|<span data-ttu-id="5bc3d-192">Požadováno</span><span class="sxs-lookup"><span data-stu-id="5bc3d-192">Required</span></span>|<span data-ttu-id="5bc3d-193">Žádné</span><span class="sxs-lookup"><span data-stu-id="5bc3d-193">None</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|<span data-ttu-id="5bc3d-194">Požadováno</span><span class="sxs-lookup"><span data-stu-id="5bc3d-194">Required</span></span>|<span data-ttu-id="5bc3d-195">Žádné</span><span class="sxs-lookup"><span data-stu-id="5bc3d-195">None</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5bc3d-196">Viz také</span><span class="sxs-lookup"><span data-stu-id="5bc3d-196">See Also</span></span>  
 <xref:System.Windows.Automation.ControlType.ProgressBar>  
 [<span data-ttu-id="5bc3d-197">Přehled typů ovládacích prvků automatizace uživatelského rozhraní</span><span class="sxs-lookup"><span data-stu-id="5bc3d-197">UI Automation Control Types Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-types-overview.md)  
 [<span data-ttu-id="5bc3d-198">Přehled automatizace uživatelského rozhraní</span><span class="sxs-lookup"><span data-stu-id="5bc3d-198">UI Automation Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-overview.md)
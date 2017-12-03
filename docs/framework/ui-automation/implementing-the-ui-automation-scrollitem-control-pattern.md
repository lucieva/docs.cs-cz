---
title: "Implementace vzoru ovládacích prvků ScrollItem pro automatizaci uživatelského rozhraní"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- control patterns, Scroll Item
- UI Automation, Scroll Item control pattern
- Scroll Item control pattern
ms.assetid: 903bab5c-80c1-44d7-bdc2-0a418893b987
caps.latest.revision: "16"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 92c3b4fad775dcd04299e18da126107d8fbb4471
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="implementing-the-ui-automation-scrollitem-control-pattern"></a><span data-ttu-id="26497-102">Implementace vzoru ovládacích prvků ScrollItem pro automatizaci uživatelského rozhraní</span><span class="sxs-lookup"><span data-stu-id="26497-102">Implementing the UI Automation ScrollItem Control Pattern</span></span>
> [!NOTE]
>  <span data-ttu-id="26497-103">Tato dokumentace je určena pro rozhraní .NET Framework vývojáře, kteří chtějí používat spravovanou [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] třídy definované v <xref:System.Windows.Automation> oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="26497-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="26497-104">Nejnovější informace o [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], najdete v části [rozhraní API systému Windows automatizace: automatizace uživatelského rozhraní](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="26497-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="26497-105">Toto téma představuje pokyny a konvence pro implementaci <xref:System.Windows.Automation.Provider.IScrollItemProvider>, včetně informací o události, vlastnosti a metody.</span><span class="sxs-lookup"><span data-stu-id="26497-105">This topic introduces guidelines and conventions for implementing the <xref:System.Windows.Automation.Provider.IScrollItemProvider>, including information about properties, methods, and events.</span></span> <span data-ttu-id="26497-106">Na konci tohoto tématu jsou uvedeny odkazy na další odkazy.</span><span class="sxs-lookup"><span data-stu-id="26497-106">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="26497-107"><xref:System.Windows.Automation.ScrollItemPattern> – Vzor ovládacích prvků se používá pro podporu jednotlivých podřízených ovládacích prvků kontejnerů, které implementují <xref:System.Windows.Automation.Provider.IScrollProvider>.</span><span class="sxs-lookup"><span data-stu-id="26497-107">The <xref:System.Windows.Automation.ScrollItemPattern> control pattern is used to support individual child controls of containers that implement <xref:System.Windows.Automation.Provider.IScrollProvider>.</span></span> <span data-ttu-id="26497-108">Tento vzor ovládacích prvků funguje jako komunikační kanál mezi podřízený ovládací prvek a jeho kontejner, aby bylo zajištěno, že kontejneru můžete měnit aktuálně viditelný obsah (nebo oblast) v rámci jeho zobrazení zobrazíte podřízený ovládací prvek.</span><span class="sxs-lookup"><span data-stu-id="26497-108">This control pattern acts as a communication channel between a child control and its container to ensure that the container can change the currently visible content (or region) within its viewport to display the child control.</span></span> <span data-ttu-id="26497-109">Příklady ovládacích prvků, které implementují tento vzor ovládacích prvků najdete v tématu [řízení vzor mapování pro klienty automatizace uživatelského rozhraní](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="26497-109">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="26497-110">Postup implementace a konvence</span><span class="sxs-lookup"><span data-stu-id="26497-110">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="26497-111">Při implementaci položky posuv – vzor ovládacích prvků, poznamenejte si následující pokyny a konvence:</span><span class="sxs-lookup"><span data-stu-id="26497-111">When implementing the Scroll Item control pattern, note the following guidelines and conventions:</span></span>  
  
-   <span data-ttu-id="26497-112">Implementace rozhraní IScrollItemProvider nejsou povinné položky v ovládacím prvku okno nebo plátno.</span><span class="sxs-lookup"><span data-stu-id="26497-112">Items contained within a Window or Canvas control are not required to implement the IScrollItemProvider interface.</span></span> <span data-ttu-id="26497-113">Jako alternativu, ale, že musí vystavit platné umístění pro <xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>.</span><span class="sxs-lookup"><span data-stu-id="26497-113">As an alternative, however, they must expose a valid location for the <xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>.</span></span> <span data-ttu-id="26497-114">To vám umožní automatizace uživatelského rozhraní klientské aplikace používat <xref:System.Windows.Automation.ScrollPattern> řídit vzor metody na kontejneru zobrazíte podřízenou položku.</span><span class="sxs-lookup"><span data-stu-id="26497-114">This will allow a UI Automation client application to use the <xref:System.Windows.Automation.ScrollPattern> control pattern methods on the container to display the child item.</span></span>  
  
<a name="Required_Members_for_IScrollItemProvider"></a>   
## <a name="required-members-for-iscrollitemprovider"></a><span data-ttu-id="26497-115">Požadované členy pro IScrollItemProvider</span><span class="sxs-lookup"><span data-stu-id="26497-115">Required Members for IScrollItemProvider</span></span>  
 <span data-ttu-id="26497-116">Je vyžadována pro implementaci rozhraní IScrollProvider následující metoda.</span><span class="sxs-lookup"><span data-stu-id="26497-116">The following method is required for implementing the IScrollProvider interface.</span></span>  
  
|<span data-ttu-id="26497-117">Požadované členy</span><span class="sxs-lookup"><span data-stu-id="26497-117">Required members</span></span>|<span data-ttu-id="26497-118">Typ člena</span><span class="sxs-lookup"><span data-stu-id="26497-118">Member type</span></span>|<span data-ttu-id="26497-119">Poznámky</span><span class="sxs-lookup"><span data-stu-id="26497-119">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IScrollItemProvider.ScrollIntoView%2A>|<span data-ttu-id="26497-120">– Metoda</span><span class="sxs-lookup"><span data-stu-id="26497-120">-   Method</span></span>|<span data-ttu-id="26497-121">Žádné</span><span class="sxs-lookup"><span data-stu-id="26497-121">None</span></span>|  
  
 <span data-ttu-id="26497-122">Tento vzor ovládacích prvků nemá žádné přidružené vlastnosti nebo události.</span><span class="sxs-lookup"><span data-stu-id="26497-122">This control pattern has no associated properties or events.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="26497-123">Výjimky</span><span class="sxs-lookup"><span data-stu-id="26497-123">Exceptions</span></span>  
 <span data-ttu-id="26497-124">Zprostředkovatelé musí throw následující výjimky.</span><span class="sxs-lookup"><span data-stu-id="26497-124">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="26497-125">Typ výjimky</span><span class="sxs-lookup"><span data-stu-id="26497-125">Exception Type</span></span>|<span data-ttu-id="26497-126">Podmínka</span><span class="sxs-lookup"><span data-stu-id="26497-126">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<span data-ttu-id="26497-127">Pokud položku nelze přesunut do zobrazení oblasti:</span><span class="sxs-lookup"><span data-stu-id="26497-127">If an item cannot be scrolled into view:</span></span><br /><br /> -   <xref:System.Windows.Automation.ScrollItemPattern.ScrollIntoView%2A>|  
  
## <a name="see-also"></a><span data-ttu-id="26497-128">Viz také</span><span class="sxs-lookup"><span data-stu-id="26497-128">See Also</span></span>  
 [<span data-ttu-id="26497-129">Přehled vzorů ovládacích prvků automatizace uživatelského rozhraní</span><span class="sxs-lookup"><span data-stu-id="26497-129">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [<span data-ttu-id="26497-130">Podpora vzorů ovládacích prvků u zprostředkovatele automatizace uživatelského rozhraní</span><span class="sxs-lookup"><span data-stu-id="26497-130">Support Control Patterns in a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)  
 [<span data-ttu-id="26497-131">Vzory ovládacího prvku automatizace uživatelského rozhraní pro klienty</span><span class="sxs-lookup"><span data-stu-id="26497-131">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [<span data-ttu-id="26497-132">Přehled stromu automatizace uživatelského rozhraní</span><span class="sxs-lookup"><span data-stu-id="26497-132">UI Automation Tree Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
 [<span data-ttu-id="26497-133">Použití mezipaměti při automatizaci uživatelského rozhraní</span><span class="sxs-lookup"><span data-stu-id="26497-133">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
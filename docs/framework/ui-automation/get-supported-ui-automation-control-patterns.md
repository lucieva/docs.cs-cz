---
title: "Získání podporovaných vzorů ovládacích prvků pro automatizaci uživatelského rozhraní"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- control patterns, getting
- UI Automation, getting control patterns
- getting, control patterns
ms.assetid: 006c54c9-50bf-48d9-a855-9d62eb95603a
caps.latest.revision: "10"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 8917890d86f059d85ad9b6a0bcf6d9a41d65585a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="get-supported-ui-automation-control-patterns"></a><span data-ttu-id="6062f-102">Získání podporovaných vzorů ovládacích prvků pro automatizaci uživatelského rozhraní</span><span class="sxs-lookup"><span data-stu-id="6062f-102">Get Supported UI Automation Control Patterns</span></span>
> [!NOTE]
>  <span data-ttu-id="6062f-103">Tato dokumentace je určena pro rozhraní .NET Framework vývojáře, kteří chtějí používat spravovanou [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] třídy definované v <xref:System.Windows.Automation> oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="6062f-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="6062f-104">Nejnovější informace o [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], najdete v části [rozhraní API systému Windows automatizace: automatizace uživatelského rozhraní](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="6062f-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="6062f-105">Toto téma ukazuje, jak načíst objekty vzor ovládací prvek z [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] elementy.</span><span class="sxs-lookup"><span data-stu-id="6062f-105">This topic shows how to retrieve control pattern objects from [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] elements.</span></span>  
  
### <a name="obtain-all-control-patterns"></a><span data-ttu-id="6062f-106">Získání všech vzory ovládacích prvků</span><span class="sxs-lookup"><span data-stu-id="6062f-106">Obtain All Control Patterns</span></span>  
  
1.  <span data-ttu-id="6062f-107">Získat <xref:System.Windows.Automation.AutomationElement> vzorů jejichž ovládacích prvků, které zajímá.</span><span class="sxs-lookup"><span data-stu-id="6062f-107">Get the <xref:System.Windows.Automation.AutomationElement> whose control patterns you are interested in.</span></span>  
  
2.  <span data-ttu-id="6062f-108">Volání <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A> k získání všech vzorů ovládacích prvků z elementu.</span><span class="sxs-lookup"><span data-stu-id="6062f-108">Call <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A> to get all control patterns from the element.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="6062f-109">Důrazně doporučujeme, klient nepoužívali <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>.</span><span class="sxs-lookup"><span data-stu-id="6062f-109">It is strongly recommended that a client not use <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>.</span></span> <span data-ttu-id="6062f-110">Výkon může být vážně ohrožené jako tato metoda volá <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> interně pro každý existující vzor ovládacích prvků.</span><span class="sxs-lookup"><span data-stu-id="6062f-110">Performance can be severely affected as this method calls <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> internally for each existing control pattern.</span></span> <span data-ttu-id="6062f-111">Pokud je to možné, by měly volat klienta <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> klíče vzorů, které vás zajímají.</span><span class="sxs-lookup"><span data-stu-id="6062f-111">If possible, a client should call <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> for the key patterns of interest.</span></span>  
  
### <a name="obtain-a-specific-control-pattern"></a><span data-ttu-id="6062f-112">Získat vzor konkrétní ovládacích prvků</span><span class="sxs-lookup"><span data-stu-id="6062f-112">Obtain a Specific Control Pattern</span></span>  
  
1.  <span data-ttu-id="6062f-113">Získat <xref:System.Windows.Automation.AutomationElement> vzorů jejichž ovládacích prvků, které zajímá.</span><span class="sxs-lookup"><span data-stu-id="6062f-113">Get the <xref:System.Windows.Automation.AutomationElement> whose control patterns you are interested in.</span></span>  
  
2.  <span data-ttu-id="6062f-114">Volání <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> nebo <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> dotazu pro konkrétní vzor.</span><span class="sxs-lookup"><span data-stu-id="6062f-114">Call <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> or <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> to query for a specific pattern.</span></span> <span data-ttu-id="6062f-115">Tyto metody jsou podobné, ale pokud není nalezen vzor, <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> vyvolá výjimku, a <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> vrátí `false`.</span><span class="sxs-lookup"><span data-stu-id="6062f-115">These methods are similar, but if the pattern is not found, <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> raises an exception, and <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> returns `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6062f-116">Příklad</span><span class="sxs-lookup"><span data-stu-id="6062f-116">Example</span></span>  
 <span data-ttu-id="6062f-117">Následující příklad načte <xref:System.Windows.Automation.AutomationElement> položky seznamu a získává <xref:System.Windows.Automation.SelectionItemPattern> z tohoto prvku.</span><span class="sxs-lookup"><span data-stu-id="6062f-117">The following example retrieves an <xref:System.Windows.Automation.AutomationElement> for a list item and obtains a <xref:System.Windows.Automation.SelectionItemPattern> from that element.</span></span>  
  
 [!code-csharp[UIAClient_snip#103](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#103)]
 [!code-vb[UIAClient_snip#103](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#103)]  
  
## <a name="see-also"></a><span data-ttu-id="6062f-118">Viz také</span><span class="sxs-lookup"><span data-stu-id="6062f-118">See Also</span></span>  
 [<span data-ttu-id="6062f-119">Vzory ovládacího prvku automatizace uživatelského rozhraní pro klienty</span><span class="sxs-lookup"><span data-stu-id="6062f-119">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
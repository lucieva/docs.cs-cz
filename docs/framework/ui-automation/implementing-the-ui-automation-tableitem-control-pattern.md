---
title: Implementace vzoru ovládacích prvků TableItem pro automatizaci uživatelského rozhraní
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Table Item
- UI Automation, Table Item control pattern
- TableItem control pattern
ms.assetid: ac178408-1485-436f-8d3e-eee3bf80cb24
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: e5d5e82c5c2cfc48c98559bd6ce14519bdfaa522
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/26/2018
ms.locfileid: "47196554"
---
# <a name="implementing-the-ui-automation-tableitem-control-pattern"></a>Implementace vzoru ovládacích prvků TableItem pro automatizaci uživatelského rozhraní
> [!NOTE]
>  Tato dokumentace je určená pro vývojáře rozhraní .NET Framework, kteří chtějí používat spravovanou [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tříd definovaných v <xref:System.Windows.Automation> oboru názvů. Nejnovější informace o [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], naleznete v tématu [Windows Automation API: automatizace uživatelského rozhraní](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Toto téma popisuje pravidla a zásady pro implementaci <xref:System.Windows.Automation.Provider.ITableItemProvider>, včetně informací o události a vlastnosti. Odkazy na další odkazy jsou uvedeny na konci přehledu.  
  
 <xref:System.Windows.Automation.TableItemPattern> – Vzor ovládacích prvků slouží k podpoře podřízené ovládací prvky kontejnerů, které implementují <xref:System.Windows.Automation.Provider.ITableProvider>. Poskytuje přístup k funkcím jednotlivé buňky vyžaduje souběžné provádění <xref:System.Windows.Automation.Provider.IGridItemProvider>. Tento vzor ovládacích prvků je obdobou <xref:System.Windows.Automation.Provider.IGridItemProvider> s rozlišovat, že žádné řídicí implementace <xref:System.Windows.Automation.Provider.ITableItemProvider> musí zveřejnit prostřednictvím kódu programu vztah mezi jednotlivé buňky a její informace řádků a sloupců. Příklady ovládacích prvků, které tento ovládací prvek model implementovat, najdete v článku [ovládací prvek vzor mapování pro klienty automatizace uživatelského rozhraní](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a>Pokyny pro implementaci a konvence  
  
-   Funkci související mřížce položky, naleznete v tématu [implementace vzoru ovládacích prvků GridItem pro automatizaci uživatelského rozhraní](../../../docs/framework/ui-automation/implementing-the-ui-automation-griditem-control-pattern.md).  
  
<a name="Required_Members_for_ITableItemProvider"></a>   
## <a name="required-members-for-itableitemprovider"></a>Požadované členy pro ITableItemProvider  
  
|Povinný člen|Typ člena|Poznámky|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.ITableItemProvider.GetColumnHeaderItems%2A>|Metoda|Žádné|  
|<xref:System.Windows.Automation.Provider.ITableItemProvider.GetRowHeaderItems%2A>|Metoda|Žádné|  
  
 Tento model ovládací prvek nemá žádné přidružené vlastnosti a události.  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a>Výjimky  
 Tento model ovládací prvek nemá žádné související výjimky.  
  
## <a name="see-also"></a>Viz také  
 [Přehled vzorů ovládacích prvků pro automatizaci uživatelského rozhraní](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [Podpora vzorů ovládacích prvků u zprostředkovatele automatizace uživatelského rozhraní](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)  
 [Vzory ovládacích prvků automatizace uživatelského rozhraní pro klienty](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [Implementace vzoru ovládacích prvků tabulka pro automatizaci uživatelského rozhraní](../../../docs/framework/ui-automation/implementing-the-ui-automation-table-control-pattern.md)  
 [Implementace vzoru ovládacích prvků GridItem pro automatizaci uživatelského rozhraní](../../../docs/framework/ui-automation/implementing-the-ui-automation-griditem-control-pattern.md)  
 [Přehled stromu automatizace uživatelského rozhraní](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
 [Použití mezipaměti při automatizaci uživatelského rozhraní](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)

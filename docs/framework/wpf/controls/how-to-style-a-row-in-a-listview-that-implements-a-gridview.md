---
title: 'Postupy: Nastavení stylu řádku v zobrazení ListView s implementací GridView'
ms.date: 03/30/2017
helpviewer_keywords:
- GridView controls [WPF], styling rows
- styling rows in ListViews implementing GridViews [WPF]
- ListView controls [WPF], styling rows with GridViews
ms.assetid: 2e406ba2-70a0-4e62-841f-0934859de76e
ms.openlocfilehash: 313ead6de45f2a137775adb0ad9aad8bd061c066
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/04/2018
ms.locfileid: "33555194"
---
# <a name="how-to-style-a-row-in-a-listview-that-implements-a-gridview"></a>Postupy: Nastavení stylu řádku v zobrazení ListView s implementací GridView
Tento příklad ukazuje, jak k úpravě stylu řádku <xref:System.Windows.Controls.ListView> ovládací prvek, který implementuje <xref:System.Windows.Controls.GridView> <xref:System.Windows.Controls.ListView.View%2A> režimu.  
  
## <a name="example"></a>Příklad  
 Můžete styl řádku <xref:System.Windows.Controls.ListView> ovládací prvek pro nastavení <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> na <xref:System.Windows.Controls.ListView> ovládacího prvku. Nastavení stylu pro jeho položky, které jsou reprezentovány jako <xref:System.Windows.Controls.ListViewItem> objekty. <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> Odkazy <xref:System.Windows.Controls.ControlTemplate> objekty, které se používají k zobrazení obsahu řádek.  
  
 Je kompletní ukázka v následujících příkladech se extrahují z, zobrazí kolekce skladbu informací, které jsou uloženy v [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] databáze. Skladeb v databázi obsahuje pole, hodnocení a hodnotu tohoto pole určuje způsob zobrazení řádek skladbu informace.  
  
 Následující příklad ukazuje, jak definovat <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> pro <xref:System.Windows.Controls.ListViewItem> objekty, které představují skladeb v kolekci skladbu. <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> Odkazy <xref:System.Windows.Controls.ControlTemplate> objekty, které určují, jak zobrazit řádek skladbu informace.  
  
 [!code-xaml[ListViewItemStyleSnippet#ItemContainerStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#itemcontainerstyle)]  
  
 Následující příklad ukazuje <xref:System.Windows.Controls.ControlTemplate> doplňuje textový řetězec `"Strongly Recommended"` na řádek. Tato šablona odkazuje <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> a zobrazí, když na skladbu hodnocení má hodnotu 5 (5). <xref:System.Windows.Controls.ControlTemplate> Zahrnuje <xref:System.Windows.Controls.GridViewRowPresenter> objekt, který nastaví rozložení obsahu řádku ve sloupcích podle definice <xref:System.Windows.Controls.GridView> režimu zobrazení.  
  
 [!code-xaml[ListViewItemStyleSnippet#ControlTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#controltemplate)]  
  
 V následujícím příkladu definuje <xref:System.Windows.Controls.GridView>.  
  
 [!code-xaml[ListViewItemStyleSnippet#GridView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#gridview)]  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [Témata s postupy](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [ListView – přehled](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [Styly a šablony](../../../../docs/framework/wpf/controls/styling-and-templating.md)

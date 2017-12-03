---
title: "Postupy: Změna vodorovného zarovnání sloupce v objektu ListView"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: ListView controls [WPF], horizontal alignment [WPF]
ms.assetid: b9573e44-9dad-4d14-939c-7859ca372758
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3ed163de9a5b01a3ddab8ef42d21f38d35f48519
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-change-the-horizontal-alignment-of-a-column-in-a-listview"></a><span data-ttu-id="18008-102">Postupy: Změna vodorovného zarovnání sloupce v objektu ListView</span><span class="sxs-lookup"><span data-stu-id="18008-102">How to: Change the Horizontal Alignment of a Column in a ListView</span></span>
<span data-ttu-id="18008-103">Ve výchozím nastavení, obsah každý sloupec v <xref:System.Windows.Controls.ListViewItem> zarovnán vlevo.</span><span class="sxs-lookup"><span data-stu-id="18008-103">By default, the content of each column in a <xref:System.Windows.Controls.ListViewItem> is left-aligned.</span></span> <span data-ttu-id="18008-104">Zarovnání každý sloupec můžete změnit zadáním <xref:System.Windows.DataTemplate> a nastavení <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> vlastnost v elementu v rámci <xref:System.Windows.DataTemplate>.</span><span class="sxs-lookup"><span data-stu-id="18008-104">You can change the alignment of each column by providing a <xref:System.Windows.DataTemplate> and setting the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property on the element within the <xref:System.Windows.DataTemplate>.</span></span> <span data-ttu-id="18008-105">Toto téma ukazuje, jak <xref:System.Windows.Controls.ListView> zarovnává jeho obsah ve výchozím nastavení a postup změny zarovnání jeden sloupec ve <xref:System.Windows.Controls.ListView>.</span><span class="sxs-lookup"><span data-stu-id="18008-105">This topic shows how a <xref:System.Windows.Controls.ListView> aligns its content by default and how to change the alignment of one column in a <xref:System.Windows.Controls.ListView>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="18008-106">Příklad</span><span class="sxs-lookup"><span data-stu-id="18008-106">Example</span></span>  
 <span data-ttu-id="18008-107">V následujícím příkladu, data v `Title` a `ISBN` sloupce je zarovnaný doleva.</span><span class="sxs-lookup"><span data-stu-id="18008-107">In the following example, the data in the `Title` and `ISBN` columns is left-aligned.</span></span>  
  
 [!code-xaml[ListViewHowTos#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="18008-108">Chcete-li změnit zarovnání `ISBN` sloupec, musíte určit, že <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> vlastnost jednotlivých <xref:System.Windows.Controls.ListViewItem> je <xref:System.Windows.HorizontalAlignment.Stretch>tak, aby elementy v každé <xref:System.Windows.Controls.ListViewItem> může mít rozsah nebo být umístěny podél celého šířka každého sloupce.</span><span class="sxs-lookup"><span data-stu-id="18008-108">To change the alignment of the `ISBN` column, you need to specify that the <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> property of each <xref:System.Windows.Controls.ListViewItem> is <xref:System.Windows.HorizontalAlignment.Stretch>, so that the elements in each <xref:System.Windows.Controls.ListViewItem> can span or be positioned along the entire width of each column.</span></span> <span data-ttu-id="18008-109">Protože <xref:System.Windows.Controls.ListView> je vázán na zdroj dat, budete muset vytvořit styl, který nastaví <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>.</span><span class="sxs-lookup"><span data-stu-id="18008-109">Because the <xref:System.Windows.Controls.ListView> is bound to a data source, you need to create a style that sets the <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>.</span></span> <span data-ttu-id="18008-110">Potom budete muset použít <xref:System.Windows.DataTemplate> k zobrazení obsahu místo použití <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> vlastnost.</span><span class="sxs-lookup"><span data-stu-id="18008-110">Next, you need to use a <xref:System.Windows.DataTemplate> to display the content instead of using the <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> property.</span></span> <span data-ttu-id="18008-111">K zobrazení `ISBN` každé šablony <xref:System.Windows.DataTemplate> může obsahovat jenom <xref:System.Windows.Controls.TextBlock> s jeho <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> vlastnost nastavena na hodnotu <xref:System.Windows.HorizontalAlignment.Right>.</span><span class="sxs-lookup"><span data-stu-id="18008-111">To display the `ISBN` of each template, the <xref:System.Windows.DataTemplate> can just contain a <xref:System.Windows.Controls.TextBlock> that has its <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property set to <xref:System.Windows.HorizontalAlignment.Right>.</span></span>  
  
 <span data-ttu-id="18008-112">V následujícím příkladu definuje styl a <xref:System.Windows.DataTemplate> nezbytné provést `ISBN` sloupec doprava a změny <xref:System.Windows.Controls.GridViewColumn> k odkazu <xref:System.Windows.DataTemplate>.</span><span class="sxs-lookup"><span data-stu-id="18008-112">The following example defines the style and <xref:System.Windows.DataTemplate> necessary to make the `ISBN` column right-aligned, and changes the <xref:System.Windows.Controls.GridViewColumn> to reference the <xref:System.Windows.DataTemplate>.</span></span>  
  
 [!code-xaml[ListViewHowTos#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#3)]  
[!code-xaml[ListViewHowTos#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#4)]  
  
## <a name="see-also"></a><span data-ttu-id="18008-113">Viz také</span><span class="sxs-lookup"><span data-stu-id="18008-113">See Also</span></span>  
 [<span data-ttu-id="18008-114">Přehled vazba dat</span><span class="sxs-lookup"><span data-stu-id="18008-114">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="18008-115">Ukázka dat – přehled</span><span class="sxs-lookup"><span data-stu-id="18008-115">Data Templating Overview</span></span>](../../../../docs/framework/wpf/data/data-templating-overview.md)  
 [<span data-ttu-id="18008-116">Vytvoření vazby na Data XML pomocí XMLDataProvider a dotazy jazyka XPath</span><span class="sxs-lookup"><span data-stu-id="18008-116">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)  
 [<span data-ttu-id="18008-117">ListView – přehled</span><span class="sxs-lookup"><span data-stu-id="18008-117">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)
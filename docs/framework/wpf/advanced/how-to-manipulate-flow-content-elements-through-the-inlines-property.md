---
title: "Postupy: Zpracování elementů obsahu toku prostřednictvím vlastnosti Inlines"
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
helpviewer_keywords:
- flow content elements [WPF], manipulating through Inlines property
- documents [WPF], manipulating flow Content elements through Inlines property
- Inlines property [WPF], manipulating flow Content elements
- properties [WPF], Inlines [WPF], manipulating flow Content elements
ms.assetid: 510780d2-3da1-4360-8763-7054bda22ea3
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 77b6d75b48fd137092600a7e2316cbcf7099de76
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-manipulate-flow-content-elements-through-the-inlines-property"></a><span data-ttu-id="2bfe2-102">Postupy: Zpracování elementů obsahu toku prostřednictvím vlastnosti Inlines</span><span class="sxs-lookup"><span data-stu-id="2bfe2-102">How to: Manipulate Flow Content Elements through the Inlines Property</span></span>
<span data-ttu-id="2bfe2-103">Tyto příklady ukazují některé z nejčastěji operací, které lze provést u vložených elementů obsahu tok (a kontejnerů, které z těchto prvků, jako <xref:System.Windows.Controls.TextBlock>) prostřednictvím **Inlines** vlastnost.</span><span class="sxs-lookup"><span data-stu-id="2bfe2-103">These examples demonstrate some of the more common operations that can be performed on inline flow content elements (and containers of such elements, such as <xref:System.Windows.Controls.TextBlock>) through the **Inlines** property.</span></span> <span data-ttu-id="2bfe2-104">Tato vlastnost se používá k přidání a odebrání položek z <xref:System.Windows.Documents.InlineCollection>.</span><span class="sxs-lookup"><span data-stu-id="2bfe2-104">This property is used to add and remove items from <xref:System.Windows.Documents.InlineCollection>.</span></span> <span data-ttu-id="2bfe2-105">Tok obsahu elementy tuto funkci **Inlines** vlastnost patří:</span><span class="sxs-lookup"><span data-stu-id="2bfe2-105">Flow content elements that feature an **Inlines** property include:</span></span>  
  
-   <xref:System.Windows.Documents.Bold>  
  
-   <xref:System.Windows.Documents.Hyperlink>  
  
-   <xref:System.Windows.Documents.Italic>  
  
-   <xref:System.Windows.Documents.Paragraph>  
  
-   <xref:System.Windows.Documents.Span>  
  
-   <xref:System.Windows.Documents.Underline>  
  
 <span data-ttu-id="2bfe2-106">Tyto příklady dojít používat <xref:System.Windows.Documents.Span> jako tok obsahu elementu, ale tyto postupy platí pro všechny elementy nebo ovládací prvky, které jsou hostiteli <xref:System.Windows.Documents.InlineCollection> kolekce.</span><span class="sxs-lookup"><span data-stu-id="2bfe2-106">These examples happen to use <xref:System.Windows.Documents.Span> as the flow content element, but these techniques are applicable to all elements or controls that host an <xref:System.Windows.Documents.InlineCollection> collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2bfe2-107">Příklad</span><span class="sxs-lookup"><span data-stu-id="2bfe2-107">Example</span></span>  
 <span data-ttu-id="2bfe2-108">Následující příklad vytvoří novou <xref:System.Windows.Documents.Span> objekt a používá **přidat** metoda pro přidání textu se spouští jako obsahu podřízené objekty <xref:System.Windows.Documents.Span>.</span><span class="sxs-lookup"><span data-stu-id="2bfe2-108">The following example creates a new <xref:System.Windows.Documents.Span> object, and then uses the **Add** method to add two text runs as content children of the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesAdd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesadd)]
 [!code-vb[SpanSnippets#_SpanInlinesAdd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesadd)]  
  
## <a name="example"></a><span data-ttu-id="2bfe2-109">Příklad</span><span class="sxs-lookup"><span data-stu-id="2bfe2-109">Example</span></span>  
 <span data-ttu-id="2bfe2-110">Následující příklad vytvoří novou <xref:System.Windows.Documents.Run> elementu a vloží ho od začátku <xref:System.Windows.Documents.Span>.</span><span class="sxs-lookup"><span data-stu-id="2bfe2-110">The following example creates a new <xref:System.Windows.Documents.Run> element and inserts it at the beginning of the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesInsert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesinsert)]
 [!code-vb[SpanSnippets#_SpanInlinesInsert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesinsert)]  
  
## <a name="example"></a><span data-ttu-id="2bfe2-111">Příklad</span><span class="sxs-lookup"><span data-stu-id="2bfe2-111">Example</span></span>  
 <span data-ttu-id="2bfe2-112">Získá počet nejvyšší úrovně v následujícím příkladu <xref:System.Windows.Documents.Inline> elementů obsažených v <xref:System.Windows.Documents.Span>.</span><span class="sxs-lookup"><span data-stu-id="2bfe2-112">The following example gets the number of top-level <xref:System.Windows.Documents.Inline> elements contained in the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesCount](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinescount)]
 [!code-vb[SpanSnippets#_SpanInlinesCount](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinescount)]  
  
## <a name="example"></a><span data-ttu-id="2bfe2-113">Příklad</span><span class="sxs-lookup"><span data-stu-id="2bfe2-113">Example</span></span>  
 <span data-ttu-id="2bfe2-114">Následující příklad odstraní poslední <xref:System.Windows.Documents.Inline> element v <xref:System.Windows.Documents.Span>.</span><span class="sxs-lookup"><span data-stu-id="2bfe2-114">The following example deletes the last <xref:System.Windows.Documents.Inline> element in the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
## <a name="example"></a><span data-ttu-id="2bfe2-115">Příklad</span><span class="sxs-lookup"><span data-stu-id="2bfe2-115">Example</span></span>  
 <span data-ttu-id="2bfe2-116">Následující příklad odebere všechny obsahu (<xref:System.Windows.Documents.Inline> elementy) z <xref:System.Windows.Documents.Span>.</span><span class="sxs-lookup"><span data-stu-id="2bfe2-116">The following example clears all of the contents (<xref:System.Windows.Documents.Inline> elements) from the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
## <a name="see-also"></a><span data-ttu-id="2bfe2-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="2bfe2-117">See Also</span></span>  
 <xref:System.Windows.Documents.BlockCollection>  
 <xref:System.Windows.Documents.InlineCollection>  
 <xref:System.Windows.Documents.ListItemCollection>  
 [<span data-ttu-id="2bfe2-118">Přehled toku dokumentu</span><span class="sxs-lookup"><span data-stu-id="2bfe2-118">Flow Document Overview</span></span>](../../../../docs/framework/wpf/advanced/flow-document-overview.md)  
 [<span data-ttu-id="2bfe2-119">Manipulace s FlowDocument prostřednictvím vlastnosti bloky</span><span class="sxs-lookup"><span data-stu-id="2bfe2-119">Manipulate a FlowDocument through the Blocks Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-a-flowdocument-through-the-blocks-property.md)  
 [<span data-ttu-id="2bfe2-120">Manipulace se sloupci tabulky pomocí vlastnosti sloupce</span><span class="sxs-lookup"><span data-stu-id="2bfe2-120">Manipulate a Table's Columns through the Columns Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-columns-through-the-columns-property.md)  
 [<span data-ttu-id="2bfe2-121">Manipulaci se skupinami řádek tabulky pomocí vlastnosti RowGroups</span><span class="sxs-lookup"><span data-stu-id="2bfe2-121">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
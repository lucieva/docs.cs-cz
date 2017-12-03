---
title: "Postupy: Seskupení položek v ovládacím prvku Windows Forms ListView"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], grouping items
- lists [Windows Forms], grouping items
- grouping
- list views [Windows Forms], grouping items
- groups
- groups [Windows Forms], in Windows Forms controls
ms.assetid: 610416a1-8da4-436c-af19-5f19e654769b
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c22134513c2c6a3ff2bc621e68f546b7bcc93ba9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control"></a><span data-ttu-id="68b8b-102">Postupy: Seskupení položek v ovládacím prvku Windows Forms ListView</span><span class="sxs-lookup"><span data-stu-id="68b8b-102">How to: Group Items in a Windows Forms ListView Control</span></span>
<span data-ttu-id="68b8b-103">Funkce k seskupení <xref:System.Windows.Forms.ListView> ovládací prvek, můžete zobrazit související sady položek ve skupinách.</span><span class="sxs-lookup"><span data-stu-id="68b8b-103">With the grouping feature of the <xref:System.Windows.Forms.ListView> control, you can display related sets of items in groups.</span></span> <span data-ttu-id="68b8b-104">Tyto skupiny jsou oddělené na obrazovce podle hlaviček vodorovné skupiny, které obsahují názvy skupiny.</span><span class="sxs-lookup"><span data-stu-id="68b8b-104">These groups are separated on the screen by horizontal group headers that contain the group titles.</span></span> <span data-ttu-id="68b8b-105">Můžete použít <xref:System.Windows.Forms.ListView> skupiny, aby bylo navigace velké seznamy jednodušší podle abecedy, seskupení položek podle data, nebo pomocí jiné logické seskupení.</span><span class="sxs-lookup"><span data-stu-id="68b8b-105">You can use <xref:System.Windows.Forms.ListView> groups to make navigating large lists easier by grouping items alphabetically, by date, or by any other logical grouping.</span></span> <span data-ttu-id="68b8b-106">Následující obrázek ukazuje některé seskupené položky.</span><span class="sxs-lookup"><span data-stu-id="68b8b-106">The following image shows some grouped items.</span></span>  
  
 <span data-ttu-id="68b8b-107">![ListView skupiny](../../../../docs/framework/winforms/controls/media/listviewgroups.gif "ListViewGroups")</span><span class="sxs-lookup"><span data-stu-id="68b8b-107">![ListView Groups](../../../../docs/framework/winforms/controls/media/listviewgroups.gif "ListViewGroups")</span></span>  
<span data-ttu-id="68b8b-108">ListView seskupeny položky</span><span class="sxs-lookup"><span data-stu-id="68b8b-108">ListView grouped items</span></span>  
  
 <span data-ttu-id="68b8b-109">Pokud chcete povolit seskupování, musíte nejdřív vytvořit jeden nebo více skupin v Návrháři nebo prostřednictvím kódu programu.</span><span class="sxs-lookup"><span data-stu-id="68b8b-109">To enable grouping, you must first create one or more groups either in the designer or programmatically.</span></span> <span data-ttu-id="68b8b-110">Po definování skupiny, můžete přiřadit <xref:System.Windows.Forms.ListView> položky do skupiny.</span><span class="sxs-lookup"><span data-stu-id="68b8b-110">After a group has been defined, you can assign <xref:System.Windows.Forms.ListView> items to groups.</span></span> <span data-ttu-id="68b8b-111">Také můžete přesunout položky z jedné skupiny do jiné prostřednictvím kódu programu.</span><span class="sxs-lookup"><span data-stu-id="68b8b-111">You can also move items from one group to another programmatically.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="68b8b-112"><xref:System.Windows.Forms.ListView>skupiny jsou k dispozici pouze na [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] Pokud aplikace zavolá <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> metoda.</span><span class="sxs-lookup"><span data-stu-id="68b8b-112"><xref:System.Windows.Forms.ListView> groups are available only on [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] when your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="68b8b-113">V dřívějších operačních systémech žádný kód týkající se skupiny nemá žádný vliv a skupin nebude zobrazovat.</span><span class="sxs-lookup"><span data-stu-id="68b8b-113">On earlier operating systems, any code relating to groups has no effect and the groups will not appear.</span></span> <span data-ttu-id="68b8b-114">Další informace naleznete v tématu <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="68b8b-114">For more information, see <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>.</span></span>  
  
### <a name="to-add-groups"></a><span data-ttu-id="68b8b-115">Přidání skupin</span><span class="sxs-lookup"><span data-stu-id="68b8b-115">To add groups</span></span>  
  
1.  <span data-ttu-id="68b8b-116">Použití <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> metodu <xref:System.Windows.Forms.ListView.Groups%2A> kolekce.</span><span class="sxs-lookup"><span data-stu-id="68b8b-116">Use the <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> method of the <xref:System.Windows.Forms.ListView.Groups%2A> collection.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#21)]  
  
### <a name="to-remove-groups"></a><span data-ttu-id="68b8b-117">Chcete-li odebrat skupiny</span><span class="sxs-lookup"><span data-stu-id="68b8b-117">To remove groups</span></span>  
  
1.  <span data-ttu-id="68b8b-118">Použití <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> nebo <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> metodu <xref:System.Windows.Forms.ListView.Groups%2A> kolekce.</span><span class="sxs-lookup"><span data-stu-id="68b8b-118">Use the <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> or <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> method of the <xref:System.Windows.Forms.ListView.Groups%2A> collection.</span></span>  
  
     <span data-ttu-id="68b8b-119"><xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> Metoda odebere jednu skupinu; <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> metoda odebere všechny skupiny ze seznamu.</span><span class="sxs-lookup"><span data-stu-id="68b8b-119">The <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> method removes a single group; the <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> method removes all groups from the list.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="68b8b-120">Odebrání skupiny neodebere položky v rámci dané skupiny.</span><span class="sxs-lookup"><span data-stu-id="68b8b-120">Removing a group does not remove the items within that group.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#22)]  
  
### <a name="to-assign-items-to-groups-or-move-items-between-groups"></a><span data-ttu-id="68b8b-121">K přiřazení položky do skupin nebo položky přesouvat mezi skupinami.</span><span class="sxs-lookup"><span data-stu-id="68b8b-121">To assign items to groups or move items between groups</span></span>  
  
1.  <span data-ttu-id="68b8b-122">Nastavte <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> vlastnost jednotlivých položek.</span><span class="sxs-lookup"><span data-stu-id="68b8b-122">Set the <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> property of individual items.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="68b8b-123">Viz také</span><span class="sxs-lookup"><span data-stu-id="68b8b-123">See Also</span></span>  
 <xref:System.Windows.Forms.ListView>  
 <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ListViewGroup>  
 [<span data-ttu-id="68b8b-124">ListView – ovládací prvek</span><span class="sxs-lookup"><span data-stu-id="68b8b-124">ListView Control</span></span>](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [<span data-ttu-id="68b8b-125">Přehled ovládacího prvku ListView</span><span class="sxs-lookup"><span data-stu-id="68b8b-125">ListView Control Overview</span></span>](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [<span data-ttu-id="68b8b-126">Funkce systému Windows XP a Windows Forms – ovládací prvky</span><span class="sxs-lookup"><span data-stu-id="68b8b-126">Windows XP Features and Windows Forms Controls</span></span>](http://msdn.microsoft.com/en-us/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)  
 [<span data-ttu-id="68b8b-127">Postupy: Přidání a odebrání položek pomocí ovládacího prvku Windows Forms ListView – ovládací prvek</span><span class="sxs-lookup"><span data-stu-id="68b8b-127">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
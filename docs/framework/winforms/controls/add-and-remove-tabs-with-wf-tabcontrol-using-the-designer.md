---
title: "Postupy: Přidávání a odebírání karet s prvkem Windows Forms TabControl pomocí Návrháře"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tabs [Windows Forms], removing from pages
- TabPage control
- TabPage control [Windows Forms], adding and removing tabs
- tabs [Windows Forms], adding to pages
- tab pages
ms.assetid: 480633db-413a-45d2-9c8f-0427cc13adbe
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 02bcf434baee0c27ca2674817df0e4033effb125
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol-using-the-designer"></a><span data-ttu-id="6e4b3-102">Postupy: Přidávání a odebírání karet s prvkem Windows Forms TabControl pomocí Návrháře</span><span class="sxs-lookup"><span data-stu-id="6e4b3-102">How to: Add and Remove Tabs with the Windows Forms TabControl Using the Designer</span></span>
<span data-ttu-id="6e4b3-103">Když umístíte <xref:System.Windows.Forms.TabControl> ovládacího prvku ve formuláři, obsahuje dvě karty ve výchozím nastavení.</span><span class="sxs-lookup"><span data-stu-id="6e4b3-103">When you place a <xref:System.Windows.Forms.TabControl> control on your form, it contains two tabs by default.</span></span> <span data-ttu-id="6e4b3-104">Můžete přidat nebo odebrat karty pomocí návrháře.</span><span class="sxs-lookup"><span data-stu-id="6e4b3-104">You can add or remove tabs using the designer.</span></span>  
  
 <span data-ttu-id="6e4b3-105">Následující postup vyžaduje **aplikace Windows** projekt pomocí formuláře obsahující <xref:System.Windows.Forms.TabControl> ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="6e4b3-105">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.TabControl> control.</span></span> <span data-ttu-id="6e4b3-106">Informace o nastavení tohoto projektu najdete v tématu [postupy: vytvoření projektu aplikace Windows](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) a [postupy: Přidání ovládacích prvků do formulářů Windows](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="6e4b3-106">For information about setting up such a project, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6e4b3-107">Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici.</span><span class="sxs-lookup"><span data-stu-id="6e4b3-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="6e4b3-108">Chcete-li změnit nastavení, zvolte **nastavení importu a exportu** na **nástroje** nabídky.</span><span class="sxs-lookup"><span data-stu-id="6e4b3-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="6e4b3-109">Další informace najdete v tématu [přizpůsobení nastavení pro vývoj v sadě Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="6e4b3-109">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-add-or-remove-a-tab-using-the-designer"></a><span data-ttu-id="6e4b3-110">Přidat nebo odebrat na kartě pomocí návrháře</span><span class="sxs-lookup"><span data-stu-id="6e4b3-110">To add or remove a tab using the designer</span></span>  
  
-   <span data-ttu-id="6e4b3-111">Na inteligentní značky ovládacího prvku, klikněte na tlačítko **přidat karta** nebo **odebrat karta**</span><span class="sxs-lookup"><span data-stu-id="6e4b3-111">On the control's smart tag, click **Add Tab** or **Remove Tab**</span></span>  
  
     <span data-ttu-id="6e4b3-112">-nebo-</span><span class="sxs-lookup"><span data-stu-id="6e4b3-112">-or-</span></span>  
  
     <span data-ttu-id="6e4b3-113">V **vlastnosti** okně klikněte na tlačítko **třemi tečkami** tlačítko (![– snímek obrazovky VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) vedle položky <xref:System.Windows.Forms.TabControl.TabPages%2A> vlastnost otevřete **TabPage – Editor kolekce**.</span><span class="sxs-lookup"><span data-stu-id="6e4b3-113">In the **Properties** window, click the **Ellipsis** button (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.TabControl.TabPages%2A> property to open the **TabPage Collection Editor**.</span></span> <span data-ttu-id="6e4b3-114">Klikněte **přidat** nebo **odebrat** tlačítko.</span><span class="sxs-lookup"><span data-stu-id="6e4b3-114">Click the **Add** or **Remove** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e4b3-115">Viz také</span><span class="sxs-lookup"><span data-stu-id="6e4b3-115">See Also</span></span>  
 [<span data-ttu-id="6e4b3-116">TabControl – ovládací prvek</span><span class="sxs-lookup"><span data-stu-id="6e4b3-116">TabControl Control</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-windows-forms.md)  
 [<span data-ttu-id="6e4b3-117">Přehled ovládacího prvku TabControl</span><span class="sxs-lookup"><span data-stu-id="6e4b3-117">TabControl Control Overview</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)  
 [<span data-ttu-id="6e4b3-118">Postupy: Přidání ovládacího prvku do stránky karty</span><span class="sxs-lookup"><span data-stu-id="6e4b3-118">How to: Add a Control to a Tab Page</span></span>](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)  
 [<span data-ttu-id="6e4b3-119">Postupy: zákaz stránek karet</span><span class="sxs-lookup"><span data-stu-id="6e4b3-119">How to: Disable Tab Pages</span></span>](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)  
 [<span data-ttu-id="6e4b3-120">Postupy: Změna vzhledu Windows Forms TabControl</span><span class="sxs-lookup"><span data-stu-id="6e4b3-120">How to: Change the Appearance of the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
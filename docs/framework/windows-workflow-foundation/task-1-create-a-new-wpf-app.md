---
title: "Úloha 1: Vytvořte novou aplikaci Windows Presentation Foundation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 270eaeba-9492-4532-af9f-403ce5c9935b
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: bfebf11d66ded668d7c0892d11adde76e0a42c01
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="task-1-create-a-new-windows-presentation-foundation-application"></a><span data-ttu-id="bedd4-102">Úloha 1: Vytvořte novou aplikaci Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="bedd4-102">Task 1: Create a New Windows Presentation Foundation Application</span></span>
<span data-ttu-id="bedd4-103">V této úloze, vytvoříte prázdnou [!INCLUDE[avalon1](../../../includes/avalon1-md.md)] aplikace pomocí šablony sady Visual Studio aplikace WPF a přidejte odkazy na příslušné [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] sestavení pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="bedd4-103">In this task, you will create an empty [!INCLUDE[avalon1](../../../includes/avalon1-md.md)] application by using the WPF Application Visual Studio template and add references to the appropriate [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] workflow assemblies.</span></span>  
  
### <a name="to-create-the-wpf-application-project"></a><span data-ttu-id="bedd4-104">Chcete-li vytvořit projekt aplikace WPF</span><span class="sxs-lookup"><span data-stu-id="bedd4-104">To create the WPF Application project</span></span>  
  
1.  <span data-ttu-id="bedd4-105">Otevřete [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] a na **soubor** nabídky, přejděte na příkaz **nový**a potom klikněte na **projektu**.</span><span class="sxs-lookup"><span data-stu-id="bedd4-105">Open [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] and on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="bedd4-106">V **nový projekt** dialogovém okně vyberte buď **Visual C#** nebo **jazyka Visual Basic** z **nainstalovaných šablonách** podokna na levé straně do pole.</span><span class="sxs-lookup"><span data-stu-id="bedd4-106">In the **New Project** dialog box, select either **Visual C#** or **Visual Basic** from the **Installed Templates** pane on the left side of the box.</span></span> <span data-ttu-id="bedd4-107">Pokud jazyk podle vašeho výběru nezobrazí, podívejte se do části **jiné jazyky**.</span><span class="sxs-lookup"><span data-stu-id="bedd4-107">If the language of your choice does not appear, look under **Other Languages**.</span></span>  
  
3.  <span data-ttu-id="bedd4-108">Vyberte **Windows** v **nainstalovaných šablonách** podokně.</span><span class="sxs-lookup"><span data-stu-id="bedd4-108">Select **Windows** in the **Installed Templates** pane.</span></span>  
  
4.  <span data-ttu-id="bedd4-109">V tomto horním podokně, potvrďte, že (výchozí hodnota) **rozhraní .NET Framework 4** byl vybraný v rozevíracím seznamu a pak vyberte **aplikaci WPF**.</span><span class="sxs-lookup"><span data-stu-id="bedd4-109">In the top pane, confirm that (the default value) **.NET Framework 4** has been selected in the drop-down list box, and then select **WPF Application**.</span></span>  
  
5.  <span data-ttu-id="bedd4-110">Nastavte na název projektu do **HostingApplication** v dolní části okna.</span><span class="sxs-lookup"><span data-stu-id="bedd4-110">Set the name of the project to **HostingApplication** at the bottom of the window.</span></span>  
  
6.  <span data-ttu-id="bedd4-111">Název řešení nastavte **RehostingTheDesigner**.</span><span class="sxs-lookup"><span data-stu-id="bedd4-111">Set the solution name to **RehostingTheDesigner**.</span></span>  
  
7.  <span data-ttu-id="bedd4-112">Klikněte na tlačítko **OK** vytvořit projekt aplikace.</span><span class="sxs-lookup"><span data-stu-id="bedd4-112">Click **OK** to create the application project.</span></span> [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)]<span data-ttu-id="bedd4-113">vytvoří základní uživatelské rozhraní WPF pro vaši aplikaci a obsahuje odpovídající XAML a soubory kódu.</span><span class="sxs-lookup"><span data-stu-id="bedd4-113"> creates a basic WPF UI for your application and includes the appropriate XAML and code-behind files.</span></span>  
  
8.  <span data-ttu-id="bedd4-114">Přidejte odkazy na **WorkflowModel** sestavení.</span><span class="sxs-lookup"><span data-stu-id="bedd4-114">Add references to **WorkflowModel** assemblies.</span></span> <span data-ttu-id="bedd4-115">Chcete-li to provést, v **Průzkumníku řešení**, klikněte pravým tlačítkem myši **HostingApplication** projektu a vyberte **přidat odkaz na**.</span><span class="sxs-lookup"><span data-stu-id="bedd4-115">To do this, in **Solution Explorer**, right-click the **HostingApplication** project and select **Add Reference**.</span></span>  
  
9. <span data-ttu-id="bedd4-116">V **přidat odkaz na** dialogové okno, klikněte na tlačítko **.NET** podržte stisknutou klávesu CTRL, vyberte následující sestavení a pak klikněte na tlačítko **OK**:</span><span class="sxs-lookup"><span data-stu-id="bedd4-116">In the **Add Reference** dialog box, click the **.NET** tab, hold down the CTRL key, select the following assemblies, and then click **OK**:</span></span>  
  
    -   <span data-ttu-id="bedd4-117">Systém.</span><span class="sxs-lookup"><span data-stu-id="bedd4-117">System.Activities</span></span>  
  
    -   <span data-ttu-id="bedd4-118">System.Activities.Presentation</span><span class="sxs-lookup"><span data-stu-id="bedd4-118">System.Activities.Presentation</span></span>  
  
    -   <span data-ttu-id="bedd4-119">System.Activities.Core.Presentation</span><span class="sxs-lookup"><span data-stu-id="bedd4-119">System.Activities.Core.Presentation</span></span>  
  
10. <span data-ttu-id="bedd4-120">Click **OK**.</span><span class="sxs-lookup"><span data-stu-id="bedd4-120">Click **OK**.</span></span>  
  
11. <span data-ttu-id="bedd4-121">V tématu [úloha 2: hostování návrháře pracovních postupů](../../../docs/framework/windows-workflow-foundation/task-2-host-the-workflow-designer.md) se dozvíte, jak k hostování plátna návrháře návrhu pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="bedd4-121">See [Task 2: Host the Workflow Designer](../../../docs/framework/windows-workflow-foundation/task-2-host-the-workflow-designer.md) to learn how to host the workflow designer design canvas.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bedd4-122">Viz také</span><span class="sxs-lookup"><span data-stu-id="bedd4-122">See Also</span></span>  
 [<span data-ttu-id="bedd4-123">Opětovného hostování návrháře pracovních postupů</span><span class="sxs-lookup"><span data-stu-id="bedd4-123">Rehosting the Workflow Designer</span></span>](../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md)  
 [<span data-ttu-id="bedd4-124">Úloha 2: Hostování návrháře pracovních postupů</span><span class="sxs-lookup"><span data-stu-id="bedd4-124">Task 2: Host the Workflow Designer</span></span>](../../../docs/framework/windows-workflow-foundation/task-2-host-the-workflow-designer.md)
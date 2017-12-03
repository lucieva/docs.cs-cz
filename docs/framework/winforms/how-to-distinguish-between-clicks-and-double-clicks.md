---
title: "Postupy: Rozlišení mezi kliknutím a poklikáním"
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
- cpp
helpviewer_keywords:
- mouse [Windows Forms], click
- mouse [Windows Forms], double-click
- mouse clicks [Windows Forms], single versus double
ms.assetid: d836ac8c-85bc-4f3a-a761-8aee03dc682c
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9b407f7c00454b0a14b4c90694d015b38ffd72ef
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-distinguish-between-clicks-and-double-clicks"></a><span data-ttu-id="4fe54-102">Postupy: Rozlišení mezi kliknutím a poklikáním</span><span class="sxs-lookup"><span data-stu-id="4fe54-102">How to: Distinguish Between Clicks and Double-Clicks</span></span>
<span data-ttu-id="4fe54-103">Obvykle jedné *klikněte na tlačítko* zahájí akci uživatele rozhraní (UI) a *dvakrát klikněte na* rozšiřuje akce.</span><span class="sxs-lookup"><span data-stu-id="4fe54-103">Typically, a single *click* initiates a user interface (UI) action and a *double-click* extends the action.</span></span> <span data-ttu-id="4fe54-104">Například jedním kliknutím obvykle vybere položku a poklepání upravuje vybranou položku.</span><span class="sxs-lookup"><span data-stu-id="4fe54-104">For example, one click usually selects an item, and a double-click edits the selected item.</span></span> <span data-ttu-id="4fe54-105">Windows Forms události kliknutí není pojmout snadno scénář, kde kliknutí a dvojitým kliknutím udělejte nekompatibilní, protože akce vázáno <xref:System.Windows.Forms.Control.Click> nebo <xref:System.Windows.Forms.Control.MouseClick> událostí se provádí před akci vázáno <xref:System.Windows.Forms.Control.DoubleClick>nebo <xref:System.Windows.Forms.Control.MouseDoubleClick> událostí.</span><span class="sxs-lookup"><span data-stu-id="4fe54-105">However, the Windows Forms click events do not easily accommodate a scenario where a click and a double-click perform incompatible actions, because an action tied to the <xref:System.Windows.Forms.Control.Click> or <xref:System.Windows.Forms.Control.MouseClick> event is performed before the action tied to the <xref:System.Windows.Forms.Control.DoubleClick> or <xref:System.Windows.Forms.Control.MouseDoubleClick> event.</span></span> <span data-ttu-id="4fe54-106">Toto téma popisuje dvě řešení tohoto problému.</span><span class="sxs-lookup"><span data-stu-id="4fe54-106">This topic demonstrates two solutions to this problem.</span></span> <span data-ttu-id="4fe54-107">Jedno řešení je zpracování události poklikejte na soubor a vrácení akce při zpracování události, klikněte na tlačítko.</span><span class="sxs-lookup"><span data-stu-id="4fe54-107">One solution is to handle the double-click event and roll back the actions in the handling of the click event.</span></span> <span data-ttu-id="4fe54-108">Ve výjimečných případech budete muset simulovat kliknutím a dvakrát klikněte na chování ve zpracování <xref:System.Windows.Forms.Control.MouseDown> událostí a pomocí <xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A> a <xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A> vlastnosti <xref:System.Windows.Forms.SystemInformation> – třída.</span><span class="sxs-lookup"><span data-stu-id="4fe54-108">In rare situations you may need to simulate click and double-click behavior by handling the <xref:System.Windows.Forms.Control.MouseDown> event and by using the <xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A> and <xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A> properties of the <xref:System.Windows.Forms.SystemInformation> class.</span></span> <span data-ttu-id="4fe54-109">Měření čas mezi kliknutí a druhý klikněte na tlačítko nastane před hodnotu <xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A> je dosaženo a kliknutím na možnost se v obdélníku definované <xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A>, proveďte akci, poklikejte na soubor; jinak, proveďte akci, klikněte na tlačítko.</span><span class="sxs-lookup"><span data-stu-id="4fe54-109">You measure the time between clicks and if a second click occurs before the value of <xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A> is reached and the click is within a rectangle defined by <xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A>, perform the double-click action; otherwise, perform the click action.</span></span>  
  
### <a name="to-roll-back-a-click-action"></a><span data-ttu-id="4fe54-110">Vrácení akce klikněte na</span><span class="sxs-lookup"><span data-stu-id="4fe54-110">To roll back a click action</span></span>  
  
-   <span data-ttu-id="4fe54-111">Zkontrolujte, zda pracujete s ovládacího prvku standard klikněte dvakrát na chování.</span><span class="sxs-lookup"><span data-stu-id="4fe54-111">Ensure that the control you are working with has standard double-click behavior.</span></span> <span data-ttu-id="4fe54-112">Pokud ne, povolte pomocí ovládacího prvku <xref:System.Windows.Forms.Control.SetStyle%2A> metoda.</span><span class="sxs-lookup"><span data-stu-id="4fe54-112">If not, enable the control with the <xref:System.Windows.Forms.Control.SetStyle%2A> method.</span></span> <span data-ttu-id="4fe54-113">Zpracovat událost poklikejte na soubor a vrátit zpět, klikněte na akci, jakož i akce poklikejte na soubor.</span><span class="sxs-lookup"><span data-stu-id="4fe54-113">Handle the double-click event and roll back the click action as well as the double-click action.</span></span> <span data-ttu-id="4fe54-114">Následující příklad kódu ukazuje, jak vytvořit vlastní tlačítko s dvojitým kliknutím povolena, a také pro návrat akce klikněte na tlačítko v kód pro zpracování události poklikejte na soubor.</span><span class="sxs-lookup"><span data-stu-id="4fe54-114">The following code example demonstrates a how to create a custom button with double-click enabled, as well as how to roll back the click action in the double-click event handling code.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ButtonDoubleClick#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ButtonDoubleClick/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.ButtonDoubleClick#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ButtonDoubleClick/VB/Form1.vb#1)]  
  
### <a name="to-distinguish-between-clicks-in-the-mousedown-event"></a><span data-ttu-id="4fe54-115">K rozlišení mezi kliknutím v MouseDown – událost</span><span class="sxs-lookup"><span data-stu-id="4fe54-115">To distinguish between clicks in the MouseDown event</span></span>  
  
-   <span data-ttu-id="4fe54-116">Zpracování <xref:System.Windows.Forms.Control.MouseDown> událostí a určete umístění a čas span mezi kliknutím odpovídající pomocí <xref:System.Windows.Forms.SystemInformation> vlastnosti a <xref:System.Windows.Forms.Timer> součásti.</span><span class="sxs-lookup"><span data-stu-id="4fe54-116">Handle the <xref:System.Windows.Forms.Control.MouseDown> event and determine the location and time span between clicks using the appropriate <xref:System.Windows.Forms.SystemInformation> properties and a <xref:System.Windows.Forms.Timer> component.</span></span> <span data-ttu-id="4fe54-117">Proveďte příslušné akce v závislosti na tom, jestli klikněte na tlačítko nebo poklikejte na soubor probíhá.</span><span class="sxs-lookup"><span data-stu-id="4fe54-117">Perform the appropriate action depending on whether a click or double-click takes place.</span></span> <span data-ttu-id="4fe54-118">Následující příklad kódu ukazuje, jak to lze provést.</span><span class="sxs-lookup"><span data-stu-id="4fe54-118">The following code example demonstrates how this can be done.</span></span>  
  
     [!code-cpp[System.Windows.Forms.SingleVersusDoubleClick#0](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.SingleVersusDoubleClick/cpp/form1.cpp#0)]
     [!code-csharp[System.Windows.Forms.SingleVersusDoubleClick#0](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.SingleVersusDoubleClick/CS/form1.cs#0)]
     [!code-vb[System.Windows.Forms.SingleVersusDoubleClick#0](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.SingleVersusDoubleClick/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4fe54-119">Probíhá kompilace kódu</span><span class="sxs-lookup"><span data-stu-id="4fe54-119">Compiling the Code</span></span>  
 <span data-ttu-id="4fe54-120">Tyto příklady vyžadují:</span><span class="sxs-lookup"><span data-stu-id="4fe54-120">These examples require:</span></span>  
  
-   <span data-ttu-id="4fe54-121">Odkazy na systém, System.Drawing a System.Windows.Forms sestavení.</span><span class="sxs-lookup"><span data-stu-id="4fe54-121">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="4fe54-122">Informace o vytváření těchto příkladech z příkazového řádku pro [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] nebo [!INCLUDE[csprcs](../../../includes/csprcs-md.md)], najdete v části [sestavení z příkazového řádku](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) nebo [vytváření pomocí příkazového řádku csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="4fe54-122">For information about building these examples from the command line for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../includes/csprcs-md.md)], see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="4fe54-123">Můžete také vytvořit tyto příklady [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] zadáním nebo vložením kód do nové projekty.</span><span class="sxs-lookup"><span data-stu-id="4fe54-123">You can also build these examples in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] by pasting the code into new projects.</span></span>  <span data-ttu-id="4fe54-124">Viz také [postupy: zkompilování a spuštění dokončení Windows Forms kód příklad pomocí sady Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="4fe54-124">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fe54-125">Viz také</span><span class="sxs-lookup"><span data-stu-id="4fe54-125">See Also</span></span>  
 [<span data-ttu-id="4fe54-126">Vstup z myši ve Windows Forms aplikace</span><span class="sxs-lookup"><span data-stu-id="4fe54-126">Mouse Input in a Windows Forms Application</span></span>](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)
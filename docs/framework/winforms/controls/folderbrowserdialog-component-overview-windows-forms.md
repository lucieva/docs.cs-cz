---
title: "FolderBrowserDialog – přehled komponenty (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: FolderBrowserDialog
helpviewer_keywords:
- FolderBrowserDialog component [Windows Forms], about FolderBrowserDialog
- directories [Windows Forms], enabling browsing in applications
- folders [Windows Forms], enabling browsing in applications
ms.assetid: 796b622c-3ba9-4356-93bb-e217fc52f2c7
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d7fab1dbe01c5b21e510841b1541150f6152ab0b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="folderbrowserdialog-component-overview-windows-forms"></a><span data-ttu-id="6c1fe-102">FolderBrowserDialog – přehled komponenty (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="6c1fe-102">FolderBrowserDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="6c1fe-103">Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> součást je modální dialogové okno, které se používá k procházení a výběru složek.</span><span class="sxs-lookup"><span data-stu-id="6c1fe-103">The Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> component is a modal dialog box that is used for browsing and selecting folders.</span></span> <span data-ttu-id="6c1fe-104">V nástroji lze také vytvořit nové složky <xref:System.Windows.Forms.FolderBrowserDialog> součásti.</span><span class="sxs-lookup"><span data-stu-id="6c1fe-104">New folders can also be created from within the <xref:System.Windows.Forms.FolderBrowserDialog> component.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6c1fe-105">Pokud chcete vybrat soubory místo složek, použijte [OpenFileDialog](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md) součásti.</span><span class="sxs-lookup"><span data-stu-id="6c1fe-105">To select files, instead of folders, use the [OpenFileDialog](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md) component.</span></span>  
  
 <span data-ttu-id="6c1fe-106"><xref:System.Windows.Forms.FolderBrowserDialog> Součást se zobrazí za běhu pomocí <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> metoda.</span><span class="sxs-lookup"><span data-stu-id="6c1fe-106">The <xref:System.Windows.Forms.FolderBrowserDialog> component is displayed at run time using the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span> <span data-ttu-id="6c1fe-107">Nastavte <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> vlastnost určit složku nejvyšší a jakýmkoliv podsložkám, které se zobrazí ve stromovém zobrazení dialogového okna.</span><span class="sxs-lookup"><span data-stu-id="6c1fe-107">Set the <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> property to determine the top-most folder and any subfolders that will appear within the tree view of the dialog box.</span></span> <span data-ttu-id="6c1fe-108">Po dialogové okno se zobrazí, můžete <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> vlastnost k získání cestu složky, která byla vybrána.</span><span class="sxs-lookup"><span data-stu-id="6c1fe-108">Once the dialog box has been shown, you can use the <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> property to get the path of the folder that was selected.</span></span>  
  
 <span data-ttu-id="6c1fe-109">Při jejím přidání do formuláře <xref:System.Windows.Forms.FolderBrowserDialog> součást se zobrazí na hlavním panelu v dolní části Návrhář formulářů Windows.</span><span class="sxs-lookup"><span data-stu-id="6c1fe-109">When it is added to a form, the <xref:System.Windows.Forms.FolderBrowserDialog> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c1fe-110">Viz také</span><span class="sxs-lookup"><span data-stu-id="6c1fe-110">See Also</span></span>  
 <xref:System.Windows.Forms.FolderBrowserDialog>  
 [<span data-ttu-id="6c1fe-111">Postupy: Výběr složek pomocí ovládacího prvku Windows Forms FolderBrowserDialog – komponenta</span><span class="sxs-lookup"><span data-stu-id="6c1fe-111">How to: Choose Folders with the Windows Forms FolderBrowserDialog Component</span></span>](../../../../docs/framework/winforms/controls/how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component.md)  
 [<span data-ttu-id="6c1fe-112">FolderBrowserDialog – komponenta</span><span class="sxs-lookup"><span data-stu-id="6c1fe-112">FolderBrowserDialog Component</span></span>](../../../../docs/framework/winforms/controls/folderbrowserdialog-component-windows-forms.md)
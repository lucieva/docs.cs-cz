---
title: "Postupy: Změna ohraničení Windows Forms "
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
helpviewer_keywords: Windows Forms, changing the borders
ms.assetid: b3d5fa56-80c6-4b10-b505-f9672307ed55
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 94c95d1d938ff8038f1057ac7648082819562b98
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-change-the-borders-of-windows-forms"></a><span data-ttu-id="87b9c-102">Postupy: Změna ohraničení Windows Forms </span><span class="sxs-lookup"><span data-stu-id="87b9c-102">How to: Change the Borders of Windows Forms</span></span>
<span data-ttu-id="87b9c-103">Máte několik stylů ohraničení lze vybírat při určování vzhled a chování Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="87b9c-103">You have several border styles to choose from when you are determining the appearance and behavior of your Windows Forms.</span></span> <span data-ttu-id="87b9c-104">Změnou <xref:System.Windows.Forms.Form.FormBorderStyle%2A> vlastnost, můžete řídit chování změny velikosti ve tvaru.</span><span class="sxs-lookup"><span data-stu-id="87b9c-104">By changing the <xref:System.Windows.Forms.Form.FormBorderStyle%2A> property, you can control the resizing behavior of the form.</span></span> <span data-ttu-id="87b9c-105">Kromě toho nastavení <xref:System.Windows.Forms.Form.FormBorderStyle%2A> má vliv na způsob zobrazení panelu popisek a co může vypadat tlačítka na něm.</span><span class="sxs-lookup"><span data-stu-id="87b9c-105">In addition, setting the <xref:System.Windows.Forms.Form.FormBorderStyle%2A> affects how the caption bar is displayed as well as what buttons might appear on it.</span></span> <span data-ttu-id="87b9c-106">Další informace naleznete v tématu <xref:System.Windows.Forms.FormBorderStyle>.</span><span class="sxs-lookup"><span data-stu-id="87b9c-106">For more information, see <xref:System.Windows.Forms.FormBorderStyle>.</span></span>  
  
 <span data-ttu-id="87b9c-107">Je rozsáhlá podpora pro tuto úlohu v [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="87b9c-107">There is extensive support for this task in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span></span>  
  
 <span data-ttu-id="87b9c-108">Viz také [postupy: Změna ohraničení Windows Forms pomocí návrháře](http://msdn.microsoft.com/library/yettzh3e\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="87b9c-108">See also [How to: Change the Borders of Windows Forms Using the Designer](http://msdn.microsoft.com/library/yettzh3e\(v=vs.110\)).</span></span>  
  
### <a name="to-set-the-border-style-of-windows-forms-programmatically"></a><span data-ttu-id="87b9c-109">Chcete-li nastavit styl ohraničení Windows Forms prostřednictvím kódu programu</span><span class="sxs-lookup"><span data-stu-id="87b9c-109">To set the border style of Windows Forms programmatically</span></span>  
  
-   <span data-ttu-id="87b9c-110">Nastavte <xref:System.Windows.Forms.Form.FormBorderStyle%2A> vlastnost na styl chcete.</span><span class="sxs-lookup"><span data-stu-id="87b9c-110">Set the <xref:System.Windows.Forms.Form.FormBorderStyle%2A> property to the style you want.</span></span> <span data-ttu-id="87b9c-111">Následující příklad kódu nastaví styl ohraničení tvaru `DlgBx1` k <xref:System.Windows.Forms.FormBorderStyle.FixedDialog>.</span><span class="sxs-lookup"><span data-stu-id="87b9c-111">The following code example sets the border style of form `DlgBx1` to <xref:System.Windows.Forms.FormBorderStyle.FixedDialog>.</span></span>  
  
    ```vb  
    DlgBx1.FormBorderStyle = System.Windows.Forms.FormBorderStyle.FixedDialog  
    ```  
  
    ```csharp  
    DlgBx1.FormBorderStyle = System.Windows.Forms.FormBorderStyle.FixedDialog;  
    ```  
  
    ```cpp  
    DlgBx1->FormBorderStyle =  
       System::Windows::Forms::FormBorderStyle::FixedDialog;  
    ```  
  
     <span data-ttu-id="87b9c-112">Viz také [postupy: vytvoření dialogová okna v době návrhu](http://msdn.microsoft.com/library/55cz5x2c\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="87b9c-112">Also see [How to: Create Dialog Boxes at Design Time](http://msdn.microsoft.com/library/55cz5x2c\(v=vs.110\)).</span></span>  
  
     <span data-ttu-id="87b9c-113">Kromě toho pokud jste vybrali styl ohraničení pro daný formulář, který poskytuje volitelné **minimalizaci** a **Maximalizovat** tlačítka, které můžete určete, jestli má jedné nebo obou těchto tlačítek k fungování.</span><span class="sxs-lookup"><span data-stu-id="87b9c-113">Additionally, if you have chosen a border style for the form that provides optional **Minimize** and **Maximize** buttons, you can specify whether you want either or both of these buttons to be functional.</span></span> <span data-ttu-id="87b9c-114">Tyto přepínače jsou užitečné, když chcete řídí činnost koncového uživatele.</span><span class="sxs-lookup"><span data-stu-id="87b9c-114">These buttons are useful when you want to closely control the user experience.</span></span> <span data-ttu-id="87b9c-115">**Minimalizaci** a **Maximalizovat** tlačítka jsou povolena ve výchozím nastavení, a jejich funkce s nimi manipulovat prostřednictvím **vlastnosti** okno.</span><span class="sxs-lookup"><span data-stu-id="87b9c-115">The **Minimize** and **Maximize** buttons are enabled by default, and their functionality is manipulated through the **Properties** window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87b9c-116">Viz také</span><span class="sxs-lookup"><span data-stu-id="87b9c-116">See Also</span></span>  
 <xref:System.Windows.Forms.FormBorderStyle>  
 <xref:System.Windows.Forms.FormBorderStyle.FixedDialog>  
 [<span data-ttu-id="87b9c-117">Začínáme s Windows Forms</span><span class="sxs-lookup"><span data-stu-id="87b9c-117">Getting Started with Windows Forms</span></span>](../../../docs/framework/winforms/getting-started-with-windows-forms.md)
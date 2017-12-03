---
title: "Postupy: Nastavení textu zobrazovaného ovládacím prvkem Windows Forms"
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
- Windows Forms, captions
- Button control [Windows Forms], button text
- StdFont object and CommandButton caption
- captions [Windows Forms], Windows Forms controls
- Text property [Windows Forms], Windows Forms control
- Button control [Windows Forms], text display
- labels [Windows Forms], adding to CommandButton control
- buttons [Windows Forms], text
- captions [Windows Forms], setting
- text
- examples [Windows Forms], controls
- text [Windows Forms], Windows Forms controls
- controls [Windows Forms], captions
- forms [Windows Forms], captions
ms.assetid: 36b95bff-8780-479d-b86a-f1a0673653aa
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a81c2202400968b4d4c95b40de7476fbd68d6182
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-the-text-displayed-by-a-windows-forms-control"></a><span data-ttu-id="5b651-102">Postupy: Nastavení textu zobrazovaného ovládacím prvkem Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5b651-102">How to: Set the Text Displayed by a Windows Forms Control</span></span>
<span data-ttu-id="5b651-103">Ovládací prvky Windows Forms obvykle zobrazí text související s primární funkce ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="5b651-103">Windows Forms controls usually display some text that is related to the primary function of the control.</span></span> <span data-ttu-id="5b651-104">Například <xref:System.Windows.Forms.Button> obvykle zobrazí popisek indikující, jaká akce se provede při kliknutí na tlačítko.</span><span class="sxs-lookup"><span data-stu-id="5b651-104">For example, a <xref:System.Windows.Forms.Button> control usually displays a caption indicating what action will be performed when the button is clicked.</span></span> <span data-ttu-id="5b651-105">Pro všechny ovládací prvky, můžete nastavit nebo vrátí text s použitím <xref:System.Windows.Forms.Control.Text%2A> vlastnost.</span><span class="sxs-lookup"><span data-stu-id="5b651-105">For all controls, you can set or return the text by using the <xref:System.Windows.Forms.Control.Text%2A> property.</span></span> <span data-ttu-id="5b651-106">Písmo můžete změnit pomocí <xref:System.Windows.Forms.Control.Font%2A> vlastnost.</span><span class="sxs-lookup"><span data-stu-id="5b651-106">You can change the font by using the <xref:System.Windows.Forms.Control.Font%2A> property.</span></span> <span data-ttu-id="5b651-107">Můžete také nastavit text pomocí návrháře.</span><span class="sxs-lookup"><span data-stu-id="5b651-107">You can also set the text using the designer.</span></span>  <span data-ttu-id="5b651-108">Také najdete v části [postup: vytvoření přístup klíčů pro Windows Forms – ovládací prvky pomocí návrháře](http://msdn.microsoft.com/library/ms233673\(v=vs.110\)), [postup: nastavení zobrazí Text s použitím ovládacího prvku Windows Forms návrháře](http://msdn.microsoft.com/library/ms233665\(v=vs.110\)), [postupy: nastavení obrázku Zobrazí ve Windows Forms pomocí návrháře ovládacího prvku](http://msdn.microsoft.com/library/ms233656\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="5b651-108">Also see [How to: Create Access Keys for Windows Forms Controls Using the Designer](http://msdn.microsoft.com/library/ms233673\(v=vs.110\)), [How to: Set the Text Displayed by a Windows Forms Control Using the Designer](http://msdn.microsoft.com/library/ms233665\(v=vs.110\)), [How to: Set the Image Displayed by a Windows Forms Control Using the Designer](http://msdn.microsoft.com/library/ms233656\(v=vs.110\)).</span></span>  
  
### <a name="to-set-the-text-displayed-by-a-control-programmatically"></a><span data-ttu-id="5b651-109">K nastavení textu zobrazovaného ovládacím prvkem prostřednictvím kódu programu</span><span class="sxs-lookup"><span data-stu-id="5b651-109">To set the text displayed by a control programmatically</span></span>  
  
1.  <span data-ttu-id="5b651-110">Nastavte <xref:System.Windows.Forms.Control.Text%2A> na řetězec.</span><span class="sxs-lookup"><span data-stu-id="5b651-110">Set the <xref:System.Windows.Forms.Control.Text%2A> property to a string.</span></span>  
  
     <span data-ttu-id="5b651-111">Chcete-li vytvořit podtržené přístupový klíč, obsahuje znak ampersand (&) před písmeno, které bude přístupový klíč.</span><span class="sxs-lookup"><span data-stu-id="5b651-111">To create an underlined access key, includes an ampersand (&) before the letter that will be the access key.</span></span>  
  
2.  <span data-ttu-id="5b651-112">Nastavte <xref:System.Windows.Forms.Control.Font%2A> vlastností pro objekt typu <xref:System.Drawing.Font>.</span><span class="sxs-lookup"><span data-stu-id="5b651-112">Set the <xref:System.Windows.Forms.Control.Font%2A> property to an object of type <xref:System.Drawing.Font>.</span></span>  
  
    ```vb  
    Button1.Text = "Click here to save changes"  
    Button1.Font = New Font("Arial", 10, FontStyle.Bold, GraphicsUnit.Point)  
    ```  
  
    ```csharp  
    button1.Text = "Click here to save changes";  
    button1.Font = new Font("Arial", 10, FontStyle.Bold,  
       GraphicsUnit.Point);  
    ```  
  
    ```cpp  
    button1->Text = "Click here to save changes";  
    button1->Font = new System::Drawing::Font("Arial",  
       10, FontStyle::Bold, GraphicsUnit::Point);  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="5b651-113">Řídicí znak můžete zobrazit speciální znak v prvky uživatelského rozhraní, které by normálně jejich interpretace, například položky nabídky.</span><span class="sxs-lookup"><span data-stu-id="5b651-113">You can use an escape character to display a special character in user-interface elements that would normally interpret them differently, such as menu items.</span></span> <span data-ttu-id="5b651-114">Například následující řádek kódu nastaví položku nabídky textu k načtení "& teď pro něco úplně jiné":</span><span class="sxs-lookup"><span data-stu-id="5b651-114">For example, the following line of code sets the menu item's text to read "& Now For Something Completely Different":</span></span>  
  
    ```vb  
    MPMenuItem.Text = "&& Now For Something Completely Different"  
    ```  
  
    ```csharp  
    mpMenuItem.Text = "&& Now For Something Completely Different";  
    ```  
  
    ```cpp  
    mpMenuItem->Text = "&& Now For Something Completely Different";  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="5b651-115">Viz také</span><span class="sxs-lookup"><span data-stu-id="5b651-115">See Also</span></span>  
 <xref:System.Windows.Forms.Control.Text%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="5b651-116">Postupy: vytváření přístupových klíčů pro ovládací prvky Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5b651-116">How to: Create Access Keys for Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md)  
 [<span data-ttu-id="5b651-117">Postupy: reakce na kliknutí na tlačítko Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5b651-117">How to: Respond to Windows Forms Button Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)
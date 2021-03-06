---
title: 'Postupy: Nastavení textu zobrazovaného ovládacím prvkem Windows Forms'
ms.date: 03/30/2017
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
ms.openlocfilehash: d9c9bea26cfc3d5b2cfc4484173a7680ff2fc34d
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/04/2018
ms.locfileid: "43525032"
---
# <a name="how-to-set-the-text-displayed-by-a-windows-forms-control"></a>Postupy: Nastavení textu zobrazovaného ovládacím prvkem Windows Forms
Ovládací prvky Windows Forms obvykle zobrazí text, který souvisí s primární funkce ovládacího prvku. Například <xref:System.Windows.Forms.Button> ovládací prvek obvykle zobrazí popisek indikující, jaká akce se provede při kliknutí na tlačítko. Pro všechny ovládací prvky, můžete nastavit nebo načíst text pomocí <xref:System.Windows.Forms.Control.Text%2A> vlastnost. Můžete změnit písmo pomocí <xref:System.Windows.Forms.Control.Font%2A> vlastnost. Můžete také nastavit text pomocí návrháře.  Také naleznete v tématu [postupy: vytvoření přístup klíčů pro Windows Forms ovládací prvky pomocí návrháře](how-to-create-access-keys-for-windows-forms-controls-using-the-designer.md), [jak: nastavit Text zobrazí s použitím ovládacího prvku Windows Forms návrháře](how-to-set-the-text-displayed-by-a-windows-forms-control-using-the-designer.md), [postupy: nastavení obrázku Zobrazený Windows Forms pomocí návrháře ovládací prvek](how-to-set-the-image-displayed-by-a-windows-forms-control-using-the-designer.md).  
  
### <a name="to-set-the-text-displayed-by-a-control-programmatically"></a>K nastavení textu zobrazovaného ovládacím prvkem prostřednictvím kódu programu  
  
1.  Nastavte <xref:System.Windows.Forms.Control.Text%2A> nastavte na řetězec.  
  
     K vytvoření podtržené přístupový klíč, obsahuje znak ampersand (&) před písmenem, který bude přístupový klíč.  
  
2.  Nastavte <xref:System.Windows.Forms.Control.Font%2A> vlastnost na objekt typu <xref:System.Drawing.Font>.  
  
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
    >  Řídicí znak slouží k zobrazení speciálního znaku v prvcích uživatelského rozhraní, které by normálně interpretovat, jako je například položky nabídky. Například následující řádek kódu nastaví text položky nabídky ke čtení "& nyní pro něco úplně odlišnému":  
  
    ```vb  
    MPMenuItem.Text = "&& Now For Something Completely Different"  
    ```  
  
    ```csharp  
    mpMenuItem.Text = "&& Now For Something Completely Different";  
    ```  
  
    ```cpp  
    mpMenuItem->Text = "&& Now For Something Completely Different";  
    ```  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Windows.Forms.Control.Text%2A?displayProperty=nameWithType>  
 [Postupy: Vytváření přístupových klíčů pro ovládací prvky Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md)  
 [Postupy: Reakce na kliknutí na tlačítko Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)

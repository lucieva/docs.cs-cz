---
title: 'Postupy: Zobrazení ikon chyby pro ověřování formuláře pomocí součásti Windows Forms ErrorProvider'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- errors [Windows Forms], displaying to users
- error icons
- ErrorProvider component [Windows Forms], displaying error icons
- error messages [Windows Forms], displaying icons
ms.assetid: 3b681a32-9db4-497b-a34b-34980eabee46
ms.openlocfilehash: 237a61cc21a18805fa502c9870d8ea472ac54d71
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/04/2018
ms.locfileid: "33527297"
---
# <a name="how-to-display-error-icons-for-form-validation-with-the-windows-forms-errorprovider-component"></a>Postupy: Zobrazení ikon chyby pro ověřování formuláře pomocí součásti Windows Forms ErrorProvider
Můžete použít Windows Forms <xref:System.Windows.Forms.ErrorProvider> součást zobrazíte ikonu chyby, když uživatel zadá neplatná data. Musí mít alespoň dva ovládací prvky na formuláři kartě mezi nimi a tím vyvolání ověřovacího kódu.  
  
### <a name="to-display-an-error-icon-when-a-controls-value-is-invalid"></a>Zobrazit ikonu chyby při ovládacího prvku hodnota je neplatná.  
  
1.  Přidání ovládacích prvků dvě – například textová pole – na formuláři Windows.  
  
2.  Přidat <xref:System.Windows.Forms.ErrorProvider> součásti pro formulář.  
  
3.  Vyberte první prvek a přidat kód pro jeho <xref:System.Windows.Forms.Control.Validating> obslužné rutiny události. Aby pro tento kód správně spouštět postup musí být připojen k události. Další informace najdete v tématu [postupy: vytváření obslužných rutin událostí spustit čas pro Windows Forms](../../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md).  
  
     Následující kód testy platnosti dat, která uživatel zadal; Pokud je neplatná, data <xref:System.Windows.Forms.ErrorProvider.SetError%2A> metoda je volána. První argument funkce <xref:System.Windows.Forms.ErrorProvider.SetError%2A> metoda určuje, kterého ovládacího prvku na ikonu vedle položky zobrazení. Druhý argument je zobrazený text chyby.  
  
    ```vb  
    Private Sub TextBox1_Validating(ByVal Sender As Object, _  
       ByVal e As System.ComponentModel.CancelEventArgs) Handles _  
       TextBox1.Validating  
          If Not IsNumeric(TextBox1.Text) Then  
             ErrorProvider1.SetError(TextBox1, "Not a numeric value.")  
          Else  
             ' Clear the error.  
             ErrorProvider1.SetError(TextBox1, "")  
          End If  
    End Sub  
    ```  
  
    ```csharp  
    protected void textBox1_Validating (object sender,  
       System.ComponentModel.CancelEventArgs e)  
    {  
       try  
       {  
          int x = Int32.Parse(textBox1.Text);  
          errorProvider1.SetError(textBox1, "");  
       }  
       catch (Exception ex)  
       {  
          errorProvider1.SetError(textBox1, "Not an integer value.");  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void textBox1_Validating(System::Object ^  sender,  
          System::ComponentModel::CancelEventArgs ^  e)  
       {  
          try  
          {  
             int x = Int32::Parse(textBox1->Text);  
             errorProvider1->SetError(textBox1, "");  
          }  
          catch (System::Exception ^ ex)  
          {  
             errorProvider1->SetError(textBox1, "Not an integer value.");  
          }  
       }  
    ```  
  
     (Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) vložte následující kód v konstruktoru formuláře k registraci obslužné rutiny události.  
  
    ```csharp  
    this.textBox1.Validating += new  
    System.ComponentModel.CancelEventHandler(this.textBox1_Validating);  
    ```  
  
    ```cpp  
    this->textBox1->Validating += gcnew  
       System::ComponentModel::CancelEventHandler  
       (this, &Form1::textBox1_Validating);  
    ```  
  
4.  Spusťte projekt. Zadejte (v tomto příkladu jiné než číselné) neplatná data do první prvek a potom karty druhou. Když se zobrazí ikona chyby, přejděte na to ukazatel myši zobrazíte text chyby.  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Windows.Forms.ErrorProvider.SetError%2A>  
 [Přehled komponenty ErrorProvider](../../../../docs/framework/winforms/controls/errorprovider-component-overview-windows-forms.md)  
 [Postupy: Zobrazování chyb v prvku DataSet pomocí komponenty Windows Forms ErrorProvider](../../../../docs/framework/winforms/controls/view-errors-within-a-dataset-with-wf-errorprovider-component.md)

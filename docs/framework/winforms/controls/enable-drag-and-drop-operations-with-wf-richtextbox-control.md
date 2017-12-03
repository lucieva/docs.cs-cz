---
title: "Postupy: Povolení operací přetažení myší pomocí ovládacího prvku Windows Forms RichTextBox"
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
- examples [Windows Forms], text boxes
- drag and drop [Windows Forms], richTextBox control
- text boxes [Windows Forms], drag-and-drop operations
- RichTextBox control [Windows Forms], drag-and-drop operations
ms.assetid: ca167d1c-2014-4cf0-96a0-20598470be3b
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 91739643aaa2d7fe3ea302d0d35edabbae0ab14f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-enable-drag-and-drop-operations-with-the-windows-forms-richtextbox-control"></a><span data-ttu-id="a38c3-102">Postupy: Povolení operací přetažení myší pomocí ovládacího prvku Windows Forms RichTextBox</span><span class="sxs-lookup"><span data-stu-id="a38c3-102">How to: Enable Drag-and-Drop Operations with the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="a38c3-103">Operace přetažení myší pomocí Windows Forms <xref:System.Windows.Forms.RichTextBox> ovládací prvek, provádí zpracování <xref:System.Windows.Forms.RichTextBox.DragEnter> a <xref:System.Windows.Forms.RichTextBox.DragDrop> události.</span><span class="sxs-lookup"><span data-stu-id="a38c3-103">Drag-and-drop operations with the Windows Forms <xref:System.Windows.Forms.RichTextBox> control are done by handling the <xref:System.Windows.Forms.RichTextBox.DragEnter> and <xref:System.Windows.Forms.RichTextBox.DragDrop> events.</span></span> <span data-ttu-id="a38c3-104">Proto jsou velmi jednoduché s operací přetažení myší <xref:System.Windows.Forms.RichTextBox> ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="a38c3-104">Thus, drag-and-drop operations are extremely simple with the <xref:System.Windows.Forms.RichTextBox> control.</span></span>  
  
### <a name="to-enable-drag-operations-in-a-richtextbox-control"></a><span data-ttu-id="a38c3-105">Pro povolení operací přetažení v ovládacím prvku RichTextBox</span><span class="sxs-lookup"><span data-stu-id="a38c3-105">To enable drag operations in a RichTextBox control</span></span>  
  
1.  <span data-ttu-id="a38c3-106">Nastavte <xref:System.Windows.Forms.RichTextBox.AllowDrop%2A> vlastnost <xref:System.Windows.Forms.RichTextBox> řídit k `true`.</span><span class="sxs-lookup"><span data-stu-id="a38c3-106">Set the <xref:System.Windows.Forms.RichTextBox.AllowDrop%2A> property of the <xref:System.Windows.Forms.RichTextBox> control to `true`.</span></span>  
  
2.  <span data-ttu-id="a38c3-107">Psaní kódu v obslužné rutině události z <xref:System.Windows.Forms.RichTextBox.DragEnter> událostí.</span><span class="sxs-lookup"><span data-stu-id="a38c3-107">Write code in the event handler of the <xref:System.Windows.Forms.RichTextBox.DragEnter> event.</span></span> <span data-ttu-id="a38c3-108">Použijte `if` příkaz a zkontrolujte, zda data přetažen přijatelné typu (v tomto případě text).</span><span class="sxs-lookup"><span data-stu-id="a38c3-108">Use an `if` statement to ensure that the data being dragged is of an acceptable type (in this case, text).</span></span> <span data-ttu-id="a38c3-109"><xref:System.Windows.Forms.DragEventArgs.Effect%2A?displayProperty=nameWithType> Může být nastavena na jakoukoli hodnotu z <xref:System.Windows.Forms.DragDropEffects> výčtu.</span><span class="sxs-lookup"><span data-stu-id="a38c3-109">The <xref:System.Windows.Forms.DragEventArgs.Effect%2A?displayProperty=nameWithType> property can be set to any value of the <xref:System.Windows.Forms.DragDropEffects> enumeration.</span></span>  
  
    ```vb  
    Private Sub RichTextBox1_DragEnter(ByVal sender As Object, _   
       ByVal e As System.Windows.Forms.DragEventArgs) _   
       Handles RichTextBox1.DragEnter  
       If (e.Data.GetDataPresent(DataFormats.Text)) Then  
          e.Effect = DragDropEffects.Copy  
       Else  
          e.Effect = DragDropEffects.None  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void richTextBox1_DragEnter(object sender,   
    System.Windows.Forms.DragEventArgs e)  
    {  
       if (e.Data.GetDataPresent(DataFormats.Text))   
          e.Effect = DragDropEffects.Copy;  
       else  
          e.Effect = DragDropEffects.None;  
    }  
    ```  
  
    ```cpp  
    private:  
       void richTextBox1_DragEnter(System::Object ^  sender,  
          System::Windows::Forms::DragEventArgs ^  e)  
       {  
          if (e->Data->GetDataPresent(DataFormats::Text))  
             e->Effect = DragDropEffects::Copy;  
          else  
             e->Effect = DragDropEffects::None;  
       }  
    ```  
  
     <span data-ttu-id="a38c3-110">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] a [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) vložte následující kód v konstruktoru formuláře k registraci obslužné rutiny události.</span><span class="sxs-lookup"><span data-stu-id="a38c3-110">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.richTextBox1.DragEnter += new  
        System.Windows.Forms.DragEventHandler  
        (this.richTextBox1_DragEnter);  
    ```  
  
    ```cpp  
    this->richTextBox1->DragEnter += gcnew  
       System::Windows::Forms::DragEventHandler  
       (this, &Form1::richTextBox1_DragEnter);  
    ```  
  
3.  <span data-ttu-id="a38c3-111">Napsat kód pro zpracování <xref:System.Windows.Forms.RichTextBox.DragDrop> událostí.</span><span class="sxs-lookup"><span data-stu-id="a38c3-111">Write code to handle the <xref:System.Windows.Forms.RichTextBox.DragDrop> event.</span></span> <span data-ttu-id="a38c3-112">Použití <xref:System.Windows.Forms.DataObject.GetData%2A?displayProperty=nameWithType> metoda pro načtení dat přetažen.</span><span class="sxs-lookup"><span data-stu-id="a38c3-112">Use the <xref:System.Windows.Forms.DataObject.GetData%2A?displayProperty=nameWithType> method to retrieve the data being dragged.</span></span>  
  
     <span data-ttu-id="a38c3-113">V příkladu níže kód nastaví <xref:System.Windows.Forms.RichTextBox.Text%2A> vlastnost <xref:System.Windows.Forms.RichTextBox> řízení rovna přetažen data.</span><span class="sxs-lookup"><span data-stu-id="a38c3-113">In the example below, the code sets the <xref:System.Windows.Forms.RichTextBox.Text%2A> property of the <xref:System.Windows.Forms.RichTextBox> control equal to the data being dragged.</span></span> <span data-ttu-id="a38c3-114">Pokud je již v text <xref:System.Windows.Forms.RichTextBox> je vložen ovládací prvek, taženou text na pozici kurzoru.</span><span class="sxs-lookup"><span data-stu-id="a38c3-114">If there is already text in the <xref:System.Windows.Forms.RichTextBox> control, the dragged text is inserted at the insertion point.</span></span>  
  
    ```vb  
    Private Sub RichTextBox1_DragDrop(ByVal sender As Object, _   
       ByVal e As System.Windows.Forms.DragEventArgs) _   
       Handles RichTextBox1.DragDrop  
       Dim i As Int16   
       Dim s As String  
  
       ' Get start position to drop the text.  
       i = RichTextBox1.SelectionStart  
       s = RichTextBox1.Text.Substring(i)  
       RichTextBox1.Text = RichTextBox1.Text.Substring(0, i)  
  
       ' Drop the text on to the RichTextBox.  
       RichTextBox1.Text = RichTextBox1.Text + _  
          e.Data.GetData(DataFormats.Text).ToString()  
       RichTextBox1.Text = RichTextBox1.Text + s  
    End Sub  
    ```  
  
    ```csharp  
    private void richTextBox1_DragDrop(object sender,   
    System.Windows.Forms.DragEventArgs e)  
    {  
       int i;  
       String s;  
  
       // Get start position to drop the text.  
       i = richTextBox1.SelectionStart;  
       s = richTextBox1.Text.Substring(i);  
       richTextBox1.Text = richTextBox1.Text.Substring(0,i);  
  
       // Drop the text on to the RichTextBox.  
       richTextBox1.Text = richTextBox1.Text +   
          e.Data.GetData(DataFormats.Text).ToString();  
       richTextBox1.Text = richTextBox1.Text + s;  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void richTextBox1_DragDrop(System::Object ^  sender,  
          System::Windows::Forms::DragEventArgs ^  e)  
       {  
          int i;  
          String ^s;  
  
       // Get start position to drop the text.  
       i = richTextBox1->SelectionStart;  
       s = richTextBox1->Text->Substring(i);  
       richTextBox1->Text = richTextBox1->Text->Substring(0,i);  
  
       // Drop the text on to the RichTextBox.  
       String ^str = String::Concat(richTextBox1->Text, e->Data  
       ->GetData(DataFormats->Text)->ToString());   
       richTextBox1->Text = String::Concat(str, s);  
       }  
    ```  
  
     <span data-ttu-id="a38c3-115">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] a [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) vložte následující kód v konstruktoru formuláře k registraci obslužné rutiny události.</span><span class="sxs-lookup"><span data-stu-id="a38c3-115">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.richTextBox1.DragDrop += new  
        System.Windows.Forms.DragEventHandler  
        (this.richTextBox1_DragDrop);  
    ```  
  
    ```cpp  
    this->richTextBox1->DragDrop += gcnew   
       System::Windows::Forms::DragEventHandler  
       (this, &Form1::richTextBox1_DragDrop);  
    ```  
  
### <a name="to-test-the-drag-and-drop-functionality-in-your-application"></a><span data-ttu-id="a38c3-116">K testování funkcí přetahování myší v aplikaci</span><span class="sxs-lookup"><span data-stu-id="a38c3-116">To test the drag-and-drop functionality in your application</span></span>  
  
1.  <span data-ttu-id="a38c3-117">Uložit a sestavit aplikaci.</span><span class="sxs-lookup"><span data-stu-id="a38c3-117">Save and build your application.</span></span> <span data-ttu-id="a38c3-118">Když je spuštěná, spusťte WordPad.</span><span class="sxs-lookup"><span data-stu-id="a38c3-118">While it is running, run WordPad.</span></span>  
  
     <span data-ttu-id="a38c3-119">WordPad je textový editor, nainstalovaná v systému Windows, který umožňuje operací přetažení myší.</span><span class="sxs-lookup"><span data-stu-id="a38c3-119">WordPad is a text editor installed by Windows that allows drag-and-drop operations.</span></span> <span data-ttu-id="a38c3-120">Je přístupný kliknutím **spustit** tlačítko výběru **spustit**, zadáním `WordPad` v textovém poli **spustit** dialogové okno a potom kliknutím na tlačítko  **OK**.</span><span class="sxs-lookup"><span data-stu-id="a38c3-120">It is accessible by clicking the **Start** button, selecting **Run**, typing `WordPad` in the text box of the **Run** dialog box, and then clicking **OK**.</span></span>  
  
2.  <span data-ttu-id="a38c3-121">Jakmile WordPad je otevřený, zadejte řetězec textu v ní.</span><span class="sxs-lookup"><span data-stu-id="a38c3-121">Once WordPad is open, type a string of text in it.</span></span> <span data-ttu-id="a38c3-122">Pomocí myši, vyberte text a poté přetáhněte vybraný text přes k <xref:System.Windows.Forms.RichTextBox> ovládací prvek v aplikaci pro Windows.</span><span class="sxs-lookup"><span data-stu-id="a38c3-122">Using the mouse, select the text, and then drag the selected text over to the <xref:System.Windows.Forms.RichTextBox> control in your Windows application.</span></span>  
  
     <span data-ttu-id="a38c3-123">Všimněte si, že když přejděte myší na <xref:System.Windows.Forms.RichTextBox> ovládací prvek (a v důsledku toho vyvolat <xref:System.Windows.Forms.RichTextBox.DragEnter> událostí), aby se změnil a mohou vyřadit vybraný text do <xref:System.Windows.Forms.RichTextBox> ovládací prvek.</span><span class="sxs-lookup"><span data-stu-id="a38c3-123">Notice that when you point the mouse at the <xref:System.Windows.Forms.RichTextBox> control (and, consequently, raise the <xref:System.Windows.Forms.RichTextBox.DragEnter> event), the mouse pointer changes and you can drop the selected text into the <xref:System.Windows.Forms.RichTextBox> control.</span></span>  
  
     <span data-ttu-id="a38c3-124">Po uvolnění tlačítka myši se ukončí vybraný text (tedy <xref:System.Windows.Forms.RichTextBox.DragDrop> událost se vyvolá) a je vložen v rámci <xref:System.Windows.Forms.RichTextBox> ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="a38c3-124">When you release the mouse button, the selected text is dropped (that is, the <xref:System.Windows.Forms.RichTextBox.DragDrop> event is raised) and is inserted within the <xref:System.Windows.Forms.RichTextBox> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a38c3-125">Viz také</span><span class="sxs-lookup"><span data-stu-id="a38c3-125">See Also</span></span>  
 <xref:System.Windows.Forms.RichTextBox>  
 [<span data-ttu-id="a38c3-126">Postupy: provádění operací přetažení myší mezi aplikacemi</span><span class="sxs-lookup"><span data-stu-id="a38c3-126">How to: Perform Drag-and-Drop Operations Between Applications</span></span>](../../../../docs/framework/winforms/advanced/how-to-perform-drag-and-drop-operations-between-applications.md)  
 [<span data-ttu-id="a38c3-127">RichTextBox – ovládací prvek</span><span class="sxs-lookup"><span data-stu-id="a38c3-127">RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [<span data-ttu-id="a38c3-128">Ovládací prvky používané ve formulářích Windows</span><span class="sxs-lookup"><span data-stu-id="a38c3-128">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
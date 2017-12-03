---
title: "Postupy: Přidružení místní nabídky k součásti Windows Forms NotifyIcon"
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
- context menus [Windows Forms], for background processes
- NotifyIcon component [Windows Forms], associating shortcut menus
- shortcut menus [Windows Forms], for background processes
ms.assetid: d68f3926-08d3-4f7d-949f-1981b29cf188
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 985aa58056f4c4ec8f3042c682291508f1434ee0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component"></a><span data-ttu-id="25201-102">Postupy: Přidružení místní nabídky k součásti Windows Forms NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="25201-102">How to: Associate a Shortcut Menu with a Windows Forms NotifyIcon Component</span></span>
> [!NOTE]
>  <span data-ttu-id="25201-103">I když <xref:System.Windows.Forms.MenuStrip> a <xref:System.Windows.Forms.ContextMenuStrip> nahradit a přidání funkce do <xref:System.Windows.Forms.MainMenu> a <xref:System.Windows.Forms.ContextMenu> ovládací prvky předchozí verze, <xref:System.Windows.Forms.MainMenu> a <xref:System.Windows.Forms.ContextMenu> se zachovají pro zpětnou kompatibilitu a budoucí použití, pokud si zvolíte.</span><span class="sxs-lookup"><span data-stu-id="25201-103">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="25201-104"><xref:System.Windows.Forms.NotifyIcon> Součást zobrazí ikonu v oznamovací oblasti stav na hlavním panelu.</span><span class="sxs-lookup"><span data-stu-id="25201-104">The <xref:System.Windows.Forms.NotifyIcon> component displays an icon in the status notification area of the taskbar.</span></span> <span data-ttu-id="25201-105">Běžně aplikace umožňují klikněte pravým tlačítkem na tuto ikonu odesílat příkazy do aplikace, který představuje.</span><span class="sxs-lookup"><span data-stu-id="25201-105">Commonly, applications enable you to right-click this icon to send commands to the application it represents.</span></span> <span data-ttu-id="25201-106">Tím, že přidružíte <xref:System.Windows.Forms.ContextMenu> součásti s <xref:System.Windows.Forms.NotifyIcon> součásti, tato funkce můžete přidat do vaší aplikace.</span><span class="sxs-lookup"><span data-stu-id="25201-106">By associating a <xref:System.Windows.Forms.ContextMenu> component with the <xref:System.Windows.Forms.NotifyIcon> component, you can add this functionality to your applications.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="25201-107">Pokud chcete minimalizovat při spuštění při zobrazování instanci aplikace <xref:System.Windows.Forms.NotifyIcon> součásti na hlavním panelu nastavit hlavní formulář <xref:System.Windows.Forms.Form.WindowState%2A> vlastnost, která má <xref:System.Windows.Forms.FormWindowState.Minimized> a ujistěte se, <xref:System.Windows.Forms.NotifyIcon> součásti <xref:System.Windows.Forms.NotifyIcon.Visible%2A> vlastnost je nastavena na `true`.</span><span class="sxs-lookup"><span data-stu-id="25201-107">If you want your application to be minimized at startup while displaying an instance of the <xref:System.Windows.Forms.NotifyIcon> component in the taskbar, set the main form's <xref:System.Windows.Forms.Form.WindowState%2A> property to <xref:System.Windows.Forms.FormWindowState.Minimized> and be sure the <xref:System.Windows.Forms.NotifyIcon> component's <xref:System.Windows.Forms.NotifyIcon.Visible%2A> property is set to `true`.</span></span>  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-at-design-time"></a><span data-ttu-id="25201-108">Chcete-li přidružení místní nabídky ke komponentě NotifyIcon v době návrhu</span><span class="sxs-lookup"><span data-stu-id="25201-108">To associate a shortcut menu with the NotifyIcon component at design time</span></span>  
  
1.  <span data-ttu-id="25201-109">Přidat <xref:System.Windows.Forms.NotifyIcon> součásti do svého formuláře a nastavte důležité vlastnosti, jako je třeba <xref:System.Windows.Forms.NotifyIcon.Icon%2A> a <xref:System.Windows.Forms.NotifyIcon.Visible%2A> vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="25201-109">Add a <xref:System.Windows.Forms.NotifyIcon> component to your form, and set the important properties, such as the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> and <xref:System.Windows.Forms.NotifyIcon.Visible%2A> properties.</span></span>  
  
     <span data-ttu-id="25201-110">Další informace najdete v tématu [postupy: přidání ikon aplikací do TaskBar se součástí Windows Forms NotifyIcon](../../../../docs/framework/winforms/controls/app-icons-to-the-taskbar-with-wf-notifyicon.md).</span><span class="sxs-lookup"><span data-stu-id="25201-110">For more information, see [How to: Add Application Icons to the TaskBar with the Windows Forms NotifyIcon Component](../../../../docs/framework/winforms/controls/app-icons-to-the-taskbar-with-wf-notifyicon.md).</span></span>  
  
2.  <span data-ttu-id="25201-111">Přidat <xref:System.Windows.Forms.ContextMenu> součásti do svého formuláře systému Windows.</span><span class="sxs-lookup"><span data-stu-id="25201-111">Add a <xref:System.Windows.Forms.ContextMenu> component to your Windows Form.</span></span>  
  
     <span data-ttu-id="25201-112">Přidání položek nabídky do místní nabídky představující příkazy, že které chcete zpřístupnit v době běhu.</span><span class="sxs-lookup"><span data-stu-id="25201-112">Add menu items to the shortcut menu representing the commands you want to make available at run time.</span></span> <span data-ttu-id="25201-113">Toto je také vhodná doba na vylepšení nabídky přidat do těchto položek nabídky, jako je například přístupové klíče.</span><span class="sxs-lookup"><span data-stu-id="25201-113">This is also a good time to add menu enhancements to these menu items, such as access keys.</span></span>  
  
3.  <span data-ttu-id="25201-114">Nastavte <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> vlastnost <xref:System.Windows.Forms.NotifyIcon> součásti do místní nabídky, které jste přidali.</span><span class="sxs-lookup"><span data-stu-id="25201-114">Set the <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> property of the <xref:System.Windows.Forms.NotifyIcon> component to the shortcut menu that you added.</span></span>  
  
     <span data-ttu-id="25201-115">S touto sadou vlastností místní nabídce se zobrazí po kliknutí na ikonu na hlavním panelu.</span><span class="sxs-lookup"><span data-stu-id="25201-115">With this property set, the shortcut menu will be displayed when the icon on the taskbar is clicked.</span></span>  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-programmatically"></a><span data-ttu-id="25201-116">Chcete-li přidružení místní nabídky ke komponentě NotifyIcon prostřednictvím kódu programu</span><span class="sxs-lookup"><span data-stu-id="25201-116">To associate a shortcut menu with the NotifyIcon component programmatically</span></span>  
  
1.  <span data-ttu-id="25201-117">Vytvoření instance <xref:System.Windows.Forms.NotifyIcon> – třída a <xref:System.Windows.Forms.ContextMenu> třídě, ať nastavení vlastností jsou nezbytné pro aplikaci (<xref:System.Windows.Forms.NotifyIcon.Icon%2A> a <xref:System.Windows.Forms.NotifyIcon.Visible%2A> vlastnosti pro <xref:System.Windows.Forms.NotifyIcon> součásti, položky nabídky pro <xref:System.Windows.Forms.ContextMenu> komponenta).</span><span class="sxs-lookup"><span data-stu-id="25201-117">Create an instance of the <xref:System.Windows.Forms.NotifyIcon> class and a <xref:System.Windows.Forms.ContextMenu> class, with whatever property settings are necessary for the application (<xref:System.Windows.Forms.NotifyIcon.Icon%2A> and <xref:System.Windows.Forms.NotifyIcon.Visible%2A> properties for the <xref:System.Windows.Forms.NotifyIcon> component, menu items for the <xref:System.Windows.Forms.ContextMenu> component).</span></span>  
  
2.  <span data-ttu-id="25201-118">Nastavte <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> vlastnost <xref:System.Windows.Forms.NotifyIcon> součásti do místní nabídky, které jste přidali.</span><span class="sxs-lookup"><span data-stu-id="25201-118">Set the <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> property of the <xref:System.Windows.Forms.NotifyIcon> component to the shortcut menu that you added.</span></span>  
  
     <span data-ttu-id="25201-119">S touto sadou vlastností místní nabídce se zobrazí po kliknutí na ikonu na hlavním panelu.</span><span class="sxs-lookup"><span data-stu-id="25201-119">With this property set, the shortcut menu will be displayed when the icon on the taskbar is clicked.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="25201-120">Následující příklad kódu vytvoří strukturu základní nabídky.</span><span class="sxs-lookup"><span data-stu-id="25201-120">The following code example creates a basic menu structure.</span></span> <span data-ttu-id="25201-121">Musíte se k přizpůsobení možnosti nabídky na ty, které aplikace, které vyvíjíte přizpůsobit.</span><span class="sxs-lookup"><span data-stu-id="25201-121">You will need to customize the menu choices to those that fit the application you are developing.</span></span> <span data-ttu-id="25201-122">Kromě toho můžete napsat kód pro zpracování <xref:System.Windows.Forms.MenuItem.Click> události pro tyto položky nabídky.</span><span class="sxs-lookup"><span data-stu-id="25201-122">Additionally, you will want to write code to handle the <xref:System.Windows.Forms.MenuItem.Click> events for these menu items.</span></span>  
  
    ```vb  
    Public ContextMenu1 As New ContextMenu  
    Public NotifyIcon1 As New NotifyIcon  
  
    Public Sub CreateIconMenuStructure()  
       ' Add menu items to shortcut menu.  
       ContextMenu1.MenuItems.Add("&Open Application")  
       ContextMenu1.MenuItems.Add("S&uspend Application")  
       ContextMenu1.MenuItems.Add("E&xit")  
  
       ' Set properties of NotifyIcon component.  
       NotifyIcon1.Icon = New System.Drawing.Icon _   
          (System.Environment.GetFolderPath _   
          (System.Environment.SpecialFolder.Personal)  _   
          & "\Icon.ico")  
       NotifyIcon1.Text = "Right-click me!"  
       NotifyIcon1.Visible = True  
       NotifyIcon1.ContextMenu = ContextMenu1  
    End Sub  
    ```  
  
```csharp  
public NotifyIcon notifyIcon1 = new NotifyIcon();  
public ContextMenu contextMenu1 = new ContextMenu();  
  
public void createIconMenuStructure()  
{  
   // Add menu items to shortcut menu.  
   contextMenu1.MenuItems.Add("&Open Application");  
   contextMenu1.MenuItems.Add("S&uspend Application");  
   contextMenu1.MenuItems.Add("E&xit");  
  
   // Set properties of NotifyIcon component.  
   notifyIcon1.Icon = new System.Drawing.Icon  
      (System.Environment.GetFolderPath  
      (System.Environment.SpecialFolder.Personal)  
      + @"\Icon.ico");  
   notifyIcon1.Visible = true;  
   notifyIcon1.Text = "Right-click me!";  
   notifyIcon1.Visible = true;  
   notifyIcon1.ContextMenu = contextMenu1;  
}  
```  
  
```cpp  
public:  
   System::Windows::Forms::NotifyIcon ^ notifyIcon1;  
   System::Windows::Forms::ContextMenu ^ contextMenu1;  
  
   void createIconMenuStructure()  
   {  
      // Add menu items to shortcut menu.  
      contextMenu1->MenuItems->Add("&Open Application");  
      contextMenu1->MenuItems->Add("S&uspend Application");  
      contextMenu1->MenuItems->Add("E&xit");  
  
      // Set properties of NotifyIcon component.  
      notifyIcon1->Icon = gcnew System::Drawing::Icon  
          (String::Concat(System::Environment::GetFolderPath  
          (System::Environment::SpecialFolder::Personal),  
          "\\Icon.ico"));  
      notifyIcon1->Text = "Right-click me!";  
      notifyIcon1->Visible = true;  
      notifyIcon1->ContextMenu = contextMenu1;  
   }  
```  
  
> [!NOTE]
>  <span data-ttu-id="25201-123">Je třeba inicializovat `notifyIcon1` a `contextMenu1,` tu lze v konstruktoru formuláře včetně následující příkazy:</span><span class="sxs-lookup"><span data-stu-id="25201-123">You must initialize `notifyIcon1` and `contextMenu1,` which you can do by including the following statements in the constructor of your form:</span></span>  
  
```cpp  
notifyIcon1 = gcnew System::Windows::Forms::NotifyIcon();  
contextMenu1 = gcnew System::Windows::Forms::ContextMenu();  
```  
  
## <a name="see-also"></a><span data-ttu-id="25201-124">Viz také</span><span class="sxs-lookup"><span data-stu-id="25201-124">See Also</span></span>  
 <xref:System.Windows.Forms.NotifyIcon>  
 <xref:System.Windows.Forms.NotifyIcon.Icon%2A>  
 [<span data-ttu-id="25201-125">Postupy: přidání ikon aplikací do TaskBar se Windows Forms NotifyIcon – komponenta</span><span class="sxs-lookup"><span data-stu-id="25201-125">How to: Add Application Icons to the TaskBar with the Windows Forms NotifyIcon Component</span></span>](../../../../docs/framework/winforms/controls/app-icons-to-the-taskbar-with-wf-notifyicon.md)  
 [<span data-ttu-id="25201-126">NotifyIcon – komponenta</span><span class="sxs-lookup"><span data-stu-id="25201-126">NotifyIcon Component</span></span>](../../../../docs/framework/winforms/controls/notifyicon-component-windows-forms.md)  
 [<span data-ttu-id="25201-127">NotifyIcon – přehled komponenty</span><span class="sxs-lookup"><span data-stu-id="25201-127">NotifyIcon Component Overview</span></span>](../../../../docs/framework/winforms/controls/notifyicon-component-overview-windows-forms.md)
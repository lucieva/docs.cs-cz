---
title: 'Postupy: Skrývání ToolStripMenuItems pomocí Návrháře'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], hiding menu items in designer
- MenuStrip control [Windows Forms], hiding menu items in designer
- menu items [Windows Forms], hiding
ms.assetid: 8f1b057e-3d8a-4f11-88df-935f7b29a836
ms.openlocfilehash: 37371269ef9db929573efff0a8e62c86a51b2c35
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/04/2018
ms.locfileid: "43523574"
---
# <a name="how-to-hide-toolstripmenuitems-using-the-designer"></a>Postupy: Skrývání ToolStripMenuItems pomocí Návrháře
Skrytí položek nabídky je způsob, jak ovládací prvek uživatelského rozhraní (UI) aplikace a omezit uživatelských příkazů. Často můžete skrýt celou nabídku, když jsou všechny položky nabídky na něm není k dispozici. To představuje méně rozptýlení pro daného uživatele. Kromě toho můžete chtít skrýt i zakázat nabídky nebo položku nabídky, protože skrytí samostatně nebrání uživateli přístup k příkazu nabídky pomocí klávesové zkratky. Další informace o deaktivace položek nabídky, naleznete v tématu [postupy: zakázání ToolStripMenuItems pomocí návrháře](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems-using-the-designer.md).  
  
> [!NOTE]
>  Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici. Chcete-li změnit nastavení, zvolte **nastavení importu a exportu** na **nástroje** nabídky. Další informace najdete v tématu [přizpůsobení integrovaného vývojového prostředí sady Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-hide-a-top-level-menu-and-its-submenu-items"></a>Chcete-li skrýt nabídek nejvyšší úrovně a jeho podnabídky položek  
  
1.  Vyberte položku nejvyšší úrovně nabídky a nastavte jeho <xref:System.Windows.Forms.ToolStripItem.Visible%2A> nebo <xref:System.Windows.Forms.ToolStripItem.Available%2A> vlastnost `false`.  
  
     Když skryjete položky nabídek nejvyšší úrovně, všechny položky nabídky v rámci této nabídky jsou rovněž skryté. Pokud kliknete na jiném zařízení, než na <xref:System.Windows.Forms.MenuStrip> po nastavení <xref:System.Windows.Forms.ToolStripItem.Visible%2A> k `false`, celý nabídka nejvyšší úrovně a její podnabídku položky zmizí z formuláře, tedy zobrazí vliv za běhu akce. Aby se zobrazila položka skrytá nabídek nejvyšší úrovně v době návrhu, klikněte na <xref:System.Windows.Forms.MenuStrip> v **komponent**v **Osnova dokumentu**, nebo v horní části mřížku vlastností.  
  
> [!NOTE]
>  Jen zřídka se skrýt celou nabídku s výjimkou více nabídky podřízené ve scénáři sloučení dokumentu (MDI interface).  
  
### <a name="to-hide-a-submenu-item"></a>Chcete-li skrýt položku podnabídky  
  
1.  Vyberte položku dílčí nabídky a nastavte jeho <xref:System.Windows.Forms.ToolStripItem.Visible%2A> vlastnost `false`.  
  
     Při skrytí položky podnabídky zůstává viditelná ve formuláři v době návrhu tak, aby ji snadno vybrat pro další práci. Ve skutečnosti to bude skrytá za běhu.  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Windows.Forms.ToolStripItem.Visible%2A>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>  
 <xref:System.Windows.Forms.ToolStripItem.Available%2A>  
 <xref:System.Windows.Forms.ToolStripMenuItem.Overflow%2A>  
 [Přehled ovládacího prvku MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)  
 [Postupy: Zákaz ToolStripMenuItems pomocí Návrháře](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems-using-the-designer.md)

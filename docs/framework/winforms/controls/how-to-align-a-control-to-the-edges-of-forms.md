---
title: 'Postupy: Zarovnávání ovládacího prvku k okrajům formulářů'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Dock property [Windows Forms], aligning controls (using code)
- forms [Windows Forms], aligning controls
- controls [Windows Forms], aligning on forms
- custom controls [Windows Forms], docking using code
ms.assetid: 5994cb59-242b-4e75-bd0e-62879c34d702
ms.openlocfilehash: a8571f668de2714511a8732772443a8897043cf2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/04/2018
ms.locfileid: "33526511"
---
# <a name="how-to-align-a-control-to-the-edges-of-forms"></a>Postupy: Zarovnávání ovládacího prvku k okrajům formulářů
Můžete provést kontrolu nad zarovnání na hranu svých formulářů podle nastavení <xref:System.Windows.Forms.Control.Dock%2A> vlastnost. Tato vlastnost určuje, kde vlastní ovládací prvek nachází ve formuláři. <xref:System.Windows.Forms.Control.Dock%2A> Vlastnost lze nastavit následující hodnoty:  
  
|Nastavení|Vliv na vlastní ovládací prvek|  
|-------------|----------------------------|  
|<xref:System.Windows.Forms.DockStyle.Bottom>|Překladišť k dolní části formuláře.|  
|<xref:System.Windows.Forms.DockStyle.Fill>|Doplní veškerý zbývající prostor ve tvaru.|  
|<xref:System.Windows.Forms.DockStyle.Left>|Přepraviště na levé straně formuláře.|  
|<xref:System.Windows.Forms.DockStyle.None>|Nepodporuje není ukotvení odkudkoli a zobrazí se v umístění určeném pomocí jeho <xref:System.Windows.Forms.Control.Location%2A> vlastnost.|  
|<xref:System.Windows.Forms.DockStyle.Right>|Přepraviště na pravé straně formuláře.|  
|<xref:System.Windows.Forms.DockStyle.Top>|Překladišť k horní části formuláře.|  
  
 Není poskytována podpora návrhu pro tuto funkci v sadě Visual Studio.  
  
### <a name="to-set-the-dock-property-for-your-control-at-run-time"></a>Nastavit vlastnost ukotvení pro ovládací prvek v době běhu  
  
1.  Nastavte <xref:System.Windows.Forms.Control.Dock%2A> vlastnost na odpovídající hodnotu v kódu.  
  
    ```vb  
    ' To set the Dock property internally.  
    Me.Dock = DockStyle.Top  
    ' To set the Dock property from another object.  
    UserControl1.Dock = DockStyle.Top  
    ```  
  
    ```csharp  
    // To set the Dock property internally.  
    this.Dock = DockStyle.Top;  
    // To set the Dock property from another object.  
    UserControl1.Dock = DockStyle.Top;  
    ```  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=nameWithType>  
 [Vývoj vlastních ovládacích prvků Windows Forms pomocí rozhraní .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 [Postupy: Ukotvení podřízených ovládacích prvků v ovládacím prvku FlowLayoutPanel](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)  
 [Postupy: Ukotvení podřízených ovládacích prvků v ovládacím prvku TableLayoutPanel](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 [Přehled vlastnosti AutoSize](../../../../docs/framework/winforms/controls/autosize-property-overview.md)

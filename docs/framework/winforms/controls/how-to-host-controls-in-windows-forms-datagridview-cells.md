---
title: 'Postupy: Umisťování ovládacích prvků do buněk Windows Forms DataGridView'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], hosting in cells
- DataGridView control [Windows Forms], hosting controls in cells
- cells [Windows Forms], hosting controls
ms.assetid: e79a9d4e-64ec-41f5-93ec-f5492633cbb2
ms.openlocfilehash: 29ffcc205d8175551aee5184cf44306fa5d3b5a0
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/05/2018
ms.locfileid: "43799811"
---
# <a name="how-to-host-controls-in-windows-forms-datagridview-cells"></a>Postupy: Umisťování ovládacích prvků do buněk Windows Forms DataGridView
<xref:System.Windows.Forms.DataGridView> Ovládací prvek obsahuje několik typů sloupce, povolení uživatelům zadávat a upravovat hodnoty v mnoha různými způsoby. Pokud tyto typy sloupců nevyhovují vašim potřebám zadávání dat, ale můžete vytvořit vlastní typy sloupců s buňky, které jsou hostiteli ovládací prvky, které si vyberete. Chcete-li to provést, je nutné definovat třídy, které jsou odvozeny z <xref:System.Windows.Forms.DataGridViewColumn> a <xref:System.Windows.Forms.DataGridViewCell>. Musíte také definovat třídu, která je odvozena z <xref:System.Windows.Forms.Control> a implementuje <xref:System.Windows.Forms.IDataGridViewEditingControl> rozhraní.  
  
 Následující příklad kódu ukazuje, jak vytvořit sloupec kalendáře. Buňkách tohoto sloupce zobrazení dat v buňkách běžný text, ale když uživatel upravuje buňky, <xref:System.Windows.Forms.DateTimePicker> ovládací prvek se zobrazí. Aby bylo možné vyhnout se nutnosti znovu implementovat funkčnost zobrazení textového pole `CalendarCell` třída odvozena z <xref:System.Windows.Forms.DataGridViewTextBoxCell> třídy namísto dědění <xref:System.Windows.Forms.DataGridViewCell> třídy přímo.  
  
> [!NOTE]
>  Pokud odvozujete od <xref:System.Windows.Forms.DataGridViewCell> nebo <xref:System.Windows.Forms.DataGridViewColumn> a přidání nových vlastností do odvozené třídy, je nutné přepsat `Clone` metoda kopírování nové vlastnosti během operace klonování. Měli byste také zavolat základní třídu `Clone` metodu tak, aby vlastností základní třídy jsou zkopírovány do nové buňky nebo sloupec.  
  
## <a name="example"></a>Příklad  
 [!code-csharp[System.Windows.Forms.DataGridViewCalendarColumn#000](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCalendarColumn/CS/datagridviewcalendarcolumn.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridViewCalendarColumn#000](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCalendarColumn/VB/datagridviewcalendarcolumn.vb#000)]  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 V následujícím příkladu vyžaduje:  
  
-   Odkazy na sestavení systému a System.Windows.Forms.  
  
 Informace o vytváření tento příklad z příkazového řádku pro Visual Basic nebo Visual C# najdete v tématu [sestavení z příkazového řádku](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) nebo [sestavení pomocí příkazového řádku csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Tento příklad v sadě Visual Studio můžete také vytvořit vložením kódu do nového projektu.  Viz také [postupy: zkompilování a spuštění dokončení Windows Forms kód příklad pomocí sady Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 <xref:System.Windows.Forms.DataGridViewCell>  
 <xref:System.Windows.Forms.DataGridViewTextBoxCell>  
 <xref:System.Windows.Forms.IDataGridViewEditingControl>  
 <xref:System.Windows.Forms.DateTimePicker>  
 [Přizpůsobení ovládacího prvku Windows Forms DataGridView](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)  
 [Architektura ovládacího prvku DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-architecture-windows-forms.md)  
 [Typy sloupců v ovládacím prvku Windows Forms DataGridView](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)

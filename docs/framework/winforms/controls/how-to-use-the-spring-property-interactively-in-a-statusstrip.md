---
title: 'Postupy: Interaktivní používání vlastnosti Spring v prvku StatusStrip'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- StatusStrip control [Windows Forms]
- ToolStrip control [Windows Forms]
- status bars [Windows Forms], examples
- Spring property [Windows Forms]
ms.assetid: 18bde842-a93c-48dd-9db3-15738a1775ce
ms.openlocfilehash: 3319771cfcf671f5457bd3e95d264a694f9fa1c6
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/05/2018
ms.locfileid: "43744187"
---
# <a name="how-to-use-the-spring-property-interactively-in-a-statusstrip"></a>Postupy: Interaktivní používání vlastnosti Spring v prvku StatusStrip
Můžete použít <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> vlastnost na pozici <xref:System.Windows.Forms.ToolStripStatusLabel> v ovládacím prvku <xref:System.Windows.Forms.StatusStrip> ovládacího prvku. <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> Vlastnost určuje, zda <xref:System.Windows.Forms.ToolStripStatusLabel> ovládací prvek automaticky vyplní dostupné místo na <xref:System.Windows.Forms.StatusStrip> ovládacího prvku.  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje, jak používat <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> vlastnost na pozici <xref:System.Windows.Forms.ToolStripStatusLabel> v ovládacím prvku <xref:System.Windows.Forms.StatusStrip> ovládacího prvku. <xref:System.Windows.Forms.ToolStripItem.Click> Obslužná rutina události provádí výhradně- nebo operace (XOR) Chcete-li přepnout hodnotu <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> vlastnost.  
  
 Použít tento příklad kódu, kompilaci a spuštění aplikace a pak klikněte na **doprostřed (Spring)** na <xref:System.Windows.Forms.StatusStrip> ovládacího prvku na hodnotu přepínače <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> vlastnost.  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#50](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#50)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#50](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#50)]  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 Tento příklad vyžaduje:  
  
-   Odkazy na sestavení System.Design System.Drawing a System.Windows.Forms.  
  
 Informace o vytváření použijeme příklad z příkazového řádku pro visual Basic nebo Visual C# najdete v tématu [sestavení z příkazového řádku](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) nebo [sestavení pomocí příkazového řádku csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Tento příklad v sadě Visual Studio můžete také vytvořit vložením kódu do nového projektu.  Viz také [postupy: zkompilování a spuštění dokončení Windows Forms kód příklad pomocí sady Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Windows.Forms.ToolStripStatusLabel>  
 <xref:System.Windows.Forms.StatusStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStripItem>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [Ovládací prvek ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)

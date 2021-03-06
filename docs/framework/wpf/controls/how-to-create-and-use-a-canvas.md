---
title: 'Postupy: Vytvoření a použití plátna'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Canvas
- Canvas control [WPF], creating
- Canvas control [WPF], using
ms.assetid: 420b9487-9a15-477c-9489-a22a4dec7779
ms.openlocfilehash: c3ddb5171ca8ded053d56fde26ab86ebc4ae5cb2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/04/2018
ms.locfileid: "33552841"
---
# <a name="how-to-create-and-use-a-canvas"></a>Postupy: Vytvoření a použití plátna
Tento příklad ukazuje, jak vytvořit a použít instanci <xref:System.Windows.Controls.Canvas>.  
  
## <a name="example"></a>Příklad  
 Následující příklad explicitně umisťuje dva <xref:System.Windows.Controls.TextBlock> elementy pomocí <xref:System.Windows.Controls.Canvas.SetTop%2A> a <xref:System.Windows.Controls.Canvas.SetLeft%2A> metody <xref:System.Windows.Controls.Canvas>. Tento příklad také přiřadí <xref:System.Windows.Controls.Control.Background%2A> barva `LightSteelBlue` k <xref:System.Windows.Controls.Canvas>.  
  
> [!NOTE]
>  Při použití [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] do polohy <xref:System.Windows.Controls.TextBlock> elementy, použijte <xref:System.Windows.Controls.Canvas.Top%2A> a <xref:System.Windows.Controls.Canvas.Left%2A> vlastnosti.  
  
 [!code-csharp[CanvasCode#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasCode/CSharp/Canvas_Code.cs#1)]
 [!code-vb[CanvasCode#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasCode/VisualBasic/canvas_vb.vb#1)]  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Windows.Controls.Canvas>  
 <xref:System.Windows.Controls.TextBlock>  
 <xref:System.Windows.Controls.Canvas.SetTop%2A>  
 <xref:System.Windows.Controls.Canvas.SetLeft%2A>  
 <xref:System.Windows.Controls.Canvas.Top%2A>  
 <xref:System.Windows.Controls.Canvas.Left%2A>  
 [Přehled panelu](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [Témata s postupy](../../../../docs/framework/wpf/controls/canvas-how-to-topics.md)

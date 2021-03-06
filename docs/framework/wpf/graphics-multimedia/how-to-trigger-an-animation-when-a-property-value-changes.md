---
title: 'Postupy: Spuštění animace při změně hodnoty vlastnosti'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], starting when property values change
- triggering animation [WPF]
- Storyboards [WPF], starting when property values change
ms.assetid: 12399c21-0300-4f4f-9e3a-d92d9907e5f5
ms.openlocfilehash: f127f00445a587ee097faa6bed28e124690de10e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561314"
---
# <a name="how-to-trigger-an-animation-when-a-property-value-changes"></a>Postupy: Spuštění animace při změně hodnoty vlastnosti
Tento příklad ukazuje, jak používat <xref:System.Windows.Trigger> zahájíte <xref:System.Windows.Media.Animation.Storyboard> při změně hodnoty vlastnosti. Můžete použít <xref:System.Windows.Trigger> uvnitř <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate>, nebo <xref:System.Windows.DataTemplate>.  
  
## <a name="example"></a>Příklad  
 Následující příklad používá <xref:System.Windows.Trigger> pro animaci <xref:System.Windows.UIElement.Opacity%2A> z <xref:System.Windows.Controls.Button> při jeho <xref:System.Windows.UIElement.IsMouseOver%2A> vlastnost stane `true`.  
  
 [!code-xaml[AnimatePropertyStoryboards#PropertyTriggerExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/AnimatePropertyStoryboards/XAML/PropertyTriggerExample.xaml#propertytriggerexample)]  
  
 Použité vlastností animace <xref:System.Windows.Trigger> objekty chovat způsobem složitější než <xref:System.Windows.EventTrigger> animací nebo animace spuštěna pomocí <xref:System.Windows.Media.Animation.Storyboard> metody.  Jejich "aby handoff" animací definované jiná <xref:System.Windows.Trigger> objekty, ale tvoří s <xref:System.Windows.EventTrigger> a metoda aktivované animace.  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Windows.Trigger>  
 [Přehled způsobů animace vlastností](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)  
 [Přehled scénářů](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)

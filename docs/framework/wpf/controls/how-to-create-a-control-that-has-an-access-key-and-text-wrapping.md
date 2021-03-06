---
title: 'Postupy: Vytvoření ovládacího prvku obsahujícího přístupový klíč a zalamování textu'
ms.date: 03/30/2017
helpviewer_keywords:
- access keys [WPF], control for
- controls [WPF], text wrapping
- wrapping text [WPF]
- keys [WPF], control for
- controls [WPF], access keys
- text wrapping [WPF]
ms.assetid: 205099d9-2551-4302-a25e-a15af9f67e04
ms.openlocfilehash: bc170334496ca4c2a2028b9c493385674d235ca6
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/05/2018
ms.locfileid: "43745606"
---
# <a name="how-to-create-a-control-that-has-an-access-key-and-text-wrapping"></a>Postupy: Vytvoření ovládacího prvku obsahujícího přístupový klíč a zalamování textu
Tento příklad ukazuje, jak vytvořit ovládací prvek, který má přístupové klávesy a podporuje zalamování textu. V příkladu se používá <xref:System.Windows.Controls.Label> ovládací prvek pro ilustraci těchto konceptů.  
  
## <a name="example"></a>Příklad  
 **Přidat zalamování textu popisku**  
  
 <xref:System.Windows.Controls.Label> Ovládací prvek nepodporuje zalamování textu. Pokud potřebujete popisek, který obtéká přes více řádků, je možné vnořovat jiný element, který nepodporuje text zabalení a vložit element uvnitř popisek. Následující příklad ukazuje způsob použití <xref:System.Windows.Controls.TextBlock> má být popisek, který obtéká několik řádků textu.  
  
 [!code-xaml[LabelSnippet#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LabelSnippet/CS/Pane1.xaml#5)]  
  
 **Přidat přístupový klíč a zalamování textu do popisku**  
  
 Pokud potřebujete <xref:System.Windows.Controls.Label> , který má přístupový klíč (symbol), použijte <xref:System.Windows.Controls.AccessText> element, který se nachází uvnitř <xref:System.Windows.Controls.Label>.  
  
 Ovládací prvky jako například <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.RadioButton>, <xref:System.Windows.Controls.CheckBox>, <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.TabItem>, <xref:System.Windows.Controls.Expander>, a <xref:System.Windows.Controls.GroupBox> mají výchozí šablony ovládacího prvku. Tyto šablony obsahují <xref:System.Windows.Controls.ContentPresenter>. Jedna z vlastností, které můžete nastavit na <xref:System.Windows.Controls.ContentPresenter> je <xref:System.Windows.Controls.ContentPresenter.RecognizesAccessKey%2A>= "true", který můžete použít k určení přístupového klíče pro ovládací prvek.  
  
 Následující příklad ukazuje, jak vytvořit <xref:System.Windows.Controls.Label> , který má přístupové klávesy a podporuje zalamování textu. Chcete-li povolit zalamování textu, příklad nastaví <xref:System.Windows.Controls.AccessText.TextWrapping%2A> vlastnosti a používá znak podtržení určit přístupový klíč. (Znak, který následuje znak podtržení se přístupový klíč).  
  
 [!code-xaml[LabelSnippet#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LabelSnippet/CS/Pane1.xaml#4)]  
  
## <a name="see-also"></a>Viz také  
 [Postupy: nastavení cílové vlastnosti popisku](https://msdn.microsoft.com/library/b24c6977-ebcb-4855-a9bb-3fd4435af8f8)

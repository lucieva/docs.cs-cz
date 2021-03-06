---
title: 'Postupy: Použití zdrojů aplikace'
ms.date: 03/30/2017
helpviewer_keywords:
- application resources [WPF]
- resources [WPF], application resources
ms.assetid: 507ea937-5191-406b-8797-0a3d9f94156d
ms.openlocfilehash: 4305c49c4322d164e2481c1508dda7c038c14694
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/04/2018
ms.locfileid: "33544154"
---
# <a name="how-to-use-application-resources"></a>Postupy: Použití zdrojů aplikace
Tento příklad ukazuje, jak používat prostředky aplikace.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje soubor definice aplikace. Definiční soubor aplikace definuje oddíl prostředků (hodnotu <xref:System.Windows.Application.Resources%2A> vlastnost). Všechny ostatní stránky, které jsou součástí aplikace může být přístup k prostředkům, které jsou definované na úrovni aplikace. V takovém případě je prostředek deklarované stylu. Vzhledem k tomu, že dokončení styl, který obsahuje šablonu řízení může být náročná, v tomto příkladu vynechá řízení šablonu, která je definována v rámci <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> Metoda setter vlastnosti stylu.  
  
 [!code-xaml[ResourcesApplication#PreTemplateResource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/app.xaml#pretemplateresource)]  
[!code-xaml[ResourcesApplication#PostTemplateResource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/app.xaml#posttemplateresource)]  
  
 Následující příklad ukazuje [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] stránky, která odkazuje na úrovni aplikace prostředek, který je definován v předchozím příkladu. Prostředek se odkazuje pomocí [StaticResource – rozšíření značek](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) určující prostředků jedinečný klíč pro požadovaný prostředek. Žádný prostředek s klíčem "GelButton" nachází na aktuální stránce, takže oboru vyhledávání prostředků pro požadovaný prostředek pokračuje mimo aktuální stránku a do definované prostředků na úrovni aplikace.  
  
 [!code-xaml[ResourcesApplication#ConsumingPage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/page1.xaml#consumingpage)]  
  
## <a name="see-also"></a>Viz také  
 [Prostředky XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [Přehled správy aplikací](../../../../docs/framework/wpf/app-development/application-management-overview.md)  
 [Témata s postupy](../../../../docs/framework/wpf/advanced/resources-how-to-topics.md)

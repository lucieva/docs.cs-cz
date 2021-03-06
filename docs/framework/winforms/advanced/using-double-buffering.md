---
title: Použití dvojitého ukládání do vyrovnávací paměti
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], double buffering
- double buffering
- flicker [Windows Forms], reducing in Windows Forms
- buffering [Windows Forms], double buffering
ms.assetid: dc484e33-7101-4e4b-ada5-d3c96155fbcd
ms.openlocfilehash: 9b09210eba0ac3a141219a7cdbff15f22c6ed003
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/04/2018
ms.locfileid: "33523907"
---
# <a name="using-double-buffering"></a>Použití dvojitého ukládání do vyrovnávací paměti
Grafiky s dvojitou vyrovnávací pamětí můžete použít ke snížení blikání v aplikacích, které obsahují komplexní vykreslovací operace. Rozhraní .NET Framework obsahuje integrovanou podporu pro dvojité ukládání do vyrovnávací paměti, nebo můžete spravovat a vykreslení grafiky ručně.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Grafiky s dvojitou vyrovnávací pamětí](../../../../docs/framework/winforms/advanced/double-buffered-graphics.md)  
 Představuje dvojité vyrovnávací paměti koncept a jsou podrobněji popsány dále rozhraní .NET Framework podporu.  
  
 [Postupy: Omezení blikání grafiky dvojitým uložením do vyrovnávací paměti pro formuláře a ovládací prvky](../../../../docs/framework/winforms/advanced/how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md)  
 Ukazuje, jak použít výchozí dvojité ukládání do vyrovnávací paměti podpora v rozhraní .NET Framework.  
  
 [Postupy: Ruční správa grafiky uložené do vyrovnávací paměti](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md)  
 Ukazuje, jak spravovat dvojité vyrovnávací paměti v aplikacích.  
  
 [Postupy: Ruční zobrazení grafiky uložené do vyrovnávací paměti](../../../../docs/framework/winforms/advanced/how-to-manually-render-buffered-graphics.md)  
 Ukazuje, jak k vykreslení grafiky s dvojitou vyrovnávací pamětí.  
  
## <a name="reference"></a>Odkaz  
 <xref:System.Windows.Forms.Control.SetStyle%2A> ,  
 Ovládací prvek metoda, která umožňuje dvojité ukládání do vyrovnávací paměti.  
  
 <xref:System.Drawing.BufferedGraphicsContext> ,  
 Poskytuje metody pro vytváření grafických vyrovnávací paměti.  
  
 <xref:System.Drawing.BufferedGraphicsManager>  
 Poskytuje přístup k grafiky uložené ve vyrovnávací paměti kontextu pro doménu aplikace.

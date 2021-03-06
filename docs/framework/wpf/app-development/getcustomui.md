---
title: GetCustomUI
ms.date: 03/30/2017
helpviewer_keywords:
- custom error messages [WPF]
ms.assetid: e55180fc-35bb-4f80-a136-772b5eb3e4e5
ms.openlocfilehash: ff68c30c4e58cebb70c59352593d7b084413dce8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/04/2018
ms.locfileid: "33548643"
---
# <a name="getcustomui"></a>GetCustomUI
Voláno rozhraním PresentationHost.exe získat vlastní průběh a chybové zprávy z hostitele, pokud je implementována.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT GetCustomUI( [out] BSTR* pwzProgressAssemblyName, [out] BSTR* pwzProgressClassName, [out] BSTR* pwzErrorAssemblyName, [out] BSTR* pwzErrorClassName );  
```  
  
#### <a name="parameters"></a>Parametry  
 `pwzProgressAssemblyName`  
  
 [out] Ukazatel na sestavení, které obsahuje zadané hostitele průběh uživatelského rozhraní.  
  
 `pwzProgressClassName`  
  
 [out] Název třídy, která je ideálně uživatelského rozhraní průběhu zadané hostitele [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] soubor s <xref:System.Windows.Controls.Page> je jeho element nejvyšší úrovně. Tato třída se nachází v sestavení, která je zadána `pwzProgressAssemblyName`.  
  
 `pwzErrorAssemblyName`  
  
 [out] Ukazatel na sestavení, které obsahuje hostitele zadané chybě uživatelského rozhraní.  
  
 `pwzErrorClassName`  
  
 [out] Název třídy, která je uživatel zadaný hostitele chyby rozhraní, pokud možno soubor XAML s <xref:System.Windows.Controls.Page> je jeho element nejvyšší úrovně. Tato třída se nachází v sestavení, která je zadána `pwzErrorAssemblyName`.  
  
## <a name="property-valuereturn-value"></a>Hodnota vlastnosti / návratová hodnota  
 HRESULT: ignorovány.  
  
## <a name="remarks"></a>Poznámky  
 Hostitelskou aplikaci může mít specifické motiv, který nemusí vyhovovat PresentationHost.exe na výchozí uživatelská rozhraní. Pokud je to tento případ, můžete implementovat hostitelskou aplikaci [GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md) vrátí průběh a chyby uživatelského rozhraní pro PresentationHost.exe. PresentationHost.exe bude vždy volat [GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md) před použitím jeho výchozí uživatelská rozhraní.  
  
 Tato funkce je volána jednou během inicializace PresentationHost společnosti.  
  
## <a name="see-also"></a>Viz také  
 [IWpfHostSupport](../../../../docs/framework/wpf/app-development/iwpfhostsupport.md)

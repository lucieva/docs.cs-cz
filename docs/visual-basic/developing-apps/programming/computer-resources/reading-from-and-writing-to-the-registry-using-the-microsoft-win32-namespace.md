---
title: Čtení z registru a zápis do něj s použitím oboru názvů Microsoft.Win32 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- registry [Visual Basic]
ms.assetid: 4a0dcce0-c27b-4199-baa8-ee4528da6a56
ms.openlocfilehash: 6309f312ed05f48e65b19d8827322071cad1f6de
ms.sourcegitcommit: 8c6c62ba1eefa492701e264e41890ee20fae77a3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/20/2018
ms.locfileid: "42751910"
---
# <a name="reading-from-and-writing-to-the-registry-using-the-microsoftwin32-namespace-visual-basic"></a>Čtení z registru a zápis do něj s použitím oboru názvů Microsoft.Win32 (Visual Basic)
I když `My.Computer.Registry` by měl zahrnovat základní potřeb při programování proti registru, můžete použít také <xref:Microsoft.Win32.Registry> a <xref:Microsoft.Win32.RegistryKey> tříd v <xref:Microsoft.Win32> obor názvů [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].  
  
## <a name="keys-in-the-registry-class"></a>Klíče registru třídy  
 <xref:Microsoft.Win32.Registry> Třída poskytuje základní klíče registrů, které můžete použít pro přístup k podklíče a jejich hodnoty. Základní klíče jsou jen pro čtení. Následující tabulka uvádí a popisuje sedm klíčů vystavené <xref:Microsoft.Win32.Registry> třídy.  
  
|**Key**|**Popis**|  
|-------------|---------------------|  
|<xref:Microsoft.Win32.Registry.ClassesRoot>|Definuje typy dokumentů a vlastnosti související s těmito typy.|  
|<xref:Microsoft.Win32.Registry.CurrentConfig>|Obsahuje informace o konfiguraci hardwaru, které nejsou specifické pro uživatele.|  
|<xref:Microsoft.Win32.Registry.CurrentUser>|Obsahuje informace o aktuální uživatelské předvolby, jako jsou proměnné prostředí.|  
|<xref:Microsoft.Win32.Registry.DynData>|Obsahuje data dynamické registru, jako je například použít virtuální ovladače zařízení.|  
|<xref:Microsoft.Win32.Registry.LocalMachine>|Obsahuje pět podklíče (Hardware, SAM, zabezpečení, softwaru a systém), které obsahují konfigurační data v místním počítači.|  
|<xref:Microsoft.Win32.Registry.PerformanceData>|Obsahuje informace o výkonu pro softwarové součásti.|  
|<xref:Microsoft.Win32.Registry.Users>|Obsahuje informace o uživatelských předvolbách výchozí.|  
  
> [!IMPORTANT]
>  Je bezpečnější zapsat data do aktuálního uživatele (<xref:Microsoft.Win32.Registry.CurrentUser>) než do místního počítače (<xref:Microsoft.Win32.Registry.LocalMachine>). Podmínku, která se obvykle označuje jako "obsazení" vyvolá se při vytváření klíče dříve vytvořil jiný, potenciálně škodlivý, proces. Chcete-li tomu zabránit, použijte metodu, <xref:Microsoft.Win32.RegistryKey.GetValue%2A>, který vrací `Nothing` Pokud klíč ještě neexistuje.  
  
## <a name="reading-a-value-from-the-registry"></a>Čtení hodnoty z registru  
 Následující kód znázorňuje způsob čtení řetězce z HKEY_CURRENT_USER.  
  
 [!code-vb[VbResourceTasks#20](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/reading-from-and-writing-to-the-registry-using-the-microsoft-win32-namespace_1.vb)]  
  
 Následující kód načte, krocích a pak zapíše řetězec do klíče HKEY_CURRENT_USER.  
  
 [!code-vb[VbResourceTasks#21](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/reading-from-and-writing-to-the-registry-using-the-microsoft-win32-namespace_2.vb)]  
  
## <a name="see-also"></a>Viz také  
 <xref:System.SystemException>  
 <xref:System.ApplicationException>  
 <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>  
 [Příkaz Try...Catch...Finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [Čtení z registru a zápis do něj](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)  
 [Zabezpečení a registr](../../../../visual-basic/developing-apps/programming/computer-resources/security-and-the-registry.md)

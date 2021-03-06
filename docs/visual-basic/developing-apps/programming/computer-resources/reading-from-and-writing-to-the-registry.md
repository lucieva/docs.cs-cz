---
title: Čtení z registru a zápis do něj pomocí oboru názvů My (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My.Computer.Registry object, tasks
- registry [Visual Basic], writing to
- registry [Visual Basic], reading
ms.assetid: a13da106-185b-41d7-b23c-416da65e21e4
ms.openlocfilehash: 6ce05b956ebf9a544eb8c95165b0f709c694f334
ms.sourcegitcommit: 869b5832b667915ac4a5dd8c86b1109ed26b6c08
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/28/2018
ms.locfileid: "39332932"
---
# <a name="reading-from-and-writing-to-the-registry-visual-basic"></a>Čtení z registru a zápis do něj pomocí oboru názvů My (Visual Basic)
Toto téma popisuje úlohy a koncepční témata, které jsou spojeny s registrem.  
  
 Při programování v jazyce Visual Basic, můžete získat přístup k registru pomocí funkce poskytované jazyka Visual Basic nebo registru třídy rozhraní .NET Framework. Informace registru hostitele z operačního systému, stejně jako informace z aplikací hostovaných na počítači. Práce s registrem může ohrozit zabezpečení tím, že nevhodný přístup k systémovým prostředkům nebo chráněné informace.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Postupy: Vytvoření klíče registru a nastavení jeho hodnoty](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-create-a-registry-key-and-set-its-value.md)  
 Popisuje způsob použití `CreateSubKey` a `SetValue` metody `My.Computer.Registry` objekt k vytvoření klíče registru a nastavení jeho hodnoty.  
  
 [Postupy: Načtení hodnoty z klíče registru](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-read-a-value-from-a-registry-key.md)  
 Popisuje způsob použití `GetValue` metodu `My.Computer.Registry` objektu k načtení hodnoty z klíče registru.  
  
 [Postupy: Odstranění klíče z registru](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-delete-a-registry-key.md)  
 Popisuje způsob použití `DeleteSubKey` metodu `My.Computer.Registry.CurrentUser` vlastnosti k odstranění klíče z registru.  
  
 [Čtení z registru a zápis do něj s použitím oboru názvů Microsoft.Win32](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry-using-the-microsoft-win32-namespace.md)  
 Popisuje způsob použití `Registry` a `RegistryKey` třídy [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] pro přístup k registru.  
  
 [Zabezpečení a registr](../../../../visual-basic/developing-apps/programming/computer-resources/security-and-the-registry.md)  
 Tento článek popisuje problémy se zabezpečením týkajících se registru.  
  
## <a name="related-sections"></a>Související oddíly  
 <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>  
 Uvádí a vysvětluje členů `My.Computer.Registry` objektu.  
  
 <xref:Microsoft.Win32.Registry>  
 Obsahuje přehled nástroje `Registry` třídy společně s odkazy na jednotlivé klíče a členy.

---
title: Zachování prázdných znaků při načítání nebo analýze XML1
ms.date: 07/20/2015
ms.assetid: f3ff58c4-55aa-4fcd-b933-e3a2ee6e706c
ms.openlocfilehash: 019b4452bcd76fff462edab6a584cf5ae0276ee7
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/04/2018
ms.locfileid: "43514445"
---
# <a name="preserving-white-space-while-loading-or-parsing-xml"></a>Zachování prázdných znaků při načítání nebo analýze XML
Toto téma popisuje, jak řídit chování prázdných [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].  
  
 Běžný scénář, kdy je pro čtení odsazený XML, vytvoření stromu XML v paměti bez ostatní uzly text prázdné znaky (tedy ne zachování prázdné znaky), provádění některých operací na XML a pak uložte soubor XML s odsazením. Při serializaci XML s formátováním je zachována pouze významný prázdný znak ve stromové struktuře XML. Toto je výchozí chování pro [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].  
  
 Další z typických možností je číst a upravovat kód XML, který již byl záměrně odsazeny. Nebudete chtít změnit tento odsazení žádným způsobem. Chcete-li to provést v [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], zachovat mezer při načtení nebo analyzovat kód XML a zakázat formátování při serializaci kódu XML.  
  
 Toto téma popisuje chování prázdné místo metody, která naplní stromů XML. Informace o řízení prázdných znaků při serializaci stromů XML, naleznete v tématu [zachování prázdných znaků při serializaci](../../../../csharp/programming-guide/concepts/linq/preserving-white-space-while-serializing.md).  
  
## <a name="behavior-of-methods-that-populate-xml-trees"></a>Chování metody, která naplní stromů XML  
 Následující metody u <xref:System.Xml.Linq.XElement> a <xref:System.Xml.Linq.XDocument> třídy naplnění stromu XML. Můžete naplnění stromu XML ze souboru, <xref:System.IO.TextReader>, <xref:System.Xml.XmlReader>, nebo řetězec:  
  
-   <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>  
  
 Pokud metoda nepřijímá <xref:System.Xml.Linq.LoadOptions> jako argument, metoda nezachová nevýznamné prázdné znaky.  
  
 Ve většině případů, pokud tato metoda přebírá <xref:System.Xml.Linq.LoadOptions> jako argument, můžete volitelně zachovat mezer nevýznamné jako textové uzly ve stromové struktuře XML. Nicméně pokud metoda je načtení XML ze <xref:System.Xml.XmlReader>, pak bude <xref:System.Xml.XmlReader> Určuje, zda budou zachovány prázdné znaky, nebo ne. Nastavení <xref:System.Xml.Linq.LoadOptions.PreserveWhitespace> nebude mít žádný efekt.  
  
 Pomocí těchto metod, pokud prázdné místo je zachována, nevýznamné prázdné místo je vložen do stromu XML jako <xref:System.Xml.Linq.XText> uzly. Pokud nejsou uchována prázdné znaky, nejsou vložen textové uzly.  
  
 Můžete vytvořit stromu XML pomocí <xref:System.Xml.XmlWriter>. Uzly, které jsou zapsány do <xref:System.Xml.XmlWriter> zaplnění ve stromové struktuře. Při vytváření stromu XML pomocí této metody všechny uzly jsou však zachovaných, bez ohledu na to, zda uzel je prázdný znak, nebo Ne, nebo určuje, zda je prázdné místo důležité nebo ne.  
  
## <a name="see-also"></a>Viz také

- [Analýza kódu XML (C#)](../../../../csharp/programming-guide/concepts/linq/parsing-xml.md)

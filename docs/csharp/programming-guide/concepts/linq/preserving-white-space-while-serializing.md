---
title: Zachování prázdných znaků při Serializing3
ms.date: 07/20/2015
ms.assetid: 0c4f8b98-483b-4cf8-86be-fa146eef90dc
ms.openlocfilehash: 7fd0a38d2a9ed8c4712b8e9a03a24a23b408f38a
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/02/2018
ms.locfileid: "48032358"
---
# <a name="preserving-white-space-while-serializing"></a>Zachování prázdných znaků při serializaci
Toto téma popisuje, jak řídit prázdných znaků při serializaci stromu XML.  
  
 Běžný scénář, kdy je pro čtení odsazený XML, vytvoření stromu XML v paměti bez ostatní uzly text prázdné místo (tedy ne zachování prázdné znaky), provádění některých operací na XML a pak uložte soubor XML s odsazením. Při serializaci XML s formátováním je zachována pouze významný prázdný znak ve stromové struktuře XML. Toto je výchozí chování pro [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].  
  
 Další z typických možností je číst a upravovat kód XML, který již byl záměrně odsazeny. Nebudete chtít změnit tento odsazení žádným způsobem. Chcete-li to provést v [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], zachovat mezer při načtení nebo analyzovat kód XML a zakázat formátování při serializaci kódu XML.  
  
## <a name="white-space-behavior-of-methods-that-serialize-xml-trees"></a>Prázdné místo chování metody, které serializace stromů XML  
 Následující metody u <xref:System.Xml.Linq.XElement> a <xref:System.Xml.Linq.XDocument> třídy serializaci stromu XML. Může serializovat stromu XML do souboru <xref:System.IO.TextReader>, nebo <xref:System.Xml.XmlReader>. `ToString` Metoda provede serializaci do řetězce.  
  
-   <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XElement.ToString%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XDocument.ToString%2A?displayProperty=nameWithType>  
  
 Pokud metoda nepřijímá <xref:System.Xml.Linq.SaveOptions> jako argument, pak metoda naformátuje (odsazení) serializovaném kódu XML. V takovém případě se zahodí všechny neplatné prázdné znaky ve stromové struktuře XML.  
  
 Pokud trvá, než metoda <xref:System.Xml.Linq.SaveOptions> jako argument, potom můžete zadat, že metoda není formátování (odsazení) serializovaném kódu XML. V takovém případě se zachovají všechny prázdné znaky ve stromové struktuře XML.  
  
## <a name="see-also"></a>Viz také

- [Serializace stromů XML (C#)](../../../../csharp/programming-guide/concepts/linq/serializing-xml-trees.md)

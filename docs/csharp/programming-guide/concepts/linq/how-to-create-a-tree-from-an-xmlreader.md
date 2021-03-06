---
title: 'Postupy: vytvoření stromu ze třídy XmlReader (C#)'
ms.date: 07/20/2015
ms.assetid: 60951c9c-7087-406c-b5bb-c60e58609b21
ms.openlocfilehash: f0e75e4d3f6964fa44c41265c1c276c32fb9e87d
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/04/2018
ms.locfileid: "43501751"
---
# <a name="how-to-create-a-tree-from-an-xmlreader-c"></a>Postupy: vytvoření stromu ze třídy XmlReader (C#)
Toto téma ukazuje, jak vytvořit stromu XML přímo ze <xref:System.Xml.XmlReader>. K vytvoření <xref:System.Xml.Linq.XElement> ze <xref:System.Xml.XmlReader>, je třeba umístit <xref:System.Xml.XmlReader> na uzlu elementu. <xref:System.Xml.XmlReader> Komentáře se přeskočí a zpracování pokynů, ale pokud <xref:System.Xml.XmlReader> je umístěn na textový uzel, bude vyvolána k chybě. Aby se zabránilo podobné chyby, vždy umístěte <xref:System.Xml.XmlReader> v elementu před vytvořením stromu XML ze <xref:System.Xml.XmlReader>.  
  
## <a name="example"></a>Příklad  
 Tento příklad používá následujícího dokumentu XML: [ukázkový soubor XML: knihy (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).  
  
 Následující kód vytvoří `T:System.Xml.XmlReader` objektu a čtení uzly, dokud nenajde prvního uzlu elementu. Pak načte <xref:System.Xml.Linq.XElement> objektu.  
  
```csharp  
XmlReader r = XmlReader.Create("books.xml");  
while (r.NodeType != XmlNodeType.Element)  
    r.Read();  
XElement e = XElement.Load(r);  
Console.WriteLine(e);  
```  
  
 Tento příklad vytvoří následující výstup:  
  
```xml  
<Catalog>  
   <Book id="bk101">  
      <Author>Garghentini, Davide</Author>  
      <Title>XML Developer's Guide</Title>  
      <Genre>Computer</Genre>  
      <Price>44.95</Price>  
      <PublishDate>2000-10-01</PublishDate>  
      <Description>An in-depth look at creating applications   
      with XML.</Description>  
   </Book>  
   <Book id="bk102">  
      <Author>Garcia, Debra</Author>  
      <Title>Midnight Rain</Title>  
      <Genre>Fantasy</Genre>  
      <Price>5.95</Price>  
      <PublishDate>2000-12-16</PublishDate>  
      <Description>A former architect battles corporate zombies,   
      an evil sorceress, and her own childhood to become queen   
      of the world.</Description>  
   </Book>  
</Catalog>  
```  
  
## <a name="see-also"></a>Viz také

- [Analýza kódu XML (C#)](../../../../csharp/programming-guide/concepts/linq/parsing-xml.md)

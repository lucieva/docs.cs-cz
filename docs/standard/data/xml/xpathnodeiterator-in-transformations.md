---
title: XPathNodeIterator v transformace
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 2bc6ddc6-674a-4f75-b264-abc35e4e5857
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 28877f10e11f2eebdcbcc8ff75854551302e3f66
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="xpathnodeiterator-in-transformations"></a><span data-ttu-id="0dc1e-102">XPathNodeIterator v transformace</span><span class="sxs-lookup"><span data-stu-id="0dc1e-102">XPathNodeIterator in Transformations</span></span>
<span data-ttu-id="0dc1e-103"><xref:System.Xml.XPath.XPathNodeIterator> Poskytuje metody k iteraci v rámci sady uzlů vytvořené v důsledku dotaz XML Path Language (XPath) nebo fragment stromu výsledek převést na uzlu nastavte pomocí metody sada uzlů.</span><span class="sxs-lookup"><span data-stu-id="0dc1e-103">The <xref:System.Xml.XPath.XPathNodeIterator> provides methods to iterate over a set of nodes created as the result of an XML Path Language (XPath) query or a result tree fragment converted to a node set by use of the node-set method.</span></span> <span data-ttu-id="0dc1e-104"><xref:System.Xml.XPath.XPathNodeIterator> Umožňuje iterovat uzlů v rámci dané sadě uzlu.</span><span class="sxs-lookup"><span data-stu-id="0dc1e-104">The <xref:System.Xml.XPath.XPathNodeIterator> enables you to iterate over the nodes within that node set.</span></span> <span data-ttu-id="0dc1e-105">Jakmile se načte sada uzlů, <xref:System.Xml.XPath.XPathNodeIterator> třída poskytuje jen pro čtení, dopředné kurzoru vybrané sada uzlů.</span><span class="sxs-lookup"><span data-stu-id="0dc1e-105">Once a node set is retrieved, the <xref:System.Xml.XPath.XPathNodeIterator> class provides a read-only, forward-only cursor to the selected set of nodes.</span></span> <span data-ttu-id="0dc1e-106">Sada uzlů se vytvoří v pořadí dokumentů, voláním této metody přesune na další uzel v pořadí dokumentů.</span><span class="sxs-lookup"><span data-stu-id="0dc1e-106">The node set is created in document order, so calling this method moves to the next node in document order.</span></span> <span data-ttu-id="0dc1e-107"><xref:System.Xml.XPath.XPathNodeIterator>Nelze sestavit uzlu stromu všech uzlů v sadě.</span><span class="sxs-lookup"><span data-stu-id="0dc1e-107"><xref:System.Xml.XPath.XPathNodeIterator> does not build a node tree of all the nodes in the set.</span></span> <span data-ttu-id="0dc1e-108">Namísto toho poskytuje okno jednoho uzlu do data vystavení základní uzlu, na který odkazuje jako pohyb ve stromové struktuře.</span><span class="sxs-lookup"><span data-stu-id="0dc1e-108">Instead, it provides a single node window into the data, exposing the underlying node it points to as you move around in the tree.</span></span> <span data-ttu-id="0dc1e-109">Metody a vlastnosti, které jsou dostupné na <xref:System.Xml.XPath.XPathNodeIterator> třída umožňují získat informace z aktuálního uzlu.</span><span class="sxs-lookup"><span data-stu-id="0dc1e-109">The methods and properties available from the <xref:System.Xml.XPath.XPathNodeIterator> class enable you to get information from the current node.</span></span> <span data-ttu-id="0dc1e-110">Seznam dostupných metod a vlastností, najdete v tématu <xref:System.Windows.Forms.ToolBar>.</span><span class="sxs-lookup"><span data-stu-id="0dc1e-110">For a list of the available methods and properties, see <xref:System.Windows.Forms.ToolBar>.</span></span>  
  
 <span data-ttu-id="0dc1e-111">Protože <xref:System.Xml.XPath.XPathNodeIterator> přesune přes sada uzlů vytvořené z dotaz XPath a přejde vpřed pouze, je způsob, jak přesunout pomocí <xref:System.Xml.XPath.XPathNodeIterator.MoveNext%2A> metoda.</span><span class="sxs-lookup"><span data-stu-id="0dc1e-111">Since an <xref:System.Xml.XPath.XPathNodeIterator> moves over a set of nodes created from an XPath query and moves forward only, the way to move is by using the <xref:System.Xml.XPath.XPathNodeIterator.MoveNext%2A> method.</span></span> <span data-ttu-id="0dc1e-112">Návratový typ této metody `Boolean`, vracejících `true` pokud ji přesune na další vybraný uzel, a `false` Pokud neexistují žádné další vybrané uzly.</span><span class="sxs-lookup"><span data-stu-id="0dc1e-112">The return type of this method is `Boolean`, returning `true` if it moves to the next selected node, and `false` if there are no more selected nodes.</span></span> <span data-ttu-id="0dc1e-113">Vrátí-li `true`, v následujícím seznamu jsou dostupné vlastnosti:</span><span class="sxs-lookup"><span data-stu-id="0dc1e-113">If it returns `true`, the following list shows the properties available:</span></span>  
  
-   <xref:System.Xml.XPath.XPathNodeIterator.Current%2A>  
  
-   <xref:System.Xml.XPath.XPathNodeIterator.CurrentPosition%2A>  
  
-   <xref:System.Xml.XPath.XPathNodeIterator.Count%2A>  
  
 <span data-ttu-id="0dc1e-114">Při hledání v uzlu nastavení při prvním volání <xref:System.Xml.XPath.XPathNodeIterator.MoveNext%2A> musí být provedeny na pozici <xref:System.Xml.XPath.XPathNodeIterator> na prvním uzlu vybrané sady.</span><span class="sxs-lookup"><span data-stu-id="0dc1e-114">When you are looking at a node set for the first time, a call to <xref:System.Xml.XPath.XPathNodeIterator.MoveNext%2A> must be made to position the <xref:System.Xml.XPath.XPathNodeIterator> on the first node of the selected set.</span></span> <span data-ttu-id="0dc1e-115">To umožňuje chvíli smyčky k zapsání.</span><span class="sxs-lookup"><span data-stu-id="0dc1e-115">This allows a while loop to be written.</span></span>  
  
 <span data-ttu-id="0dc1e-116">Následující příklad kódu ukazuje, jak předat <xref:System.Xml.XPath.XPathNodeIterator> k <xref:System.Xml.Xsl.XslTransform> jako parametr v <xref:System.Xml.Xsl.XsltArgumentList>.</span><span class="sxs-lookup"><span data-stu-id="0dc1e-116">The following code example shows how to pass an <xref:System.Xml.XPath.XPathNodeIterator> to an <xref:System.Xml.Xsl.XslTransform> as a parameter in the <xref:System.Xml.Xsl.XsltArgumentList>.</span></span> <span data-ttu-id="0dc1e-117">Vstup kód je **books.xml**, a je šablony stylů **text.xsl**.</span><span class="sxs-lookup"><span data-stu-id="0dc1e-117">The input to the code is **books.xml**, and the style sheet is **text.xsl**.</span></span> <span data-ttu-id="0dc1e-118">Soubor **test.xml** je <xref:System.Xml.XPath.XPathDocument>.</span><span class="sxs-lookup"><span data-stu-id="0dc1e-118">The file **test.xml** is the <xref:System.Xml.XPath.XPathDocument>.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
Imports System.Xml.Xsl  
Imports System.Xml.XPath  
Imports System.Text  
  
Public Class sample  
  
   Public Shared Sub Main()  
      Dim Doc As New XPathDocument("books.xml")  
      Dim nav As XPathNavigator = Doc.CreateNavigator()  
      Dim Iterator As XPathNodeIterator = nav.Select("/bookstore/book")  
  
      Dim arg As New XsltArgumentList()  
      arg.AddParam("param1", "", Iterator)  
  
      Dim xslt As New XslTransform()  
      xslt.Load("test.xsl")  
  
      Dim xd As New XPathDocument("test.xml")  
  
      Dim strmTemp = New FileStream("out.xml", FileMode.Create, FileAccess.ReadWrite)  
      xslt.Transform(xd, arg, strmTemp, Nothing)  
   End Sub 'Main  
End Class 'sample  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
using System.Xml.Xsl;  
using System.Xml.XPath;  
using System.Text;  
  
public class sample  
{  
    public static void Main()  
    {  
        XPathDocument Doc = new XPathDocument("books.xml");  
        XPathNavigator nav = Doc.CreateNavigator();  
        XPathNodeIterator Iterator = nav.Select("/bookstore/book");  
  
        XsltArgumentList arg = new XsltArgumentList();  
        arg.AddParam("param1", "", Iterator);  
  
        XslTransform xslt = new XslTransform();  
        xslt.Load("test.xsl");  
  
        XPathDocument xd = new XPathDocument("test.xml");  
  
        Stream strmTemp = new FileStream("out.xml", FileMode.Create, FileAccess.ReadWrite);  
        xslt.Transform(xd, arg, strmTemp, null);  
    }  
}  
```  
  
## <a name="booksxml"></a><span data-ttu-id="0dc1e-119">Books.XML</span><span class="sxs-lookup"><span data-stu-id="0dc1e-119">books.xml</span></span>  
  
```xml  
<?xml version='1.0'?>  
<!-- This file represents a fragment of a book store inventory database. -->  
<bookstore specialty="novel">  
    <book style="autobiography">  
    <title>Seven Years in Trenton</title>  
        <author>  
            <first-name>Jay</first-name>  
            <last-name>Adams</last-name>  
            <award>Trenton Literary Review Honorable Mention</award>  
            <country>USA</country>  
        </author>  
        <price>12</price>  
    </book>  
    <book style="textbook">  
        <title>History of Trenton</title>  
        <author>  
            <first-name>Kim</first-name>  
            <last-name>Akers</last-name>  
            <publication>  
                Selected Short Stories of  
                <first-name>Scott</first-name>  
                <last-name>Bishop</last-name>  
                <country>US</country>  
            </publication>  
        </author>  
        <price>55</price>  
    </book>  
</bookstore>  
```  
  
## <a name="testxsl"></a><span data-ttu-id="0dc1e-120">test.xsl</span><span class="sxs-lookup"><span data-stu-id="0dc1e-120">test.xsl</span></span>  
  
```xml  
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform"  
xmlns:msxsl="urn:schemas-microsoft-com:xslt" exclude-result-prefixes="msxsl">  
  
<xsl:output method="xml" indent="yes"/>  
<xsl:param name="param1"/>  
  
<xsl:template match="/">  
    <out>  
        <xsl:for-each select="$param1/title">  
            <title><xsl:value-of select="."/></title>  
        </xsl:for-each>  
    </out>  
</xsl:template>  
  
</xsl:stylesheet>  
```  
  
## <a name="testxml"></a><span data-ttu-id="0dc1e-121">test.XML</span><span class="sxs-lookup"><span data-stu-id="0dc1e-121">test.xml</span></span>  
  
```xml  
<Title attr="Test">this is a test</Title>  
```  
  
## <a name="output-outxml"></a><span data-ttu-id="0dc1e-122">Výstup (out.xml)</span><span class="sxs-lookup"><span data-stu-id="0dc1e-122">Output (out.xml)</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<out>  
  <title>Seven Years in Trenton</title>  
  <title>History of Trenton</title>  
</out>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0dc1e-123">Viz také</span><span class="sxs-lookup"><span data-stu-id="0dc1e-123">See Also</span></span>  
 [<span data-ttu-id="0dc1e-124">Třída XslTransform implementuje procesoru XSLT</span><span class="sxs-lookup"><span data-stu-id="0dc1e-124">XslTransform Class Implements the XSLT Processor</span></span>](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
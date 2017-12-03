---
title: "Pomocí XSLT k transformaci strom XML (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 373a2699-d4c5-471b-9bda-c1f0ab73b477
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 0abd857def00bd1e96332cd635d49aa50b2b873b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="using-xslt-to-transform-an-xml-tree-c"></a><span data-ttu-id="e985c-102">Pomocí XSLT k transformaci strom XML (C#)</span><span class="sxs-lookup"><span data-stu-id="e985c-102">Using XSLT to Transform an XML Tree (C#)</span></span>
<span data-ttu-id="e985c-103">Můžete vytvořit strom XML, vytvořit <xref:System.Xml.XmlReader> ve stromové struktuře XML vytvoříte nový textový dokument a vytvoření <xref:System.Xml.XmlWriter> , bude zapisovat do nového dokumentu.</span><span class="sxs-lookup"><span data-stu-id="e985c-103">You can create an XML tree, create an <xref:System.Xml.XmlReader> from the XML tree, create a new document, and create an <xref:System.Xml.XmlWriter> that will write into the new document.</span></span> <span data-ttu-id="e985c-104">Potom můžete vyvolat transformace XSLT, předávání <xref:System.Xml.XmlReader> a <xref:System.Xml.XmlWriter> k transformaci.</span><span class="sxs-lookup"><span data-stu-id="e985c-104">Then, you can invoke the XSLT transformation, passing the <xref:System.Xml.XmlReader> and <xref:System.Xml.XmlWriter> to the transformation.</span></span> <span data-ttu-id="e985c-105">Po úspěšném dokončení transformace, se zobrazí v stromu nové XML výsledky pro transformaci.</span><span class="sxs-lookup"><span data-stu-id="e985c-105">After the transformation successfully completes, the new XML tree is populated with the results of the transform.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e985c-106">Příklad</span><span class="sxs-lookup"><span data-stu-id="e985c-106">Example</span></span>  
  
```csharp  
string xslMarkup = @"<?xml version='1.0'?>  
<xsl:stylesheet xmlns:xsl='http://www.w3.org/1999/XSL/Transform' version='1.0'>  
    <xsl:template match='/Parent'>  
        <Root>  
            <C1>  
            <xsl:value-of select='Child1'/>  
            </C1>  
            <C2>  
            <xsl:value-of select='Child2'/>  
            </C2>  
        </Root>  
    </xsl:template>  
</xsl:stylesheet>";  
  
XDocument xmlTree = new XDocument(  
    new XElement("Parent",  
        new XElement("Child1", "Child1 data"),  
        new XElement("Child2", "Child2 data")  
    )  
);  
  
XDocument newTree = new XDocument();  
using (XmlWriter writer = newTree.CreateWriter()) {  
    // Load the style sheet.  
    XslCompiledTransform xslt = new XslCompiledTransform();  
    xslt.Load(XmlReader.Create(new StringReader(xslMarkup)));  
  
    // Execute the transform and output the results to a writer.  
    xslt.Transform(xmlTree.CreateReader(), writer);  
}  
  
Console.WriteLine(newTree);  
```  
  
 <span data-ttu-id="e985c-107">Tento příklad vytvoří následující výstup:</span><span class="sxs-lookup"><span data-stu-id="e985c-107">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <C1>Child1 data</C1>  
  <C2>Child2 data</C2>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e985c-108">Viz také</span><span class="sxs-lookup"><span data-stu-id="e985c-108">See Also</span></span>  
 <xref:System.Xml.Linq.XContainer.CreateWriter%2A?displayProperty=nameWithType>  
 <xref:System.Xml.Linq.XNode.CreateReader%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="e985c-109">Pokročilé technologie LINQ to XML programování (C#)</span><span class="sxs-lookup"><span data-stu-id="e985c-109">Advanced LINQ to XML Programming (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
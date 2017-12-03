---
title: "Odpovídající pomocí objektem XPathNavigator nastaveným na uzly"
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
ms.assetid: e6848c47-ee5d-401a-89a5-50b5eed40f30
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a51c358ecb50c94ccde9f86ba80fc8f0670f82d9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="matching-nodes-using-xpathnavigator"></a><span data-ttu-id="c104b-102">Odpovídající pomocí objektem XPathNavigator nastaveným na uzly</span><span class="sxs-lookup"><span data-stu-id="c104b-102">Matching Nodes using XPathNavigator</span></span>
<span data-ttu-id="c104b-103"><xref:System.Xml.XPath.XPathNavigator> Třída poskytuje <xref:System.Xml.XPath.XPathNavigator.Matches%2A> metoda k určení, jestli odpovídá uzlu výraz XPath.</span><span class="sxs-lookup"><span data-stu-id="c104b-103">The <xref:System.Xml.XPath.XPathNavigator> class provides the <xref:System.Xml.XPath.XPathNavigator.Matches%2A> method to determine if a node matches an XPath expression.</span></span> <span data-ttu-id="c104b-104"><xref:System.Xml.XPath.XPathNavigator.Matches%2A> Metoda přebírá výraz XPath jako vstup a vrátí <xref:System.Boolean> určující, jestli aktuální uzel odpovídá dané výraz XPath nebo zadané kompilované <xref:System.Xml.XPath.XPathExpression> objektu.</span><span class="sxs-lookup"><span data-stu-id="c104b-104">The <xref:System.Xml.XPath.XPathNavigator.Matches%2A> method takes an XPath expression as input and returns a <xref:System.Boolean> that indicates if the current node matches the given XPath expression or the given compiled <xref:System.Xml.XPath.XPathExpression> object.</span></span>  
  
## <a name="matching-nodes"></a><span data-ttu-id="c104b-105">Odpovídající uzly</span><span class="sxs-lookup"><span data-stu-id="c104b-105">Matching Nodes</span></span>  
 <span data-ttu-id="c104b-106"><xref:System.Xml.XPath.XPathNavigator.Matches%2A> Metoda vrátí `true` Pokud aktuálního uzlu odpovídá zadán výraz XPath.</span><span class="sxs-lookup"><span data-stu-id="c104b-106">The <xref:System.Xml.XPath.XPathNavigator.Matches%2A> method returns `true` if the current node matches the XPath expression specified.</span></span> <span data-ttu-id="c104b-107">Například v příkladu kódu, který následuje <xref:System.Xml.XPath.XPathNavigator.Matches%2A> metoda vrátí `true` Pokud je aktuální uzel elementu `b`a element `b` má atribut `c`.</span><span class="sxs-lookup"><span data-stu-id="c104b-107">For example, in the code example that follows, the <xref:System.Xml.XPath.XPathNavigator.Matches%2A> method will return `true` if the current node is the element `b`, and element `b` has an attribute `c`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c104b-108"><xref:System.Xml.XPath.XPathNavigator.Matches%2A> Metoda nezmění stav <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="c104b-108">The <xref:System.Xml.XPath.XPathNavigator.Matches%2A> method does not change the state of the <xref:System.Xml.XPath.XPathNavigator>.</span></span>  
  
```vb  
Dim document as XPathDocument = New XPathDocument("input.xml")  
Dim navigator as XPathNavigator = document.CreateNavigator()  
  
navigator.Matches("b[@c]")  
```  
  
```csharp  
XPathDocument document = new XPathDocument("input.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
navigator.Matches("b[@c]");  
```  
  
## <a name="see-also"></a><span data-ttu-id="c104b-109">Viz také</span><span class="sxs-lookup"><span data-stu-id="c104b-109">See Also</span></span>  
 <xref:System.Xml.XmlDocument>  
 <xref:System.Xml.XPath.XPathDocument>  
 <xref:System.Xml.XPath.XPathNavigator>  
 [<span data-ttu-id="c104b-110">Zpracování kódu XML dat pomocí jazyka XPath datový Model</span><span class="sxs-lookup"><span data-stu-id="c104b-110">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 [<span data-ttu-id="c104b-111">Vyberte pomocí objektem XPathNavigator nastaveným na Data XML</span><span class="sxs-lookup"><span data-stu-id="c104b-111">Select XML Data Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/select-xml-data-using-xpathnavigator.md)  
 [<span data-ttu-id="c104b-112">Vyhodnocení výrazů jazyka XPath pomocí objektem XPathNavigator nastaveným na</span><span class="sxs-lookup"><span data-stu-id="c104b-112">Evaluate XPath Expressions using XPathNavigator</span></span>](../../../../docs/standard/data/xml/evaluate-xpath-expressions-using-xpathnavigator.md)  
 [<span data-ttu-id="c104b-113">Typy uzlů rozpoznána s dotazy XPath</span><span class="sxs-lookup"><span data-stu-id="c104b-113">Node Types Recognized with XPath Queries</span></span>](../../../../docs/standard/data/xml/node-types-recognized-with-xpath-queries.md)  
 [<span data-ttu-id="c104b-114">Dotazy XPath a obory názvů</span><span class="sxs-lookup"><span data-stu-id="c104b-114">XPath Queries and Namespaces</span></span>](../../../../docs/standard/data/xml/xpath-queries-and-namespaces.md)  
 [<span data-ttu-id="c104b-115">Výrazy kompilované XPath</span><span class="sxs-lookup"><span data-stu-id="c104b-115">Compiled XPath Expressions</span></span>](../../../../docs/standard/data/xml/compiled-xpath-expressions.md)
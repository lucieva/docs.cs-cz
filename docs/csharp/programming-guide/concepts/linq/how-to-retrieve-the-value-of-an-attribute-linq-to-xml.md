---
title: "Postupy: načtení hodnoty atributu (technologie LINQ to XML) (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 817bbe89-5979-4234-bf0c-46f63692ac8c
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 12720ca8bd1937d37f8d30400e0b25afa22a40cc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-retrieve-the-value-of-an-attribute-linq-to-xml-c"></a><span data-ttu-id="5b444-102">Postupy: načtení hodnoty atributu (technologie LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="5b444-102">How to: Retrieve the Value of an Attribute (LINQ to XML) (C#)</span></span>
<span data-ttu-id="5b444-103">Toto téma ukazuje, jak získat hodnotu atributů.</span><span class="sxs-lookup"><span data-stu-id="5b444-103">This topic shows how to obtain the value of attributes.</span></span> <span data-ttu-id="5b444-104">Existují dva hlavní způsoby: může odevzdat <xref:System.Xml.Linq.XAttribute> na požadovaný typ; operátor explicitní převod potom převede obsah elementu nebo atributu zadaného typu.</span><span class="sxs-lookup"><span data-stu-id="5b444-104">There are two main ways: You can cast an <xref:System.Xml.Linq.XAttribute> to the desired type; the explicit conversion operator then converts the contents of the element or attribute to the specified type.</span></span> <span data-ttu-id="5b444-105">Alternativně můžete použít <xref:System.Xml.Linq.XAttribute.Value%2A> vlastnost.</span><span class="sxs-lookup"><span data-stu-id="5b444-105">Alternatively, you can use the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span> <span data-ttu-id="5b444-106">Přetypování je ale obecně lepší přístup.</span><span class="sxs-lookup"><span data-stu-id="5b444-106">However, casting is generally the better approach.</span></span> <span data-ttu-id="5b444-107">Pokud jste přetypovat atribut typu s povolenou hodnotou Null, kód je jednodušší při načítání hodnoty atributu, který může nebo nemusí existovat zápis.</span><span class="sxs-lookup"><span data-stu-id="5b444-107">If you cast the attribute to a nullable type, the code is simpler to write when retrieving the value of an attribute that might or might not exist.</span></span> <span data-ttu-id="5b444-108">Příklady tento postup najdete v tématu [postupy: načtení hodnoty elementu (technologie LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-element-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="5b444-108">For examples of this technique, see [How to: Retrieve the Value of an Element (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-element-linq-to-xml.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5b444-109">Příklad</span><span class="sxs-lookup"><span data-stu-id="5b444-109">Example</span></span>  
 <span data-ttu-id="5b444-110">K načtení hodnoty atributu, je právě přetypovat <xref:System.Xml.Linq.XAttribute> objekt, který má požadovaný typ.</span><span class="sxs-lookup"><span data-stu-id="5b444-110">To retrieve the value of an attribute, you just cast the <xref:System.Xml.Linq.XAttribute> object to your desired type.</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
                    new XAttribute("Attr", "abcde")  
                );  
Console.WriteLine(root);  
string str = (string)root.Attribute("Attr");  
Console.WriteLine(str);  
```  
  
 <span data-ttu-id="5b444-111">Tento příklad vytvoří následující výstup:</span><span class="sxs-lookup"><span data-stu-id="5b444-111">This example produces the following output:</span></span>  
  
```  
<Root Attr="abcde" />  
abcde  
```  
  
## <a name="example"></a><span data-ttu-id="5b444-112">Příklad</span><span class="sxs-lookup"><span data-stu-id="5b444-112">Example</span></span>  
 <span data-ttu-id="5b444-113">Následující příklad ukazuje, jak načíst hodnotu atributu kde atributu je v oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="5b444-113">The following example shows how to retrieve the value of an attribute where the attribute is in a namespace.</span></span> <span data-ttu-id="5b444-114">Další informace najdete v tématu [práci s obory názvů XML (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="5b444-114">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = new XElement(aw + "Root",  
                    new XAttribute(aw + "Attr", "abcde")  
                );  
string str = (string)root.Attribute(aw + "Attr");  
Console.WriteLine(str);  
```  
  
 <span data-ttu-id="5b444-115">Tento příklad vytvoří následující výstup:</span><span class="sxs-lookup"><span data-stu-id="5b444-115">This example produces the following output:</span></span>  
  
```  
abcde  
```  
  
## <a name="see-also"></a><span data-ttu-id="5b444-116">Viz také</span><span class="sxs-lookup"><span data-stu-id="5b444-116">See Also</span></span>  
 [<span data-ttu-id="5b444-117">Technologie LINQ to XML osy (C#)</span><span class="sxs-lookup"><span data-stu-id="5b444-117">LINQ to XML Axes (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md)
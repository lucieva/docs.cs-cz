---
title: Zachování dvojic název hodnota (C#)
ms.date: 07/20/2015
ms.assetid: 7b04b0f1-af64-42eb-8737-83f8861b5915
ms.openlocfilehash: 28c01ce17881ffe7e8fcc35e2c23dec85d50955d
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/06/2018
ms.locfileid: "48841213"
---
# <a name="maintaining-namevalue-pairs-c"></a>Zachování dvojic název/hodnota (C#)
Mnoho aplikací nutné udržovat informace, které nejlépe se ukládají jako dvojice název/hodnota. Tyto informace mohou být informace o konfiguraci nebo globální nastavení. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] obsahuje některé metody, které usnadňují zachovat sadu párů název/hodnota. Buď můžete zachovat informace jako atributy nebo sadu podřízených elementů.  
  
 Jedním z rozdílů mezi chrání informace jako atributy nebo podřízené prvky je, že atributy obsahují omezení, že může existovat pouze jeden atribut s konkrétním názvem pro daný element. Toto omezení se nevztahuje na podřízené prvky.  
  
## <a name="setattributevalue-and-setelementvalue"></a>SetAttributeValue a SetElementValue  
 Dvě metody, které usnadňují uchování páry název/hodnota jsou <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> a <xref:System.Xml.Linq.XElement.SetElementValue%2A>. Tyto dvě metody mají podobnou sémantikou.  
  
 <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> můžete přidat, upravit nebo odebrat atributy elementu.  
  
-   Při volání <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> s názvem atributu, který ještě neexistuje, metoda vytvoří nový atribut a přidá jej do zadaného prvku.  
  
-   Při volání <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> s názvem existujícího atributu a s některými zadaný obsahu, obsah atributu nahrazují se zadaným obsahem.  
  
-   Při volání <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> s názvem existujícího atribut a zadejte hodnotu null pro obsah, atribut se odebere ze svého nadřazeného objektu.  
  
 <xref:System.Xml.Linq.XElement.SetElementValue%2A> můžete přidat, upravit nebo odebrat podřízené prvky prvku.  
  
-   Při volání <xref:System.Xml.Linq.XElement.SetElementValue%2A> s názvem podřízený element, který ještě neexistuje, metoda vytvoří nový prvek a přidá jej do zadaného prvku.  
  
-   Při volání <xref:System.Xml.Linq.XElement.SetElementValue%2A> s názvem existujícího prvku a s některými zadaný obsahu, obsah elementu se nahradí se zadaným obsahem.  
  
-   Při volání <xref:System.Xml.Linq.XElement.SetElementValue%2A> s názvem existujícího prvku a zadejte hodnotu null pro obsah, elementu se odebere ze svého nadřazeného objektu.  
  
## <a name="example"></a>Příklad  
 Následující příklad vytvoří element se žádné atributy. Poté použije <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> metodu pro vytvoření a správa seznamu párů název/hodnota.  
  
```csharp  
// Create an element with no content.  
XElement root = new XElement("Root");  
  
// Add a number of name/value pairs as attributes.  
root.SetAttributeValue("Top", 22);  
root.SetAttributeValue("Left", 20);  
root.SetAttributeValue("Bottom", 122);  
root.SetAttributeValue("Right", 300);  
root.SetAttributeValue("DefaultColor", "Color.Red");  
Console.WriteLine(root);  
  
// Replace the value of Top.  
root.SetAttributeValue("Top", 10);  
Console.WriteLine(root);  
  
// Remove DefaultColor.  
root.SetAttributeValue("DefaultColor", null);  
Console.WriteLine(root);  
```  
  
 Tento příklad vytvoří následující výstup:  
  
```xml  
<Root Top="22" Left="20" Bottom="122" Right="300" DefaultColor="Color.Red" />  
<Root Top="10" Left="20" Bottom="122" Right="300" DefaultColor="Color.Red" />  
<Root Top="10" Left="20" Bottom="122" Right="300" />  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad vytvoří element se žádné podřízené prvky. Poté použije <xref:System.Xml.Linq.XElement.SetElementValue%2A> metodu pro vytvoření a správa seznamu párů název/hodnota.  
  
```csharp  
// Create an element with no content.  
XElement root = new XElement("Root");  
  
// Add a number of name/value pairs as elements.  
root.SetElementValue("Top", 22);  
root.SetElementValue("Left", 20);  
root.SetElementValue("Bottom", 122);  
root.SetElementValue("Right", 300);  
root.SetElementValue("DefaultColor", "Color.Red");  
Console.WriteLine(root);  
Console.WriteLine("----");  
  
// Replace the value of Top.  
root.SetElementValue("Top", 10);  
Console.WriteLine(root);  
Console.WriteLine("----");  
  
// Remove DefaultColor.  
root.SetElementValue("DefaultColor", null);  
Console.WriteLine(root);  
```  
  
 Tento příklad vytvoří následující výstup:  
  
```xml  
<Root>  
  <Top>22</Top>  
  <Left>20</Left>  
  <Bottom>122</Bottom>  
  <Right>300</Right>  
  <DefaultColor>Color.Red</DefaultColor>  
</Root>  
----  
<Root>  
  <Top>10</Top>  
  <Left>20</Left>  
  <Bottom>122</Bottom>  
  <Right>300</Right>  
  <DefaultColor>Color.Red</DefaultColor>  
</Root>  
----  
<Root>  
  <Top>10</Top>  
  <Left>20</Left>  
  <Bottom>122</Bottom>  
  <Right>300</Right>  
</Root>  
```  
  
## <a name="see-also"></a>Viz také

- <xref:System.Xml.Linq.XElement.SetAttributeValue%2A>  
- <xref:System.Xml.Linq.XElement.SetElementValue%2A>  
- [Změna stromů XML (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)

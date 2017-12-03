---
title: "Odvozování relační strukturu datové sady z schématu XML (XSD)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8f6cd04d-6197-4bc4-9096-8c51c7e4acae
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0aae23c295401d4b9565c35d4d47c5ab913029d5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="deriving-dataset-relational-structure-from-xml-schema-xsd"></a><span data-ttu-id="42e94-102">Odvozování relační strukturu datové sady z schématu XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="42e94-102">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>
<span data-ttu-id="42e94-103">Tato část obsahuje přehled o relační schéma `DataSet` je sestaven z dokument schématu XML definition language (XSD) schématu.</span><span class="sxs-lookup"><span data-stu-id="42e94-103">This section provides an overview of how the relational schema of a `DataSet` is built from an XML Schema definition language (XSD) schema document.</span></span> <span data-ttu-id="42e94-104">Obecně platí, pro každou `complexType` podřízený prvek elementu schématu tabulky se generuje ve `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="42e94-104">In general, for each `complexType` child element of a schema element, a table is generated in the `DataSet`.</span></span> <span data-ttu-id="42e94-105">Struktura tabulky je určen podle definice komplexního typu.</span><span class="sxs-lookup"><span data-stu-id="42e94-105">The table structure is determined by the definition of the complex type.</span></span> <span data-ttu-id="42e94-106">Tabulky se vytváří v `DataSet` nejvyšší úrovně elementy ve schématu.</span><span class="sxs-lookup"><span data-stu-id="42e94-106">Tables are created in the `DataSet` for top-level elements in the schema.</span></span> <span data-ttu-id="42e94-107">Však tabulku je vytvořen pouze pro nejvyšší úroveň `complexType` element při `complexType` element vnořen uvnitř jiné `complexType` případ vnořený elementu, ve kterém `complexType` element je namapovaný na `DataTable` v rámci `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="42e94-107">However, a table is only created for a top-level `complexType` element when the `complexType` element is nested inside another `complexType` element, in which case the nested `complexType` element is mapped to a `DataTable` within the `DataSet`.</span></span>  
  
 <span data-ttu-id="42e94-108">Další informace o XSD, najdete v části schématu XML World Wide Web Consortium (W3C) 0: Úvod do doporučení, část 1 schématu XML: struktury doporučení a XML schéma část 2: datové typy doporučení, nacházející se v [http:// www.w3.org/](http://www.w3.org/TR/).</span><span class="sxs-lookup"><span data-stu-id="42e94-108">For more information about the XSD, see the World Wide Web Consortium (W3C) XML Schema Part 0: Primer Recommendation, the XML Schema Part 1: Structures Recommendation, and the XML Schema Part 2: Datatypes Recommendation, located at [http://www.w3.org/](http://www.w3.org/TR/).</span></span>  
  
 <span data-ttu-id="42e94-109">Následující příklad ukazuje schématu XML kde `customers` je podřízený element `MyDataSet` element, který je **datovou sadu** elementu.</span><span class="sxs-lookup"><span data-stu-id="42e94-109">The following example demonstrates an XML Schema where `customers` is the child element of the `MyDataSet` element, which is a **DataSet** element.</span></span>  
  
```xml  
<xs:schema id="SomeID"   
            xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
   <xs:element name="MyDataSet" msdata:IsDataSet="true">  
     <xs:complexType>  
       <xs:choice maxOccurs="unbounded">  
         <xs:element name="customers" >   
           <xs:complexType >  
             <xs:sequence>  
               <xs:element name="CustomerID" type="xs:integer"   
                            minOccurs="0" />  
               <xs:element name="CompanyName" type="xs:string"   
                            minOccurs="0" />  
               <xs:element name="Phone" type="xs:string" />  
             </xs:sequence>  
           </xs:complexType>  
          </xs:element>  
       </xs:choice>  
     </xs:complexType>  
   </xs:element>  
 </xs:schema>  
```  
  
 <span data-ttu-id="42e94-110">V předchozím příkladu element `customers` je element komplexního typu.</span><span class="sxs-lookup"><span data-stu-id="42e94-110">In the preceding example, the element `customers` is a complex type element.</span></span> <span data-ttu-id="42e94-111">Proto je analýze definice komplexního typu, a proces mapování vytvoří v následující tabulce.</span><span class="sxs-lookup"><span data-stu-id="42e94-111">Therefore, the complex type definition is parsed, and the mapping process creates the following table.</span></span>  
  
```  
Customers (CustomerID , CompanyName, Phone)  
```  
  
 <span data-ttu-id="42e94-112">Datový typ jednotlivých sloupců v tabulce je odvozený od typu schématu XML odpovídající element nebo atribut.</span><span class="sxs-lookup"><span data-stu-id="42e94-112">The data type of each column in the table is derived from the XML Schema type of the corresponding element or attribute specified.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="42e94-113">Pokud element `customers` , jako je jednoduchý datový typ schématu XML **celé číslo**, je vygenerována žádná tabulka.</span><span class="sxs-lookup"><span data-stu-id="42e94-113">If the element `customers` is of a simple XML Schema data type such as **integer**, no table is generated.</span></span> <span data-ttu-id="42e94-114">Tabulky se vytváří jenom pro nejvyšší úrovně prvky, které jsou komplexní typy.</span><span class="sxs-lookup"><span data-stu-id="42e94-114">Tables are only created for the top-level elements that are complex types.</span></span>  
  
 <span data-ttu-id="42e94-115">V následující schématu XML **schématu** element má dva podřízené elementy, `InStateCustomers` a `OutOfStateCustomers`.</span><span class="sxs-lookup"><span data-stu-id="42e94-115">In the following XML Schema, the **Schema** element has two element children, `InStateCustomers` and `OutOfStateCustomers`.</span></span>  
  
```xml  
<xs:schema id="SomeID"   
            xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
   <xs:element name="InStateCustomers" type="customerType" />  
   <xs:element name="OutOfStateCustomers" type="customerType" />  
    <xs:complexType name="customerType" >  
  
     </xs:complexType>  
  
   <xs:element name="MyDataSet" msdata:IsDataSet="true">  
     <xs:complexType>  
       <xs:choice maxOccurs="unbounded">  
         <xs:element ref="customers" />  
       </xs:choice>  
     </xs:complexType>  
   </xs:element>  
 </xs:schema>  
```  
  
 <span data-ttu-id="42e94-116">Jak `InStateCustomers` a `OutOfStateCustomers` podřízené elementy jsou komplexní typ elementy (`customerType`).</span><span class="sxs-lookup"><span data-stu-id="42e94-116">Both the `InStateCustomers` and the `OutOfStateCustomers` child elements are complex type elements (`customerType`).</span></span> <span data-ttu-id="42e94-117">Proto proces mapování generuje následující dva identické tabulky v `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="42e94-117">Therefore, the mapping process generates the following two identical tables in the `DataSet`.</span></span>  
  
```  
InStateCustomers (CustomerID , CompanyName, Phone)  
OutOfStateCustomers (CustomerID , CompanyName, Phone)  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="42e94-118">V tomto oddílu</span><span class="sxs-lookup"><span data-stu-id="42e94-118">In This Section</span></span>  
 [<span data-ttu-id="42e94-119">Omezení (XSD) schématu XML mapování k omezení datové sady</span><span class="sxs-lookup"><span data-stu-id="42e94-119">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="42e94-120">Popisuje elementy schématu XML použitý k vytvoření jedinečné a cizí klíče omezení `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="42e94-120">Describes the XML Schema elements used to create unique and foreign key constraints in a `DataSet`.</span></span>  
  
 [<span data-ttu-id="42e94-121">Generování datovou sadu vztahů ze schématu XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="42e94-121">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 <span data-ttu-id="42e94-122">Popisuje elementy schématu XML použitý k vytvoření relace mezi sloupci tabulky v `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="42e94-122">Describes the XML Schema elements used to create relations between table columns in a `DataSet`.</span></span>  
  
 [<span data-ttu-id="42e94-123">Omezení schématu XML a relace</span><span class="sxs-lookup"><span data-stu-id="42e94-123">XML Schema Constraints and Relationships</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/xml-schema-constraints-and-relationships.md)  
 <span data-ttu-id="42e94-124">Popisuje, jak vztahy jsou implicitně vytvořen při použití schématu XML elementů vytvořte omezení v `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="42e94-124">Describes how relations are created implicitly when using XML Schema elements to create constraints in a `DataSet`.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="42e94-125">Související oddíly</span><span class="sxs-lookup"><span data-stu-id="42e94-125">Related Sections</span></span>  
 [<span data-ttu-id="42e94-126">Pomocí XML v datové sadě</span><span class="sxs-lookup"><span data-stu-id="42e94-126">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 <span data-ttu-id="42e94-127">Popisuje, jak načíst a zachování relační struktura a data v `DataSet` jako XML data.</span><span class="sxs-lookup"><span data-stu-id="42e94-127">Describes how to load and persist the relational structure and data in a `DataSet` as XML data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42e94-128">Viz také</span><span class="sxs-lookup"><span data-stu-id="42e94-128">See Also</span></span>  
 [<span data-ttu-id="42e94-129">ADO.NET spravované zprostředkovatelé a středisku pro vývojáře datové sady</span><span class="sxs-lookup"><span data-stu-id="42e94-129">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
---
title: "Omezení schématu XML a relace"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 165bc2bc-60a1-40e0-9b89-7c68ef979079
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: a324c3b7f24d3395382067ea5581313af58e13f0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="xml-schema-constraints-and-relationships"></a><span data-ttu-id="f8945-102">Omezení schématu XML a relace</span><span class="sxs-lookup"><span data-stu-id="f8945-102">XML Schema Constraints and Relationships</span></span>
<span data-ttu-id="f8945-103">Ve schématu XML definition language (XSD) schématu, můžete zadat omezení (jedinečné, klíče a omezení keyref) a vztahů (pomocí **msdata:Relationship** poznámky).</span><span class="sxs-lookup"><span data-stu-id="f8945-103">In an XML Schema definition language (XSD) schema, you can specify constraints (unique, key, and keyref constraints) and relationships (using the **msdata:Relationship** annotation).</span></span> <span data-ttu-id="f8945-104">Toto téma vysvětluje, jak se interpretují omezení a vztahy zadaný v schéma XML pro generování <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="f8945-104">This topic explains how the constraints and relationships specified in an XML Schema are interpreted to generate the <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="f8945-105">Obecně platí, v schéma XML, můžete zadat **msdata:Relationship** anotace, pokud chcete generovat pouze vztahy v **datovou sadu**.</span><span class="sxs-lookup"><span data-stu-id="f8945-105">In general, in an XML Schema, you specify the **msdata:Relationship** annotation if you want to generate only relationships in the **DataSet**.</span></span> <span data-ttu-id="f8945-106">Další informace najdete v tématu [generování vztahů datové sady z schématu XML (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md).</span><span class="sxs-lookup"><span data-stu-id="f8945-106">For more information, see [Generating DataSet Relations from XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md).</span></span> <span data-ttu-id="f8945-107">Zadejte omezení (jedinečné, klíč a keyref) Pokud chcete generovat omezení **datovou sadu**.</span><span class="sxs-lookup"><span data-stu-id="f8945-107">You specify constraints (unique, key, and keyref) if you want to generate constraints in the **DataSet**.</span></span> <span data-ttu-id="f8945-108">Všimněte si, že klíč a keyref omezení se také používají ke generování relace, jak je popsáno dále v tomto tématu.</span><span class="sxs-lookup"><span data-stu-id="f8945-108">Note that the key and keyref constraints are also used to generate relationships, as explained later in this topic.</span></span>  
  
## <a name="generating-a-relationship-from-key-and-keyref-constraints"></a><span data-ttu-id="f8945-109">Generování vztahu z klíče a keyref omezení</span><span class="sxs-lookup"><span data-stu-id="f8945-109">Generating a Relationship from key and keyref Constraints</span></span>  
 <span data-ttu-id="f8945-110">Místo zadání **msdata:Relationship** poznámky, můžete zadat klíč a keyref omezení, které se používají během procesu mapování schématu XML k vygenerování pouze omezení, ale také relace v  **Datová sada**.</span><span class="sxs-lookup"><span data-stu-id="f8945-110">Instead of specifying the **msdata:Relationship** annotation, you can specify key and keyref constraints, which are used during the XML Schema mapping process to generate not only the constraints but also the relationship in the **DataSet**.</span></span> <span data-ttu-id="f8945-111">Ale pokud zadáte `msdata:ConstraintOnly="true"` v **keyref** elementu, **datovou sadu** bude obsahovat pouze omezení a nebude obsahovat relace.</span><span class="sxs-lookup"><span data-stu-id="f8945-111">However, if you specify `msdata:ConstraintOnly="true"` in the **keyref** element, the **DataSet** will include only the constraints and will not include the relationship.</span></span>  
  
 <span data-ttu-id="f8945-112">Následující příklad ukazuje schéma XML, který zahrnuje **pořadí** a **OrderDetail** prvky, které nejsou vnořené.</span><span class="sxs-lookup"><span data-stu-id="f8945-112">The following example shows an XML Schema that includes **Order** and **OrderDetail** elements, which are not nested.</span></span> <span data-ttu-id="f8945-113">Schéma také Určuje klíč a keyref omezení.</span><span class="sxs-lookup"><span data-stu-id="f8945-113">The schema also specifies key and keyref constraints.</span></span>  
  
```xml  
<xs:schema id="MyDataSet" xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  
 <xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
      <xs:element name="OrderDetail">  
       <xs:complexType>  
         <xs:sequence>  
           <xs:element name="OrderNo" type="xs:integer" />  
           <xs:element name="ItemNo" type="xs:string" />  
         </xs:sequence>  
       </xs:complexType>  
      </xs:element>  
      <xs:element name="Order">  
        <xs:complexType>  
          <xs:sequence>  
            <xs:element name="OrderNumber" type="xs:integer" />  
            <xs:element name="EmpNumber" type="xs:integer" />  
          </xs:sequence>  
        </xs:complexType>  
      </xs:element>  
    </xs:choice>  
  </xs:complexType>  
  
  <xs:key name="OrderNumberKey"  >  
    <xs:selector xpath=".//Order" />  
    <xs:field xpath="OrderNumber" />  
  </xs:key>  
  
  <xs:keyref name="OrderNoRef" refer="OrderNumberKey">  
    <xs:selector xpath=".//OrderDetail" />  
    <xs:field xpath="OrderNo" />  
  </xs:keyref>  
 </xs:element>  
</xs:schema>  
```  
  
 <span data-ttu-id="f8945-114">**Datovou sadu** , je generován během schématu XML, zahrnuje proces mapování **pořadí** a **OrderDetail** tabulky.</span><span class="sxs-lookup"><span data-stu-id="f8945-114">The **DataSet** that is generated during the XML Schema mapping process includes the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="f8945-115">Kromě toho **datovou sadu** obsahuje vztahy a omezení.</span><span class="sxs-lookup"><span data-stu-id="f8945-115">In addition, the **DataSet** includes relationships and constraints.</span></span> <span data-ttu-id="f8945-116">Následující příklad ukazuje tyto vztahy a omezení.</span><span class="sxs-lookup"><span data-stu-id="f8945-116">The following example shows these relationships and constraints.</span></span> <span data-ttu-id="f8945-117">Všimněte si, že schéma neurčuje **msdata:Relationship** anotaci; místo toho se omezení klíč a keyref používají ke generování vztah.</span><span class="sxs-lookup"><span data-stu-id="f8945-117">Note that the schema does not specify the **msdata:Relationship** annotation; instead, the key and keyref constraints are used to generate the relation.</span></span>  
  
```  
....ConstraintName: OrderNumberKey  
....Type: UniqueConstraint  
....Table: Order  
....Columns: OrderNumber  
....IsPrimaryKey: False  
  
....ConstraintName: OrderNoRef  
....Type: ForeignKeyConstraint  
....Table: OrderDetail  
....Columns: OrderNo  
....RelatedTable: Order  
....RelatedColumns: OrderNumber  
  
..RelationName: OrderNoRef  
..ParentTable: Order  
..ParentColumns: OrderNumber  
..ChildTable: OrderDetail  
..ChildColumns: OrderNo  
..ParentKeyConstraint: OrderNumberKey  
..ChildKeyConstraint: OrderNoRef  
..Nested: False  
```  
  
 <span data-ttu-id="f8945-118">V předchozím příkladu schématu **pořadí** a **OrderDetail** nejsou vnořené prvky.</span><span class="sxs-lookup"><span data-stu-id="f8945-118">In the previous schema example, the **Order** and **OrderDetail** elements are not nested.</span></span> <span data-ttu-id="f8945-119">V následujícím příkladu schématu jsou vnořeny těchto elementů.</span><span class="sxs-lookup"><span data-stu-id="f8945-119">In the following schema example, these elements are nested.</span></span> <span data-ttu-id="f8945-120">Však žádné **msdata:Relationship** poznámky je zadán; proto se předpokládá implicitní vztah.</span><span class="sxs-lookup"><span data-stu-id="f8945-120">However, no **msdata:Relationship** annotation is specified; therefore, an implicit relation is assumed.</span></span> <span data-ttu-id="f8945-121">Další informace najdete v tématu [mapy implicitní vztahy mezi vnořené prvky schématu](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-implicit-relations-between-nested-schema-elements.md).</span><span class="sxs-lookup"><span data-stu-id="f8945-121">For more information, see [Map Implicit Relations Between Nested Schema Elements](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-implicit-relations-between-nested-schema-elements.md).</span></span> <span data-ttu-id="f8945-122">Schéma také Určuje klíč a keyref omezení.</span><span class="sxs-lookup"><span data-stu-id="f8945-122">The schema also specifies key and keyref constraints.</span></span>  
  
```xml  
<xs:schema id="MyDataSet" xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  
 <xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
  
      <xs:element name="Order">  
        <xs:complexType>  
          <xs:sequence>  
            <xs:element name="OrderNumber" type="xs:integer" />  
            <xs:element name="EmpNumber" type="xs:integer" />  
  
            <xs:element name="OrderDetail">  
              <xs:complexType>  
                <xs:sequence>  
                  <xs:element name="OrderNo" type="xs:integer" />  
                  <xs:element name="ItemNo" type="xs:string" />  
                </xs:sequence>  
              </xs:complexType>  
            </xs:element>  
          </xs:sequence>  
        </xs:complexType>  
      </xs:element>  
    </xs:choice>  
  </xs:complexType>  
  
  <xs:key name="OrderNumberKey"  >  
    <xs:selector xpath=".//Order" />  
    <xs:field xpath="OrderNumber" />  
  </xs:key>  
  
  <xs:keyref name="OrderNoRef" refer="OrderNumberKey">  
    <xs:selector xpath=".//OrderDetail" />  
    <xs:field xpath="OrderNo" />  
  </xs:keyref>  
 </xs:element>  
</xs:schema>  
```  
  
 <span data-ttu-id="f8945-123">**Datovou sadu** vyplývající z proces mapování schématu XML obsahuje dvě tabulky:</span><span class="sxs-lookup"><span data-stu-id="f8945-123">The **DataSet** resulting from the XML Schema mapping process includes two tables:</span></span>  
  
```  
Order(OrderNumber, EmpNumber, Order_Id)  
OrderDetail(OrderNumber, ItemNumber, Order_Id)  
```  
  
 <span data-ttu-id="f8945-124">**Datovou sadu** také zahrnuje dvě relace (jeden na základě **msdata:relationship** poznámky a dalších omezení klíče a keyref podle) a různé omezení.</span><span class="sxs-lookup"><span data-stu-id="f8945-124">The **DataSet** also includes the two relationships (one based on the **msdata:relationship** annotation and the other based on the key and keyref constraints) and various constraints.</span></span> <span data-ttu-id="f8945-125">Následující příklad ukazuje, vztahy a omezení.</span><span class="sxs-lookup"><span data-stu-id="f8945-125">The following example shows the relations and constraints.</span></span>  
  
```  
..RelationName: Order_OrderDetail  
..ParentTable: Order  
..ParentColumns: Order_Id  
..ChildTable: OrderDetail  
..ChildColumns: Order_Id  
..ParentKeyConstraint: Constraint1  
..ChildKeyConstraint: Order_OrderDetail  
..Nested: True  
  
..RelationName: OrderNoRef  
..ParentTable: Order  
..ParentColumns: OrderNumber  
..ChildTable: OrderDetail  
..ChildColumns: OrderNo  
..ParentKeyConstraint: OrderNumberKey  
..ChildKeyConstraint: OrderNoRef  
..Nested: False  
  
..ConstraintName: OrderNumberKey  
..Type: UniqueConstraint  
..Table: Order  
..Columns: OrderNumber  
..IsPrimaryKey: False  
  
..ConstraintName: Constraint1  
..Type: UniqueConstraint  
..Table: Order  
..Columns: Order_Id  
..IsPrimaryKey: True  
  
..ConstraintName: Order_OrderDetail  
..Type: ForeignKeyConstraint  
..Table: OrderDetail  
..Columns: Order_Id  
..RelatedTable: Order  
..RelatedColumns: Order_Id  
  
..ConstraintName: OrderNoRef  
..Type: ForeignKeyConstraint  
..Table: OrderDetail  
..Columns: OrderNo  
..RelatedTable: Order  
..RelatedColumns: OrderNumber  
```  
  
 <span data-ttu-id="f8945-126">Pokud obsahuje keyref omezení, která odkazuje na vnořené tabulky **msdata:IsNested = "true"** poznámky, **datovou sadu** vytvoří jeden vnořené vztah, který je založen na omezení keyref a související omezení unique nebo key.</span><span class="sxs-lookup"><span data-stu-id="f8945-126">If a keyref constraint referring to a nested table contains the **msdata:IsNested="true"** annotation, the **DataSet** will create a single nested relationship that is based on the keyref constraint and the related unique/key constraint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8945-127">Viz také</span><span class="sxs-lookup"><span data-stu-id="f8945-127">See Also</span></span>  
 [<span data-ttu-id="f8945-128">Odvozování relační strukturu datové sady z schématu XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="f8945-128">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 [<span data-ttu-id="f8945-129">ADO.NET spravované zprostředkovatelé a středisku pro vývojáře datové sady</span><span class="sxs-lookup"><span data-stu-id="f8945-129">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
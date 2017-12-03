---
title: "Postupy: generování objektový Model jako externí soubor"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2496fa06-3df4-4ecb-86c4-70a49ea08565
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: ca0824fd7f5c4145205d28cae4b6d262ae49cbf0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-generate-the-object-model-as-an-external-file"></a><span data-ttu-id="2ef0b-102">Postupy: generování objektový Model jako externí soubor</span><span class="sxs-lookup"><span data-stu-id="2ef0b-102">How to: Generate the Object Model as an External File</span></span>
<span data-ttu-id="2ef0b-103">Jako alternativu k mapování na základě atributů můžete pomocí nástroje příkazového řádku na SQLMetal vygenerovat objektový model jako externí soubor XML.</span><span class="sxs-lookup"><span data-stu-id="2ef0b-103">As an alternative to attribute-based mapping, you can generate your object model as an external XML file by using the SQLMetal command-line tool.</span></span> <span data-ttu-id="2ef0b-104">Další informace najdete v tématu [SqlMetal.exe (nástroj pro vytváření kódu)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="2ef0b-104">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span> <span data-ttu-id="2ef0b-105">Pomocí externího souboru XML mapování snížit zbytečné soubory do vašeho kódu.</span><span class="sxs-lookup"><span data-stu-id="2ef0b-105">By using an external XML mapping file, you reduce clutter in your code.</span></span> <span data-ttu-id="2ef0b-106">Můžete také změnit chování změnou externího souboru bez nutnosti rekompilace binární soubory aplikace.</span><span class="sxs-lookup"><span data-stu-id="2ef0b-106">You can also change behavior by modifying the external file without recompiling the binaries of your application.</span></span> <span data-ttu-id="2ef0b-107">Další informace najdete v tématu [externí mapování](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="2ef0b-107">For more information, see [External Mapping](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2ef0b-108">[!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] Nepodporuje vzniku souboru externí mapování.</span><span class="sxs-lookup"><span data-stu-id="2ef0b-108">The [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] does not support generation of an external mapping file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ef0b-109">Příklad</span><span class="sxs-lookup"><span data-stu-id="2ef0b-109">Example</span></span>  
 <span data-ttu-id="2ef0b-110">Následující příkaz vytvoří soubor externí mapování z ukázková databáze Northwind.</span><span class="sxs-lookup"><span data-stu-id="2ef0b-110">The following command generates an external mapping file from the Northwind sample database.</span></span>  
  
```  
sqlmetal /server:myserver /database:northwind /map:externalfile.xml  
```  
  
## <a name="example"></a><span data-ttu-id="2ef0b-111">Příklad</span><span class="sxs-lookup"><span data-stu-id="2ef0b-111">Example</span></span>  
 <span data-ttu-id="2ef0b-112">Následující výňatek ze souboru externí mapování zobrazuje v ukázková databáze Northwind mapování pro tabulku zákazníků.</span><span class="sxs-lookup"><span data-stu-id="2ef0b-112">The following excerpt from an external mapping file shows the mapping for the Customers table in the Northwind sample database.</span></span> <span data-ttu-id="2ef0b-113">Tato výňatek ze byl vygenerován spuštěním na SQLMetal s **/map** možnost.</span><span class="sxs-lookup"><span data-stu-id="2ef0b-113">This excerpt was generated by executing SQLMetal with the **/map** option.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<Database xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" Name="northwnd">  
  <Table Name="Customers">  
    <Type Name=".Customer">  
      <Column Name="CustomerID" Member="CustomerID" Storage="_CustomerID" DbType="NChar(5) NOT NULL" CanBeNull="False" IsPrimaryKey="True" />  
      <Column Name="CompanyName" Member="CompanyName" Storage="_CompanyName" DbType="NVarChar(40) NOT NULL" CanBeNull="False" />  
      <Column Name="ContactName" Member="ContactName" Storage="_ContactName" DbType="NVarChar(30)" />  
      <Column Name="ContactTitle" Member="ContactTitle" Storage="_ContactTitle" DbType="NVarChar(30)" />  
      <Column Name="Address" Member="Address" Storage="_Address" DbType="NVarChar(60)" />  
      <Column Name="City" Member="City" Storage="_City" DbType="NVarChar(15)" />  
      <Column Name="Region" Member="Region" Storage="_Region" DbType="NVarChar(15)" />  
      <Column Name="PostalCode" Member="PostalCode" Storage="_PostalCode" DbType="NVarChar(10)" />  
      <Column Name="Country" Member="Country" Storage="_Country" DbType="NVarChar(15)" />  
      <Column Name="Phone" Member="Phone" Storage="_Phone" DbType="NVarChar(24)" />  
      <Column Name="Fax" Member="Fax" Storage="_Fax" DbType="NVarChar(24)" />  
      <Association Name="FK_CustomerCustomerDemo_Customers" Member="CustomerCustomerDemos" Storage="_CustomerCustomerDemos" ThisKey="CustomerID" OtherTable="CustomerCustomerDemo" OtherKey="CustomerID" DeleteRule="NO ACTION" />  
      <Association Name="FK_Orders_Customers" Member="Orders" Storage="_Orders" ThisKey="CustomerID" OtherTable="Orders" OtherKey="CustomerID" DeleteRule="NO ACTION" />  
    </Type>  
  </Table>  
</Database>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2ef0b-114">Viz také</span><span class="sxs-lookup"><span data-stu-id="2ef0b-114">See Also</span></span>  
 [<span data-ttu-id="2ef0b-115">Vytváření objektový Model</span><span class="sxs-lookup"><span data-stu-id="2ef0b-115">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)  
 [<span data-ttu-id="2ef0b-116">Externí mapování</span><span class="sxs-lookup"><span data-stu-id="2ef0b-116">External Mapping</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md)  
 [<span data-ttu-id="2ef0b-117">Postupy: generování objektový Model v jazyce Visual Basic nebo C#</span><span class="sxs-lookup"><span data-stu-id="2ef0b-117">How to: Generate the Object Model in Visual Basic or C#</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-generate-the-object-model-in-visual-basic-or-csharp.md)
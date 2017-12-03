---
title: "Naplnění datové sady z modul DataAdapter"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 3fa0ac7d-e266-4954-bfac-3fbe2f913153
caps.latest.revision: "6"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 3648340050e5ee3a761efcbedd89f649ff8d9c91
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="populating-a-dataset-from-a-dataadapter"></a><span data-ttu-id="e1a8d-102">Naplnění datové sady z modul DataAdapter</span><span class="sxs-lookup"><span data-stu-id="e1a8d-102">Populating a DataSet from a DataAdapter</span></span>
<span data-ttu-id="e1a8d-103">[!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] <xref:System.Data.DataSet> Je rezidentní reprezentace data, která poskytuje konzistentní relační programovací model bez ohledu na zdroj dat.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-103">The [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]<xref:System.Data.DataSet> is a memory-resident representation of data that provides a consistent relational programming model independent of the data source.</span></span> <span data-ttu-id="e1a8d-104">`DataSet` Představuje kompletní sadu dat, který obsahuje tabulky, omezení a relace mezi tabulkami.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-104">The `DataSet` represents a complete set of data that includes tables, constraints, and relationships among the tables.</span></span> <span data-ttu-id="e1a8d-105">Protože `DataSet` je nezávislý na zdroji dat, `DataSet` může obsahovat data místní aplikace a data z více zdrojů dat.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-105">Because the `DataSet` is independent of the data source, a `DataSet` can include data local to the application, and data from multiple data sources.</span></span> <span data-ttu-id="e1a8d-106">Interakce s existujícími zdroji dat jsou řízeny prostřednictvím `DataAdapter`.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-106">Interaction with existing data sources is controlled through the `DataAdapter`.</span></span>  
  
 <span data-ttu-id="e1a8d-107">`SelectCommand` Vlastnost `DataAdapter` je `Command` objekt, který načte data z datového zdroje.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-107">The `SelectCommand` property of the `DataAdapter` is a `Command` object that retrieves data from the data source.</span></span> <span data-ttu-id="e1a8d-108">`InsertCommand`, `UpdateCommand`, A `DeleteCommand` vlastnosti `DataAdapter` jsou `Command` objekty, které spravují aktualizace dat ve zdroji dat podle změny provedené v datech v `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-108">The `InsertCommand`, `UpdateCommand`, and `DeleteCommand` properties of the `DataAdapter` are `Command` objects that manage updates to the data in the data source according to modifications made to the data in the `DataSet`.</span></span> <span data-ttu-id="e1a8d-109">Tyto vlastnosti jsou popsané v podrobněji [aktualizace zdroje dat s DataAdapters](../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md).</span><span class="sxs-lookup"><span data-stu-id="e1a8d-109">These properties are covered in more detail in [Updating Data Sources with DataAdapters](../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md).</span></span>  
  
 <span data-ttu-id="e1a8d-110">`Fill` Metodu `DataAdapter` se používá k naplnění `DataSet` s výsledky `SelectCommand` z `DataAdapter`.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-110">The `Fill` method of the `DataAdapter` is used to populate a `DataSet` with the results of the `SelectCommand` of the `DataAdapter`.</span></span> <span data-ttu-id="e1a8d-111">`Fill`vezme jako jeho argumenty `DataSet` vyplnit a `DataTable` objekt nebo název `DataTable` pro vyplnění pomocí řádků vrácených `SelectCommand`.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-111">`Fill` takes as its arguments a `DataSet` to be populated, and a `DataTable` object, or the name of the `DataTable` to be filled with the rows returned from the `SelectCommand`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e1a8d-112">Pomocí `DataAdapter` načíst všechny tabulky trvá určitou dobu, hlavně v případě, že je velký počet řádků v tabulce.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-112">Using the `DataAdapter` to retrieve all of a table takes time, especially if there are many rows in the table.</span></span> <span data-ttu-id="e1a8d-113">Důvodem je, že přístup k databázi, vyhledání a zpracování dat, a potom přenos dat do klienta je časově náročná.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-113">This is because accessing the database, locating and processing the data, and then transferring the data to the client is time-consuming.</span></span> <span data-ttu-id="e1a8d-114">Všechny tabulky stahování do klienta zamkne taky všechny řádky na serveru.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-114">Pulling all of the table to the client also locks all of the rows on the server.</span></span> <span data-ttu-id="e1a8d-115">Chcete-li zvýšit výkon, můžete použít `WHERE` klauzule výrazně omezit počet řádků, je vrácen do klienta.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-115">To improve performance, you can use the `WHERE` clause to greatly reduce the number of rows returned to the client.</span></span> <span data-ttu-id="e1a8d-116">Můžete také snížit množství dat vrácen do klienta tak, že pouze explicitně uvedete požadované sloupce v `SELECT` příkaz.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-116">You can also reduce the amount of data returned to the client by only explicitly listing required columns in the `SELECT` statement.</span></span> <span data-ttu-id="e1a8d-117">Jiné dobrým řešením je načíst řádky v dávkách (například několik set řádky v čase) a další dávku načíst pouze po dokončení aktuální dávkou klienta.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-117">Another good workaround is to retrieve the rows in batches (such as several hundred rows at a time) and only retrieve the next batch when the client is finished with the current batch.</span></span>  
  
 <span data-ttu-id="e1a8d-118">`Fill` Metoda používá `DataReader` objekt implicitně vrátí názvy sloupců a typy, které se používají k vytváření tabulek v `DataSet`a data k naplnění řádky z tabulky v `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-118">The `Fill` method uses the `DataReader` object implicitly to return the column names and types that are used to create the tables in the `DataSet`, and the data to populate the rows of the tables in the `DataSet`.</span></span> <span data-ttu-id="e1a8d-119">Tabulky a sloupce jsou vytvářeny, pouze pokud už neexistují; v opačném případě `Fill` používá existující `DataSet` schématu.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-119">Tables and columns are only created if they do not already exist; otherwise `Fill` uses the existing `DataSet` schema.</span></span> <span data-ttu-id="e1a8d-120">Typy sloupců jsou vytvořené jako [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] typů podle tabulky v [mapování datového typu v ADO.NET](../../../../docs/framework/data/adonet/data-type-mappings-in-ado-net.md).</span><span class="sxs-lookup"><span data-stu-id="e1a8d-120">Column types are created as [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] types according to the tables in [Data Type Mappings in ADO.NET](../../../../docs/framework/data/adonet/data-type-mappings-in-ado-net.md).</span></span> <span data-ttu-id="e1a8d-121">Primární klíče, které nejsou vytvořeny, pokud existují ve zdroji dat a `DataAdapter` **.**`MissingSchemaAction`</span><span class="sxs-lookup"><span data-stu-id="e1a8d-121">Primary keys are not created unless they exist in the data source and `DataAdapter`**.**`MissingSchemaAction`</span></span> <span data-ttu-id="e1a8d-122">je nastavena na `MissingSchemaAction` **.** `AddWithKey`.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-122">is set to `MissingSchemaAction`**.**`AddWithKey`.</span></span> <span data-ttu-id="e1a8d-123">Pokud `Fill` zjistí, že primární klíč pro tabulku existuje, přepíše data `DataSet` s daty ze zdroje dat pro řádky, kde hodnoty sloupec primárního klíče shodovat s hodnotami řádku vrátí ze zdroje dat.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-123">If `Fill` finds that a primary key exists for a table, it will overwrite data in the `DataSet` with data from the data source for rows where the primary key column values match those of the row returned from the data source.</span></span> <span data-ttu-id="e1a8d-124">Pokud se nenajde žádný primární klíč, připojí se data k tabulky v `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-124">If no primary key is found, the data is appended to the tables in the `DataSet`.</span></span> <span data-ttu-id="e1a8d-125">`Fill`používá všech mapování, která mohou existovat při naplňování `DataSet` (najdete v části [DataAdapter DataTable a mapování DataColumn](../../../../docs/framework/data/adonet/dataadapter-datatable-and-datacolumn-mappings.md)).</span><span class="sxs-lookup"><span data-stu-id="e1a8d-125">`Fill` uses any mappings that may exist when you populate the `DataSet` (see [DataAdapter DataTable and DataColumn Mappings](../../../../docs/framework/data/adonet/dataadapter-datatable-and-datacolumn-mappings.md)).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e1a8d-126">Pokud `SelectCommand` vrátí výsledky z vnějšího spojení, `DataAdapter` nenastaví `PrimaryKey` výsledná hodnota `DataTable`.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-126">If the `SelectCommand` returns the results of an OUTER JOIN, the `DataAdapter` does not set a `PrimaryKey` value for the resulting `DataTable`.</span></span> <span data-ttu-id="e1a8d-127">Je nutné definovat `PrimaryKey` sami, abyste měli jistotu, že jsou správně přeložit duplicitní řádky.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-127">You must define the `PrimaryKey` yourself to make sure that duplicate rows are resolved correctly.</span></span> <span data-ttu-id="e1a8d-128">Další informace najdete v tématu [definování primárních klíčů](../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).</span><span class="sxs-lookup"><span data-stu-id="e1a8d-128">For more information, see [Defining Primary Keys](../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).</span></span>  
  
 <span data-ttu-id="e1a8d-129">Následující příklad kódu vytvoří instance <xref:System.Data.SqlClient.SqlDataAdapter> používající <xref:System.Data.SqlClient.SqlConnection> Microsoft SQL Server `Northwind` databáze a naplní <xref:System.Data.DataTable> v `DataSet` se do seznamu zákazníků.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-129">The following code example creates an instance of a <xref:System.Data.SqlClient.SqlDataAdapter> that uses a <xref:System.Data.SqlClient.SqlConnection> to the Microsoft SQL Server `Northwind` database and populates a <xref:System.Data.DataTable> in a `DataSet` with the list of customers.</span></span> <span data-ttu-id="e1a8d-130">Příkaz jazyka SQL a <xref:System.Data.SqlClient.SqlConnection> předáno argumentů <xref:System.Data.SqlClient.SqlDataAdapter> konstruktor se používají k vytvoření <xref:System.Data.SqlClient.SqlDataAdapter.SelectCommand%2A> vlastnost <xref:System.Data.SqlClient.SqlDataAdapter>.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-130">The SQL statement and <xref:System.Data.SqlClient.SqlConnection> arguments passed to the <xref:System.Data.SqlClient.SqlDataAdapter> constructor are used to create the <xref:System.Data.SqlClient.SqlDataAdapter.SelectCommand%2A> property of the <xref:System.Data.SqlClient.SqlDataAdapter>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1a8d-131">Příklad</span><span class="sxs-lookup"><span data-stu-id="e1a8d-131">Example</span></span>  
  
```vb  
' Assumes that connection is a valid SqlConnection object.  
Dim queryString As String = _  
  "SELECT CustomerID, CompanyName FROM dbo.Customers"  
Dim adapter As SqlDataAdapter = New SqlDataAdapter( _  
  queryString, connection)  
  
Dim customers As DataSet = New DataSet  
adapter.Fill(customers, "Customers")  
```  
  
```csharp  
// Assumes that connection is a valid SqlConnection object.  
string queryString =   
  "SELECT CustomerID, CompanyName FROM dbo.Customers";  
SqlDataAdapter adapter = new SqlDataAdapter(queryString, connection);  
  
DataSet customers = new DataSet();  
adapter.Fill(customers, "Customers");  
```  
  
> [!NOTE]
>  <span data-ttu-id="e1a8d-132">Kód zobrazí v tomto příkladu se neotevře explicitně a zavřete `Connection`.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-132">The code shown in this example does not explicitly open and close the `Connection`.</span></span> <span data-ttu-id="e1a8d-133">`Fill` Metoda implicitně otevře `Connection` , `DataAdapter` používá, jestliže zjistí, že připojení není již otevřený.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-133">The `Fill` method implicitly opens the `Connection` that the `DataAdapter` is using if it finds that the connection is not already open.</span></span> <span data-ttu-id="e1a8d-134">Pokud `Fill` otevřít připojení, také uzavře připojení při `Fill` po dokončení.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-134">If `Fill` opened the connection, it also closes the connection when `Fill` is finished.</span></span> <span data-ttu-id="e1a8d-135">Když budete pracovat s jedinou operací, jako to může zjednodušit kódu `Fill` nebo `Update`.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-135">This can simplify your code when you deal with a single operation such as a `Fill` or an `Update`.</span></span> <span data-ttu-id="e1a8d-136">Ale pokud provádíte více operací, které vyžadují otevřené připojení, můžete zlepšit výkon aplikace explicitně volání `Open` metodu `Connection`, provádění operací na zdroji dat a potom volání `Close` metodu `Connection`.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-136">However, if you are performing multiple operations that require an open connection, you can improve the performance of your application by explicitly calling the `Open` method of the `Connection`, performing the operations against the data source, and then calling the `Close` method of the `Connection`.</span></span> <span data-ttu-id="e1a8d-137">Doporučujeme nechat připojení ke zdroji dat otevřené jako stručně kvůli uvolnění prostředků pro použití v jiných klientských aplikacích.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-137">You should try to keep connections to the data source open as briefly as possible to free resources for use by other client applications.</span></span>  
  
## <a name="multiple-result-sets"></a><span data-ttu-id="e1a8d-138">Více sad výsledků dotazu</span><span class="sxs-lookup"><span data-stu-id="e1a8d-138">Multiple Result Sets</span></span>  
 <span data-ttu-id="e1a8d-139">Pokud `DataAdapter` komunikaci sady více výsledků, dojde k několika tabulkám ve `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-139">If the `DataAdapter` encounters multiple result sets, it creates multiple tables in the `DataSet`.</span></span> <span data-ttu-id="e1a8d-140">V tabulkách jsou uvedeny přírůstkové výchozí název tabulky*N*, od verze "Tabulka" pro Table0.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-140">The tables are given an incremental default name of Table*N*, starting with "Table" for Table0.</span></span> <span data-ttu-id="e1a8d-141">Pokud je název tabulky předat jako argument k `Fill` metoda, v tabulkách jsou uvedeny přírůstkové výchozí název TableName*N*, od verze "TableName" pro TableName0.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-141">If a table name is passed as an argument to the `Fill` method, the tables are given an incremental default name of TableName*N*, starting with "TableName" for TableName0.</span></span>  
  
## <a name="populating-a-dataset-from-multiple-dataadapters"></a><span data-ttu-id="e1a8d-142">Naplnění datové sady z více DataAdapters</span><span class="sxs-lookup"><span data-stu-id="e1a8d-142">Populating a DataSet from Multiple DataAdapters</span></span>  
 <span data-ttu-id="e1a8d-143">Libovolný počet `DataAdapter` objekty lze použít s `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-143">Any number of `DataAdapter` objects can be used with a `DataSet`.</span></span> <span data-ttu-id="e1a8d-144">Každý `DataAdapter` lze použít k vyplnění jeden nebo více `DataTable` objekty a vyřešte aktualizace zpět do zdroje dat relevantní.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-144">Each `DataAdapter` can be used to fill one or more `DataTable` objects and resolve updates back to the relevant data source.</span></span> <span data-ttu-id="e1a8d-145">`DataRelation`a `Constraint` objekty mohou být přidány do `DataSet` místně, což umožňuje související data ze zdrojů dat v odlišných typů.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-145">`DataRelation` and `Constraint` objects can be added to the `DataSet` locally, which enables you to relate data from dissimilar data sources.</span></span> <span data-ttu-id="e1a8d-146">Například `DataSet` může obsahovat data z databáze Microsoft SQL Server, k databázi IBM DB2 vystavenou přes OLE DB a zdroj dat, který datové proudy XML.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-146">For example, a `DataSet` can contain data from a Microsoft SQL Server database, an IBM DB2 database exposed through OLE DB, and a data source that streams XML.</span></span> <span data-ttu-id="e1a8d-147">Jeden nebo více `DataAdapter` objekty může zpracovávat komunikaci pro každý zdroj dat.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-147">One or more `DataAdapter` objects can handle communication to each data source.</span></span>  
  
### <a name="example"></a><span data-ttu-id="e1a8d-148">Příklad</span><span class="sxs-lookup"><span data-stu-id="e1a8d-148">Example</span></span>  
 <span data-ttu-id="e1a8d-149">Následující příklad kódu naplní seznam zákazníků z `Northwind` databáze na serveru Microsoft SQL Server a seznam objednávky z `Northwind` databáze uložené v aplikaci Microsoft Access 2000.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-149">The following code example populates a list of customers from the `Northwind` database on Microsoft SQL Server, and a list of orders from the `Northwind` database stored in Microsoft Access 2000.</span></span> <span data-ttu-id="e1a8d-150">Vyplnění tabulky souvisejí s `DataRelation`, a pak je do seznamu zákazníků se zobrazují s objednávky tohoto zákazníka.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-150">The filled tables are related with a `DataRelation`, and the list of customers is then displayed with the orders for that customer.</span></span> <span data-ttu-id="e1a8d-151">Další informace o `DataRelation` objekty, najdete v části [přidání DataRelations](../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md) a [navigace DataRelations](../../../../docs/framework/data/adonet/dataset-datatable-dataview/navigating-datarelations.md).</span><span class="sxs-lookup"><span data-stu-id="e1a8d-151">For more information about `DataRelation` objects, see [Adding DataRelations](../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md) and [Navigating DataRelations](../../../../docs/framework/data/adonet/dataset-datatable-dataview/navigating-datarelations.md).</span></span>  
  
```vb  
' Assumes that customerConnection is a valid SqlConnection object.  
' Assumes that orderConnection is a valid OleDbConnection object.  
Dim custAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM dbo.Customers", customerConnection)  
  
Dim ordAdapter As OleDbDataAdapter = New OleDbDataAdapter( _  
  "SELECT * FROM Orders", orderConnection)  
  
Dim customerOrders As DataSet = New DataSet()  
custAdapter.Fill(customerOrders, "Customers")  
ordAdapter.Fill(customerOrders, "Orders")  
  
Dim relation As DataRelation = _  
  customerOrders.Relations.Add("CustOrders", _  
  customerOrders.Tables("Customers").Columns("CustomerID"), _   
  customerOrders.Tables("Orders").Columns("CustomerID"))  
  
Dim pRow, cRow As DataRow  
For Each pRow In customerOrders.Tables("Customers").Rows  
  Console.WriteLine(pRow("CustomerID").ToString())  
  
  For Each cRow In pRow.GetChildRows(relation)  
    Console.WriteLine(vbTab & cRow("OrderID").ToString())  
  Next  
Next  
```  
  
```csharp  
// Assumes that customerConnection is a valid SqlConnection object.  
// Assumes that orderConnection is a valid OleDbConnection object.  
SqlDataAdapter custAdapter = new SqlDataAdapter(  
  "SELECT * FROM dbo.Customers", customerConnection);  
OleDbDataAdapter ordAdapter = new OleDbDataAdapter(  
  "SELECT * FROM Orders", orderConnection);  
  
DataSet customerOrders = new DataSet();  
  
custAdapter.Fill(customerOrders, "Customers");  
ordAdapter.Fill(customerOrders, "Orders");  
  
DataRelation relation = customerOrders.Relations.Add("CustOrders",  
  customerOrders.Tables["Customers"].Columns["CustomerID"],  
  customerOrders.Tables["Orders"].Columns["CustomerID"]);  
  
foreach (DataRow pRow in customerOrders.Tables["Customers"].Rows)  
{  
  Console.WriteLine(pRow["CustomerID"]);  
   foreach (DataRow cRow in pRow.GetChildRows(relation))  
    Console.WriteLine("\t" + cRow["OrderID"]);  
}  
```  
  
## <a name="sql-server-decimal-type"></a><span data-ttu-id="e1a8d-152">Decimal – typ SQL serveru</span><span class="sxs-lookup"><span data-stu-id="e1a8d-152">SQL Server Decimal Type</span></span>  
 <span data-ttu-id="e1a8d-153">Ve výchozím nastavení `DataSet` ukládá data pomocí [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] datové typy.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-153">By default, the `DataSet` stores data by using [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] data types.</span></span> <span data-ttu-id="e1a8d-154">Pro většinu aplikací tyto poskytují pohodlný reprezentace informace o zdroji dat.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-154">For most applications, these provide a convenient representation of data source information.</span></span> <span data-ttu-id="e1a8d-155">Tento zápis však může způsobit problém, když je typ dat ve zdroji dat desítkový nebo číselný datový typ SQL serveru.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-155">However, this representation may cause a problem when the data type in the data source is a SQL Server decimal or numeric data type.</span></span> <span data-ttu-id="e1a8d-156">[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] `decimal` Datový typ povoluje maximálně 28 platných číslic, zatímco SQL Server `decimal` datový typ umožňuje 38 platných číslic.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-156">The [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] `decimal` data type allows a maximum of 28 significant digits, whereas the SQL Server `decimal` data type allows 38 significant digits.</span></span> <span data-ttu-id="e1a8d-157">Pokud `SqlDataAdapter` určuje během `Fill` operace, přesnost systému SQL Server `decimal` pole je větší než 28 znaků, že aktuálnímu řádku není přidáno do `DataTable`.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-157">If the `SqlDataAdapter` determines during a `Fill` operation that the precision of a SQL Server `decimal` field is larger than 28 characters, the current row is not added to the `DataTable`.</span></span> <span data-ttu-id="e1a8d-158">Místo toho `FillError` dojde k události, které umožňuje určit, zda bude ztrátu přesnosti dojít a reagují odpovídajícím způsobem.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-158">Instead the `FillError` event occurs, which enables you to determine whether a loss of precision will occur, and respond appropriately.</span></span> <span data-ttu-id="e1a8d-159">Další informace o `FillError` událostí, najdete v části [zpracování události DataAdapter](../../../../docs/framework/data/adonet/handling-dataadapter-events.md).</span><span class="sxs-lookup"><span data-stu-id="e1a8d-159">For more information about the `FillError` event, see [Handling DataAdapter Events](../../../../docs/framework/data/adonet/handling-dataadapter-events.md).</span></span> <span data-ttu-id="e1a8d-160">Získat systému SQL Server `decimal` hodnotu, můžete použít také <xref:System.Data.SqlClient.SqlDataReader> objekt a volání <xref:System.Data.SqlClient.SqlDataReader.GetSqlDecimal%2A> metoda.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-160">To get the SQL Server `decimal` value, you can also use a <xref:System.Data.SqlClient.SqlDataReader> object and call the <xref:System.Data.SqlClient.SqlDataReader.GetSqlDecimal%2A> method.</span></span>  
  
 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]<span data-ttu-id="e1a8d-161">2.0 zavedená rozšířenou podporu <xref:System.Data.SqlTypes> v `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-161"> 2.0 introduced enhanced support for <xref:System.Data.SqlTypes> in the `DataSet`.</span></span> <span data-ttu-id="e1a8d-162">Další informace najdete v tématu [SqlTypes a datovou sadu](../../../../docs/framework/data/adonet/sql/sqltypes-and-the-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="e1a8d-162">For more information, see [SqlTypes and the DataSet](../../../../docs/framework/data/adonet/sql/sqltypes-and-the-dataset.md).</span></span>  
  
## <a name="ole-db-chapters"></a><span data-ttu-id="e1a8d-163">OLE DB kapitolám</span><span class="sxs-lookup"><span data-stu-id="e1a8d-163">OLE DB Chapters</span></span>  
 <span data-ttu-id="e1a8d-164">Hierarchická sady řádků či kapitolám (typ OLE DB `DBTYPE_HCHAPTER`, typ ADO `adChapter`) lze použít k vyplnění obsah `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-164">Hierarchical rowsets, or chapters (OLE DB type `DBTYPE_HCHAPTER`, ADO type `adChapter`) can be used to fill the contents of a `DataSet`.</span></span> <span data-ttu-id="e1a8d-165">Když <xref:System.Data.OleDb.OleDbDataAdapter> zaznamená sloupec nepoužívaly kapitoly během `Fill` operace, `DataTable` se vytvoří nepoužívaly kapitoly ve sloupci a tato tabulka je plná sloupců a řádků z kapitoly.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-165">When the <xref:System.Data.OleDb.OleDbDataAdapter> encounters a chaptered column during a `Fill` operation, a `DataTable` is created for the chaptered column, and that table is filled with the columns and rows from the chapter.</span></span> <span data-ttu-id="e1a8d-166">V tabulce vytvořené pro nepoužívaly kapitoly sloupec nazýval pomocí názvu nadřazené tabulky a název sloupce nepoužívaly kapitoly ve tvaru "*ParentTableNameChapteredColumnName*".</span><span class="sxs-lookup"><span data-stu-id="e1a8d-166">The table created for the chaptered column is named by using both the parent table name and the chaptered column name in the form "*ParentTableNameChapteredColumnName*".</span></span> <span data-ttu-id="e1a8d-167">Pokud tabulka již existuje v `DataSet` odpovídající názvu nepoužívaly kapitoly sloupce, v aktuální tabulce, naplní se kapitoly data.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-167">If a table already exists in the `DataSet` that matches the name of the chaptered column, the current table is filled with the chapter data.</span></span> <span data-ttu-id="e1a8d-168">Pokud je existující tabulky, který odpovídá sloupci najít v kapitole žádný sloupec, nový sloupec přidán.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-168">If there is no column in an existing table that matches a column found in the chapter, a new column is added.</span></span>  
  
 <span data-ttu-id="e1a8d-169">Před tabulky v `DataSet` jsou vyplněny s daty ve sloupcích nepoužívaly kapitoly, vytvoření vztahu mezi nadřazenými a podřízenými tabulky hierarchické řádků přidáním sloupec celé číslo do nadřazené a podřízené tabulky, nastavení nadřazeného sloupce automatickým krokem a vytváření `DataRelation` použití přidaných sloupců z obou tabulek.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-169">Before the tables in the `DataSet` are filled with the data in the chaptered columns, a relation is created between the parent and child tables of the hierarchical rowset by adding an integer column to both the parent and child table, setting the parent column to auto-increment, and creating a `DataRelation` using the added columns from both tables.</span></span> <span data-ttu-id="e1a8d-170">Přidání vztah jmenuje pomocí nadřazené názvy sloupců tabulky a kapitoly ve tvaru "*ParentTableNameChapterColumnName*".</span><span class="sxs-lookup"><span data-stu-id="e1a8d-170">The added relation is named by using the parent table and chapter column names in the form "*ParentTableNameChapterColumnName*".</span></span>  
  
 <span data-ttu-id="e1a8d-171">Všimněte si, že v pouze existuje sloupec v relaci `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-171">Note that the related column only exists in the `DataSet`.</span></span> <span data-ttu-id="e1a8d-172">Následné výplněmi ze zdroje dat může způsobit nové řádky, které chcete přidat do tabulky místo změny slučování do existujících řádků.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-172">Subsequent fills from the data source can cause new rows to be added to the tables instead of changes being merged into existing rows.</span></span>  
  
 <span data-ttu-id="e1a8d-173">Všimněte si také, že pokud použijete `DataAdapter.Fill` přetížení, které přijímá `DataTable`, bude vyplněno pouze tuto tabulku.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-173">Note also that, if you use the `DataAdapter.Fill` overload that takes a `DataTable`, only that table will be filled.</span></span> <span data-ttu-id="e1a8d-174">Sloupec automaticky rostoucí celé číslo se stále zařadí do tabulky, ale žádné podřízené tabulky se vytvoří nebo vyplněna a vytvoří se žádný vztah.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-174">An auto-incrementing integer column will still be added to the table, but no child table will be created or filled, and no relation will be created.</span></span>  
  
 <span data-ttu-id="e1a8d-175">Následující příklad používá zprostředkovatele MSDataShape ke generování objednávek každému zákazníkovi neočekávaný sloupec kapitoly v seznamu zákazníků.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-175">The following example uses the MSDataShape Provider to generate a chapter column of orders for each customer in a list of customers.</span></span> <span data-ttu-id="e1a8d-176">A `DataSet` pak, naplní se data.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-176">A `DataSet` is then filled with the data.</span></span>  
  
```vb  
Using connection As OleDbConnection = New OleDbConnection( _  
  "Provider=MSDataShape;Data Provider=SQLOLEDB;" & _  
  "Data Source=(local);Integrated " & _  
  "Security=SSPI;Initial Catalog=northwind")  
  
Dim adapter As OleDbDataAdapter = New OleDbDataAdapter( _  
  "SHAPE {SELECT CustomerID, CompanyName FROM Customers} " & _  
  "APPEND ({SELECT CustomerID, OrderID FROM Orders} AS Orders " & _  
  "RELATE CustomerID TO CustomerID)", connection)  
  
Dim customers As DataSet = New DataSet()  
  
adapter.Fill(customers, "Customers")  
End Using  
```  
  
```csharp  
using (OleDbConnection connection = new OleDbConnection("Provider=MSDataShape;Data Provider=SQLOLEDB;" +  
  "Data Source=(local);Integrated Security=SSPI;Initial Catalog=northwind"))  
{  
OleDbDataAdapter adapter = new OleDbDataAdapter("SHAPE {SELECT CustomerID, CompanyName FROM Customers} " +  
  "APPEND ({SELECT CustomerID, OrderID FROM Orders} AS Orders " +  
  "RELATE CustomerID TO CustomerID)", connection);  
  
DataSet customers = new DataSet();  
adapter.Fill(customers, "Customers");  
}  
```  
  
 <span data-ttu-id="e1a8d-177">Když `Fill` bylo dokončeno, `DataSet` obsahuje dvě tabulky: `Customers` a `CustomersOrders`, kde `CustomersOrders` představuje nepoužívaly kapitoly sloupec.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-177">When the `Fill` operation is complete, the `DataSet` contains two tables: `Customers` and `CustomersOrders`, where `CustomersOrders` represents the chaptered column.</span></span> <span data-ttu-id="e1a8d-178">Sloupec s názvem `Orders` se přidá do `Customers` tabulky a další sloupec s názvem `CustomersOrders` se přidá do `CustomersOrders` tabulky.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-178">An additional column named `Orders` is added to the `Customers` table, and an additional column named `CustomersOrders` is added to the `CustomersOrders` table.</span></span> <span data-ttu-id="e1a8d-179">`Orders` Sloupec v `Customers` tabulky je nastavena na automatickým krokem.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-179">The `Orders` column in the `Customers` table is set to auto-increment.</span></span> <span data-ttu-id="e1a8d-180">A `DataRelation`, `CustomersOrders`, se vytvoří pomocí sloupců, které byly přidány do tabulky s `Customers` jako v nadřazené tabulce.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-180">A `DataRelation`, `CustomersOrders`, is created by using the columns that were added to the tables with `Customers` as the parent table.</span></span> <span data-ttu-id="e1a8d-181">Následující tabulky uvádí některé ukázkové výsledky.</span><span class="sxs-lookup"><span data-stu-id="e1a8d-181">The following tables show some sample results.</span></span>  
  
### <a name="tablename-customers"></a><span data-ttu-id="e1a8d-182">Název tabulky: zákazníků</span><span class="sxs-lookup"><span data-stu-id="e1a8d-182">TableName: Customers</span></span>  
  
|<span data-ttu-id="e1a8d-183">CustomerID</span><span class="sxs-lookup"><span data-stu-id="e1a8d-183">CustomerID</span></span>|<span data-ttu-id="e1a8d-184">NázevSpolečnosti</span><span class="sxs-lookup"><span data-stu-id="e1a8d-184">CompanyName</span></span>|<span data-ttu-id="e1a8d-185">Objednávky</span><span class="sxs-lookup"><span data-stu-id="e1a8d-185">Orders</span></span>|  
|----------------|-----------------|------------|  
|<span data-ttu-id="e1a8d-186">ALFKI</span><span class="sxs-lookup"><span data-stu-id="e1a8d-186">ALFKI</span></span>|<span data-ttu-id="e1a8d-187">Alfreds Futterkiste</span><span class="sxs-lookup"><span data-stu-id="e1a8d-187">Alfreds Futterkiste</span></span>|<span data-ttu-id="e1a8d-188">0</span><span class="sxs-lookup"><span data-stu-id="e1a8d-188">0</span></span>|  
|<span data-ttu-id="e1a8d-189">ANATR</span><span class="sxs-lookup"><span data-stu-id="e1a8d-189">ANATR</span></span>|<span data-ttu-id="e1a8d-190">ANA Trujillo Emparedados y helados</span><span class="sxs-lookup"><span data-stu-id="e1a8d-190">Ana Trujillo Emparedados y helados</span></span>|<span data-ttu-id="e1a8d-191">1</span><span class="sxs-lookup"><span data-stu-id="e1a8d-191">1</span></span>|  
  
### <a name="tablename-customersorders"></a><span data-ttu-id="e1a8d-192">Název tabulky: CustomersOrders</span><span class="sxs-lookup"><span data-stu-id="e1a8d-192">TableName: CustomersOrders</span></span>  
  
|<span data-ttu-id="e1a8d-193">CustomerID</span><span class="sxs-lookup"><span data-stu-id="e1a8d-193">CustomerID</span></span>|<span data-ttu-id="e1a8d-194">OrderID</span><span class="sxs-lookup"><span data-stu-id="e1a8d-194">OrderID</span></span>|<span data-ttu-id="e1a8d-195">CustomersOrders</span><span class="sxs-lookup"><span data-stu-id="e1a8d-195">CustomersOrders</span></span>|  
|----------------|-------------|---------------------|  
|<span data-ttu-id="e1a8d-196">ALFKI</span><span class="sxs-lookup"><span data-stu-id="e1a8d-196">ALFKI</span></span>|<span data-ttu-id="e1a8d-197">10643</span><span class="sxs-lookup"><span data-stu-id="e1a8d-197">10643</span></span>|<span data-ttu-id="e1a8d-198">0</span><span class="sxs-lookup"><span data-stu-id="e1a8d-198">0</span></span>|  
|<span data-ttu-id="e1a8d-199">ALFKI</span><span class="sxs-lookup"><span data-stu-id="e1a8d-199">ALFKI</span></span>|<span data-ttu-id="e1a8d-200">10692</span><span class="sxs-lookup"><span data-stu-id="e1a8d-200">10692</span></span>|<span data-ttu-id="e1a8d-201">0</span><span class="sxs-lookup"><span data-stu-id="e1a8d-201">0</span></span>|  
|<span data-ttu-id="e1a8d-202">ANATR</span><span class="sxs-lookup"><span data-stu-id="e1a8d-202">ANATR</span></span>|<span data-ttu-id="e1a8d-203">10308</span><span class="sxs-lookup"><span data-stu-id="e1a8d-203">10308</span></span>|<span data-ttu-id="e1a8d-204">1</span><span class="sxs-lookup"><span data-stu-id="e1a8d-204">1</span></span>|  
|<span data-ttu-id="e1a8d-205">ANATR</span><span class="sxs-lookup"><span data-stu-id="e1a8d-205">ANATR</span></span>|<span data-ttu-id="e1a8d-206">10625</span><span class="sxs-lookup"><span data-stu-id="e1a8d-206">10625</span></span>|<span data-ttu-id="e1a8d-207">1</span><span class="sxs-lookup"><span data-stu-id="e1a8d-207">1</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e1a8d-208">Viz také</span><span class="sxs-lookup"><span data-stu-id="e1a8d-208">See Also</span></span>  
 [<span data-ttu-id="e1a8d-209">DataAdapters a DataReaders</span><span class="sxs-lookup"><span data-stu-id="e1a8d-209">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [<span data-ttu-id="e1a8d-210">Mapování datového typu v technologii ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e1a8d-210">Data Type Mappings in ADO.NET</span></span>](../../../../docs/framework/data/adonet/data-type-mappings-in-ado-net.md)  
 [<span data-ttu-id="e1a8d-211">Úprava dat s DbDataAdapter</span><span class="sxs-lookup"><span data-stu-id="e1a8d-211">Modifying Data with a DbDataAdapter</span></span>](../../../../docs/framework/data/adonet/modifying-data-with-a-dbdataadapter.md)  
 [<span data-ttu-id="e1a8d-212">Více sad výsledků dotazu Active (MARS)</span><span class="sxs-lookup"><span data-stu-id="e1a8d-212">Multiple Active Result Sets (MARS)</span></span>](../../../../docs/framework/data/adonet/sql/multiple-active-result-sets-mars.md)  
 [<span data-ttu-id="e1a8d-213">ADO.NET spravované zprostředkovatelé a středisku pro vývojáře datové sady</span><span class="sxs-lookup"><span data-stu-id="e1a8d-213">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
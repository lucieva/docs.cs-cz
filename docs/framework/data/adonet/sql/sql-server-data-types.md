---
title: Data serveru SQL typy a ADO.NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 81b43550-23e8-43bb-b460-7eb8ac825c33
caps.latest.revision: "6"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 16c675491a378d72d82a252d79a73379f494893c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="sql-server-data-types-and-adonet"></a><span data-ttu-id="46894-102">Data serveru SQL typy a ADO.NET</span><span class="sxs-lookup"><span data-stu-id="46894-102">SQL Server Data Types and ADO.NET</span></span>
<span data-ttu-id="46894-103">SQL Server a rozhraní .NET Framework jsou založené na jiný typ systémy, které může mít za následek ztrátu dat.</span><span class="sxs-lookup"><span data-stu-id="46894-103">SQL Server and the .NET Framework are based on different type systems, which can result in potential data loss.</span></span> <span data-ttu-id="46894-104">Chcete-li zachovat integritu dat, zprostředkovatel dat .NET Framework pro SQL Server (<xref:System.Data.SqlClient>) poskytuje typu přístupového objektu metody pro práci s daty na serveru SQL.</span><span class="sxs-lookup"><span data-stu-id="46894-104">To preserve data integrity, the .NET Framework Data Provider for SQL Server (<xref:System.Data.SqlClient>) provides typed accessor methods for working with SQL Server data.</span></span> <span data-ttu-id="46894-105">Můžete použít výčtů ve <xref:System.Data.SqlDbType> třídy k určení <xref:System.Data.SqlClient.SqlParameter> datové typy.</span><span class="sxs-lookup"><span data-stu-id="46894-105">You can use the enumerations in the <xref:System.Data.SqlDbType> classes to specify <xref:System.Data.SqlClient.SqlParameter> data types.</span></span>  
  
 <span data-ttu-id="46894-106">Další informace a tabulky, které popisuje data zadáte mapování mezi datové typy rozhraní .NET Framework a SQL Server najdete v tématu [mapování datového typu SQL Server](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md).</span><span class="sxs-lookup"><span data-stu-id="46894-106">For more information and a table that that describes the data type mappings between SQL Server and .NET Framework data types, see [SQL Server Data Type Mappings](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md).</span></span>  
  
 <span data-ttu-id="46894-107">SQL Server 2008 zavádí nové typy dat, které jsou navržené tak, abyste splnili obchodní požadavky pro práci s datum a čas, strukturovaná, částečně strukturovaná i nestrukturovaná data.</span><span class="sxs-lookup"><span data-stu-id="46894-107">SQL Server 2008 introduces new data types that are designed to meet business needs to work with date and time, structured, semi-structured, and unstructured data.</span></span> <span data-ttu-id="46894-108">Ty jsou popsány v SQL Server 2008 Books Online.</span><span class="sxs-lookup"><span data-stu-id="46894-108">These are documented in SQL Server 2008 Books Online.</span></span>  
  
 <span data-ttu-id="46894-109">Datové typy systému SQL Server, které jsou k dispozici pro použití ve vaší aplikaci závisí na verzi systému SQL Server, který používáte.</span><span class="sxs-lookup"><span data-stu-id="46894-109">The SQL Server data types that are available for use in your application depends on the version of SQL Server that you are using.</span></span> <span data-ttu-id="46894-110">Další informace najdete v tématu příslušné verze SQL Server Books Online v následující tabulce.</span><span class="sxs-lookup"><span data-stu-id="46894-110">For more information, see the relevant version of SQL Server Books Online in the following table.</span></span>  
  
 <span data-ttu-id="46894-111">**SQL Server Books Online**</span><span class="sxs-lookup"><span data-stu-id="46894-111">**SQL Server Books Online**</span></span>  
  
1.  [<span data-ttu-id="46894-112">Datové typy (databázový stroj)</span><span class="sxs-lookup"><span data-stu-id="46894-112">Data Types (Database Engine)</span></span>](http://go.microsoft.com/fwlink/?LinkID=107468)  
  
## <a name="in-this-section"></a><span data-ttu-id="46894-113">V tomto oddílu</span><span class="sxs-lookup"><span data-stu-id="46894-113">In This Section</span></span>  
 [<span data-ttu-id="46894-114">SqlTypes a datové sady</span><span class="sxs-lookup"><span data-stu-id="46894-114">SqlTypes and the DataSet</span></span>](../../../../../docs/framework/data/adonet/sql/sqltypes-and-the-dataset.md)  
 <span data-ttu-id="46894-115">Popisuje typ podporu pro `SqlTypes` v `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="46894-115">Describes type support for `SqlTypes` in the `DataSet`.</span></span>  
  
 [<span data-ttu-id="46894-116">Zpracování hodnot Null</span><span class="sxs-lookup"><span data-stu-id="46894-116">Handling Null Values</span></span>](../../../../../docs/framework/data/adonet/sql/handling-null-values.md)  
 <span data-ttu-id="46894-117">Ukazuje, jak pracovat s hodnotami null a s hodnotou tři logiku.</span><span class="sxs-lookup"><span data-stu-id="46894-117">Demonstrates how to work with null values and three-valued logic.</span></span>  
  
 [<span data-ttu-id="46894-118">Porovnáním různých GUID a hodnoty uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="46894-118">Comparing GUID and uniqueidentifier Values</span></span>](../../../../../docs/framework/data/adonet/sql/comparing-guid-and-uniqueidentifier-values.md)  
 <span data-ttu-id="46894-119">Ukazuje, jak pracovat s hodnotami GUID a uniqueidentifier v systému SQL Server a rozhraní .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="46894-119">Demonstrates how to work with GUID and uniqueidentifier values in SQL Server and the .NET Framework.</span></span>  
  
 [<span data-ttu-id="46894-120">Datum a čas dat</span><span class="sxs-lookup"><span data-stu-id="46894-120">Date and Time Data</span></span>](../../../../../docs/framework/data/adonet/sql/date-and-time-data.md)  
 <span data-ttu-id="46894-121">Popisuje postup použití nových typech dat Datum a čas byla zavedená v systému SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="46894-121">Describes how to use the new date and time data types introduced in SQL Server 2008.</span></span>  
  
 [<span data-ttu-id="46894-122">Velké UDT</span><span class="sxs-lookup"><span data-stu-id="46894-122">Large UDTs</span></span>](../../../../../docs/framework/data/adonet/sql/large-udts.md)  
 <span data-ttu-id="46894-123">Ukazuje, jak k načtení dat z velké hodnoty UDT byla zavedená v systému SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="46894-123">Demonstrates how to retrieve data from large value UDTs introduced in SQL Server 2008.</span></span>  
  
 [<span data-ttu-id="46894-124">Data XML v systému SQL Server</span><span class="sxs-lookup"><span data-stu-id="46894-124">XML Data in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/xml-data-in-sql-server.md)  
 <span data-ttu-id="46894-125">Popisuje, jak pracovat s daty XML načíst ze serveru SQL.</span><span class="sxs-lookup"><span data-stu-id="46894-125">Describes how to work with XML data retrieved from SQL Server.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="46894-126">Odkaz</span><span class="sxs-lookup"><span data-stu-id="46894-126">Reference</span></span>  
 <xref:System.Data.DataSet>  
 <span data-ttu-id="46894-127">Popisuje `DataSet` třídy a všechny její členy.</span><span class="sxs-lookup"><span data-stu-id="46894-127">Describes the `DataSet` class and all of its members.</span></span>  
  
 <xref:System.Data.SqlTypes>  
 <span data-ttu-id="46894-128">Popisuje `SqlTypes` obor názvů a všechny její členy.</span><span class="sxs-lookup"><span data-stu-id="46894-128">Describes the `SqlTypes` namespace and all of its members.</span></span>  
  
 <xref:System.Data.SqlDbType>  
 <span data-ttu-id="46894-129">Popisuje `SqlDbType` výčet a všechny její členy.</span><span class="sxs-lookup"><span data-stu-id="46894-129">Describes the `SqlDbType` enumeration and all of its members.</span></span>  
  
 <xref:System.Data.DbType>  
 <span data-ttu-id="46894-130">Popisuje `DbType` výčet a všechny její členy.</span><span class="sxs-lookup"><span data-stu-id="46894-130">Describes the `DbType` enumeration and all of its members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46894-131">Viz také</span><span class="sxs-lookup"><span data-stu-id="46894-131">See Also</span></span>  
 [<span data-ttu-id="46894-132">Mapování datového typu SQL Server</span><span class="sxs-lookup"><span data-stu-id="46894-132">SQL Server Data Type Mappings</span></span>](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md)  
 [<span data-ttu-id="46894-133">Konfigurace parametrů a datové typy parametrů</span><span class="sxs-lookup"><span data-stu-id="46894-133">Configuring Parameters and Parameter Data Types</span></span>](../../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)  
 [<span data-ttu-id="46894-134">Parametry s hodnotou tabulky</span><span class="sxs-lookup"><span data-stu-id="46894-134">Table-Valued Parameters</span></span>](../../../../../docs/framework/data/adonet/sql/table-valued-parameters.md)  
 [<span data-ttu-id="46894-135">Binární a velké hodnoty dat systému SQL Server</span><span class="sxs-lookup"><span data-stu-id="46894-135">SQL Server Binary and Large-Value Data</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)  
 [<span data-ttu-id="46894-136">ADO.NET spravované zprostředkovatelé a středisku pro vývojáře datové sady</span><span class="sxs-lookup"><span data-stu-id="46894-136">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
---
title: "Více operace hromadného kopírování"
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
ms.assetid: 5ad12f94-7459-4a93-a421-4160d1a90715
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 7db77dcd58e48927e8dac9bee82f7f14cdacf196
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="multiple-bulk-copy-operations"></a><span data-ttu-id="8acf6-102">Více operace hromadného kopírování</span><span class="sxs-lookup"><span data-stu-id="8acf6-102">Multiple Bulk Copy Operations</span></span>
<span data-ttu-id="8acf6-103">Můžete provést několik operace hromadného kopírování pomocí jednu instanci <xref:System.Data.SqlClient.SqlBulkCopy> třídy.</span><span class="sxs-lookup"><span data-stu-id="8acf6-103">You can perform multiple bulk copy operations using a single instance of a <xref:System.Data.SqlClient.SqlBulkCopy> class.</span></span> <span data-ttu-id="8acf6-104">Pokud se parametry operace změnit mezi kopie (například název cílové tabulky), je nutné je aktualizovat před žádné z následných volání **WriteToServer** metod, jak je ukázáno v následujícím příkladu.</span><span class="sxs-lookup"><span data-stu-id="8acf6-104">If the operation parameters change between copies (for example, the name of the destination table), you must update them prior to any subsequent calls to any of the **WriteToServer** methods, as demonstrated in the following example.</span></span> <span data-ttu-id="8acf6-105">Pokud není výslovně změnili, všechny hodnoty vlastností zůstávají stejné, stejně jako v předchozí operace hromadného kopírování pro danou instanci.</span><span class="sxs-lookup"><span data-stu-id="8acf6-105">Unless explicitly changed, all property values remain the same as they were on the previous bulk copy operation for a given instance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8acf6-106">Provádění více operace hromadného kopírování pomocí stejné instanci <xref:System.Data.SqlClient.SqlBulkCopy> obvykle je efektivnější než při použití samostatnou instanci pro každou operaci.</span><span class="sxs-lookup"><span data-stu-id="8acf6-106">Performing multiple bulk copy operations using the same instance of <xref:System.Data.SqlClient.SqlBulkCopy> is usually more efficient than using a separate instance for each operation.</span></span>  
  
 <span data-ttu-id="8acf6-107">Pokud je třeba provést několik operace hromadného kopírování používající stejný <xref:System.Data.SqlClient.SqlBulkCopy> objektu, neexistují žádná omezení toho, jestli zdroje nebo cíle informace stejné nebo jiné v jednotlivých operacích.</span><span class="sxs-lookup"><span data-stu-id="8acf6-107">If you perform several bulk copy operations using the same <xref:System.Data.SqlClient.SqlBulkCopy> object, there are no restrictions on whether source or target information is equal or different in each operation.</span></span> <span data-ttu-id="8acf6-108">Ale musíte zajistit, že informací o přidružení typu sloupce je správně nastaveno při každém zápisu serveru.</span><span class="sxs-lookup"><span data-stu-id="8acf6-108">However, you must ensure that column association information is properly set each time you write to the server.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8acf6-109">Tato ukázka se nespustí, pokud jste vytvořili pracovní tabulky, jak je popsáno v [hromadné kopírování příklad instalace](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md).</span><span class="sxs-lookup"><span data-stu-id="8acf6-109">This sample will not run unless you have created the work tables as described in [Bulk Copy Example Setup](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md).</span></span> <span data-ttu-id="8acf6-110">Tento kód je určen k předvedení syntaxe pro používání **SqlBulkCopy** pouze.</span><span class="sxs-lookup"><span data-stu-id="8acf6-110">This code is provided to demonstrate the syntax for using **SqlBulkCopy** only.</span></span> <span data-ttu-id="8acf6-111">Pokud zdrojové a cílové tabulky jsou umístěny ve stejné instanci systému SQL Server, je snadnější a rychlejší pomocí jazyka Transact-SQL `INSERT … SELECT` příkaz Kopírovat data.</span><span class="sxs-lookup"><span data-stu-id="8acf6-111">If the source and destination tables are located in the same SQL Server instance, it is easier and faster to use a Transact-SQL `INSERT … SELECT` statement to copy the data.</span></span>  
  
 [!code-csharp[DataWorks SqlBulkCopy.ColumnMappingOrdersDetails#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.ColumnMappingOrdersDetails/CS/source.cs#1)]
 [!code-vb[DataWorks SqlBulkCopy.ColumnMappingOrdersDetails#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.ColumnMappingOrdersDetails/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="8acf6-112">Viz také</span><span class="sxs-lookup"><span data-stu-id="8acf6-112">See Also</span></span>  
 [<span data-ttu-id="8acf6-113">Operace hromadného kopírování v systému SQL Server</span><span class="sxs-lookup"><span data-stu-id="8acf6-113">Bulk Copy Operations in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/bulk-copy-operations-in-sql-server.md)  
 [<span data-ttu-id="8acf6-114">ADO.NET spravované zprostředkovatelé a středisku pro vývojáře datové sady</span><span class="sxs-lookup"><span data-stu-id="8acf6-114">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
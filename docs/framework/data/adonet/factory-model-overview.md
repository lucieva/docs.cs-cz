---
title: "Přehled modelu objektu pro vytváření"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b5dc81c4-7554-44b9-b513-769bd61e2e7b
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 54d8db28fec710aba2307d826e147eb9bab13ab9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="factory-model-overview"></a><span data-ttu-id="cf636-102">Přehled modelu objektu pro vytváření</span><span class="sxs-lookup"><span data-stu-id="cf636-102">Factory Model Overview</span></span>
<span data-ttu-id="cf636-103">ADO.NET 2.0 zavedeny nové základní třídy v <xref:System.Data.Common> oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="cf636-103">ADO.NET 2.0 introduced new base classes in the <xref:System.Data.Common> namespace.</span></span> <span data-ttu-id="cf636-104">Základní třídy, je abstraktních, což znamená, že se nemůže být přímo vytvořeny instance.</span><span class="sxs-lookup"><span data-stu-id="cf636-104">The base classes are abstract, which means that they can't be directly instantiated.</span></span> <span data-ttu-id="cf636-105">Patří mezi ně <xref:System.Data.Common.DbConnection>, <xref:System.Data.Common.DbCommand>, a <xref:System.Data.Common.DbDataAdapter> a jsou sdíleny zprostředkovatele dat .NET Framework, jako například <xref:System.Data.SqlClient> a <xref:System.Data.OleDb>.</span><span class="sxs-lookup"><span data-stu-id="cf636-105">They include <xref:System.Data.Common.DbConnection>, <xref:System.Data.Common.DbCommand>, and <xref:System.Data.Common.DbDataAdapter> and are shared by the .NET Framework data providers, such as <xref:System.Data.SqlClient> and <xref:System.Data.OleDb>.</span></span> <span data-ttu-id="cf636-106">Přidání třídy base zjednodušuje přidání funkce do zprostředkovatele dat .NET Framework bez nutnosti vytvořit nové rozhraní.</span><span class="sxs-lookup"><span data-stu-id="cf636-106">The addition of base classes simplifies adding functionality to the .NET Framework data providers without having to create new interfaces.</span></span>  
  
 <span data-ttu-id="cf636-107">ADO.NET 2.0 zavedli taky abstraktní základní třídy, které umožňují vývojáři psát kód obecných datových přístup, který není závislá na konkrétní data zprostředkovatele.</span><span class="sxs-lookup"><span data-stu-id="cf636-107">ADO.NET 2.0 also introduced abstract base classes, which enable a developer to write generic data access code that does not depend on a specific data provider.</span></span>  
  
## <a name="the-factory-design-pattern"></a><span data-ttu-id="cf636-108">Vzor návrhu objektu pro vytváření</span><span class="sxs-lookup"><span data-stu-id="cf636-108">The Factory Design Pattern</span></span>  
 <span data-ttu-id="cf636-109">Programovací model pro psaní kódu nezávislé na zprostředkovatele je založen na použití vzoru návrhu s "factory", která využívá jediného rozhraní API pro přístup k databázím napříč více poskytovatelů.</span><span class="sxs-lookup"><span data-stu-id="cf636-109">The programming model for writing provider-independent code is based on the use of the "factory" design pattern, which uses a single API to access databases across multiple providers.</span></span> <span data-ttu-id="cf636-110">Tento vzor je vhodně pojmenované, jak se vyžaduje použití specializované objektu výhradně k vytvoření jiné objekty, podobně jako objekt pro vytváření reálných.</span><span class="sxs-lookup"><span data-stu-id="cf636-110">This pattern is aptly named, as it calls for the use of a specialized object solely to create other objects, much like a real-world factory.</span></span> <span data-ttu-id="cf636-111">Podrobnější popis tohoto vzoru návrhu factory najdete v tématu "[psaní kódu přístup obecná Data v technologii ASP.NET 2.0 a ADO.NET 2.0](http://go.microsoft.com/fwlink/?LinkId=55915)" a "Obecné kódování s the ADO.NET 2.0 základní třídy a objekty Factory" [http:// MSDN.microsoft.com/library/default.asp?url=/library/dnvs05/HTML/vsgenerics.asp](http://msdn.microsoft.com/library/default.asp?url=/library/dnvs05/html/vsgenerics.asp) na webu MSDN.</span><span class="sxs-lookup"><span data-stu-id="cf636-111">For a more detailed description of the factory design pattern, see "[Writing Generic Data Access Code in ASP.NET 2.0 and ADO.NET 2.0](http://go.microsoft.com/fwlink/?LinkId=55915)" and "Generic Coding with the ADO.NET 2.0 Base Classes and Factories" [http://msdn.microsoft.com/library/default.asp?url=/library/dnvs05/html/vsgenerics.asp](http://msdn.microsoft.com/library/default.asp?url=/library/dnvs05/html/vsgenerics.asp) on MSDN.</span></span>  
  
 <span data-ttu-id="cf636-112">Od verze ADO.NET 2.0 <xref:System.Data.Common.DbProviderFactories> třída poskytuje `static` (nebo `Shared` v jazyce Visual Basic) metody pro vytváření <xref:System.Data.Common.DbProviderFactory> instance.</span><span class="sxs-lookup"><span data-stu-id="cf636-112">Starting with ADO.NET 2.0, the <xref:System.Data.Common.DbProviderFactories> class provides `static` (or `Shared` in Visual Basic) methods for creating a <xref:System.Data.Common.DbProviderFactory> instance.</span></span> <span data-ttu-id="cf636-113">Instance pak vrátí objekt správné silného typu na základě informací o zprostředkovateli služeb a připojovací řetězec zadaný v době běhu.</span><span class="sxs-lookup"><span data-stu-id="cf636-113">The instance then returns a correct strongly typed object based on provider information and the connection string supplied at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf636-114">Viz také</span><span class="sxs-lookup"><span data-stu-id="cf636-114">See Also</span></span>  
 [<span data-ttu-id="cf636-115">Získání DbProviderFactory</span><span class="sxs-lookup"><span data-stu-id="cf636-115">Obtaining a DbProviderFactory</span></span>](../../../../docs/framework/data/adonet/obtaining-a-dbproviderfactory.md)  
 [<span data-ttu-id="cf636-116">Připojení DbConnection, DbCommand a dbexception –</span><span class="sxs-lookup"><span data-stu-id="cf636-116">DbConnection, DbCommand and DbException</span></span>](../../../../docs/framework/data/adonet/dbconnection-dbcommand-and-dbexception.md)  
 [<span data-ttu-id="cf636-117">Úprava dat s DbDataAdapter</span><span class="sxs-lookup"><span data-stu-id="cf636-117">Modifying Data with a DbDataAdapter</span></span>](../../../../docs/framework/data/adonet/modifying-data-with-a-dbdataadapter.md)  
 [<span data-ttu-id="cf636-118">ADO.NET spravované zprostředkovatelé a středisku pro vývojáře datové sady</span><span class="sxs-lookup"><span data-stu-id="cf636-118">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
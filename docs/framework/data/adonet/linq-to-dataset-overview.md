---
title: "LINQ na DataSet přehled"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dc20a8fb-03f6-4b68-9c2b-7f7299e3070b
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 8b853eac26f41a3537438bd1f9b0263ae06b6e77
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="linq-to-dataset-overview"></a><span data-ttu-id="9b4ef-102">LINQ na DataSet přehled</span><span class="sxs-lookup"><span data-stu-id="9b4ef-102">LINQ to DataSet Overview</span></span>
<span data-ttu-id="9b4ef-103"><xref:System.Data.DataSet> Je jedním z více často používaný součástí [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9b4ef-103">The <xref:System.Data.DataSet> is one of the more widely used components of [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)].</span></span> <span data-ttu-id="9b4ef-104">Je důležitou součástí odpojeném programování modelu, který [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] vychází z, a umožňuje explicitně ukládat data do mezipaměti z různých zdrojů.</span><span class="sxs-lookup"><span data-stu-id="9b4ef-104">It is a key element of the disconnected programming model that [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] is based on, and it enables you to explicitly cache data from different data sources.</span></span> <span data-ttu-id="9b4ef-105">Pro prezentační vrstvy <xref:System.Data.DataSet> je úzce integrovaná s grafickým uživatelským rozhraním ovládací prvky pro datovou vazbu.</span><span class="sxs-lookup"><span data-stu-id="9b4ef-105">For the presentation tier, the <xref:System.Data.DataSet> is tightly integrated with GUI controls for data-binding.</span></span> <span data-ttu-id="9b4ef-106">Pro střední vrstvě poskytuje mezipaměti, který zachovává relační tvaru dat a zahrnuje rychle jednoduchý dotaz a hierarchii navigační služby.</span><span class="sxs-lookup"><span data-stu-id="9b4ef-106">For the middle-tier, it provides a cache that preserves the relational shape of data, and includes fast simple query and hierarchy navigation services.</span></span> <span data-ttu-id="9b4ef-107">Běžné metoda používaná k snížit počet požadavků na databázi, které se má používat <xref:System.Data.DataSet> pro ukládání do mezipaměti ve střední vrstvě.</span><span class="sxs-lookup"><span data-stu-id="9b4ef-107">A common technique used to lower the number of requests on a database is to use the <xref:System.Data.DataSet> for caching in the middle-tier.</span></span> <span data-ttu-id="9b4ef-108">Zvažte například řízené daty [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] webové aplikace.</span><span class="sxs-lookup"><span data-stu-id="9b4ef-108">For example, consider a data-driven [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web application.</span></span> <span data-ttu-id="9b4ef-109">Podstatnou část dat aplikací často nemění příliš často a je společná pro relací nebo uživatele.</span><span class="sxs-lookup"><span data-stu-id="9b4ef-109">Often, a significant portion of the application data does not change frequently and is common across sessions or users.</span></span> <span data-ttu-id="9b4ef-110">Tato data je možné mít v paměti na webovém serveru, která omezuje počet požadavků v databázi a urychluje interakce uživatele.</span><span class="sxs-lookup"><span data-stu-id="9b4ef-110">This data can be kept in memory on the Web server, which reduces the number of requests against the database and speeds up the user’s interactions.</span></span> <span data-ttu-id="9b4ef-111">Další užitečné aspekt <xref:System.Data.DataSet> je, že umožňuje aplikaci tím podmnožiny dat z jedné nebo více zdroje dat do prostoru aplikace.</span><span class="sxs-lookup"><span data-stu-id="9b4ef-111">Another useful aspect of the <xref:System.Data.DataSet> is that it allows an application to bring subsets of data from one or more data source into the application space.</span></span> <span data-ttu-id="9b4ef-112">Aplikace pak můžete upravit na data v paměti, při zachování jejich relačního modelu.</span><span class="sxs-lookup"><span data-stu-id="9b4ef-112">The application can then manipulate the data in-memory, while retaining its relational shape.</span></span>  
  
 <span data-ttu-id="9b4ef-113">Bez ohledu na jeho úroveň <xref:System.Data.DataSet> má omezené možnosti dotazu.</span><span class="sxs-lookup"><span data-stu-id="9b4ef-113">Despite its prominence, the <xref:System.Data.DataSet> has limited query capabilities.</span></span> <span data-ttu-id="9b4ef-114"><xref:System.Data.DataTable.Select%2A> Metodu můžete použít pro filtrování a řazení a <xref:System.Data.DataRow.GetChildRows%2A> a <xref:System.Data.DataRow.GetParentRow%2A> metody lze použít pro navigační hierarchie.</span><span class="sxs-lookup"><span data-stu-id="9b4ef-114">The <xref:System.Data.DataTable.Select%2A> method can be used for filtering and sorting, and the <xref:System.Data.DataRow.GetChildRows%2A> and <xref:System.Data.DataRow.GetParentRow%2A> methods can be used for hierarchy navigation.</span></span> <span data-ttu-id="9b4ef-115">Pro jakýkoli složitější ale, musí vývojář napsat vlastní dotaz.</span><span class="sxs-lookup"><span data-stu-id="9b4ef-115">For anything more complex, however, the developer must write a custom query.</span></span> <span data-ttu-id="9b4ef-116">Výsledkem může být aplikace, které nízký výkon a jsou poměrně složitá.</span><span class="sxs-lookup"><span data-stu-id="9b4ef-116">This can result in applications that perform poorly and are difficult to maintain.</span></span>  
  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]<span data-ttu-id="9b4ef-117">umožňuje snadnější a rychlejší dotazu přes data uložená v mezipaměti <xref:System.Data.DataSet> objektu.</span><span class="sxs-lookup"><span data-stu-id="9b4ef-117"> makes it easier and faster to query over data cached in a <xref:System.Data.DataSet> object.</span></span> <span data-ttu-id="9b4ef-118">Tyto dotazy jsou vyjádřeny v programovacím jazyce sám sebe, nikoli jako textové literály vložených v kódu aplikace.</span><span class="sxs-lookup"><span data-stu-id="9b4ef-118">These queries are expressed in the programming language itself, rather than as string literals embedded in the application code.</span></span> <span data-ttu-id="9b4ef-119">To znamená, že vývojáři nemají další samostatné dotazovací jazyk.</span><span class="sxs-lookup"><span data-stu-id="9b4ef-119">This means that developers do not have to learn a separate query language.</span></span> <span data-ttu-id="9b4ef-120">Kromě toho [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] umožňuje [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] vývojářům zvýšit produktivitu, fungovat, protože [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] IDE poskytuje kontrolu syntaxe kompilaci, statické zadáním a podporu technologie IntelliSense pro [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9b4ef-120">Additionally, [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] enables [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] developers to work more productively, because the [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] IDE provides compile-time syntax checking, static typing, and IntelliSense support for [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)].</span></span> [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]<span data-ttu-id="9b4ef-121">Můžete také použít k dotazu přes data, která byla konsolidována z jednoho nebo více zdrojů dat.</span><span class="sxs-lookup"><span data-stu-id="9b4ef-121"> can also be used to query over data that has been consolidated from one or more data sources.</span></span> <span data-ttu-id="9b4ef-122">To umožňuje mnoho scénářů, které vyžadují flexibilitu při fungování reprezentované a zpracovat data.</span><span class="sxs-lookup"><span data-stu-id="9b4ef-122">This enables many scenarios that require flexibility in how data is represented and handled.</span></span> <span data-ttu-id="9b4ef-123">Obecné sestavy, analýzu a aplikace pro business intelligence klást tato metoda manipulaci.</span><span class="sxs-lookup"><span data-stu-id="9b4ef-123">In particular, generic reporting, analysis, and business intelligence applications require this method of manipulation.</span></span>  
  
## <a name="querying-datasets-using-linq-to-dataset"></a><span data-ttu-id="9b4ef-124">Dotazování datové sady pomocí LINQ na DataSet</span><span class="sxs-lookup"><span data-stu-id="9b4ef-124">Querying DataSets Using LINQ to DataSet</span></span>  
 <span data-ttu-id="9b4ef-125">Před zahájením dotazování <xref:System.Data.DataSet> pomocí [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)], musí naplnit <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="9b4ef-125">Before you can begin querying a <xref:System.Data.DataSet> object using [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)], you must populate the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="9b4ef-126">Načtení dat do několika způsoby <xref:System.Data.DataSet>, například pomocí <xref:System.Data.Common.DataAdapter> třídy nebo [technologie LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md).</span><span class="sxs-lookup"><span data-stu-id="9b4ef-126">There are several ways to load data into a <xref:System.Data.DataSet>, such as using the <xref:System.Data.Common.DataAdapter> class or [LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md).</span></span> <span data-ttu-id="9b4ef-127">Jakmile jsou data načtená do <xref:System.Data.DataSet> objekt, můžete začít se dotaz.</span><span class="sxs-lookup"><span data-stu-id="9b4ef-127">After the data has been loaded into a <xref:System.Data.DataSet> object, you can begin to query it.</span></span> <span data-ttu-id="9b4ef-128">Formulování dotazy s [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] je podobný používání [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] proti dalších [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]-povolené datové zdroje.</span><span class="sxs-lookup"><span data-stu-id="9b4ef-128">Formulating queries using [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] is similar to using [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] against other [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]-enabled data sources.</span></span> [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]<span data-ttu-id="9b4ef-129">v jedné tabulky je adresovat dotazy <xref:System.Data.DataSet> nebo před více než jedné tabulky pomocí <xref:System.Linq.Enumerable.Join%2A> a <xref:System.Linq.Enumerable.GroupJoin%2A> standardní operátory dotazu.</span><span class="sxs-lookup"><span data-stu-id="9b4ef-129"> queries can be performed against single tables in a <xref:System.Data.DataSet> or against more than one table by using the <xref:System.Linq.Enumerable.Join%2A> and <xref:System.Linq.Enumerable.GroupJoin%2A> standard query operators.</span></span>  
  
 [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]<span data-ttu-id="9b4ef-130">dotazy jsou podporovaná u zadali i netypová <xref:System.Data.DataSet> objekty.</span><span class="sxs-lookup"><span data-stu-id="9b4ef-130"> queries are supported against both typed and untyped <xref:System.Data.DataSet> objects.</span></span> <span data-ttu-id="9b4ef-131">Pokud schéma <xref:System.Data.DataSet> je známý v době návrhu aplikace, zadaný <xref:System.Data.DataSet> se doporučuje.</span><span class="sxs-lookup"><span data-stu-id="9b4ef-131">If the schema of the <xref:System.Data.DataSet> is known at application design time, a typed <xref:System.Data.DataSet> is recommended.</span></span> <span data-ttu-id="9b4ef-132">V zadaný <xref:System.Data.DataSet>, tabulky a řádky zadali členy pro jednotlivé sloupce, které usnadňuje dotazy jednodušší a srozumitelnější.</span><span class="sxs-lookup"><span data-stu-id="9b4ef-132">In a typed <xref:System.Data.DataSet>, the tables and rows have typed members for each of the columns, which makes queries simpler and more readable.</span></span>  
  
 <span data-ttu-id="9b4ef-133">Kromě standardní operátory dotazu implementované v System.Core.dll [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] přidá několik <xref:System.Data.DataSet>-konkrétní rozšíření, které usnadňují dotazu přes sadu <xref:System.Data.DataRow> objekty.</span><span class="sxs-lookup"><span data-stu-id="9b4ef-133">In addition to the standard query operators implemented in System.Core.dll, [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] adds several <xref:System.Data.DataSet>-specific extensions that make it easier to query over a set of <xref:System.Data.DataRow> objects.</span></span> <span data-ttu-id="9b4ef-134">Tyto <xref:System.Data.DataSet>-konkrétní rozšíření zahrnují operátory pro porovnání pořadí řádků, jakož i metody, které poskytují přístup k hodnotám sloupce <xref:System.Data.DataRow>.</span><span class="sxs-lookup"><span data-stu-id="9b4ef-134">These <xref:System.Data.DataSet>-specific extensions include operators for comparing sequences of rows, as well as methods that provide access to the column values of a <xref:System.Data.DataRow>.</span></span>  
  
## <a name="n-tier-applications-and-linq-to-dataset"></a><span data-ttu-id="9b4ef-135">Vícevrstvé aplikace a LINQ na DataSet</span><span class="sxs-lookup"><span data-stu-id="9b4ef-135">N-tier Applications and LINQ to DataSet</span></span>  
 <span data-ttu-id="9b4ef-136">Vícevrstvé datové aplikace jsou zaměřené na data aplikací, které jsou rozdělené do několika logické vrstvy (nebo úrovně).</span><span class="sxs-lookup"><span data-stu-id="9b4ef-136">N-tier data applications are data-centric applications that are separated into multiple logical layers (or tiers).</span></span> <span data-ttu-id="9b4ef-137">Typická vícevrstvé aplikace obsahuje prezentační vrstvy, střední vrstvy a datové vrstvy.</span><span class="sxs-lookup"><span data-stu-id="9b4ef-137">A typical N-tier application includes a presentation tier, a middle tier, and a data tier.</span></span> <span data-ttu-id="9b4ef-138">Rozdělení komponent aplikace do oddělených vrstev zvyšuje udržovatelnost a škálovatelnost aplikace.</span><span class="sxs-lookup"><span data-stu-id="9b4ef-138">Separating application components into separate tiers increases the maintainability and scalability of the application.</span></span> <span data-ttu-id="9b4ef-139">Další informace o vícevrstvých datových aplikací najdete v tématu [pracovat s datovými sadami ve vícevrstvých aplikacích](http://msdn.microsoft.com/library/f6ae2ee0-ea5f-4a79-8f4b-e21c115afb20).</span><span class="sxs-lookup"><span data-stu-id="9b4ef-139">For more information about N-tier data applications, see [Work with datasets in n-tier applications](http://msdn.microsoft.com/library/f6ae2ee0-ea5f-4a79-8f4b-e21c115afb20).</span></span>  
  
 <span data-ttu-id="9b4ef-140">Ve vícevrstvé aplikace <xref:System.Data.DataSet> se často používá ve střední vrstvě pro informace o mezipaměti pro webovou aplikaci.</span><span class="sxs-lookup"><span data-stu-id="9b4ef-140">In N-tier applications, the <xref:System.Data.DataSet> is often used in the middle-tier to cache information for a Web application.</span></span> <span data-ttu-id="9b4ef-141">[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] Funkcích pro dotazování se implementuje pomocí metod rozšíření a rozšiřuje stávající 2.0 ADO.NET <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="9b4ef-141">The [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] querying functionality is implemented through extension methods and extends the existing ADO.NET 2.0 <xref:System.Data.DataSet>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b4ef-142">Viz také</span><span class="sxs-lookup"><span data-stu-id="9b4ef-142">See Also</span></span>  
 [<span data-ttu-id="9b4ef-143">Dotazování datové sady</span><span class="sxs-lookup"><span data-stu-id="9b4ef-143">Querying DataSets</span></span>](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)  
 [<span data-ttu-id="9b4ef-144">LINQ (Language-Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="9b4ef-144">LINQ (Language-Integrated Query)</span></span>](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)  
 [<span data-ttu-id="9b4ef-145">Technologie LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="9b4ef-145">LINQ to SQL</span></span>](../../../../docs/framework/data/adonet/sql/linq/index.md)
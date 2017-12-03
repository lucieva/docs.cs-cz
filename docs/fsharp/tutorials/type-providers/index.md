---
title: "Zprostředkovatelé typů"
description: "Zjistěte, jak poskytovatele typu F # je komponenta, která poskytuje typy, vlastnosti a metody pro použití ve vašich aplikacích."
keywords: "Visual f #, f #, funkční programování"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 25697ef6-465e-4248-9de5-1d199d4a8b59
ms.openlocfilehash: 68462a24a9fbd1ee671d7e335f2774adf3476750
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="type-providers"></a><span data-ttu-id="32141-104">Zprostředkovatelé typů</span><span class="sxs-lookup"><span data-stu-id="32141-104">Type Providers</span></span>

> [!NOTE]
<span data-ttu-id="32141-105">Tato příručka byla zapsána z F # 3.0 a budou aktualizovány.</span><span class="sxs-lookup"><span data-stu-id="32141-105">This guide was written from F# 3.0 and will be updated.</span></span>  <span data-ttu-id="32141-106">V tématu [FSharp.Data](http://fsharp.github.io/FSharp.Data/) pro různé platformy, aktuální typ poskytovatele.</span><span class="sxs-lookup"><span data-stu-id="32141-106">See [FSharp.Data](http://fsharp.github.io/FSharp.Data/) for up-to-date, cross-platform type providers.</span></span>

<span data-ttu-id="32141-107">Poskytovatel typů jazyka F# je komponenta, která poskytuje typy, vlastnosti a metody pro váš program.</span><span class="sxs-lookup"><span data-stu-id="32141-107">An F# type provider is a component that provides types, properties, and methods for use in your program.</span></span> <span data-ttu-id="32141-108">Poskytovatelé typů jsou významnou součástí podpory informačně obsáhlého programování v jazyce F# 3.0.</span><span class="sxs-lookup"><span data-stu-id="32141-108">Type providers are a significant part of F# 3.0 support for information-rich programming.</span></span> <span data-ttu-id="32141-109">Klíčem k informačně obsáhlému programování je odstranění bariér, které překážejí v práci s rozličnými zdroji informací nalezenými na Internetu a v moderních podnikových prostředích.</span><span class="sxs-lookup"><span data-stu-id="32141-109">The key to information-rich programming is to eliminate barriers to working with diverse information sources found on the Internet and in modern enterprise environments.</span></span> <span data-ttu-id="32141-110">Jednou takovou významnou překážkou pro zahrnutí zdroje informací do programu je nutnost reprezentovat tyto informace jako typy, vlastnosti a metody pro prostředí programovacího jazyka.</span><span class="sxs-lookup"><span data-stu-id="32141-110">One significant barrier to including a source of information into a program is the need to represent that information as types, properties, and methods for use in a programming language environment.</span></span> <span data-ttu-id="32141-111">Ruční psaní těchto typů je časově velmi náročné a obtížné na správu.</span><span class="sxs-lookup"><span data-stu-id="32141-111">Writing these types manually is very time-consuming and difficult to maintain.</span></span> <span data-ttu-id="32141-112">Běžnou alternativou je použití generátoru kódu, který do projektu přidává soubory. Konvenční typy generování kódu však nelze dobře integrovat do průzkumných režimů programování podporovaných jazykem F#, protože generovaný kód musí být nahrazen vždy, když je upraven odkaz na službu.</span><span class="sxs-lookup"><span data-stu-id="32141-112">A common alternative is to use a code generator which adds files to your project; however, the conventional types of code generation do not integrate well into exploratory modes of programming supported by F# because the generated code must be replaced each time a service reference is adjusted.</span></span>

<span data-ttu-id="32141-113">Typy poskytované poskytovateli typů jazyka F# jsou obvykle založeny na externích zdrojích informací.</span><span class="sxs-lookup"><span data-stu-id="32141-113">The types provided by F# type providers are usually based on external information sources.</span></span> <span data-ttu-id="32141-114">Například poskytovatel typů jazyka F# pro SQL poskytne typy, vlastnosti a metody potřebné pro přímou práci s tabulkami libovolné databáze SQL, ke které máte přístup.</span><span class="sxs-lookup"><span data-stu-id="32141-114">For example, an F# type provider for SQL will provide the types, properties, and methods you need to work directly with the tables of any SQL database you have access to.</span></span> <span data-ttu-id="32141-115">Obdobným způsobem poskytovatel typů pro webové služby WSDL poskytne typy, vlastnosti a metody potřebné pro přímou práci s libovolnou webovou službou WSDL.</span><span class="sxs-lookup"><span data-stu-id="32141-115">Similarly, a type provider for WSDL web services will provide the types, properties, and methods you need to work directly with any WSDL web service.</span></span>

<span data-ttu-id="32141-116">Sada typů, vlastností a metod od poskytovatele typů jazyka F# může záviset na parametrech daných kódem programu.</span><span class="sxs-lookup"><span data-stu-id="32141-116">The set of types, properties, and methods provided by an F# type provider can depend on parameters given in program code.</span></span> <span data-ttu-id="32141-117">Poskytovatel typů může například poskytnout různé typy v závislosti na připojovacím řetězci nebo adrese URL služby.</span><span class="sxs-lookup"><span data-stu-id="32141-117">For example, a type provider can provide different types depending on a connection string or a service URL.</span></span> <span data-ttu-id="32141-118">Tímto způsobem je informační prostor dostupný prostřednictvím připojovacího řetězce nebo adresy URL přímo integrován s programem.</span><span class="sxs-lookup"><span data-stu-id="32141-118">In this way, the information space available by means of a connection string or URL is directly integrated into your program.</span></span> <span data-ttu-id="32141-119">Poskytovatel typů dokáže také zajistit, aby skupiny typů byly rozbaleny dle potřeby. To znamená, že jsou rozbalovány, pokud je na typy v programu skutečně odkazováno.</span><span class="sxs-lookup"><span data-stu-id="32141-119">A type provider can also ensure that groups of types are only expanded on demand; that is, they are expanded if the types are actually referenced by your program.</span></span> <span data-ttu-id="32141-120">To umožňuje přímou integraci rozsáhlých informačních prostorů přístupných na vyžádání, jako jsou například online datové trhy, způsobem využívajícím silné typy.</span><span class="sxs-lookup"><span data-stu-id="32141-120">This allows for the direct, on-demand integration of large-scale information spaces such as online data markets in a strongly typed way.</span></span>

<span data-ttu-id="32141-121">Jazyk F# obsahuje několik předdefinovaných poskytovatelů typů pro běžně používané internetové a firemní datové služby.</span><span class="sxs-lookup"><span data-stu-id="32141-121">F# contains several built-in type providers for commonly used Internet and enterprise data services.</span></span> <span data-ttu-id="32141-122">Tito poskytovatelé typů přináší jednoduchý a pravidelný přístup k relačním databázím SQL a síťově orientovaným službám OData a WSDL a podporují používání dotazů jazyka F# LINQ na tyto datové zdroje.</span><span class="sxs-lookup"><span data-stu-id="32141-122">These type providers give simple and regular access to SQL relational databases and network-based OData and WSDL services and support the use of F# LINQ queries against these data sources.</span></span>

<span data-ttu-id="32141-123">V případě potřeby lze vytvořit vlastní poskytovatele typů nebo vytvořit odkaz na poskytovatele typů vytvořené jinými programátory.</span><span class="sxs-lookup"><span data-stu-id="32141-123">Where necessary, you can create your own custom type providers, or reference type providers that have been created by others.</span></span> <span data-ttu-id="32141-124">Předpokládejme například organizaci, která má datovou službu poskytující velké a zvyšující se množství pojmenovaných datových sad, přičemž každá z nich má vlastní stabilní schéma dat.</span><span class="sxs-lookup"><span data-stu-id="32141-124">For example, assume your organization has a data service providing a large and growing number of named data sets, each with its own stable data schema.</span></span> <span data-ttu-id="32141-125">Můžete vytvořit poskytovatele typů, který schémata přečte a nabídne programátorům nejnovější dostupné datové sady se silnými typy.</span><span class="sxs-lookup"><span data-stu-id="32141-125">You may choose to create a type provider that reads the schemas and presents the latest available data sets to the programmer in a strongly typed way.</span></span>


## <a name="related-topics"></a><span data-ttu-id="32141-126">Související témata</span><span class="sxs-lookup"><span data-stu-id="32141-126">Related Topics</span></span>


|<span data-ttu-id="32141-127">Název</span><span class="sxs-lookup"><span data-stu-id="32141-127">Title</span></span>|<span data-ttu-id="32141-128">Popis</span><span class="sxs-lookup"><span data-stu-id="32141-128">Description</span></span>|
|-----|-----------|
|[<span data-ttu-id="32141-129">Návod: Přístup k databázi SQL s použitím zprostředkovatelů typů</span><span class="sxs-lookup"><span data-stu-id="32141-129">Walkthrough: Accessing a SQL Database by Using Type Providers</span></span>](accessing-a-sql-database.md)|<span data-ttu-id="32141-130">Vysvětluje způsob používání poskytovatele typů SqlDataConnection pro přístup k tabulkám a uloženým procedurám databáze SQL na základě připojovacího řetězce pro přímé připojení k databázi.</span><span class="sxs-lookup"><span data-stu-id="32141-130">Explains how to use the SqlDataConnection type provider to access the tables and stored procedures of a SQL database based on a connection string for a direct connection to a database.</span></span> <span data-ttu-id="32141-131">Přístup využívá mapování technologie LINQ to SQL.</span><span class="sxs-lookup"><span data-stu-id="32141-131">The access uses a LINQ to SQL mapping.</span></span>|
|[<span data-ttu-id="32141-132">Návod: Přístup k databázi SQL s použitím zprostředkovatelů typů a entit</span><span class="sxs-lookup"><span data-stu-id="32141-132">Walkthrough: Accessing a SQL Database by Using Type Providers and Entities</span></span>](accessing-a-sql-database-entities.md)|<span data-ttu-id="32141-133">Vysvětluje způsob používání poskytovatele typů SqlEntityConnection pro přístup k tabulkám a uloženým procedurám databáze SQL na základě připojovacího řetězce pro přímé připojení k databázi.</span><span class="sxs-lookup"><span data-stu-id="32141-133">Explains how to use the SqlEntityConnection type provider to access the tables and stored procedures of a SQL database, based on a connection string for a direct connection to a database.</span></span> <span data-ttu-id="32141-134">Přístup využívá mapování LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="32141-134">The access uses a LINQ to Entities mapping.</span></span> <span data-ttu-id="32141-135">Tato metoda funguje s libovolnou databází, uveden je však příklad systému SQL Server.</span><span class="sxs-lookup"><span data-stu-id="32141-135">This method works with any database but the example demonstrated is SQL Server.</span></span>|
|[<span data-ttu-id="32141-136">Návod: Přístup ke službě OData s použitím zprostředkovatelů typů</span><span class="sxs-lookup"><span data-stu-id="32141-136">Walkthrough: Accessing an OData Service by Using Type Providers</span></span>](accessing-an-odata-service.md)|<span data-ttu-id="32141-137">Vysvětluje způsob používání poskytovatele typů ODataService pro přístup ke službě OData způsobem podporujícím silné typy podle adresy URL služby.</span><span class="sxs-lookup"><span data-stu-id="32141-137">Explains how to use the ODataService type provider to access an OData service in a strongly typed way based on a service URL.</span></span>|
|[<span data-ttu-id="32141-138">Návod: Přístup k webové službě s použitím zprostředkovatelů typů</span><span class="sxs-lookup"><span data-stu-id="32141-138">Walkthrough: Accessing a Web Service by Using Type Providers</span></span>](accessing-a-web-service.md)|<span data-ttu-id="32141-139">Vysvětluje způsob používání poskytovatele typů WsdlService pro přístup k webové službě WSDL způsobem podporujícím silné typy podle adresy URL služby.</span><span class="sxs-lookup"><span data-stu-id="32141-139">Explains how to use the WsdlService type provider to access a WSDL web service in a strongly typed way based on a service URL.</span></span>|
|[<span data-ttu-id="32141-140">Návod: Generování Př &#35; Typy ze souboru DBML</span><span class="sxs-lookup"><span data-stu-id="32141-140">Walkthrough: Generating F&#35; Types from a DBML File</span></span>](generating-fsharp-types-from-dbml.md)|<span data-ttu-id="32141-141">Vysvětluje způsob používání poskytovatele typů DmblFile pro přístup k tabulkám a uloženým procedurám databáze SQL na základě souboru DBML, v němž je uložena specifikace schématu databáze technologie LINQ to SQL.</span><span class="sxs-lookup"><span data-stu-id="32141-141">Explains how to use the DbmlFile type provider to access the tables and stored procedures of a SQLdatabase, based on a DBML file giving a Linq to SQL database schema specification.</span></span>|
|[<span data-ttu-id="32141-142">Návod: Generování Př &#35; Typy ze souboru schématu EDMX</span><span class="sxs-lookup"><span data-stu-id="32141-142">Walkthrough: Generating F&#35; Types from an EDMX Schema File</span></span>](generating-fsharp-types-from-edmx.md)|<span data-ttu-id="32141-143">Vysvětluje způsob používání poskytovatele typů EdmxFile pro přístup k tabulkám a uloženým procedurám databáze SQL na základě souboru EDMX, v němž je uložena specifikace schématu Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="32141-143">Explains how to use the EdmxFile type provider to access the tables and stored procedures of a SQL database, based on an EDMX file giving an Entity Framework schema specification.</span></span>|
|[<span data-ttu-id="32141-144">Kurz: Vytvoření zprostředkovatele typů</span><span class="sxs-lookup"><span data-stu-id="32141-144">Tutorial: Creating a Type Provider</span></span>](creating-a-type-provider.md)|<span data-ttu-id="32141-145">Poskytuje informace o psaní vlastních poskytovatelů typů.</span><span class="sxs-lookup"><span data-stu-id="32141-145">Provides information on writing your own custom type providers.</span></span>|
|[<span data-ttu-id="32141-146">Zabezpečení zprostředkovatele typů</span><span class="sxs-lookup"><span data-stu-id="32141-146">Type Provider Security</span></span>](type-provider-security.md)|<span data-ttu-id="32141-147">Poskytuje informace o zásadách bezpečnosti při vývoji poskytovatelů typů.</span><span class="sxs-lookup"><span data-stu-id="32141-147">Provides information about security considerations when developing type providers.</span></span>|
|[<span data-ttu-id="32141-148">Řešení potíží se zprostředkovateli typu</span><span class="sxs-lookup"><span data-stu-id="32141-148">Troubleshooting Type Providers</span></span>](troubleshooting-type-providers.md)|<span data-ttu-id="32141-149">Poskytuje informace o běžných problémech, které mohou vzniknout při práci s poskytovateli typů, a zahrnuje návrhy řešení.</span><span class="sxs-lookup"><span data-stu-id="32141-149">Provides information about common problems that can arise when working with type providers and includes suggestions for solutions.</span></span>|

## <a name="see-also"></a><span data-ttu-id="32141-150">Viz také</span><span class="sxs-lookup"><span data-stu-id="32141-150">See Also</span></span>
[<span data-ttu-id="32141-151">Referenční dokumentace jazyka F #</span><span class="sxs-lookup"><span data-stu-id="32141-151">F# Language Reference</span></span>](../../language-reference/index.md)

[<span data-ttu-id="32141-152">Visual F #</span><span class="sxs-lookup"><span data-stu-id="32141-152">Visual F#</span></span>](../../index.md)
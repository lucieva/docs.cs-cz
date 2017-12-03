---
title: LINQ to Entities
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 641f9b68-9046-47a1-abb0-1c8eaeda0e2d
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 685651f4291a11b857da82a63068e4bd2333275c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="linq-to-entities"></a><span data-ttu-id="69b3b-102">LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="69b3b-102">LINQ to Entities</span></span>
<span data-ttu-id="69b3b-103">Technologie LINQ to Entities podporuje Language-Integrated Query (LINQ), která umožňuje vývojářům psát dotazy pro koncepční model Entity Framework pomocí jazyka Visual Basic a Visual C#.</span><span class="sxs-lookup"><span data-stu-id="69b3b-103">LINQ to Entities provides Language-Integrated Query (LINQ) support that enables developers to write queries against the Entity Framework conceptual model using Visual Basic or Visual C#.</span></span> <span data-ttu-id="69b3b-104">Dotazy na Entity Framework jsou reprezentované pomocí příkazu stromu dotazů, které spustit proti do kontextu objektu.</span><span class="sxs-lookup"><span data-stu-id="69b3b-104">Queries against the Entity Framework are represented by command tree queries, which execute against the object context.</span></span> <span data-ttu-id="69b3b-105">Technologie LINQ to Entities převede Language-Integrated dotazy (LINQ) dotazy pro příkaz stromu dotazy, provádí dotazy na Entity Framework a vrátí objekty, které lze použít k rozhraní Entity Framework a LINQ.</span><span class="sxs-lookup"><span data-stu-id="69b3b-105">LINQ to Entities converts Language-Integrated Queries (LINQ) queries to command tree queries, executes the queries against the Entity Framework, and returns objects that can be used by both the Entity Framework and LINQ.</span></span> <span data-ttu-id="69b3b-106">Toto je proces pro vytvoření a provedení dotazu LINQ to Entities:</span><span class="sxs-lookup"><span data-stu-id="69b3b-106">The following is the process for creating and executing a LINQ to Entities query:</span></span>  
  
1.  <span data-ttu-id="69b3b-107">Vytvořit <xref:System.Data.Objects.ObjectQuery%601> instanci z <xref:System.Data.Objects.ObjectContext>.</span><span class="sxs-lookup"><span data-stu-id="69b3b-107">Construct an <xref:System.Data.Objects.ObjectQuery%601> instance from <xref:System.Data.Objects.ObjectContext>.</span></span>  
  
2.  <span data-ttu-id="69b3b-108">Napište dotazu LINQ to Entities v C# nebo Visual Basic pomocí <xref:System.Data.Objects.ObjectQuery%601> instance.</span><span class="sxs-lookup"><span data-stu-id="69b3b-108">Compose a LINQ to Entities query in C# or Visual Basic by using the <xref:System.Data.Objects.ObjectQuery%601> instance.</span></span>  
  
3.  <span data-ttu-id="69b3b-109">LINQ standardní operátory dotazu a výrazy převeďte na strom příkazů.</span><span class="sxs-lookup"><span data-stu-id="69b3b-109">Convert LINQ standard query operators and expressions to command trees.</span></span>  
  
4.  <span data-ttu-id="69b3b-110">Spuštění dotazu a v příkazu stromu reprezentace na zdroji dat.</span><span class="sxs-lookup"><span data-stu-id="69b3b-110">Execute the query, in command tree representation, against the data source.</span></span> <span data-ttu-id="69b3b-111">Jakékoli výjimky vydané ve zdroji dat během provádění se předávají přímo až klienta.</span><span class="sxs-lookup"><span data-stu-id="69b3b-111">Any exceptions thrown on the data source during execution are passed directly up to the client.</span></span>  
  
5.  <span data-ttu-id="69b3b-112">Vrátí výsledky dotazu zpět do klienta.</span><span class="sxs-lookup"><span data-stu-id="69b3b-112">Return query results back to the client.</span></span>  
  
## <a name="constructing-an-objectquery-instance"></a><span data-ttu-id="69b3b-113">Vytváření instanci ObjectQuery</span><span class="sxs-lookup"><span data-stu-id="69b3b-113">Constructing an ObjectQuery Instance</span></span>  
 <span data-ttu-id="69b3b-114"><xref:System.Data.Objects.ObjectQuery%601> Obecná třída reprezentuje dotaz, který vrátí kolekce nula nebo více zadaných entit.</span><span class="sxs-lookup"><span data-stu-id="69b3b-114">The <xref:System.Data.Objects.ObjectQuery%601> generic class represents a query that returns a collection of zero or more typed entities.</span></span> <span data-ttu-id="69b3b-115">Dotaz na objekt se obvykle vytvářejí na základě existující objekt kontextu, místo ručně vytvářen a vždy patří do tohoto objektu kontextu.</span><span class="sxs-lookup"><span data-stu-id="69b3b-115">An object query is typically constructed from an existing object context, instead of being manually constructed, and always belongs to that object context.</span></span> <span data-ttu-id="69b3b-116">Tento kontext poskytuje připojení a informace o metadatech, které je potřeba vytvořit a provést dotaz.</span><span class="sxs-lookup"><span data-stu-id="69b3b-116">This context provides the connection and metadata information that is required to compose and execute the query.</span></span> <span data-ttu-id="69b3b-117"><xref:System.Data.Objects.ObjectQuery%601> – Obecná třída implementuje <xref:System.Linq.IQueryable%601> obecné rozhraní, jejichž metody Tvůrce povolit dotazů LINQ má být sestaven postupně.</span><span class="sxs-lookup"><span data-stu-id="69b3b-117">The <xref:System.Data.Objects.ObjectQuery%601> generic class implements the <xref:System.Linq.IQueryable%601> generic interface, whose builder methods enable LINQ queries to be incrementally built.</span></span> <span data-ttu-id="69b3b-118">Můžete také nechat kompilátoru odvození typu entit s použitím jazyka C# `var` – klíčové slovo (`Dim` v jazyce Visual Basic, s odvození místního typu povoleno).</span><span class="sxs-lookup"><span data-stu-id="69b3b-118">You can also let the compiler infer the type of entities by using the C# `var` keyword (`Dim` in Visual Basic, with local type inference enabled).</span></span>  
  
## <a name="composing-the-queries"></a><span data-ttu-id="69b3b-119">Skládání dotazy</span><span class="sxs-lookup"><span data-stu-id="69b3b-119">Composing the Queries</span></span>  
 <span data-ttu-id="69b3b-120">Instance <xref:System.Data.Objects.ObjectQuery%601> – obecná třída, která implementuje obecná <xref:System.Linq.IQueryable%601> rozhraní, sloužit jako zdroj dat pro LINQ na dotazy entity.</span><span class="sxs-lookup"><span data-stu-id="69b3b-120">Instances of the <xref:System.Data.Objects.ObjectQuery%601> generic class, which implements the generic <xref:System.Linq.IQueryable%601> interface, serve as the data source for LINQ to Entities queries.</span></span> <span data-ttu-id="69b3b-121">V dotazu je zadat přesně informace, které chcete načíst z datového zdroje.</span><span class="sxs-lookup"><span data-stu-id="69b3b-121">In a query, you specify exactly the information that you want to retrieve from the data source.</span></span> <span data-ttu-id="69b3b-122">Dotaz můžete také určit, jak tyto informace by měl být seřazeny, seskupené a ve tvaru před vrácením.</span><span class="sxs-lookup"><span data-stu-id="69b3b-122">A query can also specify how that information should be sorted, grouped, and shaped before it is returned.</span></span> <span data-ttu-id="69b3b-123">Dotaz je v technologii LINQ, uložené v proměnné.</span><span class="sxs-lookup"><span data-stu-id="69b3b-123">In LINQ, a query is stored in a variable.</span></span> <span data-ttu-id="69b3b-124">Tato proměnná dotazu neprovede žádnou akci a vrátí žádná data; ukládá jenom informace o dotazu.</span><span class="sxs-lookup"><span data-stu-id="69b3b-124">This query variable takes no action and returns no data; it only stores the query information.</span></span> <span data-ttu-id="69b3b-125">Po vytvoření dotazu je třeba spustit tento dotaz pro načtení žádná data.</span><span class="sxs-lookup"><span data-stu-id="69b3b-125">After you create a query you must execute that query to retrieve any data.</span></span>  
  
 <span data-ttu-id="69b3b-126">Technologie LINQ to Entities dotazy můžete sestavit v dva různé syntaxe: výraz syntaxe využívající dotazy a syntaxe dotazu na základě metod.</span><span class="sxs-lookup"><span data-stu-id="69b3b-126">LINQ to Entities queries can be composed in two different syntaxes: query expression syntax and method-based query syntax.</span></span> <span data-ttu-id="69b3b-127">Syntaxe výrazu dotazu a syntaxe dotazu na základě metod jsou nové v C# 3.0 a 9.0 Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="69b3b-127">Query expression syntax and method-based query syntax are new in C# 3.0 and Visual Basic 9.0.</span></span>  
  
 <span data-ttu-id="69b3b-128">Další informace najdete v tématu [dotazy v technologii LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md).</span><span class="sxs-lookup"><span data-stu-id="69b3b-128">For more information, see [Queries in LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md).</span></span>  
  
## <a name="query-conversion"></a><span data-ttu-id="69b3b-129">Převod dotazů</span><span class="sxs-lookup"><span data-stu-id="69b3b-129">Query Conversion</span></span>  
 <span data-ttu-id="69b3b-130">K provedení dotazu LINQ to Entities proti rozhraní Entity Framework, musí dotaz LINQ převést na strom znázornění příkaz, může být spuštěn proti rozhraní Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="69b3b-130">To execute a LINQ to Entities query against the Entity Framework, the LINQ query must be converted to a command tree representation that can be executed against the Entity Framework.</span></span>  
  
 <span data-ttu-id="69b3b-131">Technologie LINQ to Entities dotazy se skládají z LINQ standardní operátory dotazu (například <xref:System.Linq.Queryable.Select%2A>, <xref:System.Linq.Queryable.Where%2A>, a <xref:System.Linq.Queryable.GroupBy%2A>) a výrazy (x > 10, Contact.LastName a tak dále).</span><span class="sxs-lookup"><span data-stu-id="69b3b-131">LINQ to Entities queries are comprised of LINQ standard query operators (such as <xref:System.Linq.Queryable.Select%2A>, <xref:System.Linq.Queryable.Where%2A>, and <xref:System.Linq.Queryable.GroupBy%2A>) and expressions (x > 10, Contact.LastName, and so on).</span></span> <span data-ttu-id="69b3b-132">LINQ operátory nejsou definované třídou, ale spíš jsou metody pro třídu.</span><span class="sxs-lookup"><span data-stu-id="69b3b-132">LINQ operators are not defined by a class, but rather are methods on a class.</span></span> <span data-ttu-id="69b3b-133">V technologii LINQ, může obsahovat výrazy nic povolenou typů v rámci <xref:System.Linq.Expressions> obor názvů a rozšíření, všechno, co může být reprezentován ve funkci lambda.</span><span class="sxs-lookup"><span data-stu-id="69b3b-133">In LINQ, expressions can contain anything allowed by types within the <xref:System.Linq.Expressions> namespace and, by extension, anything that can be represented in a lambda function.</span></span> <span data-ttu-id="69b3b-134">Toto je nadmnožinou výrazy, které jsou povoleny rozhraní Entity Framework, které jsou podle definice omezen na operace povolené v databázi a nepodporuje <xref:System.Data.Objects.ObjectQuery%601>.</span><span class="sxs-lookup"><span data-stu-id="69b3b-134">This is a superset of the expressions that are allowed by the Entity Framework, which are by definition restricted to operations allowed on the database, and supported by <xref:System.Data.Objects.ObjectQuery%601>.</span></span>  
  
 <span data-ttu-id="69b3b-135">V rozhraní Entity Framework operátory a výrazy jsou reprezentované pomocí jednoho typu hierarchie, které pak jsou umístěny ve stromu příkazů.</span><span class="sxs-lookup"><span data-stu-id="69b3b-135">In the Entity Framework, both operators and expressions are represented by a single type hierarchy, which are then placed in a command tree.</span></span> <span data-ttu-id="69b3b-136">Stromu příkazů se používá rozhraní k provedení dotazu.</span><span class="sxs-lookup"><span data-stu-id="69b3b-136">The command tree is used by the Entity Framework to execute the query.</span></span> <span data-ttu-id="69b3b-137">Pokud dotaz LINQ nemůže být vyjádřena jako strom příkazů, bude vyvolána výjimka, pokud dotaz, který je převáděn.</span><span class="sxs-lookup"><span data-stu-id="69b3b-137">If the LINQ query cannot be expressed as a command tree, an exception will be thrown when the query is being converted.</span></span> <span data-ttu-id="69b3b-138">Převod LINQ na dotazy na entity zahrnuje dvě dílčí převody: převod standardní operátory dotazu a převod výrazy.</span><span class="sxs-lookup"><span data-stu-id="69b3b-138">The conversion of LINQ to Entities queries involves two sub-conversions: the conversion of the standard query operators, and the conversion of the expressions.</span></span>  
  
 <span data-ttu-id="69b3b-139">Existuje několik LINQ standardních operátorů dotazu, které nemají platný posunutí v technologii LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="69b3b-139">There are a number of LINQ standard query operators that do not have a valid translation in LINQ to Entities.</span></span> <span data-ttu-id="69b3b-140">Pokusy o použití těchto operátorů způsobí výjimku v době překlad dotazů.</span><span class="sxs-lookup"><span data-stu-id="69b3b-140">Attempts to use these operators will result in an exception at query translation time.</span></span> <span data-ttu-id="69b3b-141">Seznam podporovaných technologie LINQ to Entities operátory najdete v tématu [podporované a nepodporované metody LINQ (LINQ to Entities)](../../../../../../docs/framework/data/adonet/ef/language-reference/supported-and-unsupported-linq-methods-linq-to-entities.md).</span><span class="sxs-lookup"><span data-stu-id="69b3b-141">For a list of supported LINQ to Entities operators, see [Supported and Unsupported LINQ Methods (LINQ to Entities)](../../../../../../docs/framework/data/adonet/ef/language-reference/supported-and-unsupported-linq-methods-linq-to-entities.md).</span></span>  
  
 <span data-ttu-id="69b3b-142">Další informace o používání standardní operátory dotazu v technologii LINQ to Entities najdete v tématu [standardní operátory dotazu v technologii LINQ to Entities dotazy](../../../../../../docs/framework/data/adonet/ef/language-reference/standard-query-operators-in-linq-to-entities-queries.md).</span><span class="sxs-lookup"><span data-stu-id="69b3b-142">For more information about using the standard query operators in LINQ to Entities, see [Standard Query Operators in LINQ to Entities Queries](../../../../../../docs/framework/data/adonet/ef/language-reference/standard-query-operators-in-linq-to-entities-queries.md).</span></span>  
  
 <span data-ttu-id="69b3b-143">Obecně platí na serveru, se vyhodnotí výrazy v technologii LINQ to Entities tak chování výraz nesmí lze očekávat, postupujte podle sémantiku CLR.</span><span class="sxs-lookup"><span data-stu-id="69b3b-143">In general, expressions in LINQ to Entities are evaluated on the server, so the behavior of the expression should not be expected to follow CLR semantics.</span></span> <span data-ttu-id="69b3b-144">Další informace najdete v tématu [výrazy v technologii LINQ to Entities dotazy](../../../../../../docs/framework/data/adonet/ef/language-reference/expressions-in-linq-to-entities-queries.md).</span><span class="sxs-lookup"><span data-stu-id="69b3b-144">For more information, see [Expressions in LINQ to Entities Queries](../../../../../../docs/framework/data/adonet/ef/language-reference/expressions-in-linq-to-entities-queries.md).</span></span>  
  
 <span data-ttu-id="69b3b-145">Informace o mapování volání metod CLR jsou kanonické funkce ve zdroji dat najdete v tématu [CLR metodu pro mapování kanonické funkce](../../../../../../docs/framework/data/adonet/ef/language-reference/clr-method-to-canonical-function-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="69b3b-145">For information about how CLR method calls are mapped to canonical functions in the data source, see [CLR Method to Canonical Function Mapping](../../../../../../docs/framework/data/adonet/ef/language-reference/clr-method-to-canonical-function-mapping.md).</span></span>  
  
 <span data-ttu-id="69b3b-146">Informace o tom, jak volat kanonický, databáze a vlastní funkce uvnitř [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] dotazy, najdete v části [volání funkce v technologii LINQ to Entities dotazy](../../../../../../docs/framework/data/adonet/ef/language-reference/calling-functions-in-linq-to-entities-queries.md).</span><span class="sxs-lookup"><span data-stu-id="69b3b-146">For information about how to call canonical, database, and custom functions from within [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] queries, see [Calling Functions in LINQ to Entities Queries](../../../../../../docs/framework/data/adonet/ef/language-reference/calling-functions-in-linq-to-entities-queries.md).</span></span>  
  
## <a name="query-execution"></a><span data-ttu-id="69b3b-147">Provádění dotazů</span><span class="sxs-lookup"><span data-stu-id="69b3b-147">Query Execution</span></span>  
 <span data-ttu-id="69b3b-148">Po vytvoření dotaz LINQ uživatelem jsou převedeny na znázornění, který je kompatibilní s rozhraní Entity Framework (ve formě stromy příkazů), které se pak spustí na zdroji dat.</span><span class="sxs-lookup"><span data-stu-id="69b3b-148">After the LINQ query is created by the user, it is converted to a representation that is compatible with the Entity Framework (in the form of command trees), which is then executed against the data source.</span></span> <span data-ttu-id="69b3b-149">Během provádění dotazu se vyhodnocují všechny výrazy dotazů (nebo součásti dotazu) v klientovi nebo na serveru.</span><span class="sxs-lookup"><span data-stu-id="69b3b-149">At query execution time, all query expressions (or components of the query) are evaluated on the client or on the server.</span></span> <span data-ttu-id="69b3b-150">To zahrnuje výrazy, které se používají ve výsledku materialization nebo entity projekce.</span><span class="sxs-lookup"><span data-stu-id="69b3b-150">This includes expressions that are used in result materialization or entity projections.</span></span> <span data-ttu-id="69b3b-151">Další informace najdete v tématu [provádění dotazu](../../../../../../docs/framework/data/adonet/ef/language-reference/query-execution.md).</span><span class="sxs-lookup"><span data-stu-id="69b3b-151">For more information, see [Query Execution](../../../../../../docs/framework/data/adonet/ef/language-reference/query-execution.md).</span></span> <span data-ttu-id="69b3b-152">Informace o tom, jak zvýšit výkon, kompilování dotazu jednou a potom ho spustíte několikrát s odlišnými parametry, najdete v článku [zkompilovat dotazy (LINQ to Entities)](../../../../../../docs/framework/data/adonet/ef/language-reference/compiled-queries-linq-to-entities.md).</span><span class="sxs-lookup"><span data-stu-id="69b3b-152">For information on how to improve performance by compiling a query once and then executing it several times with different parameters, see [Compiled Queries  (LINQ to Entities)](../../../../../../docs/framework/data/adonet/ef/language-reference/compiled-queries-linq-to-entities.md).</span></span>  
  
## <a name="materialization"></a><span data-ttu-id="69b3b-153">Vlastnost materialization</span><span class="sxs-lookup"><span data-stu-id="69b3b-153">Materialization</span></span>  
 <span data-ttu-id="69b3b-154">Vlastnost materialization je proces vrácení výsledků dotazu zpět do klienta jako typy CLR.</span><span class="sxs-lookup"><span data-stu-id="69b3b-154">Materialization is the process of returning query results back to the client as CLR types.</span></span> <span data-ttu-id="69b3b-155">V technologii LINQ to Entities jsou záznamy dat výsledky dotazu nikdy nevrátilo; je vždy základní typ CLR, definované uživatelem, nebo pomocí rozhraní Entity Framework nebo generované kompilátorem (anonymní typy).</span><span class="sxs-lookup"><span data-stu-id="69b3b-155">In LINQ to Entities, query results data records are never returned; there is always a backing CLR type, defined by the user or by the Entity Framework, or generated by the compiler (anonymous types).</span></span> <span data-ttu-id="69b3b-156">Všechny materialization objektu je prováděno pomocí rozhraní Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="69b3b-156">All object materialization is performed by the Entity Framework.</span></span> <span data-ttu-id="69b3b-157">Výjimky vyvolání během objekt materialization způsobí, že všechny chyby, které jsou výsledkem nebylo možné mezi rozhraní Entity Framework a modulu CLR.</span><span class="sxs-lookup"><span data-stu-id="69b3b-157">Any errors that result from an inability to map between the Entity Framework and the CLR will cause exceptions to be thrown during object materialization.</span></span>  
  
 <span data-ttu-id="69b3b-158">Výsledky dotazu jsou obvykle vrátil jako jeden z následujících akcí:</span><span class="sxs-lookup"><span data-stu-id="69b3b-158">Query results are usually returned as one of the following:</span></span>  
  
-   <span data-ttu-id="69b3b-159">Kolekce nula nebo více objektů zadané entity nebo projekci komplexních typů definovanou v konceptuálním modelu.</span><span class="sxs-lookup"><span data-stu-id="69b3b-159">A collection of zero or more typed entity objects or a projection of complex types defined in the conceptual model.</span></span>  
  
-   <span data-ttu-id="69b3b-160">Typy CLR, které jsou podporovány [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="69b3b-160">CLR types that are supported by the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span></span>  
  
-   <span data-ttu-id="69b3b-161">Vložené kolekce.</span><span class="sxs-lookup"><span data-stu-id="69b3b-161">Inline collections.</span></span>  
  
-   <span data-ttu-id="69b3b-162">Anonymní typy.</span><span class="sxs-lookup"><span data-stu-id="69b3b-162">Anonymous types.</span></span>  
  
 <span data-ttu-id="69b3b-163">Další informace najdete v tématu [výsledky dotazu](../../../../../../docs/framework/data/adonet/ef/language-reference/query-results.md).</span><span class="sxs-lookup"><span data-stu-id="69b3b-163">For more information, see [Query Results](../../../../../../docs/framework/data/adonet/ef/language-reference/query-results.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="69b3b-164">V tomto oddílu</span><span class="sxs-lookup"><span data-stu-id="69b3b-164">In This Section</span></span>  
 [<span data-ttu-id="69b3b-165">Dotazy v technologii LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="69b3b-165">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)  
  
 [<span data-ttu-id="69b3b-166">Výrazy v technologii LINQ to Entities dotazy</span><span class="sxs-lookup"><span data-stu-id="69b3b-166">Expressions in LINQ to Entities Queries</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/expressions-in-linq-to-entities-queries.md)  
  
 [<span data-ttu-id="69b3b-167">Volání funkcí v technologii LINQ to Entities dotazy</span><span class="sxs-lookup"><span data-stu-id="69b3b-167">Calling Functions in LINQ to Entities Queries</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/calling-functions-in-linq-to-entities-queries.md)  
  
 [<span data-ttu-id="69b3b-168">Kompilované dotazy (LINQ to Entities)</span><span class="sxs-lookup"><span data-stu-id="69b3b-168">Compiled Queries  (LINQ to Entities)</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/compiled-queries-linq-to-entities.md)  
  
 [<span data-ttu-id="69b3b-169">Spuštění dotazu</span><span class="sxs-lookup"><span data-stu-id="69b3b-169">Query Execution</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/query-execution.md)  
  
 [<span data-ttu-id="69b3b-170">Výsledky dotazu</span><span class="sxs-lookup"><span data-stu-id="69b3b-170">Query Results</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/query-results.md)  
  
 [<span data-ttu-id="69b3b-171">Standardní operátory dotazu v technologii LINQ to Entities dotazy</span><span class="sxs-lookup"><span data-stu-id="69b3b-171">Standard Query Operators in LINQ to Entities Queries</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/standard-query-operators-in-linq-to-entities-queries.md)  
  
 [<span data-ttu-id="69b3b-172">Metoda CLR pro mapování kanonické funkce</span><span class="sxs-lookup"><span data-stu-id="69b3b-172">CLR Method to Canonical Function Mapping</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/clr-method-to-canonical-function-mapping.md)  
  
 [<span data-ttu-id="69b3b-173">Podporované a nepodporované LINQ metody (LINQ to Entities)</span><span class="sxs-lookup"><span data-stu-id="69b3b-173">Supported and Unsupported LINQ Methods (LINQ to Entities)</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/supported-and-unsupported-linq-methods-linq-to-entities.md)  
  
 [<span data-ttu-id="69b3b-174">Známé problémy a aspekty v technologii LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="69b3b-174">Known Issues and Considerations in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/known-issues-and-considerations-in-linq-to-entities.md)  
  
## <a name="see-also"></a><span data-ttu-id="69b3b-175">Viz také</span><span class="sxs-lookup"><span data-stu-id="69b3b-175">See Also</span></span>  
 [<span data-ttu-id="69b3b-176">Známé problémy a aspekty v technologii LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="69b3b-176">Known Issues and Considerations in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/known-issues-and-considerations-in-linq-to-entities.md)  
 [<span data-ttu-id="69b3b-177">LINQ (Language-Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="69b3b-177">LINQ (Language-Integrated Query)</span></span>](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)  
 [<span data-ttu-id="69b3b-178">LINQ a ADO.NET</span><span class="sxs-lookup"><span data-stu-id="69b3b-178">LINQ and ADO.NET</span></span>](../../../../../../docs/framework/data/adonet/linq-and-ado-net.md)  
 [<span data-ttu-id="69b3b-179">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="69b3b-179">ADO.NET Entity Framework</span></span>](../../../../../../docs/framework/data/adonet/ef/index.md)
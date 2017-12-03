---
title: "Syntaxe využívající dotazy a syntaxe využívající metody v jazyce LINQ (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- LINQ [C#], query syntax vs. method syntax
- queries [LINQ in C#], syntax comparisons
ms.assetid: eedd6dd9-fec2-428c-9581-5b8783810ded
caps.latest.revision: "30"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 0127ee0815c4ba6a697456fe45bd373bcf9ba4e4
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/18/2017
---
# <a name="query-syntax-and-method-syntax-in-linq-c"></a><span data-ttu-id="75a85-102">Syntaxe využívající dotazy a syntaxe využívající metody v jazyce LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="75a85-102">Query Syntax and Method Syntax in LINQ (C#)</span></span>
<span data-ttu-id="75a85-103">Většina dotazů v úvodní integrované Query Language ([!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]) dokumentace jsou zapsány pomocí syntaxe deklarativní dotazu LINQ.</span><span class="sxs-lookup"><span data-stu-id="75a85-103">Most queries in the introductory Language Integrated Query ([!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]) documentation are written by using the LINQ declarative query syntax.</span></span> <span data-ttu-id="75a85-104">Syntaxe dotazu je však přeložit do volání metod pro rozhraní .NET common language runtime (CLR), při kompilaci kódu.</span><span class="sxs-lookup"><span data-stu-id="75a85-104">However, the query syntax must be translated into method calls for the .NET common language runtime (CLR) when the code is compiled.</span></span> <span data-ttu-id="75a85-105">Tato metoda volání vyvolají standardní operátory dotazu, které mají názvy jako `Where`, `Select`, `GroupBy`, `Join`, `Max`, a `Average`.</span><span class="sxs-lookup"><span data-stu-id="75a85-105">These method calls invoke the standard query operators, which have names such as `Where`, `Select`, `GroupBy`, `Join`, `Max`, and `Average`.</span></span> <span data-ttu-id="75a85-106">Můžete je volat přímo pomocí syntaxe využívající metody místo syntaxe dotazu.</span><span class="sxs-lookup"><span data-stu-id="75a85-106">You can call them directly by using method syntax instead of query syntax.</span></span>  
  
 <span data-ttu-id="75a85-107">Syntaxe dotazu a syntaxe využívající metody jsou sémanticky identické, ale Spousta lidí najít syntaxe dotazů jednodušší a snadněji číst.</span><span class="sxs-lookup"><span data-stu-id="75a85-107">Query syntax and method syntax are semantically identical, but many people find query syntax simpler and easier to read.</span></span> <span data-ttu-id="75a85-108">Některé dotazy musí být vyjádřena jako volání metody.</span><span class="sxs-lookup"><span data-stu-id="75a85-108">Some queries must be expressed as method calls.</span></span> <span data-ttu-id="75a85-109">Například musíte použít volání metody vyjádřit dotaz, který načte počet elementů, které splňují zadanou podmínku.</span><span class="sxs-lookup"><span data-stu-id="75a85-109">For example, you must use a method call to express a query that retrieves the number of elements that match a specified condition.</span></span> <span data-ttu-id="75a85-110">Volání metody musíte použít také pro dotaz, který načte elementu, který má maximální hodnota ve zdrojové sekvence.</span><span class="sxs-lookup"><span data-stu-id="75a85-110">You also must use a method call for a query that retrieves the element that has the maximum value in a source sequence.</span></span> <span data-ttu-id="75a85-111">Referenční dokumentaci k nástroji standardní operátory dotazu v <xref:System.Linq> obor názvů se obvykle používá metoda syntaxe.</span><span class="sxs-lookup"><span data-stu-id="75a85-111">The reference documentation for the standard query operators in the <xref:System.Linq> namespace generally uses method syntax.</span></span> <span data-ttu-id="75a85-112">Proto i v případě Začínáme zápis [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] dotazy, je vhodné se seznámit s použití syntaxe využívající metody v dotazech a ve výrazech dotazů sami.</span><span class="sxs-lookup"><span data-stu-id="75a85-112">Therefore, even when getting started writing [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries, it is useful to be familiar with how to use method syntax in queries and in query expressions themselves.</span></span>  
  
## <a name="standard-query-operator-extension-methods"></a><span data-ttu-id="75a85-113">Metody rozšíření standardních operátorů dotazů</span><span class="sxs-lookup"><span data-stu-id="75a85-113">Standard Query Operator Extension Methods</span></span>  
 <span data-ttu-id="75a85-114">Následující příklad ukazuje jednoduchý *dotaz výrazu* a sémanticky ekvivalentní dotaz zapisují jako *dotaz založený na metoda*.</span><span class="sxs-lookup"><span data-stu-id="75a85-114">The following example shows a simple *query expression* and the semantically equivalent query written as a *method-based query*.</span></span>  
  
 [!code-csharp[csLINQGettingStarted#22](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/query-syntax-and-method-syntax-in-linq_1.cs)]  
  
 <span data-ttu-id="75a85-115">Výstup z uvedených dvou příkladech se shoduje.</span><span class="sxs-lookup"><span data-stu-id="75a85-115">The output from the two examples is identical.</span></span> <span data-ttu-id="75a85-116">Uvidíte, že typ proměnné v dotazu je stejná v obou forms: <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="75a85-116">You can see that the type of the query variable is the same in both forms: <xref:System.Collections.Generic.IEnumerable%601>.</span></span>  
  
 <span data-ttu-id="75a85-117">Zjistit dotaz na základě metod Podívejme se na jeho přesněji.</span><span class="sxs-lookup"><span data-stu-id="75a85-117">To understand the method-based query, let's examine it more closely.</span></span> <span data-ttu-id="75a85-118">Na pravé straně výrazu, Všimněte si, že `where` klauzule teď vyjádřený jako metodu instance na `numbers` má typ objektu, který jako vám bude odvolat `IEnumerable<int>`.</span><span class="sxs-lookup"><span data-stu-id="75a85-118">On the right side of the expression, notice that the `where` clause is now expressed as an instance method on the `numbers` object, which as you will recall has a type of `IEnumerable<int>`.</span></span> <span data-ttu-id="75a85-119">Pokud jste se seznámili s Obecná <xref:System.Collections.Generic.IEnumerable%601> rozhraní, víte, že nemá `Where` metoda.</span><span class="sxs-lookup"><span data-stu-id="75a85-119">If you are familiar with the generic <xref:System.Collections.Generic.IEnumerable%601> interface, you know that it does not have a `Where` method.</span></span> <span data-ttu-id="75a85-120">Ale pokud vyvolání seznamu dokončení IntelliSense v prostředí Visual Studio IDE, zobrazí se jenom `Where` metoda, ale jiné metody, jako `Select`, `SelectMany`, `Join`, a `Orderby`.</span><span class="sxs-lookup"><span data-stu-id="75a85-120">However, if you invoke the IntelliSense completion list in the Visual Studio IDE, you will see not only a `Where` method, but many other methods such as `Select`, `SelectMany`, `Join`, and `Orderby`.</span></span> <span data-ttu-id="75a85-121">Toto jsou všechny standardní operátory dotazu.</span><span class="sxs-lookup"><span data-stu-id="75a85-121">These are all the standard query operators.</span></span>  
  
 <span data-ttu-id="75a85-122">![Standardní operátory dotazu v Intellisense](../../../../csharp/programming-guide/concepts/linq/media/standardqueryops.png "StandardQueryOps")</span><span class="sxs-lookup"><span data-stu-id="75a85-122">![Standard Query Operators in Intellisense](../../../../csharp/programming-guide/concepts/linq/media/standardqueryops.png "StandardQueryOps")</span></span>  
  
 <span data-ttu-id="75a85-123">I když vypadá to, jako kdyby <xref:System.Collections.Generic.IEnumerable%601> podřízených zahrnout tyto další metody fakt tomu tak není.</span><span class="sxs-lookup"><span data-stu-id="75a85-123">Although it looks as if <xref:System.Collections.Generic.IEnumerable%601> has been redefined to include these additional methods, in fact this is not the case.</span></span> <span data-ttu-id="75a85-124">Standardní operátory dotazu jsou implementované jako nový druh metodu s názvem *rozšiřující metody*.</span><span class="sxs-lookup"><span data-stu-id="75a85-124">The standard query operators are implemented as a new kind of method called *extension methods*.</span></span> <span data-ttu-id="75a85-125">Metody rozšíření "rozšíření" existující typ; je možné volat jako kdyby byly metody instance typu.</span><span class="sxs-lookup"><span data-stu-id="75a85-125">Extensions methods "extend" an existing type; they can be called as if they were instance methods on the type.</span></span> <span data-ttu-id="75a85-126">Rozšíření standardní operátory dotazu <xref:System.Collections.Generic.IEnumerable%601> a který je proč můžete napsat `numbers.Where(...)`.</span><span class="sxs-lookup"><span data-stu-id="75a85-126">The standard query operators extend <xref:System.Collections.Generic.IEnumerable%601> and that is why you can write `numbers.Where(...)`.</span></span>  
  
 <span data-ttu-id="75a85-127">Abyste mohli začít používat [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], všechno, co máte skutečně potřebujete vědět o rozšiřující metody je postup, aby byly v oboru ve vaší aplikaci pomocí správného `using` direktivy.</span><span class="sxs-lookup"><span data-stu-id="75a85-127">To get started using [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], all that you really have to know about extension methods is how to bring them into scope in your application by using the correct `using` directives.</span></span> <span data-ttu-id="75a85-128">Z vaší aplikace metody rozšíření a normální instanci metody jsou stejné.</span><span class="sxs-lookup"><span data-stu-id="75a85-128">From your application's point of view, an extension method and a regular instance method are the same.</span></span>  
  
 <span data-ttu-id="75a85-129">Další informace o metodách rozšíření najdete v tématu [rozšiřující metody](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="75a85-129">For more information about extension methods, see [Extension Methods](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md).</span></span> <span data-ttu-id="75a85-130">Další informace o standardních operátorů dotazu najdete v tématu [standardní přehled operátory dotazu (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md).</span><span class="sxs-lookup"><span data-stu-id="75a85-130">For more information about standard query operators, see [Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md).</span></span> <span data-ttu-id="75a85-131">Některé [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] poskytovatelů, jako například [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], implementovat vlastní standardní operátory dotazu a další rozšiřující metody pro jiné typy kromě <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="75a85-131">Some [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] providers, such as [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] and [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], implement their own standard query operators and additional extension methods for other types besides <xref:System.Collections.Generic.IEnumerable%601>.</span></span>  
  
## <a name="lambda-expressions"></a><span data-ttu-id="75a85-132">Výrazy lambda</span><span class="sxs-lookup"><span data-stu-id="75a85-132">Lambda Expressions</span></span>  
 <span data-ttu-id="75a85-133">V předchozím příkladu, Všimněte si, že podmíněným výrazem (`num % 2 == 0`) se předá jako argumentu v řádku `Where` metoda: `Where(num => num % 2 == 0).` tento výraz vložené nazývá výrazu lambda.</span><span class="sxs-lookup"><span data-stu-id="75a85-133">In the previous example, notice that the conditional expression (`num % 2 == 0`) is passed as an in-line argument to the `Where` method: `Where(num => num % 2 == 0).` This inline expression is called a lambda expression.</span></span> <span data-ttu-id="75a85-134">Je pohodlný způsob, jak napsat kód, který byste jinak museli k zapsání v těžkopádnější formuláře jako anonymní metody nebo obecný delegát strom výrazu se nezdařilo.</span><span class="sxs-lookup"><span data-stu-id="75a85-134">It is a convenient way to write code that would otherwise have to be written in more cumbersome form as an anonymous method or a generic delegate or an expression tree.</span></span> <span data-ttu-id="75a85-135">V jazyce C# `=>` je lambda operátor, který je pro čtení jako "vloží do".</span><span class="sxs-lookup"><span data-stu-id="75a85-135">In C# `=>` is the lambda operator, which is read as "goes to".</span></span> <span data-ttu-id="75a85-136">`num` Na levé straně operátoru je vstupní proměnné, který odpovídá `num` ve výrazu dotazu.</span><span class="sxs-lookup"><span data-stu-id="75a85-136">The `num` on the left of the operator is the input variable which corresponds to `num` in the query expression.</span></span> <span data-ttu-id="75a85-137">Kompilátor lze odvodit typ `num` vzhledem k tomu, který zná `numbers` je obecný <xref:System.Collections.Generic.IEnumerable%601> typu.</span><span class="sxs-lookup"><span data-stu-id="75a85-137">The compiler can infer the type of `num` because it knows that `numbers` is a generic <xref:System.Collections.Generic.IEnumerable%601> type.</span></span> <span data-ttu-id="75a85-138">Tělo argument lambda je stejně jako výraz v syntaxi dotazu nebo v jakékoli jiné C# výraz nebo příkaz; může zahrnovat volání metod a jiné komplexní logiku.</span><span class="sxs-lookup"><span data-stu-id="75a85-138">The body of the lambda is just the same as the expression in query syntax or in any other C# expression or statement; it can include method calls and other complex logic.</span></span> <span data-ttu-id="75a85-139">"Návratovou hodnotu" je právě výsledkem výrazu.</span><span class="sxs-lookup"><span data-stu-id="75a85-139">The "return value" is just the expression result.</span></span>  
  
 <span data-ttu-id="75a85-140">Abyste mohli začít používat [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], není nutné používat lambdas hojně.</span><span class="sxs-lookup"><span data-stu-id="75a85-140">To get started using [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], you do not have to use lambdas extensively.</span></span> <span data-ttu-id="75a85-141">Ale některé dotazy lze vyjádřit pouze v syntaxe využívající metody a některé z nich vyžadovat výrazy lambda.</span><span class="sxs-lookup"><span data-stu-id="75a85-141">However, certain queries can only be expressed in method syntax and some of those require lambda expressions.</span></span> <span data-ttu-id="75a85-142">Po seznámení s lambdas, zjistíte, že jsou nástroje výkonný a flexibilní vaší [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] sady nástrojů.</span><span class="sxs-lookup"><span data-stu-id="75a85-142">After you become more familiar with lambdas, you will find that they are a powerful and flexible tool in your [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] toolbox.</span></span> <span data-ttu-id="75a85-143">Další informace najdete v tématu [výrazy Lambda](../../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="75a85-143">For more information, see [Lambda Expressions](../../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>  
  
## <a name="composability-of-queries"></a><span data-ttu-id="75a85-144">Skládání dotazů</span><span class="sxs-lookup"><span data-stu-id="75a85-144">Composability of Queries</span></span>  
 <span data-ttu-id="75a85-145">V předchozím příkladu kódu, Všimněte si, že `OrderBy` metoda je volána pomocí operátoru tečka na volání `Where`.</span><span class="sxs-lookup"><span data-stu-id="75a85-145">In the previous code example, note that the `OrderBy` method is invoked by using the dot operator on the call to `Where`.</span></span> <span data-ttu-id="75a85-146">`Where`Vytvoří filtrované pořadí a potom `Orderby` funguje v tomto pořadí tak, že ho řazení.</span><span class="sxs-lookup"><span data-stu-id="75a85-146">`Where` produces a filtered sequence, and then `Orderby` operates on that sequence by sorting it.</span></span> <span data-ttu-id="75a85-147">Protože vrátit dotazy `IEnumerable`, můžete vytvořit v syntaxi metoda podle řetězení volání metod společně.</span><span class="sxs-lookup"><span data-stu-id="75a85-147">Because queries return an `IEnumerable`, you compose them in method syntax by chaining the method calls together.</span></span> <span data-ttu-id="75a85-148">Toto je kompilátor jaké na pozadí při psaní dotazy pomocí syntaxe dotazu.</span><span class="sxs-lookup"><span data-stu-id="75a85-148">This is what the compiler does behind the scenes when you write queries by using query syntax.</span></span> <span data-ttu-id="75a85-149">A protože proměnné dotazu neukládá výsledky dotazu, můžete upravit ji nebo ji použít jako základ pro nový dotaz kdykoli, i když nebyla spuštěna.</span><span class="sxs-lookup"><span data-stu-id="75a85-149">And because a query variable does not store the results of the query, you can modify it or use it as the basis for a new query at any time, even after it has been executed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75a85-150">Viz také</span><span class="sxs-lookup"><span data-stu-id="75a85-150">See Also</span></span>  
 [<span data-ttu-id="75a85-151">Začínáme s dotazy LINQ v jazyku C#</span><span class="sxs-lookup"><span data-stu-id="75a85-151">Getting Started with LINQ in C#</span></span>](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)
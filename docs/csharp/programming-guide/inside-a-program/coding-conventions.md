---
title: "Převody kódování C# (Průvodce programováním v C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- coding conventions, C#
- Visual C#, coding conventions
- C# language, coding conventions
ms.assetid: f4f60de9-d49b-4fb6-bab1-20e19ea24710
caps.latest.revision: "32"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 84ddc2b3cebb6bad95f5076889de11f12624b4de
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="c-coding-conventions-c-programming-guide"></a><span data-ttu-id="b1d95-102">Převody kódování C# (Průvodce programováním v C#)</span><span class="sxs-lookup"><span data-stu-id="b1d95-102">C# Coding Conventions (C# Programming Guide)</span></span>
<span data-ttu-id="b1d95-103">[Specifikace jazyka C#](http://go.microsoft.com/fwlink/?LinkId=199552) nedefinuje kódování standard.</span><span class="sxs-lookup"><span data-stu-id="b1d95-103">The [C# Language Specification](http://go.microsoft.com/fwlink/?LinkId=199552) does not define a coding standard.</span></span> <span data-ttu-id="b1d95-104">Podle pokynů v tomto tématu jsou však použít společností Microsoft k vývoji ukázky a dokumentace.</span><span class="sxs-lookup"><span data-stu-id="b1d95-104">However, the guidelines in this topic are used by Microsoft to develop samples and documentation.</span></span>  
  
 <span data-ttu-id="b1d95-105">Konvence psaní kódu slouží k následujícím účelům:</span><span class="sxs-lookup"><span data-stu-id="b1d95-105">Coding conventions serve the following purposes:</span></span>  
  
-   <span data-ttu-id="b1d95-106">Konzistentní vzhled kódu, vytvářejí tak, aby čtenáři můžou zaměřit na obsah, není rozložení.</span><span class="sxs-lookup"><span data-stu-id="b1d95-106">They create a consistent look to the code, so that readers can focus on content, not layout.</span></span>  
  
-   <span data-ttu-id="b1d95-107">Umožňují uživatelům pochopit kód rychleji provede odhad založené na předchozí zkušenosti.</span><span class="sxs-lookup"><span data-stu-id="b1d95-107">They enable readers to understand the code more quickly by making assumptions based on previous experience.</span></span>  
  
-   <span data-ttu-id="b1d95-108">Usnadnění jejich kopírování, změna a údržbě kód.</span><span class="sxs-lookup"><span data-stu-id="b1d95-108">They facilitate copying, changing, and maintaining the code.</span></span>  
  
-   <span data-ttu-id="b1d95-109">Vysvětlují, C# osvědčené postupy.</span><span class="sxs-lookup"><span data-stu-id="b1d95-109">They demonstrate C# best practices.</span></span>  
  
## <a name="naming-conventions"></a><span data-ttu-id="b1d95-110">Zásady vytváření názvů</span><span class="sxs-lookup"><span data-stu-id="b1d95-110">Naming Conventions</span></span>  
  
-   <span data-ttu-id="b1d95-111">V krátké příklady, které neobsahují [pomocí direktiv](../../../csharp/language-reference/keywords/using-directive.md), použijte kvalifikaci oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="b1d95-111">In short examples that do not include [using directives](../../../csharp/language-reference/keywords/using-directive.md), use namespace qualifications.</span></span> <span data-ttu-id="b1d95-112">Pokud víte, že je ve výchozím nastavení v projektu naimportovat obor názvů, nemáte k plnému určení názvy z daného oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="b1d95-112">If you know that a namespace is imported by default in a project, you do not have to fully qualify the names from that namespace.</span></span> <span data-ttu-id="b1d95-113">Kvalifikované názvy může být poškozená po tečku (.) Pokud jsou moc dlouhý na jeden řádek, jak je znázorněno v následujícím příkladu.</span><span class="sxs-lookup"><span data-stu-id="b1d95-113">Qualified names can be broken after a dot (.) if they are too long for a single line, as shown in the following example.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#1](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#1)]  
  
-   <span data-ttu-id="b1d95-114">Chcete-li změnit názvy objektů, které byly vytvořeny pomocí návrháře nástroje sady Visual Studio, aby byly podle dalších pokynů nemáte.</span><span class="sxs-lookup"><span data-stu-id="b1d95-114">You do not have to change the names of objects that were created by using the Visual Studio designer tools to make them fit other guidelines.</span></span>  
  
## <a name="layout-conventions"></a><span data-ttu-id="b1d95-115">Konvence rozložení</span><span class="sxs-lookup"><span data-stu-id="b1d95-115">Layout Conventions</span></span>  
 <span data-ttu-id="b1d95-116">Dobrý rozložení používá formátování zdůraznil struktura kódu a snadněji kód.</span><span class="sxs-lookup"><span data-stu-id="b1d95-116">Good layout uses formatting to emphasize the structure of your code and to make the code easier to read.</span></span> <span data-ttu-id="b1d95-117">Příklady Microsoft a ukázky splňovat následující konvence:</span><span class="sxs-lookup"><span data-stu-id="b1d95-117">Microsoft examples and samples conform to the following conventions:</span></span>  
  
-   <span data-ttu-id="b1d95-118">Použijte výchozí nastavení editoru kódu (inteligentní odsazení, čtyř znaků odsazení, karty, které jsou uloženy jako prostory).</span><span class="sxs-lookup"><span data-stu-id="b1d95-118">Use the default Code Editor settings (smart indenting, four-character indents, tabs saved as spaces).</span></span> <span data-ttu-id="b1d95-119">Další informace najdete v tématu [možnosti, textový Editor, C#, formátování vzorků](/visualstudio/ide/reference/options-text-editor-csharp-formatting).</span><span class="sxs-lookup"><span data-stu-id="b1d95-119">For more information, see [Options, Text Editor, C#, Formatting](/visualstudio/ide/reference/options-text-editor-csharp-formatting).</span></span>  
  
-   <span data-ttu-id="b1d95-120">Zapište pouze jeden příkaz na každém řádku.</span><span class="sxs-lookup"><span data-stu-id="b1d95-120">Write only one statement per line.</span></span>  
  
-   <span data-ttu-id="b1d95-121">Zapsat jenom jedna deklarace na každý řádek.</span><span class="sxs-lookup"><span data-stu-id="b1d95-121">Write only one declaration per line.</span></span>  
  
-   <span data-ttu-id="b1d95-122">Pokud pokračování řádků nejsou automaticky odsazeny, je odsadit jedné karty zastavení (čtyři prostory).</span><span class="sxs-lookup"><span data-stu-id="b1d95-122">If continuation lines are not indented automatically, indent them one tab stop (four spaces).</span></span>  
  
-   <span data-ttu-id="b1d95-123">Přidejte alespoň jeden prázdný řádek mezi definice metod a vlastností definice.</span><span class="sxs-lookup"><span data-stu-id="b1d95-123">Add at least one blank line between method definitions and property definitions.</span></span>  
  
-   <span data-ttu-id="b1d95-124">Závorky lze použijte k provádění klauzule ve výrazu je zřejmé, jak je znázorněno v následujícím kódu.</span><span class="sxs-lookup"><span data-stu-id="b1d95-124">Use parentheses to make clauses in an expression apparent, as shown in the following code.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#2](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#2)]  
  
## <a name="commenting-conventions"></a><span data-ttu-id="b1d95-125">Konvence při psaní komentářů</span><span class="sxs-lookup"><span data-stu-id="b1d95-125">Commenting Conventions</span></span>  
  
-   <span data-ttu-id="b1d95-126">Komentář umístíte na samostatném řádku, nikoli na konci řádku kódu.</span><span class="sxs-lookup"><span data-stu-id="b1d95-126">Place the comment on a separate line, not at the end of a line of code.</span></span>  
  
-   <span data-ttu-id="b1d95-127">Začněte text poznámky s velkým písmenem.</span><span class="sxs-lookup"><span data-stu-id="b1d95-127">Begin comment text with an uppercase letter.</span></span>  
  
-   <span data-ttu-id="b1d95-128">Ukončení text poznámky s tečkou.</span><span class="sxs-lookup"><span data-stu-id="b1d95-128">End comment text with a period.</span></span>  
  
-   <span data-ttu-id="b1d95-129">Vložit jeden mezer mezi oddělovač komentář (/ /) a text poznámky, jak je znázorněno v následujícím příkladu.</span><span class="sxs-lookup"><span data-stu-id="b1d95-129">Insert one space between the comment delimiter (//) and the comment text, as shown in the following example.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#3](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#3)]  
  
-   <span data-ttu-id="b1d95-130">Nevytvářejte formátovaný bloky hvězdičky kolem komentáře.</span><span class="sxs-lookup"><span data-stu-id="b1d95-130">Do not create formatted blocks of asterisks around comments.</span></span>  
  
## <a name="language-guidelines"></a><span data-ttu-id="b1d95-131">Pokyny pro jazyk</span><span class="sxs-lookup"><span data-stu-id="b1d95-131">Language Guidelines</span></span>  
 <span data-ttu-id="b1d95-132">Následující části popisují postupy, které týmem C# následujících pokynů můžete připravit příklady kódu a ukázky.</span><span class="sxs-lookup"><span data-stu-id="b1d95-132">The following sections describe practices that the C# team follows to prepare code examples and samples.</span></span>  
  
### <a name="string-data-type"></a><span data-ttu-id="b1d95-133">Datový typ String</span><span class="sxs-lookup"><span data-stu-id="b1d95-133">String Data Type</span></span>  
  
-   <span data-ttu-id="b1d95-134">Použití `+` operátor ke zřetězení krátké řetězce, jak je znázorněno v následujícím kódu.</span><span class="sxs-lookup"><span data-stu-id="b1d95-134">Use the `+` operator to concatenate short strings, as shown in the following code.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#6](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#6)]  
  
-   <span data-ttu-id="b1d95-135">Chcete-li připojit řetězců v smyčky, zejména v případě, že pracujete s velkým množstvím textu, použijte <xref:System.Text.StringBuilder> objektu.</span><span class="sxs-lookup"><span data-stu-id="b1d95-135">To append strings in loops, especially when you are working with large amounts of text, use a <xref:System.Text.StringBuilder> object.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#7](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#7)]  
  
### <a name="implicitly-typed-local-variables"></a><span data-ttu-id="b1d95-136">Implicitně typované lokální proměnné</span><span class="sxs-lookup"><span data-stu-id="b1d95-136">Implicitly Typed Local Variables</span></span>  
  
-   <span data-ttu-id="b1d95-137">Použití [implicitní zadáním](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) pro místní proměnné, když je typ proměnné zřejmé z pravé strany přiřazení nebo přesné typ není důležité.</span><span class="sxs-lookup"><span data-stu-id="b1d95-137">Use [implicit typing](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) for local variables when the type of the variable is obvious from the right side of the assignment, or when the precise type is not important.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#8](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#8)]  
  
-   <span data-ttu-id="b1d95-138">Nepoužívejte [var](../../../csharp/language-reference/keywords/var.md) při typ není zřejmá z pravé strany přiřazení.</span><span class="sxs-lookup"><span data-stu-id="b1d95-138">Do not use [var](../../../csharp/language-reference/keywords/var.md) when the type is not apparent from the right side of the assignment.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#9](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#9)]  
  
-   <span data-ttu-id="b1d95-139">Nespoléhejte na název proměnné určit typ proměnné.</span><span class="sxs-lookup"><span data-stu-id="b1d95-139">Do not rely on the variable name to specify the type of the variable.</span></span> <span data-ttu-id="b1d95-140">Nemusí být správný.</span><span class="sxs-lookup"><span data-stu-id="b1d95-140">It might not be correct.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#10](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#10)]  
  
-   <span data-ttu-id="b1d95-141">Nepoužívejte `var` místě [dynamické](../../../csharp/language-reference/keywords/dynamic.md).</span><span class="sxs-lookup"><span data-stu-id="b1d95-141">Avoid the use of `var` in place of [dynamic](../../../csharp/language-reference/keywords/dynamic.md).</span></span>  
  
-   <span data-ttu-id="b1d95-142">Použít implicitní zadáním určit typ proměnné smyčky v [pro](../../../csharp/language-reference/keywords/for.md) a [foreach](../../../csharp/language-reference/keywords/foreach-in.md) smyčky.</span><span class="sxs-lookup"><span data-stu-id="b1d95-142">Use implicit typing to determine the type of the loop variable in [for](../../../csharp/language-reference/keywords/for.md) and [foreach](../../../csharp/language-reference/keywords/foreach-in.md) loops.</span></span>  
  
     <span data-ttu-id="b1d95-143">Následující příklad používá implicitní zadáním v `for` příkaz.</span><span class="sxs-lookup"><span data-stu-id="b1d95-143">The following example uses implicit typing in a `for` statement.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#11](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#11)]  
  
     <span data-ttu-id="b1d95-144">Následující příklad používá implicitní zadáním v `foreach` příkaz.</span><span class="sxs-lookup"><span data-stu-id="b1d95-144">The following example uses implicit typing in a `foreach` statement.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#12](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#12)]  
  
### <a name="unsigned-data-type"></a><span data-ttu-id="b1d95-145">Nepodepsaný datový typ</span><span class="sxs-lookup"><span data-stu-id="b1d95-145">Unsigned Data Type</span></span>  
  
-   <span data-ttu-id="b1d95-146">Obecně platí, použijte `int` místo typy bez znaménka.</span><span class="sxs-lookup"><span data-stu-id="b1d95-146">In general, use `int` rather than unsigned types.</span></span> <span data-ttu-id="b1d95-147">Použití `int` je běžné v C#, a je jednodušší interakci s další knihovny při použití `int`.</span><span class="sxs-lookup"><span data-stu-id="b1d95-147">The use of `int` is common throughout C#, and it is easier to interact with other libraries when you use `int`.</span></span>  
  
### <a name="arrays"></a><span data-ttu-id="b1d95-148">Pole</span><span class="sxs-lookup"><span data-stu-id="b1d95-148">Arrays</span></span>  
  
-   <span data-ttu-id="b1d95-149">Při inicializaci pole na ose deklarace, použijte stručným syntaxi.</span><span class="sxs-lookup"><span data-stu-id="b1d95-149">Use the concise syntax when you initialize arrays on the declaration line.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#13](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#13)]  
  
### <a name="delegates"></a><span data-ttu-id="b1d95-150">Delegáty</span><span class="sxs-lookup"><span data-stu-id="b1d95-150">Delegates</span></span>  
  
-   <span data-ttu-id="b1d95-151">Použijte stručným syntaxi pro vytvoření instance typu delegáta.</span><span class="sxs-lookup"><span data-stu-id="b1d95-151">Use the concise syntax to create instances of a delegate type.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#14](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#14)]  
  
     [!code-csharp[csProgGuideCodingConventions#15](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#15)]  
  
### <a name="try-catch-and-using-statements-in-exception-handling"></a><span data-ttu-id="b1d95-152">Zpracování výjimek s použitím příkazů try-catch a using</span><span class="sxs-lookup"><span data-stu-id="b1d95-152">try-catch and using Statements in Exception Handling</span></span>  
  
-   <span data-ttu-id="b1d95-153">Použití [try-catch –](../../../csharp/language-reference/keywords/try-catch.md) příkaz pro většinu zpracování výjimek.</span><span class="sxs-lookup"><span data-stu-id="b1d95-153">Use a [try-catch](../../../csharp/language-reference/keywords/try-catch.md) statement for most exception handling.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#16](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#16)]  
  
-   <span data-ttu-id="b1d95-154">Zjednodušení kódu s použitím jazyka C# [pomocí příkazu](../../../csharp/language-reference/keywords/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b1d95-154">Simplify your code by using the C# [using statement](../../../csharp/language-reference/keywords/using-statement.md).</span></span> <span data-ttu-id="b1d95-155">Pokud máte [try-finally –](../../../csharp/language-reference/keywords/try-finally.md) příkaz, ve kterém kód pouze v `finally` blok je volání <xref:System.IDisposable.Dispose%2A> metoda, použití `using` příkaz místo.</span><span class="sxs-lookup"><span data-stu-id="b1d95-155">If you have a [try-finally](../../../csharp/language-reference/keywords/try-finally.md) statement in which the only code in the `finally` block is a call to the <xref:System.IDisposable.Dispose%2A> method, use a `using` statement instead.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#17](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#17)]  
  
### <a name="-and-124124-operators"></a><span data-ttu-id="b1d95-156">& & a &#124; &#124; Operátory</span><span class="sxs-lookup"><span data-stu-id="b1d95-156">&& and &#124;&#124; Operators</span></span>  
  
-   <span data-ttu-id="b1d95-157">Pokud chcete zabránit výjimky a zvyšuje výkon přeskočení nepotřebné porovnání, použijte [ && ](../../../csharp/language-reference/operators/conditional-and-operator.md) místo [ & ](../../../csharp/language-reference/operators/and-operator.md) a [&#124; &#124;](../../../csharp/language-reference/operators/conditional-or-operator.md) místo [&#124;](../../../csharp/language-reference/operators/or-operator.md) při provádění porovnávání, jak je znázorněno v následujícím příkladu.</span><span class="sxs-lookup"><span data-stu-id="b1d95-157">To avoid exceptions and increase performance by skipping unnecessary comparisons, use [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) instead of [&](../../../csharp/language-reference/operators/and-operator.md) and [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md) instead of [&#124;](../../../csharp/language-reference/operators/or-operator.md) when you perform comparisons, as shown in the following example.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#18](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#18)]  
  
### <a name="new-operator"></a><span data-ttu-id="b1d95-158">Operátor new</span><span class="sxs-lookup"><span data-stu-id="b1d95-158">New Operator</span></span>  
  
-   <span data-ttu-id="b1d95-159">Použijte stručným formu konkretizaci objektu s implicitní zadáte, jak je znázorněno v následující prohlášení.</span><span class="sxs-lookup"><span data-stu-id="b1d95-159">Use the concise form of object instantiation, with implicit typing, as shown in the following declaration.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#19](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#19)]  
  
     <span data-ttu-id="b1d95-160">Předchozí řádek je ekvivalentní následující deklaraci.</span><span class="sxs-lookup"><span data-stu-id="b1d95-160">The previous line is equivalent to the following declaration.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#20](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#20)]  
  
-   <span data-ttu-id="b1d95-161">Inicializátory objektů slouží ke zjednodušení vytváření objektů.</span><span class="sxs-lookup"><span data-stu-id="b1d95-161">Use object initializers to simplify object creation.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#21](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#21)]  
  
### <a name="event-handling"></a><span data-ttu-id="b1d95-162">Zpracování událostí</span><span class="sxs-lookup"><span data-stu-id="b1d95-162">Event Handling</span></span>  
  
-   <span data-ttu-id="b1d95-163">Pokud definujete obslužnou rutinu události, které není potřeba odebrat později, použijte výraz lambda.</span><span class="sxs-lookup"><span data-stu-id="b1d95-163">If you are defining an event handler that you do not need to remove later, use a lambda expression.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#22](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#22)]  
  
     [!code-csharp[csProgGuideCodingConventions#23](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#23)]  
  
### <a name="static-members"></a><span data-ttu-id="b1d95-164">Statické členy</span><span class="sxs-lookup"><span data-stu-id="b1d95-164">Static Members</span></span>  
  
-   <span data-ttu-id="b1d95-165">Volání [statické](../../../csharp/language-reference/keywords/static.md) členy pomocí názvu třídy: *ClassName.StaticMember*.</span><span class="sxs-lookup"><span data-stu-id="b1d95-165">Call [static](../../../csharp/language-reference/keywords/static.md) members by using the class name: *ClassName.StaticMember*.</span></span> <span data-ttu-id="b1d95-166">Tento postup umožňuje kód srozumitelnější tím, že statické přístup vymazat.</span><span class="sxs-lookup"><span data-stu-id="b1d95-166">This practice makes code more readable by making static access clear.</span></span>  <span data-ttu-id="b1d95-167">Statický člen definované v základní třídě s názvem odvozené třídy nemohou být.</span><span class="sxs-lookup"><span data-stu-id="b1d95-167">Do not qualify a static member defined in a base class with the name of a derived class.</span></span>  <span data-ttu-id="b1d95-168">Během tento kód zkompiloval, je zavádějící čitelnost kód a kód mohou končit v budoucnu, pokud přidáte do odvozené třídy je statický člen se stejným názvem.</span><span class="sxs-lookup"><span data-stu-id="b1d95-168">While that code compiles, the code readability is misleading, and the code may break in the future if you add a static member with the same name to the derived class.</span></span>  
  
### <a name="linq-queries"></a><span data-ttu-id="b1d95-169">Dotazů LINQ</span><span class="sxs-lookup"><span data-stu-id="b1d95-169">LINQ Queries</span></span>  
  
-   <span data-ttu-id="b1d95-170">Používejte smysluplný názvy proměnných dotazu.</span><span class="sxs-lookup"><span data-stu-id="b1d95-170">Use meaningful names for query variables.</span></span> <span data-ttu-id="b1d95-171">Následující příklad používá `seattleCustomers` pro zákazníky, kteří jsou umístěné v Ostravě.</span><span class="sxs-lookup"><span data-stu-id="b1d95-171">The following example uses `seattleCustomers` for customers who are located in Seattle.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#25](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#25)]  
  
-   <span data-ttu-id="b1d95-172">Pomocí aliasy se ujistěte, že jsou názvy vlastností anonymní typů správně písmeno, a to pomocí Pascal velká a malá písmena.</span><span class="sxs-lookup"><span data-stu-id="b1d95-172">Use aliases to make sure that property names of anonymous types are correctly capitalized, using Pascal casing.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#26](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#26)]  
  
-   <span data-ttu-id="b1d95-173">Přejmenujte vlastnosti názvy vlastností, které ve výsledku by být nejednoznačný.</span><span class="sxs-lookup"><span data-stu-id="b1d95-173">Rename properties when the property names in the result would be ambiguous.</span></span> <span data-ttu-id="b1d95-174">Například pokud dotaz vrátí zákazníka, název a ID distributora, místo necháte jako `Name` a `ID` ve výsledku, přejmenujte je o vysvětlení, že `Name` je název zákazníka, a `ID` je ID distributora.</span><span class="sxs-lookup"><span data-stu-id="b1d95-174">For example, if your query returns a customer name and a distributor ID, instead of leaving them as `Name` and `ID` in the result, rename them to clarify that `Name` is the name of a customer, and `ID` is the ID of a distributor.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#27](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#27)]  
  
-   <span data-ttu-id="b1d95-175">Použití implicitní zadáním v deklarace proměnné dotazu a proměnné rozsahu.</span><span class="sxs-lookup"><span data-stu-id="b1d95-175">Use implicit typing in the declaration of query variables and range variables.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#25](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#25)]  
  
-   <span data-ttu-id="b1d95-176">Zarovnat klauzule dotazu v části [z](../../../csharp/language-reference/keywords/from-clause.md) klauzule, jak je znázorněno v předchozích příkladech.</span><span class="sxs-lookup"><span data-stu-id="b1d95-176">Align query clauses under the [from](../../../csharp/language-reference/keywords/from-clause.md) clause, as shown in the previous examples.</span></span>  
  
-   <span data-ttu-id="b1d95-177">Použití [kde](../../../csharp/language-reference/keywords/where-clause.md) klauzule před další klauzule dotazu zajistit, že novější klauzule dotazu fungovat na menší, filtrovat sadu dat.</span><span class="sxs-lookup"><span data-stu-id="b1d95-177">Use [where](../../../csharp/language-reference/keywords/where-clause.md) clauses before other query clauses to ensure that later query clauses operate on the reduced, filtered set of data.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#29](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#29)]  
  
-   <span data-ttu-id="b1d95-178">Použití více `from` klauzule místo [spojení](../../../csharp/language-reference/keywords/join-clause.md) klauzule pro přístup k vnitřní kolekce.</span><span class="sxs-lookup"><span data-stu-id="b1d95-178">Use multiple `from` clauses instead of a [join](../../../csharp/language-reference/keywords/join-clause.md) clause to access inner collections.</span></span> <span data-ttu-id="b1d95-179">Například kolekce `Student` jednotlivých objektů může obsahovat kolekce výsledků testu.</span><span class="sxs-lookup"><span data-stu-id="b1d95-179">For example, a collection of `Student` objects might each contain a collection of test scores.</span></span> <span data-ttu-id="b1d95-180">Po provedení následující dotaz vrátí každý skóre, který je více než 90, společně s poslední název studenty, kteří obdrželi skóre.</span><span class="sxs-lookup"><span data-stu-id="b1d95-180">When the following query is executed, it returns each score that is over 90, along with the last name of the student who received the score.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#30](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#30)]  
  
## <a name="security"></a><span data-ttu-id="b1d95-181">Zabezpečení</span><span class="sxs-lookup"><span data-stu-id="b1d95-181">Security</span></span>  
 <span data-ttu-id="b1d95-182">Postupujte podle pokynů v [pokyny zabezpečení kódování](../../../standard/security/secure-coding-guidelines.md).</span><span class="sxs-lookup"><span data-stu-id="b1d95-182">Follow the guidelines in [Secure Coding Guidelines](../../../standard/security/secure-coding-guidelines.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1d95-183">Viz také</span><span class="sxs-lookup"><span data-stu-id="b1d95-183">See Also</span></span>  
 [<span data-ttu-id="b1d95-184">Visual Basic – konvence kódování</span><span class="sxs-lookup"><span data-stu-id="b1d95-184">Visual Basic Coding Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/coding-conventions.md)  
 [<span data-ttu-id="b1d95-185">Pokyny pro zabezpečené kódování</span><span class="sxs-lookup"><span data-stu-id="b1d95-185">Secure Coding Guidelines</span></span>](../../../standard/security/secure-coding-guidelines.md)
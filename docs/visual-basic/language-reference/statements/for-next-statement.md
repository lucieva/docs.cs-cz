---
title: "For...Next – příkaz (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Step
- vb.Next
- vb.To
- vb.for
helpviewer_keywords:
- infinite loops
- Next keyword [Visual Basic], For...Next statements
- For keyword [Visual Basic], For...Next statements
- Step keyword [Visual Basic], For...Next statements
- operator overloading, For...Next statement
- To keyword [Visual Basic], For...Next statements
- endless loops
- loops, endless
- instructions, repeating
- Next statement [Visual Basic], For...Next
- For...Next statements
- loop structures [Visual Basic], For...Next
- loops, infinite
- Exit statement [Visual Basic], For...Next statements
- For statement [Visual Basic]
ms.assetid: f5fc0d51-67ce-4c36-9f09-31c9a91c94e9
caps.latest.revision: "64"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 009c5a383cc3296f7f92888a344fa265547f1077
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="fornext-statement-visual-basic"></a><span data-ttu-id="ecb19-102">For...Next – příkaz (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ecb19-102">For...Next Statement (Visual Basic)</span></span>
<span data-ttu-id="ecb19-103">Opakuje skupinu příkazy zadaného počtu opakování.</span><span class="sxs-lookup"><span data-stu-id="ecb19-103">Repeats a group of statements a specified number of times.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecb19-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="ecb19-104">Syntax</span></span>  
  
```  
For counter [ As datatype ] = start To end [ Step step ]  
    [ statements ]  
    [ Continue For ]  
    [ statements ]  
    [ Exit For ]  
    [ statements ]  
Next [ counter ]  
```  
  
## <a name="parts"></a><span data-ttu-id="ecb19-105">Součásti</span><span class="sxs-lookup"><span data-stu-id="ecb19-105">Parts</span></span>  
  
|<span data-ttu-id="ecb19-106">Část</span><span class="sxs-lookup"><span data-stu-id="ecb19-106">Part</span></span>|<span data-ttu-id="ecb19-107">Popis</span><span class="sxs-lookup"><span data-stu-id="ecb19-107">Description</span></span>|  
|----------|-----------------|  
|`counter`|<span data-ttu-id="ecb19-108">V požadované `For` příkaz.</span><span class="sxs-lookup"><span data-stu-id="ecb19-108">Required in the `For` statement.</span></span> <span data-ttu-id="ecb19-109">Číselné proměnné.</span><span class="sxs-lookup"><span data-stu-id="ecb19-109">Numeric variable.</span></span> <span data-ttu-id="ecb19-110">Řídicí proměnná smyčky.</span><span class="sxs-lookup"><span data-stu-id="ecb19-110">The control variable for the loop.</span></span> <span data-ttu-id="ecb19-111">Další informace najdete v tématu [čítač Argument](#BKMK_Counter) dál v tomto tématu.</span><span class="sxs-lookup"><span data-stu-id="ecb19-111">For more information, see [Counter Argument](#BKMK_Counter) later in this topic.</span></span>|  
|`datatype`|<span data-ttu-id="ecb19-112">Volitelné.</span><span class="sxs-lookup"><span data-stu-id="ecb19-112">Optional.</span></span> <span data-ttu-id="ecb19-113">Datový typ `counter`.</span><span class="sxs-lookup"><span data-stu-id="ecb19-113">Data type of `counter`.</span></span> <span data-ttu-id="ecb19-114">Další informace najdete v tématu [čítač Argument](#BKMK_Counter) dál v tomto tématu.</span><span class="sxs-lookup"><span data-stu-id="ecb19-114">For more information, see [Counter Argument](#BKMK_Counter) later in this topic.</span></span>|  
|`start`|<span data-ttu-id="ecb19-115">Požadováno.</span><span class="sxs-lookup"><span data-stu-id="ecb19-115">Required.</span></span> <span data-ttu-id="ecb19-116">Číselný výraz.</span><span class="sxs-lookup"><span data-stu-id="ecb19-116">Numeric expression.</span></span> <span data-ttu-id="ecb19-117">Počáteční hodnota `counter`.</span><span class="sxs-lookup"><span data-stu-id="ecb19-117">The initial value of `counter`.</span></span>|  
|`end`|<span data-ttu-id="ecb19-118">Požadováno.</span><span class="sxs-lookup"><span data-stu-id="ecb19-118">Required.</span></span> <span data-ttu-id="ecb19-119">Číselný výraz.</span><span class="sxs-lookup"><span data-stu-id="ecb19-119">Numeric expression.</span></span> <span data-ttu-id="ecb19-120">Konečná hodnota `counter`.</span><span class="sxs-lookup"><span data-stu-id="ecb19-120">The final value of `counter`.</span></span>|  
|`step`|<span data-ttu-id="ecb19-121">Volitelné.</span><span class="sxs-lookup"><span data-stu-id="ecb19-121">Optional.</span></span> <span data-ttu-id="ecb19-122">Číselný výraz.</span><span class="sxs-lookup"><span data-stu-id="ecb19-122">Numeric expression.</span></span> <span data-ttu-id="ecb19-123">Hodnota, o kterou `counter` se zvýší pokaždé, když pomocí smyčky.</span><span class="sxs-lookup"><span data-stu-id="ecb19-123">The amount by which `counter` is incremented each time through the loop.</span></span>|  
|`statements`|<span data-ttu-id="ecb19-124">Volitelné.</span><span class="sxs-lookup"><span data-stu-id="ecb19-124">Optional.</span></span> <span data-ttu-id="ecb19-125">Jeden nebo více příkazů mezi `For` a `Next` , na kterých běží zadaného počtu opakování.</span><span class="sxs-lookup"><span data-stu-id="ecb19-125">One or more statements between `For` and `Next` that run the specified number of times.</span></span>|  
|`Continue For`|<span data-ttu-id="ecb19-126">Volitelné.</span><span class="sxs-lookup"><span data-stu-id="ecb19-126">Optional.</span></span> <span data-ttu-id="ecb19-127">Přenosy ovládacího prvku do další iterace smyčky.</span><span class="sxs-lookup"><span data-stu-id="ecb19-127">Transfers control to the next loop iteration.</span></span>|  
|`Exit For`|<span data-ttu-id="ecb19-128">Volitelné.</span><span class="sxs-lookup"><span data-stu-id="ecb19-128">Optional.</span></span> <span data-ttu-id="ecb19-129">Přenosy ovládacího prvku mimo `For` smyčky.</span><span class="sxs-lookup"><span data-stu-id="ecb19-129">Transfers control out of the `For` loop.</span></span>|  
|`Next`|<span data-ttu-id="ecb19-130">Požadováno.</span><span class="sxs-lookup"><span data-stu-id="ecb19-130">Required.</span></span> <span data-ttu-id="ecb19-131">Ukončí definice `For` smyčky.</span><span class="sxs-lookup"><span data-stu-id="ecb19-131">Terminates the definition of the `For` loop.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="ecb19-132">`To` – Klíčové slovo v tomto příkazu slouží k určení rozsahu čítače.</span><span class="sxs-lookup"><span data-stu-id="ecb19-132">The `To` keyword is used in this statement to specify the range for the counter.</span></span> <span data-ttu-id="ecb19-133">Můžete také použít toto klíčové slovo v [vyberte... Příkaz případ](../../../visual-basic/language-reference/statements/select-case-statement.md) a v deklaracích pole.</span><span class="sxs-lookup"><span data-stu-id="ecb19-133">You can also use this keyword in the [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md) and in array declarations.</span></span> <span data-ttu-id="ecb19-134">Další informace o deklaracích pole najdete v tématu [Dim – příkaz](../../../visual-basic/language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ecb19-134">For more information about array declarations, see [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>  
  
## <a name="simple-examples"></a><span data-ttu-id="ecb19-135">Jednoduché příklady</span><span class="sxs-lookup"><span data-stu-id="ecb19-135">Simple Examples</span></span>  
 <span data-ttu-id="ecb19-136">Můžete použít `For`... `Next` struktury, pokud má být opakován sadu příkazy set stanovený počet.</span><span class="sxs-lookup"><span data-stu-id="ecb19-136">You use a `For`...`Next` structure when you want to repeat a set of statements a set number of times.</span></span>  
  
 <span data-ttu-id="ecb19-137">V následujícím příkladu `index` proměnnou začíná na hodnotu 1 a je zvýšen při každé iteraci smyčky, končí po hodnotu `index` dosáhne 5.</span><span class="sxs-lookup"><span data-stu-id="ecb19-137">In the following example, the `index` variable starts with a value of 1 and is incremented with each iteration of the loop, ending after the value of `index` reaches 5.</span></span>  
  
 [!code-vb[VbVbalrStatements#111](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_1.vb)]  
  
 <span data-ttu-id="ecb19-138">V následujícím příkladu `number` proměnnou spustí na 2 a je snížit 0,25 na každé iteraci smyčky, končí po hodnotu `number` dosáhne 0.</span><span class="sxs-lookup"><span data-stu-id="ecb19-138">In the following example, the `number` variable starts at 2 and is reduced by 0.25 on each iteration of the loop, ending after the value of `number` reaches 0.</span></span> <span data-ttu-id="ecb19-139">`Step` Argument `-.25` snižuje hodnotu podle 0,25 na každé iteraci smyčky.</span><span class="sxs-lookup"><span data-stu-id="ecb19-139">The `Step` argument of `-.25` reduces the value by 0.25 on each iteration of the loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#112](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_2.vb)]  
  
> [!TIP]
>  <span data-ttu-id="ecb19-140">A [při... End While – příkaz](../../../visual-basic/language-reference/statements/while-end-while-statement.md) nebo [provést... Příkaz LOOP](../../../visual-basic/language-reference/statements/do-loop-statement.md) funguje dobře, pokud neznáte předem jak často má spustit příkazy ve smyčce.</span><span class="sxs-lookup"><span data-stu-id="ecb19-140">A [While...End While Statement](../../../visual-basic/language-reference/statements/while-end-while-statement.md) or [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md) works well when you don't know in advance how many times to run the statements in the loop.</span></span> <span data-ttu-id="ecb19-141">Ale očekáváte-li spustit konkrétní počet opakování, smyčky `For`... `Next` smyčka je lepší volbou.</span><span class="sxs-lookup"><span data-stu-id="ecb19-141">However, when you expect to run the loop a specific number of times, a `For`...`Next` loop is a better choice.</span></span> <span data-ttu-id="ecb19-142">Když poprvé vstoupíte smyčky určíte počet iterací.</span><span class="sxs-lookup"><span data-stu-id="ecb19-142">You determine the number of iterations when you first enter the loop.</span></span>  
  
## <a name="nesting-loops"></a><span data-ttu-id="ecb19-143">Vnoření smyčky</span><span class="sxs-lookup"><span data-stu-id="ecb19-143">Nesting Loops</span></span>  
 <span data-ttu-id="ecb19-144">Lze vnořit `For` smyčky umístěním jednoho smyčky v rámci jiného.</span><span class="sxs-lookup"><span data-stu-id="ecb19-144">You can nest `For` loops by putting one loop within another.</span></span> <span data-ttu-id="ecb19-145">Následující příklad ukazuje vnořené `For`... `Next` struktury, které mají různé krok hodnoty.</span><span class="sxs-lookup"><span data-stu-id="ecb19-145">The following example demonstrates nested `For`...`Next` structures that have different step values.</span></span> <span data-ttu-id="ecb19-146">Vnější smyčky vytvoří řetězec pro každou iteraci smyčky.</span><span class="sxs-lookup"><span data-stu-id="ecb19-146">The outer loop creates a string for every iteration of the loop.</span></span> <span data-ttu-id="ecb19-147">Vnitřní smyčka snižuje proměnnou smyčky čítače pro každou iteraci smyčky.</span><span class="sxs-lookup"><span data-stu-id="ecb19-147">The inner loop decrements a loop counter variable for every iteration of the loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#113](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_3.vb)]  
  
 <span data-ttu-id="ecb19-148">Při vnoření smyčky, musí mít jedinečnou každou smyčku `counter` proměnné.</span><span class="sxs-lookup"><span data-stu-id="ecb19-148">When nesting loops, each loop must have a unique `counter` variable.</span></span>  
  
 <span data-ttu-id="ecb19-149">Můžete také vnořovat různých druhů řídicí struktury v rámci navzájem.</span><span class="sxs-lookup"><span data-stu-id="ecb19-149">You can also nest different kinds control structures within each other.</span></span> <span data-ttu-id="ecb19-150">Další informace najdete v tématu [vnořené řídicí struktury](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span><span class="sxs-lookup"><span data-stu-id="ecb19-150">For more information, see [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>  
  
## <a name="exit-for-and-continue-for"></a><span data-ttu-id="ecb19-151">Pro ukončení a pokračovat pro</span><span class="sxs-lookup"><span data-stu-id="ecb19-151">Exit For and Continue For</span></span>  
 <span data-ttu-id="ecb19-152">`Exit For` Příkazu se okamžitě ukončí `For`...`Next`</span><span class="sxs-lookup"><span data-stu-id="ecb19-152">The `Exit For` statement immediately exits the `For`…`Next`</span></span> <span data-ttu-id="ecb19-153">smyčky a přenosy ovládacího prvku do příkazu, který odpovídá `Next` příkaz.</span><span class="sxs-lookup"><span data-stu-id="ecb19-153">loop and transfers control to the statement that follows the `Next` statement.</span></span>  
  
 <span data-ttu-id="ecb19-154">`Continue For` Řízení příkaz okamžitě přenese do další iterace smyčky.</span><span class="sxs-lookup"><span data-stu-id="ecb19-154">The `Continue For` statement transfers control immediately to the next iteration of the loop.</span></span> <span data-ttu-id="ecb19-155">Další informace najdete v tématu [pokračovat příkaz](../../../visual-basic/language-reference/statements/continue-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ecb19-155">For more information, see [Continue Statement](../../../visual-basic/language-reference/statements/continue-statement.md).</span></span>  
  
 <span data-ttu-id="ecb19-156">Následující příklad ukazuje použití `Continue For` a `Exit For` příkazy.</span><span class="sxs-lookup"><span data-stu-id="ecb19-156">The following example illustrates the use of the `Continue For` and `Exit For` statements.</span></span>  
  
 [!code-vb[VbVbalrStatements#115](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_4.vb)]  
  
 <span data-ttu-id="ecb19-157">Můžete použít a zadat libovolný počet `Exit For` příkazy v `For`...`Next`</span><span class="sxs-lookup"><span data-stu-id="ecb19-157">You can put any number of `Exit For` statements in a `For`…`Next`</span></span> <span data-ttu-id="ecb19-158">Smyčky.</span><span class="sxs-lookup"><span data-stu-id="ecb19-158">loop.</span></span> <span data-ttu-id="ecb19-159">Při použití uvnitř vnořené `For`...`Next`</span><span class="sxs-lookup"><span data-stu-id="ecb19-159">When used within nested `For`…`Next`</span></span> <span data-ttu-id="ecb19-160">smyčky, `Exit For` ukončí nejvnitřnější smyčky a předá řízení další vyšší úroveň vnoření.</span><span class="sxs-lookup"><span data-stu-id="ecb19-160">loops, `Exit For` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>  
  
 <span data-ttu-id="ecb19-161">`Exit For`Po vyhodnocení nějaká podmínka se často používá (například v `If`... `Then`... `Else` struktura).</span><span class="sxs-lookup"><span data-stu-id="ecb19-161">`Exit For` is often used after you evaluate some condition (for example, in an `If`...`Then`...`Else` structure).</span></span> <span data-ttu-id="ecb19-162">Můžete chtít použít `Exit For` byly splněny následující podmínky:</span><span class="sxs-lookup"><span data-stu-id="ecb19-162">You might want to use `Exit For` for the following conditions:</span></span>  
  
-   <span data-ttu-id="ecb19-163">Pokračovat v procházení je zbytečné nebo dokonce znemožňují.</span><span class="sxs-lookup"><span data-stu-id="ecb19-163">Continuing to iterate is unnecessary or impossible.</span></span> <span data-ttu-id="ecb19-164">Chybná hodnota nebo žádost o ukončení může vytvořit tuto podmínku.</span><span class="sxs-lookup"><span data-stu-id="ecb19-164">An erroneous value or a termination request might create this condition.</span></span>  
  
-   <span data-ttu-id="ecb19-165">A `Try`... `Catch`... `Finally` příkaz zachytí výjimku.</span><span class="sxs-lookup"><span data-stu-id="ecb19-165">A `Try`...`Catch`...`Finally` statement catches an exception.</span></span> <span data-ttu-id="ecb19-166">Můžete použít `Exit For` na konci `Finally` bloku.</span><span class="sxs-lookup"><span data-stu-id="ecb19-166">You might use `Exit For` at the end of the `Finally` block.</span></span>  
  
-   <span data-ttu-id="ecb19-167">Máte nekonečnou smyčku, což je smyčku, který by mohl spustit velký, nebo i nekonečné stanovený počet.</span><span class="sxs-lookup"><span data-stu-id="ecb19-167">You have an endless loop, which is a loop that could run a large or even infinite number of times.</span></span> <span data-ttu-id="ecb19-168">Pokud zjistíte takové podmínky, můžete použít `Exit For` abyste se vyhnuli smyčky.</span><span class="sxs-lookup"><span data-stu-id="ecb19-168">If you detect such a condition, you can use `Exit For` to escape the loop.</span></span> <span data-ttu-id="ecb19-169">Další informace najdete v tématu [provést... Cykly příkaz](../../../visual-basic/language-reference/statements/do-loop-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ecb19-169">For more information, see [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md).</span></span>  
  
## <a name="technical-implementation"></a><span data-ttu-id="ecb19-170">Technická implementace</span><span class="sxs-lookup"><span data-stu-id="ecb19-170">Technical Implementation</span></span>  
 <span data-ttu-id="ecb19-171">Když `For`... `Next` spuštění cyklu, vyhodnotí jazyka Visual Basic `start`, `end`, a `step`.</span><span class="sxs-lookup"><span data-stu-id="ecb19-171">When a `For`...`Next` loop starts, Visual Basic evaluates `start`, `end`, and `step`.</span></span> <span data-ttu-id="ecb19-172">Visual Basic vyhodnotí tyto hodnoty pouze v tento čas a potom přiřadí `start` k `counter`.</span><span class="sxs-lookup"><span data-stu-id="ecb19-172">Visual Basic evaluates these values only at this time and then assigns `start` to `counter`.</span></span> <span data-ttu-id="ecb19-173">Před příkaz bloku spustí, Visual Basic porovná `counter` k `end`.</span><span class="sxs-lookup"><span data-stu-id="ecb19-173">Before the statement block runs, Visual Basic compares `counter` to `end`.</span></span> <span data-ttu-id="ecb19-174">Pokud `counter` je větší než `end` hodnotu (nebo menší, pokud `step` záporné), `For` cykly končí a řídit předává do příkazu, který odpovídá `Next` příkaz.</span><span class="sxs-lookup"><span data-stu-id="ecb19-174">If `counter` is already larger than the `end` value (or smaller if `step` is negative), the `For` loop ends and control passes to the statement that follows the `Next` statement.</span></span> <span data-ttu-id="ecb19-175">Jinak spustí příkaz bloku.</span><span class="sxs-lookup"><span data-stu-id="ecb19-175">Otherwise, the statement block runs.</span></span>  
  
 <span data-ttu-id="ecb19-176">Pokaždé, když komunikaci jazyka Visual Basic `Next` prohlášení, navýší `counter` podle `step` a vrátí do `For` příkaz.</span><span class="sxs-lookup"><span data-stu-id="ecb19-176">Each time Visual Basic encounters the `Next` statement, it increments `counter` by `step` and returns to the `For` statement.</span></span> <span data-ttu-id="ecb19-177">Znovu porovná `counter` k `end`, a znovu ji buď běží bloku nebo ukončení smyčky, v závislosti na výsledku.</span><span class="sxs-lookup"><span data-stu-id="ecb19-177">Again it compares `counter` to `end`, and again it either runs the block or exits the loop, depending on the result.</span></span> <span data-ttu-id="ecb19-178">Tento proces pokračuje, dokud `counter` předá `end` nebo `Exit For` příkaz je zjistil.</span><span class="sxs-lookup"><span data-stu-id="ecb19-178">This process continues until `counter` passes `end` or an `Exit For` statement is encountered.</span></span>  
  
 <span data-ttu-id="ecb19-179">Dokud nebude zastavit smyčky `counter` uplynutí `end`.</span><span class="sxs-lookup"><span data-stu-id="ecb19-179">The loop doesn't stop until `counter` has passed `end`.</span></span> <span data-ttu-id="ecb19-180">Pokud `counter` rovná `end`, že opakování ve smyčce bude pokračovat.</span><span class="sxs-lookup"><span data-stu-id="ecb19-180">If `counter` is equal to `end`, the loop continues.</span></span> <span data-ttu-id="ecb19-181">Porovnání, které určuje, jestli se má spustit blok je `counter`  <=  `end` Pokud `step` kladné a `counter`  >=  `end` Pokud `step` záporné.</span><span class="sxs-lookup"><span data-stu-id="ecb19-181">The comparison that determines whether to run the block is `counter` <= `end` if `step` is positive and `counter` >= `end` if `step` is negative.</span></span>  
  
 <span data-ttu-id="ecb19-182">Pokud změníte hodnotu `counter` při uvnitř smyčku, může být obtížné číst a ladění kódu.</span><span class="sxs-lookup"><span data-stu-id="ecb19-182">If you change the value of `counter` while inside a loop, your code might be more difficult to read and debug.</span></span> <span data-ttu-id="ecb19-183">Změna hodnoty `start`, `end`, nebo `step` nemá vliv iterace hodnoty, které se zjistilo, že při prvním zadání smyčky.</span><span class="sxs-lookup"><span data-stu-id="ecb19-183">Changing the value of `start`, `end`, or `step` doesn't affect the iteration values that were determined when the loop was first entered.</span></span>  
  
 <span data-ttu-id="ecb19-184">Pokud je vnořovat smyčky, kompilátor signály chybu pokud zjistí `Next` příkaz vnější úroveň vnoření před `Next` prohlášení o informacích o vnitřní úroveň.</span><span class="sxs-lookup"><span data-stu-id="ecb19-184">If you nest loops, the compiler signals an error if it encounters the `Next` statement of an outer nesting level before the `Next` statement of an inner level.</span></span> <span data-ttu-id="ecb19-185">Ale kompilátor to zjistit překrývající se chyby pouze v případě, že zadáte `counter` v každé `Next` příkaz.</span><span class="sxs-lookup"><span data-stu-id="ecb19-185">However, the compiler can detect this overlapping error only if you specify `counter` in every `Next` statement.</span></span>  
  
### <a name="step-argument"></a><span data-ttu-id="ecb19-186">Argument krok</span><span class="sxs-lookup"><span data-stu-id="ecb19-186">Step Argument</span></span>  
 <span data-ttu-id="ecb19-187">Hodnota `step` může být kladná nebo záporná.</span><span class="sxs-lookup"><span data-stu-id="ecb19-187">The value of `step` can be either positive or negative.</span></span> <span data-ttu-id="ecb19-188">Tento parametr určuje zpracování smyčky podle následující tabulky:</span><span class="sxs-lookup"><span data-stu-id="ecb19-188">This parameter determines loop processing according to the following table:</span></span>  
  
|<span data-ttu-id="ecb19-189">**Hodnota kroku**</span><span class="sxs-lookup"><span data-stu-id="ecb19-189">**Step value**</span></span>|<span data-ttu-id="ecb19-190">**Smyčky provede Pokud**</span><span class="sxs-lookup"><span data-stu-id="ecb19-190">**Loop executes if**</span></span>|  
|--------------------|--------------------------|  
|<span data-ttu-id="ecb19-191">Kladné nebo nula.</span><span class="sxs-lookup"><span data-stu-id="ecb19-191">Positive or zero</span></span>|`counter` <= `end`|  
|<span data-ttu-id="ecb19-192">Záporný</span><span class="sxs-lookup"><span data-stu-id="ecb19-192">Negative</span></span>|`counter` >= `end`|  
  
 <span data-ttu-id="ecb19-193">Výchozí hodnota `step` je 1.</span><span class="sxs-lookup"><span data-stu-id="ecb19-193">The default value of `step` is 1.</span></span>  
  
###  <span data-ttu-id="ecb19-194"><a name="BKMK_Counter"></a>Argument čítače</span><span class="sxs-lookup"><span data-stu-id="ecb19-194"><a name="BKMK_Counter"></a> Counter Argument</span></span>  
 <span data-ttu-id="ecb19-195">Následující tabulka udává, zda `counter` definuje novou místní proměnné, která je vymezen na celou `For…Next` smyčky.</span><span class="sxs-lookup"><span data-stu-id="ecb19-195">The following table indicates whether `counter` defines a new local variable that’s scoped to the entire `For…Next` loop.</span></span> <span data-ttu-id="ecb19-196">Toto rozhodnutí závisí na tom, zda `datatype` je k dispozici a zda `counter` je již definován.</span><span class="sxs-lookup"><span data-stu-id="ecb19-196">This determination depends on whether `datatype` is present and whether `counter` is already defined.</span></span>  
  
|<span data-ttu-id="ecb19-197">Je `datatype` přítomen?</span><span class="sxs-lookup"><span data-stu-id="ecb19-197">Is `datatype` present?</span></span>|<span data-ttu-id="ecb19-198">Je `counter` již definována?</span><span class="sxs-lookup"><span data-stu-id="ecb19-198">Is `counter` already defined?</span></span>|<span data-ttu-id="ecb19-199">Výsledek (jestli `counter` definuje novou místní proměnné, která je vymezen na celou `For...Next` smyčky)</span><span class="sxs-lookup"><span data-stu-id="ecb19-199">Result (whether `counter` defines a new local variable that’s scoped to the entire `For...Next` loop)</span></span>|  
|----------------------------|-----------------------------------|-------------------------------------------------------------------------------------------------------------|  
|<span data-ttu-id="ecb19-200">Ne</span><span class="sxs-lookup"><span data-stu-id="ecb19-200">No</span></span>|<span data-ttu-id="ecb19-201">Ano</span><span class="sxs-lookup"><span data-stu-id="ecb19-201">Yes</span></span>|<span data-ttu-id="ecb19-202">Ne, protože `counter` je již definován.</span><span class="sxs-lookup"><span data-stu-id="ecb19-202">No, because `counter` is already defined.</span></span> <span data-ttu-id="ecb19-203">Pokud obor `counter` není místní k postupu, dojde k upozornění kompilace.</span><span class="sxs-lookup"><span data-stu-id="ecb19-203">If the scope of `counter` isn't local to the procedure, a compile-time warning occurs.</span></span>|  
|<span data-ttu-id="ecb19-204">Ne</span><span class="sxs-lookup"><span data-stu-id="ecb19-204">No</span></span>|<span data-ttu-id="ecb19-205">Ne</span><span class="sxs-lookup"><span data-stu-id="ecb19-205">No</span></span>|<span data-ttu-id="ecb19-206">Ano.</span><span class="sxs-lookup"><span data-stu-id="ecb19-206">Yes.</span></span> <span data-ttu-id="ecb19-207">Datový typ je odvozeno z `start`, `end`, a `step` výrazy.</span><span class="sxs-lookup"><span data-stu-id="ecb19-207">The data type is inferred from the `start`, `end`, and `step` expressions.</span></span> <span data-ttu-id="ecb19-208">Informace o odvození typu najdete v tématu [Option Infer – příkaz](../../../visual-basic/language-reference/statements/option-infer-statement.md) a [odvození místního typu](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="ecb19-208">For information about type inference, see [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) and [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>|  
|<span data-ttu-id="ecb19-209">Ano</span><span class="sxs-lookup"><span data-stu-id="ecb19-209">Yes</span></span>|<span data-ttu-id="ecb19-210">Ano</span><span class="sxs-lookup"><span data-stu-id="ecb19-210">Yes</span></span>|<span data-ttu-id="ecb19-211">Ano, ale jenom v případě existující `counter` proměnná je definována mimo proces.</span><span class="sxs-lookup"><span data-stu-id="ecb19-211">Yes, but only if the existing `counter` variable is defined outside the procedure.</span></span> <span data-ttu-id="ecb19-212">Tuto proměnnou zůstane samostatné.</span><span class="sxs-lookup"><span data-stu-id="ecb19-212">That variable remains separate.</span></span> <span data-ttu-id="ecb19-213">Pokud obor existující `counter` proměnné je místní k postupu, dojde k chybě kompilace.</span><span class="sxs-lookup"><span data-stu-id="ecb19-213">If the scope of the existing `counter` variable is local to the procedure, a compile-time error occurs.</span></span>|  
|<span data-ttu-id="ecb19-214">Ano</span><span class="sxs-lookup"><span data-stu-id="ecb19-214">Yes</span></span>|<span data-ttu-id="ecb19-215">Ne</span><span class="sxs-lookup"><span data-stu-id="ecb19-215">No</span></span>|<span data-ttu-id="ecb19-216">Ano.</span><span class="sxs-lookup"><span data-stu-id="ecb19-216">Yes.</span></span>|  
  
 <span data-ttu-id="ecb19-217">Datový typ `counter` Určuje typ iterace, které musí mít jednu z následujících typů:</span><span class="sxs-lookup"><span data-stu-id="ecb19-217">The data type of `counter` determines the type of the iteration, which must be one of the following types:</span></span>  
  
-   <span data-ttu-id="ecb19-218">A `Byte`, `SByte`, `UShort`, `Short`, `UInteger`, `Integer`, `ULong`, `Long`, `Decimal`, `Single`, nebo `Double`.</span><span class="sxs-lookup"><span data-stu-id="ecb19-218">A `Byte`, `SByte`, `UShort`, `Short`, `UInteger`, `Integer`, `ULong`, `Long`, `Decimal`, `Single`, or `Double`.</span></span>  
  
-   <span data-ttu-id="ecb19-219">Výčet, který je deklarovat pomocí [Enum – příkaz](../../../visual-basic/language-reference/statements/enum-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ecb19-219">An enumeration that you declare by using an [Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md).</span></span>  
  
-   <span data-ttu-id="ecb19-220">`Object`.</span><span class="sxs-lookup"><span data-stu-id="ecb19-220">An `Object`.</span></span>  
  
-   <span data-ttu-id="ecb19-221">Typ `T` má následující operátory, kde `B` je typ, který lze použít v `Boolean` výraz.</span><span class="sxs-lookup"><span data-stu-id="ecb19-221">A type `T` that has the following operators, where `B` is a type that can be used in a `Boolean` expression.</span></span>  
  
     `Public Shared Operator >= (op1 As T, op2 As T) As B`  
  
     `Public Shared Operator <= (op1 As T, op2 As T) As B`  
  
     `Public Shared Operator - (op1 As T, op2 As T) As T`  
  
     `Public Shared Operator + (op1 As T, op2 As T) As T`  
  
 <span data-ttu-id="ecb19-222">Volitelně můžete zadat `counter` proměnné v `Next` příkaz.</span><span class="sxs-lookup"><span data-stu-id="ecb19-222">You can optionally specify the `counter` variable in the `Next` statement.</span></span> <span data-ttu-id="ecb19-223">Tuto syntaxi zlepšuje čitelnost vašeho programu, zejména v případě, že budete mít člověk vnořené `For` smyčky.</span><span class="sxs-lookup"><span data-stu-id="ecb19-223">This syntax improves the readability of your program, especially if you have nested `For` loops.</span></span> <span data-ttu-id="ecb19-224">Musíte zadat proměnné, která se zobrazí v odpovídající `For` příkaz.</span><span class="sxs-lookup"><span data-stu-id="ecb19-224">You must specify the variable that appears in the corresponding `For` statement.</span></span>  
  
 <span data-ttu-id="ecb19-225">`start`, `end`, A `step` výrazy lze vyhodnotit na datový typ, který rozšiřuje typu `counter`.</span><span class="sxs-lookup"><span data-stu-id="ecb19-225">The `start`, `end`, and `step` expressions can evaluate to any data type that widens to the type of `counter`.</span></span> <span data-ttu-id="ecb19-226">Pokud používáte uživatelsky definovaný typ. pro `counter`, možná budete muset definovat `CType` operátor převodu převést typy `start`, `end`, nebo `step` typu `counter`.</span><span class="sxs-lookup"><span data-stu-id="ecb19-226">If you use a user-defined type for `counter`, you might have to define the `CType` conversion operator to convert the types of `start`, `end`, or `step` to the type of `counter`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ecb19-227">Příklad</span><span class="sxs-lookup"><span data-stu-id="ecb19-227">Example</span></span>  
 <span data-ttu-id="ecb19-228">Následující příklad odebere všechny elementy obecné seznamu.</span><span class="sxs-lookup"><span data-stu-id="ecb19-228">The following example removes all elements from a generic list.</span></span> <span data-ttu-id="ecb19-229">Místo [pro každou... Další příkaz](../../../visual-basic/language-reference/statements/for-each-next-statement.md), příklad ukazuje `For`... `Next` příkaz, který iteruje v sestupném pořadí.</span><span class="sxs-lookup"><span data-stu-id="ecb19-229">Instead of a [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md), the example shows a `For`...`Next` statement that iterates in descending order.</span></span> <span data-ttu-id="ecb19-230">Tento příklad používá tato technika, protože `removeAt` metoda způsobí, že prvky po odebrané elementu, který chcete mít nižší hodnotu indexu.</span><span class="sxs-lookup"><span data-stu-id="ecb19-230">The example uses this technique because the `removeAt` method causes elements after the removed element to have a lower index value.</span></span>  
  
 [!code-vb[VbVbalrStatements#114](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_5.vb)]  
  
## <a name="example"></a><span data-ttu-id="ecb19-231">Příklad</span><span class="sxs-lookup"><span data-stu-id="ecb19-231">Example</span></span>  
 <span data-ttu-id="ecb19-232">V následujícím příkladu prochází výčet, který je deklarovaný s použitím [Enum – příkaz](../../../visual-basic/language-reference/statements/enum-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ecb19-232">The following example iterates through an enumeration that's declared by using an [Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md).</span></span>  
  
 [!code-vb[VbVbalrStatements#116](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_6.vb)]  
  
## <a name="example"></a><span data-ttu-id="ecb19-233">Příklad</span><span class="sxs-lookup"><span data-stu-id="ecb19-233">Example</span></span>  
 <span data-ttu-id="ecb19-234">V následujícím příkladu příkaz parametry použití třídy, která má přetížení operátoru pro `+`, `-`, `>=`, a `<=` operátory.</span><span class="sxs-lookup"><span data-stu-id="ecb19-234">In the following example, the statement parameters use a class that has operator overloads for the `+`, `-`, `>=`, and `<=` operators.</span></span>  
  
 [!code-vb[VbVbalrStatements#117](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_7.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="ecb19-235">Viz také</span><span class="sxs-lookup"><span data-stu-id="ecb19-235">See Also</span></span>  
 <xref:System.Collections.Generic.List%601>  
 [<span data-ttu-id="ecb19-236">Struktury smyčky</span><span class="sxs-lookup"><span data-stu-id="ecb19-236">Loop Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [<span data-ttu-id="ecb19-237">Chvíli... End While – příkaz</span><span class="sxs-lookup"><span data-stu-id="ecb19-237">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)  
 [<span data-ttu-id="ecb19-238">Provést... Příkaz smyčky</span><span class="sxs-lookup"><span data-stu-id="ecb19-238">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)  
 [<span data-ttu-id="ecb19-239">Vnořené řídicí struktury</span><span class="sxs-lookup"><span data-stu-id="ecb19-239">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [<span data-ttu-id="ecb19-240">Exit – příkaz</span><span class="sxs-lookup"><span data-stu-id="ecb19-240">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)  
 [<span data-ttu-id="ecb19-241">Kolekce</span><span class="sxs-lookup"><span data-stu-id="ecb19-241">Collections</span></span>](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b)
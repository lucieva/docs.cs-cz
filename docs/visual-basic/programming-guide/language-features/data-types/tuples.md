---
title: "Řazené kolekce členů v jazyce Visual Basic"
ms.custom: 
ms.date: 04/23/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords: tuples [Visual Basic]
ms.assetid: 3e66cd1b-3432-4e1d-8c37-5ebacae8f53f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: be50b22e9acca9ff8cfbde798d78869ee1c72634
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="tuples-visual-basic"></a><span data-ttu-id="fbc26-102">Řazené kolekce členů (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fbc26-102">Tuples (Visual Basic)</span></span>

<span data-ttu-id="fbc26-103">Počínaje 2017 Visual Basic, jazyka Visual Basic má integrovanou podporu pro řazené kolekce členů, která umožňuje vytváření řazených kolekcí členů a přístup k elementům jednodušší řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="fbc26-103">Starting with Visual Basic 2017, the Visual Basic language offers built-in support for tuples that makes creating tuples and accessing the elements of tuples easier.</span></span> <span data-ttu-id="fbc26-104">Řazené kolekce členů je šedé – datová struktura, která má specifické číslo a pořadí hodnot.</span><span class="sxs-lookup"><span data-stu-id="fbc26-104">A tuple is a light-weight data structure that has a specific number and sequence of values.</span></span> <span data-ttu-id="fbc26-105">Pokud instanci můžete vytvořit řazenou kolekci členů, můžete definovat číslo a datový typ jednotlivých hodnota (nebo element).</span><span class="sxs-lookup"><span data-stu-id="fbc26-105">When you instantiate the tuple, you define the number and the data type of each value (or element).</span></span> <span data-ttu-id="fbc26-106">Například 2 řazené kolekce členů (nebo dvojici) má dva elementy.</span><span class="sxs-lookup"><span data-stu-id="fbc26-106">For example, a 2-tuple (or pair) has two elements.</span></span> <span data-ttu-id="fbc26-107">Může být první `Boolean` hodnotu, zatímco druhý `String`.</span><span class="sxs-lookup"><span data-stu-id="fbc26-107">The first might be a `Boolean` value, while the second is a `String`.</span></span> <span data-ttu-id="fbc26-108">Protože řazených kolekcí členů usnadňují ukládat víc hodnot v jednom objektu, se často používají jako lehký způsob, jak vrátit více hodnot z metody.</span><span class="sxs-lookup"><span data-stu-id="fbc26-108">Because tuples make it easy to store multiple values in a single object, they are often used as a lightweight way to return multiple values from a method.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fbc26-109">Vyžaduje podporu řazené kolekce členů <xref:System.ValueTuple> typu.</span><span class="sxs-lookup"><span data-stu-id="fbc26-109">Tuple support requires the <xref:System.ValueTuple> type.</span></span> <span data-ttu-id="fbc26-110">Pokud není nainstalovaná rozhraní .NET Framework 4.7, je nutné přidat balíček NuGet `System.ValueTuple`, která je k dispozici v galerii NuGet.</span><span class="sxs-lookup"><span data-stu-id="fbc26-110">If the .NET Framework 4.7 is not installed, you must add the NuGet package `System.ValueTuple`, which is available on the NuGet Gallery.</span></span> <span data-ttu-id="fbc26-111">Bez tohoto balíčku může se zobrazit chyba kompilace podobná "Předdefinované type 'ValueTuple(Of,,,)' není definované nebo importovat."</span><span class="sxs-lookup"><span data-stu-id="fbc26-111">Without this package, you may get a compilation error similar to, "Predefined type 'ValueTuple(Of,,,)' is not defined or imported."</span></span>

## <a name="instantiating-and-using-a-tuple"></a><span data-ttu-id="fbc26-112">Vytváření instancí a použití řazené kolekce členů</span><span class="sxs-lookup"><span data-stu-id="fbc26-112">Instantiating and using a tuple</span></span>

<span data-ttu-id="fbc26-113">Řazené kolekce členů instance uzavřením závorkách zasílání rychlých zpráv hodnot oddělených čárkami.</span><span class="sxs-lookup"><span data-stu-id="fbc26-113">You instantiate a tuple by enclosing its comma-delimited values im parentheses.</span></span> <span data-ttu-id="fbc26-114">Každý z těchto hodnot se pak stane pole řazenou kolekci členů.</span><span class="sxs-lookup"><span data-stu-id="fbc26-114">Each of those values then becomes a field of the tuple.</span></span> <span data-ttu-id="fbc26-115">Například následující kód definuje triple (nebo 3 řazené kolekce členů) `Date` jako svou první hodnotu `String` jako jeho sekundu a `Boolean` jako jeho třetí.</span><span class="sxs-lookup"><span data-stu-id="fbc26-115">For example, the following code defines a triple (or 3-tuple) with a `Date` as its first value, a `String` as its second, and a `Boolean` as its third.</span></span>

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#1)]

<span data-ttu-id="fbc26-116">Ve výchozím nastavení, název každého pole v řazené kolekce členů se skládá z řetězce `Item` společně s tohoto pole na základě jedné pozice v řazené kolekci členů.</span><span class="sxs-lookup"><span data-stu-id="fbc26-116">By default, the name of each field in a tuple consists of the string `Item` along with the field's one-based position in the tuple.</span></span> <span data-ttu-id="fbc26-117">Pro tento 3-řazené kolekce členů `Date` pole je `Item1`, `String` pole je `Item2`a `Boolean` pole je `Item3`.</span><span class="sxs-lookup"><span data-stu-id="fbc26-117">For this 3-tuple, the `Date` field is `Item1`, the `String` field is `Item2`, and the `Boolean` field is `Item3`.</span></span> <span data-ttu-id="fbc26-118">Tento příklad zobrazuje hodnoty polí řazené kolekce členů instanci v předchozím řádku kódu</span><span class="sxs-lookup"><span data-stu-id="fbc26-118">The following example displays the values of fields of the tuple instantiated in the previous line of code</span></span>

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#2)]

<span data-ttu-id="fbc26-119">Čtení a zápis; jsou tato pole řazené kolekce členů jazyka Visual Basic poté, co jste instanci řazené kolekce členů, můžete její hodnoty upravit.</span><span class="sxs-lookup"><span data-stu-id="fbc26-119">The fields of a Visual Basic tuple are read-write; after you've instantiated a tuple, you can modify its values.</span></span> <span data-ttu-id="fbc26-120">Následující příklad změní dvě ze tří polí řazené kolekce členů vytvořili v předchozím příkladu a zobrazí výsledek.</span><span class="sxs-lookup"><span data-stu-id="fbc26-120">The following example modifies two of the three fields of the tuple created in the previous example and displays the result.</span></span>

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#3)]

## <a name="instantiating-and-using-a-named-tuple"></a><span data-ttu-id="fbc26-121">Vytváření instancí a použití pojmenovaného řazené kolekce členů</span><span class="sxs-lookup"><span data-stu-id="fbc26-121">Instantiating and using a named tuple</span></span>

<span data-ttu-id="fbc26-122">Místo použití výchozí názvy polí řazené kolekce členů, můžete vytvořit instanci *s názvem řazené kolekce členů* přiřazením vlastní názvy elementů řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="fbc26-122">Rather than using default names for a tuple's fields, you can instantiate a *named tuple* by assigning your own names to the tuple's elements.</span></span> <span data-ttu-id="fbc26-123">Pole řazené kolekce členů lze přistupovat pomocí jejich přiřazené názvy *nebo* jejich výchozí názvy.</span><span class="sxs-lookup"><span data-stu-id="fbc26-123">The tuple's fields can then be accessed by their assigned names *or* by their default names.</span></span> <span data-ttu-id="fbc26-124">Následující příklad vytvoří stejné 3-n-tice jako dříve, s tím rozdílem, že ji explicitně názvy první pole `EventDate`, druhý `Name`a třetí `IsHoliday`.</span><span class="sxs-lookup"><span data-stu-id="fbc26-124">The following example instantiates the same 3-tuple as previously, except that it explicitly names the first field `EventDate`, the second `Name`, and the third `IsHoliday`.</span></span> <span data-ttu-id="fbc26-125">Pak zobrazí hodnoty polí, upraví je a znovu zobrazuje hodnoty polí.</span><span class="sxs-lookup"><span data-stu-id="fbc26-125">It then displays the field values, modifies them, and displays the field values again.</span></span>

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#4)]

## <a name="tuples-versus-structures"></a><span data-ttu-id="fbc26-126">Řazené kolekce členů a struktury</span><span class="sxs-lookup"><span data-stu-id="fbc26-126">Tuples versus structures</span></span>

<span data-ttu-id="fbc26-127">Visual Basic řazené kolekce členů je typ hodnoty, která je instance jednoho z **System.ValueTuple** obecné typy.</span><span class="sxs-lookup"><span data-stu-id="fbc26-127">A Visual Basic tuple is a value type that is an instance of one of the a **System.ValueTuple** generic types.</span></span> <span data-ttu-id="fbc26-128">Například `holiday` řazené kolekce členů definované v předchozím příkladu představuje instanci <xref:System.ValueTuple%603> struktura.</span><span class="sxs-lookup"><span data-stu-id="fbc26-128">For example, the `holiday` tuple defined in the previous example is an instance of the <xref:System.ValueTuple%603> structure.</span></span> <span data-ttu-id="fbc26-129">Je určený jako lightweight kontejner pro data.</span><span class="sxs-lookup"><span data-stu-id="fbc26-129">It is designed to be a lightweight container for data.</span></span> <span data-ttu-id="fbc26-130">Vzhledem k tomu, že řazenou kolekci členů cílem je usnadnit práci pro vytvoření objektu s více datovými položkami, chybí některé funkce, které by mohly mít do vlastní struktury.</span><span class="sxs-lookup"><span data-stu-id="fbc26-130">Since the tuple aims to make it easy to create an object with multiple data items, it lacks some of the features that a custom structure might have.</span></span> <span data-ttu-id="fbc26-131">Mezi ně patří:</span><span class="sxs-lookup"><span data-stu-id="fbc26-131">These include:</span></span>

- <span data-ttu-id="fbc26-132">Členy zákazníka.</span><span class="sxs-lookup"><span data-stu-id="fbc26-132">Customer members.</span></span> <span data-ttu-id="fbc26-133">Nelze definovat vlastní vlastnosti, metody nebo události pro řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="fbc26-133">You cannot define your own properties, methods, or events for a tuple.</span></span>

- <span data-ttu-id="fbc26-134">Ověření.</span><span class="sxs-lookup"><span data-stu-id="fbc26-134">Validation.</span></span> <span data-ttu-id="fbc26-135">Nelze ověřit data přiřazené pole.</span><span class="sxs-lookup"><span data-stu-id="fbc26-135">You cannot validate the data assigned to fields.</span></span>

- <span data-ttu-id="fbc26-136">Neměnitelnosti.</span><span class="sxs-lookup"><span data-stu-id="fbc26-136">Immutability.</span></span> <span data-ttu-id="fbc26-137">Měnitelný jsou řazené kolekce členů jazyka Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="fbc26-137">Visual Basic tuples are mutable.</span></span> <span data-ttu-id="fbc26-138">Naproti tomu do vlastní struktury umožňuje určit informaci, jestli instance měnitelný nebo neměnné.</span><span class="sxs-lookup"><span data-stu-id="fbc26-138">In contrast, a custom structure allows you to control whether an instance is mutable or immutable.</span></span>

<span data-ttu-id="fbc26-139">Pokud vlastní členy, vlastnost a pole ověření nebo neměnitelnosti jsou důležité, abyste používali Visual Basicu [struktura](../../../language-reference/statements/structure-statement.md) příkaz k definování typu vlastní hodnoty.</span><span class="sxs-lookup"><span data-stu-id="fbc26-139">If custom members, property and field validation, or immutability are important, you should use the Visual Basic [Structure](../../../language-reference/statements/structure-statement.md) statement to define a custom value type.</span></span>

<span data-ttu-id="fbc26-140">Visual Basic řazené kolekce členů dědění členů jeho **ValueTuple** typu.</span><span class="sxs-lookup"><span data-stu-id="fbc26-140">A Visual Basic tuple does inherit the members of its **ValueTuple** type.</span></span> <span data-ttu-id="fbc26-141">Kromě jeho polí mezi ně patří následující metody:</span><span class="sxs-lookup"><span data-stu-id="fbc26-141">In addition to its fields, these include the following methods:</span></span>

| <span data-ttu-id="fbc26-142">Člen</span><span class="sxs-lookup"><span data-stu-id="fbc26-142">Member</span></span> | <span data-ttu-id="fbc26-143">Popis</span><span class="sxs-lookup"><span data-stu-id="fbc26-143">Description</span></span> |
| ---|---|
| <span data-ttu-id="fbc26-144">CompareTo</span><span class="sxs-lookup"><span data-stu-id="fbc26-144">CompareTo</span></span> | <span data-ttu-id="fbc26-145">Porovná aktuální řazenou kolekci členů do jiné řazené kolekce členů s stejný počet elementů.</span><span class="sxs-lookup"><span data-stu-id="fbc26-145">Compares the current tuple to another tuple with the same number of elements.</span></span> |
| <span data-ttu-id="fbc26-146">Rovná se</span><span class="sxs-lookup"><span data-stu-id="fbc26-146">Equals</span></span> | <span data-ttu-id="fbc26-147">Určuje, zda aktuální řazenou kolekci členů je rovno jiné řazené kolekce členů nebo objekt.</span><span class="sxs-lookup"><span data-stu-id="fbc26-147">Determines whether the current tuple is equal to another tuple or object.</span></span> |
| <span data-ttu-id="fbc26-148">GetHashCode</span><span class="sxs-lookup"><span data-stu-id="fbc26-148">GetHashCode</span></span> | <span data-ttu-id="fbc26-149">Vypočítá kód hash pro aktuální instanci.</span><span class="sxs-lookup"><span data-stu-id="fbc26-149">Calculates the hash code for the current instance.</span></span> |
| <span data-ttu-id="fbc26-150">ToString</span><span class="sxs-lookup"><span data-stu-id="fbc26-150">ToString</span></span> | <span data-ttu-id="fbc26-151">Vrátí řetězcovou reprezentaci této řazené kolekce členů, která má tvar `(Item1, Item2...)`, kde `Item1` a `Item2` představují hodnoty polí řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="fbc26-151">Returns the string representation of this tuple, which takes the form `(Item1, Item2...)`, where `Item1` and `Item2` represent the values of the tuple's fields.</span></span> |

<span data-ttu-id="fbc26-152">Kromě toho **ValueTuple** typy implementovat <xref:System.Collections.IStructuralComparable> a <xref:System.Collections.IStructuralEquatable> rozhraní, které umožňují definovat komparátory zákazníka.</span><span class="sxs-lookup"><span data-stu-id="fbc26-152">In addition, the **ValueTuple** types implement <xref:System.Collections.IStructuralComparable> and <xref:System.Collections.IStructuralEquatable> interfaces, which allow you to define customer comparers.</span></span>

## <a name="assignment-and-tuples"></a><span data-ttu-id="fbc26-153">Přiřazení a řazených kolekcí členů</span><span class="sxs-lookup"><span data-stu-id="fbc26-153">Assignment and tuples</span></span>

<span data-ttu-id="fbc26-154">Visual Basic podporuje přiřazení mezi typy řazené kolekce členů, které mají stejný počet polí.</span><span class="sxs-lookup"><span data-stu-id="fbc26-154">Visual Basic supports assignment between tuple types that have the same number of fields.</span></span> <span data-ttu-id="fbc26-155">Typy polí lze převést, pokud platí jedna z následujících akcí:</span><span class="sxs-lookup"><span data-stu-id="fbc26-155">The field types can be converted if one of the following is true:</span></span>

- <span data-ttu-id="fbc26-156">Zdrojové a cílové pole jsou stejného typu.</span><span class="sxs-lookup"><span data-stu-id="fbc26-156">The source and target field are of the same type.</span></span>

- <span data-ttu-id="fbc26-157">Rozšiřující (nebo implicitní) převodu typ zdroje pro cílový typ je definována.</span><span class="sxs-lookup"><span data-stu-id="fbc26-157">A widening (or implicit) conversion of the source type to the target type is defined.</span></span> 

- <span data-ttu-id="fbc26-158">`Option Strict`je `On`, a narrowing (nebo explicitní) převodu typ zdroje pro cílový typ je definovaná.</span><span class="sxs-lookup"><span data-stu-id="fbc26-158">`Option Strict` is `On`, and a narrowing (or explicit) conversion of the source type to the target type is defined.</span></span> <span data-ttu-id="fbc26-159">Tento převod může vyvolat výjimku, pokud je zdroj hodnota mimo rozsah typu cíle.</span><span class="sxs-lookup"><span data-stu-id="fbc26-159">This conversion can throw an exception if the source value is outside the range of the target type.</span></span>

<span data-ttu-id="fbc26-160">Jiné převody nejsou považovány za přiřazení.</span><span class="sxs-lookup"><span data-stu-id="fbc26-160">Other conversions are not considered for assignments.</span></span> <span data-ttu-id="fbc26-161">Podívejme se na druhy přiřazení, které jsou povoleny mezi typy řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="fbc26-161">Let's look at the kinds of assignments that are allowed between tuple types.</span></span>

<span data-ttu-id="fbc26-162">Vezměte v úvahu tyto proměnné použít v následujících příkladech:</span><span class="sxs-lookup"><span data-stu-id="fbc26-162">Consider these variables used in the following examples:</span></span>

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#1)]

<span data-ttu-id="fbc26-163">První dvě proměnné, `unnamed` a `anonymous`, nemají sémantického názvy zadaná pro pole.</span><span class="sxs-lookup"><span data-stu-id="fbc26-163">The first two variables, `unnamed` and `anonymous`, do not have semantic names provided for the fields.</span></span> <span data-ttu-id="fbc26-164">Jejich názvy polí jsou výchozí `Item1` a `Item2`.</span><span class="sxs-lookup"><span data-stu-id="fbc26-164">Their field names are the default `Item1` and `Item2`.</span></span> <span data-ttu-id="fbc26-165">Poslední dvě proměnné, `named` a `differentName` mít názvy sémantického pole.</span><span class="sxs-lookup"><span data-stu-id="fbc26-165">The last two variables, `named` and `differentName` have semantic field names.</span></span> <span data-ttu-id="fbc26-166">Všimněte si, že tyto dvě řazené kolekce členů mají odlišné názvy polí.</span><span class="sxs-lookup"><span data-stu-id="fbc26-166">Note that these two tuples have different names for the fields.</span></span>

<span data-ttu-id="fbc26-167">Všechny čtyři tyto řazené kolekce členů mít stejný počet polí (označované jako "Arita") a typy těchto polí jsou identické.</span><span class="sxs-lookup"><span data-stu-id="fbc26-167">All four of these tuples have the same number of fields (referred to as 'arity'), and the types of those fields are identical.</span></span> <span data-ttu-id="fbc26-168">Proto všechny tyto přiřazení fungovat:</span><span class="sxs-lookup"><span data-stu-id="fbc26-168">Therefore, all of these assignments work:</span></span>

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#2)]

<span data-ttu-id="fbc26-169">Všimněte si, že nejsou přiřazeny názvy řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="fbc26-169">Notice that the names of the tuples are not assigned.</span></span> <span data-ttu-id="fbc26-170">Hodnoty polí jsou přiřazeny následující pořadí polí v řazené kolekci členů.</span><span class="sxs-lookup"><span data-stu-id="fbc26-170">The values of the fields are assigned following the order of the fields in the tuple.</span></span>

<span data-ttu-id="fbc26-171">Všimněte si, že jsme můžete přiřadit `named` řazené kolekce členů k `conversion` řazené kolekce členů, i když první pole `named` je `Integer`a první pole `conversion` je `Long`.</span><span class="sxs-lookup"><span data-stu-id="fbc26-171">Finally, notice that we can assign the `named` tuple to the `conversion` tuple, even though the first field of `named` is an `Integer`, and the first field of `conversion` is a `Long`.</span></span> <span data-ttu-id="fbc26-172">Toto přiřazení se podaří, protože převod `Integer` k `Long` je rozšiřující převod.</span><span class="sxs-lookup"><span data-stu-id="fbc26-172">This assignment succeeds because converting an `Integer` to a `Long` is a widening conversion.</span></span>

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#3)]

<span data-ttu-id="fbc26-173">Řazené kolekce členů s odlišný počet polí nejsou přiřadit:</span><span class="sxs-lookup"><span data-stu-id="fbc26-173">Tuples with different numbers of fields are not assignable:</span></span>

```vb
' Does not compile.
' VB30311: Value of type '(Integer, Integer, Integer)' cannot be converted
'          to '(Answer As Integer, Message As String)'
var differentShape = (1, 2, 3)
named = differentShape
```

## <a name="tuples-as-method-return-values"></a><span data-ttu-id="fbc26-174">Řazené kolekce členů jako metodu návratové hodnoty</span><span class="sxs-lookup"><span data-stu-id="fbc26-174">Tuples as method return values</span></span>

<span data-ttu-id="fbc26-175">Metoda může vrátit pouze jednu hodnotu.</span><span class="sxs-lookup"><span data-stu-id="fbc26-175">A method can return only a single value.</span></span> <span data-ttu-id="fbc26-176">Často ale chcete volání metoda vrátí více hodnot.</span><span class="sxs-lookup"><span data-stu-id="fbc26-176">Frequently, though, you'd like a method call to return multiple values.</span></span> <span data-ttu-id="fbc26-177">Toto omezení obejít několika způsoby:</span><span class="sxs-lookup"><span data-stu-id="fbc26-177">There are several ways to work around this limitation:</span></span>

- <span data-ttu-id="fbc26-178">Můžete vytvořit vlastní třídu nebo strukturu, jehož vlastnosti nebo pole představují hodnoty vrácené metodou.</span><span class="sxs-lookup"><span data-stu-id="fbc26-178">You can create a custom class or structure whose properties or fields represent values returned by the method.</span></span> <span data-ttu-id="fbc26-179">Proto je těžké řešení; To vyžaduje, aby definujete vlastní typ, jehož jediným účelem je načítání hodnot z volání metody.</span><span class="sxs-lookup"><span data-stu-id="fbc26-179">Thus is a heavyweight solution; it requires that you define a custom type whose only purpose is to retrieve values from a method call.</span></span>

- <span data-ttu-id="fbc26-180">Můžete vrátit jednu hodnotu z metody a vrátit zbývající hodnoty předáním odkazu na metodu.</span><span class="sxs-lookup"><span data-stu-id="fbc26-180">You can return a single value from the method, and return the remaining values by passing them by reference to the method.</span></span> <span data-ttu-id="fbc26-181">To zahrnuje režií při vytváření instance proměnné a rizika nechtěném přepsání hodnotu proměnné, kterou předáte odkazem.</span><span class="sxs-lookup"><span data-stu-id="fbc26-181">This involves the overhead of instantiating a variable and risks inadvertently overwriting the value of the variable that you pass by reference.</span></span>

- <span data-ttu-id="fbc26-182">Můžete použít řazenou kolekci členů, která poskytuje jednoduché řešení pro načítání více vrácených hodnot.</span><span class="sxs-lookup"><span data-stu-id="fbc26-182">You can use a tuple, which provides a lightweight solution to retrieving multiple return values.</span></span>

<span data-ttu-id="fbc26-183">Například **TryParse** metody v rozhraní .NET vrátit `Boolean` hodnotu, která určuje, zda analýza operace byla úspěšně dokončena.</span><span class="sxs-lookup"><span data-stu-id="fbc26-183">For example, the **TryParse** methods in .NET return a `Boolean` value that indicates whether the parsing operation succeeded.</span></span> <span data-ttu-id="fbc26-184">Výsledek analýzy operace se vrátí do proměnné předaná odkazu na metodu.</span><span class="sxs-lookup"><span data-stu-id="fbc26-184">The result of the parsing operation is returned in a variable passed by reference to the method.</span></span> <span data-ttu-id="fbc26-185">Za normálních okolností volání metoda analýzy, jako <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> vypadá podobně jako následující:</span><span class="sxs-lookup"><span data-stu-id="fbc26-185">Normally, a call to the a parsing method such as <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> looks like the following:</span></span>

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#1)]

<span data-ttu-id="fbc26-186">Se jsme zabalení volání vrací řazenou kolekci členů z analýzy operace <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> metoda vlastní metoda.</span><span class="sxs-lookup"><span data-stu-id="fbc26-186">We can return a tuple from the parsing operation if we wrap the call to the <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> method in our own method.</span></span> <span data-ttu-id="fbc26-187">V následujícím příkladu `NumericLibrary.ParseInteger` volání <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> metodu a vrátí pojmenované řazené kolekce členů s dva elementy.</span><span class="sxs-lookup"><span data-stu-id="fbc26-187">In the following example, `NumericLibrary.ParseInteger` calls the <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> method and returns a named tuple with two elements.</span></span> 

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#2)]

<span data-ttu-id="fbc26-188">Pak můžete volat metodu s kódem podobně jako tento:</span><span class="sxs-lookup"><span data-stu-id="fbc26-188">You can then call the method with code like the following:</span></span>

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#3)]

## <a name="visual-basic-tuples-and-tuples-in-the-net-framework"></a><span data-ttu-id="fbc26-189">Řazené kolekce členů jazyka Visual Basic a řazených kolekcí členů v rozhraní .NET Framework</span><span class="sxs-lookup"><span data-stu-id="fbc26-189">Visual Basic tuples and tuples in the .NET Framework</span></span>

<span data-ttu-id="fbc26-190">Visual Basic řazené kolekce členů je instance jednoho **System.ValueTuple** obecné typy, které byly zavedeny v 4.7 rozhraní .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fbc26-190">A Visual Basic tuple is an instance of one of the **System.ValueTuple** generic types, which were introduced in the .NET Framework 4.7.</span></span> <span data-ttu-id="fbc26-191">Rozhraní .NET Framework také obsahuje sadu obecného **System.Tuple** třídy.</span><span class="sxs-lookup"><span data-stu-id="fbc26-191">The .NET Framework also includes a set of generic **System.Tuple** classes.</span></span> <span data-ttu-id="fbc26-192">Tyto třídy, ale liší od řazených kolekcí členů jazyka Visual Basic a **System.ValueTuple** obecné typy v mnoha různými způsoby:</span><span class="sxs-lookup"><span data-stu-id="fbc26-192">These classes, however, differ from Visual Basic tuples and the **System.ValueTuple** generic types in a number of ways:</span></span>

- <span data-ttu-id="fbc26-193">Elementy **řazené kolekce členů** třídy jsou vlastnosti s názvem `Item1`, `Item2`a tak dále.</span><span class="sxs-lookup"><span data-stu-id="fbc26-193">The elements of the **Tuple** classes are properties named `Item1`, `Item2`, and so on.</span></span> <span data-ttu-id="fbc26-194">V jazyce Visual Basic řazených kolekcí členů a **ValueTuple** pole jsou typy, elementy řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="fbc26-194">In Visual Basic tuples and the **ValueTuple** types, tuple elements are fields.</span></span>

- <span data-ttu-id="fbc26-195">Nelze přiřadit řádkům elementy **řazené kolekce členů** instance nebo **ValueTuple** instance.</span><span class="sxs-lookup"><span data-stu-id="fbc26-195">You cannot assign meaningful names to the elements of a **Tuple** instance or of a **ValueTuple** instance.</span></span> <span data-ttu-id="fbc26-196">Visual Basic umožňuje přiřadit názvy, které komunikují význam pole.</span><span class="sxs-lookup"><span data-stu-id="fbc26-196">Visual Basic allows you to assign names that communicate the meaning of the fields.</span></span>

- <span data-ttu-id="fbc26-197">Vlastnosti **řazené kolekce členů** instance jsou jen pro čtení, jsou neměnné řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="fbc26-197">The properties of a **Tuple** instance are read-only; the tuples are immutable.</span></span> <span data-ttu-id="fbc26-198">V jazyce Visual Basic řazených kolekcí členů a **ValueTuple** typy, jsou řazené kolekce členů pole pro čtení a zápis; jsou měnitelný řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="fbc26-198">In Visual Basic tuples and the **ValueTuple** types, tuple fields are read-write; the tuples are mutable.</span></span>

- <span data-ttu-id="fbc26-199">Obecná **řazené kolekce členů** typy jsou odkazové typy.</span><span class="sxs-lookup"><span data-stu-id="fbc26-199">The generic **Tuple** types are reference types.</span></span> <span data-ttu-id="fbc26-200">Použití těchto **řazené kolekce členů** typy znamená přidělování objektů.</span><span class="sxs-lookup"><span data-stu-id="fbc26-200">Using these **Tuple** types means allocating objects.</span></span> <span data-ttu-id="fbc26-201">V aktivní cesty to může být měřitelný dopad na výkon vaší aplikace.</span><span class="sxs-lookup"><span data-stu-id="fbc26-201">On hot paths, this can have a measurable impact on your application's performance.</span></span> <span data-ttu-id="fbc26-202">Řazené kolekce členů jazyka Visual Basic a **ValueTuple** typy jsou typy hodnot.</span><span class="sxs-lookup"><span data-stu-id="fbc26-202">Visual Basic tuples and the **ValueTuple** types are value types.</span></span>

<span data-ttu-id="fbc26-203">Rozšiřující metody v <xref:System.TupleExtensions> třída usnadňují převod mezi řazených kolekcí členů jazyka Visual Basic a .NET **řazené kolekce členů** objekty.</span><span class="sxs-lookup"><span data-stu-id="fbc26-203">Extension methods in the <xref:System.TupleExtensions> class make it easy to convert between Visual Basic tuples and .NET **Tuple** objects.</span></span> <span data-ttu-id="fbc26-204">**ToTuple** metoda převede řazené kolekce členů jazyka Visual Basic .NET **řazené kolekce členů** objekt a **ToValueTuple** metoda převede .NET **řazené kolekce členů** objekt řazené kolekce členů jazyka Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="fbc26-204">The **ToTuple** method converts a Visual Basic tuple to a .NET **Tuple** object, and the **ToValueTuple** method converts a .NET **Tuple** object to a Visual Basic tuple.</span></span>

<span data-ttu-id="fbc26-205">Následující příklad vytvoří řazenou kolekci členů, převede ji na .NET **řazené kolekce členů** objekt a převede ji zpět do Visual Basic řazené kolekce členů.</span><span class="sxs-lookup"><span data-stu-id="fbc26-205">The following example creates a tuple, converts it to a .NET **Tuple** object, and converts it back to a Visual Basic tuple.</span></span> <span data-ttu-id="fbc26-206">V příkladu pak porovná tato řazené kolekce členů s původní, abyste zajistili, že jsou stejné.</span><span class="sxs-lookup"><span data-stu-id="fbc26-206">The example then compares this tuple with the original one to ensure that they are equal.</span></span>

[!code-vb[Convert](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple2.vb#1)]

## <a name="see-also"></a><span data-ttu-id="fbc26-207">Viz také</span><span class="sxs-lookup"><span data-stu-id="fbc26-207">See also</span></span>

[<span data-ttu-id="fbc26-208">Referenční dokumentace jazyka Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fbc26-208">Visual Basic Language Reference</span></span>](index.md)  
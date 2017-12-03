---
title: "Deconstructing řazených kolekcí členů a dalších typů"
description: "Naučte se deconstruct řazených kolekcí členů a dalších typů."
keywords: "Rozhraní .NET, rozhraní .NET core, C#"
author: rpetrusha
ms-author: ronpet
ms.date: 07/18/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 0b0c4b0f-4a47-4f66-9b8e-f5c63b195960
ms.openlocfilehash: e626eeb1f3de2716e1ffe4fcbec1c16558e5bf0e
ms.sourcegitcommit: a3ba258f7a8cab5c6d19a3743dd95e904ecebc44
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/27/2017
---
# <a name="deconstructing-tuples-and-other-types"></a><span data-ttu-id="94833-104">Deconstructing řazených kolekcí členů a dalších typů</span><span class="sxs-lookup"><span data-stu-id="94833-104">Deconstructing tuples and other types</span></span> #

<span data-ttu-id="94833-105">Řazené kolekce členů poskytuje šedé – způsob, jak načíst více hodnot z volání metody.</span><span class="sxs-lookup"><span data-stu-id="94833-105">A tuple provides a light-weight way to retrieve multiple values from a method call.</span></span> <span data-ttu-id="94833-106">Ale po načtete řazenou kolekci členů, je potřeba zpracovat jeho jednotlivé prvky.</span><span class="sxs-lookup"><span data-stu-id="94833-106">But once you retrieve the tuple, you have to handle its individual elements.</span></span> <span data-ttu-id="94833-107">To na základě elementu pomocí elementu je náročnější, jak ukazuje následující příklad.</span><span class="sxs-lookup"><span data-stu-id="94833-107">Doing this on an element-by-element basis is cumbersome, as the following example shows.</span></span> <span data-ttu-id="94833-108">`QueryCityData` , Metoda vrátí 3-řazené kolekce členů, každý z jeho elementy je přiřazený k proměnné v rámci samostatné operace.</span><span class="sxs-lookup"><span data-stu-id="94833-108">The `QueryCityData` method returns a 3-tuple, and each of its elements is assigned to a variable in a separate operation.</span></span>

[!code-csharp[WithoutDeconstruction](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/deconstruct-tuple1.cs)]

<span data-ttu-id="94833-109">Načítání více hodnot pro pole a vlastnosti z objektu může být stejně náročná: je potřeba přiřadit hodnotu pole nebo vlastnost proměnné na základě člena člena.</span><span class="sxs-lookup"><span data-stu-id="94833-109">Retrieving multiple field and property values from an object can be equally cumbersome: you have to assign a field or property value to a variable on a member-by-member basis.</span></span> 

<span data-ttu-id="94833-110">Od verze jazyka C# 7, můžete načíst více prvků z řazené kolekce členů nebo načíst více pole, vlastnosti a počítaných hodnot z objektu v jedné *deconstruct* operaci.</span><span class="sxs-lookup"><span data-stu-id="94833-110">Starting with C# 7, you can retrieve multiple elements from a tuple or retrieve multiple field, property, and computed values from an object in a single *deconstruct* operation.</span></span> <span data-ttu-id="94833-111">Pokud jste deconstruct řazené kolekce členů, přiřadíte jeho elementy jednotlivé proměnné.</span><span class="sxs-lookup"><span data-stu-id="94833-111">When you deconstruct a tuple, you assign its elements to individual variables.</span></span> <span data-ttu-id="94833-112">Pokud jste deconstruct objekt, přiřadíte vybrané hodnoty jednotlivých proměnné.</span><span class="sxs-lookup"><span data-stu-id="94833-112">When you deconstruct an object, you assign selected values to individual variables.</span></span> 

## <a name="deconstructing-a-tuple"></a><span data-ttu-id="94833-113">Deconstructing řazené kolekce členů</span><span class="sxs-lookup"><span data-stu-id="94833-113">Deconstructing a tuple</span></span>

<span data-ttu-id="94833-114">C# – funkce integrovanou podporu pro deconstructing řazené kolekce členů, který vám umožňuje rozbalit všechny položky v řazené kolekce členů v rámci jedné operace.</span><span class="sxs-lookup"><span data-stu-id="94833-114">C# features built-in support for deconstructing tuples, which lets you unpackage all the items in a tuple in a single operation.</span></span> <span data-ttu-id="94833-115">Obecná syntaxe deconstructing řazené kolekce členů je podobná syntaxi pro definování jednu: uzavřete proměnné, do kterých má být přiřazena v závorkách v levé části příkazu přiřazení každý prvek.</span><span class="sxs-lookup"><span data-stu-id="94833-115">The general syntax for deconstructing a tuple is similar to the syntax for defining one: you enclose the variables to which each element is to be assigned in parentheses in the left side of an assignment statement.</span></span> <span data-ttu-id="94833-116">Například následující příkaz přiřadí elementy 4-řazené kolekce členů čtyři samostatné proměnné:</span><span class="sxs-lookup"><span data-stu-id="94833-116">For example, the following statement assigns the elements of a 4-tuple to four separate variables:</span></span>

```csharp
var (name, address, city, zip) = contact.GetAddressInfo();
```

<span data-ttu-id="94833-117">Existují tři způsoby, jak deconstruct řazené kolekce členů:</span><span class="sxs-lookup"><span data-stu-id="94833-117">There are three ways to deconstruct a tuple:</span></span>

- <span data-ttu-id="94833-118">Je možné deklarovat explicitně typ každé pole v závorkách.</span><span class="sxs-lookup"><span data-stu-id="94833-118">You can explicitly declare the type of each field inside parentheses.</span></span> <span data-ttu-id="94833-119">Následující příklad používá tento přístup k deconstruct 3 řazené kolekce členů vrácený `QueryCityData` metoda.</span><span class="sxs-lookup"><span data-stu-id="94833-119">The following example uses this approach to deconstruct the 3-tuple returned by the `QueryCityData` method.</span></span>

    [!code-csharp[Deconstruction-Explicit](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/deconstruct-tuple2.cs#1)]

- <span data-ttu-id="94833-120">Můžete použít `var` – klíčové slovo, že C# odvodí typ pro každou proměnnou.</span><span class="sxs-lookup"><span data-stu-id="94833-120">You can use the `var` keyword so that C# infers the type of each variable.</span></span> <span data-ttu-id="94833-121">Umístit `var` – klíčové slovo mimo závorkách.</span><span class="sxs-lookup"><span data-stu-id="94833-121">You place the `var` keyword outside of the parentheses.</span></span> <span data-ttu-id="94833-122">Následující příklad používá odvození typu při deconstructing 3 řazené kolekce členů vrácený `QueryCityData` metoda.</span><span class="sxs-lookup"><span data-stu-id="94833-122">The following example uses type inference when deconstructing the 3-tuple returned by the `QueryCityData` method.</span></span>
 
    [!code-csharp[Deconstruction-Infer](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/deconstruct-tuple3.cs#1)]

    <span data-ttu-id="94833-123">Můžete také `var` – klíčové slovo jednotlivě s některého nebo všech deklarace proměnných v závorkách.</span><span class="sxs-lookup"><span data-stu-id="94833-123">You can also use the `var` keyword individually with any or all of the variable declarations inside the parentheses.</span></span> 

    [!code-csharp[Deconstruction-Infer-Some](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/deconstruct-tuple4.cs#1)]

    <span data-ttu-id="94833-124">Toto je náročná a se nedoporučuje.</span><span class="sxs-lookup"><span data-stu-id="94833-124">This is cumbersome and is not recommended.</span></span>

- <span data-ttu-id="94833-125">Nakonec může deconstruct řazenou kolekci členů do proměnné, které již byl deklarován.</span><span class="sxs-lookup"><span data-stu-id="94833-125">Lastly, you may deconstruct the tuple into variables that have already been declared.</span></span>

    [!code-csharp[Deconstruction-Declared](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/deconstruct-tuple5.cs#1)]

<span data-ttu-id="94833-126">Všimněte si, že i v případě, že každé pole v řazené kolekci členů má stejný typ nelze zadat konkrétní typ mimo závorkách.</span><span class="sxs-lookup"><span data-stu-id="94833-126">Note that you cannot specify a specific type outside the parentheses even if every field in the tuple has the same type.</span></span> <span data-ttu-id="94833-127">To vygeneruje Chyba kompilátoru CS8136, "formuláře 'var (...)' Deconstruction zakáže konkrétního typu pro 'var'.".</span><span class="sxs-lookup"><span data-stu-id="94833-127">This generates compiler error CS8136, "Deconstruction 'var (...)' form disallows a specific type for 'var'.".</span></span>

<span data-ttu-id="94833-128">Všimněte si, že je nutné přiřadit také každý prvek řazenou kolekci členů k proměnné.</span><span class="sxs-lookup"><span data-stu-id="94833-128">Note that you must also assign each element of the tuple to a variable.</span></span> <span data-ttu-id="94833-129">Pokud nezadáte žádné elementy, kompilátor vygeneruje chyba CS8132, "Nelze deconstruct řazená kolekce členů x elementy do proměnné"y"."</span><span class="sxs-lookup"><span data-stu-id="94833-129">If you omit any elements, the compiler generates error CS8132, "Cannot deconstruct a tuple of 'x' elements into 'y' variables."</span></span>

<span data-ttu-id="94833-130">Všimněte si, že není možné kombinovat deklarace a přiřazení do existujících proměnných na levé straně deconstruction.</span><span class="sxs-lookup"><span data-stu-id="94833-130">Note that you cannot mix declarations and assignments to existing variables on the left-hand side of a deconstruction.</span></span> <span data-ttu-id="94833-131">Kompilátor vygeneruje chyba CS8184, "deconstruction nelze kombinovat deklarace a výrazy na levou-stranu-straně."</span><span class="sxs-lookup"><span data-stu-id="94833-131">The compiler generates error CS8184, "a deconstruction cannot mix declarations and expressions on the left-hand-side."</span></span> <span data-ttu-id="94833-132">Když členy obsahovat nově deklarované a existující proměnné.</span><span class="sxs-lookup"><span data-stu-id="94833-132">when the members include newly declared and existing variables.</span></span>

## <a name="deconstructing-tuple-elements-with-discards"></a><span data-ttu-id="94833-133">Deconstructing prvky řazené kolekce členů s zahodí</span><span class="sxs-lookup"><span data-stu-id="94833-133">Deconstructing tuple elements with discards</span></span>

<span data-ttu-id="94833-134">Často při deconstructing řazené kolekce členů, co vás zajímá hodnoty jenom některé prvky.</span><span class="sxs-lookup"><span data-stu-id="94833-134">Often when deconstructing a tuple, you're interested in the values of only some elements.</span></span> <span data-ttu-id="94833-135">Od verze jazyka C# 7, můžete využít výhod podpory jazyka C# na pro *zahodí*, které jsou jen pro zápis proměnné, jejichž hodnoty, které jste se rozhodli ignorovat.</span><span class="sxs-lookup"><span data-stu-id="94833-135">Starting with C# 7, you can take advantage of C#'s support for *discards*, which are write-only variables whose values you've chosen to ignore.</span></span> <span data-ttu-id="94833-136">Zahození je určen znakem podtržítka ("\_") v přiřazení.</span><span class="sxs-lookup"><span data-stu-id="94833-136">A discard is designated by an underscore character ("\_") in an assignment.</span></span> <span data-ttu-id="94833-137">Zahodit tolik hodnoty podle potřeby; všechny jsou reprezentované pomocí jedné zahození `_`.</span><span class="sxs-lookup"><span data-stu-id="94833-137">You can discard as many values as you like; all are represented by the single discard, `_`.</span></span>

<span data-ttu-id="94833-138">Následující příklad ukazuje použití řazené kolekce členů s zahození.</span><span class="sxs-lookup"><span data-stu-id="94833-138">The following example illustrates the use of tuples with discards.</span></span> <span data-ttu-id="94833-139">`QueryCityDataForYears` Metoda vrátí hodnotu 6-řazené kolekce členů s názvem města, jeho oblasti, rok, název města plnění pro tento rok, druhý roku a název města plnění pro tento druhý roku.</span><span class="sxs-lookup"><span data-stu-id="94833-139">The `QueryCityDataForYears` method returns a 6-tuple with the name of a city, its area, a year, the city's population for that year, a second year, and the city's population for that second year.</span></span> <span data-ttu-id="94833-140">Příklad ukazuje změnu v plnění mezi tyto dva roky.</span><span class="sxs-lookup"><span data-stu-id="94833-140">The example shows the change in population between those two years.</span></span> <span data-ttu-id="94833-141">Data k dispozici z řazenou kolekci členů, jsme unconcerned oblasti města a víme název města a kalendářní data v době návrhu.</span><span class="sxs-lookup"><span data-stu-id="94833-141">Of the data available from the tuple, we're unconcerned with the city area, and we know the city name and the two dates at design-time.</span></span> <span data-ttu-id="94833-142">V důsledku toho jsme se pouze zajímá dvě naplnění hodnotami uloženými v řazené kolekci členů a jeho zbývající hodnoty jako zahození dokáže zpracovat.</span><span class="sxs-lookup"><span data-stu-id="94833-142">As a result, we're only interested in the two population values stored in the tuple, and can handle its remaining values as discards.</span></span>  

[!code-csharp[Tuple-discard](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/discard-tuple1.cs)]

### <a name="deconstructing-user-defined-types"></a><span data-ttu-id="94833-143">Deconstructing uživatelem definované typy</span><span class="sxs-lookup"><span data-stu-id="94833-143">Deconstructing user-defined types</span></span>

<span data-ttu-id="94833-144">Typy bez řazené kolekce členů není nabízí integrovanou podporu pro zahodí.</span><span class="sxs-lookup"><span data-stu-id="94833-144">Non-tuple types do not offer built-in support for discards.</span></span> <span data-ttu-id="94833-145">Však můžete jako autor třídy, struktury nebo rozhraní povolit typ, který má být deconstructed implementací jeden nebo více instancí `Deconstruct` metody.</span><span class="sxs-lookup"><span data-stu-id="94833-145">However, as the author of a class, a struct, or an interface, you can allow instances of the type to be deconstructed by implementing one or more `Deconstruct` methods.</span></span> <span data-ttu-id="94833-146">Metoda vrátí void a každou hodnotu být deconstructed je indikován [out](language-reference/keywords/out-parameter-modifier.md) parametr v podpis metody.</span><span class="sxs-lookup"><span data-stu-id="94833-146">The method returns void, and each value to be deconstructed is indicated by an [out](language-reference/keywords/out-parameter-modifier.md) parameter in the method signature.</span></span> <span data-ttu-id="94833-147">Například následující `Deconstruct` metodu `Person` vrátí první a poslední název třídy:</span><span class="sxs-lookup"><span data-stu-id="94833-147">For example, the following `Deconstruct` method of a `Person` class returns the first, middle, and last name:</span></span>

[!code-csharp[Class-deconstruct](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/deconstruct-class1.cs#1)]

<span data-ttu-id="94833-148">Potom můžete deconstruct instanci `Person` třídu s názvem `p` spolu s přiřazením takto:</span><span class="sxs-lookup"><span data-stu-id="94833-148">You can then deconstruct an instance of the `Person` class named `p` with an assignment like the following:</span></span>

[!code-csharp[Class-deconstruct](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/deconstruct-class1.cs#2)]

<span data-ttu-id="94833-149">Následující příklad přetížení `Deconstruct` metoda vrátí různé kombinace vlastnosti `Person` objektu.</span><span class="sxs-lookup"><span data-stu-id="94833-149">The following example overloads the `Deconstruct` method to return various combinations of properties of a `Person` object.</span></span> <span data-ttu-id="94833-150">Jednotlivé přetížení vrátit:</span><span class="sxs-lookup"><span data-stu-id="94833-150">Individual overloads return:</span></span>

- <span data-ttu-id="94833-151">První a poslední název.</span><span class="sxs-lookup"><span data-stu-id="94833-151">A first and last name.</span></span>
- <span data-ttu-id="94833-152">First, last a křestní jméno.</span><span class="sxs-lookup"><span data-stu-id="94833-152">A first, last, and middle name.</span></span>
- <span data-ttu-id="94833-153">Křestní jméno, příjmení, název města a název stavu.</span><span class="sxs-lookup"><span data-stu-id="94833-153">A first name, a last name, a city name, and a state name.</span></span>

[!code-csharp[Class-deconstruct](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/deconstruct-class2.cs)]

<span data-ttu-id="94833-154">Vzhledem k tomu může dojít k přetížení `Deconstruct` metoda tak, aby odrážela skupiny dat, která se běžně extrahují z objekt, je třeba pečlivě k definování `Deconstruct` metody s podpisy, které jsou charakteristické a jednoznačné.</span><span class="sxs-lookup"><span data-stu-id="94833-154">Because you can overload the `Deconstruct` method to reflect groups of data that are commonly extracted from an object, you should be careful to define `Deconstruct` methods with signatures that are distinctive and unambiguous.</span></span> <span data-ttu-id="94833-155">Více `Deconstruct` metody, které mají stejný počet `out` parametry nebo stejný počet a typ `out` parametry v jiném pořadí může způsobit nejasnostem.</span><span class="sxs-lookup"><span data-stu-id="94833-155">Multiple `Deconstruct` methods that have the same number of `out` parameters or the same number and type of `out` parameters in a different order can cause confusion.</span></span> 

<span data-ttu-id="94833-156">Přetížené `Deconstruct` metoda následující příklad znázorňuje jeden zdroj možné záměny.</span><span class="sxs-lookup"><span data-stu-id="94833-156">The overloaded `Deconstruct` method in the following example illustrates one possible source of confusion.</span></span> <span data-ttu-id="94833-157">Vrátí první přetížení křestní jméno, křestní jméno, příjmení a stáří `Person` objekt v tomto pořadí.</span><span class="sxs-lookup"><span data-stu-id="94833-157">The first overload returns the first name, middle name, last name, and age of a `Person` object, in that order.</span></span> <span data-ttu-id="94833-158">Druhý přetížení vrátí název informace pouze společně s roční příjem, ale první a poslední název je v jiném pořadí.</span><span class="sxs-lookup"><span data-stu-id="94833-158">The second overload returns name information only along with annual income, but the first, middle, and last name are in a different order.</span></span> <span data-ttu-id="94833-159">To umožňuje snadno zaměnit pořadí argumentů při deconstructing `Person` instance.</span><span class="sxs-lookup"><span data-stu-id="94833-159">This makes it easy to confuse the order of arguments when deconstructing a `Person` instance.</span></span>

[!code-csharp[Deconstruct-ambiguity](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/deconstruct-ambiguous.cs)]

## <a name="deconstructing-a-user-defined-type-with-discards"></a><span data-ttu-id="94833-160">Deconstructing uživatelsky definovaný typ. se zahodí.</span><span class="sxs-lookup"><span data-stu-id="94833-160">Deconstructing a user-defined type with discards</span></span>

<span data-ttu-id="94833-161">Stejně jako s [řazených kolekcí členů](#deconstructing-tuple-elements-with-discards), zahození můžete ignorovat vybraných položek vrácených `Deconstruct` metoda.</span><span class="sxs-lookup"><span data-stu-id="94833-161">Just as you do with [tuples](#deconstructing-tuple-elements-with-discards), you can use discards to ignore selected items returned by a `Deconstruct` method.</span></span> <span data-ttu-id="94833-162">Každý zahození je definované proměnné s názvem "\_", a operaci jeden deconstruction může obsahovat více zahození.</span><span class="sxs-lookup"><span data-stu-id="94833-162">Each discard is defined by a variable named "\_", and a single deconstruction operation can include multiple discards.</span></span>

<span data-ttu-id="94833-163">Následující příklad deconstructs `Person` objektu do čtyř řetězce (první a poslední názvů, Město a stav), ale zahodí příjmení a stavu.</span><span class="sxs-lookup"><span data-stu-id="94833-163">The following example deconstructs a `Person` object into four strings (the first and last names, the city, and the state) but discards the last name and the state.</span></span>

[!code-csharp[Class-discard](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/class-discard1.cs#1)]

## <a name="deconstructing-a-user-defined-type-with-an-extension-method"></a><span data-ttu-id="94833-164">Deconstructing uživatelem definovaný typ pomocí metody rozšíření</span><span class="sxs-lookup"><span data-stu-id="94833-164">Deconstructing a user-defined type with an extension method</span></span>

<span data-ttu-id="94833-165">Pokud vytváříte nebyla třída, struktura nebo rozhraní, můžete stále deconstruct objekty daného typu implementací jeden nebo více `Deconstruct` [rozšiřující metody](programming-guide/classes-and-structs/extension-methods.md) k návratu hodnot, které vás zajímají.</span><span class="sxs-lookup"><span data-stu-id="94833-165">If you didn't author a class, struct, or interface, you can still deconstruct objects of that type by implementing one or more `Deconstruct` [extension methods](programming-guide/classes-and-structs/extension-methods.md) to return the values in which you're interested.</span></span> 

<span data-ttu-id="94833-166">V následujícím příkladu definuje dvě `Deconstruct` rozšiřující metody pro <xref:System.Reflection.PropertyInfo?displayProperty=nameWithType> třídy.</span><span class="sxs-lookup"><span data-stu-id="94833-166">The following example defines two `Deconstruct` extension methods for the <xref:System.Reflection.PropertyInfo?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="94833-167">Vrátí první sadu hodnot, které uvést parametry vlastnosti, včetně jeho typu, zda je statický nebo instanci, zda je jen pro čtení a jestli je indexovaný.</span><span class="sxs-lookup"><span data-stu-id="94833-167">The first returns a set of values that indicate the characteristics of the property, including its type, whether it's static or instance, whether it's read-only, and whether it's indexed.</span></span> <span data-ttu-id="94833-168">Druhý určuje vlastnosti usnadnění.</span><span class="sxs-lookup"><span data-stu-id="94833-168">The second indicates the property's accessibility.</span></span> <span data-ttu-id="94833-169">Protože usnadnění get a sadu přístupových objektů se může lišit, logické hodnoty označuje, zda má vlastnost samostatné získání a nastavení přístupových objektů a pokud ano, zda mají stejné usnadnění.</span><span class="sxs-lookup"><span data-stu-id="94833-169">Because the accessibility of get and set accessors can differ, Boolean values indicate whether the property has separate get and set accessors and, if it does, whether they have the same accessibility.</span></span> <span data-ttu-id="94833-170">Pokud je pouze jeden přistupujícího objektu nebo get i přistupující objekt set mají stejné usnadnění `access` proměnné označuje usnadnění vlastnost jako celek.</span><span class="sxs-lookup"><span data-stu-id="94833-170">If there is only one accessor or both the get and the set accessor have the same accessibility, the `access` variable indicates the accessibility of the property as a whole.</span></span> <span data-ttu-id="94833-171">V opačném usnadnění operace get a sadu přístupových objektů jsou označeny accessaccessibility je indikován `getAccess` a `setAccess` proměnné.</span><span class="sxs-lookup"><span data-stu-id="94833-171">Otherwise, the accessibility of the get and set accessors are indicated by the accessaccessibility is indicated by the `getAccess` and `setAccess` variables.</span></span>

[!code-csharp[Extension-deconstruct](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/deconstruct-extension1.cs)]
 
## <a name="see-also"></a><span data-ttu-id="94833-172">Viz také</span><span class="sxs-lookup"><span data-stu-id="94833-172">See also</span></span>
<span data-ttu-id="94833-173">[Zahození](discards.md) </span><span class="sxs-lookup"><span data-stu-id="94833-173">[Discards](discards.md) </span></span>  
[<span data-ttu-id="94833-174">Řazené kolekce členů</span><span class="sxs-lookup"><span data-stu-id="94833-174">Tuples</span></span>](tuples.md)  
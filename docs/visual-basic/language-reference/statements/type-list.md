---
title: "Seznam typů (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- StructureConstraint
- vb.StructureConstraint
- ClassConstraint
- vb.ClassConstraint
helpviewer_keywords:
- class constraint
- constraints, Visual Basic generic types
- generic parameters
- generics [Visual Basic], constraints
- generics [Visual Basic], type list
- structure constraint
- constraints, in type parameters
- generics [Visual Basic], generic types
- parameters [Visual Basic], type
- constraints, Structure keyword
- type parameters [Visual Basic], constraints
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- generics [Visual Basic], type parameters
- type parameters
- constraints, Class keyword
ms.assetid: 56db947a-2ae8-40f2-a70a-960764e9d0db
caps.latest.revision: "33"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 35e72414b236615dc230b654ccfeed290841fb31
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="type-list-visual-basic"></a><span data-ttu-id="4d598-102">Seznam typů (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4d598-102">Type List (Visual Basic)</span></span>
<span data-ttu-id="4d598-103">Určuje, *parametry typu* pro *Obecné* programovací element.</span><span class="sxs-lookup"><span data-stu-id="4d598-103">Specifies the *type parameters* for a *generic* programming element.</span></span> <span data-ttu-id="4d598-104">Několik parametrů jsou oddělené čárkami.</span><span class="sxs-lookup"><span data-stu-id="4d598-104">Multiple parameters are separated by commas.</span></span> <span data-ttu-id="4d598-105">Toto je syntaxe pro jeden typ parametru.</span><span class="sxs-lookup"><span data-stu-id="4d598-105">Following is the syntax for one type parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d598-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="4d598-106">Syntax</span></span>  
  
```  
[genericmodifier] typename [ As constraintlist ]  
```  
  
## <a name="parts"></a><span data-ttu-id="4d598-107">Součásti</span><span class="sxs-lookup"><span data-stu-id="4d598-107">Parts</span></span>  
  
|<span data-ttu-id="4d598-108">Termín</span><span class="sxs-lookup"><span data-stu-id="4d598-108">Term</span></span>|<span data-ttu-id="4d598-109">Definice</span><span class="sxs-lookup"><span data-stu-id="4d598-109">Definition</span></span>|  
|---|---|  
|`genericmodifier`|<span data-ttu-id="4d598-110">Volitelné.</span><span class="sxs-lookup"><span data-stu-id="4d598-110">Optional.</span></span> <span data-ttu-id="4d598-111">Lze použít pouze v obecných rozhraní a delegáti.</span><span class="sxs-lookup"><span data-stu-id="4d598-111">Can be used only in generic interfaces and delegates.</span></span> <span data-ttu-id="4d598-112">Je možné deklarovat typu kovariantní pomocí [se](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md) – klíčové slovo nebo kontravariant pomocí [v](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md) – klíčové slovo.</span><span class="sxs-lookup"><span data-stu-id="4d598-112">You can declare a type covariant by using the [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md) keyword or contravariant by using the [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md) keyword.</span></span> <span data-ttu-id="4d598-113">V tématu [kovariance a kontravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span><span class="sxs-lookup"><span data-stu-id="4d598-113">See [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>|  
|`typename`|<span data-ttu-id="4d598-114">Požadováno.</span><span class="sxs-lookup"><span data-stu-id="4d598-114">Required.</span></span> <span data-ttu-id="4d598-115">Název typu parametru.</span><span class="sxs-lookup"><span data-stu-id="4d598-115">Name of the type parameter.</span></span> <span data-ttu-id="4d598-116">Toto je zástupný symbol, budou nahrazeny určitého typu poskytl argument typu.</span><span class="sxs-lookup"><span data-stu-id="4d598-116">This is a placeholder, to be replaced by a defined type supplied by the corresponding type argument.</span></span>|  
|`constraintlist`|<span data-ttu-id="4d598-117">Volitelné.</span><span class="sxs-lookup"><span data-stu-id="4d598-117">Optional.</span></span> <span data-ttu-id="4d598-118">Seznam požadavků, které určují datový typ, který můžete zadat pro `typename`.</span><span class="sxs-lookup"><span data-stu-id="4d598-118">List of requirements that constrain the data type that can be supplied for `typename`.</span></span> <span data-ttu-id="4d598-119">Pokud máte více omezení, uzavřete je do složených závorek (`{ }`) a oddělte je čárkami.</span><span class="sxs-lookup"><span data-stu-id="4d598-119">If you have multiple constraints, enclose them in curly braces (`{ }`) and separate them with commas.</span></span> <span data-ttu-id="4d598-120">Je nutné zavést seznamu omezení s [jako](../../../visual-basic/language-reference/statements/as-clause.md) – klíčové slovo.</span><span class="sxs-lookup"><span data-stu-id="4d598-120">You must introduce the constraint list with the [As](../../../visual-basic/language-reference/statements/as-clause.md) keyword.</span></span> <span data-ttu-id="4d598-121">Používáte `As` pouze jednou na začátku seznamu.</span><span class="sxs-lookup"><span data-stu-id="4d598-121">You use `As` only once, at the beginning of the list.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4d598-122">Poznámky</span><span class="sxs-lookup"><span data-stu-id="4d598-122">Remarks</span></span>  
 <span data-ttu-id="4d598-123">Každý obecný programovací element vyžaduje alespoň jeden parametr typu.</span><span class="sxs-lookup"><span data-stu-id="4d598-123">Every generic programming element must take at least one type parameter.</span></span> <span data-ttu-id="4d598-124">Parametr typu je zástupný symbol pro konkrétní typ ( *vytvořený element*), kód klienta Určuje, kdy se vytvoří instance obecného typu.</span><span class="sxs-lookup"><span data-stu-id="4d598-124">A type parameter is a placeholder for a specific type (a *constructed element*) that client code specifies when it creates an instance of the generic type.</span></span> <span data-ttu-id="4d598-125">Můžete definovat obecné třídy, struktury, rozhraní, postupu nebo delegovat.</span><span class="sxs-lookup"><span data-stu-id="4d598-125">You can define a generic class, structure, interface, procedure, or delegate.</span></span>  
  
 <span data-ttu-id="4d598-126">Další informace o při definování obecného typu, najdete v části [obecné typy v jazyce Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span><span class="sxs-lookup"><span data-stu-id="4d598-126">For more information on when to define a generic type, see [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span></span> <span data-ttu-id="4d598-127">Další informace o typu názvy parametrů najdete v tématu [deklarované názvy elementů](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="4d598-127">For more information on type parameter names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="4d598-128">Pravidla</span><span class="sxs-lookup"><span data-stu-id="4d598-128">Rules</span></span>  
  
-   <span data-ttu-id="4d598-129">**Závorky.**</span><span class="sxs-lookup"><span data-stu-id="4d598-129">**Parentheses.**</span></span> <span data-ttu-id="4d598-130">Pokud zadáte seznam parametrů typu, je nutné uzavřít do závorek a je nutné zavést seznamu pomocí [z](../../../visual-basic/language-reference/statements/of-clause.md) – klíčové slovo.</span><span class="sxs-lookup"><span data-stu-id="4d598-130">If you supply a type parameter list, you must enclose it in parentheses, and you must introduce the list with the [Of](../../../visual-basic/language-reference/statements/of-clause.md) keyword.</span></span> <span data-ttu-id="4d598-131">Používáte `Of` pouze jednou na začátku seznamu.</span><span class="sxs-lookup"><span data-stu-id="4d598-131">You use `Of` only once, at the beginning of the list.</span></span>  
  
-   <span data-ttu-id="4d598-132">**Omezení.**</span><span class="sxs-lookup"><span data-stu-id="4d598-132">**Constraints.**</span></span> <span data-ttu-id="4d598-133">Seznam *omezení* parametr pro typ může obsahovat následující položky v libovolné kombinace:</span><span class="sxs-lookup"><span data-stu-id="4d598-133">A list of *constraints* on a type parameter can include the following items in any combination:</span></span>  
  
    -   <span data-ttu-id="4d598-134">Libovolný počet rozhraní.</span><span class="sxs-lookup"><span data-stu-id="4d598-134">Any number of interfaces.</span></span> <span data-ttu-id="4d598-135">Zadaný typ musí implementovat každé rozhraní v tomto seznamu.</span><span class="sxs-lookup"><span data-stu-id="4d598-135">The supplied type must implement every interface in this list.</span></span>  
  
    -   <span data-ttu-id="4d598-136">Maximálně jednu třídu.</span><span class="sxs-lookup"><span data-stu-id="4d598-136">At most one class.</span></span> <span data-ttu-id="4d598-137">Zadaný typ musí dědit z této třídy.</span><span class="sxs-lookup"><span data-stu-id="4d598-137">The supplied type must inherit from that class.</span></span>  
  
    -   <span data-ttu-id="4d598-138">`New` – Klíčové slovo.</span><span class="sxs-lookup"><span data-stu-id="4d598-138">The `New` keyword.</span></span> <span data-ttu-id="4d598-139">Zadaný typ musí vystavit konstruktor bez parametrů, kterým může přistupovat obecného typu.</span><span class="sxs-lookup"><span data-stu-id="4d598-139">The supplied type must expose a parameterless constructor that your generic type can access.</span></span> <span data-ttu-id="4d598-140">To je užitečné, pokud omezit parametr typu pomocí jednoho nebo více rozhraní.</span><span class="sxs-lookup"><span data-stu-id="4d598-140">This is useful if you constrain a type parameter by one or more interfaces.</span></span> <span data-ttu-id="4d598-141">Typ, který implementuje rozhraní nevystavuje nutně konstruktor, a v závislosti na úroveň přístupu tohoto konstruktoru, nemusí být možné pro přístup k ní kód v rámci obecného typu.</span><span class="sxs-lookup"><span data-stu-id="4d598-141">A type that implements interfaces does not necessarily expose a constructor, and depending on the access level of a constructor, the code within the generic type might not be able to access it.</span></span>  
  
    -   <span data-ttu-id="4d598-142">Buď `Class` – klíčové slovo nebo `Structure` – klíčové slovo.</span><span class="sxs-lookup"><span data-stu-id="4d598-142">Either the `Class` keyword or the `Structure` keyword.</span></span> <span data-ttu-id="4d598-143">`Class` – Klíčové slovo omezí parametr obecného typu, který se požadovat, aby některý typ argument předaný být odkazového typu, například řetězce, pole nebo delegáta, nebo vytvořen objekt ze třídy.</span><span class="sxs-lookup"><span data-stu-id="4d598-143">The `Class` keyword constrains a generic type parameter to require that any type argument passed to it be a reference type, for example a string, array, or delegate, or an object created from a class.</span></span> <span data-ttu-id="4d598-144">`Structure` – Klíčové slovo omezí parametr obecného typu, který se vyžadují, aby některý typ argument předaný typ hodnoty, například strukturu, výčet nebo základní datového typu.</span><span class="sxs-lookup"><span data-stu-id="4d598-144">The `Structure` keyword constrains a generic type parameter to require that any type argument passed to it be a value type, for example a structure, enumeration, or elementary data type.</span></span> <span data-ttu-id="4d598-145">Nemůže současně obsahovat `Class` a `Structure` ve stejné `constraintlist`.</span><span class="sxs-lookup"><span data-stu-id="4d598-145">You cannot include both `Class` and `Structure` in the same `constraintlist`.</span></span>  
  
     <span data-ttu-id="4d598-146">Zadaný typ musí splňovat každý požadavek, můžete zahrnout `constraintlist`.</span><span class="sxs-lookup"><span data-stu-id="4d598-146">The supplied type must satisfy every requirement you include in `constraintlist`.</span></span>  
  
     <span data-ttu-id="4d598-147">Omezení pro každý parametr typu jsou nezávislé na omezení dalších parametrů typu.</span><span class="sxs-lookup"><span data-stu-id="4d598-147">Constraints on each type parameter are independent of constraints on other type parameters.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="4d598-148">Chování</span><span class="sxs-lookup"><span data-stu-id="4d598-148">Behavior</span></span>  
  
-   <span data-ttu-id="4d598-149">**Nahrazení kompilaci.**</span><span class="sxs-lookup"><span data-stu-id="4d598-149">**Compile-Time Substitution.**</span></span> <span data-ttu-id="4d598-150">Při vytváření typu vytvořený z obecné programovací element, můžete zadat určitého typu pro každý parametr typu.</span><span class="sxs-lookup"><span data-stu-id="4d598-150">When you create a constructed type from a generic programming element, you supply a defined type for each type parameter.</span></span> <span data-ttu-id="4d598-151">Visual Basic – kompilátor nahradí zadaný typu pro každý výskyt `typename` v rámci obecné elementu.</span><span class="sxs-lookup"><span data-stu-id="4d598-151">The Visual Basic compiler substitutes that supplied type for every occurrence of `typename` within the generic element.</span></span>  
  
-   <span data-ttu-id="4d598-152">**Neexistence omezení.**</span><span class="sxs-lookup"><span data-stu-id="4d598-152">**Absence of Constraints.**</span></span> <span data-ttu-id="4d598-153">Pokud nezadáte žádné omezení pro parametr typu, je omezený na operace a členy nepodporuje kódu [Object – datový typ](../../../visual-basic/language-reference/data-types/object-data-type.md) pro tento parametr typu.</span><span class="sxs-lookup"><span data-stu-id="4d598-153">If you do not specify any constraints on a type parameter, your code is limited to the operations and members supported by the [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md) for that type parameter.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d598-154">Příklad</span><span class="sxs-lookup"><span data-stu-id="4d598-154">Example</span></span>  
 <span data-ttu-id="4d598-155">Následující příklad ukazuje definici kostru obecné slovník třídy, včetně kostru funkci, kterou chcete přidat novou položku do slovníku.</span><span class="sxs-lookup"><span data-stu-id="4d598-155">The following example shows a skeleton definition of a generic dictionary class, including a skeleton function to add a new entry to the dictionary.</span></span>  
  
 [!code-vb[VbVbalrStatements#3](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/type-list_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="4d598-156">Příklad</span><span class="sxs-lookup"><span data-stu-id="4d598-156">Example</span></span>  
 <span data-ttu-id="4d598-157">Protože `dictionary` je obecný, kód, který používá ji můžete vytvořit různé objekty z něj, každý s stejné funkce, ale funguje na jiný datový typ.</span><span class="sxs-lookup"><span data-stu-id="4d598-157">Because `dictionary` is generic, the code that uses it can create a variety of objects from it, each having the same functionality but acting on a different data type.</span></span> <span data-ttu-id="4d598-158">Následující příklad ukazuje řádek kódu, který vytvoří `dictionary` objektu s `String` položky a `Integer` klíče.</span><span class="sxs-lookup"><span data-stu-id="4d598-158">The following example shows a line of code that creates a `dictionary` object with `String` entries and `Integer` keys.</span></span>  
  
 [!code-vb[VbVbalrStatements#4](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/type-list_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="4d598-159">Příklad</span><span class="sxs-lookup"><span data-stu-id="4d598-159">Example</span></span>  
 <span data-ttu-id="4d598-160">Následující příklad ukazuje definici ekvivalentní kostru vygenerované v předchozím příkladu.</span><span class="sxs-lookup"><span data-stu-id="4d598-160">The following example shows the equivalent skeleton definition generated by the preceding example.</span></span>  
  
 [!code-vb[VbVbalrStatements#5](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/type-list_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="4d598-161">Viz také</span><span class="sxs-lookup"><span data-stu-id="4d598-161">See Also</span></span>  
 [<span data-ttu-id="4d598-162">Z</span><span class="sxs-lookup"><span data-stu-id="4d598-162">Of</span></span>](../../../visual-basic/language-reference/statements/of-clause.md)  
 [<span data-ttu-id="4d598-163">New – operátor</span><span class="sxs-lookup"><span data-stu-id="4d598-163">New Operator</span></span>](../../../visual-basic/language-reference/operators/new-operator.md)  
 [<span data-ttu-id="4d598-164">Úrovně přístupu v jazyce Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4d598-164">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [<span data-ttu-id="4d598-165">Object – datový typ</span><span class="sxs-lookup"><span data-stu-id="4d598-165">Object Data Type</span></span>](../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [<span data-ttu-id="4d598-166">Function – příkaz</span><span class="sxs-lookup"><span data-stu-id="4d598-166">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="4d598-167">Structure – příkaz</span><span class="sxs-lookup"><span data-stu-id="4d598-167">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="4d598-168">Sub – příkaz</span><span class="sxs-lookup"><span data-stu-id="4d598-168">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="4d598-169">Postupy: použití obecné třídy</span><span class="sxs-lookup"><span data-stu-id="4d598-169">How to: Use a Generic Class</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)  
 [<span data-ttu-id="4d598-170">Kovariance a kontravariance</span><span class="sxs-lookup"><span data-stu-id="4d598-170">Covariance and Contravariance</span></span>](../../programming-guide/concepts/covariance-contravariance/index.md)  
 [<span data-ttu-id="4d598-171">V</span><span class="sxs-lookup"><span data-stu-id="4d598-171">In</span></span>](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)  
 [<span data-ttu-id="4d598-172">Na více systémů</span><span class="sxs-lookup"><span data-stu-id="4d598-172">Out</span></span>](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
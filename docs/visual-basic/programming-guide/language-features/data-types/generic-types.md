---
title: "Obecné typy v jazyce Visual Basic (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- generic interfaces
- data type arguments [Visual Basic], defining
- generic delegates
- arguments [Visual Basic], data types
- Of keyword [Visual Basic], using
- delegates, generic
- constraints, Visual Basic generic types
- generic parameters
- data type parameters
- procedures [Visual Basic], generic
- generic procedures
- data types [Visual Basic], generic
- data types [Visual Basic], as parameters
- generics [Visual Basic], generic types
- data types [Visual Basic], as arguments
- generic classes [Visual Basic], Visual Basic
- parameters [Visual Basic], type
- type arguments
- interfaces [Visual Basic], generic
- generics [Visual Basic]
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- generic structures [Visual Basic]
- generic classes [Visual Basic]
- type parameters
- data type arguments
- structures [Visual Basic], generic
- parameters [Visual Basic], data type
- collections, generic
- classes [Visual Basic], generic
- data type parameters [Visual Basic], defining
- type arguments [Visual Basic], defining
- arguments [Visual Basic], type
ms.assetid: 89f771d9-ecbb-4737-88b8-116b63c6cf4d
caps.latest.revision: "45"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 463391da61cbafe1f50a246307994cfa134dba38
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="generic-types-in-visual-basic-visual-basic"></a><span data-ttu-id="93b2f-102">Obecné typy v jazyce Visual Basic (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="93b2f-102">Generic Types in Visual Basic (Visual Basic)</span></span>
<span data-ttu-id="93b2f-103">A *obecného typu* je jeden programovací element, který přizpůsobí provádět stejné funkce pro různé datové typy.</span><span class="sxs-lookup"><span data-stu-id="93b2f-103">A *generic type* is a single programming element that adapts to perform the same functionality for a variety of data types.</span></span> <span data-ttu-id="93b2f-104">Při definování obecné třídy nebo postup nemáte definovat samostatné verze pro každý typ dat, pro které můžete chtít provést této funkce.</span><span class="sxs-lookup"><span data-stu-id="93b2f-104">When you define a generic class or procedure, you do not have to define a separate version for each data type for which you might want to perform that functionality.</span></span>  
  
 <span data-ttu-id="93b2f-105">Sledují se šroubováku s vyměnitelné oznámení.</span><span class="sxs-lookup"><span data-stu-id="93b2f-105">An analogy is a screwdriver set with removable heads.</span></span> <span data-ttu-id="93b2f-106">Zkontrolujte šroubovacím, budete muset zapnout a vyberte správnou hlavičku pro tento šroub (s drážkou, překročí, starred).</span><span class="sxs-lookup"><span data-stu-id="93b2f-106">You inspect the screw you need to turn and select the correct head for that screw (slotted, crossed, starred).</span></span> <span data-ttu-id="93b2f-107">Jakmile můžete vložit správné head šroubovák popisovač, provedete přesně stejnou funkci s šroubovák, konkrétně vypnutí šroubek.</span><span class="sxs-lookup"><span data-stu-id="93b2f-107">Once you insert the correct head in the screwdriver handle, you perform the exact same function with the screwdriver, namely turning the screw.</span></span>  
  
 <span data-ttu-id="93b2f-108">![Diagram šroubováku jako obecný nástroj](../../../../visual-basic/programming-guide/language-features/data-types/media/genericscrewdriver.gif "GenericScrewDriver")</span><span class="sxs-lookup"><span data-stu-id="93b2f-108">![Diagram of a screwdriver set as a generic tool](../../../../visual-basic/programming-guide/language-features/data-types/media/genericscrewdriver.gif "GenericScrewDriver")</span></span>  
<span data-ttu-id="93b2f-109">Šroubováku jako obecný nástroj</span><span class="sxs-lookup"><span data-stu-id="93b2f-109">Screwdriver set as a generic tool</span></span>  
  
 <span data-ttu-id="93b2f-110">Při definování obecného typu Parametrizace s jeden nebo více datových typů.</span><span class="sxs-lookup"><span data-stu-id="93b2f-110">When you define a generic type, you parameterize it with one or more data types.</span></span> <span data-ttu-id="93b2f-111">To umožňuje použití kódu můžete nastavit typy dat, které mají požadavky na jeho.</span><span class="sxs-lookup"><span data-stu-id="93b2f-111">This allows the using code to tailor the data types to its requirements.</span></span> <span data-ttu-id="93b2f-112">Váš kód můžou deklarovat několik různých programovací elementy ze obecné elementu, každé z nich funguje na jinou sadu datových typů.</span><span class="sxs-lookup"><span data-stu-id="93b2f-112">Your code can declare several different programming elements from the generic element, each one acting on a different set of data types.</span></span> <span data-ttu-id="93b2f-113">Ale deklarované elementy všechny provádět stejné logiky, bez ohledu na to, jaké typy dat používají.</span><span class="sxs-lookup"><span data-stu-id="93b2f-113">But the declared elements all perform the identical logic, no matter what data types they are using.</span></span>  
  
 <span data-ttu-id="93b2f-114">Například můžete chtít vytvořit a použít fronty třídu, která funguje na určité datový typ jako `String`.</span><span class="sxs-lookup"><span data-stu-id="93b2f-114">For example, you might want to create and use a queue class that operates on a specific data type such as `String`.</span></span> <span data-ttu-id="93b2f-115">Je možné deklarovat třídy z <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType>, jak ukazuje následující příklad.</span><span class="sxs-lookup"><span data-stu-id="93b2f-115">You can declare such a class from <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType>, as the following example shows.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#1](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-types_1.vb)]  
  
 <span data-ttu-id="93b2f-116">Teď můžete použít `stringQ` pracovat pouze s `String` hodnoty.</span><span class="sxs-lookup"><span data-stu-id="93b2f-116">You can now use `stringQ` to work exclusively with `String` values.</span></span> <span data-ttu-id="93b2f-117">Protože `stringQ` je specifický pro `String` místo se zobecněn pro `Object` hodnoty, není nutné pozdní vazba nebo typ převodu.</span><span class="sxs-lookup"><span data-stu-id="93b2f-117">Because `stringQ` is specific for `String` instead of being generalized for `Object` values, you do not have late binding or type conversion.</span></span> <span data-ttu-id="93b2f-118">Tím ušetříte čas spuštění a snižuje běhové chyby.</span><span class="sxs-lookup"><span data-stu-id="93b2f-118">This saves execution time and reduces run-time errors.</span></span>  
  
 <span data-ttu-id="93b2f-119">Další informace o použití obecného typu, najdete v části [postupy: použití obecné třídy](../../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md).</span><span class="sxs-lookup"><span data-stu-id="93b2f-119">For more information on using a generic type, see [How to: Use a Generic Class](../../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md).</span></span>  
  
## <a name="example-of-a-generic-class"></a><span data-ttu-id="93b2f-120">Příklad obecné třídy</span><span class="sxs-lookup"><span data-stu-id="93b2f-120">Example of a Generic Class</span></span>  
 <span data-ttu-id="93b2f-121">Následující příklad ukazuje definici kostru obecné třídy.</span><span class="sxs-lookup"><span data-stu-id="93b2f-121">The following example shows a skeleton definition of a generic class.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#2](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-types_2.vb)]  
  
 <span data-ttu-id="93b2f-122">V předchozím kostru `t` je *parametr typu*, který je zástupný symbol pro datový typ, který zadáte po deklarování třídy.</span><span class="sxs-lookup"><span data-stu-id="93b2f-122">In the preceding skeleton, `t` is a *type parameter*, that is, a placeholder for a data type that you supply when you declare the class.</span></span> <span data-ttu-id="93b2f-123">Někde v kódu, můžou deklarovat různých verzích `classHolder` zadáním různé datové typy pro `t`.</span><span class="sxs-lookup"><span data-stu-id="93b2f-123">Elsewhere in your code, you can declare various versions of `classHolder` by supplying various data types for `t`.</span></span> <span data-ttu-id="93b2f-124">Následující příklad ukazuje dva tato prohlášení.</span><span class="sxs-lookup"><span data-stu-id="93b2f-124">The following example shows two such declarations.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#3](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-types_3.vb)]  
  
 <span data-ttu-id="93b2f-125">Předchozí příkazy deklarovat *sestavený třídy*, ve kterém konkrétního typu nahrazuje parametr typu.</span><span class="sxs-lookup"><span data-stu-id="93b2f-125">The preceding statements declare *constructed classes*, in which a specific type replaces the type parameter.</span></span> <span data-ttu-id="93b2f-126">Tato nahrazení je šíření v kódu v rámci sestavené třídy.</span><span class="sxs-lookup"><span data-stu-id="93b2f-126">This replacement is propagated throughout the code within the constructed class.</span></span> <span data-ttu-id="93b2f-127">Následující příklad ukazuje, co `processNewItem` postup vypadá jako v `integerClass`.</span><span class="sxs-lookup"><span data-stu-id="93b2f-127">The following example shows what the `processNewItem` procedure looks like in `integerClass`.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#4](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-types_4.vb)]  
  
 <span data-ttu-id="93b2f-128">Více kompletní příklad najdete v tématu [postupy: definování třídy, můžete zadat identické funkce pro různé datové typy](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md).</span><span class="sxs-lookup"><span data-stu-id="93b2f-128">For a more complete example, see [How to: Define a Class That Can Provide Identical Functionality on Different Data Types](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md).</span></span>  
  
## <a name="eligible-programming-elements"></a><span data-ttu-id="93b2f-129">Oprávněné programovací elementy</span><span class="sxs-lookup"><span data-stu-id="93b2f-129">Eligible Programming Elements</span></span>  
 <span data-ttu-id="93b2f-130">Můžete definovat a použití obecné třídy, struktury, rozhraní, postupy a delegáti.</span><span class="sxs-lookup"><span data-stu-id="93b2f-130">You can define and use generic classes, structures, interfaces, procedures, and delegates.</span></span> <span data-ttu-id="93b2f-131">Všimněte si, že [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] definuje několik obecných tříd, struktur a rozhraní, které představují běžně používané obecné elementy.</span><span class="sxs-lookup"><span data-stu-id="93b2f-131">Note that the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] defines several generic classes, structures, and interfaces that represent commonly used generic elements.</span></span> <span data-ttu-id="93b2f-132"><xref:System.Collections.Generic?displayProperty=nameWithType> Obor názvů obsahuje slovník, seznamů, front a zásobníky.</span><span class="sxs-lookup"><span data-stu-id="93b2f-132">The <xref:System.Collections.Generic?displayProperty=nameWithType> namespace provides dictionaries, lists, queues, and stacks.</span></span> <span data-ttu-id="93b2f-133">Před definováním vlastního obecné elementu, zkontrolujte, jestli je již k dispozici v <xref:System.Collections.Generic?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="93b2f-133">Before defining your own generic element, see if it is already available in <xref:System.Collections.Generic?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="93b2f-134">Postupy nejsou typy, ale můžete definovat a použijte obecné procedury.</span><span class="sxs-lookup"><span data-stu-id="93b2f-134">Procedures are not types, but you can define and use generic procedures.</span></span> <span data-ttu-id="93b2f-135">V tématu [obecné procedury v jazyce Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="93b2f-135">See [Generic Procedures in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md).</span></span>  
  
## <a name="advantages-of-generic-types"></a><span data-ttu-id="93b2f-136">Výhody obecných typů</span><span class="sxs-lookup"><span data-stu-id="93b2f-136">Advantages of Generic Types</span></span>  
 <span data-ttu-id="93b2f-137">Obecný typ slouží jako základ pro deklarování několik různých programovací prvky, z nichž každý funguje na určité datový typ.</span><span class="sxs-lookup"><span data-stu-id="93b2f-137">A generic type serves as a basis for declaring several different programming elements, each of which operates on a specific data type.</span></span> <span data-ttu-id="93b2f-138">Alternativy k obecného typu jsou:</span><span class="sxs-lookup"><span data-stu-id="93b2f-138">The alternatives to a generic type are:</span></span>  
  
1.  <span data-ttu-id="93b2f-139">Jeden typ pracující na `Object` datového typu.</span><span class="sxs-lookup"><span data-stu-id="93b2f-139">A single type operating on the `Object` data type.</span></span>  
  
2.  <span data-ttu-id="93b2f-140">Sadu *specifický* verze typu jednotlivých verzí jednotlivě programového a pracující na typu jeden konkrétní data, jako `String`, `Integer`, nebo uživatelsky definovaný typ. například `customer`.</span><span class="sxs-lookup"><span data-stu-id="93b2f-140">A set of *type-specific* versions of the type, each version individually coded and operating on one specific data type such as `String`, `Integer`, or a user-defined type such as `customer`.</span></span>  
  
 <span data-ttu-id="93b2f-141">Obecný typ má následující výhody přes tyto možnosti:</span><span class="sxs-lookup"><span data-stu-id="93b2f-141">A generic type has the following advantages over these alternatives:</span></span>  
  
-   <span data-ttu-id="93b2f-142">**Zabezpečení typů.**</span><span class="sxs-lookup"><span data-stu-id="93b2f-142">**Type Safety.**</span></span> <span data-ttu-id="93b2f-143">Obecné typy vynutit kontrola typu v kompilaci.</span><span class="sxs-lookup"><span data-stu-id="93b2f-143">Generic types enforce compile-time type checking.</span></span> <span data-ttu-id="93b2f-144">Na základě typů `Object` přijměte jakýkoli datový typ a musíte napsat kód a zkontrolujte, zda typ vstupních dat. přijatelný.</span><span class="sxs-lookup"><span data-stu-id="93b2f-144">Types based on `Object` accept any data type, and you must write code to check whether an input data type is acceptable.</span></span> <span data-ttu-id="93b2f-145">S obecné typy můžete kompilátor catch neshody typu než čas spuštění.</span><span class="sxs-lookup"><span data-stu-id="93b2f-145">With generic types, the compiler can catch type mismatches before run time.</span></span>  
  
-   <span data-ttu-id="93b2f-146">**Výkon.**</span><span class="sxs-lookup"><span data-stu-id="93b2f-146">**Performance.**</span></span> <span data-ttu-id="93b2f-147">Obecné typy nemusíte *pole* a *unbox* data, protože každé z nich se specializuje na jednoho datového typu.</span><span class="sxs-lookup"><span data-stu-id="93b2f-147">Generic types do not have to *box* and *unbox* data, because each one is specialized for one data type.</span></span> <span data-ttu-id="93b2f-148">Na základě operace `Object` musí pole vstupních dat typy převést tak, aby `Object` a unbox dat určený pro výstup.</span><span class="sxs-lookup"><span data-stu-id="93b2f-148">Operations based on `Object` must box input data types to convert them to `Object` and unbox data destined for output.</span></span> <span data-ttu-id="93b2f-149">Zabalení a rozbalení snížit výkon.</span><span class="sxs-lookup"><span data-stu-id="93b2f-149">Boxing and unboxing reduce performance.</span></span>  
  
     <span data-ttu-id="93b2f-150">Na základě typů `Object` jsou také pozdní vazby, což znamená, že přístup k jejich členové vyžaduje další kódu v době běhu.</span><span class="sxs-lookup"><span data-stu-id="93b2f-150">Types based on `Object` are also late-bound, which means that accessing their members requires extra code at run time.</span></span> <span data-ttu-id="93b2f-151">To také snižuje výkon.</span><span class="sxs-lookup"><span data-stu-id="93b2f-151">This also reduces performance.</span></span>  
  
-   <span data-ttu-id="93b2f-152">**Konsolidace kódu.**</span><span class="sxs-lookup"><span data-stu-id="93b2f-152">**Code Consolidation.**</span></span> <span data-ttu-id="93b2f-153">Kód v obecného typu musí být definovaný jenom jednou.</span><span class="sxs-lookup"><span data-stu-id="93b2f-153">The code in a generic type has to be defined only once.</span></span> <span data-ttu-id="93b2f-154">Sadu typ specifické verze typu musí replikovat stejný kód v jednotlivých verzích s jediným rozdílem je konkrétní datový typ pro tuto verzi.</span><span class="sxs-lookup"><span data-stu-id="93b2f-154">A set of type-specific versions of a type must replicate the same code in each version, with the only difference being the specific data type for that version.</span></span> <span data-ttu-id="93b2f-155">S obecné typy jsou všechny verze specifický generovány z původní obecného typu.</span><span class="sxs-lookup"><span data-stu-id="93b2f-155">With generic types, the type-specific versions are all generated from the original generic type.</span></span>  
  
-   <span data-ttu-id="93b2f-156">**Opakované použití kódu.**</span><span class="sxs-lookup"><span data-stu-id="93b2f-156">**Code Reuse.**</span></span> <span data-ttu-id="93b2f-157">Pokud je obecný lze znovu kód, který není závislá na datový typ. použít s různými datovými typy.</span><span class="sxs-lookup"><span data-stu-id="93b2f-157">Code that does not depend on a particular data type can be reused with various data types if it is generic.</span></span> <span data-ttu-id="93b2f-158">Můžete je často opakují i s datový typ, který jste není předpovědi původně.</span><span class="sxs-lookup"><span data-stu-id="93b2f-158">You can often reuse it even with a data type that you did not originally predict.</span></span>  
  
-   <span data-ttu-id="93b2f-159">**Podpora rozhraní IDE.**</span><span class="sxs-lookup"><span data-stu-id="93b2f-159">**IDE Support.**</span></span> <span data-ttu-id="93b2f-160">Pokud používáte vytvořený typ deklarovaný od obecného typu, integrované vývojové prostředí (IDE) vám může poskytnout další podporu při vývoji vašeho kódu.</span><span class="sxs-lookup"><span data-stu-id="93b2f-160">When you use a constructed type declared from a generic type, the integrated development environment (IDE) can give you more support while you are developing your code.</span></span> <span data-ttu-id="93b2f-161">IntelliSense můžete můžete například zobrazit možnosti specifický pro argument metoda nebo konstruktor.</span><span class="sxs-lookup"><span data-stu-id="93b2f-161">For example, IntelliSense can show you the type-specific options for an argument to a constructor or method.</span></span>  
  
-   <span data-ttu-id="93b2f-162">**Obecné algoritmy.**</span><span class="sxs-lookup"><span data-stu-id="93b2f-162">**Generic Algorithms.**</span></span> <span data-ttu-id="93b2f-163">Abstraktní algoritmy, které jsou nezávislé na typ jsou vhodnými kandidáty pro obecné typy.</span><span class="sxs-lookup"><span data-stu-id="93b2f-163">Abstract algorithms that are type-independent are good candidates for generic types.</span></span> <span data-ttu-id="93b2f-164">Například obecné procedury, která Seřadí položky pomocí <xref:System.IComparable> rozhraní lze použít s datovým typem, který implementuje <xref:System.IComparable>.</span><span class="sxs-lookup"><span data-stu-id="93b2f-164">For example, a generic procedure that sorts items using the <xref:System.IComparable> interface can be used with any data type that implements <xref:System.IComparable>.</span></span>  
  
## <a name="constraints"></a><span data-ttu-id="93b2f-165">Omezení</span><span class="sxs-lookup"><span data-stu-id="93b2f-165">Constraints</span></span>  
 <span data-ttu-id="93b2f-166">I když kód v definici obecného typu by měl být jako typ nezávislé nejblíže, můžete vyžadovat určité funkce jakýkoli datový typ zadaný do obecného typu.</span><span class="sxs-lookup"><span data-stu-id="93b2f-166">Although the code in a generic type definition should be as type-independent as possible, you might need to require a certain capability of any data type supplied to your generic type.</span></span> <span data-ttu-id="93b2f-167">Například pokud chcete k porovnání dvou položek za účelem řazení nebo kompletování, jejich datový typ musí implementovat <xref:System.IComparable> rozhraní.</span><span class="sxs-lookup"><span data-stu-id="93b2f-167">For example, if you want to compare two items for the purpose of sorting or collating, their data type must implement the <xref:System.IComparable> interface.</span></span> <span data-ttu-id="93b2f-168">Tento požadavek můžete vynutit přidáním *omezení* typ parametru.</span><span class="sxs-lookup"><span data-stu-id="93b2f-168">You can enforce this requirement by adding a *constraint* to the type parameter.</span></span>  
  
### <a name="example-of-a-constraint"></a><span data-ttu-id="93b2f-169">Příklad omezení</span><span class="sxs-lookup"><span data-stu-id="93b2f-169">Example of a Constraint</span></span>  
 <span data-ttu-id="93b2f-170">Následující příklad ukazuje definici kostru třídy s omezením, která vyžaduje argument typu k implementaci <xref:System.IComparable>.</span><span class="sxs-lookup"><span data-stu-id="93b2f-170">The following example shows a skeleton definition of a class with a constraint that requires the type argument to implement <xref:System.IComparable>.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#5](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-types_5.vb)]  
  
 <span data-ttu-id="93b2f-171">Pokud následné kódu se pokusí vytvořit třídu z `itemManager` se zadaným typem, který neimplementuje <xref:System.IComparable>, kompilátor nevydá signál k chybě.</span><span class="sxs-lookup"><span data-stu-id="93b2f-171">If subsequent code attempts to construct a class from `itemManager` supplying a type that does not implement <xref:System.IComparable>, the compiler signals an error.</span></span>  
  
### <a name="types-of-constraints"></a><span data-ttu-id="93b2f-172">Typy omezení</span><span class="sxs-lookup"><span data-stu-id="93b2f-172">Types of Constraints</span></span>  
 <span data-ttu-id="93b2f-173">Vaše omezení v libovolné kombinace můžete určit následující požadavky:</span><span class="sxs-lookup"><span data-stu-id="93b2f-173">Your constraint can specify the following requirements in any combination:</span></span>  
  
-   <span data-ttu-id="93b2f-174">Argument typu musí implementovat jednu nebo více rozhraní</span><span class="sxs-lookup"><span data-stu-id="93b2f-174">The type argument must implement one or more interfaces</span></span>  
  
-   <span data-ttu-id="93b2f-175">Argument typu musí být typu, nebo nastavte dědičnost z maximálně jednu třídu</span><span class="sxs-lookup"><span data-stu-id="93b2f-175">The type argument must be of the type of, or inherit from, at most one class</span></span>  
  
-   <span data-ttu-id="93b2f-176">Argument typu musí vystavit přístupné pro kód, který vytvoří objekty z něj konstruktor bez parametrů</span><span class="sxs-lookup"><span data-stu-id="93b2f-176">The type argument must expose a parameterless constructor accessible to the code that creates objects from it</span></span>  
  
-   <span data-ttu-id="93b2f-177">Argument typu musí být *odkazují na typ*, nebo musí být *typu hodnoty*</span><span class="sxs-lookup"><span data-stu-id="93b2f-177">The type argument must be a *reference type*, or it must be a *value type*</span></span>  
  
 <span data-ttu-id="93b2f-178">Pokud potřebujete použít více než jeden požadavek, můžete použít oddělené čárkami *seznamu omezení* uvnitř složené závorky (`{ }`).</span><span class="sxs-lookup"><span data-stu-id="93b2f-178">If you need to impose more than one requirement, you use a comma-separated *constraint list* inside braces (`{ }`).</span></span> <span data-ttu-id="93b2f-179">Pokud chcete vyžadovat dostupný konstruktor, zahrnete [operátor New](../../../../visual-basic/language-reference/operators/new-operator.md) – klíčové slovo v seznamu.</span><span class="sxs-lookup"><span data-stu-id="93b2f-179">To require an accessible constructor, you include the [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) keyword in the list.</span></span> <span data-ttu-id="93b2f-180">Pokud chcete vyžadovat typu odkazu, zahrnete `Class` – klíčové slovo; tak, aby vyžadovala typu hodnoty zahrnete `Structure` – klíčové slovo.</span><span class="sxs-lookup"><span data-stu-id="93b2f-180">To require a reference type, you include the `Class` keyword; to require a value type, you include the `Structure` keyword.</span></span>  
  
 <span data-ttu-id="93b2f-181">Další informace o omezení najdete v tématu [seznam typů](../../../../visual-basic/language-reference/statements/type-list.md).</span><span class="sxs-lookup"><span data-stu-id="93b2f-181">For more information on constraints, see [Type List](../../../../visual-basic/language-reference/statements/type-list.md).</span></span>  
  
### <a name="example-of-multiple-constraints"></a><span data-ttu-id="93b2f-182">Příklad více omezení</span><span class="sxs-lookup"><span data-stu-id="93b2f-182">Example of Multiple Constraints</span></span>  
 <span data-ttu-id="93b2f-183">Následující příklad ukazuje definici kostru obecné třídy s seznamu omezení na parametr typu.</span><span class="sxs-lookup"><span data-stu-id="93b2f-183">The following example shows a skeleton definition of a generic class with a constraint list on the type parameter.</span></span> <span data-ttu-id="93b2f-184">V kódu, který vytvoří instanci této třídy, musí implementovat argument typu i <xref:System.IComparable> a <xref:System.IDisposable> rozhraní, být odkazového typu a vystavit přístupné bezparametrový konstruktor.</span><span class="sxs-lookup"><span data-stu-id="93b2f-184">In the code that creates an instance of this class, the type argument must implement both the <xref:System.IComparable> and <xref:System.IDisposable> interfaces, be a reference type, and expose an accessible parameterless constructor.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#6](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-types_6.vb)]  
  
## <a name="important-terms"></a><span data-ttu-id="93b2f-185">Důležité termíny</span><span class="sxs-lookup"><span data-stu-id="93b2f-185">Important Terms</span></span>  
 <span data-ttu-id="93b2f-186">Obecné typy zavést a používají následující termíny:</span><span class="sxs-lookup"><span data-stu-id="93b2f-186">Generic types introduce and use the following terms:</span></span>  
  
-   <span data-ttu-id="93b2f-187">*Obecný typ*.</span><span class="sxs-lookup"><span data-stu-id="93b2f-187">*Generic Type*.</span></span> <span data-ttu-id="93b2f-188">Definice třídy, struktury, rozhraní, postup nebo delegáta, pro kterou je zadat nejméně jeden datový typ při jeho deklaraci.</span><span class="sxs-lookup"><span data-stu-id="93b2f-188">A definition of a class, structure, interface, procedure, or delegate for which you supply at least one data type when you declare it.</span></span>  
  
-   <span data-ttu-id="93b2f-189">*Zadejte parametr*.</span><span class="sxs-lookup"><span data-stu-id="93b2f-189">*Type Parameter*.</span></span> <span data-ttu-id="93b2f-190">V definici obecného typu zástupný symbol pro datový typ je zadat při deklaraci typu.</span><span class="sxs-lookup"><span data-stu-id="93b2f-190">In a generic type definition, a placeholder for a data type you supply when you declare the type.</span></span>  
  
-   <span data-ttu-id="93b2f-191">*Argument typu*.</span><span class="sxs-lookup"><span data-stu-id="93b2f-191">*Type Argument*.</span></span> <span data-ttu-id="93b2f-192">Konkrétní datový typ, který nahrazuje parametr typu při deklaraci typu vytvořený z obecného typu.</span><span class="sxs-lookup"><span data-stu-id="93b2f-192">A specific data type that replaces a type parameter when you declare a constructed type from a generic type.</span></span>  
  
-   <span data-ttu-id="93b2f-193">*Omezení*.</span><span class="sxs-lookup"><span data-stu-id="93b2f-193">*Constraint*.</span></span> <span data-ttu-id="93b2f-194">Podmínkou na parametr typu, který omezuje argument typu můžete zadat pro něj.</span><span class="sxs-lookup"><span data-stu-id="93b2f-194">A condition on a type parameter that restricts the type argument you can supply for it.</span></span> <span data-ttu-id="93b2f-195">Omezení může vyžadovat, aby argument typu musí implementovat určité rozhraní, se konkrétní třídy dědí, mít dostupný konstruktor nebo být odkazového typu nebo typ hodnoty.</span><span class="sxs-lookup"><span data-stu-id="93b2f-195">A constraint can require that the type argument must implement a particular interface, be or inherit from a particular class, have an accessible parameterless constructor, or be a reference type or a value type.</span></span> <span data-ttu-id="93b2f-196">Zkombinováním těchto omezení, ale můžete zadat maximálně jednu třídu.</span><span class="sxs-lookup"><span data-stu-id="93b2f-196">You can combine these constraints, but you can specify at most one class.</span></span>  
  
-   <span data-ttu-id="93b2f-197">*Vytvořený typ*.</span><span class="sxs-lookup"><span data-stu-id="93b2f-197">*Constructed Type*.</span></span> <span data-ttu-id="93b2f-198">Třída, struktura, rozhraní, postup nebo delegáta deklarovat zadáním argumenty typu pro jeho parametry typu od obecného typu.</span><span class="sxs-lookup"><span data-stu-id="93b2f-198">A class, structure, interface, procedure, or delegate declared from a generic type by supplying type arguments for its type parameters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93b2f-199">Viz také</span><span class="sxs-lookup"><span data-stu-id="93b2f-199">See Also</span></span>  
 [<span data-ttu-id="93b2f-200">Datové typy</span><span class="sxs-lookup"><span data-stu-id="93b2f-200">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [<span data-ttu-id="93b2f-201">Znaky typu</span><span class="sxs-lookup"><span data-stu-id="93b2f-201">Type Characters</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)  
 [<span data-ttu-id="93b2f-202">Typy hodnot a odkazové typy</span><span class="sxs-lookup"><span data-stu-id="93b2f-202">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [<span data-ttu-id="93b2f-203">Převody typů v jazyce Visual Basic</span><span class="sxs-lookup"><span data-stu-id="93b2f-203">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="93b2f-204">Řešení potíží s datové typy</span><span class="sxs-lookup"><span data-stu-id="93b2f-204">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="93b2f-205">Datové typy</span><span class="sxs-lookup"><span data-stu-id="93b2f-205">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="93b2f-206">Z</span><span class="sxs-lookup"><span data-stu-id="93b2f-206">Of</span></span>](../../../../visual-basic/language-reference/statements/of-clause.md)  
 [<span data-ttu-id="93b2f-207">Jako</span><span class="sxs-lookup"><span data-stu-id="93b2f-207">As</span></span>](../../../../visual-basic/language-reference/statements/as-clause.md)  
 [<span data-ttu-id="93b2f-208">Object – datový typ</span><span class="sxs-lookup"><span data-stu-id="93b2f-208">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [<span data-ttu-id="93b2f-209">Kovariance a kontravariance</span><span class="sxs-lookup"><span data-stu-id="93b2f-209">Covariance and Contravariance</span></span>](../../concepts/covariance-contravariance/index.md)  
 [<span data-ttu-id="93b2f-210">Iterátory</span><span class="sxs-lookup"><span data-stu-id="93b2f-210">Iterators</span></span>](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)
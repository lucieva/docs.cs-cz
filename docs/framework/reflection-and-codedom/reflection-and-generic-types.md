---
title: "Reflexe a obecné typy"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- generics [.NET Framework], reflection emit
- reflection emit, generic types
- reflection, generic types
- type arguments
- generics [.NET Framework], reflection
- viewing type information
- type information, viewing
- types, generic
- type parameters
ms.assetid: f7180fc5-dd41-42d4-8a8e-1b34288e06de
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 99d8da622b23a98b8a48ad6fcdb82c270d24ed22
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="reflection-and-generic-types"></a><span data-ttu-id="b2506-102">Reflexe a obecné typy</span><span class="sxs-lookup"><span data-stu-id="b2506-102">Reflection and Generic Types</span></span>
<span data-ttu-id="b2506-103"><a name="top"></a>Z hlediska reflexe, rozdíl mezi obecného typu a typ obyčejnou je, že obecného typu má přidruženo sadu parametrů typů (je-li definice obecného typu) nebo zadejte argumenty (Pokud je vytvořený typ).</span><span class="sxs-lookup"><span data-stu-id="b2506-103"><a name="top"></a> From the point of view of reflection, the difference between a generic type and an ordinary type is that a generic type has associated with it a set of type parameters (if it is a generic type definition) or type arguments (if it is a constructed type).</span></span> <span data-ttu-id="b2506-104">Obecná metoda se liší od metody obyčejnou stejným způsobem.</span><span class="sxs-lookup"><span data-stu-id="b2506-104">A generic method differs from an ordinary method in the same way.</span></span>  
  
 <span data-ttu-id="b2506-105">Existují dva klíče k pochopení, jak reflexe zpracovává obecné typy a metody:</span><span class="sxs-lookup"><span data-stu-id="b2506-105">There are two keys to understanding how reflection handles generic types and methods:</span></span>  
  
-   <span data-ttu-id="b2506-106">Parametry typu definice obecného typu a definice obecné metody jsou reprezentované pomocí instance <xref:System.Type> třídy.</span><span class="sxs-lookup"><span data-stu-id="b2506-106">The type parameters of generic type definitions and generic method definitions are represented by instances of the <xref:System.Type> class.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b2506-107">Mnoho vlastností a metod <xref:System.Type> mají různé chování při <xref:System.Type> objekt představuje parametr obecného typu.</span><span class="sxs-lookup"><span data-stu-id="b2506-107">Many properties and methods of <xref:System.Type> have different behavior when a <xref:System.Type> object represents a generic type parameter.</span></span> <span data-ttu-id="b2506-108">Tyto rozdíly jsou popsané v tématech vlastnosti a metody.</span><span class="sxs-lookup"><span data-stu-id="b2506-108">These differences are documented in the property and method topics.</span></span> <span data-ttu-id="b2506-109">Například v tématu <xref:System.Type.IsAutoClass%2A> a <xref:System.Type.DeclaringType%2A>.</span><span class="sxs-lookup"><span data-stu-id="b2506-109">For example, see <xref:System.Type.IsAutoClass%2A> and <xref:System.Type.DeclaringType%2A>.</span></span> <span data-ttu-id="b2506-110">Kromě toho někteří členové jsou platné pouze tehdy, když <xref:System.Type> objekt představuje parametr obecného typu.</span><span class="sxs-lookup"><span data-stu-id="b2506-110">In addition, some members are valid only when a <xref:System.Type> object represents a generic type parameter.</span></span> <span data-ttu-id="b2506-111">Například v tématu <xref:System.Type.GetGenericTypeDefinition%2A>.</span><span class="sxs-lookup"><span data-stu-id="b2506-111">For example, see <xref:System.Type.GetGenericTypeDefinition%2A>.</span></span>  
  
-   <span data-ttu-id="b2506-112">Pokud instance <xref:System.Type> představuje obecného typu, pak obsahuje pole typů, které představují parametry typu (pro definice obecného typu) nebo argumenty typu (pro sestavené typy).</span><span class="sxs-lookup"><span data-stu-id="b2506-112">If an instance of <xref:System.Type> represents a generic type, then it includes an array of types that represent the type parameters (for generic type definitions) or the type arguments (for constructed types).</span></span> <span data-ttu-id="b2506-113">Totéž platí instance <xref:System.Reflection.MethodInfo> třídu, která představuje obecné metody.</span><span class="sxs-lookup"><span data-stu-id="b2506-113">The same is true of an instance of the <xref:System.Reflection.MethodInfo> class that represents a generic method.</span></span>  
  
 <span data-ttu-id="b2506-114">Poskytuje metody reflexe <xref:System.Type> a <xref:System.Reflection.MethodInfo> máte přístup k poli parametrů typu a určení, zda instanci <xref:System.Type> představuje parametr typu nebo skutečným typem.</span><span class="sxs-lookup"><span data-stu-id="b2506-114">Reflection provides methods of <xref:System.Type> and <xref:System.Reflection.MethodInfo> that allow you to access the array of type parameters, and to determine whether an instance of <xref:System.Type> represents a type parameter or an actual type.</span></span>  
  
 <span data-ttu-id="b2506-115">Například kód ukázka metody popsané v tomto poli, najdete v části [postup: Zkontrolujte a vytvořit instance obecných typů pomocí reflexe](../../../docs/framework/reflection-and-codedom/how-to-examine-and-instantiate-generic-types-with-reflection.md).</span><span class="sxs-lookup"><span data-stu-id="b2506-115">For example code demonstrating the methods discussed here, see [How to: Examine and Instantiate Generic Types with Reflection](../../../docs/framework/reflection-and-codedom/how-to-examine-and-instantiate-generic-types-with-reflection.md).</span></span>  
  
 <span data-ttu-id="b2506-116">Následující diskusi předpokládá znalost terminologie obecných typů, jako je rozdíl mezi typ parametry a argumenty a otevřené nebo zavřené sestavené typy.</span><span class="sxs-lookup"><span data-stu-id="b2506-116">The following discussion assumes familiarity with the terminology of generics, such as the difference between type parameters and arguments and open or closed constructed types.</span></span> <span data-ttu-id="b2506-117">Další informace najdete v tématu [obecné typy](../../../docs/standard/generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="b2506-117">For more information, see [Generics](../../../docs/standard/generics/index.md).</span></span>  
  
 <span data-ttu-id="b2506-118">Tento přehled se skládá z následujících částí:</span><span class="sxs-lookup"><span data-stu-id="b2506-118">This overview consists of the following sections:</span></span>  
  
-   [<span data-ttu-id="b2506-119">Obecný typ nebo metoda, je to?</span><span class="sxs-lookup"><span data-stu-id="b2506-119">Is This a Generic Type or Method?</span></span>](#is_this_a_generic_type_or_method)  
  
-   [<span data-ttu-id="b2506-120">Generování uzavřené obecné typy</span><span class="sxs-lookup"><span data-stu-id="b2506-120">Generating Closed Generic Types</span></span>](#generating_closed_generic_types)  
  
-   [<span data-ttu-id="b2506-121">Zkoumání argumenty Typ a parametry typu</span><span class="sxs-lookup"><span data-stu-id="b2506-121">Examining Type Arguments and Type Parameters</span></span>](#examining_type_arguments)  
  
-   [<span data-ttu-id="b2506-122">Výstupních podmínek</span><span class="sxs-lookup"><span data-stu-id="b2506-122">Invariants</span></span>](#invariants)  
  
-   [<span data-ttu-id="b2506-123">Související témata</span><span class="sxs-lookup"><span data-stu-id="b2506-123">Related Topics</span></span>](#related_topics)  
  
<a name="is_this_a_generic_type_or_method"></a>   
## <a name="is-this-a-generic-type-or-method"></a><span data-ttu-id="b2506-124">Obecný typ nebo metoda, je to?</span><span class="sxs-lookup"><span data-stu-id="b2506-124">Is This a Generic Type or Method?</span></span>  
 <span data-ttu-id="b2506-125">Při použití reflexe prozkoumat neznámého typu, reprezentována instanci <xref:System.Type>, použijte <xref:System.Type.IsGenericType%2A> vlastnosti k určení, zda je neznámý typ Obecné.</span><span class="sxs-lookup"><span data-stu-id="b2506-125">When you use reflection to examine an unknown type, represented by an instance of <xref:System.Type>, use the <xref:System.Type.IsGenericType%2A> property to determine whether the unknown type is generic.</span></span> <span data-ttu-id="b2506-126">Vrátí `true` Pokud typ je obecná.</span><span class="sxs-lookup"><span data-stu-id="b2506-126">It returns `true` if the type is generic.</span></span> <span data-ttu-id="b2506-127">Podobně když zkontrolujte Neznámá metoda, reprezentována instanci <xref:System.Reflection.MethodInfo> třídy, použijte <xref:System.Reflection.MethodInfo.IsGenericMethod%2A> vlastnosti k určení, zda je obecná metoda.</span><span class="sxs-lookup"><span data-stu-id="b2506-127">Similarly, when you examine an unknown method, represented by an instance of the <xref:System.Reflection.MethodInfo> class, use the <xref:System.Reflection.MethodInfo.IsGenericMethod%2A> property to determine whether the method is generic.</span></span>  
  
### <a name="is-this-a-generic-type-or-method-definition"></a><span data-ttu-id="b2506-128">Obecný typ nebo metoda definice, je to?</span><span class="sxs-lookup"><span data-stu-id="b2506-128">Is This a Generic Type or Method Definition?</span></span>  
 <span data-ttu-id="b2506-129">Použít <xref:System.Type.IsGenericTypeDefinition%2A> vlastnosti k určení zda <xref:System.Type> objekt představuje obecného typu definice a používání <xref:System.Reflection.MethodInfo.IsGenericMethodDefinition%2A> metoda k určení zda <xref:System.Reflection.MethodInfo> představuje definici obecná metoda.</span><span class="sxs-lookup"><span data-stu-id="b2506-129">Use the <xref:System.Type.IsGenericTypeDefinition%2A> property to determine whether a <xref:System.Type> object represents a generic type definition, and use the <xref:System.Reflection.MethodInfo.IsGenericMethodDefinition%2A> method to determine whether a <xref:System.Reflection.MethodInfo> represents a generic method definition.</span></span>  
  
 <span data-ttu-id="b2506-130">Obecné metody a typu definice jsou šablony, ze kterých instantiable typy jsou vytvořeny.</span><span class="sxs-lookup"><span data-stu-id="b2506-130">Generic type and method definitions are the templates from which instantiable types are created.</span></span> <span data-ttu-id="b2506-131">Obecné typy v knihovně tříd rozhraní .NET Framework, jako <xref:System.Collections.Generic.Dictionary%602>, jsou definice obecného typu.</span><span class="sxs-lookup"><span data-stu-id="b2506-131">Generic types in the .NET Framework class library, such as <xref:System.Collections.Generic.Dictionary%602>, are generic type definitions.</span></span>  
  
### <a name="is-the-type-or-method-open-or-closed"></a><span data-ttu-id="b2506-132">Typ nebo metoda otevřené nebo zavřené?</span><span class="sxs-lookup"><span data-stu-id="b2506-132">Is the Type or Method Open or Closed?</span></span>  
 <span data-ttu-id="b2506-133">Obecný typ nebo metoda je zavřený, pokud byla nahrazena instantiable typy pro všechny její parametry typu, včetně všech parametrů typu všech nadřazených typů.</span><span class="sxs-lookup"><span data-stu-id="b2506-133">A generic type or method is closed if instantiable types have been substituted for all its type parameters, including all the type parameters of all enclosing types.</span></span> <span data-ttu-id="b2506-134">Instance obecného typu můžete vytvořit, pouze pokud je uzavřený.</span><span class="sxs-lookup"><span data-stu-id="b2506-134">You can only create an instance of a generic type if it is closed.</span></span> <span data-ttu-id="b2506-135"><xref:System.Type.ContainsGenericParameters%2A?displayProperty=nameWithType> Vlastnost vrátí `true` Pokud typ je otevřený.</span><span class="sxs-lookup"><span data-stu-id="b2506-135">The <xref:System.Type.ContainsGenericParameters%2A?displayProperty=nameWithType> property returns `true` if a type is open.</span></span> <span data-ttu-id="b2506-136">Pro metody <xref:System.Reflection.MethodInfo.ContainsGenericParameters%2A?displayProperty=nameWithType> metoda provádí stejnou funkci.</span><span class="sxs-lookup"><span data-stu-id="b2506-136">For methods, the <xref:System.Reflection.MethodInfo.ContainsGenericParameters%2A?displayProperty=nameWithType> method performs the same function.</span></span>  
  
 [<span data-ttu-id="b2506-137">Zpět na začátek</span><span class="sxs-lookup"><span data-stu-id="b2506-137">Back to top</span></span>](#top)  
  
<a name="generating_closed_generic_types"></a>   
## <a name="generating-closed-generic-types"></a><span data-ttu-id="b2506-138">Generování uzavřené obecné typy</span><span class="sxs-lookup"><span data-stu-id="b2506-138">Generating Closed Generic Types</span></span>  
 <span data-ttu-id="b2506-139">Jakmile máte na obecný typ nebo metoda definice, použijte <xref:System.Type.MakeGenericType%2A> metodu pro vytvoření uzavřené obecného typu nebo <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A> metodu pro vytvoření <xref:System.Reflection.MethodInfo> pro uzavřená obecná metoda.</span><span class="sxs-lookup"><span data-stu-id="b2506-139">Once you have a generic type or method definition, use the <xref:System.Type.MakeGenericType%2A> method to create a closed generic type or the <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A> method to create a <xref:System.Reflection.MethodInfo> for a closed generic method.</span></span>  
  
### <a name="getting-the-generic-type-or-method-definition"></a><span data-ttu-id="b2506-140">Získávání obecného typu nebo definice – metoda</span><span class="sxs-lookup"><span data-stu-id="b2506-140">Getting the Generic Type or Method Definition</span></span>  
 <span data-ttu-id="b2506-141">Pokud máte otevřený obecný typ nebo metoda, která není obecný typ nebo metoda definice, nelze vytvořit její instance a není možné zadat parametry typu, které chybí.</span><span class="sxs-lookup"><span data-stu-id="b2506-141">If you have an open generic type or method that is not a generic type or method definition, you cannot create instances of it and you cannot supply the type parameters that are missing.</span></span> <span data-ttu-id="b2506-142">Musí mít obecný typ nebo metoda definice.</span><span class="sxs-lookup"><span data-stu-id="b2506-142">You must have a generic type or method definition.</span></span> <span data-ttu-id="b2506-143">Použití <xref:System.Type.GetGenericTypeDefinition%2A> metoda získat definice obecného typu nebo <xref:System.Reflection.MethodInfo.GetGenericMethodDefinition%2A> metoda získat definici obecná metoda.</span><span class="sxs-lookup"><span data-stu-id="b2506-143">Use the <xref:System.Type.GetGenericTypeDefinition%2A> method to obtain the generic type definition or the <xref:System.Reflection.MethodInfo.GetGenericMethodDefinition%2A> method to obtain the generic method definition.</span></span>  
  
 <span data-ttu-id="b2506-144">Pokud máte například <xref:System.Type> objekt reprezentující `Dictionary<int, string>` (`Dictionary(Of Integer, String)` v jazyce Visual Basic) a chcete vytvořit typ `Dictionary<string, MyClass>`, můžete použít <xref:System.Type.GetGenericTypeDefinition%2A> metodu za účelem získání <xref:System.Type> představující `Dictionary<TKey, TValue>` a potom pomocí <xref:System.Type.MakeGenericType%2A> metoda k vytvoření <xref:System.Type> představující `Dictionary<int, MyClass>`.</span><span class="sxs-lookup"><span data-stu-id="b2506-144">For example, if you have a <xref:System.Type> object representing `Dictionary<int, string>` (`Dictionary(Of Integer, String)` in Visual Basic) and you want to create the type `Dictionary<string, MyClass>`, you can use the <xref:System.Type.GetGenericTypeDefinition%2A> method to get a <xref:System.Type> representing `Dictionary<TKey, TValue>` and then use the <xref:System.Type.MakeGenericType%2A> method to produce a <xref:System.Type> representing `Dictionary<int, MyClass>`.</span></span>  
  
 <span data-ttu-id="b2506-145">Příklad otevřete obecného typu, který není obecného typu naleznete v části "Parametr typu nebo Argument typu" dál v tomto tématu.</span><span class="sxs-lookup"><span data-stu-id="b2506-145">For an example of an open generic type that is not a generic type, see "Type Parameter or Type Argument" later in this topic.</span></span>  
  
 [<span data-ttu-id="b2506-146">Zpět na začátek</span><span class="sxs-lookup"><span data-stu-id="b2506-146">Back to top</span></span>](#top)  
  
<a name="examining_type_arguments"></a>   
## <a name="examining-type-arguments-and-type-parameters"></a><span data-ttu-id="b2506-147">Zkoumání argumenty Typ a parametry typu</span><span class="sxs-lookup"><span data-stu-id="b2506-147">Examining Type Arguments and Type Parameters</span></span>  
 <span data-ttu-id="b2506-148">Použít <xref:System.Type.GetGenericArguments%2A?displayProperty=nameWithType> metoda získat pole <xref:System.Type> objekty, které představují parametry typu nebo typ argumenty obecného typu a použít <xref:System.Reflection.MethodInfo.GetGenericArguments%2A?displayProperty=nameWithType> metoda provedete stejný pro obecné metody.</span><span class="sxs-lookup"><span data-stu-id="b2506-148">Use the <xref:System.Type.GetGenericArguments%2A?displayProperty=nameWithType> method to obtain an array of <xref:System.Type> objects that represent the type parameters or type arguments of a generic type, and use the <xref:System.Reflection.MethodInfo.GetGenericArguments%2A?displayProperty=nameWithType> method to do the same for a generic method.</span></span>  
  
 <span data-ttu-id="b2506-149">Jakmile víte, že <xref:System.Type> představuje parametr typu objektu, existuje mnoho další otázky reflexe dokáže odpovědět.</span><span class="sxs-lookup"><span data-stu-id="b2506-149">Once you know that a <xref:System.Type> object represents a type parameter, there are many additional questions reflection can answer.</span></span> <span data-ttu-id="b2506-150">Můžete určit zdrojový parametr typu, jeho pozice a jeho omezení.</span><span class="sxs-lookup"><span data-stu-id="b2506-150">You can determine the type parameter's source, its position, and its constraints.</span></span>  
  
### <a name="type-parameter-or-type-argument"></a><span data-ttu-id="b2506-151">Argument typu nebo parametr typu</span><span class="sxs-lookup"><span data-stu-id="b2506-151">Type Parameter or Type Argument</span></span>  
 <span data-ttu-id="b2506-152">K určení, zda je parametr typu nebo typ argument konkrétní element pole, použijte <xref:System.Type.IsGenericParameter%2A> vlastnost.</span><span class="sxs-lookup"><span data-stu-id="b2506-152">To determine whether a particular element of the array is a type parameter or a type argument, use the <xref:System.Type.IsGenericParameter%2A> property.</span></span> <span data-ttu-id="b2506-153"><xref:System.Type.IsGenericParameter%2A> Vlastnost je `true` Pokud se element nachází parametr typu.</span><span class="sxs-lookup"><span data-stu-id="b2506-153">The <xref:System.Type.IsGenericParameter%2A> property is `true` if the element is a type parameter.</span></span>  
  
 <span data-ttu-id="b2506-154">Obecný typ může být otevřete, aniž by musel být definice obecného typu, v takovém případě má směs typu argumentů a parametrů typu.</span><span class="sxs-lookup"><span data-stu-id="b2506-154">A generic type can be open without being a generic type definition, in which case it has a mixture of type arguments and type parameters.</span></span> <span data-ttu-id="b2506-155">Například v následujícím kódu třídy `D` je odvozen z typu vytvořené nahraďte první parametr typu `D` pro druhý parametr typu `B`.</span><span class="sxs-lookup"><span data-stu-id="b2506-155">For example, in the following code, class `D` derives from a type created by substituting the first type parameter of `D` for the second type parameter of `B`.</span></span>  
  
```csharp  
class B<T, U> {}  
class D<V, W> : B<int, V> {}  
```  
  
```vb  
Class B(Of T, U)  
End Class  
Class D(Of V, W)  
    Inherits B(Of Integer, V)  
End Class  
```  
  
```cpp  
generic<typename T, typename U> ref class B {};  
generic<typename V, typename W> ref class D : B<int, V> {};  
```  
  
 <span data-ttu-id="b2506-156">Pokud získáte <xref:System.Type> objekt reprezentující `D<V, W>` a použít <xref:System.Type.BaseType%2A> vlastnost k získání jeho základní typ, výsledná `type B<int, V>` je otevřená, ale není definice obecného typu.</span><span class="sxs-lookup"><span data-stu-id="b2506-156">If you obtain a <xref:System.Type> object representing `D<V, W>` and use the <xref:System.Type.BaseType%2A> property to obtain its base type, the resulting `type B<int, V>` is open, but it is not a generic type definition.</span></span>  
  
### <a name="source-of-a-generic-parameter"></a><span data-ttu-id="b2506-157">Zdroj obecný parametr</span><span class="sxs-lookup"><span data-stu-id="b2506-157">Source of a Generic Parameter</span></span>  
 <span data-ttu-id="b2506-158">Parametr obecného typu může pocházet z typu, který je zkoumán, z vnějšího typu nebo z obecné metody.</span><span class="sxs-lookup"><span data-stu-id="b2506-158">A generic type parameter might come from the type you are examining, from an enclosing type, or from a generic method.</span></span> <span data-ttu-id="b2506-159">Můžete určit zdroj parametr obecného typu následujícím způsobem:</span><span class="sxs-lookup"><span data-stu-id="b2506-159">You can determine the source of the generic type parameter as follows:</span></span>  
  
-   <span data-ttu-id="b2506-160">Nejprve pomocí <xref:System.Type.DeclaringMethod%2A> vlastnosti k určení, zda parametr typu pochází z obecná metoda.</span><span class="sxs-lookup"><span data-stu-id="b2506-160">First, use the <xref:System.Type.DeclaringMethod%2A> property to determine whether the type parameter comes from a generic method.</span></span> <span data-ttu-id="b2506-161">Pokud hodnota vlastnosti není odkaz s hodnotou null (`Nothing` v jazyce Visual Basic), pak zdroj je obecná metoda.</span><span class="sxs-lookup"><span data-stu-id="b2506-161">If the property value is not a null reference (`Nothing` in Visual Basic), then the source is a generic method.</span></span>  
  
-   <span data-ttu-id="b2506-162">Pokud zdroj není obecná metoda, použijte <xref:System.Type.DeclaringType%2A> patří vlastnosti k určení obecného typu parametr obecného typu.</span><span class="sxs-lookup"><span data-stu-id="b2506-162">If the source is not a generic method, use the <xref:System.Type.DeclaringType%2A> property to determine the generic type the generic type parameter belongs to.</span></span>  
  
 <span data-ttu-id="b2506-163">Pokud parametr typu patří do obecné metody <xref:System.Type.DeclaringType%2A> vlastnost vrací typ, který deklarovaný obecná metoda, která je důležité.</span><span class="sxs-lookup"><span data-stu-id="b2506-163">If the type parameter belongs to a generic method, the <xref:System.Type.DeclaringType%2A> property returns the type that declared the generic method, which is irrelevant.</span></span>  
  
### <a name="position-of-a-generic-parameter"></a><span data-ttu-id="b2506-164">Pozice obecný parametr</span><span class="sxs-lookup"><span data-stu-id="b2506-164">Position of a Generic Parameter</span></span>  
 <span data-ttu-id="b2506-165">Ve výjimečných případech je potřeba určit umístění parametr typu v seznamu parametrů typu jeho deklarující třídy.</span><span class="sxs-lookup"><span data-stu-id="b2506-165">In rare situations, it is necessary to determine the position of a type parameter in the type parameter list of its declaring class.</span></span> <span data-ttu-id="b2506-166">Předpokládejme například, že máte <xref:System.Type> objekt reprezentující `B<int, V>` typ z předchozího příkladu.</span><span class="sxs-lookup"><span data-stu-id="b2506-166">For example, suppose you have a <xref:System.Type> object representing the `B<int, V>` type from the preceding example.</span></span> <span data-ttu-id="b2506-167"><xref:System.Type.GetGenericArguments%2A> Metoda vám poskytne seznam argumentů typu a při kontrole `V` můžete použít <xref:System.Type.DeclaringMethod%2A> a <xref:System.Type.DeclaringType%2A> vlastnosti, které chcete zjistit, které pocházejí z.</span><span class="sxs-lookup"><span data-stu-id="b2506-167">The <xref:System.Type.GetGenericArguments%2A> method gives you a list of type arguments, and when you examine `V` you can use the <xref:System.Type.DeclaringMethod%2A> and <xref:System.Type.DeclaringType%2A> properties to discover where it comes from.</span></span> <span data-ttu-id="b2506-168">Pak můžete použít <xref:System.Type.GenericParameterPosition%2A> vlastnosti k určení pozici v seznamu parametrů typu kterých byla definována.</span><span class="sxs-lookup"><span data-stu-id="b2506-168">You can then use the <xref:System.Type.GenericParameterPosition%2A> property to determine its position in the type parameter list where it was defined.</span></span> <span data-ttu-id="b2506-169">V tomto příkladu `V` je na pozici 0 (nula) v seznamu Typ parametru, kde byl definován.</span><span class="sxs-lookup"><span data-stu-id="b2506-169">In this example, `V` is at position 0 (zero) in the type parameter list where it was defined.</span></span>  
  
### <a name="base-type-and-interface-constraints"></a><span data-ttu-id="b2506-170">Základní typ a omezení rozhraní</span><span class="sxs-lookup"><span data-stu-id="b2506-170">Base Type and Interface Constraints</span></span>  
 <span data-ttu-id="b2506-171">Použití <xref:System.Type.GetGenericParameterConstraints%2A> metoda získat základní typ omezení a rozhraní omezení typu parametru.</span><span class="sxs-lookup"><span data-stu-id="b2506-171">Use the <xref:System.Type.GetGenericParameterConstraints%2A> method to obtain the base type constraint and interface constraints of a type parameter.</span></span> <span data-ttu-id="b2506-172">Pořadí prvků pole není důležité.</span><span class="sxs-lookup"><span data-stu-id="b2506-172">The order of the elements of the array is not significant.</span></span> <span data-ttu-id="b2506-173">Element reprezentuje omezení rozhraní, pokud je typ rozhraní.</span><span class="sxs-lookup"><span data-stu-id="b2506-173">An element represents an interface constraint if it is an interface type.</span></span>  
  
### <a name="generic-parameter-attributes"></a><span data-ttu-id="b2506-174">Obecný parametr atributy</span><span class="sxs-lookup"><span data-stu-id="b2506-174">Generic Parameter Attributes</span></span>  
 <span data-ttu-id="b2506-175"><xref:System.Type.GenericParameterAttributes%2A> Získá vlastnost <xref:System.Reflection.GenericParameterAttributes> hodnotu, která určuje odchylku (kovariance a kontravariance) a speciální omezení typu parametru.</span><span class="sxs-lookup"><span data-stu-id="b2506-175">The <xref:System.Type.GenericParameterAttributes%2A> property gets a <xref:System.Reflection.GenericParameterAttributes> value that indicates the variance (covariance or contravariance) and the special constraints of a type parameter.</span></span>  
  
#### <a name="covariance-and-contravariance"></a><span data-ttu-id="b2506-176">Kovariance a kontravariance</span><span class="sxs-lookup"><span data-stu-id="b2506-176">Covariance and Contravariance</span></span>  
 <span data-ttu-id="b2506-177">Pokud chcete zjistit, jestli se parametr typu je kovariant nebo kontravariant, použít <xref:System.Reflection.GenericParameterAttributes.VarianceMask?displayProperty=nameWithType> maskování na <xref:System.Reflection.GenericParameterAttributes> hodnotu, která je vrácený <xref:System.Type.GenericParameterAttributes%2A> vlastnost.</span><span class="sxs-lookup"><span data-stu-id="b2506-177">To determine whether a type parameter is covariant or contravariant, apply the <xref:System.Reflection.GenericParameterAttributes.VarianceMask?displayProperty=nameWithType> mask to the <xref:System.Reflection.GenericParameterAttributes> value that is returned by the <xref:System.Type.GenericParameterAttributes%2A> property.</span></span> <span data-ttu-id="b2506-178">Pokud je výsledek <xref:System.Reflection.GenericParameterAttributes.None?displayProperty=nameWithType>, parametr typu je neutrální.</span><span class="sxs-lookup"><span data-stu-id="b2506-178">If the result is <xref:System.Reflection.GenericParameterAttributes.None?displayProperty=nameWithType>, the type parameter is invariant.</span></span> <span data-ttu-id="b2506-179">V tématu [kovariance a kontravariance](../../../docs/standard/generics/covariance-and-contravariance.md).</span><span class="sxs-lookup"><span data-stu-id="b2506-179">See [Covariance and Contravariance](../../../docs/standard/generics/covariance-and-contravariance.md).</span></span>  
  
#### <a name="special-constraints"></a><span data-ttu-id="b2506-180">Zvláštní omezení</span><span class="sxs-lookup"><span data-stu-id="b2506-180">Special Constraints</span></span>  
 <span data-ttu-id="b2506-181">K určení speciálních omezení parametr typu, použít <xref:System.Reflection.GenericParameterAttributes.SpecialConstraintMask?displayProperty=nameWithType> maskování na <xref:System.Reflection.GenericParameterAttributes> hodnotu, která je vrácený <xref:System.Type.GenericParameterAttributes%2A> vlastnost.</span><span class="sxs-lookup"><span data-stu-id="b2506-181">To determine the special constraints of a type parameter, apply the <xref:System.Reflection.GenericParameterAttributes.SpecialConstraintMask?displayProperty=nameWithType> mask to the <xref:System.Reflection.GenericParameterAttributes> value that is returned by the <xref:System.Type.GenericParameterAttributes%2A> property.</span></span> <span data-ttu-id="b2506-182">Pokud je výsledek <xref:System.Reflection.GenericParameterAttributes.None?displayProperty=nameWithType>, neexistují žádné zvláštní omezení.</span><span class="sxs-lookup"><span data-stu-id="b2506-182">If the result is <xref:System.Reflection.GenericParameterAttributes.None?displayProperty=nameWithType>, there are no special constraints.</span></span> <span data-ttu-id="b2506-183">Parametr typu může být omezené být odkazového typu, musí být typu hodnot neumožňující hodnotu Null a mít výchozí konstruktor.</span><span class="sxs-lookup"><span data-stu-id="b2506-183">A type parameter can be constrained to be a reference type, to be a non-nullable value type, and to have a default constructor.</span></span>  
  
 [<span data-ttu-id="b2506-184">Zpět na začátek</span><span class="sxs-lookup"><span data-stu-id="b2506-184">Back to top</span></span>](#top)  
  
<a name="invariants"></a>   
## <a name="invariants"></a><span data-ttu-id="b2506-185">Výstupních podmínek</span><span class="sxs-lookup"><span data-stu-id="b2506-185">Invariants</span></span>  
 <span data-ttu-id="b2506-186">Tabulku invariantní podmínky pro běžné podmínky v reflexe pro obecné typy, najdete v části <xref:System.Type.IsGenericType%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b2506-186">For a table of the invariant conditions for common terms in reflection for generic types, see <xref:System.Type.IsGenericType%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b2506-187">Další podmínky týkající se obecné metody, najdete v části <xref:System.Reflection.MethodInfo.IsGenericMethod%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b2506-187">For additional terms relating to generic methods, see <xref:System.Reflection.MethodInfo.IsGenericMethod%2A?displayProperty=nameWithType>.</span></span>  
  
 [<span data-ttu-id="b2506-188">Zpět na začátek</span><span class="sxs-lookup"><span data-stu-id="b2506-188">Back to top</span></span>](#top)  
  
<a name="related_topics"></a>   
## <a name="related-topics"></a><span data-ttu-id="b2506-189">Související témata</span><span class="sxs-lookup"><span data-stu-id="b2506-189">Related Topics</span></span>  
  
|<span data-ttu-id="b2506-190">Název</span><span class="sxs-lookup"><span data-stu-id="b2506-190">Title</span></span>|<span data-ttu-id="b2506-191">Popis</span><span class="sxs-lookup"><span data-stu-id="b2506-191">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="b2506-192">Postupy: prozkoumání a vytvoření instancí obecných typů pomocí reflexe</span><span class="sxs-lookup"><span data-stu-id="b2506-192">How to: Examine and Instantiate Generic Types with Reflection</span></span>](../../../docs/framework/reflection-and-codedom/how-to-examine-and-instantiate-generic-types-with-reflection.md)|<span data-ttu-id="b2506-193">Ukazuje, jak pomocí vlastnosti a metody <xref:System.Type> a <xref:System.Reflection.MethodInfo> prozkoumat obecné typy.</span><span class="sxs-lookup"><span data-stu-id="b2506-193">Shows how to use the properties and methods of <xref:System.Type> and <xref:System.Reflection.MethodInfo> to examine generic types.</span></span>|  
|[<span data-ttu-id="b2506-194">Obecné typy</span><span class="sxs-lookup"><span data-stu-id="b2506-194">Generics</span></span>](../../../docs/standard/generics/index.md)|<span data-ttu-id="b2506-195">Popisuje funkce obecných typů a jak je podporována v rozhraní .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b2506-195">Describes the generics feature and how it is supported in the .NET Framework.</span></span>|  
|[<span data-ttu-id="b2506-196">Postupy: definování obecného typu pomocí reflexe emitování</span><span class="sxs-lookup"><span data-stu-id="b2506-196">How to: Define a Generic Type with Reflection Emit</span></span>](../../../docs/framework/reflection-and-codedom/how-to-define-a-generic-type-with-reflection-emit.md)|<span data-ttu-id="b2506-197">Ukazuje, jak pomocí reflexe emitování ke generování obecné typy v dynamických sestavení.</span><span class="sxs-lookup"><span data-stu-id="b2506-197">Shows how to use reflection emit to generate generic types in dynamic assemblies.</span></span>|  
|[<span data-ttu-id="b2506-198">Zobrazení informací o typu</span><span class="sxs-lookup"><span data-stu-id="b2506-198">Viewing Type Information</span></span>](../../../docs/framework/reflection-and-codedom/viewing-type-information.md)|<span data-ttu-id="b2506-199">Popisuje <xref:System.Type> třídy a poskytuje příklady kódu, které ukazují, jak používat <xref:System.Type> s různými třídami reflexe ke získání informací o konstruktory, metody, pole, vlastnosti a události.</span><span class="sxs-lookup"><span data-stu-id="b2506-199">Describes the <xref:System.Type> class and provides code examples that illustrate how to use <xref:System.Type> with various reflection classes to obtain information about constructors, methods, fields, properties, and events.</span></span>|
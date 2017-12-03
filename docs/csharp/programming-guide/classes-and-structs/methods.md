---
title: "Metody (Průvodce programováním v C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- methods [C#]
- C# language, methods
ms.assetid: cc738f07-e8cd-4683-9585-9f40c0667c37
caps.latest.revision: "41"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ff6e59f70a5718f6616fa9a585dd84144e1774a0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="methods-c-programming-guide"></a><span data-ttu-id="6d7f5-102">Metody (Průvodce programováním v C#)</span><span class="sxs-lookup"><span data-stu-id="6d7f5-102">Methods (C# Programming Guide)</span></span>
<span data-ttu-id="6d7f5-103">Metoda je blok kódu, který obsahuje řadu příkazů.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-103">A method is a code block that contains a series of statements.</span></span> <span data-ttu-id="6d7f5-104">Program způsobí, že příkazy provádět volání metody a zadání argumentů požadovaná metoda.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-104">A program causes the statements to be executed by calling the method and specifying any required method arguments.</span></span> <span data-ttu-id="6d7f5-105">V jazyce C# každé spuštění instrukce se provádí v kontextu metody.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-105">In C#, every executed instruction is performed in the context of a method.</span></span> <span data-ttu-id="6d7f5-106">Hlavní metoda je vstupní bod pro každou aplikaci C# a je volána metodou common language runtime (CLR) při spuštění programu.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-106">The Main method is the entry point for every C# application and it is called by the common language runtime (CLR) when the program is started.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6d7f5-107">Toto téma popisuje pojmenované metody.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-107">This topic discusses named methods.</span></span> <span data-ttu-id="6d7f5-108">Informace o anonymní funkce najdete v tématu [anonymní funkce](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).</span><span class="sxs-lookup"><span data-stu-id="6d7f5-108">For information about anonymous functions, see [Anonymous Functions](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).</span></span>  
  
## <a name="method-signatures"></a><span data-ttu-id="6d7f5-109">Podpisy – metoda</span><span class="sxs-lookup"><span data-stu-id="6d7f5-109">Method Signatures</span></span>  
 <span data-ttu-id="6d7f5-110">Metody, které jsou deklarované v [třída](../../../csharp/language-reference/keywords/class.md) nebo [struktura](../../../csharp/language-reference/keywords/struct.md) zadáním úroveň přístupu, jako `public` nebo `private`, volitelné modifikátory jako `abstract` nebo `sealed`, návratový hodnota, název metody a všechny parametry metody.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-110">Methods are declared in a [class](../../../csharp/language-reference/keywords/class.md) or [struct](../../../csharp/language-reference/keywords/struct.md) by specifying the access level such as `public` or `private`, optional modifiers such as `abstract` or `sealed`, the return value, the name of the method, and any method parameters.</span></span> <span data-ttu-id="6d7f5-111">Následující části jsou společně podpis metody.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-111">These parts together are the signature of the method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6d7f5-112">Návratový typ metody není součástí podpis metody pro účely přetěžování metody.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-112">A return type of a method is not part of the signature of the method for the purposes of method overloading.</span></span> <span data-ttu-id="6d7f5-113">Je však součástí podpis metody při určování kompatibilitu mezi delegáta a metodu, která odkazuje na.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-113">However, it is part of the signature of the method when determining the compatibility between a delegate and the method that it points to.</span></span>  
  
 <span data-ttu-id="6d7f5-114">Parametry metody jsou uzavřené v závorkách a jsou odděleny čárkami.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-114">Method parameters are enclosed in parentheses and are separated by commas.</span></span> <span data-ttu-id="6d7f5-115">Závorky, jinak znamenat, že metoda nevyžaduje žádné parametry.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-115">Empty parentheses indicate that the method requires no parameters.</span></span> <span data-ttu-id="6d7f5-116">Tato třída obsahuje tři metody:</span><span class="sxs-lookup"><span data-stu-id="6d7f5-116">This class contains three methods:</span></span>  
  
 [!code-csharp[csProgGuideObjects#40](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/methods_1.cs)]  
  
## <a name="method-access"></a><span data-ttu-id="6d7f5-117">Přístup k metodě</span><span class="sxs-lookup"><span data-stu-id="6d7f5-117">Method Access</span></span>  
 <span data-ttu-id="6d7f5-118">Volání metody objektu je jako přístup k poli.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-118">Calling a method on an object is like accessing a field.</span></span> <span data-ttu-id="6d7f5-119">Po názvu objektu přidáte období, název metody, a kulaté závorky.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-119">After the object name, add a period, the name of the method, and parentheses.</span></span> <span data-ttu-id="6d7f5-120">Argumenty jsou uvedeny v závorkách a jsou odděleny čárkami.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-120">Arguments are listed within the parentheses, and are separated by commas.</span></span> <span data-ttu-id="6d7f5-121">Metody `Motorcycle` třída proto nelze volat jako v následujícím příkladu:</span><span class="sxs-lookup"><span data-stu-id="6d7f5-121">The methods of the `Motorcycle` class can therefore be called as in the following example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#41](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/methods_2.cs)]  
  
## <a name="method-parameters-vs-arguments"></a><span data-ttu-id="6d7f5-122">Parametry metody vs. Arguments</span><span class="sxs-lookup"><span data-stu-id="6d7f5-122">Method Parameters vs. Arguments</span></span>  
 <span data-ttu-id="6d7f5-123">Definice metoda určuje názvy a typy parametrů, které jsou požadovány.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-123">The method definition specifies the names and types of any parameters that are required.</span></span> <span data-ttu-id="6d7f5-124">Při volání metody kód zavolá metodu, poskytuje konkrétní hodnoty nazývaných argumenty pro jednotlivé parametry.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-124">When calling code calls the method, it provides concrete values called arguments for each parameter.</span></span> <span data-ttu-id="6d7f5-125">Argumenty, které musí být kompatibilní s typem parametru ale argument jméno (pokud existuje) použité v kód volání nemusí být stejný jako parametr s názvem definované v metodě.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-125">The arguments must be compatible with the parameter type but the argument name (if any) used in the calling code does not have to be the same as the parameter named defined in the method.</span></span> <span data-ttu-id="6d7f5-126">Příklad:</span><span class="sxs-lookup"><span data-stu-id="6d7f5-126">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#74](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/methods_3.cs)]  
  
## <a name="passing-by-reference-vs-passing-by-value"></a><span data-ttu-id="6d7f5-127">Předání odkaz vs. Předání hodnotou</span><span class="sxs-lookup"><span data-stu-id="6d7f5-127">Passing by Reference vs. Passing by Value</span></span>  
 <span data-ttu-id="6d7f5-128">Ve výchozím nastavení když typ hodnoty je předána metodě, je kopie předán místo samotného objektu.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-128">By default, when a value type is passed to a method, a copy is passed instead of the object itself.</span></span> <span data-ttu-id="6d7f5-129">Změny argument tedy mít žádný vliv na původní kopie v metodě volání.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-129">Therefore, changes to the argument have no effect on the original copy in the calling method.</span></span> <span data-ttu-id="6d7f5-130">Typ hodnoty odkazem můžete předat pomocí ref – klíčové slovo.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-130">You can pass a value-type by reference by using the ref keyword.</span></span> <span data-ttu-id="6d7f5-131">Další informace najdete v tématu [předávání parametrů typu hodnoty](../../../csharp/programming-guide/classes-and-structs/passing-value-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="6d7f5-131">For more information, see [Passing Value-Type Parameters](../../../csharp/programming-guide/classes-and-structs/passing-value-type-parameters.md).</span></span> <span data-ttu-id="6d7f5-132">Seznam typů předdefinovaných hodnot najdete v tématu [Tabulka typů hodnot](../../../csharp/language-reference/keywords/value-types-table.md).</span><span class="sxs-lookup"><span data-stu-id="6d7f5-132">For a list of built-in value types, see [Value Types Table](../../../csharp/language-reference/keywords/value-types-table.md).</span></span>  
  
 <span data-ttu-id="6d7f5-133">Když metoda předána objekt typu odkazu, odkaz na objekt je předán.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-133">When an object of a reference type is passed to a method, a reference to the object is passed.</span></span> <span data-ttu-id="6d7f5-134">To znamená metoda obdrží, ale ne samotný objekt argument, který určuje umístění objektu.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-134">That is, the method receives not the object itself but an argument that indicates the location of the object.</span></span> <span data-ttu-id="6d7f5-135">Pokud změníte členem objektu pomocí tohoto odkazu, změny se v argumentu v metodě volání, i když tento objekt předat hodnotu.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-135">If you change a member of the object by using this reference, the change is reflected in the argument in the calling method, even if you pass the object by value.</span></span>  
  
 <span data-ttu-id="6d7f5-136">Vytvoření typu odkazu pomocí `class` – klíčové slovo, jak ukazuje následující příklad.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-136">You create a reference type by using the `class` keyword, as the following example shows.</span></span>  
  
 [!code-csharp[csProgGuideObjects#42](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/methods_4.cs)]  
  
 <span data-ttu-id="6d7f5-137">Nyní Pokud předáte objekt, který je založen na tento typ a metodu, je předaná odkaz na objekt.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-137">Now, if you pass an object that is based on this type to a method, a reference to the object is passed.</span></span> <span data-ttu-id="6d7f5-138">Následující příklad předá objekt typu `SampleRefType` metodě `ModifyObject`.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-138">The following example passes an object of type `SampleRefType` to method `ModifyObject`.</span></span>  
  
 [!code-csharp[csProgGuideObjects#75](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/methods_5.cs)]  
  
 <span data-ttu-id="6d7f5-139">V příkladu nemá v podstatě má stejnou funkci jako předchozí příklad, předá argumentu podle hodnoty metodu.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-139">The example does essentially the same thing as the previous example in that it passes an argument by value to a method.</span></span> <span data-ttu-id="6d7f5-140">Ale protože odkaz na typ se používá, výsledek se liší.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-140">But, because a reference type is used, the result is different.</span></span> <span data-ttu-id="6d7f5-141">Změna, která se provádí v `ModifyObject` k `value` pole parametru, `obj`, také změní `value` pole argumentu, `rt`v `TestRefType` metoda.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-141">The modification that is made in `ModifyObject` to the `value` field of the parameter, `obj`, also changes the `value` field of the argument, `rt`, in the `TestRefType` method.</span></span> <span data-ttu-id="6d7f5-142">`TestRefType` Metoda zobrazí 33 jako výstup.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-142">The `TestRefType` method displays 33 as the output.</span></span>  
  
 <span data-ttu-id="6d7f5-143">Další informace o tom, jak předat odkazové typy odkazem a hodnotou najdete v tématu [předávání parametrů typu odkazu](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md) a [odkazové typy](../../../csharp/language-reference/keywords/reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="6d7f5-143">For more information about how to pass reference types by reference and by value, see [Passing Reference-Type Parameters](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md) and [Reference Types](../../../csharp/language-reference/keywords/reference-types.md).</span></span>  
  
## <a name="return-values"></a><span data-ttu-id="6d7f5-144">Návratové hodnoty</span><span class="sxs-lookup"><span data-stu-id="6d7f5-144">Return Values</span></span>  
<span data-ttu-id="6d7f5-145">Metody můžete vrátit hodnotu volajícímu.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-145">Methods can return a value to the caller.</span></span> <span data-ttu-id="6d7f5-146">Pokud je návratový typ, není typu uvedené před název metody `void`, metoda může vrátit hodnotu pomocí `return` – klíčové slovo.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-146">If the return type, the type listed before the method name, is not `void`, the method can return the value by using the `return` keyword.</span></span> <span data-ttu-id="6d7f5-147">Příkaz s `return` – klíčové slovo, za nímž následuje hodnotu, která odpovídá návratový typ, vrátí tuto hodnotu Metoda volajícímu.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-147">A statement with the `return` keyword followed by a value that matches the return type will return that value to the method caller.</span></span> 

<span data-ttu-id="6d7f5-148">Hodnota může být vrácen volajícímu hodnotu nebo, počínaje C# 7, [odkazem](ref-returns.md).</span><span class="sxs-lookup"><span data-stu-id="6d7f5-148">The value can be returned to the caller by value or, starting with C# 7, [by reference](ref-returns.md).</span></span> <span data-ttu-id="6d7f5-149">Hodnoty jsou vráceny volajícímu odkazem, pokud `ref` – klíčové slovo se používá v podpis metody a postupuje každý `return` – klíčové slovo.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-149">Values are returned to the caller by reference if the `ref` keyword is used in the method signature and it follows each `return` keyword.</span></span> <span data-ttu-id="6d7f5-150">Například následující příkaz podpisu a vraťte se metoda znamenat, že metoda vrátí názvy proměnných `estDistance` odkazem na volajícího.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-150">For example, the following method signature and return statement indicate that the method returns a variable names `estDistance` by reference to the caller.</span></span>

```csharp
public ref double GetEstimatedDistance()
{
   return ref estDistance;
}
```

<span data-ttu-id="6d7f5-151">`return` – Klíčové slovo také zastaví provádění metody.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-151">The `return` keyword also stops the execution of the method.</span></span> <span data-ttu-id="6d7f5-152">Pokud je návratový typ `void`, `return` je stále užitečné zastavit provádění metody příkaz bez hodnoty.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-152">If the return type is `void`, a `return` statement without a value is still useful to stop the execution of the method.</span></span> <span data-ttu-id="6d7f5-153">Bez `return` – klíčové slovo, metoda skončí při ukončení bloku kódu.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-153">Without the `return` keyword, the method will stop executing when it reaches the end of the code block.</span></span> <span data-ttu-id="6d7f5-154">Metody s není void vrací typ jsou nutné k použití `return` – klíčové slovo bude vrácena hodnota.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-154">Methods with a non-void return type are required to use the `return` keyword to return a value.</span></span> <span data-ttu-id="6d7f5-155">Například použít tyto dvě metody `return` – klíčové slovo vrátit celá čísla:</span><span class="sxs-lookup"><span data-stu-id="6d7f5-155">For example, these two methods use the `return` keyword to return integers:</span></span>  
  
 [!code-csharp[csProgGuideObjects#44](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/methods_6.cs)]  
  
 <span data-ttu-id="6d7f5-156">Pokud chcete použít hodnotu, vrátí metoda, můžete použít metodu volání volání metody samotné kdekoli hodnota stejného typu by být dostatečná.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-156">To use a value returned from a method, the calling method can use the method call itself anywhere a value of the same type would be sufficient.</span></span> <span data-ttu-id="6d7f5-157">Můžete také přiřadit návratovou hodnotu proměnné.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-157">You can also assign the return value to a variable.</span></span> <span data-ttu-id="6d7f5-158">Například následující příklady kódu dvě dosažení stejné cíle:</span><span class="sxs-lookup"><span data-stu-id="6d7f5-158">For example, the following two code examples accomplish the same goal:</span></span>  
  
 [!code-csharp[csProgGuideObjects#45](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/methods_7.cs)]  
  
 [!code-csharp[csProgGuideObjects#46](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/methods_8.cs)]  
  
 <span data-ttu-id="6d7f5-159">Použití místní proměnné, v takovém případě `result`, ukládat hodnota je volitelná.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-159">Using a local variable, in this case, `result`, to store a value is optional.</span></span> <span data-ttu-id="6d7f5-160">Dobře čitelnost kódu, nebo může být nutné, pokud je třeba uložit původní hodnota argumentu pro celý rozsah metodu.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-160">It may help the readability of the code, or it may be necessary if you need to store the original value of the argument for the entire scope of the method.</span></span>  

<span data-ttu-id="6d7f5-161">Na používání hodnoty vrácené odkaz z metody, je třeba deklarovat [ref místní](ref-returns.md#ref-locals) proměnná, pokud chcete upravit její hodnotu.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-161">To use a value returned by reference from a method, you must declare a [ref local](ref-returns.md#ref-locals) variable if you intend to modify its value.</span></span> <span data-ttu-id="6d7f5-162">Například pokud `Planet.GetEstimatedDistance` metoda vrátí <xref:System.Double> hodnotu odkazem, můžete ji definovat jako místní proměnné ref kódem takto:</span><span class="sxs-lookup"><span data-stu-id="6d7f5-162">For example, if the `Planet.GetEstimatedDistance` method returns a <xref:System.Double> value by reference, you can define it as a ref local variable with code like the following:</span></span>

```csharp
ref int distance = plant 
```

<span data-ttu-id="6d7f5-163">Vrácení vícerozměrné z metody, `M`, která mění tohoto pole obsah není nutné v případě, že pole do předána volání funkce `M`.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-163">Returning a multi-dimensional array from a method, `M`, that modifies the array's contents is not necessary if the calling function passed the array into `M`.</span></span>  <span data-ttu-id="6d7f5-164">Může vrátit výsledné pole z `M` pro dobrý styl nebo funkční toku hodnoty, ale není nutné, protože C# předá všechny odkazové typy podle hodnoty a odkaz na pole hodnotu má ukazatel na pole.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-164">You may return the resulting array from `M` for good style or functional flow of values, but it is not necessary because C# passes all reference types by value, and the value of an array reference is the pointer to the array.</span></span> <span data-ttu-id="6d7f5-165">V metodě `M`, všechny změny do tohoto pole obsahu, jsou lze zobrazit pomocí kód, který obsahuje odkaz na pole, jak je znázorněno v následujícím příkladu.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-165">In the method `M`, any changes to the array's contents are observable by any code that has a reference to the array, as shown in the following example.</span></span>  
  
```csharp  
static void Main(string[] args)  
        {  
            int[,] matrix = new int[2, 2];  
            FillMatrix(matrix);  
            // matrix is now full of -1  
        }  
  
        public static void FillMatrix(int[,] matrix)  
        {  
            for (int i = 0; i < matrix.GetLength(0); i++)  
            {  
                for (int j = 0; j < matrix.GetLength(1); j++)  
                {  
                    matrix[i, j] = -1;  
                }  
            }  
        }  
```  
  
 <span data-ttu-id="6d7f5-166">Další informace najdete v tématu [vrátit](../../../csharp/language-reference/keywords/return.md).</span><span class="sxs-lookup"><span data-stu-id="6d7f5-166">For more information, see [return](../../../csharp/language-reference/keywords/return.md).</span></span>  
  
## <a name="async-methods"></a><span data-ttu-id="6d7f5-167">Asynchronní metody</span><span class="sxs-lookup"><span data-stu-id="6d7f5-167">Async Methods</span></span>  
 <span data-ttu-id="6d7f5-168">Pomocí funkce asynchronní můžete vyvolat asynchronních metod bez použití explicitní zpětná volání nebo Ruční rozdělení kódu mezi více metod nebo výrazy lambda.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-168">By using the async feature, you can invoke asynchronous methods without using explicit callbacks or manually splitting your code across multiple methods or lambda expressions.</span></span> 
  
 <span data-ttu-id="6d7f5-169">Pokud označíte metodu s [asynchronní](../../../csharp/language-reference/keywords/async.md) modifikátor, můžete použít [await](../../../csharp/language-reference/keywords/await.md) operátor v metodě.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-169">If you mark a method with the [async](../../../csharp/language-reference/keywords/async.md) modifier, you can use the [await](../../../csharp/language-reference/keywords/await.md) operator in the method.</span></span> <span data-ttu-id="6d7f5-170">Když řízení dosáhne výraz await v asynchronní metody, řízení vrátí volajícímu a průběh v metodě je pozastaveno, dokud dokončení awaited úlohy.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-170">When control reaches an await expression in the async method, control returns to the caller, and progress in the method is suspended until the awaited task completes.</span></span> <span data-ttu-id="6d7f5-171">Po dokončení úlohy provádění může pokračovat v metodě.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-171">When the task is complete, execution can resume in the method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6d7f5-172">Asynchronní metody vrátí volající, pokud zjistí první awaited objekt, který ještě není dokončena nebo získá na konec asynchronní metody, cokoliv nastane dříve.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-172">An async method returns to the caller when either it encounters the first awaited object that’s not yet complete or it gets to the end of the async method, whichever occurs first.</span></span>  
  
 <span data-ttu-id="6d7f5-173">Asynchronní metody může mít návratový typ <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.Task>, nebo void.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-173">An async method can have a return type of <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.Task>, or void.</span></span> <span data-ttu-id="6d7f5-174">Typ vrácené hodnoty void slouží především k definování obslužné rutiny událostí, kdy je potřeba typ vrácené hodnoty void.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-174">The void return type is used primarily to define event handlers, where a void return type is required.</span></span> <span data-ttu-id="6d7f5-175">Asynchronní metody, který vrátí prázdnou hodnotu nemůže být očekáváno a volající metody vrácení void nelze catch výjimky, které vyvolá metoda.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-175">An async method that returns void can't be awaited, and the caller of a void-returning method can't catch exceptions that the method throws.</span></span>  
  
 <span data-ttu-id="6d7f5-176">V následujícím příkladu `DelayAsync` je asynchronní metody, který má návratový typ <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-176">In the following example, `DelayAsync` is an async method that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="6d7f5-177">`DelayAsync`má `return` příkaz, který vrátí celé číslo.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-177">`DelayAsync` has a `return` statement that returns an integer.</span></span> <span data-ttu-id="6d7f5-178">Proto metoda deklaraci `DelayAsync` musí mít návratový typ `Task<int>`.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-178">Therefore the method declaration of `DelayAsync` must have a return type of `Task<int>`.</span></span> <span data-ttu-id="6d7f5-179">Vzhledem k tomu, že je návratový typ `Task<int>`, vyhodnocení `await` výrazu v `DoSomethingAsync` vytváří celé číslo, jak ukazuje následující příkaz: `int result = await delayTask`.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-179">Because the return type is `Task<int>`, the evaluation of the `await` expression in `DoSomethingAsync` produces an integer as the following statement demonstrates: `int result = await delayTask`.</span></span>  
  
 <span data-ttu-id="6d7f5-180">`startButton_Click` Metoda je příkladem asynchronní metody, který má návratový typ void.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-180">The `startButton_Click` method is an example of an async method that has a return type of void.</span></span> <span data-ttu-id="6d7f5-181">Protože `DoSomethingAsync` je asynchronní metody, úlohy pro volání `DoSomethingAsync` musí být očekáváno, jak ukazuje následující příkaz: `await DoSomethingAsync();`.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-181">Because `DoSomethingAsync` is an async method, the task for the call to `DoSomethingAsync` must be awaited, as the following statement shows: `await DoSomethingAsync();`.</span></span> <span data-ttu-id="6d7f5-182">`startButton_Click` Metoda musí být definovány se `async` modifikátor vzhledem k tomu, že metoda má `await` výrazu.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-182">The `startButton_Click` method must be defined with the `async` modifier because the method has an `await` expression.</span></span>  
  
 [!code-csharp[csAsyncMethod#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/methods_9.cs)]  
  
 <span data-ttu-id="6d7f5-183">Asynchronní metody nelze deklarovat všechny [ref](../../../csharp/language-reference/keywords/ref.md) nebo [out](../../../csharp/language-reference/keywords/out.md) parametry, ale můžete volat metody, které mají tyto parametry.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-183">An async method can't declare any [ref](../../../csharp/language-reference/keywords/ref.md) or [out](../../../csharp/language-reference/keywords/out.md) parameters, but it can call methods that have such parameters.</span></span>  
  
 <span data-ttu-id="6d7f5-184">Další informace o asynchronní metody najdete v tématu [asynchronní programování pomocí modifikátoru async a operátoru await](../../../csharp/programming-guide/concepts/async/index.md), [řízení toku v asynchronních programech](../../../csharp/programming-guide/concepts/async/control-flow-in-async-programs.md), a [asynchronní vrátit typy](../../../csharp/programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="6d7f5-184">For more information about async methods, see [Asynchronous Programming with async and await](../../../csharp/programming-guide/concepts/async/index.md), [Control Flow in Async Programs](../../../csharp/programming-guide/concepts/async/control-flow-in-async-programs.md), and [Async Return Types](../../../csharp/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
## <a name="expression-body-definitions"></a><span data-ttu-id="6d7f5-185">Výraz definice textu</span><span class="sxs-lookup"><span data-stu-id="6d7f5-185">Expression Body Definitions</span></span>  
 <span data-ttu-id="6d7f5-186">Je běžné metoda definicemi, jednoduše okamžitě vrátí s výsledkem výrazu nebo které mají jediný příkaz jako text metody.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-186">It is common to have method definitions that simply return immediately with the result of an expression, or that have a single statement as the body of the method.</span></span>  <span data-ttu-id="6d7f5-187">Je syntaxe zástupce pro definování těchto metod, pomocí `=>`:</span><span class="sxs-lookup"><span data-stu-id="6d7f5-187">There is a syntax shortcut for defining such methods using `=>`:</span></span>  
  
```csharp  
public Point Move(int dx, int dy) => new Point(x + dx, y + dy);   
public void Print() => Console.WriteLine(First + " " + Last);  
// Works with operators, properties, and indexers too.  
public static Complex operator +(Complex a, Complex b) => a.Add(b);  
public string Name => First + " " + Last;   
public Customer this[long id] => store.LookupCustomer(id);  
```  
  
 <span data-ttu-id="6d7f5-188">Pokud metoda vrátí `void` nebo asynchronní metody, pak těla metody musí být příkaz výraz (stejné jako u lambdas).</span><span class="sxs-lookup"><span data-stu-id="6d7f5-188">If the method returns `void` or is an async method, then the body of the method must be a statement expression (same as with lambdas).</span></span>  <span data-ttu-id="6d7f5-189">Pro vlastnostmi a indexery, se musí být jen pro čtení, a nepoužíváte `get` – klíčové slovo přistupujícího objektu.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-189">For properties and indexers, they must be read only, and you don't use the `get` accessor keyword.</span></span>  
  
## <a name="iterators"></a><span data-ttu-id="6d7f5-190">Iterátory</span><span class="sxs-lookup"><span data-stu-id="6d7f5-190">Iterators</span></span>  
 <span data-ttu-id="6d7f5-191">Iterátor provede vlastní iterace nad kolekcí, jako je například seznam nebo pole.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-191">An iterator performs a custom iteration over a collection, such as a list or an array.</span></span> <span data-ttu-id="6d7f5-192">Iterátor používá [yield vrátit](../../../csharp/language-reference/keywords/yield.md) příkaz vrátit každý element, jeden v čase.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-192">An iterator uses the [yield return](../../../csharp/language-reference/keywords/yield.md) statement to return each element one at a time.</span></span> <span data-ttu-id="6d7f5-193">Když [yield vrátit](../../../csharp/language-reference/keywords/yield.md) příkaz je dosaženo, uloží je aktuální umístění v kódu.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-193">When a [yield return](../../../csharp/language-reference/keywords/yield.md) statement is reached, the current location in code is remembered.</span></span> <span data-ttu-id="6d7f5-194">Při iteraci volání při příštím spuštění restartování z tohoto umístění.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-194">Execution is restarted from that location when the iterator is called the next time.</span></span>  
  
 <span data-ttu-id="6d7f5-195">Volání iterovat z kódu klienta pomocí [foreach](../../../csharp/language-reference/keywords/foreach-in.md) příkaz.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-195">You call an iterator from client code by using a [foreach](../../../csharp/language-reference/keywords/foreach-in.md) statement.</span></span>  
  
 <span data-ttu-id="6d7f5-196">Návratový typ iterovat může být <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, nebo <xref:System.Collections.Generic.IEnumerator%601>.</span><span class="sxs-lookup"><span data-stu-id="6d7f5-196">The return type of an iterator can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
 <span data-ttu-id="6d7f5-197">Další informace najdete v tématu [iterátory](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span><span class="sxs-lookup"><span data-stu-id="6d7f5-197">For more information, see [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="6d7f5-198">Specifikace jazyka C#</span><span class="sxs-lookup"><span data-stu-id="6d7f5-198">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6d7f5-199">Viz také</span><span class="sxs-lookup"><span data-stu-id="6d7f5-199">See Also</span></span>  
 [<span data-ttu-id="6d7f5-200">Průvodce programováním v C#</span><span class="sxs-lookup"><span data-stu-id="6d7f5-200">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="6d7f5-201">Třídy a struktury</span><span class="sxs-lookup"><span data-stu-id="6d7f5-201">Classes and Structs</span></span>](index.md)  
 [<span data-ttu-id="6d7f5-202">Modifikátory přístupu</span><span class="sxs-lookup"><span data-stu-id="6d7f5-202">Access Modifiers</span></span>](access-modifiers.md)  
 [<span data-ttu-id="6d7f5-203">Statické třídy a jejich členové</span><span class="sxs-lookup"><span data-stu-id="6d7f5-203">Static Classes and Static Class Members</span></span>](static-classes-and-static-class-members.md)  
 [<span data-ttu-id="6d7f5-204">Dědičnost</span><span class="sxs-lookup"><span data-stu-id="6d7f5-204">Inheritance</span></span>](inheritance.md)  
 [<span data-ttu-id="6d7f5-205">Abstraktní a uzavřené třídy a jejich členové</span><span class="sxs-lookup"><span data-stu-id="6d7f5-205">Abstract and Sealed Classes and Class Members</span></span>](abstract-and-sealed-classes-and-class-members.md)  
 [<span data-ttu-id="6d7f5-206">Parametry</span><span class="sxs-lookup"><span data-stu-id="6d7f5-206">params</span></span>](../../../csharp/language-reference/keywords/params.md)  
 [<span data-ttu-id="6d7f5-207">Vrátí</span><span class="sxs-lookup"><span data-stu-id="6d7f5-207">return</span></span>](../../../csharp/language-reference/keywords/return.md)  
 [<span data-ttu-id="6d7f5-208">na více systémů</span><span class="sxs-lookup"><span data-stu-id="6d7f5-208">out</span></span>](../../../csharp/language-reference/keywords/out.md)  
 [<span data-ttu-id="6d7f5-209">REF</span><span class="sxs-lookup"><span data-stu-id="6d7f5-209">ref</span></span>](../../../csharp/language-reference/keywords/ref.md)  
 [<span data-ttu-id="6d7f5-210">Předávání parametrů</span><span class="sxs-lookup"><span data-stu-id="6d7f5-210">Passing Parameters</span></span>](passing-parameters.md)
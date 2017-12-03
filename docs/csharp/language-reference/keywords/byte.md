---
title: "byte (Referenční dokumentace jazyka C#)"
ms.date: 03/14/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- byte
- byte_CSharpKeyword
helpviewer_keywords: byte keyword [C#]
ms.assetid: 111f1db9-ca32-4f0e-b497-4783517eda47
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 231a491914071b1d43b5a8938e677be531726e75
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="byte-c-reference"></a><span data-ttu-id="5c726-102">byte (Referenční dokumentace jazyka C#)</span><span class="sxs-lookup"><span data-stu-id="5c726-102">byte (C# Reference)</span></span>

<span data-ttu-id="5c726-103">`byte`označuje typ integrální, který ukládá hodnoty, které je uvedené v následující tabulce.</span><span class="sxs-lookup"><span data-stu-id="5c726-103">`byte` denotes an integral type that stores values as indicated in the following table.</span></span>  
  
|<span data-ttu-id="5c726-104">Typ</span><span class="sxs-lookup"><span data-stu-id="5c726-104">Type</span></span>|<span data-ttu-id="5c726-105">Rozsah</span><span class="sxs-lookup"><span data-stu-id="5c726-105">Range</span></span>|<span data-ttu-id="5c726-106">Velikost</span><span class="sxs-lookup"><span data-stu-id="5c726-106">Size</span></span>|<span data-ttu-id="5c726-107">Typ rozhraní .NET Framework</span><span class="sxs-lookup"><span data-stu-id="5c726-107">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`byte`|<span data-ttu-id="5c726-108">0 až 255</span><span class="sxs-lookup"><span data-stu-id="5c726-108">0 to 255</span></span>|<span data-ttu-id="5c726-109">Nepodepsané 8bitové celé číslo</span><span class="sxs-lookup"><span data-stu-id="5c726-109">Unsigned 8-bit integer</span></span>|<xref:System.Byte?displayProperty=nameWithType>|  
  
## <a name="literals"></a><span data-ttu-id="5c726-110">Literály</span><span class="sxs-lookup"><span data-stu-id="5c726-110">Literals</span></span>  

 <span data-ttu-id="5c726-111">Můžete deklarace a inicializace `byte` proměnné přiřazením decimal literál, hexadecimální literál, nebo (počínaje C# 7) binární literálu do ní.</span><span class="sxs-lookup"><span data-stu-id="5c726-111">You can declare and initialize a `byte` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7) a binary literal to it.</span></span> <span data-ttu-id="5c726-112">Pokud literálu celé číslo je mimo rozsah `byte` (tj. Pokud je menší než <xref:System.Byte.MinValue?displayProperty=nameWithType> nebo větší než <xref:System.Byte.MaxValue?displayProperty=nameWithType>), dojde k chybě kompilace.</span><span class="sxs-lookup"><span data-stu-id="5c726-112">If the integer literal is outside the range of `byte` (that is, if it is less than <xref:System.Byte.MinValue?displayProperty=nameWithType> or greater than <xref:System.Byte.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="5c726-113">V následujícím příkladu, celá čísla rovno 201, která jsou reprezentovány jako decimal, šestnáctkové, a binární literály jsou implicitně převést z [int](../../../csharp/language-reference/keywords/int.md) k `byte` hodnoty.</span><span class="sxs-lookup"><span data-stu-id="5c726-113">In the following example, integers equal to 201 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [int](../../../csharp/language-reference/keywords/int.md) to `byte` values.</span></span>    
  
[!code-csharp[Byte](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Byte)]  

> [!NOTE] 
> <span data-ttu-id="5c726-114">Použijte předponu `0x` nebo `0X` k označení hexadecimální literál a předponu `0b` nebo `0B` k označení binární literál.</span><span class="sxs-lookup"><span data-stu-id="5c726-114">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="5c726-115">Decimal literály mít žádná předpona.</span><span class="sxs-lookup"><span data-stu-id="5c726-115">Decimal literals have no prefix.</span></span>

<span data-ttu-id="5c726-116">Od verze jazyka C# 7, byly přidány několik funkcí za účelem zlepšení čitelnosti.</span><span class="sxs-lookup"><span data-stu-id="5c726-116">Starting with C# 7, a couple of features have been added to enhance readability.</span></span> 
 - <span data-ttu-id="5c726-117">C# 7.0 umožňuje použití znak podtržítka `_`, jako oddělovač číslice.</span><span class="sxs-lookup"><span data-stu-id="5c726-117">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
 - <span data-ttu-id="5c726-118">C# 7.2 umožňuje `_` má být použit jako číslice oddělovače pro binární nebo hexadecimální literál, po předponu.</span><span class="sxs-lookup"><span data-stu-id="5c726-118">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="5c726-119">Decimal literál není povolená tak, aby měl úvodní podtržítka.</span><span class="sxs-lookup"><span data-stu-id="5c726-119">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="5c726-120">Níže jsou uvedeny některé příklady.</span><span class="sxs-lookup"><span data-stu-id="5c726-120">Some examples are shown below.</span></span>

[!code-csharp[Byte](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ByteS)]  
 
## <a name="conversions"></a><span data-ttu-id="5c726-121">Převody</span><span class="sxs-lookup"><span data-stu-id="5c726-121">Conversions</span></span>  
 <span data-ttu-id="5c726-122">Je předdefinovaný implicitní převod z `byte` k [krátké](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [Celé_číslo](../../../csharp/language-reference/keywords/uint.md), [dlouho ](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [dvojité](../../../csharp/language-reference/keywords/double.md), nebo [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="5c726-122">There is a predefined implicit conversion from `byte` to [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span>  
  
 <span data-ttu-id="5c726-123">Nelze implicitně převést bez literál číselné typy větší velikost úložiště na `byte`.</span><span class="sxs-lookup"><span data-stu-id="5c726-123">You cannot implicitly convert non-literal numeric types of larger storage size to `byte`.</span></span> <span data-ttu-id="5c726-124">Další informace o velikosti úložiště celočíselných typů najdete v tématu [tabulka celočíselných typů](../../../csharp/language-reference/keywords/integral-types-table.md).</span><span class="sxs-lookup"><span data-stu-id="5c726-124">For more information on the storage sizes of integral types, see [Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md).</span></span> <span data-ttu-id="5c726-125">Zvažte například následující dva `byte` proměnné `x` a `y`:</span><span class="sxs-lookup"><span data-stu-id="5c726-125">Consider, for example, the following two `byte` variables `x` and `y`:</span></span>  
  
```  
byte x = 10, y = 20;  
```  
  
 <span data-ttu-id="5c726-126">Následující příkaz přiřazení bude k chybě kompilace vytvořit, protože výsledkem aritmetické výrazu na pravé straně operátoru přiřazení `int` ve výchozím nastavení.</span><span class="sxs-lookup"><span data-stu-id="5c726-126">The following assignment statement will produce a compilation error, because the arithmetic expression on the right-hand side of the assignment operator evaluates to `int` by default.</span></span>  
  
```  
// Error: conversion from int to byte:  
byte z = x + y;  
```  
  
 <span data-ttu-id="5c726-127">Chcete-li tento problém vyřešit, použijte přetypování:</span><span class="sxs-lookup"><span data-stu-id="5c726-127">To fix this problem, use a cast:</span></span>  
  
```  
// OK: explicit conversion:  
byte z = (byte)(x + y);  
```  
  
 <span data-ttu-id="5c726-128">Je ale možné použít následující příkazy, kde Cílová proměnná má stejnou velikost úložiště nebo větší velikost úložiště:</span><span class="sxs-lookup"><span data-stu-id="5c726-128">It is possible though, to use the following statements where the destination variable has the same storage size or a larger storage size:</span></span>  
  
```  
int x = 10, y = 20;  
int m = x + y;  
long n = x + y;  
```  
  
 <span data-ttu-id="5c726-129">Navíc není žádný implicitní převod z typů s plovoucí desetinnou čárkou na `byte`.</span><span class="sxs-lookup"><span data-stu-id="5c726-129">Also, there is no implicit conversion from floating-point types to `byte`.</span></span> <span data-ttu-id="5c726-130">Například následující příkaz vygeneruje Chyba kompilátoru, pokud se používá explicitní přetypování:</span><span class="sxs-lookup"><span data-stu-id="5c726-130">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```  
// Error: no implicit conversion from double:  
byte x = 3.0;   
// OK: explicit conversion:  
byte y = (byte)3.0;  
```  
  
 <span data-ttu-id="5c726-131">Při volání přetížené metody, se musí použít přetypování.</span><span class="sxs-lookup"><span data-stu-id="5c726-131">When calling overloaded methods, a cast must be used.</span></span> <span data-ttu-id="5c726-132">Zvažte například následující přetížené metody, které používají `byte` a [int](../../../csharp/language-reference/keywords/int.md) parametry:</span><span class="sxs-lookup"><span data-stu-id="5c726-132">Consider, for example, the following overloaded methods that use `byte` and [int](../../../csharp/language-reference/keywords/int.md) parameters:</span></span>  
  
```  
public static void SampleMethod(int i) {}  
public static void SampleMethod(byte b) {}  
```  
  
 <span data-ttu-id="5c726-133">Pomocí `byte` přetypování zaručuje, že správný typ je volána, například:</span><span class="sxs-lookup"><span data-stu-id="5c726-133">Using the `byte` cast guarantees that the correct type is called, for example:</span></span>  
  
```  
// Calling the method with the int parameter:  
SampleMethod(5);  
// Calling the method with the byte parameter:  
SampleMethod((byte)5);  
```  
  
 <span data-ttu-id="5c726-134">Informace v aritmetických výrazech s smíšený typy s plovoucí desetinnou čárkou a integrální typy najdete v tématu [float](../../../csharp/language-reference/keywords/float.md) a [dvojité](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="5c726-134">For information on arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
 <span data-ttu-id="5c726-135">Další informace o implicitní číselný převod pravidel najdete v tématu [implicitní číselné převody tabulky](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="5c726-135">For more information on implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="5c726-136">Specifikace jazyka C#</span><span class="sxs-lookup"><span data-stu-id="5c726-136">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5c726-137">Viz také</span><span class="sxs-lookup"><span data-stu-id="5c726-137">See Also</span></span>  
 <xref:System.Byte>  
 [<span data-ttu-id="5c726-138">Referenční dokumentace jazyka C#</span><span class="sxs-lookup"><span data-stu-id="5c726-138">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="5c726-139">Průvodce programováním v C#</span><span class="sxs-lookup"><span data-stu-id="5c726-139">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="5c726-140">Klíčová slova jazyka C#</span><span class="sxs-lookup"><span data-stu-id="5c726-140">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="5c726-141">Tabulka celočíselných typů</span><span class="sxs-lookup"><span data-stu-id="5c726-141">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [<span data-ttu-id="5c726-142">Tabulka předdefinovaných typů</span><span class="sxs-lookup"><span data-stu-id="5c726-142">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="5c726-143">Tabulka implicitních číselných převodů</span><span class="sxs-lookup"><span data-stu-id="5c726-143">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [<span data-ttu-id="5c726-144">Tabulka explicitních číselných převodů</span><span class="sxs-lookup"><span data-stu-id="5c726-144">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
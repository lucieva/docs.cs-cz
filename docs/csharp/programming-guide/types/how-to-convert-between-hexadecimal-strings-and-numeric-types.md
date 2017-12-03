---
title: "Postupy: Převod mezi hexadecimálními řetězci a číselnými typy (Průvodce programováním v C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- hexadecimal strings [C#], converting to numeric type
- conversions [C#], hexidecimal strings
- strings [C#], converting hexadecimal strings
- hexadecimal strings [C#]
ms.assetid: 7115c49f-7d1d-40c3-8bd9-aae0cc1d46b6
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 91e5cff52c67e1e7930d92da7c87ab1f4a3120af
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-convert-between-hexadecimal-strings-and-numeric-types-c-programming-guide"></a><span data-ttu-id="2dfbd-102">Postupy: Převod mezi hexadecimálními řetězci a číselnými typy (Průvodce programováním v C#)</span><span class="sxs-lookup"><span data-stu-id="2dfbd-102">How to: Convert Between Hexadecimal Strings and Numeric Types (C# Programming Guide)</span></span>
<span data-ttu-id="2dfbd-103">Tyto příklady ukazují, jak provádět následující úlohy:</span><span class="sxs-lookup"><span data-stu-id="2dfbd-103">These examples show you how to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="2dfbd-104">Získat šestnáctkové hodnoty každý znak v [řetězec](../../../csharp/language-reference/keywords/string.md).</span><span class="sxs-lookup"><span data-stu-id="2dfbd-104">Obtain the hexadecimal value of each character in a [string](../../../csharp/language-reference/keywords/string.md).</span></span>  
  
-   <span data-ttu-id="2dfbd-105">Získat [char](../../../csharp/language-reference/keywords/char.md) odpovídající každé hodnotě v řetězec hexadecimálních znaků.</span><span class="sxs-lookup"><span data-stu-id="2dfbd-105">Obtain the [char](../../../csharp/language-reference/keywords/char.md) that corresponds to each value in a hexadecimal string.</span></span>  
  
-   <span data-ttu-id="2dfbd-106">Převést hexadecimální `string` k [int](../../../csharp/language-reference/keywords/int.md).</span><span class="sxs-lookup"><span data-stu-id="2dfbd-106">Convert a hexadecimal `string` to an [int](../../../csharp/language-reference/keywords/int.md).</span></span>  
  
-   <span data-ttu-id="2dfbd-107">Převést hexadecimální `string` k [float](../../../csharp/language-reference/keywords/float.md).</span><span class="sxs-lookup"><span data-stu-id="2dfbd-107">Convert a hexadecimal `string` to a [float](../../../csharp/language-reference/keywords/float.md).</span></span>  
  
-   <span data-ttu-id="2dfbd-108">Převést [bajtů](../../../csharp/language-reference/keywords/byte.md) pole pro hexadecimální `string`.</span><span class="sxs-lookup"><span data-stu-id="2dfbd-108">Convert a [byte](../../../csharp/language-reference/keywords/byte.md) array to a hexadecimal `string`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2dfbd-109">Příklad</span><span class="sxs-lookup"><span data-stu-id="2dfbd-109">Example</span></span>  
 <span data-ttu-id="2dfbd-110">Výstupy šestnáctkové hodnoty každý znak v tomto příkladu `string`.</span><span class="sxs-lookup"><span data-stu-id="2dfbd-110">This example outputs the hexadecimal value of each character in a `string`.</span></span> <span data-ttu-id="2dfbd-111">Nejprve analyzuje `string` na pole znaků.</span><span class="sxs-lookup"><span data-stu-id="2dfbd-111">First it parses the `string` to an array of characters.</span></span> <span data-ttu-id="2dfbd-112">Potom zavolá <xref:System.Convert.ToInt32%28System.Char%29> na každý znak získat jeho číselnou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="2dfbd-112">Then it calls <xref:System.Convert.ToInt32%28System.Char%29> on each character to obtain its numeric value.</span></span> <span data-ttu-id="2dfbd-113">Nakonec formátuje číslo jako hexadecimální vyjádření v `string`.</span><span class="sxs-lookup"><span data-stu-id="2dfbd-113">Finally, it formats the number as its hexadecimal representation in a `string`.</span></span>  
  
 [!code-csharp[csProgGuideTypes#30](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="2dfbd-114">Příklad</span><span class="sxs-lookup"><span data-stu-id="2dfbd-114">Example</span></span>  
 <span data-ttu-id="2dfbd-115">V tomto příkladu analyzuje `string` z hexadecimální hodnoty a výstupy znak odpovídající každé šestnáctkové hodnoty.</span><span class="sxs-lookup"><span data-stu-id="2dfbd-115">This example parses a `string` of hexadecimal values and outputs the character corresponding to each hexadecimal value.</span></span> <span data-ttu-id="2dfbd-116">První volání [rozdělení (Char\[\])](xref:System.String.Split(System.Char[])) metoda získat každý šestnáctkové hodnoty jako samostatnou `string` v matici.</span><span class="sxs-lookup"><span data-stu-id="2dfbd-116">First it calls the [Split(Char\[\])](xref:System.String.Split(System.Char[])) method to obtain each hexadecimal value as an individual `string` in an array.</span></span> <span data-ttu-id="2dfbd-117">Potom zavolá <xref:System.Convert.ToInt32%28System.String%2CSystem.Int32%29> Převést šestnáctkové hodnoty hodnotu decimal vyjádřené [int](../../../csharp/language-reference/keywords/int.md). Zobrazuje dvěma různými způsoby získat znak odpovídající tento kód znaku.</span><span class="sxs-lookup"><span data-stu-id="2dfbd-117">Then it calls <xref:System.Convert.ToInt32%28System.String%2CSystem.Int32%29> to convert the hexadecimal value to a decimal value represented as an [int](../../../csharp/language-reference/keywords/int.md). It shows two different ways to obtain the character corresponding to that character code.</span></span> <span data-ttu-id="2dfbd-118">První způsob využívá <xref:System.Char.ConvertFromUtf32%28System.Int32%29>, který vrátí znak odpovídající argument celého čísla jako `string`.</span><span class="sxs-lookup"><span data-stu-id="2dfbd-118">The first technique uses <xref:System.Char.ConvertFromUtf32%28System.Int32%29>, which returns the character corresponding to the integer argument as a `string`.</span></span> <span data-ttu-id="2dfbd-119">Druhý způsob spočívá explicitně vrhá `int` k [char](../../../csharp/language-reference/keywords/char.md).</span><span class="sxs-lookup"><span data-stu-id="2dfbd-119">The second technique explicitly casts the `int` to a [char](../../../csharp/language-reference/keywords/char.md).</span></span>  
  
 [!code-csharp[csProgGuideTypes#31](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_2.cs)]  
  
## <a name="example"></a><span data-ttu-id="2dfbd-120">Příklad</span><span class="sxs-lookup"><span data-stu-id="2dfbd-120">Example</span></span>  
 <span data-ttu-id="2dfbd-121">Tento příklad ukazuje další způsob, jak převést hexadecimální `string` na celé číslo, voláním <xref:System.Int32.Parse%28System.String%2CSystem.Globalization.NumberStyles%29> metoda.</span><span class="sxs-lookup"><span data-stu-id="2dfbd-121">This example shows another way to convert a hexadecimal `string` to an integer, by calling the <xref:System.Int32.Parse%28System.String%2CSystem.Globalization.NumberStyles%29> method.</span></span>  
  
 [!code-csharp[csProgGuideTypes#32](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_3.cs)]  
  
## <a name="example"></a><span data-ttu-id="2dfbd-122">Příklad</span><span class="sxs-lookup"><span data-stu-id="2dfbd-122">Example</span></span>  
 <span data-ttu-id="2dfbd-123">Následující příklad ukazuje, jak převést hexadecimální `string` k [float](../../../csharp/language-reference/keywords/float.md) pomocí <xref:System.BitConverter?displayProperty=nameWithType> třídy a <xref:System.Int32.Parse%2A?displayProperty=nameWithType> metoda.</span><span class="sxs-lookup"><span data-stu-id="2dfbd-123">The following example shows how to convert a hexadecimal `string` to a [float](../../../csharp/language-reference/keywords/float.md) by using the <xref:System.BitConverter?displayProperty=nameWithType> class and the <xref:System.Int32.Parse%2A?displayProperty=nameWithType> method.</span></span>  
  
 [!code-csharp[csProgGuideTypes#39](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_4.cs)]  
  
## <a name="example"></a><span data-ttu-id="2dfbd-124">Příklad</span><span class="sxs-lookup"><span data-stu-id="2dfbd-124">Example</span></span>  
 <span data-ttu-id="2dfbd-125">Následující příklad ukazuje, jak převést [bajtů](../../../csharp/language-reference/keywords/byte.md) pole pro řetězec hexadecimálních znaků pomocí <xref:System.BitConverter?displayProperty=nameWithType> třídy.</span><span class="sxs-lookup"><span data-stu-id="2dfbd-125">The following example shows how to convert a [byte](../../../csharp/language-reference/keywords/byte.md) array to a hexadecimal string by using the <xref:System.BitConverter?displayProperty=nameWithType> class.</span></span>  
  
 [!code-csharp[csProgGuideTypes#38](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_5.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="2dfbd-126">Viz také</span><span class="sxs-lookup"><span data-stu-id="2dfbd-126">See Also</span></span>  
 [<span data-ttu-id="2dfbd-127">Standardní řetězce formátu čísla</span><span class="sxs-lookup"><span data-stu-id="2dfbd-127">Standard Numeric Format Strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)  
 [<span data-ttu-id="2dfbd-128">Typy</span><span class="sxs-lookup"><span data-stu-id="2dfbd-128">Types</span></span>](../../../csharp/programming-guide/types/index.md)  
 [<span data-ttu-id="2dfbd-129">Postupy: určení, zda řetězec reprezentuje číselnou hodnotu</span><span class="sxs-lookup"><span data-stu-id="2dfbd-129">How to: Determine Whether a String Represents a Numeric Value</span></span>](../../../csharp/programming-guide/strings/how-to-determine-whether-a-string-represents-a-numeric-value.md)
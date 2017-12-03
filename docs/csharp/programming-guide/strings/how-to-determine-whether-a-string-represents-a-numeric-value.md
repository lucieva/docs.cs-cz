---
title: "Postupy: Určení, zda řetězec reprezentuje číselnou hodnotu (Průvodce programováním v C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- numeric strings [C#]
- validating numeric input [C#]
- strings [C#], numeric
ms.assetid: a4e84e10-ea0a-489f-a868-503dded9d85f
caps.latest.revision: "9"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 850c5d0e7a246b2319ba841dae9884c90390d38c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-determine-whether-a-string-represents-a-numeric-value-c-programming-guide"></a><span data-ttu-id="723d9-102">Postupy: Určení, zda řetězec reprezentuje číselnou hodnotu (Průvodce programováním v C#)</span><span class="sxs-lookup"><span data-stu-id="723d9-102">How to: Determine Whether a String Represents a Numeric Value (C# Programming Guide)</span></span>
<span data-ttu-id="723d9-103">K určení, zda řetězec je platný reprezentace zadané číselného typu, použijte statickou `TryParse` metodu, která je implementována všechny primitivní číselnými typy a také typy, jako <xref:System.DateTime> a <xref:System.Net.IPAddress>.</span><span class="sxs-lookup"><span data-stu-id="723d9-103">To determine whether a string is a valid representation of a specified numeric type, use the static `TryParse` method that is implemented by all primitive numeric types and also by types such as <xref:System.DateTime> and <xref:System.Net.IPAddress>.</span></span> <span data-ttu-id="723d9-104">Následující příklad ukazuje, jak určit, zda "108" je platná [int](../../../csharp/language-reference/keywords/int.md).</span><span class="sxs-lookup"><span data-stu-id="723d9-104">The following example shows how to determine whether "108" is a valid [int](../../../csharp/language-reference/keywords/int.md).</span></span>  
  
```  
int i = 0;   
string s = "108";  
bool result = int.TryParse(s, out i); //i now = 108  
```  
  
 <span data-ttu-id="723d9-105">Pokud řetězec obsahuje číselného typu znaky nebo číselná hodnota je příliš velký či příliš malý pro konkrétní typ, který jste zadali, `TryParse` vrací hodnotu false a nastaví výstupní parametr na hodnotu nula.</span><span class="sxs-lookup"><span data-stu-id="723d9-105">If the string contains nonnumeric characters or the numeric value is too large or too small for the particular type you have specified, `TryParse` returns false and sets the out parameter to zero.</span></span> <span data-ttu-id="723d9-106">Jinak vrátí hodnotu true a nastaví parametr mimo na číselnou hodnotu řetězce.</span><span class="sxs-lookup"><span data-stu-id="723d9-106">Otherwise, it returns true and sets the out parameter to the numeric value of the string.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="723d9-107">Řetězec může obsahovat pouze znaky a stále není platné pro typ jehož `TryParse` metoda, která používáte.</span><span class="sxs-lookup"><span data-stu-id="723d9-107">A string may contain only numeric characters and still not be valid for the type whose `TryParse` method that you use.</span></span> <span data-ttu-id="723d9-108">Například "256" není platná hodnota pro `byte` , ale je platná pro `int`.</span><span class="sxs-lookup"><span data-stu-id="723d9-108">For example, "256" is not a valid value for `byte` but it is valid for `int`.</span></span> <span data-ttu-id="723d9-109">"98.6" není platná hodnota pro `int` , ale je platná `decimal`.</span><span class="sxs-lookup"><span data-stu-id="723d9-109">"98.6" is not a valid value for `int` but it is a valid `decimal`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="723d9-110">Příklad</span><span class="sxs-lookup"><span data-stu-id="723d9-110">Example</span></span>  
 <span data-ttu-id="723d9-111">Následující příklady ukazují, jak používat `TryParse` s řetězcové vyjádření `long`, `byte`, a `decimal` hodnoty.</span><span class="sxs-lookup"><span data-stu-id="723d9-111">The following examples show how to use `TryParse` with string representations of `long`, `byte`, and `decimal` values.</span></span>  
  
 [!code-csharp[csProgGuideStrings#14](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-determine-whether-a-string-represents-a-numeric-value_1.cs)]  
  
## <a name="robust-programming"></a><span data-ttu-id="723d9-112">Robustní programování</span><span class="sxs-lookup"><span data-stu-id="723d9-112">Robust Programming</span></span>  
 <span data-ttu-id="723d9-113">Číselný primitivní typy také implementace `Parse` statickou metodu, která vyvolá výjimku, pokud řetězec není platné číslo.</span><span class="sxs-lookup"><span data-stu-id="723d9-113">Primitive numeric types also implement the `Parse` static method, which throws an exception if the string is not a valid number.</span></span> <span data-ttu-id="723d9-114">`TryParse`je obecně efektivnější, protože ji právě vrací hodnotu false, pokud číslo není platné.</span><span class="sxs-lookup"><span data-stu-id="723d9-114">`TryParse` is generally more efficient because it just returns false if the number is not valid.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="723d9-115">Zabezpečení rozhraní .NET Framework</span><span class="sxs-lookup"><span data-stu-id="723d9-115">.NET Framework Security</span></span>  
 <span data-ttu-id="723d9-116">Vždy nutné použít `TryParse` nebo `Parse` metody k ověření uživatelského vstupu z ovládací prvky například textová pole a pole se seznamem.</span><span class="sxs-lookup"><span data-stu-id="723d9-116">Always use the `TryParse` or `Parse` methods to validate user input from controls such as text boxes and combo boxes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="723d9-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="723d9-117">See Also</span></span>  
 [<span data-ttu-id="723d9-118">Postupy: převedení pole bajtů na typ int</span><span class="sxs-lookup"><span data-stu-id="723d9-118">How to: Convert a byte Array to an int</span></span>](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md)  
 [<span data-ttu-id="723d9-119">Postupy: převedení řetězce na číslo.</span><span class="sxs-lookup"><span data-stu-id="723d9-119">How to: Convert a String to a Number</span></span>](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md)  
 [<span data-ttu-id="723d9-120">Postupy: převod mezi hexadecimálními řetězci a číselnými typy</span><span class="sxs-lookup"><span data-stu-id="723d9-120">How to: Convert Between Hexadecimal Strings and Numeric Types</span></span>](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md)  
 [<span data-ttu-id="723d9-121">Analýza číselných řetězců</span><span class="sxs-lookup"><span data-stu-id="723d9-121">Parsing Numeric Strings</span></span>](../../../standard/base-types/parsing-numeric.md)  
 [<span data-ttu-id="723d9-122">Typy formátování</span><span class="sxs-lookup"><span data-stu-id="723d9-122">Formatting Types</span></span>](../../../standard/base-types/formatting-types.md)
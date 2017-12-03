---
title: "Tabulka formátování číselných výsledků (Referenční dokumentace jazyka C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- formatting [C#]
- numeric formatting [C#]
- String.Format method
- Console.Write method
ms.assetid: 120ba537-4448-4c62-8676-7a8fdd98f496
caps.latest.revision: "14"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: cce14d5124ffdf030701ae0fc769278da51f86cc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="formatting-numeric-results-table-c-reference"></a><span data-ttu-id="e4b83-102">Tabulka formátování číselných výsledků (Referenční dokumentace jazyka C#)</span><span class="sxs-lookup"><span data-stu-id="e4b83-102">Formatting Numeric Results Table (C# Reference)</span></span>
<span data-ttu-id="e4b83-103">Můžete formátování číselných výsledků pomocí <xref:System.String.Format%2A?displayProperty=nameWithType> metoda, nebo pomocí <xref:System.Console.Write%2A?displayProperty=nameWithType> nebo <xref:System.Console.WriteLine%2A?displayProperty=nameWithType> metodu, která volá `String.Format`.</span><span class="sxs-lookup"><span data-stu-id="e4b83-103">You can format numeric results by using the <xref:System.String.Format%2A?displayProperty=nameWithType> method, or through the <xref:System.Console.Write%2A?displayProperty=nameWithType> or <xref:System.Console.WriteLine%2A?displayProperty=nameWithType> method, which calls `String.Format`.</span></span> <span data-ttu-id="e4b83-104">Formát zadané pomocí řetězce formátu.</span><span class="sxs-lookup"><span data-stu-id="e4b83-104">The format is specified by using format strings.</span></span> <span data-ttu-id="e4b83-105">Následující tabulka obsahuje podporované standardní formát řetězce.</span><span class="sxs-lookup"><span data-stu-id="e4b83-105">The following table contains the supported standard format strings.</span></span> <span data-ttu-id="e4b83-106">Řetězec formátu má následující podobu: `Axx`, kde `A` je specifikátor formátu a `xx` je specifikátor přesnosti.</span><span class="sxs-lookup"><span data-stu-id="e4b83-106">The format string takes the following form: `Axx`, where `A` is the format specifier and `xx` is the precision specifier.</span></span> <span data-ttu-id="e4b83-107">Specifikátor formátu řídí typ formátování aplikované na číselnou hodnotu a specifikátor přesnosti určuje počet platných číslic nebo desetinných míst formátovaný výstupu.</span><span class="sxs-lookup"><span data-stu-id="e4b83-107">The format specifier controls the type of formatting applied to the numeric value, and the precision specifier controls the number of significant digits or decimal places of the formatted output.</span></span> <span data-ttu-id="e4b83-108">Hodnota může být v rozmezí specifikátor přesnosti od 0 do 99.</span><span class="sxs-lookup"><span data-stu-id="e4b83-108">The value of the precision specifier ranges from 0 to 99.</span></span>  
  
 <span data-ttu-id="e4b83-109">Další informace o standardní a vlastní formátování řetězce najdete v tématu [typy formátování](../../../standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="e4b83-109">For more information about standard and custom formatting strings, see [Formatting Types](../../../standard/base-types/formatting-types.md).</span></span> <span data-ttu-id="e4b83-110">Další informace o `String.Format` metodu, najdete v části <xref:System.String.Format%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e4b83-110">For more information about the `String.Format` method, see <xref:System.String.Format%2A?displayProperty=nameWithType>.</span></span>  
  
|<span data-ttu-id="e4b83-111">Specifikace formátu</span><span class="sxs-lookup"><span data-stu-id="e4b83-111">Format Specifier</span></span>|<span data-ttu-id="e4b83-112">Popis</span><span class="sxs-lookup"><span data-stu-id="e4b83-112">Description</span></span>|<span data-ttu-id="e4b83-113">Příklady</span><span class="sxs-lookup"><span data-stu-id="e4b83-113">Examples</span></span>|<span data-ttu-id="e4b83-114">Výstup</span><span class="sxs-lookup"><span data-stu-id="e4b83-114">Output</span></span>|  
|----------------------|-----------------|--------------|------------|  
|<span data-ttu-id="e4b83-115">C nebo c</span><span class="sxs-lookup"><span data-stu-id="e4b83-115">C or c</span></span>|<span data-ttu-id="e4b83-116">Měna</span><span class="sxs-lookup"><span data-stu-id="e4b83-116">Currency</span></span>|<span data-ttu-id="e4b83-117">Console.Write ("{0}",: c 2.5);</span><span class="sxs-lookup"><span data-stu-id="e4b83-117">Console.Write("{0:C}", 2.5);</span></span><br /><br /> <span data-ttu-id="e4b83-118">Console.Write ("{0}",: c čísla -2,5);</span><span class="sxs-lookup"><span data-stu-id="e4b83-118">Console.Write("{0:C}", -2.5);</span></span>|<span data-ttu-id="e4b83-119">$2.50</span><span class="sxs-lookup"><span data-stu-id="e4b83-119">$2.50</span></span><br /><br /> <span data-ttu-id="e4b83-120">($2.50)</span><span class="sxs-lookup"><span data-stu-id="e4b83-120">($2.50)</span></span>|  
|<span data-ttu-id="e4b83-121">D nebo d</span><span class="sxs-lookup"><span data-stu-id="e4b83-121">D or d</span></span>|<span data-ttu-id="e4b83-122">Desetinné číslo</span><span class="sxs-lookup"><span data-stu-id="e4b83-122">Decimal</span></span>|<span data-ttu-id="e4b83-123">Console.Write ("{0:D5}", 25);</span><span class="sxs-lookup"><span data-stu-id="e4b83-123">Console.Write("{0:D5}", 25);</span></span>|<span data-ttu-id="e4b83-124">00025</span><span class="sxs-lookup"><span data-stu-id="e4b83-124">00025</span></span>|  
|<span data-ttu-id="e4b83-125">E nebo e</span><span class="sxs-lookup"><span data-stu-id="e4b83-125">E or e</span></span>|<span data-ttu-id="e4b83-126">Scientific</span><span class="sxs-lookup"><span data-stu-id="e4b83-126">Scientific</span></span>|<span data-ttu-id="e4b83-127">Console.Write ("{0:E}", částku 250 000 jedné);</span><span class="sxs-lookup"><span data-stu-id="e4b83-127">Console.Write("{0:E}", 250000);</span></span>|<span data-ttu-id="e4b83-128">2.500000E + 005</span><span class="sxs-lookup"><span data-stu-id="e4b83-128">2.500000E+005</span></span>|  
|<span data-ttu-id="e4b83-129">F nebo f</span><span class="sxs-lookup"><span data-stu-id="e4b83-129">F or f</span></span>|<span data-ttu-id="e4b83-130">Pevná desetinná čárka</span><span class="sxs-lookup"><span data-stu-id="e4b83-130">Fixed-point</span></span>|<span data-ttu-id="e4b83-131">Console.Write ("{0: F2}", 25);</span><span class="sxs-lookup"><span data-stu-id="e4b83-131">Console.Write("{0:F2}", 25);</span></span><br /><br /> <span data-ttu-id="e4b83-132">Console.Write ("{0: F0}", 25);</span><span class="sxs-lookup"><span data-stu-id="e4b83-132">Console.Write("{0:F0}", 25);</span></span>|<span data-ttu-id="e4b83-133">25.00</span><span class="sxs-lookup"><span data-stu-id="e4b83-133">25.00</span></span><br /><br /> <span data-ttu-id="e4b83-134">25</span><span class="sxs-lookup"><span data-stu-id="e4b83-134">25</span></span>|  
|<span data-ttu-id="e4b83-135">G nebo g</span><span class="sxs-lookup"><span data-stu-id="e4b83-135">G or g</span></span>|<span data-ttu-id="e4b83-136">Obecné</span><span class="sxs-lookup"><span data-stu-id="e4b83-136">General</span></span>|<span data-ttu-id="e4b83-137">Console.Write ("{0: g}", 2.5);</span><span class="sxs-lookup"><span data-stu-id="e4b83-137">Console.Write("{0:G}", 2.5);</span></span>|<span data-ttu-id="e4b83-138">2.5</span><span class="sxs-lookup"><span data-stu-id="e4b83-138">2.5</span></span>|  
|<span data-ttu-id="e4b83-139">N nebo n</span><span class="sxs-lookup"><span data-stu-id="e4b83-139">N or n</span></span>|<span data-ttu-id="e4b83-140">Číslo</span><span class="sxs-lookup"><span data-stu-id="e4b83-140">Number</span></span>|<span data-ttu-id="e4b83-141">Console.Write ("{0: n}", 2500000);</span><span class="sxs-lookup"><span data-stu-id="e4b83-141">Console.Write("{0:N}", 2500000);</span></span>|<span data-ttu-id="e4b83-142">2,500,000.00</span><span class="sxs-lookup"><span data-stu-id="e4b83-142">2,500,000.00</span></span>|  
|<span data-ttu-id="e4b83-143">X nebo x</span><span class="sxs-lookup"><span data-stu-id="e4b83-143">X or x</span></span>|<span data-ttu-id="e4b83-144">Šestnáctková hodnota</span><span class="sxs-lookup"><span data-stu-id="e4b83-144">Hexadecimal</span></span>|<span data-ttu-id="e4b83-145">Console.Write ("{0: x}", 250);</span><span class="sxs-lookup"><span data-stu-id="e4b83-145">Console.Write("{0:X}", 250);</span></span><br /><br /> <span data-ttu-id="e4b83-146">Console.Write ("{0: x}", 0xffff);</span><span class="sxs-lookup"><span data-stu-id="e4b83-146">Console.Write("{0:X}", 0xffff);</span></span>|<span data-ttu-id="e4b83-147">DM</span><span class="sxs-lookup"><span data-stu-id="e4b83-147">FA</span></span><br /><br /> <span data-ttu-id="e4b83-148">FFFF</span><span class="sxs-lookup"><span data-stu-id="e4b83-148">FFFF</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e4b83-149">Viz také</span><span class="sxs-lookup"><span data-stu-id="e4b83-149">See Also</span></span>  
 [<span data-ttu-id="e4b83-150">Referenční dokumentace jazyka C#</span><span class="sxs-lookup"><span data-stu-id="e4b83-150">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="e4b83-151">Průvodce programováním v C#</span><span class="sxs-lookup"><span data-stu-id="e4b83-151">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="e4b83-152">Standardní řetězce formátu čísla</span><span class="sxs-lookup"><span data-stu-id="e4b83-152">Standard Numeric Format Strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)  
 [<span data-ttu-id="e4b83-153">Referenční tabulky pro typy</span><span class="sxs-lookup"><span data-stu-id="e4b83-153">Reference Tables for Types</span></span>](../../../csharp/language-reference/keywords/reference-tables-for-types.md)  
 [<span data-ttu-id="e4b83-154">řetězec</span><span class="sxs-lookup"><span data-stu-id="e4b83-154">string</span></span>](../../../csharp/language-reference/keywords/string.md)
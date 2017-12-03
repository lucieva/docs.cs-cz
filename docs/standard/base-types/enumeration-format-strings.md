---
title: "Vytvoření výčtu řetězců formátu"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- format specifiers, enumeration format strings
- enumeration format strings
- formatting [.NET Framework], enumeration
ms.assetid: dd1ff672-1052-42cf-8666-4924fb6cd1a1
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e0992d8591711073f9094c29fad980a8e652e686
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="enumeration-format-strings"></a><span data-ttu-id="445e6-102">Vytvoření výčtu řetězců formátu</span><span class="sxs-lookup"><span data-stu-id="445e6-102">Enumeration Format Strings</span></span>
<span data-ttu-id="445e6-103">Můžete použít <xref:System.Enum.ToString%2A?displayProperty=nameWithType> metodu pro vytvoření nového objektu řetězec, který představuje numerické, šestnáctkové nebo řetězcovou hodnotu člena výčtu.</span><span class="sxs-lookup"><span data-stu-id="445e6-103">You can use the <xref:System.Enum.ToString%2A?displayProperty=nameWithType> method to create a new string object that represents the numeric, hexadecimal, or string value of an enumeration member.</span></span> <span data-ttu-id="445e6-104">Tato metoda přijímá jeden výčet formátování řetězce zadejte hodnotu, která mají být vráceny.</span><span class="sxs-lookup"><span data-stu-id="445e6-104">This method takes one of the enumeration formatting strings to specify the value that you want returned.</span></span>  
  
 <span data-ttu-id="445e6-105">Následující tabulka uvádí výčet formátování řetězců a hodnoty, které vracejí.</span><span class="sxs-lookup"><span data-stu-id="445e6-105">The following table lists the enumeration formatting strings and the values they return.</span></span> <span data-ttu-id="445e6-106">Tyto specifikátory formátu nerozlišují malá a velká písmena.</span><span class="sxs-lookup"><span data-stu-id="445e6-106">These format specifiers are not case-sensitive.</span></span>  
  
| <span data-ttu-id="445e6-107">Řetězec formátu</span><span class="sxs-lookup"><span data-stu-id="445e6-107">Format string</span></span> | <span data-ttu-id="445e6-108">Výsledek</span><span class="sxs-lookup"><span data-stu-id="445e6-108">Result</span></span> |  
| ------------- | ------ |  
| <span data-ttu-id="445e6-109">G nebo g</span><span class="sxs-lookup"><span data-stu-id="445e6-109">G or g</span></span> | <span data-ttu-id="445e6-110">Zobrazí položku výčtu jako řetězcovou hodnotu, pokud je to možné a v opačném případě zobrazí celočíselnou hodnotu aktuální instance.</span><span class="sxs-lookup"><span data-stu-id="445e6-110">Displays the enumeration entry as a string value, if possible, and otherwise displays the integer value of the current instance.</span></span> <span data-ttu-id="445e6-111">Pokud výčet definován se **příznaky** sadu atributů, řetězec hodnoty každé platné položka jsou zřetězeny společně, oddělených čárkami.</span><span class="sxs-lookup"><span data-stu-id="445e6-111">If the enumeration is defined with the **Flags** attribute set, the string values of each valid entry are concatenated together, separated by commas.</span></span> <span data-ttu-id="445e6-112">Pokud **příznaky** není nastavený atribut, jako číselná položka je zobrazena neplatná hodnota.</span><span class="sxs-lookup"><span data-stu-id="445e6-112">If the **Flags** attribute is not set, an invalid value is displayed as a numeric entry.</span></span> <span data-ttu-id="445e6-113">Následující příklad ilustruje specifikátor formátu.</span><span class="sxs-lookup"><span data-stu-id="445e6-113">The following example illustrates the G format specifier.</span></span><br><br><span data-ttu-id="445e6-114">[!code-csharp[Formatting.Enum#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#1)] [!code-vb[Formatting.Enum#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#1)]</span><span class="sxs-lookup"><span data-stu-id="445e6-114">[!code-csharp[Formatting.Enum#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#1)] [!code-vb[Formatting.Enum#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#1)]</span></span> |  
| <span data-ttu-id="445e6-115">F nebo f</span><span class="sxs-lookup"><span data-stu-id="445e6-115">F or f</span></span> | <span data-ttu-id="445e6-116">Zobrazí položku výčtu jako řetězcovou hodnotu, pokud je to možné.</span><span class="sxs-lookup"><span data-stu-id="445e6-116">Displays the enumeration entry as a string value, if possible.</span></span> <span data-ttu-id="445e6-117">Pokud hodnota může být zcela zobrazena jako souhrn položek ve výčtu (i když **příznaky** atribut není k dispozici), řetězcové hodnoty každé platné položka jsou zřetězen dohromady, oddělených čárkami.</span><span class="sxs-lookup"><span data-stu-id="445e6-117">If the value can be completely displayed as a summation of the entries in the enumeration (even if the **Flags** attribute is not present), the string values of each valid entry are concatenated together, separated by commas.</span></span> <span data-ttu-id="445e6-118">Pokud hodnotu nelze určit zcela podle položek výčtu, hodnota je naformátován jako celočíselnou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="445e6-118">If the value cannot be completely determined by the enumeration entries, then the value is formatted as the integer value.</span></span> <span data-ttu-id="445e6-119">Následující příklad ukazuje specifikátor formátu F.</span><span class="sxs-lookup"><span data-stu-id="445e6-119">The following example illustrates the F format specifier.</span></span><br><br><span data-ttu-id="445e6-120">[!code-csharp[Formatting.Enum#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#2)] [!code-vb[Formatting.Enum#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#2)]</span><span class="sxs-lookup"><span data-stu-id="445e6-120">[!code-csharp[Formatting.Enum#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#2)] [!code-vb[Formatting.Enum#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#2)]</span></span> |  
| <span data-ttu-id="445e6-121">D nebo d</span><span class="sxs-lookup"><span data-stu-id="445e6-121">D or d</span></span> | <span data-ttu-id="445e6-122">Zobrazí položku výčtu jako celočíselnou hodnotu v nejkratší možné reprezentaci.</span><span class="sxs-lookup"><span data-stu-id="445e6-122">Displays the enumeration entry as an integer value in the shortest representation possible.</span></span> <span data-ttu-id="445e6-123">Následující příklad ukazuje specifikátor formátu D.</span><span class="sxs-lookup"><span data-stu-id="445e6-123">The following example illustrates the D format specifier.</span></span><br><br><span data-ttu-id="445e6-124">[!code-csharp[Formatting.Enum#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#3)] [!code-vb[Formatting.Enum#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#3)]</span><span class="sxs-lookup"><span data-stu-id="445e6-124">[!code-csharp[Formatting.Enum#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#3)] [!code-vb[Formatting.Enum#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#3)]</span></span> |  
| <span data-ttu-id="445e6-125">X nebo x</span><span class="sxs-lookup"><span data-stu-id="445e6-125">X or x</span></span> | <span data-ttu-id="445e6-126">Zobrazí výčet položku jako šestnáctkové hodnoty.</span><span class="sxs-lookup"><span data-stu-id="445e6-126">Displays the enumeration entry as a hexadecimal value.</span></span> <span data-ttu-id="445e6-127">Hodnota je zajistit, že hodnota je minimální osm číslic v rozsahu určeném úvodními nulami podle potřeby.</span><span class="sxs-lookup"><span data-stu-id="445e6-127">The value is represented with leading zeros as necessary, to ensure that the value is a minimum eight digits in length.</span></span> <span data-ttu-id="445e6-128">Následující příklad ukazuje specifikátor formátu X.</span><span class="sxs-lookup"><span data-stu-id="445e6-128">The following example illustrates the X format specifier.</span></span><br /><br /> <span data-ttu-id="445e6-129">[!code-csharp[Formatting.Enum#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#4)] [!code-vb[Formatting.Enum#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#4)]</span><span class="sxs-lookup"><span data-stu-id="445e6-129">[!code-csharp[Formatting.Enum#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#4)] [!code-vb[Formatting.Enum#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#4)]</span></span> |  
  
## <a name="example"></a><span data-ttu-id="445e6-130">Příklad</span><span class="sxs-lookup"><span data-stu-id="445e6-130">Example</span></span>  
 <span data-ttu-id="445e6-131">V následujícím příkladu definuje výčet nazvaný `Colors` , tvoří tři položky: `Red`, `Blue`, a `Green`.</span><span class="sxs-lookup"><span data-stu-id="445e6-131">The following example defines an enumeration called `Colors` that consists of three entries: `Red`, `Blue`, and `Green`.</span></span>  
  
 [!code-csharp[Formatting.Enum#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#5)]
 [!code-vb[Formatting.Enum#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#5)]  
  
 <span data-ttu-id="445e6-132">Po definování výčtu instance lze deklarovat následujícím způsobem.</span><span class="sxs-lookup"><span data-stu-id="445e6-132">After the enumeration is defined, an instance can be declared in the following manner.</span></span>  
  
 [!code-csharp[Formatting.Enum#6](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#6)]
 [!code-vb[Formatting.Enum#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#6)]  
  
 <span data-ttu-id="445e6-133">`Color.ToString(System.String)` Metoda pak lze použít k zobrazení hodnot výčtu různými způsoby v závislosti na specifikátor formátu do ní předán.</span><span class="sxs-lookup"><span data-stu-id="445e6-133">The `Color.ToString(System.String)` method can then be used to display the enumeration value in different ways, depending on the format specifier passed to it.</span></span>  
  
 [!code-csharp[Formatting.Enum#7](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#7)]
 [!code-vb[Formatting.Enum#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="445e6-134">Viz také</span><span class="sxs-lookup"><span data-stu-id="445e6-134">See Also</span></span>  
 [<span data-ttu-id="445e6-135">Typy formátování</span><span class="sxs-lookup"><span data-stu-id="445e6-135">Formatting Types</span></span>](../../../docs/standard/base-types/formatting-types.md)
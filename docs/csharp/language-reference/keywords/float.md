---
title: float – klíčové slovo (referenční dokumentace jazyka C#)
ms.date: 07/20/2015
f1_keywords:
- float
- float_CSharpKeyword
helpviewer_keywords:
- float keyword [C#]
- floating-point numbers [C#], float keyword
ms.assetid: 1e77db7b-dedb-48b7-8dd1-b055e96a9258
ms.openlocfilehash: da697aa6f1f429418a69d9f58a13f46a3da9ac74
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2018
ms.locfileid: "50187176"
---
# <a name="float-c-reference"></a>float (Referenční dokumentace jazyka C#)

`float` – Klíčové slovo znamená jednoduchý typ, který ukládá 32bitové hodnoty s plovoucí desetinnou čárkou. V následující tabulce jsou uvedeny přesnosti a rozsahu pro `float` typu.

|Typ|Přibližný rozsah|Přesnost|Typ formátu .NET|  
|----------|-----------------------|---------------|-------------------------|  
|`float`|±1.5 x 10<sup>−45</sup> k ±3.4 x 10<sup>38</sup>|~ 6. až 9 číslic|<xref:System.Single?displayProperty=nameWithType>|  

## <a name="literals"></a>Literály

Ve výchozím nastavení, skutečné číselný literál na pravé straně operátoru přiřazení je považován za [double](double.md). Proto se inicializovat proměnnou s plovoucí desetinnou čárkou, použijte příponu `f` nebo `F`, jako v následujícím příkladu:

```csharp
float x = 3.5F;
```

Pokud je předchozí deklarace nepoužívají příponu, obdržíte chybu kompilace, protože se pokoušíte ukládat [double](double.md) hodnoty do `float` proměnné.

## <a name="conversions"></a>Převody

Integrální číselné typy a typy s plovoucí desetinnou čárkou ve výrazu můžete kombinovat. V takovém případě integrální typy jsou převedeny na typy s plovoucí desetinnou čárkou. Vyhodnocení výrazu se provádí dle následujících pravidel:

- Pokud jeden z typů s plovoucí desetinnou čárkou je [double](double.md), je výraz vyhodnocen [double](double.md), nebo [bool](bool.md) v relační porovnání nebo porovnání rovnosti.

- Pokud neexistuje žádné [double](double.md) zadejte výraz, výraz je vyhodnocen jako `float`, nebo [bool](bool.md) v relační porovnání nebo porovnání rovnosti.

Výraz s plovoucí desetinnou čárkou může obsahovat následující sady hodnot:

- Kladnou a zápornou nulou

- Kladné a záporné nekonečno.

- Hodnota not-a-Number (NaN)

- Konečná sada nenulové hodnoty

Další informace o těchto hodnotách naleznete v části Standard IEEE pro binární aritmetiku, k dispozici na [IEEE](https://www.ieee.org) webu.

## <a name="example"></a>Příklad

V následujícím příkladu [int](int.md), [krátký](short.md)a `float` jsou zahrnuty v matematickém výrazu dává `float` výsledek. (Nezapomeňte, že `float` je alias pro <xref:System.Single?displayProperty=nameWithType> typu.) Všimněte si, že neexistuje žádná [double](double.md) ve výrazu.

[!code-csharp[csrefKeywordsTypes#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#13)]

## <a name="c-language-specification"></a>specifikace jazyka C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Viz také:

- <xref:System.Single>  
- [Referenční dokumentace jazyka C#](../index.md)  
- [Průvodce programováním v jazyce C#](../../programming-guide/index.md)  
- [Přetypování a převody typů](../../programming-guide/types/casting-and-type-conversions.md)  
- [Klíčová slova jazyka C#](index.md)  
- [Tabulka celočíselných typů](integral-types-table.md)  
- [Tabulka předdefinovaných typů](built-in-types-table.md)  
- [Tabulka implicitních číselných převodů](implicit-numeric-conversions-table.md)  
- [Tabulka explicitních číselných převodů](explicit-numeric-conversions-table.md)  
---
title: C# pro příkaz
ms.date: 06/13/2018
f1_keywords:
- for
- for_CSharpKeyword
helpviewer_keywords:
- for keyword [C#]
ms.assetid: 34041a40-2c87-467a-9ffb-a0417d8f67a8
ms.openlocfilehash: c6ef926d6fb2c79b7b7f71c3b24b86a7ab057c88
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/04/2018
ms.locfileid: "43511725"
---
# <a name="for-c-reference"></a>pro (referenční dokumentace jazyka C#)

`for` Příkaz opakuje příkaz nebo blok příkazů během zadaný logický výraz je vyhodnocen jako `true`.

Na libovolný bod v rámci `for` blok příkazů, můžete přerušit ze smyčky s použitím [přerušení](break.md) příkazu nebo kroku na následující iteraci ve smyčce pomocí [pokračovat](continue.md) příkazu. Také můžete ukončit `for` smyčky pomocí [goto](goto.md), [vrátit](return.md), nebo [throw](throw.md) příkazy.

## <a name="structure-of-the-for-statement"></a>Struktura `for` – příkaz

`for` Definuje příkaz *inicializátor*, *podmínku*, a *iterátoru* oddíly:

```csharp
for (initializer; condition; iterator)
    body
```

Všechny tři oddíly jsou volitelné. Tělo smyčky je příkaz nebo blok příkazů.

Následující příklad ukazuje `for` všechny oddíly definované příkazem:

[!code-csharp-interactive[for loop example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#5)]

### <a name="the-initializer-section"></a>*Inicializátor* oddílu

Příkazy v *inicializátor* oddílu jsou spouštěny pouze jednou, před vstupem smyčky. *Inicializátor* oddíl je některý z následujících:

- Deklarace a inicializace proměnné místní smyčky, která není přístupná z mimo smyčku.

- Nula nebo více výrazy příkazu z následujícího seznamu, oddělené čárkami:

  - [přiřazení](../operators/assignment-operator.md) – příkaz

  - vyvolání metody

  - Přidání předpony nebo přípony [přírůstek](../operators/increment-operator.md) výraz, jako například `++i` nebo `i++`

  - Přidání předpony nebo přípony [snížení](../operators/decrement-operator.md) výraz, jako například `--i` nebo `i--`

  - Vytvoření objektu pomocí [nové](new-operator.md) – klíčové slovo

  - [operátor await](await.md) výraz

*Inicializátor* oddílu ve výše uvedeném příkladu deklaruje a inicializuje proměnnou místní smyčky `i`:

```csharp
int i = 0
```

### <a name="the-condition-section"></a>*Podmínku* oddílu

*Podmínku* část, pokud jsou k dispozici, musí být logický výraz. Tento výraz je vyhodnocen před každou iteraci smyčky. Pokud *podmínku* části není k dispozici nebo je logický výraz vyhodnocen `true`, další iteraci smyčky je provedeno; jinak, je ukončen smyčky.

*Podmínku* oddílu ve výše uvedeném příkladu určuje Pokud smyčku ukončí založena na hodnotě proměnné cyklu místní:

```csharp
i < 5
```

### <a name="the-iterator-section"></a>*Iterátoru* oddílu

*Iterátoru* oddíl definuje, co se stane po každé iteraci těla smyčky. *Iterátoru* oddíl obsahuje nula nebo více z následujících výrazy příkazu, oddělené čárkami:

- [přiřazení](../operators/assignment-operator.md) – příkaz

- vyvolání metody

- Přidání předpony nebo přípony [přírůstek](../operators/increment-operator.md) výraz, jako například `++i` nebo `i++`

- Přidání předpony nebo přípony [snížení](../operators/decrement-operator.md) výraz, jako například `--i` nebo `i--`

- Vytvoření objektu pomocí [nové](new-operator.md) – klíčové slovo

- [operátor await](await.md) výraz

*Iterátoru* proměnná místní smyčky zvýší části v předchozím příkladu:

```csharp
i++
```

## <a name="examples"></a>Příklady

Následující příklad ukazuje několik méně běžné použití `for` části příkazu: přiřazení hodnoty proměnné vnější smyčky v *inicializátor* části volání metody v obou  *Inicializátor* a *iterátoru* oddíly a změnou hodnoty dvou proměnných ve *iterátoru* oddílu. Vyberte **spustit** ke spuštění příkladu kódu. Potom můžete upravit kód a potom ho spusťte znovu.

[!code-csharp-interactive[not typical for loop example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#6)]

Následující příklad definuje nekonečné `for` smyčka:

[!code-csharp[infinite for loop example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#7)]

## <a name="c-language-specification"></a>specifikace jazyka C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Viz také:

- [For – příkaz (specifikace jazyka C#)](/dotnet/csharp/language-reference/language-specification/statements#the-for-statement)
- [Referenční dokumentace jazyka C#](../index.md)
- [Průvodce programováním v jazyce C#](../../programming-guide/index.md)
- [Klíčová slova jazyka C#](index.md)
- [foreach, in](foreach-in.md)
- [for – příkaz (C++)](/cpp/cpp/for-statement-cpp)
- [Příkazy iterace](iteration-statements.md)

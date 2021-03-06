---
title: do (Referenční dokumentace jazyka C#)
ms.date: 05/28/2018
f1_keywords:
- do_CSharpKeyword
- do
helpviewer_keywords:
- do keyword [C#]
ms.assetid: 50725f79-9ba6-4898-aa78-6e331568a1bb
ms.openlocfilehash: 89c13f5b547c13052e229ff6eb3a39ae5babce41
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/18/2018
ms.locfileid: "45994465"
---
# <a name="do-c-reference"></a>do (Referenční dokumentace jazyka C#)

`do` Příkaz opakuje příkaz nebo blok příkazů během zadaný logický výraz je vyhodnocen jako `true`. Vzhledem k tomu, že tento výraz je vyhodnocen po každém spuštění smyčky, `do-while` cyklus se opakuje, jednou nebo vícekrát. Tím se liší od [při](while.md) smyčku, která spustí nulakrát nebo vícekrát.

Na libovolný bod v rámci `do` blok příkazů, můžete přerušit ze smyčky s použitím [přerušení](break.md) příkazu.

Přejdete přímo na vyhodnocení `while` výrazem s použitím [pokračovat](continue.md) příkazu. Pokud je výraz vyhodnocen `true`, běh programu pokračuje prvním příkazem ve smyčce. V opačném případě běh programu pokračuje prvním příkazem za smyčky.

Také můžete ukončit `do-while` smyčky pomocí [goto](goto.md), [vrátit](return.md), nebo [throw](throw.md) příkazy.

## <a name="example"></a>Příklad

Následující příklad ukazuje použití `do` příkazu. Vyberte **spustit** ke spuštění příkladu kódu. Potom můžete upravit kód a potom ho spusťte znovu.

[!code-csharp-interactive[do loop example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#4)]

## <a name="c-language-specification"></a>specifikace jazyka C#

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Viz také:

- [Referenční dokumentace jazyka C#](../index.md)  
- [Průvodce programováním v jazyce C#](../../programming-guide/index.md)  
- [Klíčová slova jazyka C#](index.md)  
- [do-while – příkaz (C++)](/cpp/cpp/do-while-statement-cpp)  
- [Příkazy iterace](iteration-statements.md)  
- [while – příkaz](while.md)  

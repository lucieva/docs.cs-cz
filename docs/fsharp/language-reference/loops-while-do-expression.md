---
title: 'Smyčky: Výraz while...do (F#)'
description: Naleznete v tématu jak při... proveďte použit výraz provádět iterativní spuštění (opakování), zatímco je zadaný testovací podmínka pravdivá.
ms.date: 05/16/2016
ms.openlocfilehash: 5cf4461669221f91cb50e238c25494f03a10bbc2
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/02/2018
ms.locfileid: "45664706"
---
# <a name="loops-whiledo-expression"></a>Smyčky: Výraz while...do

`while...do` Použit výraz provádět iterativní spuštění (opakování), zatímco je zadaný testovací podmínka pravdivá.

## <a name="syntax"></a>Syntaxe

```fsharp
while test-expression do
    body-expression
```

## <a name="remarks"></a>Poznámky

*Výrazu testu* je vyhodnocen; Pokud je `true`, *výraz těla* provádí a testovací výraz je vyhodnocen znovu. *Výraz těla* musí mít typ `unit`. Pokud je test výraz `false`, konce iterace.

Následující příklad ukazuje použití `while...do` výrazu.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5301.fs)]

Výstup předchozího kódu je datový proud náhodných čísel od 1 do 20, poslední z nich je 10.

```
13 19 8 18 16 2 10
Found a 10!
```

>[!NOTE]
Můžete použít `while...do` ve výrazech pořadí a jiných výrazech výpočtu se v takovém případě přizpůsobenou verzi `while...do` výraz je použit. Další informace najdete v tématu [pořadí](sequences.md), [asynchronní pracovní postupy](asynchronous-workflows.md), a [výrazech výpočtu](computation-expressions.md).

## <a name="see-also"></a>Viz také:

- [Referenční dokumentace jazyka F#](index.md)
- [Smyčky: `for...in` výraz](loops-for-in-expression.md)
- [Smyčky: `for...to` výraz](loops-for-to-expression.md)

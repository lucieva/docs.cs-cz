---
title: into (Referenční dokumentace jazyka C#)
ms.date: 07/20/2015
f1_keywords:
- into_CSharpKeyword
- into
helpviewer_keywords:
- into keyword [C#]
ms.assetid: 81ec62c1-f0b1-4755-8a31-959876e77f65
ms.openlocfilehash: 6d46ae67dd84650172125c62ea70dc109671a89b
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/04/2018
ms.locfileid: "43507840"
---
# <a name="into-c-reference"></a>into (Referenční dokumentace jazyka C#)

`into` Kontextové klíčové slovo lze použít k vytvoření dočasného identifikátor pro ukládání výsledků [skupiny](group-clause.md), [spojení](join-clause.md) nebo [vyberte](select-clause.md) klauzuli do nového identifikátoru. Tento identifikátor může být sám generátor pro příkazy další dotaz. Při použití `group` nebo `select` klauzule, použijte nový identifikátor se někdy označuje jako *pokračování*.

## <a name="example"></a>Příklad

Následující příklad ukazuje použití `into` – klíčové slovo umožňující dočasné identifikátor `fruitGroup` která má odvozený typ `IGrouping`. S použitím identifikátoru, můžete vyvolat <xref:System.Linq.Enumerable.Count%2A> metodu na každý skupinu a vybrat jenom skupiny, které obsahují dva nebo více slov.

[!code-csharp[cscsrefQueryKeywords#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Into.cs#18)]

Použití `into` v `group` klauzule je potřeba, pouze pokud budete chtít provádět operace dalšího dotazu pro každou skupinu. Další informace najdete v tématu [group – klauzule](group-clause.md).

Příklad použití `into` v `join` klauzule, naleznete v tématu [klauzule join](join-clause.md).

## <a name="see-also"></a>Viz také:

- [Klíčová slova dotazu (LINQ)](query-keywords.md)  
- [LINQ – výrazy dotazů](../../../csharp/programming-guide/linq-query-expressions/index.md)  
- [group – klauzule](group-clause.md)  
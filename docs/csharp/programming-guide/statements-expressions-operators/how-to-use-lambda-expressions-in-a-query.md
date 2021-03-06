---
title: 'Postupy: Použití výrazů lambda v dotazu (Průvodce programováním v C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [C#], in LINQ
ms.assetid: 3cac4d25-d11f-4abd-9e7c-0f02e97ae06d
ms.openlocfilehash: 1632466aaa29cb79f053bd3ac2ca42e8b03ea89c
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/04/2018
ms.locfileid: "43506481"
---
# <a name="how-to-use-lambda-expressions-in-a-query-c-programming-guide"></a>Postupy: Použití výrazů lambda v dotazu (Průvodce programováním v C#)
Nepoužívat výrazy lambda přímo v syntaxi dotazů, ale je použít ve volání metody a výrazy dotazů můžou obsahovat volání metody. Ve skutečnosti nějakých operací dotazů lze vyjádřit pouze v syntaxe metody. Další informace o rozdílech mezi syntaxi dotazů a syntaxe využívající metody, naleznete v tématu [syntaxi dotazů a syntaxe využívající metody v jazyce LINQ](../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md).  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak pomocí výrazu lambda v dotazu založených na volání metody <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType> standardní operátor dotazu. Všimněte si, že <xref:System.Linq.Enumerable.Where%2A> metoda v tomto příkladu má vstupní parametr typu delegáta <xref:System.Func%601> a tohoto delegáta celého čísla jako vstup převezme a vrátí logickou hodnotu. Výraz lambda lze převést na tento delegát. To šlo [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] dotaz, který se používá <xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType> typ parametru metody, bude `Expression<Func<int,bool>>` však lambda výraz by vypadat stejně. Další informace o typu výrazu naleznete v tématu <xref:System.Linq.Expressions.Expression?displayProperty=nameWithType>.  
  
 [!code-csharp[csProgGuideLINQ#1](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-use-lambda-expressions-in-a-query_1.cs)]  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak použít výraz lambda ve volání metody, výrazu dotazu. Výraz lambda je nezbytné vzhledem k tomu <xref:System.Linq.Enumerable.Sum%2A> standardní operátor dotazu nelze vyvolat pomocí syntaxe dotazu.  
  
 Dotaz nejprve skupiny studentů podle jejich úrovně na podnikové úrovni, jak jsou definovány v `GradeLevel` výčtu. Potom pro každou skupinu přidá celkové hodnocení pro každého studenta. To vyžaduje dvě `Sum` operace. Vnitřní `Sum` vypočítá celkové skóre pro každého studenta a vnější `Sum` udržuje spuštěné, celkový součet všech studentů ve skupině.  
  
 [!code-csharp[csProgGuideLINQ#2](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-use-lambda-expressions-in-a-query_2.cs)]  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 Tento kód spustit, zkopírujte a vložte metodu do `StudentClass` , který je součástí [postupy: dotazování kolekci objektů](../../../csharp/programming-guide/linq-query-expressions/how-to-query-a-collection-of-objects.md) a volejte jej z `Main` metody.  
  
## <a name="see-also"></a>Viz také

- [Výrazy lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)  
- [Stromy výrazů (C#)](../concepts/expression-trees/index.md)  

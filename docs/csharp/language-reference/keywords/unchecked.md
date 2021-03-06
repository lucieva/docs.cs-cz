---
title: unchecked (Referenční dokumentace jazyka C#)
ms.date: 07/20/2015
f1_keywords:
- unchecked_CSharpKeyword
- unchecked
helpviewer_keywords:
- unchecked keyword [C#]
ms.assetid: 0c021f7c-923f-4b3d-a58f-55336f5ac27e
ms.openlocfilehash: daccd7916a9f81f26f468ab0f64833d9537cff8e
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/08/2018
ms.locfileid: "44206007"
---
# <a name="unchecked-c-reference"></a>unchecked (Referenční dokumentace jazyka C#)
`unchecked` – Klíčové slovo se používá k potlačení kontroly přetečení pro aritmetické operace s celými čísly a převody.  
  
 Nekontrolovaném kontextu Pokud výraz vytvoří hodnotu, která je mimo rozsah cílového typu přetečení, není označena. Například protože výpočet v následujícím příkladu se provádí v `unchecked` bloku nebo výraz, skutečnost, že je výsledek příliš velký pro celé číslo se ignoruje, a `int1` je přiřazena hodnota-2,147,483,639.  
  
 [!code-csharp[csrefKeywordsChecked#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/unchecked_1.cs)]  
  
 Pokud `unchecked` se odebere prostředí, dojde k chybě kompilace. Přetečení lze zjistit v době kompilace, protože všechny podmínky výrazu jsou konstanty.  
  
 Výrazy, které obsahují nekonstantní podmínky jsou ve výchozím nastavení zaškrtnuté políčko v době kompilace a čas spuštění. Zobrazit [zaškrtnutí](../../../csharp/language-reference/keywords/checked.md) informace o povolení kontrolované prostředí.  
  
 Protože kontrole pro přetečení trvá určitou dobu, použití nezaškrtnuto kódu v situacích, ve kterých je nehrozí nebezpečí přetečení může zlepšit výkon. Ale pokud přetečení je možné, by měl použít kontrolované prostředí.  
  
## <a name="example"></a>Příklad  
 Tento příklad ukazuje způsob použití `unchecked` – klíčové slovo.  
  
 [!code-csharp[csrefKeywordsChecked#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/unchecked_2.cs)]  
  
## <a name="c-language-specification"></a>Specifikace jazyka C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Viz také

- [Referenční dokumentace jazyka C#](../../../csharp/language-reference/index.md)  
- [Průvodce programováním v jazyce C#](../../../csharp/programming-guide/index.md)  
- [Klíčová slova jazyka C#](../../../csharp/language-reference/keywords/index.md)  
- [Zaškrtnuto a nezaškrtnuto](../../../csharp/language-reference/keywords/checked-and-unchecked.md)  
- [checked](../../../csharp/language-reference/keywords/checked.md)

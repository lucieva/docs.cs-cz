---
title: Předávání parametrů typu hodnoty (Průvodce programováním v C#)
ms.date: 07/20/2015
helpviewer_keywords:
- method parameters [C#], value types
- parameters [C#], value
ms.assetid: 193ab86f-5f9b-4359-ac29-7cdf8afad3a6
ms.openlocfilehash: 29dbaf9c16ee5d0ba6cfde872673a65acd2bac84
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/04/2018
ms.locfileid: "43523664"
---
# <a name="passing-value-type-parameters-c-programming-guide"></a>Předávání parametrů typu hodnoty (Průvodce programováním v C#)
A [typ hodnoty](../../../csharp/language-reference/keywords/value-types.md) proměnná obsahuje jeho data přímo jako nikoli [typu odkazu](../../../csharp/language-reference/keywords/reference-types.md) proměnnou, která obsahuje odkaz na svoje data. Předání hodnotou proměnné typu hodnoty metodě znamená předání kopii proměnné metodě. Žádné změny k parametru, které se provedou uvnitř metody nemají žádný vliv na původní data uložená v proměnné argumentu. Pokud chcete volané metody, chcete-li změnit hodnotu parametru, musíte jí předat odkazem, pomocí [ref](../../../csharp/language-reference/keywords/ref.md) nebo [si](../../../csharp/language-reference/keywords/out-parameter-modifier.md) – klíčové slovo. Můžete také použít [v](../../../csharp/language-reference/keywords/in-parameter-modifier.md) – klíčové slovo předávání pomocí odkazu, aby kopie při zajištění, že se nezmění hodnotu parametru hodnoty. Pro zjednodušení následující příklady používají `ref`.  
  
## <a name="passing-value-types-by-value"></a>Předávání typů hodnot podle hodnoty  
 Následující příklad ukazuje předání typu hodnoty parametrů podle hodnoty. Proměnná `n` je předán podle hodnoty do metody `SquareIt`. Všechny změny, které se provedou uvnitř metody mít žádný vliv na původní hodnotu proměnné.  
  
 [!code-csharp[csProgGuideParameters#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_1.cs)]  
  
 Proměnná `n` je typ hodnoty. Obsahuje data, hodnota `5`. Když `SquareIt` je vyvolána, obsah `n` se zkopírují do parametru `x`, který je druhou uvnitř metody. V `Main`, ale hodnota `n` je stejný po volání `SquareIt` metody, jak byl před. Změny, které u něho uvnitř metody, kterou ovlivňuje pouze místní proměnná `x`.  
  
## <a name="passing-value-types-by-reference"></a>Typy hodnot předávání odkazem.  
 Následující příklad je stejný jako předchozí příklad, s tím rozdílem, argument je předán jako `ref` parametru. Hodnota argumentu základní `n`, když se změní `x` se změnilo v metodě.  
  
 [!code-csharp[csProgGuideParameters#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_2.cs)]  
  
 V tomto příkladu není hodnota `n` , který je předán; místo toho odkaz na `n` je předán. Parametr `x` není [int](../../../csharp/language-reference/keywords/int.md); je odkaz na `int`, v tomto případě odkaz na `n`. Proto když `x` je spolehlivosti uvnitř metody, co skutečně je druhou je co `x` odkazuje, `n`.  
  
## <a name="swapping-value-types"></a>Vzájemná záměna typy hodnot  
 Běžným příkladem změny hodnot argumentů je metoda odkládacího souboru, můžete předat metodě k dispozici dvě proměnné, kde Metoda Zamění jejich obsah. Argumenty musí předat metodě prohození podle odkazu. V opačném případě prohození místních kopií parametry uvnitř metody a nedošlo k žádné změně ve volání metody. Následující příklad zaměňuje celočíselné hodnoty.  
  
 [!code-csharp[csProgGuideParameters#5](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_3.cs)]  
  
 Při volání `SwapByRef` metody, použijte `ref` – klíčové slovo ve volání, jak je znázorněno v následujícím příkladu.  
  
 [!code-csharp[csProgGuideParameters#6](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_4.cs)]  
  
## <a name="see-also"></a>Viz také

- [Průvodce programováním v jazyce C#](../../../csharp/programming-guide/index.md)  
- [Předávání parametrů](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md)  
- [Předávání parametrů typu odkazu](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md)

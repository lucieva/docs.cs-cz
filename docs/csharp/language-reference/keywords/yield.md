---
title: yield (Referenční dokumentace jazyka C#)
ms.date: 07/20/2015
f1_keywords:
- yield
- yield_CSharpKeyword
helpviewer_keywords:
- yield keyword [C#]
ms.assetid: 1089194f-9e53-46a2-8642-53ccbe9d414d
ms.openlocfilehash: be93b91ceaecdcf00029be57f07b9237a60c07b9
ms.sourcegitcommit: 700b9003ea6bdd83a53458bbc436c9b5778344f1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/03/2018
ms.locfileid: "48261538"
---
# <a name="yield-c-reference"></a>yield (Referenční dokumentace jazyka C#)
Při použití `yield` [kontextové klíčové slovo](../../../csharp/language-reference/keywords/index.md#contextual-keywords) v příkazu, dáváte tak najevo, metoda, operátor nebo `get` přístupový objekt, ve kterém se zobrazí, je iterátor. Pomocí `yield` k definování iterátor už není nutné explicitní extra třídy (třídy, která definuje stav výčtu, viz <xref:System.Collections.Generic.IEnumerator%601> příklad) při implementaci <xref:System.Collections.IEnumerable> a <xref:System.Collections.IEnumerator> vzor pro vlastní shromažďování Zadejte.  
  
 Následující příklad ukazuje dvě formy `yield` příkazu.  
  
```csharp  
yield return <expression>;  
yield break;  
```  
  
## <a name="remarks"></a>Poznámky  
 Můžete použít `yield return` příkaz vrátit vždy jeden prvek v čase.  
  
 Metodu iterátoru spotřebujete pomocí [foreach](../../../csharp/language-reference/keywords/foreach-in.md) příkaz nebo dotaz LINQ. Každá iterace `foreach` smyčky zavolá metodu iterátoru. Když `yield return` je v metodě iterátoru dosažen příkaz `expression` dochází, a je zachováno aktuální umístění v kódu. Provádění je restartováno ze zmíněného umístění pokaždé, když je zavolána funkce iterátoru.  
  
 Můžete použít `yield break` příkaz do konce iterace.  
  
 Další informace o iterátorech naleznete v tématu [iterátory](../../iterators.md).  
  
## <a name="iterator-methods-and-get-accessors"></a>Iterátory a přístupové objekty get  
 Deklarace iterátoru musí splňovat následující požadavky:  
  
-   Návratový typ musí být <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, nebo <xref:System.Collections.Generic.IEnumerator%601>.  
  
-   Deklarace nemůže mít žádnou [v](../../../csharp/language-reference/keywords/in-parameter-modifier.md) [ref](../../../csharp/language-reference/keywords/ref.md) nebo [si](../../../csharp/language-reference/keywords/out-parameter-modifier.md) parametry.  
  
 `yield` Typ iterátoru, který vrací <xref:System.Collections.IEnumerable> nebo <xref:System.Collections.IEnumerator> je `object`.  Pokud iterátor vrátí <xref:System.Collections.Generic.IEnumerable%601> nebo <xref:System.Collections.Generic.IEnumerator%601>, musí existovat implicitní převod z typu výrazu v `yield return` příkazu parametr obecného typu.  
  
 Není možné zahrnout `yield return` nebo `yield break` příkaz v metodách, které mají následující vlastnosti:  
  
-   Anonymní metody. Další informace najdete v tématu [anonymní metody](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md).  
  
-   Metody, které obsahují nebezpečné bloky. Další informace najdete v tématu [nebezpečné](../../../csharp/language-reference/keywords/unsafe.md).  
  
## <a name="exception-handling"></a>Zpracování výjimek  
 A `yield return` příkaz nelze umístit do bloku try-catch. A `yield return` příkaz lze umístit do bloku try příkazu try-finally.  
  
 A `yield break` příkaz lze umístit do bloku try nebo catch bloku, ale ne bloku finally.  
  
 Pokud `foreach` text (mimo metodu iterátoru) vyvolá výjimku, `finally` je proveden blok v metodě iterátoru.  
  
## <a name="technical-implementation"></a>Technická implementace  
 V následujícím kódu vrátí `IEnumerable<string>` z metody iterátoru a poté iteruje skrz příslušné prvky.  
  
```csharp  
IEnumerable<string> elements = MyIteratorMethod();  
foreach (string element in elements)  
{  
   ...  
}  
```  
  
 Volání `MyIteratorMethod` neprovede tělo metody. Místo toho volání vrátí `IEnumerable<string>` do `elements` proměnné.  
  
 Při iteraci `foreach` smyčky, <xref:System.Collections.IEnumerator.MoveNext%2A> metoda je volána pro `elements`. Toto volání provádí tělo `MyIteratorMethod` až do další `yield return` je dosažen příkaz. Výraz vrácený příkazem `yield return` příkaz určuje nejen hodnotu `element` proměnné k využití v těle smyčky, ale také <xref:System.Collections.Generic.IEnumerator%601.Current%2A> vlastnost `elements`, což je `IEnumerable<string>`.  
  
 Na každé další iteraci `foreach` smyčky, tělo iterátoru pokračuje odkud zastaví se opět tehdy, když se dosáhne `yield return` příkazu. `foreach` Smyčka dokončena, jakmile konce metody iterátoru nebo `yield break` je dosažen příkaz.  
  
## <a name="example"></a>Příklad  
 Následující příklad obsahuje `yield return` , který se nachází uvnitř `for` smyčky. Každá iterace `foreach` tělo s příkazy v `Main` metoda vytvoří volání `Power` funkce iterátoru. Každé volání funkce iterátoru pokračuje do dalšího provedení příkazu `yield return` prohlášení, které nastane při další iteraci `for` smyčky.  
  
 Návratový typ metody iterátoru je <xref:System.Collections.IEnumerable>, což je typ rozhraní iterátoru. Při volání metody iterátoru je vrácen vyčíslitelný objekt, který obsahuje mocniny čísla.  
  
 [!code-csharp[csrefKeywordsContextual#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/yield_1.cs)]  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje `get` přístupovou metodu iterátoru. V tomto příkladu každá `yield return` příkazu vrátí instanci třídy definované uživatelem.  
  
 [!code-csharp[csrefKeywordsContextual#21](../../../csharp/language-reference/keywords/codesnippet/CSharp/yield_2.cs)]  
  
## <a name="c-language-specification"></a>Specifikace jazyka C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Viz také

- [Referenční dokumentace jazyka C#](../../../csharp/language-reference/index.md)  
- [Průvodce programováním v jazyce C#](../../../csharp/programming-guide/index.md)  
- [foreach, in](../../../csharp/language-reference/keywords/foreach-in.md)  
- [Iterátory](../../iterators.md)

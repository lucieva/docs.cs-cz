---
title: Polymorfismus (Průvodce programováním v C#)
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, polymorphism
- polymorphism [C#]
ms.assetid: 086af969-29a5-4ce8-a993-0b7d53839dab
ms.openlocfilehash: 25192d57955d15c5707816ee6c4a515893891507
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/04/2018
ms.locfileid: "43523390"
---
# <a name="polymorphism-c-programming-guide"></a>Polymorfismus (Průvodce programováním v C#)
Polymorfismus se často označuje jako třetí ze čtyř pilířů objektově orientované programování po zapouzdření a dědičnosti. Polymorfismus řecké slovo, které znamená "mnoho ve tvaru" a má dva různé aspekty:  
  
-   V době běhu můžou se považovat objekty odvozené třídy základní třídy na místech, jako je například parametry metody a kolekce nebo pole objektů. Pokud k tomu dojde, deklarovaného typu objektu již není stejný jako jeho typ za běhu.  
  
-   Základní třídy mohou definovat a implementovat [virtuální](../../../csharp/language-reference/keywords/virtual.md) *metody*, a mohou odvozené třídy [přepsat](../../../csharp/language-reference/keywords/override.md) je, což znamená, že poskytují vlastní definice a implementaci. V době běhu když klientský kód volá metodu, CLR vyhledá run-time typu objektu a vyvolá tuto přepsat virtuální metodu. Proto ve zdrojovém kódu můžete volat metodu v základní třídě a způsobit, že odvozené třídy verzi metody, který se spustí.  
  
 Virtuální metody umožňují pracovat se skupinami souvisejících objektů jednotným způsobem. Předpokládejme například, že máte kreslicí aplikace, která umožňuje uživateli vytvořit různé druhy obrazců na návrhovém povrchu. Si nejste jisti v době kompilace jaké konkrétní typy tvary uživatel vytvořit. Ale aplikace musí udržovat přehled o různých typech tvary, které jsou vytvořeny a musí je aktualizovat v reakci na akce myši uživatele. Polymorfismus můžete použít pro vyřešení tohoto problému v dva základní kroky:  
  
1.  Vytvoření hierarchie třídy, ve kterém každý konkrétní tvar třída odvozena z obecnou základní třídu.  
  
2.  Použijte virtuální metoda k vyvolání metody odpovídající na všechny odvozené třídy pomocí jednoho volání metody základní třídy.  
  
 Nejprve vytvořte základní třídu s názvem `Shape`a odvozené třídy jako `Rectangle`, `Circle`, a `Triangle`. Poskytují `Shape` třídy virtuální metody volá `Draw`, a představuje přepsání, které v jednotlivých odvozené třídy za účelem vykreslení konkrétní obrazce třídy. Vytvoření `List<Shape>` objektu a k němu přidejte kruh, trojúhelník a obdélník. Chcete-li aktualizovat na návrhovém povrchu, použijte [foreach](../../../csharp/language-reference/keywords/foreach-in.md) smyčky k iteraci v rámci seznamu a volání `Draw` metodu na každý `Shape` objekt v seznamu. Přestože se každý objekt v seznamu má deklarovaný typ `Shape`, je typu za běhu (verze přepsané metody v každé odvozené třídy), která bude vyvolána.  
  
 [!code-csharp[csProgGuideInheritance#50](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/polymorphism_1.cs)]  
  
 V jazyce C#, je polymorfní každý typ, protože všechny typy, včetně uživatelem definované typy dědí <xref:System.Object>.  
  
## <a name="polymorphism-overview"></a>Polymorfismus přehled  
  
### <a name="virtual-members"></a>Virtuální členové  
 Pokud je odvozená třída dědí ze základní třídy, získává všechny metody, pole, vlastnosti a události základní třídy. Návrhář odvozené třídy můžete zvolit, jestli se má  
  
-   přepsat virtuální členy základní třídy  
  
-   dědit nejbližší metodu základní třídy bez jeho přepsání  
  
-   definujte novou implementaci nevirtuální těchto členů, které skrýt implementace základní třídy  
  
 Odvozená třída může přepsat člena základní třídy pouze v případě, že členu základní třídy je deklarován jako [virtuální](../../../csharp/language-reference/keywords/virtual.md) nebo [abstraktní](../../../csharp/language-reference/keywords/abstract.md). Odvozené člen musí používat [přepsat](../../../csharp/language-reference/keywords/override.md) – klíčové slovo explicitně určit, že metoda je určena k účasti v virtuální volání. Následující kód představuje příklad:  
  
 [!code-csharp[csProgGuideInheritance#20](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/polymorphism_2.cs)]  
  
 Pole nemůže být virtuální; pouze metody, vlastnosti, události a indexerů může být virtuální. Je-li odvozená třída přepíše člena virtuální, se kterou nazývá i v případě, že instance této třídy je přistupováno jako jedna instance základní třídy. Následující kód představuje příklad:  
  
 [!code-csharp[csProgGuideInheritance#21](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/polymorphism_3.cs)]  
  
 Virtuální metody a vlastnosti umožňují odvozené třídy pro rozšíření bez nutnosti použít implementaci základní třídy metody základní třídy. Další informace najdete v tématu [Správa verzí pomocí nových klíčových slov Override a](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md). Rozhraní obsahuje jiný způsob, jak definovat metodu nebo sadu metod, jejichž implementace je ponecháno na odvozené třídy. Další informace najdete v tématu [rozhraní](../../../csharp/programming-guide/interfaces/index.md).  
  
### <a name="hiding-base-class-members-with-new-members"></a>Skrytí členy základní třídy s novými členy  
 Pokud chcete vaše odvozené člen mají stejný název jako členem v základní třídě, ale nechcete, aby ho účastnit virtuální volání, můžete použít [nové](../../../csharp/language-reference/keywords/new.md) – klíčové slovo. `new` – Klíčové slovo je umístěn před návratovým typem, který se nahrazuje člena třídy. Následující kód představuje příklad:  
  
 [!code-csharp[csProgGuideInheritance#18](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/polymorphism_4.cs)]  
  
 Členy skryté základní třídy je pořád přístupný z klientského kódu přetypování instance odvozené třídy do instance základní třídy. Příklad:  
  
 [!code-csharp[csProgGuideInheritance#19](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/polymorphism_5.cs)]  
  
### <a name="preventing-derived-classes-from-overriding-virtual-members"></a>Zabrání přepsání virtuální členy odvozených tříd  
 Virtuální členové zůstanou po neomezenou dobu, bez ohledu na tom, kolik třídy byly prohlášeny mezi virtuální člen a třídy, která původně deklarovala virtuální. Pokud třída A deklaruje virtuální člen a třídy B je odvozena od A a b je odvozena třída jazyka C, tříd C dědí virtuální člen a má možnost přepsat, bez ohledu na to, jestli třídy B pro tento člen deklarovaný přepsání. Následující kód představuje příklad:  
  
 [!code-csharp[csProgGuideInheritance#22](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/polymorphism_6.cs)]  
  
 Odvozená třída může zastavit virtuální dědičnost deklarováním jako přepsání [zapečetěné](../../../csharp/language-reference/keywords/sealed.md). To vyžaduje, aby uvedení `sealed` – klíčové slovo před `override` – klíčové slovo v deklaraci třídy člena. Následující kód představuje příklad:  
  
 [!code-csharp[csProgGuideInheritance#24](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/polymorphism_7.cs)]  
  
 V předchozím příkladu metoda `DoWork` už není virtuální pro jakoukoli třídu odvozenou z C. Je stále virtuální pro instance jazyka C, i když jsou přetypovat na typ nebo typ B A. zapečetěné metody lze nahradit odvozené třídy pomocí `new` – klíčové slovo, jako v následujícím příkladu:  
  
 [!code-csharp[csProgGuideInheritance#25](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/polymorphism_8.cs)]  
  
 V takovém případě pokud `DoWork` je volán na použití proměnné typu D, D nové `DoWork` je volána. Pokud je proměnná typu jazyka C, B nebo A slouží k přístupu k instance D, volání `DoWork` bude pravidlům virtuální dědičnost, směrování volání selžou provádění `DoWork` ve třídě C.  
  
### <a name="accessing-base-class-virtual-members-from-derived-classes"></a>Přístup k virtuální členy základní třídy z odvozené třídy  
 Odvozená třída, která má nahradit nebo přepsat metodu nebo vlastnost k němu přístup metody nebo vlastnosti v základní třídě pomocí klíčového slova base. Následující kód představuje příklad:  
  
 [!code-csharp[csProgGuideInheritance#26](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/polymorphism_9.cs)]  
  
 Další informace najdete v tématu [základní](../../../csharp/language-reference/keywords/base.md).  
  
> [!NOTE]
>  Doporučuje se, že používat virtuální členy `base` volat implementaci základní třídy, se kterou v jejich vlastní implementaci. Umožňuje chování základní třídy dojít umožňuje odvozené třídy soustředit na implementaci chování specifické pro odvozenou třídu. Pokud není volána implementace základní třídy, záleží odvozené třídy, aby jejich chování kompatibilní s chováním základní třídy.  
  
## <a name="in-this-section"></a>V tomto oddílu  
  
-   [Správa verzí pomocí klíčových slov override a new](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md)  
  
-   [Znalost, kdy použít klíčová slova override a new](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md)  
  
-   [Postupy: Potlačení metody ToString](../../../csharp/programming-guide/classes-and-structs/how-to-override-the-tostring-method.md)  
  
## <a name="see-also"></a>Viz také

- [Průvodce programováním v jazyce C#](../../../csharp/programming-guide/index.md)  
- [Průvodce programováním v jazyce C#](../../../csharp/programming-guide/index.md)  
- [Dědičnost](../../../csharp/programming-guide/classes-and-structs/inheritance.md)  
- [Abstraktní a uzavřené třídy a jejich členové](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)  
- [Metody](../../../csharp/programming-guide/classes-and-structs/methods.md)  
- [Události](../../../csharp/programming-guide/events/index.md)  
- [Vlastnosti](../../../csharp/programming-guide/classes-and-structs/properties.md)  
- [Indexery](../../../csharp/programming-guide/indexers/index.md)  
- [Typy](../../../csharp/programming-guide/types/index.md)

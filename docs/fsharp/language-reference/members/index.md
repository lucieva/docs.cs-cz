---
title: Členy (F#)
description: Další informace o členy objektu F# programovací jazyk.
ms.date: 05/16/2016
ms.openlocfilehash: 6dcdb1d7fa061fb838d4aa8f7a2912fd168c3781
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/02/2018
ms.locfileid: "33562203"
---
# <a name="members"></a>Členové

Tato část popisuje členy F# typy objektů.


## <a name="remarks"></a>Poznámky
*Členové* jsou funkce, které jsou součástí definice typu a jsou deklarovány pomocí `member` – klíčové slovo. F#typy objektů, jako jsou záznamy, třídy, rozlišovaná sjednocení, rozhraní, a podporu členů struktury. Další informace najdete v tématu [záznamy](../records.md), [třídy](../classes.md), [Rozlišované sjednocení](../discriminated-Unions.md), [rozhraní](../interfaces.md), a [struktury](../structures.md).

Členové obvykle tvoří veřejného rozhraní pro typ, který je důvod, proč jsou veřejné, pokud není uvedeno jinak. Členové mohou být deklarovány také soukromý nebo interní. Další informace najdete v tématu [řízení přístupu](../access-Control.md). Podpisy pro typy lze také vystavit nebo bez odkrytí některé členy typu. Další informace najdete v tématu [podpisy](../signatures.md).

Privátní pole a `do` vazeb, které se používají pouze s třídami, nejsou členy hodnotu true, protože jsou součástí veřejného rozhraní typu nikdy a nejsou deklarovány s `member` – klíčové slovo, ale jsou popsané v této části taky.


## <a name="related-topics"></a>Související témata


|Téma|Popis|
|-----|-----------|
|[`let` Vazby ve třídách](let-bindings-in-classes.md)|Popisuje definici privátního polí a funkcí v třídách.|
|[`do` Vazby ve třídách](do-bindings-in-classes.md)|Popisuje specifikace kód inicializace objektu.|
|[Vlastnosti](properties.md)|Popisuje vlastnosti členů v třídami a ostatními typy.|
|[Indexované vlastnosti](indexed-properties.md)|Popisuje vlastnosti jako pole v třídami a ostatními typy.|
|[Metody](methods.md)|Popisuje funkce, které jsou členy typu.|
|[Konstruktory](constructors.md)|Popisuje speciálních funkcí, které je třeba inicializovat objekty typu.|
|[Přetížení operátoru](../operator-overloading.md)|Popisuje definice pro typy vlastní operátory.|
|[Události](events.md)|Popisuje definici událostí a podpora ve zpracování událostí F#.|
|[Explicitní pole: Klíčové slovo `val`](explicit-fields-the-val-keyword.md)|Popisuje definice neinicializované pole typu.|

---
title: Tabulka celočíselných typů (referenční dokumentace jazyka C#)
description: Přehled integrované C# integrální typy
ms.date: 08/20/2018
helpviewer_keywords:
- integral types, C#
- Visual C#, integral types
- types [C#], integral types
- ranges of integral types [C#]
ms.assetid: 62e86126-46ff-40b0-9028-e61d7558268c
ms.openlocfilehash: 4ac16d185a52cdb03fcb22f57ebf7506f2fb2745
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/07/2018
ms.locfileid: "44078845"
---
# <a name="integral-types-table-c-reference"></a>Tabulka celočíselných typů (referenční dokumentace jazyka C#)

V následující tabulce jsou uvedeny velikosti a rozsah celočíselných typů, které představují podmnožinu jednoduchých typů.  
  
|Typ|Rozsah|Velikost|  
|----------|-----------|----------|  
|[sbyte](sbyte.md)|-128 až 127|8bitové celé číslo se znaménkem|  
|[byte](byte.md)|0 až 255|Celé číslo bez znaménka 8 bitů|  
|[char](char.md)|U + 0000 U + ffff|16bitový znak Unicode|  
|[short](short.md)|-32 768 do 32 767|16bitové celé číslo se znaménkem|  
|[ushort](ushort.md)|0 až 65 535|Celé číslo bez znaménka 16 bitů|  
|[int](int.md)|-2 147 483 648 do 2 147 483 647|32bitové celé číslo se znaménkem|  
|[uint](uint.md)|0 do 4 294 967 295|Nepodepsané 32bitové celé číslo|  
|[long](long.md)|-9,223,372,036,854,775,808 k 9,223,372,036,854,775,807|64bitové celé číslo se znaménkem|  
|[ulong](ulong.md)|0 na 18,446,744,073,709,551,615|64-bit znaménka.|  

## <a name="remarks"></a>Poznámky
  
Pokud se překročí Hodnota reprezentovaná celočíselného literálu <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, chybu kompilátoru [CS1021](../../misc/cs1021.md) vyvolá.

Použití <xref:System.Numerics.BigInteger?displayProperty=nameWithType> pro reprezentaci libovolně velké podepsané celé číslo.
  
## <a name="see-also"></a>Viz také:

- [Referenční dokumentace jazyka C#](../index.md)
- [Průvodce programováním v jazyce C#](../../programming-guide/index.md)
- [Klíčová slova jazyka C#](index.md)
- [Referenční tabulky pro typy](reference-tables-for-types.md)
- [Tabulka typů s plovoucí desetinnou čárkou](floating-point-types-table.md)
- [Tabulka výchozích hodnot](default-values-table.md)
- [Tabulka formátování číselných výsledků](formatting-numeric-results-table.md)
- [Tabulka předdefinovaných typů](built-in-types-table.md)

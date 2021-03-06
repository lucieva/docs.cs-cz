---
title: Zaškrtnuto a nezaškrtnuto (Referenční dokumentace jazyka C#)
ms.date: 05/15/2018
helpviewer_keywords:
- operators [C#], checked and unchecked
- exceptions [C#], overflow checking
- checked statement [C#]
- overflow checking [C#]
- unchecked statement [C#]
- statements [C#], checked and unchecked
ms.assetid: a84bc877-2c7f-4396-8735-1ce97c42f35e
ms.openlocfilehash: 04f603905690497bcd4249f73c7296be2c269a60
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/05/2018
ms.locfileid: "43741929"
---
# <a name="checked-and-unchecked-c-reference"></a>Zaškrtnuto a nezaškrtnuto (Referenční dokumentace jazyka C#)
Příkazy jazyka C# lze spustit v kontextu zaškrtnuté nebo nezaškrtnuté. Aritmetické přetečení ve zkontrolovaném kontextu, vyvolá výjimku. V nekontrolovaném kontextu je ignorován Přetečení aritmetické operace a výsledek je rozdělená do se zahodí všechny bity nejvyšším, které se nehodí do cílového typu.  
  
-   [checked](checked.md) kontextu zadejte zaškrtnuto.  
  
-   [unchecked](unchecked.md) zadejte nezkontrolovaném kontextu.  
  
 Tyto operace jsou ovlivněny kontrola přetečení:  
  
-   Pomocí následující předdefinované operátory na integrální typy výrazů:  
  
     `++`, `--`, unární `-`, `+`, `-`, `*`, `/`  
  
-   Explicitní číselné převody mezi celočíselnými typy nebo z `float` nebo `double` na celočíselný typ.  
  
 Pokud ani `checked` ani `unchecked` není zadán, výchozí kontext pro výrazy nekonstantní (výrazy, které jsou vyhodnocovány v době běhu) je definován hodnotou [-checked](../compiler-options/checked-compiler-option.md) – možnost kompilátoru. Ve výchozím nastavení má tato možnost hodnotu unset a aritmetické operace jsou provedeny v nekontrolovaném kontextu.
 
 Pro konstantní výrazy (výrazy, které může být plně vyhodnocen v době kompilace) je vždy zaškrtnuto výchozí kontext. Pokud není konstantní výraz je explicitně umístěné v nekontrolovaném kontextu, přetečení, ke kterým dochází při vyhodnocení za kompilace výrazu způsobit chyby kompilace.
  
## <a name="see-also"></a>Viz také  

- [Referenční dokumentace jazyka C#](../index.md)  
- [Průvodce programováním v jazyce C#](../../programming-guide/index.md)  
- [Klíčová slova jazyka C#](index.md)  
- [Klíčová slova příkazů](statement-keywords.md)

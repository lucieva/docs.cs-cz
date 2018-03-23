---
title: -refout (Visual Basic)
ms.date: 03/16/2018
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [Visual Basic]
- /refout compiler option [Visual Basic]
- -refout compiler option [Visual Basic]
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d6075b92efd1eec9797fca248e97a325bd5df4bb
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/23/2018
---
# <a name="-refout-visual-basic"></a>-refout (Visual Basic)

**- Refout** možnost určuje cestu k souboru, kde referenční sestavení by měla být výstup.

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a>Syntaxe

```console
-refout:filepath
```

## <a name="arguments"></a>Arguments

 `filepath` Cesta a název souboru referenční sestavení. Obecně je nutné v dílčí složce primární sestavení. Doporučené konvence (používané MSBuild) je umístit referenční sestavení v "ref nebo" podsložky relativně k primární sestavení. Všechny složky v `filepath` musí existovat; kompilátor je nevytvoří. 

## <a name="remarks"></a>Poznámky

Podporuje jazyka Visual Basic `-refout` přepínače, počínaje verzí 15.3.

Referenční sestavení jsou pouze metadata sestavení, které obsahují metadata, ale žádný kód implementace. Obsahují informace o typu a členu pro všechno kromě anonymní typy. Jejich těla metody nahrazená s jedním `throw null` příkaz. Důvod použití `throw null` těla metody (na rozdíl od žádné těla) je tak, aby PEVerify můžete spustit a předat (tedy ověření úplnost metadat).

Zahrnout odkaz na sestavení úrovni sestavení [ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) atribut. Tento atribut je možné zadat zdroj (pak kompilátor nebudete muset syntetizace ji). Z důvodu tohoto atributu moduly runtime odmítnout načíst odkaz na sestavení pro spuštění (ale stále může být načteno do kontextu pouze pro reflexi). Nástroje, které odráží sestavení potřeba zajistit, že se načíst odkaz na sestavení jako pouze pro reflexi; jinak, modul runtime vyvolá <xref:System.BadImageFormatException>.

`-refout` a [ `-refonly` ](refonly-compiler-option.md) možnosti se vzájemně vylučují.

## <a name="see-also"></a>Viz také
[-refonly](refonly-compiler-option.md)   
[Visual Basic Command-Line Compiler](index.md)  
[Příkazové řádky ukázkové kompilace](sample-compilation-command-lines.md)  

---
title: Seznam atributů (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- attribute list
- attributes [Visual Basic], applying
ms.assetid: 5880073a-68a4-4b6b-8a07-ace32959a4e2
ms.openlocfilehash: 23f2004a34f5d6dc27c8263f6e66642dd32c6a5f
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/10/2018
ms.locfileid: "37936926"
---
# <a name="attribute-list-visual-basic"></a>Seznam atributů (Visual Basic)
Určuje atributy, které se použijí pro deklarovaný programový prvek. Více atributů jsou odděleny čárkami. Následuje syntaxe pro jeden atribut.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
[ attributemodifier ] attributename [ ( attributearguments | attributeinitializer ) ]  
```  
  
## <a name="parts"></a>Součásti  
|||
|---|---|
|`attributemodifier`|Vyžaduje se pro atributy použité na začátku zdrojového souboru. Může být [sestavení](../../../visual-basic/language-reference/modifiers/assembly.md) nebo [modulu](../../../visual-basic/language-reference/modifiers/module-keyword.md).|
|`attributename`| Požadováno. Název atributu.|
|`attributearguments`|Volitelné. Seznam poziční argumenty pro tento atribut. Více argumentů jsou odděleny čárkami.|
|`attributeinitializer`|Volitelné. Seznam inicializátorů proměnnou nebo vlastnost pro tento atribut. Více inicializátory jsou odděleny čárkami.|
  
## <a name="remarks"></a>Poznámky  
 Jeden nebo více atributů, které můžete použít na téměř jakýkoli programovací element (typy, postupy, vlastnosti a tak dále). Atributy se zobrazí v metadatech sestavení proto mohou pomoci při přidání poznámek ke kódu nebo určete, jak používat určitý programovací element. Můžete použít atributy definované ve Visual Basic a rozhraní .NET Framework a je možné definovat vlastní atributy.  

 Další informace o použití atributů naleznete v tématu [atributy přehled](../../../visual-basic/programming-guide/concepts/attributes/index.md). Informace o názvech atributů najdete v tématu [deklarované názvy elementů](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
## <a name="rules"></a>pravidla  
  
-   **Umístění.** Můžete použít atributy k nejvíce deklarovaný programový prvek. Pokud chcete použít jeden nebo více atributů, umístíte *bloku atributu* na začátku deklarace elementu. Každá položka v seznamu atributů určuje atribut, který chcete použít a modifikátor a argumenty, které používáte pro toto volání atributu.  
  
-   **Lomené závorky.** Pokud zadáte seznam atributů, je nutné uzavřít do lomené závorky ("`<`"a"`>`").  
  
-   **Část prohlášení.** Atribut musí být součástí deklarace elementu, ne samostatný příkaz. Můžete použít posloupností pokračování řádku (" `_`") pro rozšíření příkazu deklarace do více řádků zdrojového kódu.  
  
-   **Modifikátory.** Modifikátor atribut (`Assembly` nebo `Module`) je vyžadován na každý atribut na programovací prvek na začátku zdrojového souboru. Atribut modifikátory nejsou povoleny atributy u elementů, které nejsou na začátku zdrojového souboru.  
  
-   **Argumenty.** Všechny poziční argumenty pro atribut musí předcházet všechny proměnné nebo vlastnosti inicializátory.  
  
## <a name="example"></a>Příklad  
 Následující příklad se vztahuje <xref:System.Runtime.InteropServices.DllImportAttribute> atribut kostru definici typu `Function` postup.  
  
 [!code-vb[VbVbalrStatements#1](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/attribute-list_1.vb)]  
  
 <xref:System.Runtime.InteropServices.DllImportAttribute> Označuje, že s atributy postup představuje vstupní bod v nespravované dynamická knihovna (DLL). Atribut poskytuje název knihovny DLL jako poziční argument a další informace jako proměnné inicializátory.  
  
## <a name="see-also"></a>Viz také  
 [Assembly](../../../visual-basic/language-reference/modifiers/assembly.md)  
 [Modul \<– klíčové slovo >](../../../visual-basic/language-reference/modifiers/module-keyword.md)  
 [Přehled atributy](../../../visual-basic/programming-guide/concepts/attributes/index.md)  
 [Postupy: Přerušení a kombinace příkazů v kódu](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)

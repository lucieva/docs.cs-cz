---
title: '&#39;Jako kterákoli&#39; není podporována v &#39;Declare&#39; – příkazy'
ms.date: 07/20/2015
f1_keywords:
- bc30828
- vbc30828
helpviewer_keywords:
- BC30828
ms.assetid: 7e5cf519-8b64-4ac5-8116-705fe26c846d
ms.openlocfilehash: 34beaeb7178645d5a167d1b7b969bb3e4f500e1a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588223"
---
# <a name="39as-any39-is-not-supported-in-39declare39-statements"></a>&#39;Jako kterákoli&#39; není podporována v &#39;Declare&#39; – příkazy
`Any` Datový typ se použila se `Declare` příkazy v Visual Basic 6.0 a starší verze, které chcete povolit použití argumenty, které může obsahovat jakýkoli typ dat. Přetížení, ale podporuje jazyka Visual Basic a díky tomu tak `Any` datový typ zastaralé.  
  
 **ID chyby:** BC30828  
  
## <a name="to-correct-this-error"></a>Oprava této chyby  
  
1.  Deklarovat parametry specifický typ, který chcete použít; například.  
  
     [!code-vb[VbVbalrStatements#95](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/as-any-is-not-supported-in-declare-statements_1.vb)]  
  
2.  Použití <xref:System.Runtime.InteropServices.MarshalAsAttribute> atribut k určení `As Any` při `Void*` je očekáváno procedura volaná.  
  
     [!code-vb[VbVbalrStatements#96](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/as-any-is-not-supported-in-declare-statements_2.vb)]  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [Návod: Volání rozhraní API systému Windows](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)  
 [Příkaz Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [Vytváření prototypů ve spravovaném kódu](../../../framework/interop/creating-prototypes-in-managed-code.md)

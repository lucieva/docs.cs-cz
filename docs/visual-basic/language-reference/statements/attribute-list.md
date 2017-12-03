---
title: "Seznam atributů (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- attribute list
- attributes [Visual Basic], applying
ms.assetid: 5880073a-68a4-4b6b-8a07-ace32959a4e2
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: adfb980380bb787280715ca0185950657e174eb1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="attribute-list-visual-basic"></a><span data-ttu-id="b1e20-102">Seznam atributů (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b1e20-102">Attribute List (Visual Basic)</span></span>
<span data-ttu-id="b1e20-103">Určuje atributy, které se použijí na deklarované programovací element.</span><span class="sxs-lookup"><span data-stu-id="b1e20-103">Specifies the attributes to be applied to a declared programming element.</span></span> <span data-ttu-id="b1e20-104">Více atributů jsou oddělené čárkami.</span><span class="sxs-lookup"><span data-stu-id="b1e20-104">Multiple attributes are separated by commas.</span></span> <span data-ttu-id="b1e20-105">Toto je syntaxe pro jeden atribut.</span><span class="sxs-lookup"><span data-stu-id="b1e20-105">Following is the syntax for one attribute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1e20-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="b1e20-106">Syntax</span></span>  
  
```  
[ attributemodifier ] attributename [ ( attributearguments | attributeinitializer ) ]  
```  
  
## <a name="parts"></a><span data-ttu-id="b1e20-107">Součásti</span><span class="sxs-lookup"><span data-stu-id="b1e20-107">Parts</span></span>  
 `attributemodifier`  
 <span data-ttu-id="b1e20-108">Vyžaduje se pro atributy použité na začátku zdrojového souboru.</span><span class="sxs-lookup"><span data-stu-id="b1e20-108">Required for attributes applied at the beginning of a source file.</span></span> <span data-ttu-id="b1e20-109">Může být [sestavení](../../../visual-basic/language-reference/modifiers/assembly.md) nebo [modulu](../../../visual-basic/language-reference/modifiers/module-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="b1e20-109">Can be [Assembly](../../../visual-basic/language-reference/modifiers/assembly.md) or [Module](../../../visual-basic/language-reference/modifiers/module-keyword.md).</span></span>  
  
 `attributename`  
 <span data-ttu-id="b1e20-110">Požadováno.</span><span class="sxs-lookup"><span data-stu-id="b1e20-110">Required.</span></span> <span data-ttu-id="b1e20-111">Název atributu.</span><span class="sxs-lookup"><span data-stu-id="b1e20-111">Name of the attribute.</span></span>  
  
 `attributearguments`  
 <span data-ttu-id="b1e20-112">Volitelné.</span><span class="sxs-lookup"><span data-stu-id="b1e20-112">Optional.</span></span> <span data-ttu-id="b1e20-113">Seznam argumentů umístění pro tento atribut.</span><span class="sxs-lookup"><span data-stu-id="b1e20-113">List of positional arguments for this attribute.</span></span> <span data-ttu-id="b1e20-114">Více argumentů jsou oddělené čárkami.</span><span class="sxs-lookup"><span data-stu-id="b1e20-114">Multiple arguments are separated by commas.</span></span>  
  
 `attributeinitializer`  
 <span data-ttu-id="b1e20-115">Volitelné.</span><span class="sxs-lookup"><span data-stu-id="b1e20-115">Optional.</span></span> <span data-ttu-id="b1e20-116">Seznam inicializátory proměnné nebo vlastnosti pro tento atribut.</span><span class="sxs-lookup"><span data-stu-id="b1e20-116">List of variable or property initializers for this attribute.</span></span> <span data-ttu-id="b1e20-117">Více inicializátory jsou oddělené čárkami.</span><span class="sxs-lookup"><span data-stu-id="b1e20-117">Multiple initializers are separated by commas.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b1e20-118">Poznámky</span><span class="sxs-lookup"><span data-stu-id="b1e20-118">Remarks</span></span>  
 <span data-ttu-id="b1e20-119">Můžete použít jeden nebo více atributů na téměř všechny programovací element (typy, postupy, vlastnosti a tak dále).</span><span class="sxs-lookup"><span data-stu-id="b1e20-119">You can apply one or more attributes to nearly any programming element (types, procedures, properties, and so forth).</span></span> <span data-ttu-id="b1e20-120">Atributy se zobrazí v metadatech vaše sestavení a pomohou vám opatřit poznámkami kódu nebo zadejte, jak používat určitý programovací element.</span><span class="sxs-lookup"><span data-stu-id="b1e20-120">Attributes appear in your assembly's metadata, and they can help you annotate your code or specify how to use a particular programming element.</span></span> <span data-ttu-id="b1e20-121">Můžete použít atributy definované ve Visual Basic a rozhraní .NET Framework a je možné definovat vlastní atributy.</span><span class="sxs-lookup"><span data-stu-id="b1e20-121">You can apply attributes defined by Visual Basic and the .NET Framework, and you can define your own attributes.</span></span>  

 <span data-ttu-id="b1e20-122">Další informace o použití atributů naleznete v tématu [atributy přehled](../../../visual-basic/programming-guide/concepts/attributes/index.md).</span><span class="sxs-lookup"><span data-stu-id="b1e20-122">For more information on when to use attributes, see [Attributes overview](../../../visual-basic/programming-guide/concepts/attributes/index.md).</span></span> <span data-ttu-id="b1e20-123">Informace o názvech atributů najdete v tématu [deklarované názvy elementů](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="b1e20-123">For information on attribute names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="b1e20-124">Pravidla</span><span class="sxs-lookup"><span data-stu-id="b1e20-124">Rules</span></span>  
  
-   <span data-ttu-id="b1e20-125">**Umístění.**</span><span class="sxs-lookup"><span data-stu-id="b1e20-125">**Placement.**</span></span> <span data-ttu-id="b1e20-126">Atributy můžete použít k nejvíce deklarované elementům programování.</span><span class="sxs-lookup"><span data-stu-id="b1e20-126">You can apply attributes to most declared programming elements.</span></span> <span data-ttu-id="b1e20-127">Chcete-li použít jeden nebo více atributů, umístěte *atribut bloku* na začátku prohlášení element.</span><span class="sxs-lookup"><span data-stu-id="b1e20-127">To apply one or more attributes, you place an *attribute block* at the beginning of the element declaration.</span></span> <span data-ttu-id="b1e20-128">Každá položka v seznamu atributů určuje atribut, který chcete použít a modifikátor a argumenty, které používáte pro toto volání atributu.</span><span class="sxs-lookup"><span data-stu-id="b1e20-128">Each entry in the attribute list specifies an attribute you wish to apply, and the modifier and arguments you are using for this invocation of the attribute.</span></span>  
  
-   <span data-ttu-id="b1e20-129">**Lomené závorky.**</span><span class="sxs-lookup"><span data-stu-id="b1e20-129">**Angle Brackets.**</span></span> <span data-ttu-id="b1e20-130">Pokud zadáte jenom seznam atributů, je nutné uzavřít do lomené závorky ("`<`"a"`>`").</span><span class="sxs-lookup"><span data-stu-id="b1e20-130">If you supply an attribute list, you must enclose it in angle brackets ("`<`" and "`>`").</span></span>  
  
-   <span data-ttu-id="b1e20-131">**Součástí deklarace.**</span><span class="sxs-lookup"><span data-stu-id="b1e20-131">**Part of the Declaration.**</span></span> <span data-ttu-id="b1e20-132">Atribut musí být součástí deklaraci elementu, nikoli samostatný příkaz.</span><span class="sxs-lookup"><span data-stu-id="b1e20-132">The attribute must be part of the element declaration, not a separate statement.</span></span> <span data-ttu-id="b1e20-133">Můžete použít posloupnost pokračování řádku (" `_`") k rozšíření příkaz deklarace na více řádků zdrojového kódu.</span><span class="sxs-lookup"><span data-stu-id="b1e20-133">You can use the line-continuation sequence (" `_`") to extend the declaration statement onto multiple source-code lines.</span></span>  
  
-   <span data-ttu-id="b1e20-134">**Modifikátory.**</span><span class="sxs-lookup"><span data-stu-id="b1e20-134">**Modifiers.**</span></span> <span data-ttu-id="b1e20-135">Atributu – modifikátor (`Assembly` nebo `Module`) je potřeba na každý atribut použitý programovací element na začátku zdrojového souboru.</span><span class="sxs-lookup"><span data-stu-id="b1e20-135">An attribute modifier (`Assembly` or `Module`) is required on every attribute applied to a programming element at the beginning of a source file.</span></span> <span data-ttu-id="b1e20-136">Modifikátory atribut nejsou povoleny u atributů použitých na elementy, které nejsou na začátku zdrojového souboru.</span><span class="sxs-lookup"><span data-stu-id="b1e20-136">Attribute modifiers are not allowed on attributes applied to elements that are not at the beginning of a source file.</span></span>  
  
-   <span data-ttu-id="b1e20-137">**Argumenty.**</span><span class="sxs-lookup"><span data-stu-id="b1e20-137">**Arguments.**</span></span> <span data-ttu-id="b1e20-138">Všechny argumenty poziční atributu musí předcházet inicializátory všechny proměnné nebo vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="b1e20-138">All positional arguments for an attribute must precede any variable or property initializers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1e20-139">Příklad</span><span class="sxs-lookup"><span data-stu-id="b1e20-139">Example</span></span>  
 <span data-ttu-id="b1e20-140">Následující příklad se vztahuje <xref:System.Runtime.InteropServices.DllImportAttribute> atribut kostru definice `Function` postupu.</span><span class="sxs-lookup"><span data-stu-id="b1e20-140">The following example applies the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute to a skeleton definition of a `Function` procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#1](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/attribute-list_1.vb)]  
  
 <span data-ttu-id="b1e20-141"><xref:System.Runtime.InteropServices.DllImportAttribute>Označuje, že s atributy postup představuje vstupní bod v nespravované dynamická knihovna (DLL).</span><span class="sxs-lookup"><span data-stu-id="b1e20-141"><xref:System.Runtime.InteropServices.DllImportAttribute> indicates that the attributed procedure represents an entry point in an unmanaged dynamic-link library (DLL).</span></span> <span data-ttu-id="b1e20-142">Atribut poskytuje název DLL jako poziční argument a dalších informací jako proměnné inicializátory.</span><span class="sxs-lookup"><span data-stu-id="b1e20-142">The attribute supplies the DLL name as a positional argument and the other information as variable initializers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1e20-143">Viz také</span><span class="sxs-lookup"><span data-stu-id="b1e20-143">See Also</span></span>  
 [<span data-ttu-id="b1e20-144">Sestavení</span><span class="sxs-lookup"><span data-stu-id="b1e20-144">Assembly</span></span>](../../../visual-basic/language-reference/modifiers/assembly.md)  
 [<span data-ttu-id="b1e20-145">Modul \<– klíčové slovo ></span><span class="sxs-lookup"><span data-stu-id="b1e20-145">Module \<keyword></span></span>](../../../visual-basic/language-reference/modifiers/module-keyword.md)  
 [<span data-ttu-id="b1e20-146">Přehled atributy</span><span class="sxs-lookup"><span data-stu-id="b1e20-146">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)  
 [<span data-ttu-id="b1e20-147">Postupy: přerušení a kombinace příkazů v kódu</span><span class="sxs-lookup"><span data-stu-id="b1e20-147">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
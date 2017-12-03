---
title: "Option Compare – příkaz"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Compare
- vb.OptionCompare
helpviewer_keywords:
- case sensitivity, Option Compare statement
- Compare keyword [Visual Basic]
- binary comparison [Visual Basic]
- strings [Visual Basic], returning from functions
- binary comparison [Visual Basic], Option Compare statement
- strings [Visual Basic], comparing
- string comparison [Visual Basic], Option Compare statement
- Text keyword [Visual Basic], Option Compare statement
- Binary keyword [Visual Basic], Option Compare statement
- string comparison [Visual Basic], sorting data
- Option Compare statement [Visual Basic]
- text [Visual Basic], comparing
ms.assetid: 54e8eeeb-3b0d-4fb9-acce-fbfbd5975f6e
caps.latest.revision: "37"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 281b18322f5be4e7dadcb9533680b25016a44c96
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="option-compare-statement"></a><span data-ttu-id="bc583-102">Option Compare – příkaz</span><span class="sxs-lookup"><span data-stu-id="bc583-102">Option Compare Statement</span></span>
<span data-ttu-id="bc583-103">Deklaruje výchozí metoda porovnání pro použití při porovnávání dat řetězce.</span><span class="sxs-lookup"><span data-stu-id="bc583-103">Declares the default comparison method to use when comparing string data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc583-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="bc583-104">Syntax</span></span>  
  
```  
Option Compare { Binary | Text }  
```  
  
## <a name="parts"></a><span data-ttu-id="bc583-105">Součásti</span><span class="sxs-lookup"><span data-stu-id="bc583-105">Parts</span></span>  
  
|<span data-ttu-id="bc583-106">Termín</span><span class="sxs-lookup"><span data-stu-id="bc583-106">Term</span></span>|<span data-ttu-id="bc583-107">Definice</span><span class="sxs-lookup"><span data-stu-id="bc583-107">Definition</span></span>|  
|---|---|  
|`Binary`|<span data-ttu-id="bc583-108">Volitelné.</span><span class="sxs-lookup"><span data-stu-id="bc583-108">Optional.</span></span> <span data-ttu-id="bc583-109">Výsledkem porovnání řetězců podle pořadí řazení odvozené z interní binární reprezentace znaky.</span><span class="sxs-lookup"><span data-stu-id="bc583-109">Results in string comparisons based on a sort order derived from the internal binary representations of the characters.</span></span><br /><br /> <span data-ttu-id="bc583-110">Tento typ porovnání je užitečný zejména v případě, že řetězce mohou obsahovat znaky, které nemají interpretovat jako text.</span><span class="sxs-lookup"><span data-stu-id="bc583-110">This type of comparison is useful especially if the strings can contain characters that are not to be interpreted as text.</span></span> <span data-ttu-id="bc583-111">V takovém případě nechcete na posunu porovnání s abecedním rovnocenností, jako je například nerozlišování.</span><span class="sxs-lookup"><span data-stu-id="bc583-111">In this case, you do not want to bias comparisons with alphabetical equivalences, such as case insensitivity.</span></span>|  
|`Text`|<span data-ttu-id="bc583-112">Volitelné.</span><span class="sxs-lookup"><span data-stu-id="bc583-112">Optional.</span></span> <span data-ttu-id="bc583-113">Výsledkem porovnání řetězců podle pořadí řazení velká a malá písmena text určen podle národního prostředí vašeho systému.</span><span class="sxs-lookup"><span data-stu-id="bc583-113">Results in string comparisons based on a case-insensitive text sort order determined by your system's locale.</span></span><br /><br /> <span data-ttu-id="bc583-114">Tento typ porovnání je užitečný, pokud vaše řetězce obsahovat všechny znaky textu a chcete porovnat je s ohledem na účet abecedním rovnocenností například nerozlišování a úzce související písmena.</span><span class="sxs-lookup"><span data-stu-id="bc583-114">This type of comparison is useful if your strings contain all text characters, and you want to compare them taking into account alphabetic equivalences such as case insensitivity and closely related letters.</span></span> <span data-ttu-id="bc583-115">Například můžete chtít zvážit `A` a `a` být stejné, a `Ä` a `ä` na dřívější než `B` a `b`.</span><span class="sxs-lookup"><span data-stu-id="bc583-115">For example, you might want to consider `A` and `a` to be equal, and `Ä` and `ä` to come before `B` and `b`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bc583-116">Poznámky</span><span class="sxs-lookup"><span data-stu-id="bc583-116">Remarks</span></span>  
 <span data-ttu-id="bc583-117">Pokud se používá, `Option Compare` příkazu musí být v souboru před jakékoli jiné příkazy zdrojového kódu.</span><span class="sxs-lookup"><span data-stu-id="bc583-117">If used, the `Option Compare` statement must appear in a file before any other source code statements.</span></span>  
  
 <span data-ttu-id="bc583-118">`Option Compare` Příkaz určuje metodu porovnání řetězce (`Binary` nebo `Text`).</span><span class="sxs-lookup"><span data-stu-id="bc583-118">The `Option Compare` statement specifies the string comparison method (`Binary` or `Text`).</span></span>  <span data-ttu-id="bc583-119">Výchozí metoda porovnání textu je `Binary`.</span><span class="sxs-lookup"><span data-stu-id="bc583-119">The default text comparison method is `Binary`.</span></span>  
  
 <span data-ttu-id="bc583-120">A `Binary` porovnání porovná číselnou hodnotu Unicode každý znak v každé řetězec.</span><span class="sxs-lookup"><span data-stu-id="bc583-120">A `Binary` comparison compares the numeric Unicode value of each character in each string.</span></span> <span data-ttu-id="bc583-121">A `Text` porovnání porovná každý znak Unicode podle její lexikální význam v aktuální jazykovou verzi.</span><span class="sxs-lookup"><span data-stu-id="bc583-121">A `Text` comparison compares each Unicode character based on its lexical meaning in the current culture.</span></span>  
  
 <span data-ttu-id="bc583-122">V systému Windows je určen pořadí řazení podle znakové stránky.</span><span class="sxs-lookup"><span data-stu-id="bc583-122">In Microsoft Windows, sort order is determined by the code page.</span></span> <span data-ttu-id="bc583-123">Další informace najdete v tématu [znakové stránky](/cpp/c-runtime-library/code-pages).</span><span class="sxs-lookup"><span data-stu-id="bc583-123">For more information, see [Code Pages](/cpp/c-runtime-library/code-pages).</span></span>  
  
 <span data-ttu-id="bc583-124">V následujícím příkladu, řazení znaků v angličtině nebo Evropské znaková stránka (ANSI 1252) pomocí `Option Compare Binary`, který vytváří typické binární řazení.</span><span class="sxs-lookup"><span data-stu-id="bc583-124">In the following example, characters in the English/European code page (ANSI 1252) are sorted by using `Option Compare Binary`, which produces a typical binary sort order.</span></span>  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 <span data-ttu-id="bc583-125">Když jsou seřazeny stejné znaky na stejné stránce kódu s použitím `Option Compare Text`, vytváří následující text pořadí řazení.</span><span class="sxs-lookup"><span data-stu-id="bc583-125">When the same characters in the same code page are sorted by using `Option Compare Text`, the following text sort order is produced.</span></span>  
  
 `(A=a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`  
  
## <a name="when-an-option-compare-statement-is-not-present"></a><span data-ttu-id="bc583-126">Při porovnání možnost příkazu není k dispozici</span><span class="sxs-lookup"><span data-stu-id="bc583-126">When an Option Compare Statement Is Not Present</span></span>  
 <span data-ttu-id="bc583-127">Pokud zdrojový kód neobsahuje `Option Compare` příkaz, **možnost porovnat** nastavení na [stránka kompilovat, Návrhář projektu (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) se používá.</span><span class="sxs-lookup"><span data-stu-id="bc583-127">If the source code does not contain an `Option Compare` statement, the **Option Compare** setting on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) is used.</span></span> <span data-ttu-id="bc583-128">Pokud používáte kompilátoru příkazového řádku, nastavení určeného [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) – možnost kompilátoru se používá.</span><span class="sxs-lookup"><span data-stu-id="bc583-128">If you use the command-line compiler, the setting specified by the [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) compiler option is used.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
#### <a name="to-set-option-compare-in-the-ide"></a><span data-ttu-id="bc583-129">Chcete-li nastavit možnost porovnat v prostředí IDE</span><span class="sxs-lookup"><span data-stu-id="bc583-129">To set Option Compare in the IDE</span></span>  
  
1.  <span data-ttu-id="bc583-130">V **Průzkumníku**, vyberte projektu.</span><span class="sxs-lookup"><span data-stu-id="bc583-130">In **Solution Explorer**, select a project.</span></span> <span data-ttu-id="bc583-131">Na **projektu** nabídky, klikněte na tlačítko **vlastnosti**.</span><span class="sxs-lookup"><span data-stu-id="bc583-131">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="bc583-132">Další informace najdete v tématu [NIB: Správa vlastností projektu s Návrhář projektu](http://msdn.microsoft.com/en-us/983f3c18-832f-4666-afec-74b716ff3e0e).</span><span class="sxs-lookup"><span data-stu-id="bc583-132">For more information, see [NIB: Managing Project Properties with the Project Designer](http://msdn.microsoft.com/en-us/983f3c18-832f-4666-afec-74b716ff3e0e).</span></span>  
  
2.  <span data-ttu-id="bc583-133">Klikněte **zkompilovat** kartě.</span><span class="sxs-lookup"><span data-stu-id="bc583-133">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="bc583-134">Nastavte hodnotu v **možnost porovnat** pole.</span><span class="sxs-lookup"><span data-stu-id="bc583-134">Set the value in the **Option Compare** box.</span></span>  
  
 <span data-ttu-id="bc583-135">Při vytváření projektu, **možnost porovnat** nastavení na **zkompilovat** karta je nastaven na **možnost porovnat** nastavení v **možnosti** Dialogové okno.</span><span class="sxs-lookup"><span data-stu-id="bc583-135">When you create a project, the **Option Compare** setting on the **Compile** tab is set to the **Option Compare** setting in the **Options** dialog box.</span></span> <span data-ttu-id="bc583-136">Chcete-li změnit toto nastavení na **nástroje** nabídky, klikněte na tlačítko **možnosti**.</span><span class="sxs-lookup"><span data-stu-id="bc583-136">To change this setting, on the **Tools** menu, click **Options**.</span></span> <span data-ttu-id="bc583-137">V **možnosti** dialogové okno, rozbalte seznam **projekty a řešení**a potom klikněte na **VB výchozí**.</span><span class="sxs-lookup"><span data-stu-id="bc583-137">In the **Options** dialog box, expand **Projects and Solutions**, and then click **VB Defaults**.</span></span> <span data-ttu-id="bc583-138">Počáteční výchozí nastavení v **VB výchozí** je **binární**.</span><span class="sxs-lookup"><span data-stu-id="bc583-138">The initial default setting in **VB Defaults** is **Binary**.</span></span>  
  
#### <a name="to-set-option-compare-on-the-command-line"></a><span data-ttu-id="bc583-139">Chcete-li nastavit možnost porovnat na příkazovém řádku</span><span class="sxs-lookup"><span data-stu-id="bc583-139">To set Option Compare on the command line</span></span>  
  
-   <span data-ttu-id="bc583-140">Zahrnout [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) – možnost kompilátoru v **Vbc –** příkaz.</span><span class="sxs-lookup"><span data-stu-id="bc583-140">Include the [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) compiler option in the **vbc** command.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc583-141">Příklad</span><span class="sxs-lookup"><span data-stu-id="bc583-141">Example</span></span>  
 <span data-ttu-id="bc583-142">Následující příklad používá `Option Compare` příkaz binární porovnání nastavit jako výchozí metoda porovnání řetězce.</span><span class="sxs-lookup"><span data-stu-id="bc583-142">The following example uses the `Option Compare` statement to set the binary comparison as the default string comparison method.</span></span> <span data-ttu-id="bc583-143">Chcete-li použít tento kód, zrušte komentář u `Option Compare Binary` příkaz a umístí jej v horní části zdrojového souboru.</span><span class="sxs-lookup"><span data-stu-id="bc583-143">To use this code, uncomment the `Option Compare Binary` statement, and put it at the top of the source file.</span></span>  
  
 [!code-vb[VbVbalrStatements#45](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-compare-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="bc583-144">Příklad</span><span class="sxs-lookup"><span data-stu-id="bc583-144">Example</span></span>  
 <span data-ttu-id="bc583-145">Následující příklad používá `Option Compare` příkaz nastavit pořadí řazení velká a malá písmena text jako výchozí metoda porovnání řetězce.</span><span class="sxs-lookup"><span data-stu-id="bc583-145">The following example uses the `Option Compare` statement to set the case-insensitive text sort order as the default string comparison method.</span></span> <span data-ttu-id="bc583-146">Chcete-li použít tento kód, zrušte komentář u `Option Compare Text` příkaz a umístí jej v horní části zdrojového souboru.</span><span class="sxs-lookup"><span data-stu-id="bc583-146">To use this code, uncomment the `Option Compare Text` statement, and put it at the top of the source file.</span></span>  
  
 [!code-vb[VbVbalrStatements#46](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-compare-statement_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="bc583-147">Viz také</span><span class="sxs-lookup"><span data-stu-id="bc583-147">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Strings.InStr%2A>  
 <xref:Microsoft.VisualBasic.Strings.InStrRev%2A>  
 <xref:Microsoft.VisualBasic.Strings.Replace%2A>  
 <xref:Microsoft.VisualBasic.Strings.Split%2A>  
 <xref:Microsoft.VisualBasic.Strings.StrComp%2A>  
 [<span data-ttu-id="bc583-148">/ optioncompare</span><span class="sxs-lookup"><span data-stu-id="bc583-148">/optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)  
 [<span data-ttu-id="bc583-149">Operátory porovnávání</span><span class="sxs-lookup"><span data-stu-id="bc583-149">Comparison Operators</span></span>](../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [<span data-ttu-id="bc583-150">Operátory porovnání v jazyce Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bc583-150">Comparison Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [<span data-ttu-id="bc583-151">Like – operátor</span><span class="sxs-lookup"><span data-stu-id="bc583-151">Like Operator</span></span>](../../../visual-basic/language-reference/operators/like-operator.md)  
 [<span data-ttu-id="bc583-152">Řetězcové funkce</span><span class="sxs-lookup"><span data-stu-id="bc583-152">String Functions</span></span>](../../../visual-basic/language-reference/functions/string-functions.md)  
 [<span data-ttu-id="bc583-153">Option Explicit – příkaz</span><span class="sxs-lookup"><span data-stu-id="bc583-153">Option Explicit Statement</span></span>](../../../visual-basic/language-reference/statements/option-explicit-statement.md)  
 [<span data-ttu-id="bc583-154">Option Strict – příkaz</span><span class="sxs-lookup"><span data-stu-id="bc583-154">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
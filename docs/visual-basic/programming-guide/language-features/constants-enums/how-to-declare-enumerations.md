---
title: "Postupy: Deklarace výčtů (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declarations [Visual Basic], enumerations
- enumerations [Visual Basic], declaring
- declaring enumerations [Visual Basic]
ms.assetid: db4ca1c3-f429-4c81-ae81-29e0157b29fd
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 938550ebbfcf099729db3de96b809549cb234d81
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-declare-enumerations-visual-basic"></a><span data-ttu-id="8c211-102">Postupy: Deklarace výčtů (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8c211-102">How to: Declare Enumerations (Visual Basic)</span></span>
<span data-ttu-id="8c211-103">Vytvoření výčtu s `Enum` příkazu v části deklarace třídy nebo modulu.</span><span class="sxs-lookup"><span data-stu-id="8c211-103">You create an enumeration with the `Enum` statement in the declarations section of a class or module.</span></span> <span data-ttu-id="8c211-104">Výčet v rámci metodu nelze deklarovat.</span><span class="sxs-lookup"><span data-stu-id="8c211-104">You cannot declare an enumeration within a method.</span></span> <span data-ttu-id="8c211-105">Pokud chcete zadat odpovídající úroveň přístupu, použijte `Private`, `Protected`, `Friend`, nebo `Public`.</span><span class="sxs-lookup"><span data-stu-id="8c211-105">To specify the appropriate level of access, use `Private`, `Protected`, `Friend`, or `Public`.</span></span>  
  
 <span data-ttu-id="8c211-106">`Enum` Typ má název, typ základní a sady polí, každý reprezentující konstantu.</span><span class="sxs-lookup"><span data-stu-id="8c211-106">An `Enum` type has a name, an underlying type, and a set of fields, each representing a constant.</span></span> <span data-ttu-id="8c211-107">Název musí být platný kvalifikátor Visual Basic .NET.</span><span class="sxs-lookup"><span data-stu-id="8c211-107">The name must be a valid Visual Basic .NET qualifier.</span></span> <span data-ttu-id="8c211-108">Základní typ musí být jeden z typů celé číslo –`Byte`, `Short`, `Long` nebo `Integer`.</span><span class="sxs-lookup"><span data-stu-id="8c211-108">The underlying type must be one of the integer types—`Byte`, `Short`, `Long` or `Integer`.</span></span> <span data-ttu-id="8c211-109">`Integer`je výchozí.</span><span class="sxs-lookup"><span data-stu-id="8c211-109">`Integer` is the default.</span></span> <span data-ttu-id="8c211-110">Výčty jsou vždy silného typu a se nedají zaměňovat s typy číslo celé číslo.</span><span class="sxs-lookup"><span data-stu-id="8c211-110">Enumerations are always strongly typed and are not interchangeable with integer number types.</span></span>  
  
 <span data-ttu-id="8c211-111">Výčty nesmí mít hodnoty s plovoucí desetinnou čárkou.</span><span class="sxs-lookup"><span data-stu-id="8c211-111">Enumerations cannot have floating-point values.</span></span> <span data-ttu-id="8c211-112">Pokud je výčet přiřazenou hodnotu s plovoucí desetinnou čárkou s `Option Strict On`, výsledků chyby kompilátoru.</span><span class="sxs-lookup"><span data-stu-id="8c211-112">If an enumeration is assigned a floating-point value with `Option Strict On`, a compiler error results.</span></span> <span data-ttu-id="8c211-113">Pokud `Option Strict` je `Off`, hodnota je automaticky převeden na `Enum` typu.</span><span class="sxs-lookup"><span data-stu-id="8c211-113">If `Option Strict` is `Off`, the value is automatically converted to the `Enum` type.</span></span>  
  
 <span data-ttu-id="8c211-114">Informace o názvech a jak používat `Imports` najdete v části prohlášení není zapotřebí, aby kvalifikace názvu [výčty a kvalifikace názvu](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span><span class="sxs-lookup"><span data-stu-id="8c211-114">For information on names, and how to use the `Imports` statement to make name qualification unnecessary, see [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span></span>  
  
### <a name="to-declare-an-enumeration"></a><span data-ttu-id="8c211-115">Chcete-li deklarace výčtů</span><span class="sxs-lookup"><span data-stu-id="8c211-115">To declare an enumeration</span></span>  
  
1.  <span data-ttu-id="8c211-116">Zápis deklaraci, která zahrnuje úroveň přístupu kódu, `Enum` – klíčové slovo a platný název, jako v následujících příkladech, z nichž každý deklaruje jiné `Enum`.</span><span class="sxs-lookup"><span data-stu-id="8c211-116">Write a declaration that includes a code access level, the `Enum` keyword, and a valid name, as in the following examples, each of which declares a different `Enum`.</span></span>  
  
     [!code-vb[VbEnumsTask#3](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_1.vb)]  
  
2.  <span data-ttu-id="8c211-117">Definujte konstanty ve výčtu.</span><span class="sxs-lookup"><span data-stu-id="8c211-117">Define the constants in the enumeration.</span></span> <span data-ttu-id="8c211-118">Ve výchozím nastavení, je inicializováno první konstanta ve výčtu `0`, a následné konstanty jsou inicializována tak, aby na hodnotu jedna víc než předchozí konstanta.</span><span class="sxs-lookup"><span data-stu-id="8c211-118">By default, the first constant in an enumeration is initialized to `0`, and subsequent constants are initialized to a value of one more than the previous constant.</span></span> <span data-ttu-id="8c211-119">Například následující výčet `Days`, obsahuje konstanta s názvem `Sunday` s hodnotou `0`, konstanta s názvem `Monday` s hodnotou `1`, konstanta s názvem `Tuesday` s hodnotou `2`a tak dále.</span><span class="sxs-lookup"><span data-stu-id="8c211-119">For example, the following enumeration, `Days`, contains a constant named `Sunday` with the value `0`, a constant named `Monday` with the value `1`, a constant named `Tuesday` with the value of `2`, and so on.</span></span>  
  
     [!code-vb[VbEnumsTask#4](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_2.vb)]  
  
3.  <span data-ttu-id="8c211-120">Můžete explicitně přiřadit hodnoty konstant ve výčtu pomocí příkazu přiřazení.</span><span class="sxs-lookup"><span data-stu-id="8c211-120">You can explicitly assign values to constants in an enumeration by using an assignment statement.</span></span> <span data-ttu-id="8c211-121">Můžete přiřadit jakékoli celé číslo, včetně záporná čísla.</span><span class="sxs-lookup"><span data-stu-id="8c211-121">You can assign any integer value, including negative numbers.</span></span> <span data-ttu-id="8c211-122">Například můžete konstanty hodnoty menší než nula představují chybové stavy.</span><span class="sxs-lookup"><span data-stu-id="8c211-122">For example, you may want constants with values less than zero to represent error conditions.</span></span> <span data-ttu-id="8c211-123">V následující výčet konstanta `Invalid` je explicitně přiřazena hodnota `–1`a konstantu `Sunday` je přiřazena hodnota `0`.</span><span class="sxs-lookup"><span data-stu-id="8c211-123">In the following enumeration, the constant `Invalid` is explicitly assigned the value `–1`, and the constant `Sunday` is assigned the value `0`.</span></span> <span data-ttu-id="8c211-124">Protože se jedná o první konstanta ve výčtu, `Saturday` je také inicializován na hodnotu `0`.</span><span class="sxs-lookup"><span data-stu-id="8c211-124">Because it is the first constant in the enumeration, `Saturday` is also initialized to the value `0`.</span></span> <span data-ttu-id="8c211-125">Hodnota `Monday` je `1` (jednu vyšší než hodnota `Sunday`); hodnota `Tuesday` je `2`a tak dále.</span><span class="sxs-lookup"><span data-stu-id="8c211-125">The value of `Monday` is `1` (one more than the value of `Sunday`); the value of `Tuesday` is `2`, and so on.</span></span>  
  
     [!code-vb[VbEnumsTask#5](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_3.vb)]  
  
### <a name="to-declare-an-enumeration-as-an-explicit-type"></a><span data-ttu-id="8c211-126">Chcete-li deklarovat výčet jako explicitního typu</span><span class="sxs-lookup"><span data-stu-id="8c211-126">To declare an enumeration as an explicit type</span></span>  
  
-   <span data-ttu-id="8c211-127">Zadejte typ výčtového typu pomocí `As` klauzule, jak je znázorněno v následujícím příkladu.</span><span class="sxs-lookup"><span data-stu-id="8c211-127">Specify the type of the enum by using the `As` clause, as shown in the following example.</span></span>  
  
     [!code-vb[VbEnumsTask#6](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="8c211-128">Viz také</span><span class="sxs-lookup"><span data-stu-id="8c211-128">See Also</span></span>  
 [<span data-ttu-id="8c211-129">Výčty a kvalifikace názvu</span><span class="sxs-lookup"><span data-stu-id="8c211-129">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [<span data-ttu-id="8c211-130">Postupy: odkazování na člena výčtu</span><span class="sxs-lookup"><span data-stu-id="8c211-130">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [<span data-ttu-id="8c211-131">Postupy: iterace výčet v jazyce Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8c211-131">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)  
 [<span data-ttu-id="8c211-132">Postupy: určení řetězce spojeného s hodnotou výčtu</span><span class="sxs-lookup"><span data-stu-id="8c211-132">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)  
 [<span data-ttu-id="8c211-133">Kdy použít výčet</span><span class="sxs-lookup"><span data-stu-id="8c211-133">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)  
 [<span data-ttu-id="8c211-134">Přehled konstant</span><span class="sxs-lookup"><span data-stu-id="8c211-134">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)  
 [<span data-ttu-id="8c211-135">Datové typy konstanty a literálu</span><span class="sxs-lookup"><span data-stu-id="8c211-135">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)  
 [<span data-ttu-id="8c211-136">Konstanty a výčty</span><span class="sxs-lookup"><span data-stu-id="8c211-136">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
---
title: "Postupy: Skrytí zděděné proměnné (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- qualification [Visual Basic], of element names
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declaration statements [Visual Basic], declared elements
- referencing declared elements [Visual Basic]
- declared elements [Visual Basic], referencing
- declared elements [Visual Basic], about declared elements
- variables [Visual Basic], hiding inherited
ms.assetid: 765728d9-7351-4a30-999d-b5f34f024412
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d2059da873f8b9ec9ea51191139c652a9e01d92b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-hide-an-inherited-variable-visual-basic"></a><span data-ttu-id="8780d-102">Postupy: Skrytí zděděné proměnné (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8780d-102">How to: Hide an Inherited Variable (Visual Basic)</span></span>
<span data-ttu-id="8780d-103">Odvozené třídy dědí všechny definice své základní třídy.</span><span class="sxs-lookup"><span data-stu-id="8780d-103">A derived class inherits all the definitions of its base class.</span></span> <span data-ttu-id="8780d-104">Pokud chcete k definování proměnné pomocí stejný název jako element základní třídy, můžete skrýt, nebo *stínové*, základní třída prvku při definování vaše proměnná v odvozené třídě.</span><span class="sxs-lookup"><span data-stu-id="8780d-104">If you want to define a variable using the same name as an element of the base class, you can hide, or *shadow*, that base class element when you define your variable in the derived class.</span></span> <span data-ttu-id="8780d-105">Pokud to uděláte, kód v odvozené třídě přistupuje vaše proměnná, pokud ji explicitně obchází stínového provozu mechanismus.</span><span class="sxs-lookup"><span data-stu-id="8780d-105">If you do this, code in the derived class accesses your variable unless it explicitly bypasses the shadowing mechanism.</span></span>  
  
 <span data-ttu-id="8780d-106">Dalším důvodem, že chcete skrytí zděděné proměnné je k ochraně proti základní třída revize.</span><span class="sxs-lookup"><span data-stu-id="8780d-106">Another reason you might want to hide an inherited variable is to protect against base class revision.</span></span> <span data-ttu-id="8780d-107">Základní třída může ke změně, která mění na element, který se dědí.</span><span class="sxs-lookup"><span data-stu-id="8780d-107">The base class might undergo a change that alters the element you are inheriting.</span></span> <span data-ttu-id="8780d-108">V takovém případě `Shadows` modifikátor vynutí odkazy z odvozené třídy vyřešen do proměnné, místo do elementu základní třídy.</span><span class="sxs-lookup"><span data-stu-id="8780d-108">If this happens, the `Shadows` modifier forces references from the derived class to be resolved to your variable, instead of to the base class element.</span></span>  
  
### <a name="to-hide-an-inherited-variable"></a><span data-ttu-id="8780d-109">Skrytí zděděné proměnné</span><span class="sxs-lookup"><span data-stu-id="8780d-109">To hide an inherited variable</span></span>  
  
1.  <span data-ttu-id="8780d-110">Ujistěte se, že je deklarovaná, které chcete skrýt proměnné na úrovni třídy (mimo jakéhokoli postupu).</span><span class="sxs-lookup"><span data-stu-id="8780d-110">Be sure the variable you want to hide is declared at class level (outside any procedure).</span></span> <span data-ttu-id="8780d-111">Jinak není potřeba ho skrýt.</span><span class="sxs-lookup"><span data-stu-id="8780d-111">Otherwise you do not need to hide it.</span></span>  
  
2.  <span data-ttu-id="8780d-112">V odvozené třídě, zápisu [Dim – příkaz](../../../../visual-basic/language-reference/statements/dim-statement.md) deklarace vaše proměnná.</span><span class="sxs-lookup"><span data-stu-id="8780d-112">Inside your derived class, write a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) declaring your variable.</span></span> <span data-ttu-id="8780d-113">Použijte stejný název jako u zděděné proměnné.</span><span class="sxs-lookup"><span data-stu-id="8780d-113">Use the same name as that of the inherited variable.</span></span>  
  
3.  <span data-ttu-id="8780d-114">Zahrnout [stínů](../../../../visual-basic/language-reference/modifiers/shadows.md) – klíčové slovo v deklaraci.</span><span class="sxs-lookup"><span data-stu-id="8780d-114">Include the [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) keyword in the declaration.</span></span>  
  
     <span data-ttu-id="8780d-115">Když kód v odvozené třídě odkazuje na název proměnné, kompilátor vyřeší odkaz na vaše proměnná.</span><span class="sxs-lookup"><span data-stu-id="8780d-115">When code in the derived class refers to the variable name, the compiler resolves the reference to your variable.</span></span>  
  
     <span data-ttu-id="8780d-116">Následující příklad ilustruje, stínový provoz zděděné proměnné.</span><span class="sxs-lookup"><span data-stu-id="8780d-116">The following example illustrates shadowing of an inherited variable.</span></span>  
  
    ```  
    Public Class shadowBaseClass  
        Public shadowString As String = "This is the base class string."  
    End Class  
    Public Class shadowDerivedClass  
        Inherits shadowBaseClass  
        Public Shadows shadowString As String = "This is the derived class string."  
        Public Sub showStrings()  
            Dim s As String = "Unqualified shadowString: " & shadowString &  
                vbCrLf & "MyBase.shadowString: " & MyBase.shadowString  
            MsgBox(s)  
        End Sub  
    End Class  
    ```  
  
     <span data-ttu-id="8780d-117">V předchozím příkladu deklaruje proměnnou `shadowString` v základní třídě a stín v odvozené třídě.</span><span class="sxs-lookup"><span data-stu-id="8780d-117">The preceding example declares the variable `shadowString` in the base class and shadows it in the derived class.</span></span> <span data-ttu-id="8780d-118">Postup `showStrings` v odvozené třídě zobrazí stínového provozu verzi řetězec při název `shadowString` není kvalifikován.</span><span class="sxs-lookup"><span data-stu-id="8780d-118">The procedure `showStrings` in the derived class displays the shadowing version of the string when the name `shadowString` is not qualified.</span></span> <span data-ttu-id="8780d-119">Potom zobrazí stíněné verze při `shadowString` je kvalifikovaný s `MyBase` – klíčové slovo.</span><span class="sxs-lookup"><span data-stu-id="8780d-119">It then displays the shadowed version when `shadowString` is qualified with the `MyBase` keyword.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="8780d-120">Robustní programování</span><span class="sxs-lookup"><span data-stu-id="8780d-120">Robust Programming</span></span>  
 <span data-ttu-id="8780d-121">Stínový provoz zavádí více než jedna verze proměnné se stejným názvem.</span><span class="sxs-lookup"><span data-stu-id="8780d-121">Shadowing introduces more than one version of a variable with the same name.</span></span> <span data-ttu-id="8780d-122">Pokud příkaz kódu odkazuje na název proměnné, verze, do které kompilátor vyřeší odkaz závisí na faktorech, jako je například umístění příkaz kódu a přítomnost opravňující řetězec.</span><span class="sxs-lookup"><span data-stu-id="8780d-122">When a code statement refers to the variable name, the version to which the compiler resolves the reference depends on factors such as the location of the code statement and the presence of a qualifying string.</span></span> <span data-ttu-id="8780d-123">To může zvýšit riziko napadení odkazující na nezamýšleným verzi stíněné proměnné.</span><span class="sxs-lookup"><span data-stu-id="8780d-123">This can increase the risk of referring to an unintended version of a shadowed variable.</span></span> <span data-ttu-id="8780d-124">Plně kvalifikovaný všechny odkazy na proměnnou stíněné můžete snížit rizika.</span><span class="sxs-lookup"><span data-stu-id="8780d-124">You can lower that risk by fully qualifying all references to a shadowed variable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8780d-125">Viz také</span><span class="sxs-lookup"><span data-stu-id="8780d-125">See Also</span></span>  
 [<span data-ttu-id="8780d-126">Odkazy na deklarované elementy</span><span class="sxs-lookup"><span data-stu-id="8780d-126">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [<span data-ttu-id="8780d-127">Stínový provoz v jazyce Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8780d-127">Shadowing in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)  
 [<span data-ttu-id="8780d-128">Rozdíly mezi stínováním a přepsáním</span><span class="sxs-lookup"><span data-stu-id="8780d-128">Differences Between Shadowing and Overriding</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)  
 [<span data-ttu-id="8780d-129">Postupy: skrytí proměnné se stejným názvem jako má vaše proměnná</span><span class="sxs-lookup"><span data-stu-id="8780d-129">How to: Hide a Variable with the Same Name as Your Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)  
 [<span data-ttu-id="8780d-130">Postupy: přístup k proměnné skryté odvozenou třídou</span><span class="sxs-lookup"><span data-stu-id="8780d-130">How to: Access a Variable Hidden by a Derived Class</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)  
 [<span data-ttu-id="8780d-131">Přepsání</span><span class="sxs-lookup"><span data-stu-id="8780d-131">Overrides</span></span>](../../../../visual-basic/language-reference/modifiers/overrides.md)  
 [<span data-ttu-id="8780d-132">ME, My, MyBase a MyClass</span><span class="sxs-lookup"><span data-stu-id="8780d-132">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 [<span data-ttu-id="8780d-133">Základní informace o dědičnosti</span><span class="sxs-lookup"><span data-stu-id="8780d-133">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
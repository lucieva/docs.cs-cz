---
title: Propagace typu (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declared elements [Visual Basic], scope
- visibility [Visual Basic], declared elements
- Partial keyword [Visual Basic], unexpected results with type promotion
- scope [Visual Basic], declared elements
- scope [Visual Basic], Visual Basic
- type promotion
- declared elements [Visual Basic], visibility
ms.assetid: 035eeb15-e4c5-4288-ab3c-6bd5d22f7051
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f3a55c023afe7afe96f862f0b3cbbdb03a15b902
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="type-promotion-visual-basic"></a><span data-ttu-id="6b20a-102">Propagace typu (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6b20a-102">Type Promotion (Visual Basic)</span></span>
<span data-ttu-id="6b20a-103">Když je deklarovat programovací element v modulu, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] zvýší úroveň jeho oboru do oboru názvů, který obsahuje modul.</span><span class="sxs-lookup"><span data-stu-id="6b20a-103">When you declare a programming element in a module, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] promotes its scope to the namespace containing the module.</span></span> <span data-ttu-id="6b20a-104">To se označuje jako *zadejte povýšení*.</span><span class="sxs-lookup"><span data-stu-id="6b20a-104">This is known as *type promotion*.</span></span>  
  
 <span data-ttu-id="6b20a-105">Následující příklad ukazuje definici kostru modulu a dva členové tohoto modulu.</span><span class="sxs-lookup"><span data-stu-id="6b20a-105">The following example shows a skeleton definition of a module and two members of that module.</span></span>  
  
 [!code-vb[VbVbalrDeclaredElements#1](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_1.vb)]  
  
 <span data-ttu-id="6b20a-106">V rámci `projModule`, programovací elementy deklarovat na úrovni modulu povýšené na `projNamespace`.</span><span class="sxs-lookup"><span data-stu-id="6b20a-106">Within `projModule`, programming elements declared at module level are promoted to `projNamespace`.</span></span> <span data-ttu-id="6b20a-107">V předchozím příkladu `basicEnum` a `innerClass` povýšené, ale `numberSub` není, protože nemá na úrovni modulu.</span><span class="sxs-lookup"><span data-stu-id="6b20a-107">In the preceding example, `basicEnum` and `innerClass` are promoted, but `numberSub` is not, because it is not declared at module level.</span></span>  
  
## <a name="effect-of-type-promotion"></a><span data-ttu-id="6b20a-108">Účinek propagace typu</span><span class="sxs-lookup"><span data-stu-id="6b20a-108">Effect of Type Promotion</span></span>  
 <span data-ttu-id="6b20a-109">Účinek povýšení typ je řetězec kvalifikace nemusí obsahovat název modulu.</span><span class="sxs-lookup"><span data-stu-id="6b20a-109">The effect of type promotion is that a qualification string does not need to include the module name.</span></span> <span data-ttu-id="6b20a-110">Následující příklad volá dvě podle postupu v předchozím příkladu.</span><span class="sxs-lookup"><span data-stu-id="6b20a-110">The following example makes two calls to the procedure in the preceding example.</span></span>  
  
 [!code-vb[VbVbalrDeclaredElements#2](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_2.vb)]  
  
 <span data-ttu-id="6b20a-111">V předchozím příkladu použije první volání dokončení kvalifikace řetězce.</span><span class="sxs-lookup"><span data-stu-id="6b20a-111">In the preceding example, the first call uses complete qualification strings.</span></span> <span data-ttu-id="6b20a-112">Je to ale není nutné z důvodu propagace typu.</span><span class="sxs-lookup"><span data-stu-id="6b20a-112">However, this is not necessary because of type promotion.</span></span> <span data-ttu-id="6b20a-113">Druhý volání také přístupů modulu členy bez zahrnutí `projModule` v řetězcích kvalifikaci.</span><span class="sxs-lookup"><span data-stu-id="6b20a-113">The second call also accesses the module's members without including `projModule` in the qualification strings.</span></span>  
  
## <a name="defeat-of-type-promotion"></a><span data-ttu-id="6b20a-114">Odpojovací propagace typu</span><span class="sxs-lookup"><span data-stu-id="6b20a-114">Defeat of Type Promotion</span></span>  
 <span data-ttu-id="6b20a-115">Pokud obor názvů již obsahuje člena se stejným názvem jako člena modulu, typu povýšení se nepotlačí pro tento člen modulu.</span><span class="sxs-lookup"><span data-stu-id="6b20a-115">If the namespace already has a member with the same name as a module member, type promotion is defeated for that module member.</span></span> <span data-ttu-id="6b20a-116">Následující příklad ukazuje definici kostru výčet a modul v rámci stejného oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="6b20a-116">The following example shows a skeleton definition of an enumeration and a module within the same namespace.</span></span>  
  
 [!code-vb[VbVbalrDeclaredElements#3](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_3.vb)]  
  
 <span data-ttu-id="6b20a-117">V předchozím příkladu [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] nelze zvýšit úroveň třída `abc` k `thisNameSpace` protože výčet na úrovni oboru názvů se stejným názvem již existuje.</span><span class="sxs-lookup"><span data-stu-id="6b20a-117">In the preceding example, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] cannot promote class `abc` to `thisNameSpace` because there is already an enumeration with the same name at namespace level.</span></span> <span data-ttu-id="6b20a-118">Pro přístup k `abcSub`, musíte použít úplnou kvalifikace řetězec `thisNamespace.thisModule.abc.abcSub`.</span><span class="sxs-lookup"><span data-stu-id="6b20a-118">To access `abcSub`, you must use the full qualification string `thisNamespace.thisModule.abc.abcSub`.</span></span> <span data-ttu-id="6b20a-119">Ale třídy `xyz` je stále povýšit, a dostanete `xyzSub` s kratší řetězec kvalifikace `thisNamespace.xyz.xyzSub`.</span><span class="sxs-lookup"><span data-stu-id="6b20a-119">However, class `xyz` is still promoted, and you can access `xyzSub` with the shorter qualification string `thisNamespace.xyz.xyzSub`.</span></span>  
  
### <a name="defeat-of-type-promotion-for-partial-types"></a><span data-ttu-id="6b20a-120">Odpojovací propagace typu pro částečné typy</span><span class="sxs-lookup"><span data-stu-id="6b20a-120">Defeat of Type Promotion for Partial Types</span></span>  
 <span data-ttu-id="6b20a-121">Pokud třídu nebo strukturu uvnitř modul používá [částečné](../../../../visual-basic/language-reference/modifiers/partial.md) – klíčové slovo, propagace typu je automaticky nepotlačí pro tuto třídu nebo strukturu, zda obor názvů obsahuje člena se stejným názvem.</span><span class="sxs-lookup"><span data-stu-id="6b20a-121">If a class or structure inside a module uses the [Partial](../../../../visual-basic/language-reference/modifiers/partial.md) keyword, type promotion is automatically defeated for that class or structure, whether or not the namespace has a member with the same name.</span></span> <span data-ttu-id="6b20a-122">Další prvky v modulu jsou stále vhodné pro typ akce.</span><span class="sxs-lookup"><span data-stu-id="6b20a-122">Other elements in the module are still eligible for type promotion.</span></span>  
  
 <span data-ttu-id="6b20a-123">**Důsledky.**</span><span class="sxs-lookup"><span data-stu-id="6b20a-123">**Consequences.**</span></span> <span data-ttu-id="6b20a-124">Odpojovací propagace typu částečné definice může způsobit neočekávané výsledky a i chyby kompilátoru.</span><span class="sxs-lookup"><span data-stu-id="6b20a-124">Defeat of type promotion of a partial definition can cause unexpected results and even compiler errors.</span></span> <span data-ttu-id="6b20a-125">Následující příklad ukazuje kostru částečné definice třídy, z nichž jeden je uvnitř modul.</span><span class="sxs-lookup"><span data-stu-id="6b20a-125">The following example shows skeleton partial definitions of a class, one of which is inside a module.</span></span>  
  
 [!code-vb[VbVbalrDeclaredElements#4](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_4.vb)]  
  
 <span data-ttu-id="6b20a-126">V předchozím příkladu může vývojář očekávat kompilátoru sloučit dva částečné definice `sampleClass`.</span><span class="sxs-lookup"><span data-stu-id="6b20a-126">In the preceding example, the developer might expect the compiler to merge the two partial definitions of `sampleClass`.</span></span> <span data-ttu-id="6b20a-127">Ale kompilátor nebere v úvahu povýšení pro definici částečné uvnitř `sampleModule`.</span><span class="sxs-lookup"><span data-stu-id="6b20a-127">However, the compiler does not consider promotion for the partial definition inside `sampleModule`.</span></span> <span data-ttu-id="6b20a-128">V důsledku toho pokusí zkompilovat dvě samostatné a jiné třídy, i s názvem `sampleClass` , ale s jinou kvalifikace cesty.</span><span class="sxs-lookup"><span data-stu-id="6b20a-128">As a result, it attempts to compile two separate and distinct classes, both named `sampleClass` but with different qualification paths.</span></span>  
  
 <span data-ttu-id="6b20a-129">Kompilátor sloučí částečné definice jenom v případě, že jsou identické jejich plně kvalifikované cesty.</span><span class="sxs-lookup"><span data-stu-id="6b20a-129">The compiler merges partial definitions only when their fully qualified paths are identical.</span></span>  
  
## <a name="recommendations"></a><span data-ttu-id="6b20a-130">Doporučení</span><span class="sxs-lookup"><span data-stu-id="6b20a-130">Recommendations</span></span>  
 <span data-ttu-id="6b20a-131">Následující doporučení představují vhodné programování.</span><span class="sxs-lookup"><span data-stu-id="6b20a-131">The following recommendations represent good programming practice.</span></span>  
  
-   <span data-ttu-id="6b20a-132">**Jedinečné názvy.**</span><span class="sxs-lookup"><span data-stu-id="6b20a-132">**Unique Names.**</span></span> <span data-ttu-id="6b20a-133">Když máte plnou kontrolu nad názvů programovací elementy, vždycky je vhodné použít všude, kde jedinečné názvy.</span><span class="sxs-lookup"><span data-stu-id="6b20a-133">When you have full control over the naming of programming elements, it is always a good idea to use unique names everywhere.</span></span> <span data-ttu-id="6b20a-134">Identické názvy vyžadovat další kvalifikace a mohl provádět kódu těžší ke čtení.</span><span class="sxs-lookup"><span data-stu-id="6b20a-134">Identical names require extra qualification and can make your code harder to read.</span></span> <span data-ttu-id="6b20a-135">Také mohou vést k jemně chyb a neočekávané výsledky.</span><span class="sxs-lookup"><span data-stu-id="6b20a-135">They can also lead to subtle errors and unexpected results.</span></span>  
  
-   <span data-ttu-id="6b20a-136">**Úplné kvalifikaci.**</span><span class="sxs-lookup"><span data-stu-id="6b20a-136">**Full Qualification.**</span></span> <span data-ttu-id="6b20a-137">Při práci s moduly a další prvky v o stejný obor názvů, nejbezpečnější způsob je vždy nutné použít úplnou kvalifikaci pro všechny programovací elementy.</span><span class="sxs-lookup"><span data-stu-id="6b20a-137">When you are working with modules and other elements in the same namespace, the safest approach is to always use full qualification for all programming elements.</span></span> <span data-ttu-id="6b20a-138">Pokud je propagace typu nepotlačí pro člena modulu a které nemohou být plně tohoto člena, může nechtěně přístup různé programovací element.</span><span class="sxs-lookup"><span data-stu-id="6b20a-138">If type promotion is defeated for a module member and you do not fully qualify that member, you could inadvertently access a different programming element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b20a-139">Viz také</span><span class="sxs-lookup"><span data-stu-id="6b20a-139">See Also</span></span>  
 [<span data-ttu-id="6b20a-140">Module – příkaz</span><span class="sxs-lookup"><span data-stu-id="6b20a-140">Module Statement</span></span>](../../../../visual-basic/language-reference/statements/module-statement.md)  
 [<span data-ttu-id="6b20a-141">Namespace – příkaz</span><span class="sxs-lookup"><span data-stu-id="6b20a-141">Namespace Statement</span></span>](../../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [<span data-ttu-id="6b20a-142">Částečné</span><span class="sxs-lookup"><span data-stu-id="6b20a-142">Partial</span></span>](../../../../visual-basic/language-reference/modifiers/partial.md)  
 [<span data-ttu-id="6b20a-143">Rozsah v jazyce Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6b20a-143">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)  
 [<span data-ttu-id="6b20a-144">Postupy: řízení rozsahu proměnné</span><span class="sxs-lookup"><span data-stu-id="6b20a-144">How to: Control the Scope of a Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md)  
 [<span data-ttu-id="6b20a-145">Odkazy na deklarované elementy</span><span class="sxs-lookup"><span data-stu-id="6b20a-145">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
---
title: Nothing (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- Nothing
- vb.Nothing
helpviewer_keywords:
- Nothing keyword [Visual Basic]
- Nothing keyword [Visual Basic], syntax
ms.assetid: 06176e2d-bbf7-4a37-afaa-a86ad21ee99f
caps.latest.revision: "31"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6932fee01ec6f39f67fb1a26a9a5b5cbd47d9767
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="nothing-visual-basic"></a><span data-ttu-id="6e8fa-102">Nothing (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6e8fa-102">Nothing (Visual Basic)</span></span>
<span data-ttu-id="6e8fa-103">Představuje výchozí hodnotu jakéhokoli datového typu.</span><span class="sxs-lookup"><span data-stu-id="6e8fa-103">Represents the default value of any data type.</span></span> <span data-ttu-id="6e8fa-104">U typů odkazu, je výchozí hodnota `null` odkaz.</span><span class="sxs-lookup"><span data-stu-id="6e8fa-104">For reference types, the default value is the `null` reference.</span></span> <span data-ttu-id="6e8fa-105">U typů hodnot výchozí hodnota závisí na tom, zda hodnota typ s možnou hodnotou Null.</span><span class="sxs-lookup"><span data-stu-id="6e8fa-105">For value types, the default value depends on whether the value type is nullable.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6e8fa-106">Pro typy hodnot neumožňující hodnotu Null `Nothing` v jazyce Visual Basic se liší od `null` v jazyce C#.</span><span class="sxs-lookup"><span data-stu-id="6e8fa-106">For non-nullable value types, `Nothing` in Visual Basic differs from `null` in C#.</span></span> <span data-ttu-id="6e8fa-107">V jazyce Visual Basic, pokud nastavíte proměnnou typu hodnot neumožňující hodnotu Null na `Nothing`, proměnná nastavená na výchozí hodnotu pro příslušným deklarovaným typem.</span><span class="sxs-lookup"><span data-stu-id="6e8fa-107">In Visual Basic, if you set a variable of a non-nullable value type to `Nothing`, the variable is set to the default value for its declared type.</span></span> <span data-ttu-id="6e8fa-108">V jazyce C#, chcete-li přiřadit proměnné typu hodnot neumožňující hodnotu Null na `null`, dojde k chybě kompilace.</span><span class="sxs-lookup"><span data-stu-id="6e8fa-108">In C#, if you assign a variable of a non-nullable value type to `null`, a compile-time error occurs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6e8fa-109">Poznámky</span><span class="sxs-lookup"><span data-stu-id="6e8fa-109">Remarks</span></span>  
 <span data-ttu-id="6e8fa-110">`Nothing`představuje výchozí hodnotu datového typu.</span><span class="sxs-lookup"><span data-stu-id="6e8fa-110">`Nothing` represents the default value of a data type.</span></span> <span data-ttu-id="6e8fa-111">Výchozí hodnota závisí na tom, jestli je proměnná hodnota typu nebo typu odkazu.</span><span class="sxs-lookup"><span data-stu-id="6e8fa-111">The default value depends on whether the variable is of a value type or of a reference type.</span></span>  
  
 <span data-ttu-id="6e8fa-112">Proměnná *typ hodnoty* přímo obsahuje jeho hodnotu.</span><span class="sxs-lookup"><span data-stu-id="6e8fa-112">A variable of a *value type* directly contains its value.</span></span> <span data-ttu-id="6e8fa-113">Typy hodnot zahrnout všechny číselné datové typy, `Boolean`, `Char`, `Date`, všechny struktury a všechny výčty.</span><span class="sxs-lookup"><span data-stu-id="6e8fa-113">Value types include all numeric data types, `Boolean`, `Char`, `Date`, all structures, and all enumerations.</span></span> <span data-ttu-id="6e8fa-114">Proměnná *odkazují na typ* ukládá odkaz na instanci objektu v paměti.</span><span class="sxs-lookup"><span data-stu-id="6e8fa-114">A variable of a *reference type* stores a reference to an instance of the object in memory.</span></span> <span data-ttu-id="6e8fa-115">Odkazové typy zahrnují třídy, pole, delegáti a řetězce.</span><span class="sxs-lookup"><span data-stu-id="6e8fa-115">Reference types include classes, arrays, delegates, and strings.</span></span> <span data-ttu-id="6e8fa-116">Další informace najdete v tématu [typy hodnot a typy odkazu](../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="6e8fa-116">For more information, see [Value Types and Reference Types](../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span></span>  
  
 <span data-ttu-id="6e8fa-117">Pokud je proměnná hodnoty typ, chování `Nothing` závisí na tom, jestli je proměnná s možnou hodnotou Null datového typu.</span><span class="sxs-lookup"><span data-stu-id="6e8fa-117">If a variable is of a value type, the behavior of `Nothing` depends on whether the variable is of a nullable data type.</span></span> <span data-ttu-id="6e8fa-118">Chcete-li představují typ s možnou hodnotou Null hodnoty, přidejte `?` modifikátor k názvu typu.</span><span class="sxs-lookup"><span data-stu-id="6e8fa-118">To represent a nullable value type, add a `?` modifier to the type name.</span></span> <span data-ttu-id="6e8fa-119">Přiřazení `Nothing` s možnou hodnotou Null proměnné nastaví hodnotu `null`.</span><span class="sxs-lookup"><span data-stu-id="6e8fa-119">Assigning `Nothing` to a nullable variable sets the value to `null`.</span></span> <span data-ttu-id="6e8fa-120">Další informace a příklady naleznete v tématu [typy s možnou hodnotou Null hodnot](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md).</span><span class="sxs-lookup"><span data-stu-id="6e8fa-120">For more information and examples, see [Nullable Value Types](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md).</span></span>  
  
 <span data-ttu-id="6e8fa-121">Pokud je proměnná typu hodnotu, která není null, přiřazení `Nothing` k nastaví se výchozí hodnota pro příslušným deklarovaným typem.</span><span class="sxs-lookup"><span data-stu-id="6e8fa-121">If a variable is of a value type that is not nullable, assigning `Nothing` to it sets it to the default value for its declared type.</span></span> <span data-ttu-id="6e8fa-122">Pokud se tento typ obsahuje proměnné členů, jsou nastavené na výchozí hodnoty.</span><span class="sxs-lookup"><span data-stu-id="6e8fa-122">If that type contains variable members, they are all set to their default values.</span></span> <span data-ttu-id="6e8fa-123">Následující příklad znázorňuje to pro skalární typy.</span><span class="sxs-lookup"><span data-stu-id="6e8fa-123">The following example illustrates this for scalar types.</span></span>  
  
 [!code-vb[VbVbalrKeywords#7](../../visual-basic/language-reference/codesnippet/VisualBasic/nothing_1.vb)]  
  
 <span data-ttu-id="6e8fa-124">Pokud je proměnná typu odkaz, přiřazení `Nothing` proměnnou ji nastaví na `null` odkazu proměnnou typu.</span><span class="sxs-lookup"><span data-stu-id="6e8fa-124">If a variable is of a reference type, assigning `Nothing` to the variable sets it to a `null` reference of the variable's type.</span></span> <span data-ttu-id="6e8fa-125">Proměnné, který je nastaven `null` odkaz není spojen s libovolného objektu.</span><span class="sxs-lookup"><span data-stu-id="6e8fa-125">A variable that is set to a `null` reference is not associated with any object.</span></span> <span data-ttu-id="6e8fa-126">Následující příklad ukazuje to.</span><span class="sxs-lookup"><span data-stu-id="6e8fa-126">The following example demonstrates this.</span></span>  
  
 [!code-vb[VbVbalrKeywords#8](../../visual-basic/language-reference/codesnippet/VisualBasic/nothing_2.vb)]  
  
 <span data-ttu-id="6e8fa-127">Při kontrole, jestli odkaz (nebo zadejte hodnot hodnotu Null) je proměnná `null`, nepoužívejte `= Nothing` nebo `<> Nothing`.</span><span class="sxs-lookup"><span data-stu-id="6e8fa-127">When checking whether a reference (or nullable value type) variable is `null`, do not use `= Nothing` or `<> Nothing`.</span></span> <span data-ttu-id="6e8fa-128">Vždy používat `Is Nothing` nebo `IsNot Nothing`.</span><span class="sxs-lookup"><span data-stu-id="6e8fa-128">Always use `Is Nothing` or `IsNot Nothing`.</span></span>  
  
 <span data-ttu-id="6e8fa-129">Pro řetězce v jazyce Visual Basic, prázdný řetězec rovná `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="6e8fa-129">For strings in Visual Basic, the empty string equals `Nothing`.</span></span> <span data-ttu-id="6e8fa-130">Proto `"" = Nothing` hodnotu true.</span><span class="sxs-lookup"><span data-stu-id="6e8fa-130">Therefore, `"" = Nothing` is true.</span></span>  
  
 <span data-ttu-id="6e8fa-131">Následující příklad ukazuje porovnání, které používají `Is` a `IsNot` operátory.</span><span class="sxs-lookup"><span data-stu-id="6e8fa-131">The following example shows comparisons that use the `Is` and `IsNot` operators.</span></span>  
  
 [!code-vb[VbVbalrKeywords#9](../../visual-basic/language-reference/codesnippet/VisualBasic/nothing_3.vb)]  
  
 <span data-ttu-id="6e8fa-132">Pokud je deklarovat proměnnou bez použití `As` klauzule a nastavte ji na `Nothing`, proměnná má typ `Object`.</span><span class="sxs-lookup"><span data-stu-id="6e8fa-132">If you declare a variable without using an `As` clause and set it to `Nothing`, the variable has a type of `Object`.</span></span> <span data-ttu-id="6e8fa-133">Příkladem je `Dim something = Nothing`.</span><span class="sxs-lookup"><span data-stu-id="6e8fa-133">An example of this is `Dim something = Nothing`.</span></span> <span data-ttu-id="6e8fa-134">V takovém případě dojde k chybě kompilace při `Option Strict` na a `Option Infer` je vypnutý.</span><span class="sxs-lookup"><span data-stu-id="6e8fa-134">A compile-time error occurs in this case when `Option Strict` is on and `Option Infer` is off.</span></span>  
  
 <span data-ttu-id="6e8fa-135">Přiřadíte-li `Nothing` proměnné objektu už odkazuje na jakoukoli instanci objektu.</span><span class="sxs-lookup"><span data-stu-id="6e8fa-135">When you assign `Nothing` to an object variable, it no longer refers to any object instance.</span></span> <span data-ttu-id="6e8fa-136">Pokud proměnná měl dříve uvedených instance, jeho nastavení na hodnotu `Nothing` nezavře instance sám sebe.</span><span class="sxs-lookup"><span data-stu-id="6e8fa-136">If the variable had previously referred to an instance, setting it to `Nothing` does not terminate the instance itself.</span></span> <span data-ttu-id="6e8fa-137">Ukončení instance a uvolnění paměti a systém prostředků s ním spojená, až poté, co má systém uvolňování (GC) zjistí, že neexistují žádné aktivní odkazy zbývající.</span><span class="sxs-lookup"><span data-stu-id="6e8fa-137">The instance is terminated, and the memory and system resources associated with it are released, only after the garbage collector (GC) detects that there are no active references remaining.</span></span>  
  
 <span data-ttu-id="6e8fa-138">`Nothing`se liší od <xref:System.DBNull> objekt, který představuje Neinicializovaný variant nebo sloupci neexistující databáze.</span><span class="sxs-lookup"><span data-stu-id="6e8fa-138">`Nothing` differs from the <xref:System.DBNull> object, which represents an uninitialized variant or a nonexistent database column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e8fa-139">Viz také</span><span class="sxs-lookup"><span data-stu-id="6e8fa-139">See Also</span></span>  
 [<span data-ttu-id="6e8fa-140">Dim – příkaz</span><span class="sxs-lookup"><span data-stu-id="6e8fa-140">Dim Statement</span></span>](../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="6e8fa-141">Doba života objektu: Objekty vytváření a zničení</span><span class="sxs-lookup"><span data-stu-id="6e8fa-141">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)  
 [<span data-ttu-id="6e8fa-142">Doba platnosti v jazyce Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6e8fa-142">Lifetime in Visual Basic</span></span>](../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)  
 [<span data-ttu-id="6e8fa-143">Is – operátor</span><span class="sxs-lookup"><span data-stu-id="6e8fa-143">Is Operator</span></span>](../../visual-basic/language-reference/operators/is-operator.md)  
 [<span data-ttu-id="6e8fa-144">IsNot – operátor</span><span class="sxs-lookup"><span data-stu-id="6e8fa-144">IsNot Operator</span></span>](../../visual-basic/language-reference/operators/isnot-operator.md)  
 [<span data-ttu-id="6e8fa-145">Typy hodnot s povolenou hodnotou Null</span><span class="sxs-lookup"><span data-stu-id="6e8fa-145">Nullable Value Types</span></span>](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
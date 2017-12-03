---
title: "Omezení přístupnosti přístupového objektu (Průvodce programováním v C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- read-only properties [C#]
- read-only indexers [C#]
- accessors [C#]
- properties [C#], read-only
- asymmetric accessor accesibility [C#]
- indexers [C#], read-only
ms.assetid: 6e655798-e112-4301-a680-6310a6e012e1
caps.latest.revision: "26"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: a4905885323f59d8b8b2654a5331e02054334398
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="restricting-accessor-accessibility-c-programming-guide"></a><span data-ttu-id="2d749-102">Omezení přístupnosti přístupového objektu (Průvodce programováním v C#)</span><span class="sxs-lookup"><span data-stu-id="2d749-102">Restricting Accessor Accessibility (C# Programming Guide)</span></span>
<span data-ttu-id="2d749-103">[Získat](../../../csharp/language-reference/keywords/get.md) a [nastavit](../../../csharp/language-reference/keywords/set.md) části vlastnosti nebo indexeru se nazývají *přístupové objekty*.</span><span class="sxs-lookup"><span data-stu-id="2d749-103">The [get](../../../csharp/language-reference/keywords/get.md) and [set](../../../csharp/language-reference/keywords/set.md) portions of a property or indexer are called *accessors*.</span></span> <span data-ttu-id="2d749-104">Ve výchozím nastavení mají stejné viditelnost těchto přístupových objektů, nebo úroveň přístupu: u vlastnosti nebo indexeru, do které patří.</span><span class="sxs-lookup"><span data-stu-id="2d749-104">By default these accessors have the same visibility, or access level: that of the property or indexer to which they belong.</span></span> <span data-ttu-id="2d749-105">Další informace najdete v tématu [úrovní přístupu](../../../csharp/language-reference/keywords/accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="2d749-105">For more information, see [accessibility levels](../../../csharp/language-reference/keywords/accessibility-levels.md).</span></span> <span data-ttu-id="2d749-106">Někdy je však vhodné omezit přístup na jednu z těchto přístupových objektů.</span><span class="sxs-lookup"><span data-stu-id="2d749-106">However, it is sometimes useful to restrict access to one of these accessors.</span></span> <span data-ttu-id="2d749-107">Obvykle to zahrnuje omezení přístupnosti `set` přistupujícího objektu, při zachování `get` přistupujícího objektu veřejně přístupná.</span><span class="sxs-lookup"><span data-stu-id="2d749-107">Typically, this involves restricting the accessibility of the `set` accessor, while keeping the `get` accessor publicly accessible.</span></span> <span data-ttu-id="2d749-108">Příklad:</span><span class="sxs-lookup"><span data-stu-id="2d749-108">For example:</span></span>  
  
 [!code-csharp[csProgGuideIndexers#6](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/restricting-accessor-accessibility_1.cs)]  
  
 <span data-ttu-id="2d749-109">V tomto příkladu vlastnost s názvem `Name` definuje `get` a `set` přistupujícího objektu.</span><span class="sxs-lookup"><span data-stu-id="2d749-109">In this example, a property called `Name` defines a `get` and `set` accessor.</span></span> <span data-ttu-id="2d749-110">`get` Přistupujícího objektu obdrží usnadnění úroveň samotné, vlastnosti `public` v takovém případě při `set` přistupujícího objektu je omezená explicitně použitím [chráněné](../../../csharp/language-reference/keywords/protected.md) – modifikátor přístupu k přistupující objekt sám sebe.</span><span class="sxs-lookup"><span data-stu-id="2d749-110">The `get` accessor receives the accessibility level of the property itself, `public` in this case, while the `set` accessor is explicitly restricted by applying the [protected](../../../csharp/language-reference/keywords/protected.md) access modifier to the accessor itself.</span></span>  
  
## <a name="restrictions-on-access-modifiers-on-accessors"></a><span data-ttu-id="2d749-111">Omezení modifikátory přístupu na přístupové objekty</span><span class="sxs-lookup"><span data-stu-id="2d749-111">Restrictions on Access Modifiers on Accessors</span></span>  
 <span data-ttu-id="2d749-112">Pomocí modifikátory přistupujícího objektu vlastnosti nebo indexery je nutné splnit následující podmínky:</span><span class="sxs-lookup"><span data-stu-id="2d749-112">Using the accessor modifiers on properties or indexers is subject to these conditions:</span></span>  
  
-   <span data-ttu-id="2d749-113">Modifikátory přistupujícího objektu nelze použít na rozhraní nebo pomocí explicitní [rozhraní](../../../csharp/language-reference/keywords/interface.md) implementaci prvku.</span><span class="sxs-lookup"><span data-stu-id="2d749-113">You cannot use accessor modifiers on an interface or an explicit [interface](../../../csharp/language-reference/keywords/interface.md) member implementation.</span></span>  
  
-   <span data-ttu-id="2d749-114">Modifikátory přistupující objekt můžete použít pouze v případě, že jsou vlastnost nebo indexer má oba `set` a `get` přistupující objekty.</span><span class="sxs-lookup"><span data-stu-id="2d749-114">You can use accessor modifiers only if the property or indexer has both `set` and `get` accessors.</span></span> <span data-ttu-id="2d749-115">V takovém případě je modifikátor povolená na jedné ze dvou přístupových objektů.</span><span class="sxs-lookup"><span data-stu-id="2d749-115">In this case, the modifier is permitted on one only of the two accessors.</span></span>  
  
-   <span data-ttu-id="2d749-116">Pokud má vlastnost nebo indexer [přepsat](../../../csharp/language-reference/keywords/override.md) modifikátor, modifikátor přistupujícího objektu se musí shodovat přistupujícího objektu přepsaného přistupujícího objektu, pokud existuje.</span><span class="sxs-lookup"><span data-stu-id="2d749-116">If the property or indexer has an [override](../../../csharp/language-reference/keywords/override.md) modifier, the accessor modifier must match the accessor of the overridden accessor, if any.</span></span>  
  
-   <span data-ttu-id="2d749-117">Úroveň usnadnění na přistupujícím objektu musí být více omezující než úroveň usnadnění na vlastnost nebo indexer sám sebe.</span><span class="sxs-lookup"><span data-stu-id="2d749-117">The accessibility level on the accessor must be more restrictive than the accessibility level on the property or indexer itself.</span></span>  
  
## <a name="access-modifiers-on-overriding-accessors"></a><span data-ttu-id="2d749-118">Modifikátory přístupu při přepsání přístupové objekty</span><span class="sxs-lookup"><span data-stu-id="2d749-118">Access Modifiers on Overriding Accessors</span></span>  
 <span data-ttu-id="2d749-119">Při přepsání vlastnosti nebo indexeru, musí být přístupný pro kód přepsání přepsaného přistupující objekty.</span><span class="sxs-lookup"><span data-stu-id="2d749-119">When you override a property or indexer, the overridden accessors must be accessible to the overriding code.</span></span> <span data-ttu-id="2d749-120">Navíc úroveň usnadnění jak vlastnost/indexeru a že přístupové objekty musí odpovídat odpovídající přepsané vlastnosti nebo indexeru a přístupy.</span><span class="sxs-lookup"><span data-stu-id="2d749-120">Also, the accessibility level of both the property/indexer, and that of the accessors must match the corresponding overridden property/indexer and the accessors.</span></span> <span data-ttu-id="2d749-121">Příklad:</span><span class="sxs-lookup"><span data-stu-id="2d749-121">For example:</span></span>  
  
 [!code-csharp[csProgGuideIndexers#7](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/restricting-accessor-accessibility_2.cs)]  
  
## <a name="implementing-interfaces"></a><span data-ttu-id="2d749-122">Implementace rozhraní</span><span class="sxs-lookup"><span data-stu-id="2d749-122">Implementing Interfaces</span></span>  
 <span data-ttu-id="2d749-123">Pokud používáte přistupující objekt k implementaci rozhraní, nemusí mít přistupující – modifikátor přístupu.</span><span class="sxs-lookup"><span data-stu-id="2d749-123">When you use an accessor to implement an interface, the accessor may not have an access modifier.</span></span> <span data-ttu-id="2d749-124">Ale pokud budete implementovat rozhraní pomocí jednoho přístupového objektu, například `get`, jiné přistupující objekt může mít – modifikátor přístupu, jako v následujícím příkladu:</span><span class="sxs-lookup"><span data-stu-id="2d749-124">However, if you implement the interface using one accessor, such as `get`, the other accessor can have an access modifier, as in the following example:</span></span>  
  
 [!code-csharp[csProgGuideIndexers#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/restricting-accessor-accessibility_3.cs)]  
  
## <a name="accessor-accessibility-domain"></a><span data-ttu-id="2d749-125">Doména přístupnosti přístupového objektu</span><span class="sxs-lookup"><span data-stu-id="2d749-125">Accessor Accessibility Domain</span></span>  
 <span data-ttu-id="2d749-126">Používáte-li – modifikátor přístupu přistupujícího objektu, [doména přístupnosti](../../../csharp/language-reference/keywords/accessibility-domain.md) přistupujícího objektu je dáno tento modifikátor.</span><span class="sxs-lookup"><span data-stu-id="2d749-126">If you use an access modifier on the accessor, the [accessibility domain](../../../csharp/language-reference/keywords/accessibility-domain.md) of the accessor is determined by this modifier.</span></span>  
  
 <span data-ttu-id="2d749-127">Pokud jste nepoužili – modifikátor přístupu na přistupujícím objektu, doména přístupnosti přistupujícího objektu je určen podle usnadnění úroveň vlastnost nebo indexer.</span><span class="sxs-lookup"><span data-stu-id="2d749-127">If you did not use an access modifier on the accessor, the accessibility domain of the accessor is determined by the accessibility level of the property or indexer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2d749-128">Příklad</span><span class="sxs-lookup"><span data-stu-id="2d749-128">Example</span></span>  
 <span data-ttu-id="2d749-129">Následující příklad obsahuje tři třídy `BaseClass`, `DerivedClass`, a `MainClass`.</span><span class="sxs-lookup"><span data-stu-id="2d749-129">The following example contains three classes, `BaseClass`, `DerivedClass`, and `MainClass`.</span></span> <span data-ttu-id="2d749-130">Existují dvě vlastnosti na `BaseClass`, `Name` a `Id` u obou tříd.</span><span class="sxs-lookup"><span data-stu-id="2d749-130">There are two properties on the `BaseClass`, `Name` and `Id` on both classes.</span></span> <span data-ttu-id="2d749-131">Příklad ukazuje, jak vlastnost `Id` na `DerivedClass` může být skryté vlastností `Id` na `BaseClass` při použití – modifikátor omezující přístupu, jako [chráněné](../../../csharp/language-reference/keywords/protected.md) nebo [ privátní](../../../csharp/language-reference/keywords/private.md).</span><span class="sxs-lookup"><span data-stu-id="2d749-131">The example demonstrates how the property `Id` on `DerivedClass` can be hidden by the property `Id` on `BaseClass` when you use a restrictive access modifier such as [protected](../../../csharp/language-reference/keywords/protected.md) or [private](../../../csharp/language-reference/keywords/private.md).</span></span> <span data-ttu-id="2d749-132">Proto když přiřadit hodnoty této vlastnosti, vlastnost na `BaseClass` třídy se nazývá místo.</span><span class="sxs-lookup"><span data-stu-id="2d749-132">Therefore, when you assign values to this property, the property on the `BaseClass` class is called instead.</span></span> <span data-ttu-id="2d749-133">Nahrazení – modifikátor přístupu podle [veřejné](../../../csharp/language-reference/keywords/public.md) bude zpřístupněte vlastnost.</span><span class="sxs-lookup"><span data-stu-id="2d749-133">Replacing the access modifier by [public](../../../csharp/language-reference/keywords/public.md) will make the property accessible.</span></span>  
  
 <span data-ttu-id="2d749-134">Příklad také ukazuje, který modifikátor omezující přístup, například `private` nebo `protected`na `set` přistupujícího `Name` vlastnost v `DerivedClass` brání přístupu na přistupující objekt a vygeneruje se chyba při přiřazení do ho.</span><span class="sxs-lookup"><span data-stu-id="2d749-134">The example also demonstrates that a restrictive access modifier, such as `private` or `protected`, on the `set` accessor of the `Name` property in `DerivedClass` prevents access to the accessor and generates an error when you assign to it.</span></span>  
  
 [!code-csharp[csProgGuideIndexers#5](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/restricting-accessor-accessibility_4.cs)]  
  
## <a name="comments"></a><span data-ttu-id="2d749-135">Komentáře</span><span class="sxs-lookup"><span data-stu-id="2d749-135">Comments</span></span>  
 <span data-ttu-id="2d749-136">Všimněte si, že pokud nahradíte deklaraci `new private string Id` podle `new public string Id`, získat výstup:</span><span class="sxs-lookup"><span data-stu-id="2d749-136">Notice that if you replace the declaration `new private string Id` by `new public string Id`, you get the output:</span></span>  
  
 `Name and ID in the base class: Name-BaseClass, ID-BaseClass`  
  
 `Name and ID in the derived class: John, John123`  
  
## <a name="see-also"></a><span data-ttu-id="2d749-137">Viz také</span><span class="sxs-lookup"><span data-stu-id="2d749-137">See Also</span></span>  
 [<span data-ttu-id="2d749-138">Průvodce programováním v C#</span><span class="sxs-lookup"><span data-stu-id="2d749-138">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="2d749-139">Vlastnosti</span><span class="sxs-lookup"><span data-stu-id="2d749-139">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)  
 [<span data-ttu-id="2d749-140">Indexery</span><span class="sxs-lookup"><span data-stu-id="2d749-140">Indexers</span></span>](../../../csharp/programming-guide/indexers/index.md)  
 [<span data-ttu-id="2d749-141">Modifikátory přístupu</span><span class="sxs-lookup"><span data-stu-id="2d749-141">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)
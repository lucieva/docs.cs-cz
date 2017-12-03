---
title: "Třídy (Průvodce programováním v C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- classes [C#]
- C# language, classes
ms.assetid: e8848524-7273-429f-8aba-c658d5eff5ad
caps.latest.revision: "40"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 37e810fc5a5397a6b9240346ac28505b11b1e817
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="classes-c-programming-guide"></a><span data-ttu-id="72053-102">Třídy (Průvodce programováním v C#)</span><span class="sxs-lookup"><span data-stu-id="72053-102">Classes (C# Programming Guide)</span></span>
<span data-ttu-id="72053-103">A *třída* je konstruktor, který umožňuje vytvořit vlastní typy společně seskupením proměnné jiné typy, metod a události.</span><span class="sxs-lookup"><span data-stu-id="72053-103">A *class* is a construct that enables you to create your own custom types by grouping together variables of other types, methods and events.</span></span> <span data-ttu-id="72053-104">Třída je jako plán, podle kterého.</span><span class="sxs-lookup"><span data-stu-id="72053-104">A class is like a blueprint.</span></span> <span data-ttu-id="72053-105">Definuje data a chování typu.</span><span class="sxs-lookup"><span data-stu-id="72053-105">It defines the data and behavior of a type.</span></span> <span data-ttu-id="72053-106">Pokud třída není deklarovaný jako statický, kód klienta můžete ji použít tak, že vytvoříte *objekty* nebo *instance* které jsou přiřazeny k proměnné.</span><span class="sxs-lookup"><span data-stu-id="72053-106">If the class is not declared as static, client code can use it by creating *objects* or *instances* which are assigned to a variable.</span></span> <span data-ttu-id="72053-107">Proměnná zůstane v paměti, dokud všechny odkazy na ni se dostala mimo rozsah.</span><span class="sxs-lookup"><span data-stu-id="72053-107">The variable remains in memory until all references to it go out of scope.</span></span> <span data-ttu-id="72053-108">V té době modulu CLR označí je vhodné pro uvolňování paměti.</span><span class="sxs-lookup"><span data-stu-id="72053-108">At that time, the CLR marks it as eligible for garbage collection.</span></span> <span data-ttu-id="72053-109">Pokud třída je deklarován jako [statické](../../../csharp/language-reference/keywords/static.md), pak existuje pouze jedna kopie v paměti a kód klienta pouze k němu přístup prostřednictvím třídy samostatně, není *proměnnou instance*.</span><span class="sxs-lookup"><span data-stu-id="72053-109">If the class is declared as [static](../../../csharp/language-reference/keywords/static.md), then only one copy exists in memory and client code can only access it through the class itself, not an *instance variable*.</span></span> <span data-ttu-id="72053-110">Další informace najdete v tématu [statické třídy a statické členy třídy](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="72053-110">For more information, see [Static Classes and Static Class Members](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>  
  
 <span data-ttu-id="72053-111">Na rozdíl od struktury, třídy podporu *dědičnosti*, základní vlastnosti objektově orientované programování.</span><span class="sxs-lookup"><span data-stu-id="72053-111">Unlike structs, classes support *inheritance*, a fundamental characteristic of object-oriented programming.</span></span> <span data-ttu-id="72053-112">Další informace najdete v tématu [dědičnosti](../../../csharp/programming-guide/classes-and-structs/inheritance.md).</span><span class="sxs-lookup"><span data-stu-id="72053-112">For more information, see [Inheritance](../../../csharp/programming-guide/classes-and-structs/inheritance.md).</span></span>  
  
## <a name="declaring-classes"></a><span data-ttu-id="72053-113">Deklarace tříd</span><span class="sxs-lookup"><span data-stu-id="72053-113">Declaring Classes</span></span>  
 <span data-ttu-id="72053-114">Třídy jsou deklarovány s použitím [třída](../../../csharp/language-reference/keywords/class.md) – klíčové slovo, jak je znázorněno v následujícím příkladu:</span><span class="sxs-lookup"><span data-stu-id="72053-114">Classes are declared by using the [class](../../../csharp/language-reference/keywords/class.md) keyword, as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#79](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/classes_1.cs)]  
  
 <span data-ttu-id="72053-115">`class` – Klíčové slovo předchází úroveň přístupu.</span><span class="sxs-lookup"><span data-stu-id="72053-115">The `class` keyword is preceded by the access level.</span></span> <span data-ttu-id="72053-116">Protože [veřejné](../../../csharp/language-reference/keywords/public.md) se používá v tomto případě každý, kdo může vytvářet objekty z této třídy.</span><span class="sxs-lookup"><span data-stu-id="72053-116">Because [public](../../../csharp/language-reference/keywords/public.md) is used in this case, anyone can create objects from this class.</span></span> <span data-ttu-id="72053-117">Následuje název třídy `class` – klíčové slovo.</span><span class="sxs-lookup"><span data-stu-id="72053-117">The name of the class follows the `class` keyword.</span></span> <span data-ttu-id="72053-118">Zbývající část definice je tělo třídy, kde jsou definovány chování a data.</span><span class="sxs-lookup"><span data-stu-id="72053-118">The remainder of the definition is the class body, where the behavior and data are defined.</span></span> <span data-ttu-id="72053-119">Pole, vlastnosti, metod a události na třídě se souhrnně označují jako *třídy členy*.</span><span class="sxs-lookup"><span data-stu-id="72053-119">Fields, properties, methods, and events on a class are collectively referred to as *class members*.</span></span>  
  
## <a name="creating-objects"></a><span data-ttu-id="72053-120">Vytváření objektů</span><span class="sxs-lookup"><span data-stu-id="72053-120">Creating Objects</span></span>  
 <span data-ttu-id="72053-121">I když se někdy používají zcela zaměnitelným významem, třídy a objekt jsou různých věcí.</span><span class="sxs-lookup"><span data-stu-id="72053-121">Although they are sometimes used interchangeably, a class and an object are different things.</span></span> <span data-ttu-id="72053-122">Třída definuje typ objektu, ale není objekt sám sebe.</span><span class="sxs-lookup"><span data-stu-id="72053-122">A class defines a type of object, but it is not an object itself.</span></span> <span data-ttu-id="72053-123">Objekt je založeno na třídě konkrétní entita a se někdy označuje jako instance třídy.</span><span class="sxs-lookup"><span data-stu-id="72053-123">An object is a concrete entity based on a class, and is sometimes referred to as an instance of a class.</span></span>  
  
 <span data-ttu-id="72053-124">Objekty mohou být vytvořeny pomocí [nové](../../../csharp/language-reference/keywords/new.md) – klíčové slovo a název třídy, která objekt budou založeny na, jako jsou to:</span><span class="sxs-lookup"><span data-stu-id="72053-124">Objects can be created by using the [new](../../../csharp/language-reference/keywords/new.md) keyword followed by the name of the class that the object will be based on, like this:</span></span>  
  
 [!code-csharp[csProgGuideObjects#80](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/classes_2.cs)]  
  
 <span data-ttu-id="72053-125">Když je vytvořena instance třídy, odkaz na objekt je předán zpět do programátorů.</span><span class="sxs-lookup"><span data-stu-id="72053-125">When an instance of a class is created, a reference to the object is passed back to the programmer.</span></span> <span data-ttu-id="72053-126">V předchozím příkladu `object1` je odkaz na objekt, který je založen na `Customer`.</span><span class="sxs-lookup"><span data-stu-id="72053-126">In the previous example, `object1` is a reference to an object that is based on `Customer`.</span></span> <span data-ttu-id="72053-127">Tento odkaz odkazuje na nový objekt, ale neobsahuje samotná data objektu.</span><span class="sxs-lookup"><span data-stu-id="72053-127">This reference refers to the new object but does not contain the object data itself.</span></span> <span data-ttu-id="72053-128">Ve skutečnosti můžete vytvořit odkaz na objekt bez vytvoření objektu vůbec:</span><span class="sxs-lookup"><span data-stu-id="72053-128">In fact, you can create an object reference without creating an object at all:</span></span>  
  
 [!code-csharp[csProgGuideObjects#81](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/classes_3.cs)]  
  
 <span data-ttu-id="72053-129">Nedoporučujeme vytváření odkazy na objekty, jako je tato, které není odkaz na objekt, protože při pokusu o přístup k objektu pomocí odkazu v době běhu selže.</span><span class="sxs-lookup"><span data-stu-id="72053-129">We don't recommend creating object references such as this one that don't refer to an object because trying to access an object through such a reference will fail at run time.</span></span> <span data-ttu-id="72053-130">Však můžete provést odkazu odkazovat na objekt, buď tím, že vytvoříte nový objekt, nebo jeho přiřazení k existující objekt, jako je tato:</span><span class="sxs-lookup"><span data-stu-id="72053-130">However, such a reference can be made to refer to an object, either by creating a new object, or by assigning it to an existing object, such as this:</span></span>  
  
 [!code-csharp[csProgGuideObjects#82](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/classes_4.cs)]  
  
 <span data-ttu-id="72053-131">Tento kód vytvoří dvě odkazy na objekty, které odkazují na stejný objekt.</span><span class="sxs-lookup"><span data-stu-id="72053-131">This code creates two object references that both refer to the same object.</span></span> <span data-ttu-id="72053-132">Proto všechny změny provedené prostřednictvím objektu `object3` se projeví v následné použití `object4`.</span><span class="sxs-lookup"><span data-stu-id="72053-132">Therefore, any changes to the object made through `object3` will be reflected in subsequent uses of `object4`.</span></span> <span data-ttu-id="72053-133">Protože objekty, které jsou založeny na třídy jsou označovány pomocí odkazu, třídy jsou známé jako odkazové typy.</span><span class="sxs-lookup"><span data-stu-id="72053-133">Because objects that are based on classes are referred to by reference, classes are known as reference types.</span></span>  
  
## <a name="class-inheritance"></a><span data-ttu-id="72053-134">Dědičnost tříd</span><span class="sxs-lookup"><span data-stu-id="72053-134">Class Inheritance</span></span>  
 <span data-ttu-id="72053-135">Dědičnost se dá udělat pomocí *odvození*, což znamená, že třída je deklarovaná pomocí *základní třída* z který dědí dat a chování.</span><span class="sxs-lookup"><span data-stu-id="72053-135">Inheritance is accomplished by using a *derivation*, which means a class is declared by using a *base class* from which it inherits data and behavior.</span></span> <span data-ttu-id="72053-136">Základní třída je určena připojením dvojtečkou a název základní třídy následující název odvozené třídy takto:</span><span class="sxs-lookup"><span data-stu-id="72053-136">A base class is specified by appending a colon and the name of the base class following the derived class name, like this:</span></span>  
  
 [!code-csharp[csProgGuideObjects#83](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/classes_5.cs)]  
  
 <span data-ttu-id="72053-137">Třída deklaruje základní třídu, dědí všechny členy základní třídy, s výjimkou konstruktorů.</span><span class="sxs-lookup"><span data-stu-id="72053-137">When a class declares a base class, it inherits all the members of the base class except the constructors.</span></span>  
  
 <span data-ttu-id="72053-138">Na rozdíl od C++ lze pouze přímo třídu v jazyce C# dědit z jedné základní třídy.</span><span class="sxs-lookup"><span data-stu-id="72053-138">Unlike C++, a class in C# can only directly inherit from one base class.</span></span> <span data-ttu-id="72053-139">Ale protože sám základní třídy mohou dědit z jiné třídy, třídy mohou nepřímo dědit vícenásobné základní třídy.</span><span class="sxs-lookup"><span data-stu-id="72053-139">However, because a base class may itself inherit from another class, a class may indirectly inherit multiple base classes.</span></span> <span data-ttu-id="72053-140">Kromě toho třída může implementovat přímo více než jedno rozhraní.</span><span class="sxs-lookup"><span data-stu-id="72053-140">Furthermore, a class can directly implement more than one interface.</span></span> <span data-ttu-id="72053-141">Další informace najdete v tématu [rozhraní](../../../csharp/programming-guide/interfaces/index.md).</span><span class="sxs-lookup"><span data-stu-id="72053-141">For more information, see [Interfaces](../../../csharp/programming-guide/interfaces/index.md).</span></span>  
  
 <span data-ttu-id="72053-142">Třídu lze deklarovat [abstraktní](../../../csharp/language-reference/keywords/abstract.md).</span><span class="sxs-lookup"><span data-stu-id="72053-142">A class can be declared [abstract](../../../csharp/language-reference/keywords/abstract.md).</span></span> <span data-ttu-id="72053-143">Abstraktní třída obsahuje abstraktní metody, které mají definici podpis, ale žádné implementace.</span><span class="sxs-lookup"><span data-stu-id="72053-143">An abstract class contains abstract methods that have a signature definition but no implementation.</span></span> <span data-ttu-id="72053-144">Nelze vytvořit instanci abstraktní třídy.</span><span class="sxs-lookup"><span data-stu-id="72053-144">Abstract classes cannot be instantiated.</span></span> <span data-ttu-id="72053-145">Je možné použít pouze prostřednictvím odvozené třídy, které implementují abstraktní metody.</span><span class="sxs-lookup"><span data-stu-id="72053-145">They can only be used through derived classes that implement the abstract methods.</span></span> <span data-ttu-id="72053-146">Naopak [zapečetěné](../../../csharp/language-reference/keywords/sealed.md) třídy není povoleno ostatní třídy k odvozování z něj.</span><span class="sxs-lookup"><span data-stu-id="72053-146">By contrast, a [sealed](../../../csharp/language-reference/keywords/sealed.md) class does not allow other classes to derive from it.</span></span> <span data-ttu-id="72053-147">Další informace najdete v tématu [abstraktní a zapečetěné třídy a jejich členové](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="72053-147">For more information, see [Abstract and Sealed Classes and Class Members](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).</span></span>  
  
 <span data-ttu-id="72053-148">Definice tříd můžete rozdělit mezi jiné zdrojové soubory.</span><span class="sxs-lookup"><span data-stu-id="72053-148">Class definitions can be split between different source files.</span></span> <span data-ttu-id="72053-149">Další informace najdete v tématu [částečné třídy a metody](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md).</span><span class="sxs-lookup"><span data-stu-id="72053-149">For more information, see [Partial Classes and Methods](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md).</span></span>  
  
## <a name="description"></a><span data-ttu-id="72053-150">Popis</span><span class="sxs-lookup"><span data-stu-id="72053-150">Description</span></span>  
 <span data-ttu-id="72053-151">V následujícím příkladu je definována veřejnou třídu, která obsahuje jednoho pole, metodu a speciální metodu s názvem konstruktor.</span><span class="sxs-lookup"><span data-stu-id="72053-151">In the following example, a public class that contains a single field, a method, and a special method called a constructor is defined.</span></span> <span data-ttu-id="72053-152">Další informace najdete v tématu [konstruktory](../../../csharp/programming-guide/classes-and-structs/constructors.md).</span><span class="sxs-lookup"><span data-stu-id="72053-152">For more information, see [Constructors](../../../csharp/programming-guide/classes-and-structs/constructors.md).</span></span> <span data-ttu-id="72053-153">Instance třídy je pak vytvářet pomocí `new` – klíčové slovo.</span><span class="sxs-lookup"><span data-stu-id="72053-153">The class is then instantiated with the `new` keyword.</span></span>  
  
## <a name="example"></a><span data-ttu-id="72053-154">Příklad</span><span class="sxs-lookup"><span data-stu-id="72053-154">Example</span></span>  
 [!code-csharp[csProgGuideObjects#84](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/classes_6.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="72053-155">Specifikace jazyka C#</span><span class="sxs-lookup"><span data-stu-id="72053-155">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="72053-156">Viz také</span><span class="sxs-lookup"><span data-stu-id="72053-156">See Also</span></span>  
 [<span data-ttu-id="72053-157">Průvodce programováním v C#</span><span class="sxs-lookup"><span data-stu-id="72053-157">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="72053-158">Objektově orientované programování</span><span class="sxs-lookup"><span data-stu-id="72053-158">Object-Oriented Programming</span></span>](../concepts/object-oriented-programming.md)  
 [<span data-ttu-id="72053-159">Polymorfismus</span><span class="sxs-lookup"><span data-stu-id="72053-159">Polymorphism</span></span>](../../../csharp/programming-guide/classes-and-structs/polymorphism.md)  
 [<span data-ttu-id="72053-160">Členy</span><span class="sxs-lookup"><span data-stu-id="72053-160">Members</span></span>](../../../csharp/programming-guide/classes-and-structs/members.md)  
 [<span data-ttu-id="72053-161">Metody</span><span class="sxs-lookup"><span data-stu-id="72053-161">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)  
 [<span data-ttu-id="72053-162">Konstruktory</span><span class="sxs-lookup"><span data-stu-id="72053-162">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
 [<span data-ttu-id="72053-163">Finalizační metody</span><span class="sxs-lookup"><span data-stu-id="72053-163">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)  
 [<span data-ttu-id="72053-164">Objekty</span><span class="sxs-lookup"><span data-stu-id="72053-164">Objects</span></span>](../../../csharp/programming-guide/classes-and-structs/objects.md)
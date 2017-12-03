---
title: "Statické třídy a jejich členové (Průvodce programováním v C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- C# language, static members
- static members [C#]
- static classes [C#]
- C# language, static classes
- static class members [C#]
ms.assetid: 235614b5-1371-4dbd-9abd-b406a8b0298b
caps.latest.revision: "49"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: cf2517dd5989d36341b840ffcb476cbeb14baf54
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="static-classes-and-static-class-members-c-programming-guide"></a><span data-ttu-id="ced42-102">Statické třídy a jejich členové (Průvodce programováním v C#)</span><span class="sxs-lookup"><span data-stu-id="ced42-102">Static Classes and Static Class Members (C# Programming Guide)</span></span>
<span data-ttu-id="ced42-103">A [statické](../../../csharp/language-reference/keywords/static.md) třída je v podstatě stejný jako nestatickou třídu, ale je jeden rozdíl: statická třída nelze vytvořit instanci.</span><span class="sxs-lookup"><span data-stu-id="ced42-103">A [static](../../../csharp/language-reference/keywords/static.md) class is basically the same as a non-static class, but there is one difference: a static class cannot be instantiated.</span></span> <span data-ttu-id="ced42-104">Jinými slovy, nemůžete použít [nové](../../../csharp/language-reference/keywords/new.md) – klíčové slovo vytvoření proměnné typu třídy.</span><span class="sxs-lookup"><span data-stu-id="ced42-104">In other words, you cannot use the [new](../../../csharp/language-reference/keywords/new.md) keyword to create a variable of the class type.</span></span> <span data-ttu-id="ced42-105">Protože neexistuje žádná instance proměnné, máte přístup k členové statické třídy pomocí samotný název třídy.</span><span class="sxs-lookup"><span data-stu-id="ced42-105">Because there is no instance variable, you access the members of a static class by using the class name itself.</span></span> <span data-ttu-id="ced42-106">Například pokud máte statického třídy, která má název `UtilityClass` s veřejnou metodu s názvem `MethodA`, volejte metodu, jak je znázorněno v následujícím příkladu:</span><span class="sxs-lookup"><span data-stu-id="ced42-106">For example, if you have a static class that is named `UtilityClass` that has a public method named `MethodA`, you call the method as shown in the following example:</span></span>  
  
```csharp  
UtilityClass.MethodA();  
```  
  
 <span data-ttu-id="ced42-107">Statická třída slouží jako kontejner vhodné pro sady metod, které právě pracují vstupní parametry a nemají k získání nebo nastavení všechna pole interní instance.</span><span class="sxs-lookup"><span data-stu-id="ced42-107">A static class can be used as a convenient container for sets of methods that just operate on input parameters and do not have to get or set any internal instance fields.</span></span> <span data-ttu-id="ced42-108">Například v knihovně tříd rozhraní .NET Framework, statické <xref:System.Math?displayProperty=nameWithType> třída obsahuje metody, které provádějí matematické operace, aniž by bylo nutné ukládat a načítat data, která jsou jedinečná pro konkrétní instanci <xref:System.Math> třídy.</span><span class="sxs-lookup"><span data-stu-id="ced42-108">For example, in the .NET Framework Class Library, the static <xref:System.Math?displayProperty=nameWithType> class contains methods that perform mathematical operations, without any requirement to store or retrieve data that is unique to a particular instance of the <xref:System.Math> class.</span></span> <span data-ttu-id="ced42-109">To znamená můžete použít členy třídy tak, že zadáte název třídy a název metody, jak je znázorněno v následujícím příkladu.</span><span class="sxs-lookup"><span data-stu-id="ced42-109">That is, you apply the members of the class by specifying the class name and the method name, as shown in the following example.</span></span>  
  
```csharp  
double dub = -3.14;  
Console.WriteLine(Math.Abs(dub));  
Console.WriteLine(Math.Floor(dub));  
Console.WriteLine(Math.Round(Math.Abs(dub)));  
  
// Output:  
// 3.14  
// -4  
// 3  
```  
  
 <span data-ttu-id="ced42-110">Je tomu u všechny typy tříd, informací o typu pro statická třída zavedená [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] modul common language runtime (CLR), když je načten program, který odkazuje na třídu.</span><span class="sxs-lookup"><span data-stu-id="ced42-110">As is the case with all class types, the type information for a static class is loaded by the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] common language runtime (CLR) when the program that references the class is loaded.</span></span> <span data-ttu-id="ced42-111">Program nelze zadat přesně při načtení třídy.</span><span class="sxs-lookup"><span data-stu-id="ced42-111">The program cannot specify exactly when the class is loaded.</span></span> <span data-ttu-id="ced42-112">Nicméně je zaručeno, má být načten a na jeho pole inicializovat a jeho statického konstruktoru voláno před provedením třída odkazuje poprvé v programu.</span><span class="sxs-lookup"><span data-stu-id="ced42-112">However, it is guaranteed to be loaded and to have its fields initialized and its static constructor called before the class is referenced for the first time in your program.</span></span> <span data-ttu-id="ced42-113">Statický konstruktor je volána pouze jednou a statická třída zůstane v paměti pro dobu životnosti domény aplikace, ve kterém se nachází váš program.</span><span class="sxs-lookup"><span data-stu-id="ced42-113">A static constructor is only called one time, and a static class remains in memory for the lifetime of the application domain in which your program resides.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ced42-114">Vytvoření nestatickou třídu, která povoluje pouze jednu instanci vlastní kód, který se má vytvořit, naleznete v části [implementace jednotlivý prvek v C#](http://go.microsoft.com/fwlink/?LinkID=100567).</span><span class="sxs-lookup"><span data-stu-id="ced42-114">To create a non-static class that allows only one instance of itself to be created, see [Implementing Singleton in C#](http://go.microsoft.com/fwlink/?LinkID=100567).</span></span>  
  
 <span data-ttu-id="ced42-115">Následující seznam obsahuje hlavní funkce statické třídy:</span><span class="sxs-lookup"><span data-stu-id="ced42-115">The following list provides the main features of a static class:</span></span>  
  
-   <span data-ttu-id="ced42-116">Obsahuje pouze statické členy.</span><span class="sxs-lookup"><span data-stu-id="ced42-116">Contains only static members.</span></span>  
  
-   <span data-ttu-id="ced42-117">Nelze vytvořit instanci.</span><span class="sxs-lookup"><span data-stu-id="ced42-117">Cannot be instantiated.</span></span>  
  
-   <span data-ttu-id="ced42-118">Je zapečetěná.</span><span class="sxs-lookup"><span data-stu-id="ced42-118">Is sealed.</span></span>  
  
-   <span data-ttu-id="ced42-119">Nemůže obsahovat [konstruktory instancí](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="ced42-119">Cannot contain [Instance Constructors](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).</span></span>  
  
 <span data-ttu-id="ced42-120">Vytvoření statické třídy je tedy v podstatě stejný jako vytváření třídu, která obsahuje jenom statické členy a soukromý konstruktor.</span><span class="sxs-lookup"><span data-stu-id="ced42-120">Creating a static class is therefore basically the same as creating a class that contains only static members and a private constructor.</span></span> <span data-ttu-id="ced42-121">Soukromý konstruktor zabrání vytváření instancí třídy.</span><span class="sxs-lookup"><span data-stu-id="ced42-121">A private constructor prevents the class from being instantiated.</span></span> <span data-ttu-id="ced42-122">Výhodou použití statická třída je, že kompilátor můžete zkontrolovat a ujistěte se, že žádné členy instancí jsou omylem přidán.</span><span class="sxs-lookup"><span data-stu-id="ced42-122">The advantage of using a static class is that the compiler can check to make sure that no instance members are accidentally added.</span></span> <span data-ttu-id="ced42-123">Kompilátor zaručí, že instance této třídy nelze vytvořit.</span><span class="sxs-lookup"><span data-stu-id="ced42-123">The compiler will guarantee that instances of this class cannot be created.</span></span>  
  
 <span data-ttu-id="ced42-124">Statické třídy jsou zapečetěné a nelze ji proto zdědit.</span><span class="sxs-lookup"><span data-stu-id="ced42-124">Static classes are sealed and therefore cannot be inherited.</span></span> <span data-ttu-id="ced42-125">Nelze zdědit z libovolné třídy s výjimkou <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="ced42-125">They cannot inherit from any class except <xref:System.Object>.</span></span> <span data-ttu-id="ced42-126">Statické třídy nemohou obsahovat konstruktoru instance; však mohou obsahovat statický konstruktor.</span><span class="sxs-lookup"><span data-stu-id="ced42-126">Static classes cannot contain an instance constructor; however, they can contain a static constructor.</span></span> <span data-ttu-id="ced42-127">Nestatické třídy měli také definovat statického konstruktoru, pokud třída obsahuje statické členy, které vyžadují netriviální inicializace.</span><span class="sxs-lookup"><span data-stu-id="ced42-127">Non-static classes should also define a static constructor if the class contains static members that require non-trivial initialization.</span></span> <span data-ttu-id="ced42-128">Další informace najdete v tématu [statické konstruktory](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="ced42-128">For more information, see [Static Constructors](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ced42-129">Příklad</span><span class="sxs-lookup"><span data-stu-id="ced42-129">Example</span></span>  
 <span data-ttu-id="ced42-130">Tady je příklad statické třídy, která obsahuje dvě metody, které převést teploty z c na Fahrenheita a Fahrenheita k c:</span><span class="sxs-lookup"><span data-stu-id="ced42-130">Here is an example of a static class that contains two methods that convert temperature from Celsius to Fahrenheit and from Fahrenheit to Celsius:</span></span>  
  
 [!code-csharp[csProgGuideObjects#31](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-classes-and-static-class-members_1.cs)]  
  
## <a name="static-members"></a><span data-ttu-id="ced42-131">Statické členy</span><span class="sxs-lookup"><span data-stu-id="ced42-131">Static Members</span></span>  
 <span data-ttu-id="ced42-132">Nestatické třídy může obsahovat statických metod, polí, vlastnosti a události.</span><span class="sxs-lookup"><span data-stu-id="ced42-132">A non-static class can contain static methods, fields, properties, or events.</span></span> <span data-ttu-id="ced42-133">Statický člen je možné volat na třídě, i když se vytvořil žádná instance třídy.</span><span class="sxs-lookup"><span data-stu-id="ced42-133">The static member is callable on a class even when no instance of the class has been created.</span></span> <span data-ttu-id="ced42-134">Statický člen vždy přístup k názvu třídy, ne název instance.</span><span class="sxs-lookup"><span data-stu-id="ced42-134">The static member is always accessed by the class name, not the instance name.</span></span> <span data-ttu-id="ced42-135">Existuje pouze jedna kopie je statický člen, bez ohledu na to, kolik instancí třídy jsou vytvořeny.</span><span class="sxs-lookup"><span data-stu-id="ced42-135">Only one copy of a static member exists, regardless of how many instances of the class are created.</span></span> <span data-ttu-id="ced42-136">Statické metody a vlastnosti nemůže získat přístup nestatické pole a události v jejich obsahující typ, a pokud je výslovně předán v parametru metody nemají přístup k proměnné instance libovolného objektu.</span><span class="sxs-lookup"><span data-stu-id="ced42-136">Static methods and properties cannot access non-static fields and events in their containing type, and they cannot access an instance variable of any object unless it is explicitly passed in a method parameter.</span></span>  
  
 <span data-ttu-id="ced42-137">Je typičtější deklarovat nestatickou třídu s některé statických členů, než se deklarovat celou třídu jako statické.</span><span class="sxs-lookup"><span data-stu-id="ced42-137">It is more typical to declare a non-static class with some static members, than to declare an entire class as static.</span></span> <span data-ttu-id="ced42-138">Dva běžná použití statických polí jsou si nechat počet objektů, které byly vytvořeny, nebo uložit hodnotu, která musí být sdílen všechny instance.</span><span class="sxs-lookup"><span data-stu-id="ced42-138">Two common uses of static fields are to keep a count of the number of objects that have been instantiated, or to store a value that must be shared among all instances.</span></span>  
  
 <span data-ttu-id="ced42-139">Statické metody můžete přetížený ale přepsána nejsou, protože náleží do třídy a ne na jakoukoli instanci třídy.</span><span class="sxs-lookup"><span data-stu-id="ced42-139">Static methods can be overloaded but not overridden, because they belong to the class, and not to any instance of the class.</span></span>  
  
 <span data-ttu-id="ced42-140">I když pole nelze deklarovat jako `static const`, [const](../../../csharp/language-reference/keywords/const.md) pole je v podstatě statické ve své chování.</span><span class="sxs-lookup"><span data-stu-id="ced42-140">Although a field cannot be declared as `static const`, a [const](../../../csharp/language-reference/keywords/const.md) field is essentially static in its behavior.</span></span> <span data-ttu-id="ced42-141">Patří do typu, aby instance typu.</span><span class="sxs-lookup"><span data-stu-id="ced42-141">It belongs to the type, not to instances of the type.</span></span> <span data-ttu-id="ced42-142">Proto const pole je přístupná pomocí stejné `ClassName.MemberName` zápis, který se používá pro statických polí.</span><span class="sxs-lookup"><span data-stu-id="ced42-142">Therefore, const fields can be accessed by using the same `ClassName.MemberName` notation that is used for static fields.</span></span> <span data-ttu-id="ced42-143">Vyžaduje se žádná instance objektu.</span><span class="sxs-lookup"><span data-stu-id="ced42-143">No object instance is required.</span></span>  
  
 <span data-ttu-id="ced42-144">C# nepodporuje statické místní proměnné (proměnné, které jsou deklarované v oboru metoda).</span><span class="sxs-lookup"><span data-stu-id="ced42-144">C# does not support static local variables (variables that are declared in method scope).</span></span>  
  
 <span data-ttu-id="ced42-145">Deklarace členové statické třídy pomocí `static` – klíčové slovo před návratový typ člena, jak je znázorněno v následujícím příkladu:</span><span class="sxs-lookup"><span data-stu-id="ced42-145">You declare static class members by using the `static` keyword before the return type of the member, as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#29](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-classes-and-static-class-members_2.cs)]  
  
 <span data-ttu-id="ced42-146">Statické členy se inicializují před statický člen přistupuje poprvé a před statického konstruktoru, pokud existuje, je volána.</span><span class="sxs-lookup"><span data-stu-id="ced42-146">Static members are initialized before the static member is accessed for the first time and before the static constructor, if there is one, is called.</span></span> <span data-ttu-id="ced42-147">O přístup člena statická třída, použijte název třídy místo název proměnné a určete tak umístění člena, jak je znázorněno v následujícím příkladu:</span><span class="sxs-lookup"><span data-stu-id="ced42-147">To access a static class member, use the name of the class instead of a variable name to specify the location of the member, as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#30](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-classes-and-static-class-members_3.cs)]  
  
 <span data-ttu-id="ced42-148">Pokud vaše třída obsahuje statická pole, zadejte statický konstruktor, který inicializuje je při načítání třídy.</span><span class="sxs-lookup"><span data-stu-id="ced42-148">If your class contains static fields, provide a static constructor that initializes them when the class is loaded.</span></span>  
  
 <span data-ttu-id="ced42-149">Volání statickou metodu generuje volání instrukce v Microsoft (MSIL intermediate language), zatímco generuje volání metody instance `callvirt` instrukce, které také zkontroluje pro odkazuje na objekt s hodnotou null.</span><span class="sxs-lookup"><span data-stu-id="ced42-149">A call to a static method generates a call instruction in Microsoft intermediate language (MSIL), whereas a call to an instance method generates a `callvirt` instruction, which also checks for a null object references.</span></span> <span data-ttu-id="ced42-150">Ale ve většině případů výkonu rozdíl mezi nimi není důležité.</span><span class="sxs-lookup"><span data-stu-id="ced42-150">However, most of the time the performance difference between the two is not significant.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="ced42-151">Specifikace jazyka C#</span><span class="sxs-lookup"><span data-stu-id="ced42-151">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ced42-152">Viz také</span><span class="sxs-lookup"><span data-stu-id="ced42-152">See Also</span></span>  
 [<span data-ttu-id="ced42-153">Průvodce programováním v C#</span><span class="sxs-lookup"><span data-stu-id="ced42-153">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="ced42-154">statické</span><span class="sxs-lookup"><span data-stu-id="ced42-154">static</span></span>](../../../csharp/language-reference/keywords/static.md)  
 [<span data-ttu-id="ced42-155">Třídy</span><span class="sxs-lookup"><span data-stu-id="ced42-155">Classes</span></span>](../../../csharp/programming-guide/classes-and-structs/classes.md)  
 [<span data-ttu-id="ced42-156">– Třída</span><span class="sxs-lookup"><span data-stu-id="ced42-156">class</span></span>](../../../csharp/language-reference/keywords/class.md)  
 [<span data-ttu-id="ced42-157">Statické konstruktory</span><span class="sxs-lookup"><span data-stu-id="ced42-157">Static Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/static-constructors.md)  
 [<span data-ttu-id="ced42-158">Konstruktory instancí</span><span class="sxs-lookup"><span data-stu-id="ced42-158">Instance Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md)
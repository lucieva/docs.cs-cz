---
title: "Výrazy lambda (Průvodce programováním v C#)"
ms.date: 03/03/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- lambda expressions [C#]
- outer variables [C#]
- statement lambda [C#]
- expression lambda [C#]
- expressions [C#], lambda
ms.assetid: 57e3ba27-9a82-4067-aca7-5ca446b7bf93
caps.latest.revision: "64"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 9127cc5404fb85356f01cac26aa7b03a8ccd70da
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="lambda-expressions-c-programming-guide"></a><span data-ttu-id="0a87c-102">Výrazy lambda (Průvodce programováním v C#)</span><span class="sxs-lookup"><span data-stu-id="0a87c-102">Lambda Expressions (C# Programming Guide)</span></span>
<span data-ttu-id="0a87c-103">Výraz lambda je [anonymní funkce](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md) , můžete použít k vytvoření [delegáti](../../../csharp/programming-guide/delegates/using-delegates.md) nebo [strom výrazu](http://msdn.microsoft.com/library/fb1d3ed8-d5b0-4211-a71f-dd271529294b) typy.</span><span class="sxs-lookup"><span data-stu-id="0a87c-103">A lambda expression is an [anonymous function](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md) that you can use to create [delegates](../../../csharp/programming-guide/delegates/using-delegates.md) or [expression tree](http://msdn.microsoft.com/library/fb1d3ed8-d5b0-4211-a71f-dd271529294b) types.</span></span> <span data-ttu-id="0a87c-104">Pomocí výrazů lambda můžete psát místní funkce, které mohou být předány jako argumenty nebo vráceny jako hodnota volání funkce.</span><span class="sxs-lookup"><span data-stu-id="0a87c-104">By using lambda expressions, you can write local functions that can be passed as arguments or returned as the value of function calls.</span></span> <span data-ttu-id="0a87c-105">Výrazy lambda jsou zvláště užitečné pro psaní výrazů dotazů LINQ.</span><span class="sxs-lookup"><span data-stu-id="0a87c-105">Lambda expressions are particularly helpful for writing LINQ query expressions.</span></span>  
  
 <span data-ttu-id="0a87c-106">K vytvoření výrazu lambda, můžete zadat vstupní parametry (pokud existuje) na levé straně operátoru lambda [ => ](../../../csharp/language-reference/operators/lambda-operator.md), a umístí výraz nebo příkaz bloku na druhé straně.</span><span class="sxs-lookup"><span data-stu-id="0a87c-106">To create a lambda expression, you specify input parameters (if any) on the left side of the lambda operator [=>](../../../csharp/language-reference/operators/lambda-operator.md), and you put the expression or statement block on the other side.</span></span> <span data-ttu-id="0a87c-107">Například výrazu lambda `x => x * x` určuje parametr, který je pojmenován `x` a vrátí hodnotu `x` kvadratických.</span><span class="sxs-lookup"><span data-stu-id="0a87c-107">For example, the lambda expression `x => x * x` specifies a parameter that’s named `x` and returns the value of `x` squared.</span></span> <span data-ttu-id="0a87c-108">Tento výraz můžete přiřadit typu delegátu, jak ukazuje následující příklad:</span><span class="sxs-lookup"><span data-stu-id="0a87c-108">You can assign this expression to a delegate type, as the following example shows:</span></span>  
  
```csharp  
delegate int del(int i);  
static void Main(string[] args)  
{  
    del myDelegate = x => x * x;  
    int j = myDelegate(5); //j = 25  
}  
```  
  
 <span data-ttu-id="0a87c-109">Postup vytvoření typu stromu výrazu:</span><span class="sxs-lookup"><span data-stu-id="0a87c-109">To create an expression tree type:</span></span>  
  
```csharp  
using System.Linq.Expressions;  
  
namespace ConsoleApplication1  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            Expression<del> myET = x => x * x;  
        }  
    }  
}  
```  
  
 <span data-ttu-id="0a87c-110">`=>` Operátor má stejnou prioritu jako přiřazení (`=`) a je [právo asociativní](../../../csharp/programming-guide/statements-expressions-operators/operators.md) (viz oddíl "Asociativnost" článku operátory).</span><span class="sxs-lookup"><span data-stu-id="0a87c-110">The `=>` operator has the same precedence as assignment (`=`) and is [right associative](../../../csharp/programming-guide/statements-expressions-operators/operators.md) (see "Associativity" section of the Operators article).</span></span>  
  
 <span data-ttu-id="0a87c-111">Lambdas se používají v na základě metod [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] dotazuje jako argumenty pro standardní dotaz operátor metody, jako <xref:System.Linq.Enumerable.Where%2A>.</span><span class="sxs-lookup"><span data-stu-id="0a87c-111">Lambdas are used in method-based [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries as arguments to standard query operator methods such as <xref:System.Linq.Enumerable.Where%2A>.</span></span>  
  
 <span data-ttu-id="0a87c-112">Při použití syntaxe na základě metod k volání <xref:System.Linq.Enumerable.Where%2A> metoda v <xref:System.Linq.Enumerable> – třída (stejně jako [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] k objektům a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]) parametr je typem delegáta <xref:System.Func%602?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0a87c-112">When you use method-based syntax to call the <xref:System.Linq.Enumerable.Where%2A> method in the <xref:System.Linq.Enumerable> class (as you do in [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] to Objects and [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]) the parameter is a delegate type <xref:System.Func%602?displayProperty=nameWithType>.</span></span> <span data-ttu-id="0a87c-113">Výraz lambda je nejvhodnějším způsobem vytvoření tohoto delegátu.</span><span class="sxs-lookup"><span data-stu-id="0a87c-113">A lambda expression is the most convenient way to create that delegate.</span></span> <span data-ttu-id="0a87c-114">Když zavoláte na stejnou metodu, například <xref:System.Linq.Queryable?displayProperty=nameWithType> – třída (stejně jako [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]) je typ parametru <xref:System.Linq.Expressions.Expression?displayProperty=nameWithType>< Func\> kde Func je všechny delegáty Func s až šestnáct vstupní parametry.</span><span class="sxs-lookup"><span data-stu-id="0a87c-114">When you call the same method in, for example, the <xref:System.Linq.Queryable?displayProperty=nameWithType> class (as you do in [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]) then the parameter type is an <xref:System.Linq.Expressions.Expression?displayProperty=nameWithType><Func\> where Func is any of the Func delegates with up to sixteen input parameters.</span></span> <span data-ttu-id="0a87c-115">Výraz lambda je opět pouze velmi stručným způsobem vytvoření tohoto stromu výrazu.</span><span class="sxs-lookup"><span data-stu-id="0a87c-115">Again, a lambda expression is just a very concise way to construct that expression tree.</span></span> <span data-ttu-id="0a87c-116">Povolit lambdas `Where` volání vypadat, i když ve skutečnosti je jiný typ objektu vytvořeny z argument lambda.</span><span class="sxs-lookup"><span data-stu-id="0a87c-116">The lambdas allow the `Where` calls to look similar although in fact the type of object created from the lambda is different.</span></span>  
  
 <span data-ttu-id="0a87c-117">V předchozím příkladu, Všimněte si, že delegáta má jeden implicitně typované vstupní parametr typu `int`a vrátí `int`.</span><span class="sxs-lookup"><span data-stu-id="0a87c-117">In the previous example, notice that the delegate signature has one implicitly-typed input parameter of type `int`, and returns an `int`.</span></span> <span data-ttu-id="0a87c-118">Výraz lambda lze převést na delegáta daného typu, protože má také jeden vstupní parametr (`x`) a návratovou hodnotu, která můžete kompilátor implicitně převést na typ `int`.</span><span class="sxs-lookup"><span data-stu-id="0a87c-118">The lambda expression can be converted to a delegate of that type because it also has one input parameter (`x`) and a return value that the compiler can implicitly convert to type `int`.</span></span> <span data-ttu-id="0a87c-119">(Odvození typu je popsáno podrobněji v následujících částech). Pokud je delegát vyvolán pomocí vstupního parametru 5, vrátí výsledek 25.</span><span class="sxs-lookup"><span data-stu-id="0a87c-119">(Type inference is discussed in more detail in the following sections.) When the delegate is invoked by using an input parameter of 5, it returns a result of 25.</span></span>  
  
 <span data-ttu-id="0a87c-120">Lambdas nejsou povoleny na levé straně [je](../../../csharp/language-reference/keywords/is.md) nebo [jako](../../../csharp/language-reference/keywords/as.md) operátor.</span><span class="sxs-lookup"><span data-stu-id="0a87c-120">Lambdas are not allowed on the left side of the [is](../../../csharp/language-reference/keywords/is.md) or [as](../../../csharp/language-reference/keywords/as.md) operator.</span></span>  
  
 <span data-ttu-id="0a87c-121">Všechna omezení, která platí pro anonymní metody, platí také pro výrazy lambda.</span><span class="sxs-lookup"><span data-stu-id="0a87c-121">All restrictions that apply to anonymous methods also apply to lambda expressions.</span></span> <span data-ttu-id="0a87c-122">Další informace najdete v tématu [anonymní metody](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md).</span><span class="sxs-lookup"><span data-stu-id="0a87c-122">For more information, see [Anonymous Methods](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md).</span></span>  
  
## <a name="expression-lambdas"></a><span data-ttu-id="0a87c-123">Výrazové lambdy</span><span class="sxs-lookup"><span data-stu-id="0a87c-123">Expression Lambdas</span></span>  
 <span data-ttu-id="0a87c-124">Výraz lambda s výrazu na pravé straně = > operátor je volána *výrazu lambda*.</span><span class="sxs-lookup"><span data-stu-id="0a87c-124">A lambda expression with an expression on the right side of the => operator is called an *expression lambda*.</span></span> <span data-ttu-id="0a87c-125">Lambda výrazy jsou používány při sestavování [stromů výrazů](http://msdn.microsoft.com/library/fb1d3ed8-d5b0-4211-a71f-dd271529294b).</span><span class="sxs-lookup"><span data-stu-id="0a87c-125">Expression lambdas are used extensively in the construction of [Expression Trees](http://msdn.microsoft.com/library/fb1d3ed8-d5b0-4211-a71f-dd271529294b).</span></span> <span data-ttu-id="0a87c-126">Výrazová lambda vrátí výsledek výrazu a má následující základní podobu:</span><span class="sxs-lookup"><span data-stu-id="0a87c-126">An expression lambda returns the result of the expression and takes the following basic form:</span></span>  
  
```csharp
(input-parameters) => expression
```

 <span data-ttu-id="0a87c-127">Závorky jsou nepovinné pouze v případě, že lambda má jeden vstupní parametr; v opačném případě jsou vyžadovány.</span><span class="sxs-lookup"><span data-stu-id="0a87c-127">The parentheses are optional only if the lambda has one input parameter; otherwise they are required.</span></span> <span data-ttu-id="0a87c-128">Dva nebo více vstupních parametrů je odděleno čárkami, které jsou uvedeny v závorkách:</span><span class="sxs-lookup"><span data-stu-id="0a87c-128">Two or more input parameters are separated by commas enclosed in parentheses:</span></span>  
  
```csharp
(x, y) => x == y
```

 <span data-ttu-id="0a87c-129">Někdy je pro kompilátor obtížné či nemožné odvodit vstupní typy.</span><span class="sxs-lookup"><span data-stu-id="0a87c-129">Sometimes it is difficult or impossible for the compiler to infer the input types.</span></span> <span data-ttu-id="0a87c-130">V takovém případě můžete určit typy explicitně, jak je znázorněno v následujícím příkladu:</span><span class="sxs-lookup"><span data-stu-id="0a87c-130">When this occurs, you can specify the types explicitly as shown in the following example:</span></span>  
  
```csharp
(int x, string s) => s.Length > x
```

 <span data-ttu-id="0a87c-131">Zadejte nulové vstupní parametry s prázdnými závorkami:</span><span class="sxs-lookup"><span data-stu-id="0a87c-131">Specify zero input parameters with empty parentheses:</span></span>  
  
```csharp
() => SomeMethod()
```

 <span data-ttu-id="0a87c-132">V předchozím příkladu si všimněte, že hlavní část výrazové lambdy může být tvořena voláním metody.</span><span class="sxs-lookup"><span data-stu-id="0a87c-132">Note in the previous example that the body of an expression lambda can consist of a method call.</span></span> <span data-ttu-id="0a87c-133">Pokud však vytváříte stromy výrazu, které jsou vyhodnocovány mimo rozhraní .NET Framework, například na SQL Server, neměli byste používat volání metody ve výrazech lambda.</span><span class="sxs-lookup"><span data-stu-id="0a87c-133">However, if you are creating expression trees that are evaluated outside of the .NET Framework, such as in SQL Server, you should not use method calls in lambda expressions.</span></span> <span data-ttu-id="0a87c-134">Metody nemají význam mimo kontext modulu CLR (Common Language Runtime) rozhraní .NET.</span><span class="sxs-lookup"><span data-stu-id="0a87c-134">The methods will have no meaning outside the context of the .NET common language runtime.</span></span>  
  
## <a name="statement-lambdas"></a><span data-ttu-id="0a87c-135">Příkazové lambdy</span><span class="sxs-lookup"><span data-stu-id="0a87c-135">Statement Lambdas</span></span>  
 <span data-ttu-id="0a87c-136">Příkazová lambda se podobá výrazové lambdě s tím rozdílem, že výrazy jsou uzavřeny ve složených závorkách:</span><span class="sxs-lookup"><span data-stu-id="0a87c-136">A statement lambda resembles an expression lambda except that the statement(s) is enclosed in braces:</span></span>  
  
<span data-ttu-id="0a87c-137">(vstupní parametry) = > {příkaz;}</span><span class="sxs-lookup"><span data-stu-id="0a87c-137">(input-parameters) => { statement; }</span></span>

 <span data-ttu-id="0a87c-138">Text příkazové lambdy může obsahovat libovolný počet příkazů. V praxi jich však není obvykle více než dva nebo tři.</span><span class="sxs-lookup"><span data-stu-id="0a87c-138">The body of a statement lambda can consist of any number of statements; however, in practice there are typically no more than two or three.</span></span>  
  
[!code-csharp[StatementLamba#1](../../../../samples\snippets\csharp\programming-guide\lambda-expressions/statements.cs#1)]

[!code-csharp[StatementLamba#2](../../../../samples\snippets\csharp\programming-guide\lambda-expressions/statements.cs#2)]

 <span data-ttu-id="0a87c-139">Příkazové lambdy nelze stejně jako anonymní metody používat k vytvoření stromů výrazu.</span><span class="sxs-lookup"><span data-stu-id="0a87c-139">Statement lambdas, like anonymous methods, cannot be used to create expression trees.</span></span>  
  
## <a name="async-lambdas"></a><span data-ttu-id="0a87c-140">Asynchronní lambdy</span><span class="sxs-lookup"><span data-stu-id="0a87c-140">Async Lambdas</span></span>  
 <span data-ttu-id="0a87c-141">Můžete snadno vytvořit lambda – výrazy a příkazy, které zahrnují asynchronní zpracování pomocí [asynchronní](../../../csharp/language-reference/keywords/async.md) a [await](../../../csharp/language-reference/keywords/await.md) klíčová slova.</span><span class="sxs-lookup"><span data-stu-id="0a87c-141">You can easily create lambda expressions and statements that incorporate asynchronous processing by using the [async](../../../csharp/language-reference/keywords/async.md) and [await](../../../csharp/language-reference/keywords/await.md) keywords.</span></span> <span data-ttu-id="0a87c-142">Například následující příklad Windows Forms obsahuje obslužnou rutinu události, která volá a čeká použití asynchronní metody `ExampleMethodAsync`.</span><span class="sxs-lookup"><span data-stu-id="0a87c-142">For example, the following Windows Forms example contains an event handler that calls and awaits an async method, `ExampleMethodAsync`.</span></span>  
  
```csharp
public partial class Form1 : Form  
{  
    public Form1()  
    {  
        InitializeComponent();  
    }  
  
    private async void button1_Click(object sender, EventArgs e)  
    {  
        // ExampleMethodAsync returns a Task.  
        await ExampleMethodAsync();  
        textBox1.Text += "\r\nControl returned to Click event handler.\n";  
    }  
  
    async Task ExampleMethodAsync()  
    {  
        // The following line simulates a task-returning asynchronous process.  
        await Task.Delay(1000);  
    }  
}  
```

 <span data-ttu-id="0a87c-143">Stejný ovladač událostí můžete přidat pomocí asynchronní lambdy.</span><span class="sxs-lookup"><span data-stu-id="0a87c-143">You can add the same event handler by using an async lambda.</span></span> <span data-ttu-id="0a87c-144">Chcete-li přidat Tato obslužná rutina, přidejte `async` modifikátor před seznam parametrů lambda, jak ukazuje následující příklad.</span><span class="sxs-lookup"><span data-stu-id="0a87c-144">To add this handler, add an `async` modifier before the lambda parameter list, as the following example shows.</span></span>  
  
```csharp  
public partial class Form1 : Form  
{  
    public Form1()  
    {  
        InitializeComponent();  
        button1.Click += async (sender, e) =>  
        {  
            // ExampleMethodAsync returns a Task.  
            await ExampleMethodAsync();  
            textBox1.Text += "\nControl returned to Click event handler.\n";  
        };  
    }  
  
    async Task ExampleMethodAsync()  
    {  
        // The following line simulates a task-returning asynchronous process.  
        await Task.Delay(1000);  
    }  
}  
```  

 <span data-ttu-id="0a87c-145">Další informace o tom, jak vytvořit a použít asynchronní metody najdete v tématu [asynchronní programování pomocí modifikátoru async a operátoru await](../../../csharp/programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="0a87c-145">For more information about how to create and use async methods, see [Asynchronous Programming with async and await](../../../csharp/programming-guide/concepts/async/index.md).</span></span>  
  
## <a name="lambdas-with-the-standard-query-operators"></a><span data-ttu-id="0a87c-146">Výrazy lambda se standardními operátory dotazu</span><span class="sxs-lookup"><span data-stu-id="0a87c-146">Lambdas with the Standard Query Operators</span></span>  
 <span data-ttu-id="0a87c-147">Mnoho standardní operátory dotazu mít vstupní parametr s typem je jedním z <xref:System.Func%602> rodiny obecných delegátů.</span><span class="sxs-lookup"><span data-stu-id="0a87c-147">Many Standard query operators have an input parameter whose type is one of the <xref:System.Func%602> family of generic delegates.</span></span> <span data-ttu-id="0a87c-148">Tyto delegáty používají parametry typu pro definování počtu a typů vstupních parametrů a návratový typ delegátu.</span><span class="sxs-lookup"><span data-stu-id="0a87c-148">These delegates use type parameters to define the number and types of input parameters, and the return type of the delegate.</span></span> <span data-ttu-id="0a87c-149">`Func`Delegáti jsou velmi užitečné pro zapouzdření uživatelem definované výrazy, které se použijí pro každý prvek v sadě zdrojová data.</span><span class="sxs-lookup"><span data-stu-id="0a87c-149">`Func` delegates are very useful for encapsulating user-defined expressions that are applied to each element in a set of source data.</span></span> <span data-ttu-id="0a87c-150">Zvažte například následující typ delegátu:</span><span class="sxs-lookup"><span data-stu-id="0a87c-150">For example, consider the following delegate type:</span></span>  
  
```csharp  
public delegate TResult Func<TArg0, TResult>(TArg0 arg0)  
```  
  
 <span data-ttu-id="0a87c-151">Delegát se dá vytvořit instance jako `Func<int,bool> myFunc` kde `int` je vstupní parametr a `bool` je návratovou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="0a87c-151">The delegate can be instantiated as `Func<int,bool> myFunc` where `int` is an input parameter and `bool` is the return value.</span></span> <span data-ttu-id="0a87c-152">Vrácená hodnota je vždy určena v posledním parametru typu.</span><span class="sxs-lookup"><span data-stu-id="0a87c-152">The return value is always specified in the last type parameter.</span></span> <span data-ttu-id="0a87c-153">`Func<int, string, bool>`definuje delegáta s dva vstupní parametry, `int` a `string`a návratový typ `bool`.</span><span class="sxs-lookup"><span data-stu-id="0a87c-153">`Func<int, string, bool>` defines a delegate with two input parameters, `int` and `string`, and a return type of `bool`.</span></span> <span data-ttu-id="0a87c-154">Následující `Func` delegáta, při vyvolání, vrátí hodnotu PRAVDA nebo NEPRAVDA označuje, zda vstupní parametr rovna 5:</span><span class="sxs-lookup"><span data-stu-id="0a87c-154">The following `Func` delegate, when it is invoked, will return true or false to indicate whether the input parameter is equal to 5:</span></span>  
  
```csharp  
Func<int, bool> myFunc = x => x == 5;  
bool result = myFunc(4); // returns false of course  
```  
  
 <span data-ttu-id="0a87c-155">Výraz lambda může taky poskytovat, pokud je typ argumentu `Expression<Func>`, například v operátory standardní dotazu, které jsou definovány v System.Linq.Queryable.</span><span class="sxs-lookup"><span data-stu-id="0a87c-155">You can also supply a lambda expression when the argument type is an `Expression<Func>`, for example in the standard query operators that are defined in System.Linq.Queryable.</span></span> <span data-ttu-id="0a87c-156">Pokud zadáte `Expression<Func>` argument, argument lambda se zkompiluje na strom výrazu.</span><span class="sxs-lookup"><span data-stu-id="0a87c-156">When you specify an `Expression<Func>` argument, the lambda will be compiled to an expression tree.</span></span>  
  
 <span data-ttu-id="0a87c-157">Operátor standardní dotaz, <xref:System.Linq.Enumerable.Count%2A> metoda, zobrazí se zde:</span><span class="sxs-lookup"><span data-stu-id="0a87c-157">A standard query operator, the <xref:System.Linq.Enumerable.Count%2A> method, is shown here:</span></span>  
  
```csharp  
int[] numbers = { 5, 4, 1, 3, 9, 8, 6, 7, 2, 0 };  
int oddNumbers = numbers.Count(n => n % 2 == 1);  
```  
  
 <span data-ttu-id="0a87c-158">Kompilátor může odvodit typ vstupního parametru, nebo jej můžete nastavit také explicitně.</span><span class="sxs-lookup"><span data-stu-id="0a87c-158">The compiler can infer the type of the input parameter, or you can also specify it explicitly.</span></span> <span data-ttu-id="0a87c-159">Tento výraz lambda konkrétní počty těchto celých čísel (`n`) které při dělený dva mít zbytek 1.</span><span class="sxs-lookup"><span data-stu-id="0a87c-159">This particular lambda expression counts those integers (`n`) which when divided by two have a remainder of 1.</span></span>  
  
 <span data-ttu-id="0a87c-160">Následující kód vytvoří sekvenci, která obsahuje všechny elementy ve `numbers` pole, které jsou na levé straně 9, protože se jedná o první číslo v pořadí, které nesplňují podmínku:</span><span class="sxs-lookup"><span data-stu-id="0a87c-160">The following line of code produces a sequence that contains all elements in the `numbers` array that are to the left side of the 9 because that's the first number in the sequence that doesn't meet the condition:</span></span>  
  
```csharp  
var firstNumbersLessThan6 = numbers.TakeWhile(n => n < 6);  
```  
  
 <span data-ttu-id="0a87c-161">Tento příklad znázorňuje způsob zadávání většího počtu vstupních parametrů uzavřením do závorek.</span><span class="sxs-lookup"><span data-stu-id="0a87c-161">This example shows how to specify multiple input parameters by enclosing them in parentheses.</span></span> <span data-ttu-id="0a87c-162">Metoda vrátí všechny prvky v poli čísel, dokud není zjištěno číslo, jehož hodnota je nižší než jeho pozice.</span><span class="sxs-lookup"><span data-stu-id="0a87c-162">The method returns all the elements in the numbers array until a number is encountered whose value is less than its position.</span></span> <span data-ttu-id="0a87c-163">Nezaměňujte operátor lambda (`=>`) s operátorem větší než nebo rovna (`>=`).</span><span class="sxs-lookup"><span data-stu-id="0a87c-163">Do not confuse the lambda operator (`=>`) with the greater than or equal operator (`>=`).</span></span>  
  
```csharp  
var firstSmallNumbers = numbers.TakeWhile((n, index) => n >= index);  
```  
  
## <a name="type-inference-in-lambdas"></a><span data-ttu-id="0a87c-164">Odvození typu ve výrazech lambda</span><span class="sxs-lookup"><span data-stu-id="0a87c-164">Type Inference in Lambdas</span></span>  
 <span data-ttu-id="0a87c-165">Při psaní výrazů lambda není často nutné zadat typ pro vstupní parametry, protože kompilátor může odvodit typ na základě hlavní části výrazu lambda, typu delegátu parametru a dalších faktorů, jak je popsáno ve specifikaci jazyka C#.</span><span class="sxs-lookup"><span data-stu-id="0a87c-165">When writing lambdas, you often do not have to specify a type for the input parameters because the compiler can infer the type based on the lambda body, the parameter’s delegate type, and other factors as described in the C# Language Specification.</span></span> <span data-ttu-id="0a87c-166">Pro většinu standardních operátorů pro dotazování je prvním vstupem typ prvků ve zdrojové sekvenci.</span><span class="sxs-lookup"><span data-stu-id="0a87c-166">For most of the standard query operators, the first input is the type of the elements in the source sequence.</span></span> <span data-ttu-id="0a87c-167">Ano, pokud se dotazuje `IEnumerable<Customer>`, pak je potřeba odvodit vstupní proměnné `Customer` objekt, což znamená, máte přístup k jeho metody a vlastnosti:</span><span class="sxs-lookup"><span data-stu-id="0a87c-167">So if you are querying an `IEnumerable<Customer>`, then the input variable is inferred to be a `Customer` object, which means you have access to its methods and properties:</span></span>  
  
```csharp  
customers.Where(c => c.City == "London");  
```  
  
 <span data-ttu-id="0a87c-168">Obecná pravidla pro výrazy lambda jsou následující:</span><span class="sxs-lookup"><span data-stu-id="0a87c-168">The general rules for lambdas are as follows:</span></span>  
  
-   <span data-ttu-id="0a87c-169">Výraz lambda musí obsahovat stejný počet parametrů jako typ delegátu.</span><span class="sxs-lookup"><span data-stu-id="0a87c-169">The lambda must contain the same number of parameters as the delegate type.</span></span>  
  
-   <span data-ttu-id="0a87c-170">Každý vstupní parametr ve výrazu lambda musí být implicitně převoditelný na odpovídající parametr delegátu.</span><span class="sxs-lookup"><span data-stu-id="0a87c-170">Each input parameter in the lambda must be implicitly convertible to its corresponding delegate parameter.</span></span>  
  
-   <span data-ttu-id="0a87c-171">Vrácená hodnota lambda (pokud existuje) musí být implicitně převoditelná na návratový typ delegátu.</span><span class="sxs-lookup"><span data-stu-id="0a87c-171">The return value of the lambda (if any) must be implicitly convertible to the delegate's return type.</span></span>  
  
 <span data-ttu-id="0a87c-172">Výrazy lambda nemají vlastní určený typ, protože systém běžných typů nezná vnitřní pojem „výraz lambda“.</span><span class="sxs-lookup"><span data-stu-id="0a87c-172">Note that lambda expressions in themselves do not have a type because the common type system has no intrinsic concept of "lambda expression."</span></span> <span data-ttu-id="0a87c-173">Někdy je však vhodné hovořit neformálně o „typu“ výrazu lambda.</span><span class="sxs-lookup"><span data-stu-id="0a87c-173">However, it is sometimes convenient to speak informally of the "type" of a lambda expression.</span></span> <span data-ttu-id="0a87c-174">V těchto případech se typ odkazuje na typ delegáta nebo <xref:System.Linq.Expressions.Expression> typ výrazu lambda je převeden.</span><span class="sxs-lookup"><span data-stu-id="0a87c-174">In these cases the type refers to the delegate type or <xref:System.Linq.Expressions.Expression> type to which the lambda expression is converted.</span></span>  
  
## <a name="variable-scope-in-lambda-expressions"></a><span data-ttu-id="0a87c-175">Rozsah proměnné ve výrazech lambda</span><span class="sxs-lookup"><span data-stu-id="0a87c-175">Variable Scope in Lambda Expressions</span></span>  
 <span data-ttu-id="0a87c-176">Lambdas mohou odkazovat na *vnější proměnné* (viz [anonymní metody](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)), které jsou v oboru v metody, která definuje funkci lambda, nebo v oboru v typu, který obsahuje výraz lambda.</span><span class="sxs-lookup"><span data-stu-id="0a87c-176">Lambdas can refer to *outer variables* (see [Anonymous Methods](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)) that are in scope in the method that defines the lambda function, or in scope in the type that contains the lambda expression.</span></span> <span data-ttu-id="0a87c-177">Proměnné, které jsou zachyceny tímto způsobem, jsou uloženy pro použití ve výrazu lambda i v případě, že proměnné by jinak přesáhly rozsah platnosti a bylo by vynuceno uvolnění paměti.</span><span class="sxs-lookup"><span data-stu-id="0a87c-177">Variables that are captured in this manner are stored for use in the lambda expression even if the variables would otherwise go out of scope and be garbage collected.</span></span> <span data-ttu-id="0a87c-178">Vnější proměnná musí být jednoznačně přiřazena dříve, než může být upotřebena ve výrazu lambda.</span><span class="sxs-lookup"><span data-stu-id="0a87c-178">An outer variable must be definitely assigned before it can be consumed in a lambda expression.</span></span> <span data-ttu-id="0a87c-179">Následující příklad znázorňuje tato pravidla:</span><span class="sxs-lookup"><span data-stu-id="0a87c-179">The following example demonstrates these rules:</span></span>  
  
```csharp  
delegate bool D();  
delegate bool D2(int i);  
  
class Test  
{  
    D del;  
    D2 del2;  
    public void TestMethod(int input)  
    {  
        int j = 0;  
        // Initialize the delegates with lambda expressions.  
        // Note access to 2 outer variables.  
        // del will be invoked within this method.  
        del = () => { j = 10;  return j > input; };  
  
        // del2 will be invoked after TestMethod goes out of scope.  
        del2 = (x) => {return x == j; };  
  
        // Demonstrate value of j:  
        // Output: j = 0   
        // The delegate has not been invoked yet.  
        Console.WriteLine("j = {0}", j);        // Invoke the delegate.  
        bool boolResult = del();  
  
        // Output: j = 10 b = True  
        Console.WriteLine("j = {0}. b = {1}", j, boolResult);  
    }  
  
    static void Main()  
    {  
        Test test = new Test();  
        test.TestMethod(5);  
  
        // Prove that del2 still has a copy of  
        // local variable j from TestMethod.  
        bool result = test.del2(10);  
  
        // Output: True  
        Console.WriteLine(result);  
  
        Console.ReadKey();  
    }  
}  
```  
  
 <span data-ttu-id="0a87c-180">Následující pravidla se vztahují na rozsah proměnné ve výrazu lambda:</span><span class="sxs-lookup"><span data-stu-id="0a87c-180">The following rules apply to variable scope in lambda expressions:</span></span>  
  
-   <span data-ttu-id="0a87c-181">Proměnná, která je zachycena, nebude uvolněna z paměti, dokud delegát, který na ni odkazuje, nebude mít oprávnění k uvolňování paměti.</span><span class="sxs-lookup"><span data-stu-id="0a87c-181">A variable that is captured will not be garbage-collected until the delegate that references it becomes eligible for garbage collection.</span></span>  
  
-   <span data-ttu-id="0a87c-182">Proměnné, které jsou představeny v rámci výrazu lambda, nejsou viditelné ve vnější metodě.</span><span class="sxs-lookup"><span data-stu-id="0a87c-182">Variables introduced within a lambda expression are not visible in the outer method.</span></span>  
  
-   <span data-ttu-id="0a87c-183">Výraz lambda nemůže zaznamenat přímo `ref` nebo `out` parametr z metody nadřazených.</span><span class="sxs-lookup"><span data-stu-id="0a87c-183">A lambda expression cannot directly capture a `ref` or `out` parameter from an enclosing method.</span></span>  
  
-   <span data-ttu-id="0a87c-184">Příkaz return ve výrazu lambda nezpůsobí vrácení ohraničující metody.</span><span class="sxs-lookup"><span data-stu-id="0a87c-184">A return statement in a lambda expression does not cause the enclosing method to return.</span></span>  
  
-   <span data-ttu-id="0a87c-185">Nemůže obsahovat výraz lambda `goto` příkaz `break` prohlášení, nebo `continue` příkaz, který je uvnitř funkce lambda, pokud příkaz přechod cíl je mimo blok.</span><span class="sxs-lookup"><span data-stu-id="0a87c-185">A lambda expression cannot contain a `goto` statement, `break` statement, or `continue` statement that is inside the lambda function if the jump statement’s target is outside the block.</span></span> <span data-ttu-id="0a87c-186">Je také chybou mít příkaz skoku mimo blok funkce lambda, pokud je cíl uvnitř bloku.</span><span class="sxs-lookup"><span data-stu-id="0a87c-186">It is also an error to have a jump statement outside the lambda function block if the target is inside the block.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="0a87c-187">Specifikace jazyka C#</span><span class="sxs-lookup"><span data-stu-id="0a87c-187">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="featured-book-chapter"></a><span data-ttu-id="0a87c-188">Doporučená kapitola knihy</span><span class="sxs-lookup"><span data-stu-id="0a87c-188">Featured Book Chapter</span></span>  
 <span data-ttu-id="0a87c-189">[Výrazy Lambda, delegáti a události](http://go.microsoft.com/fwlink/?LinkId=195395) v [C# 3.0 Cookbook, Third Edition: víc než 250 řešení pro programátory v jazyce C# 3.0](http://go.microsoft.com/fwlink/?LinkId=195369)</span><span class="sxs-lookup"><span data-stu-id="0a87c-189">[Delegates, Events, and Lambda Expressions](http://go.microsoft.com/fwlink/?LinkId=195395) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](http://go.microsoft.com/fwlink/?LinkId=195369)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a87c-190">Viz také</span><span class="sxs-lookup"><span data-stu-id="0a87c-190">See Also</span></span>  
 [<span data-ttu-id="0a87c-191">Průvodce programováním v C#</span><span class="sxs-lookup"><span data-stu-id="0a87c-191">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="0a87c-192">LINQ (Language-Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="0a87c-192">LINQ (Language-Integrated Query)</span></span>](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)  
 [<span data-ttu-id="0a87c-193">Anonymní metody</span><span class="sxs-lookup"><span data-stu-id="0a87c-193">Anonymous Methods</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
 [<span data-ttu-id="0a87c-194">je</span><span class="sxs-lookup"><span data-stu-id="0a87c-194">is</span></span>](../../../csharp/language-reference/keywords/is.md)  
 [<span data-ttu-id="0a87c-195">Stromy výrazů</span><span class="sxs-lookup"><span data-stu-id="0a87c-195">Expression Trees</span></span>](http://msdn.microsoft.com/library/fb1d3ed8-d5b0-4211-a71f-dd271529294b)  
 [<span data-ttu-id="0a87c-196">Visual Studio 2008 C# – ukázky (viz ukázkové dotazy LINQ soubory a XQuery programu)</span><span class="sxs-lookup"><span data-stu-id="0a87c-196">Visual Studio 2008 C# Samples (see LINQ Sample Queries files and XQuery program)</span></span>](http://code.msdn.microsoft.com/Visual-Studio-2008-C-d295cdba)  
 [<span data-ttu-id="0a87c-197">Rekurzivní lambda – výrazy</span><span class="sxs-lookup"><span data-stu-id="0a87c-197">Recursive lambda expressions</span></span>](http://go.microsoft.com/fwlink/?LinkId=112395)
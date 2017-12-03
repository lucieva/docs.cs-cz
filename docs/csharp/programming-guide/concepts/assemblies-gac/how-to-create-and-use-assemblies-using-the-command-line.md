---
title: "Postupy: vytvoření a použití sestavení s pomocí příkazového řádku (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 408ddce3-89e3-4e12-8353-34a49beeb72b
caps.latest.revision: "4"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d59988ec4899b4115d8d0fd7172e0c8ff8802378
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-and-use-assemblies-using-the-command-line-c"></a><span data-ttu-id="c8600-102">Postupy: vytvoření a použití sestavení s pomocí příkazového řádku (C#)</span><span class="sxs-lookup"><span data-stu-id="c8600-102">How to: Create and Use Assemblies Using the Command Line (C#)</span></span>
<span data-ttu-id="c8600-103">Sestavení nebo dynamického propojení knihovna (DLL), je propojen s vaším programem za běhu.</span><span class="sxs-lookup"><span data-stu-id="c8600-103">An assembly, or a dynamic linking library (DLL), is linked to your program at run time.</span></span> <span data-ttu-id="c8600-104">Chcete-li ukazují, vytvoření a použití knihovny DLL, zvažte následující scénáře:</span><span class="sxs-lookup"><span data-stu-id="c8600-104">To demonstrate building and using a DLL, consider the following scenario:</span></span>  
  
-   <span data-ttu-id="c8600-105">`MathLibrary.DLL`: Knihovna soubor, který obsahuje metody, která se má volat za běhu.</span><span class="sxs-lookup"><span data-stu-id="c8600-105">`MathLibrary.DLL`: The library file that contains the methods to be called at run time.</span></span> <span data-ttu-id="c8600-106">V tomto příkladu knihovnu DLL obsahuje dvě metody, `Add` a `Multiply`.</span><span class="sxs-lookup"><span data-stu-id="c8600-106">In this example, the DLL contains two methods, `Add` and `Multiply`.</span></span>  
  
-   <span data-ttu-id="c8600-107">`Add`: Zdrojový soubor, který obsahuje metodu `Add`.</span><span class="sxs-lookup"><span data-stu-id="c8600-107">`Add`: The source file that contains the method `Add`.</span></span> <span data-ttu-id="c8600-108">Vrátí součet její parametry.</span><span class="sxs-lookup"><span data-stu-id="c8600-108">It returns the sum of its parameters.</span></span> <span data-ttu-id="c8600-109">Třída `AddClass` obsahující metodu `Add` je členem oboru názvů `UtilityMethods`.</span><span class="sxs-lookup"><span data-stu-id="c8600-109">The class `AddClass` that contains the method `Add` is a member of the namespace `UtilityMethods`.</span></span>  
  
-   <span data-ttu-id="c8600-110">`Mult`: Zdrojový kód, který obsahuje metodu `Multiply`.</span><span class="sxs-lookup"><span data-stu-id="c8600-110">`Mult`: The source code that contains the method `Multiply`.</span></span> <span data-ttu-id="c8600-111">Vrátí součin jeho parametry.</span><span class="sxs-lookup"><span data-stu-id="c8600-111">It returns the product of its parameters.</span></span> <span data-ttu-id="c8600-112">Třída `MultiplyClass` obsahující metodu `Multiply` je také členem oboru názvů `UtilityMethods`.</span><span class="sxs-lookup"><span data-stu-id="c8600-112">The class `MultiplyClass` that contains the method `Multiply` is also a member of the namespace `UtilityMethods`.</span></span>  
  
-   <span data-ttu-id="c8600-113">`TestCode`: Soubor, který obsahuje `Main` metoda.</span><span class="sxs-lookup"><span data-stu-id="c8600-113">`TestCode`: The file that contains the `Main` method.</span></span> <span data-ttu-id="c8600-114">Metody v souboru DLL používá k výpočtu součet a produktu argumenty běhu.</span><span class="sxs-lookup"><span data-stu-id="c8600-114">It uses the methods in the DLL file to calculate the sum and the product of the run-time arguments.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8600-115">Příklad</span><span class="sxs-lookup"><span data-stu-id="c8600-115">Example</span></span>  
  
```csharp  
// File: Add.cs   
namespace UtilityMethods  
{  
    public class AddClass   
    {  
        public static long Add(long i, long j)   
        {   
            return (i + j);  
        }  
    }  
}  
```  
  
```csharp  
// File: Mult.cs  
namespace UtilityMethods   
{  
    public class MultiplyClass  
    {  
        public static long Multiply(long x, long y)   
        {  
            return (x * y);   
        }  
    }  
}  
```  
  
```csharp  
// File: TestCode.cs  
  
using UtilityMethods;  
  
class TestCode  
{  
    static void Main(string[] args)   
    {  
        System.Console.WriteLine("Calling methods from MathLibrary.DLL:");  
  
        if (args.Length != 2)  
        {  
            System.Console.WriteLine("Usage: TestCode <num1> <num2>");  
            return;  
        }  
  
        long num1 = long.Parse(args[0]);  
        long num2 = long.Parse(args[1]);  
  
        long sum = AddClass.Add(num1, num2);  
        long product = MultiplyClass.Multiply(num1, num2);  
  
        System.Console.WriteLine("{0} + {1} = {2}", num1, num2, sum);  
        System.Console.WriteLine("{0} * {1} = {2}", num1, num2, product);  
    }  
}  
/* Output (assuming 1234 and 5678 are entered as command-line arguments):  
    Calling methods from MathLibrary.DLL:  
    1234 + 5678 = 6912  
    1234 * 5678 = 7006652          
*/  
```  
  
 <span data-ttu-id="c8600-116">Tento soubor obsahuje algoritmus, který používá metody DLL `Add` a `Multiply`.</span><span class="sxs-lookup"><span data-stu-id="c8600-116">This file contains the algorithm that uses the DLL methods, `Add` and `Multiply`.</span></span> <span data-ttu-id="c8600-117">Začíná Analýza argumentů zadali z příkazového řádku, `num1` a `num2`.</span><span class="sxs-lookup"><span data-stu-id="c8600-117">It starts with parsing the arguments entered from the command line, `num1` and `num2`.</span></span> <span data-ttu-id="c8600-118">Pak se vypočítává součet `Add` metoda na `AddClass` třídy a produktu pomocí `Multiply` metoda na `MultiplyClass` – třída.</span><span class="sxs-lookup"><span data-stu-id="c8600-118">Then it calculates the sum by using the `Add` method on the `AddClass` class, and the product by using the `Multiply` method on the `MultiplyClass` class.</span></span>  
  
 <span data-ttu-id="c8600-119">Všimněte si, že `using` – direktiva na začátku souboru umožňuje používat třídu nekvalifikované názvy tak, aby odkazovaly metody DLL při kompilaci, následujícím způsobem:</span><span class="sxs-lookup"><span data-stu-id="c8600-119">Notice that the `using` directive at the beginning of the file enables you to use the unqualified class names to reference the DLL methods at compile time, as follows:</span></span>  
  
```csharp  
MultiplyClass.Multiply(num1, num2);  
```  
  
 <span data-ttu-id="c8600-120">Jinak budete muset použít plně kvalifikované názvy následujícím způsobem:</span><span class="sxs-lookup"><span data-stu-id="c8600-120">Otherwise, you have to use the fully qualified names, as follows:</span></span>  
  
```csharp  
UtilityMethods.MultiplyClass.Multiply(num1, num2);  
```  
  
## <a name="execution"></a><span data-ttu-id="c8600-121">Spuštění</span><span class="sxs-lookup"><span data-stu-id="c8600-121">Execution</span></span>  
 <span data-ttu-id="c8600-122">Chcete-li spustit program, zadejte název souboru EXE, za nímž následuje dvou čísel, následujícím způsobem:</span><span class="sxs-lookup"><span data-stu-id="c8600-122">To run the program, enter the name of the EXE file, followed by two numbers, as follows:</span></span>  
  
 `TestCode 1234 5678`  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c8600-123">Probíhá kompilace kódu</span><span class="sxs-lookup"><span data-stu-id="c8600-123">Compiling the Code</span></span>  
 <span data-ttu-id="c8600-124">K vytvoření souboru `MathLibrary.DLL`, zkompilovat dva soubory `Add` a `Mult` pomocí následující příkazový řádek.</span><span class="sxs-lookup"><span data-stu-id="c8600-124">To build the file `MathLibrary.DLL`, compile the two files `Add` and `Mult` by using the following command line.</span></span>  
  
```csharp  
csc /target:library /out:MathLibrary.DLL Add.cs Mult.cs  
```  
  
 <span data-ttu-id="c8600-125">[/Target: library](../../../../csharp/language-reference/compiler-options/target-library-compiler-option.md) – možnost kompilátoru říká kompilátoru výstup knihovny DLL místo soubor EXE.</span><span class="sxs-lookup"><span data-stu-id="c8600-125">The [/target:library](../../../../csharp/language-reference/compiler-options/target-library-compiler-option.md) compiler option tells the compiler to output a DLL instead of an EXE file.</span></span> <span data-ttu-id="c8600-126">[/Out](../../../../csharp/language-reference/compiler-options/out-compiler-option.md) – možnost kompilátoru a potom podle názvu souboru se používá k určení názvu souboru DLL.</span><span class="sxs-lookup"><span data-stu-id="c8600-126">The [/out](../../../../csharp/language-reference/compiler-options/out-compiler-option.md) compiler option followed by a file name is used to specify the DLL file name.</span></span> <span data-ttu-id="c8600-127">Jinak, kompilátor použije první soubor (`Add.cs`) jako název knihovnu DLL.</span><span class="sxs-lookup"><span data-stu-id="c8600-127">Otherwise, the compiler uses the first file (`Add.cs`) as the name of the DLL.</span></span>  
  
 <span data-ttu-id="c8600-128">K vytvoření spustitelný soubor `TestCode.exe`, použijte následující příkazový řádek:</span><span class="sxs-lookup"><span data-stu-id="c8600-128">To build the executable file, `TestCode.exe`, use the following command line:</span></span>  
  
```csharp  
csc /out:TestCode.exe /reference:MathLibrary.DLL TestCode.cs  
```  
  
 <span data-ttu-id="c8600-129">**/Out** – možnost kompilátoru říká kompilátoru do výstupního souboru EXE a určuje název souboru výstupního souboru (`TestCode.exe`).</span><span class="sxs-lookup"><span data-stu-id="c8600-129">The **/out** compiler option tells the compiler to output an EXE file and specifies the name of the output file (`TestCode.exe`).</span></span> <span data-ttu-id="c8600-130">Tato možnost kompilátoru je volitelné.</span><span class="sxs-lookup"><span data-stu-id="c8600-130">This compiler option is optional.</span></span> <span data-ttu-id="c8600-131">[/Reference](../../../../csharp/language-reference/compiler-options/reference-compiler-option.md) – možnost kompilátoru Určuje soubor knihovny DLL nebo soubory, které tento program používá.</span><span class="sxs-lookup"><span data-stu-id="c8600-131">The [/reference](../../../../csharp/language-reference/compiler-options/reference-compiler-option.md) compiler option specifies the DLL file or files that this program uses.</span></span> <span data-ttu-id="c8600-132">Další informace najdete v tématu [/reference](../../../../csharp/language-reference/compiler-options/reference-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="c8600-132">For more information, see [/reference](../../../../csharp/language-reference/compiler-options/reference-compiler-option.md).</span></span>  
  
 <span data-ttu-id="c8600-133">Další informace o sestavení z příkazového řádku najdete v tématu [vytváření pomocí příkazového řádku csc.exe](../../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="c8600-133">For more information about building from the command line, see [Command-line Building With csc.exe](../../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8600-134">Viz také</span><span class="sxs-lookup"><span data-stu-id="c8600-134">See Also</span></span>  
 [<span data-ttu-id="c8600-135">Průvodce programováním v C#</span><span class="sxs-lookup"><span data-stu-id="c8600-135">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="c8600-136">Sestavení a globální mezipaměti sestavení (C#)</span><span class="sxs-lookup"><span data-stu-id="c8600-136">Assemblies and the Global Assembly Cache (C#)</span></span>](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md)  
 [<span data-ttu-id="c8600-137">Vytvoření třídy k umístění funkcí DLL</span><span class="sxs-lookup"><span data-stu-id="c8600-137">Creating a Class to Hold DLL Functions</span></span>](../../../../framework/interop/creating-a-class-to-hold-dll-functions.md)
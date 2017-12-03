---
title: "Testování C# s použitím Mstestu a .NET Core jednotky"
description: "Další koncepty test jednotky v C# a .NET Core prostřednictvím interaktivní prostředí sestavování podrobné ukázkové řešení pomocí testovacích dotnet a Mstestu."
keywords: Mstestu, .NET, .NET Core
author: ncarandini
ms.author: wiwagn
ms.date: 09/08/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: ed447641-3e85-4e50-b7ed-004630048a3e
ms.openlocfilehash: 2915c2f4b18b9e9d03915c2f17cfc96d4f401c09
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="unit-testing-c-with-mstest-and-net-core"></a><span data-ttu-id="7b193-104">Testování C# s použitím Mstestu a .NET Core jednotky</span><span class="sxs-lookup"><span data-stu-id="7b193-104">Unit testing C# with MSTest and .NET Core</span></span>

<span data-ttu-id="7b193-105">Tento kurz vás provede interaktivní prostředí vytváření ukázkové řešení podrobné další koncepty testování částí.</span><span class="sxs-lookup"><span data-stu-id="7b193-105">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="7b193-106">Pokud chcete postupovat v kurzu pomocí předdefinovaných řešení, [zobrazení nebo stažení ukázkového kódu](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/) před zahájením.</span><span class="sxs-lookup"><span data-stu-id="7b193-106">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/) before you begin.</span></span> <span data-ttu-id="7b193-107">Pokyny ke stažení najdete v tématu [ukázky a výukové programy](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="7b193-107">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

### <a name="creating-the-source-project"></a><span data-ttu-id="7b193-108">Vytvoření projektu zdroje</span><span class="sxs-lookup"><span data-stu-id="7b193-108">Creating the source project</span></span>

<span data-ttu-id="7b193-109">Otevřete okno prostředí.</span><span class="sxs-lookup"><span data-stu-id="7b193-109">Open a shell window.</span></span> <span data-ttu-id="7b193-110">Vytvořte adresář s názvem *testování pomocí dotnet – testování* pro uložení řešení.</span><span class="sxs-lookup"><span data-stu-id="7b193-110">Create a directory called *unit-testing-using-dotnet-test* to hold the solution.</span></span> <span data-ttu-id="7b193-111">Uvnitř tohoto nového adresáře, spusťte [ `dotnet new sln` ](../tools/dotnet-new.md) vytvořit nový soubor řešení pro knihovny tříd a k testovacímu projektu.</span><span class="sxs-lookup"><span data-stu-id="7b193-111">Inside this new directory, run [`dotnet new sln`](../tools/dotnet-new.md) to create a new solution file for the class library and the test project.</span></span> <span data-ttu-id="7b193-112">Dále vytvořte *PrimeService* adresáře.</span><span class="sxs-lookup"><span data-stu-id="7b193-112">Next, create a *PrimeService* directory.</span></span> <span data-ttu-id="7b193-113">Následující obrys doposud ukazuje strukturu adresáře a souboru:</span><span class="sxs-lookup"><span data-stu-id="7b193-113">The following outline shows the directory and file structure thus far:</span></span>

```
/unit-testing-using-mstest
    unit-testing-using-mstest.sln
    /PrimeService
```

<span data-ttu-id="7b193-114">Ujistěte se, *PrimeService* aktuální adresář a spusťte [ `dotnet new classlib` ](../tools/dotnet-new.md) a vytvořte tak projekt zdroje.</span><span class="sxs-lookup"><span data-stu-id="7b193-114">Make *PrimeService* the current directory and run [`dotnet new classlib`](../tools/dotnet-new.md) to create the source project.</span></span> <span data-ttu-id="7b193-115">Přejmenování *Class1.cs* k *PrimeService.cs*.</span><span class="sxs-lookup"><span data-stu-id="7b193-115">Rename *Class1.cs* to *PrimeService.cs*.</span></span> <span data-ttu-id="7b193-116">Použití vývoje řízeného testováním (TDD), vytvořte na selhání implementace `PrimeService` třídy:</span><span class="sxs-lookup"><span data-stu-id="7b193-116">To use test-driven development (TDD), you create a failing implementation of the `PrimeService` class:</span></span>

```csharp
using System;

namespace Prime.Services
{
    public class PrimeService
    {
        public bool IsPrime(int candidate) 
        {
            throw new NotImplementedException("Please create a test first");
        } 
    }
}
```

<span data-ttu-id="7b193-117">Změna adresáře zpět do *jednotky – testování pomocí mstestu* adresáře.</span><span class="sxs-lookup"><span data-stu-id="7b193-117">Change the directory back to the *unit-testing-using-mstest* directory.</span></span> <span data-ttu-id="7b193-118">Spustit [ `dotnet sln add PrimeService/PrimeService.csproj` ](../tools/dotnet-sln.md) přidání projektu knihovny tříd do řešení.</span><span class="sxs-lookup"><span data-stu-id="7b193-118">Run [`dotnet sln add PrimeService/PrimeService.csproj`](../tools/dotnet-sln.md) to add the class library project to the solution.</span></span> 

### <a name="creating-the-test-project"></a><span data-ttu-id="7b193-119">Vytvoření projektu testů</span><span class="sxs-lookup"><span data-stu-id="7b193-119">Creating the test project</span></span>

<span data-ttu-id="7b193-120">Dále vytvořte *PrimeService.Tests* adresáře.</span><span class="sxs-lookup"><span data-stu-id="7b193-120">Next, create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="7b193-121">Zobrazí následující osnova adresářovou strukturu:</span><span class="sxs-lookup"><span data-stu-id="7b193-121">The following outline shows the directory structure:</span></span>

```
/unit-testing-using-mstest
    unit-testing-using-mstest.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

<span data-ttu-id="7b193-122">Ujistěte se, *PrimeService.Tests* adresář aktuální adresář a vytvoření nového projektu pomocí [ `dotnet new mstest` ](../tools/dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="7b193-122">Make the *PrimeService.Tests* directory the current directory and create a new project using [`dotnet new mstest`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="7b193-123">Nový příkaz dotnet vytvoří testovací projekt, který používá Mstestu jako knihovně testu.</span><span class="sxs-lookup"><span data-stu-id="7b193-123">The dotnet new command creates a test project that uses MStest as the test library.</span></span> <span data-ttu-id="7b193-124">Nástroj test runner v nakonfiguruje vygenerované šablony *PrimeServiceTests.csproj* souboru:</span><span class="sxs-lookup"><span data-stu-id="7b193-124">The generated template configures the test runner in the *PrimeServiceTests.csproj* file:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.3.0" />
  <PackageReference Include="MSTest.TestAdapter" Version="1.1.18" />
  <PackageReference Include="MSTest.TestFramework" Version="1.1.18" />
</ItemGroup>
```

<span data-ttu-id="7b193-125">K testovacímu projektu vyžaduje další balíčky k vytváření a spouštění testování částí.</span><span class="sxs-lookup"><span data-stu-id="7b193-125">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="7b193-126">`dotnet new`v předchozím kroku přidat testovat Mstestu SDK, Mstestu framework a runner Mstestu.</span><span class="sxs-lookup"><span data-stu-id="7b193-126">`dotnet new` in the previous step added the MSTest SDK, the MSTest test framework, and the MSTest runner.</span></span> <span data-ttu-id="7b193-127">Nyní přidejte `PrimeService` knihovny tříd jako další závislosti do projektu.</span><span class="sxs-lookup"><span data-stu-id="7b193-127">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="7b193-128">Použití [ `dotnet add reference` ](../tools/dotnet-add-reference.md) příkaz:</span><span class="sxs-lookup"><span data-stu-id="7b193-128">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```
dotnet add reference ../PrimeService/PrimeService.csproj
```

<span data-ttu-id="7b193-129">Zobrazí celý soubor v [ukázky úložiště](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService.Tests.csproj) na Githubu.</span><span class="sxs-lookup"><span data-stu-id="7b193-129">You can see the entire file in the [samples repository](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService.Tests.csproj) on GitHub.</span></span>

<span data-ttu-id="7b193-130">Zobrazí následující osnova rozložení konečné řešení:</span><span class="sxs-lookup"><span data-stu-id="7b193-130">The following outline shows the final solution layout:</span></span>

```
/unit-testing-using-mstest
    unit-testing-using-mstest.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
        Test Source Files
        PrimeServiceTests.csproj
```

<span data-ttu-id="7b193-131">Spuštění [ `dotnet sln add .\PrimeService.Tests\PrimeService.Tests.csproj` ](../tools/dotnet-sln.md) v *testování pomocí dotnet – testování* adresáře.</span><span class="sxs-lookup"><span data-stu-id="7b193-131">Execute [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.csproj`](../tools/dotnet-sln.md) in the *unit-testing-using-dotnet-test* directory.</span></span> 

## <a name="creating-the-first-test"></a><span data-ttu-id="7b193-132">Vytvoření prvního testu</span><span class="sxs-lookup"><span data-stu-id="7b193-132">Creating the first test</span></span>

<span data-ttu-id="7b193-133">Volá TDD přístup pro zápis jeden selhání test, což předat a zopakováním postupu.</span><span class="sxs-lookup"><span data-stu-id="7b193-133">The TDD approach calls for writing one failing test, making it pass, then repeating the process.</span></span> <span data-ttu-id="7b193-134">Odebrat *UnitTest1.cs* z *PrimeService.Tests* adresáře a vytvořte nový soubor C# s s názvem *PrimeService_IsPrimeShould.cs* s následujícím obsahem:</span><span class="sxs-lookup"><span data-stu-id="7b193-134">Remove *UnitTest1.cs* from the *PrimeService.Tests* directory and create a new C# file named *PrimeService_IsPrimeShould.cs* with the following content:</span></span>

```csharp
using Microsoft.VisualStudio.TestTools.UnitTesting;
using Prime.Services;

namespace Prime.UnitTests.Services
{
    [TestClass]
    public class PrimeService_IsPrimeShould
    {
        private readonly PrimeService _primeService;

        public PrimeService_IsPrimeShould()
        {
            _primeService = new PrimeService();
        }

        [TestMethod]
        public void ReturnFalseGivenValueOf1()
        {
            var result = _primeService.IsPrime(1);

            Assert.IsFalse(result, "1 should not be prime");
        }
    }
}
```

<span data-ttu-id="7b193-135">`[TestClass]` Atribut označuje třídu, která obsahuje testování částí.</span><span class="sxs-lookup"><span data-stu-id="7b193-135">The `[TestClass]` attribute denotes a class that contains unit tests.</span></span> <span data-ttu-id="7b193-136">`[TestMethod]` Atribut uvádí, že je metoda metodou test.</span><span class="sxs-lookup"><span data-stu-id="7b193-136">The `[TestMethod]` attribute indicates a method is a test method.</span></span> 

<span data-ttu-id="7b193-137">Uložte tento soubor a spusťte [ `dotnet test` ](../tools/dotnet-test.md) vytvářet testy a knihovny tříd a poté spusťte testy.</span><span class="sxs-lookup"><span data-stu-id="7b193-137">Save this file and execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="7b193-138">Nástroj test runner Mstestu obsahuje vstupní bod programu ke spuštění testů.</span><span class="sxs-lookup"><span data-stu-id="7b193-138">The MSTest test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="7b193-139">`dotnet test`Spustí nástroj test runner pomocí projektu testů jednotek, které jste vytvořili.</span><span class="sxs-lookup"><span data-stu-id="7b193-139">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="7b193-140">Test se nezdaří.</span><span class="sxs-lookup"><span data-stu-id="7b193-140">Your test fails.</span></span> <span data-ttu-id="7b193-141">Nevytvořili jste ještě implementace.</span><span class="sxs-lookup"><span data-stu-id="7b193-141">You haven't created the implementation yet.</span></span> <span data-ttu-id="7b193-142">Ujistěte se, tento test předat napsáním kód nejjednodušší `PrimeService` třídu, která funguje:</span><span class="sxs-lookup"><span data-stu-id="7b193-142">Make this test pass by writing the simplest code in the `PrimeService` class that works:</span></span>

```csharp
public bool IsPrime(int candidate)
{
    if (candidate == 1)
    {
        return false;
    }
    throw new NotImplementedException("Please create a test first");
}
```

<span data-ttu-id="7b193-143">V *jednotky – testování pomocí mstestu* spusťte `dotnet test` znovu.</span><span class="sxs-lookup"><span data-stu-id="7b193-143">In the *unit-testing-using-mstest* directory, run `dotnet test` again.</span></span> <span data-ttu-id="7b193-144">`dotnet test` Příkaz spustí sestavení pro `PrimeService` projektu a pak `PrimeService.Tests` projektu.</span><span class="sxs-lookup"><span data-stu-id="7b193-144">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="7b193-145">Po sestavení obou projektů, spustí se tento jeden test.</span><span class="sxs-lookup"><span data-stu-id="7b193-145">After building both projects, it runs this single test.</span></span> <span data-ttu-id="7b193-146">Pak předá.</span><span class="sxs-lookup"><span data-stu-id="7b193-146">It passes.</span></span>

## <a name="adding-more-features"></a><span data-ttu-id="7b193-147">Přidání další funkce</span><span class="sxs-lookup"><span data-stu-id="7b193-147">Adding more features</span></span>

<span data-ttu-id="7b193-148">Teď, když jste udělali jeden testovací předání, je čas zapsat informace.</span><span class="sxs-lookup"><span data-stu-id="7b193-148">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="7b193-149">Existuje několik dalších jednoduchý případů pro prvočísel: 0, -1.</span><span class="sxs-lookup"><span data-stu-id="7b193-149">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="7b193-150">Můžete přidat nové testování pomocí `[TestMethod]` atribut, ale které rychle stane zdlouhavé.</span><span class="sxs-lookup"><span data-stu-id="7b193-150">You could add new tests with the `[TestMethod]` attribute, but that quickly becomes tedious.</span></span> <span data-ttu-id="7b193-151">Existují další Mstestu atributy, které vám umožní zápisu sada testů, podobně jako.</span><span class="sxs-lookup"><span data-stu-id="7b193-151">There are other MSTest attributes that enable you to write a suite of similar tests.</span></span>  <span data-ttu-id="7b193-152">A `[DataTestMethod]`atribut představuje sada testů, které provést stejný kód, ale mají jinou vstupní argumenty.</span><span class="sxs-lookup"><span data-stu-id="7b193-152">A `[DataTestMethod]`attribute represents a suite of tests that execute the same code but have different input arguments.</span></span> <span data-ttu-id="7b193-153">Můžete použít `[DataRow]` atribut zadat hodnoty pro tyto vstupy.</span><span class="sxs-lookup"><span data-stu-id="7b193-153">You can use the `[DataRow]` attribute to specify values for those inputs.</span></span>

<span data-ttu-id="7b193-154">Místo vytváření nové testů, platí tyto dva atributy pro vytvoření testu jedné řízených daty.</span><span class="sxs-lookup"><span data-stu-id="7b193-154">Instead of creating new tests, apply these two attributes to create a single data driven test.</span></span> <span data-ttu-id="7b193-155">Test řízených daty je metoda, která porovná několik hodnoty menší než dva, což je s nejnižším číslem prime::</span><span class="sxs-lookup"><span data-stu-id="7b193-155">The data driven test is a method that tests several values less than two, which is the lowest prime number: :</span></span>

[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]

<span data-ttu-id="7b193-156">Spustit `dotnet test`, a dvě z nich testy nezdaří.</span><span class="sxs-lookup"><span data-stu-id="7b193-156">Run `dotnet test`, and two of these tests fail.</span></span> <span data-ttu-id="7b193-157">Chcete-li všechny testy průchodu, změnit `if` klauzule na začátku metody:</span><span class="sxs-lookup"><span data-stu-id="7b193-157">To make all of the tests pass, change the `if` clause at the beginning of the method:</span></span>

```csharp
if (candidate < 2)
```

<span data-ttu-id="7b193-158">Pokračujte k iteraci v přidáním další testy, další teorií a další kód v knihovně hlavní.</span><span class="sxs-lookup"><span data-stu-id="7b193-158">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="7b193-159">Máte [dokončení verzi testy](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs) a [dokončení implementace knihovny](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService/PrimeService.cs).</span><span class="sxs-lookup"><span data-stu-id="7b193-159">You have the [finished version of the tests](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs) and the [complete implementation of the library](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService/PrimeService.cs).</span></span>

<span data-ttu-id="7b193-160">Když jste sestavili malé knihovny a sadu testů jednotek pro danou knihovnu.</span><span class="sxs-lookup"><span data-stu-id="7b193-160">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="7b193-161">Řešení si strukturovaná, tak, aby přidání nové balíčky a testy je součástí normálním pracovním postupu.</span><span class="sxs-lookup"><span data-stu-id="7b193-161">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="7b193-162">Jste soustředí většinu čas a úsilí na řešení cílů aplikace.</span><span class="sxs-lookup"><span data-stu-id="7b193-162">You've concentrated most of your time and effort on solving the goals of the application.</span></span>
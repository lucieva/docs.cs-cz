---
title: "Cílové rozhraní"
description: "Další informace o cílové rozhraní pro aplikace .NET Core a knihovny."
author: richlander
ms.author: mairaw
ms.date: 09/22/2017
ms.topic: article
ms.custom: updateeachrelease
ms.prod: .net
ms.technology: dotnet-standard
ms.openlocfilehash: 20152a951f11b1b923209b56b31663a9a8a81587
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="target-frameworks"></a><span data-ttu-id="d2a3f-103">Cílové rozhraní</span><span class="sxs-lookup"><span data-stu-id="d2a3f-103">Target frameworks</span></span>

<span data-ttu-id="d2a3f-104">K identifikaci rozhraní v aplikaci nebo knihovna určujete sadu rozhraní API, které chcete zpřístupnit aplikace nebo knihovny.</span><span class="sxs-lookup"><span data-stu-id="d2a3f-104">When you target a framework in an app or library, you're specifying the set of APIs that you'd like to make available to the app or library.</span></span> <span data-ttu-id="d2a3f-105">Určete cílové rozhraní v souboru projektu pomocí cílový Framework Monikery (TFMs).</span><span class="sxs-lookup"><span data-stu-id="d2a3f-105">You specify the target framework in your project file using Target Framework Monikers (TFMs).</span></span>

<span data-ttu-id="d2a3f-106">Aplikace nebo knihovny, můžete vybrat verzi [.NET Standard](~/docs/standard/net-standard.md).</span><span class="sxs-lookup"><span data-stu-id="d2a3f-106">An app or library can target a version of [.NET Standard](~/docs/standard/net-standard.md).</span></span> <span data-ttu-id="d2a3f-107">Verze rozhraní .NET standardní představují standardizované sadu rozhraní API přes všechny implementace rozhraní .NET.</span><span class="sxs-lookup"><span data-stu-id="d2a3f-107">.NET Standard versions represent standardized sets of APIs across all .NET implementations.</span></span> <span data-ttu-id="d2a3f-108">Například můžete knihovnu zacílit .NET Standard 1.6 a získat přístup k rozhraní API této funkce v .NET Core a rozhraní .NET Framework pomocí stejné základu kódu.</span><span class="sxs-lookup"><span data-stu-id="d2a3f-108">For example, a library can target .NET Standard 1.6 and gain access to APIs that function across .NET Core and .NET Framework using the same codebase.</span></span>

<span data-ttu-id="d2a3f-109">Aplikace nebo knihovny, můžete také vybrat konkrétní implementace rozhraní .NET k získání přístupu k rozhraní API pro konkrétní implementaci.</span><span class="sxs-lookup"><span data-stu-id="d2a3f-109">An app or library can also target a specific .NET implementation to gain access to implementation-specific APIs.</span></span> <span data-ttu-id="d2a3f-110">Například aplikace, která cílí Xamarin.iOS (například `Xamarin.iOS10`) získá přístup k rozhraní API pro zadaný Xamarin iOS obálek pro iOS 10 nebo aplikaci, která cílí na univerzální platformu Windows (UPW, `uap10.0`) má přístup k rozhraní API, která kompilace pro zařízení se systémem Windows 10.</span><span class="sxs-lookup"><span data-stu-id="d2a3f-110">For example, an app that targets Xamarin.iOS (for example, `Xamarin.iOS10`) gets access to Xamarin-provided iOS API wrappers for iOS 10, or an app that targets the Universal Windows Platform (UWP, `uap10.0`) has access to APIs that compile for devices that run Windows 10.</span></span>

<span data-ttu-id="d2a3f-111">Pro některé cílové rozhraní (například rozhraní .NET Framework) rozhraní API jsou definované sestavení, že rozhraní nainstaluje v systému a může zahrnovat aplikační rozhraní API (například ASP.NET).</span><span class="sxs-lookup"><span data-stu-id="d2a3f-111">For some target frameworks (for example, the .NET Framework), the APIs are defined by the assemblies that the framework installs on a system and may include application framework APIs (for example, ASP.NET).</span></span>

<span data-ttu-id="d2a3f-112">Na základě balíčku cílové rozhraní (například .NET Standard a .NET Core) rozhraní API definováno balíčky součástí aplikace nebo knihovny.</span><span class="sxs-lookup"><span data-stu-id="d2a3f-112">For package-based target frameworks (for example, .NET Standard and .NET Core), the APIs are defined by the packages included in the app or library.</span></span> <span data-ttu-id="d2a3f-113">A *metapackage* je balíčku NuGet, který nemá žádný obsah samostatně, ale je seznam závislosti (dalších balíčků).</span><span class="sxs-lookup"><span data-stu-id="d2a3f-113">A *metapackage* is a NuGet package that has no content of its own but is a list of dependencies (other packages).</span></span> <span data-ttu-id="d2a3f-114">Na základě balíčku cílové rozhraní NuGet implicitně určuje metapackage, který odkazuje na všechny balíčky, které společně tvoří rozhraní.</span><span class="sxs-lookup"><span data-stu-id="d2a3f-114">A NuGet package-based target framework implicitly specifies a metapackage that references all the packages that together make up the framework.</span></span>

## <a name="latest-target-framework-versions"></a><span data-ttu-id="d2a3f-115">Nejnovější target framework verze</span><span class="sxs-lookup"><span data-stu-id="d2a3f-115">Latest target framework versions</span></span>

<span data-ttu-id="d2a3f-116">Následující tabulka definuje nejběžnější cílové rozhraní, jak se odkazuje a kterou verzi [.NET Standard](~/docs/standard/net-standard.md) implementace.</span><span class="sxs-lookup"><span data-stu-id="d2a3f-116">The following table defines the most common target frameworks, how they're referenced, and which version of the [.NET Standard](~/docs/standard/net-standard.md) they implement.</span></span> <span data-ttu-id="d2a3f-117">Tyto target framework verze jsou nejnovější stabilní verze.</span><span class="sxs-lookup"><span data-stu-id="d2a3f-117">These target framework versions are the latest stable versions.</span></span> <span data-ttu-id="d2a3f-118">Předběžných verzí se nezobrazí.</span><span class="sxs-lookup"><span data-stu-id="d2a3f-118">Pre-release versions aren't shown.</span></span> <span data-ttu-id="d2a3f-119">Cílový Framework Přezdívka (TFM) je standardizovaná formát tokenu pro zadání cílové rozhraní aplikace .NET nebo knihovny.</span><span class="sxs-lookup"><span data-stu-id="d2a3f-119">A Target Framework Moniker (TFM) is a standardized token format for specifying the target framework of a .NET app or library.</span></span> 

| <span data-ttu-id="d2a3f-120">Cílová architektura</span><span class="sxs-lookup"><span data-stu-id="d2a3f-120">Target Framework</span></span>      | <span data-ttu-id="d2a3f-121">Nejnovější verzi</span><span class="sxs-lookup"><span data-stu-id="d2a3f-121">Latest Version</span></span> | <span data-ttu-id="d2a3f-122">Cílový Framework Přezdívka (TFM)</span><span class="sxs-lookup"><span data-stu-id="d2a3f-122">Target Framework Moniker (TFM)</span></span> | <span data-ttu-id="d2a3f-123">Implementováno</span><span class="sxs-lookup"><span data-stu-id="d2a3f-123">Implemented</span></span> <br/> <span data-ttu-id="d2a3f-124">Standardní verze rozhraní .NET</span><span class="sxs-lookup"><span data-stu-id="d2a3f-124">.NET Standard Version</span></span> |
| :-------------------: | :------------: | :----------------------------: | :-------------------------------------: |
| <span data-ttu-id="d2a3f-125">Standardní rozhraní .NET</span><span class="sxs-lookup"><span data-stu-id="d2a3f-125">.NET Standard</span></span>         | <span data-ttu-id="d2a3f-126">2.0</span><span class="sxs-lookup"><span data-stu-id="d2a3f-126">2.0</span></span>            | <span data-ttu-id="d2a3f-127">netstandard2.0</span><span class="sxs-lookup"><span data-stu-id="d2a3f-127">netstandard2.0</span></span>                 | <span data-ttu-id="d2a3f-128">Není k dispozici</span><span class="sxs-lookup"><span data-stu-id="d2a3f-128">N/A</span></span>                                     |
| <span data-ttu-id="d2a3f-129">Aplikace .NET core</span><span class="sxs-lookup"><span data-stu-id="d2a3f-129">.NET Core Application</span></span> | <span data-ttu-id="d2a3f-130">2.0</span><span class="sxs-lookup"><span data-stu-id="d2a3f-130">2.0</span></span>            | <span data-ttu-id="d2a3f-131">netcoreapp2.0</span><span class="sxs-lookup"><span data-stu-id="d2a3f-131">netcoreapp2.0</span></span>                  | <span data-ttu-id="d2a3f-132">2.0</span><span class="sxs-lookup"><span data-stu-id="d2a3f-132">2.0</span></span>                                     |
| <span data-ttu-id="d2a3f-133">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="d2a3f-133">.NET Framework</span></span>        | <span data-ttu-id="d2a3f-134">4.7.1</span><span class="sxs-lookup"><span data-stu-id="d2a3f-134">4.7.1</span></span>          | <span data-ttu-id="d2a3f-135">net471</span><span class="sxs-lookup"><span data-stu-id="d2a3f-135">net471</span></span>                         | <span data-ttu-id="d2a3f-136">2.0</span><span class="sxs-lookup"><span data-stu-id="d2a3f-136">2.0</span></span>                                     |

## <a name="supported-target-framework-versions"></a><span data-ttu-id="d2a3f-137">Podporované target framework verze</span><span class="sxs-lookup"><span data-stu-id="d2a3f-137">Supported target framework versions</span></span>

<span data-ttu-id="d2a3f-138">Cílové rozhraní se obvykle odkazuje TFM.</span><span class="sxs-lookup"><span data-stu-id="d2a3f-138">A target framework is typically referenced by a TFM.</span></span> <span data-ttu-id="d2a3f-139">V následující tabulce jsou uvedeny cílové rozhraní nepodporuje rozhraní .NET Core SDK a klienta NuGet.</span><span class="sxs-lookup"><span data-stu-id="d2a3f-139">The following table shows the target frameworks supported by the .NET Core SDK and the NuGet client.</span></span> <span data-ttu-id="d2a3f-140">Ekvivalenty se zobrazí v závorkách.</span><span class="sxs-lookup"><span data-stu-id="d2a3f-140">Equivalents are shown within brackets.</span></span> <span data-ttu-id="d2a3f-141">Například `win81` je ekvivalentní TFM k `netcore451`.</span><span class="sxs-lookup"><span data-stu-id="d2a3f-141">For example, `win81` is an equivalent TFM to `netcore451`.</span></span>

| <span data-ttu-id="d2a3f-142">Cílová architektura</span><span class="sxs-lookup"><span data-stu-id="d2a3f-142">Target Framework</span></span>           | <span data-ttu-id="d2a3f-143">TFM</span><span class="sxs-lookup"><span data-stu-id="d2a3f-143">TFM</span></span> |
| -------------------------- | --- |
| <span data-ttu-id="d2a3f-144">Standardní rozhraní .NET</span><span class="sxs-lookup"><span data-stu-id="d2a3f-144">.NET Standard</span></span>              | <span data-ttu-id="d2a3f-145">netstandard1.0</span><span class="sxs-lookup"><span data-stu-id="d2a3f-145">netstandard1.0</span></span><br><span data-ttu-id="d2a3f-146">netstandard1.1</span><span class="sxs-lookup"><span data-stu-id="d2a3f-146">netstandard1.1</span></span><br><span data-ttu-id="d2a3f-147">netstandard1.2</span><span class="sxs-lookup"><span data-stu-id="d2a3f-147">netstandard1.2</span></span><br><span data-ttu-id="d2a3f-148">netstandard1.3</span><span class="sxs-lookup"><span data-stu-id="d2a3f-148">netstandard1.3</span></span><br><span data-ttu-id="d2a3f-149">netstandard1.4</span><span class="sxs-lookup"><span data-stu-id="d2a3f-149">netstandard1.4</span></span><br><span data-ttu-id="d2a3f-150">netstandard1.5</span><span class="sxs-lookup"><span data-stu-id="d2a3f-150">netstandard1.5</span></span><br><span data-ttu-id="d2a3f-151">netstandard1.6</span><span class="sxs-lookup"><span data-stu-id="d2a3f-151">netstandard1.6</span></span><br><span data-ttu-id="d2a3f-152">netstandard2.0</span><span class="sxs-lookup"><span data-stu-id="d2a3f-152">netstandard2.0</span></span> |
| <span data-ttu-id="d2a3f-153">.NET Core</span><span class="sxs-lookup"><span data-stu-id="d2a3f-153">.NET Core</span></span>                  | <span data-ttu-id="d2a3f-154">netcoreapp1.0</span><span class="sxs-lookup"><span data-stu-id="d2a3f-154">netcoreapp1.0</span></span><br><span data-ttu-id="d2a3f-155">netcoreapp1.1</span><span class="sxs-lookup"><span data-stu-id="d2a3f-155">netcoreapp1.1</span></span><br><span data-ttu-id="d2a3f-156">netcoreapp2.0</span><span class="sxs-lookup"><span data-stu-id="d2a3f-156">netcoreapp2.0</span></span> |
| <span data-ttu-id="d2a3f-157">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="d2a3f-157">.NET Framework</span></span>             | <span data-ttu-id="d2a3f-158">net11</span><span class="sxs-lookup"><span data-stu-id="d2a3f-158">net11</span></span><br><span data-ttu-id="d2a3f-159">net20</span><span class="sxs-lookup"><span data-stu-id="d2a3f-159">net20</span></span><br><span data-ttu-id="d2a3f-160">Net35</span><span class="sxs-lookup"><span data-stu-id="d2a3f-160">net35</span></span><br><span data-ttu-id="d2a3f-161">net40</span><span class="sxs-lookup"><span data-stu-id="d2a3f-161">net40</span></span><br><span data-ttu-id="d2a3f-162">net403</span><span class="sxs-lookup"><span data-stu-id="d2a3f-162">net403</span></span><br><span data-ttu-id="d2a3f-163">net45</span><span class="sxs-lookup"><span data-stu-id="d2a3f-163">net45</span></span><br><span data-ttu-id="d2a3f-164">net451</span><span class="sxs-lookup"><span data-stu-id="d2a3f-164">net451</span></span><br><span data-ttu-id="d2a3f-165">net452</span><span class="sxs-lookup"><span data-stu-id="d2a3f-165">net452</span></span><br><span data-ttu-id="d2a3f-166">net46</span><span class="sxs-lookup"><span data-stu-id="d2a3f-166">net46</span></span><br><span data-ttu-id="d2a3f-167">net461</span><span class="sxs-lookup"><span data-stu-id="d2a3f-167">net461</span></span><br><span data-ttu-id="d2a3f-168">net462</span><span class="sxs-lookup"><span data-stu-id="d2a3f-168">net462</span></span><br><span data-ttu-id="d2a3f-169">net47</span><span class="sxs-lookup"><span data-stu-id="d2a3f-169">net47</span></span><br><span data-ttu-id="d2a3f-170">net471</span><span class="sxs-lookup"><span data-stu-id="d2a3f-170">net471</span></span> |
| <span data-ttu-id="d2a3f-171">Windows Store</span><span class="sxs-lookup"><span data-stu-id="d2a3f-171">Windows Store</span></span>              | <span data-ttu-id="d2a3f-172">netcore [netcore45]</span><span class="sxs-lookup"><span data-stu-id="d2a3f-172">netcore [netcore45]</span></span><br><span data-ttu-id="d2a3f-173">netcore45 [win] [win8]</span><span class="sxs-lookup"><span data-stu-id="d2a3f-173">netcore45 [win] [win8]</span></span><br><span data-ttu-id="d2a3f-174">netcore451 [win81]</span><span class="sxs-lookup"><span data-stu-id="d2a3f-174">netcore451 [win81]</span></span> |
| <span data-ttu-id="d2a3f-175">Malých rozhraní .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d2a3f-175">.NET Micro Framework</span></span>       | <span data-ttu-id="d2a3f-176">netmf</span><span class="sxs-lookup"><span data-stu-id="d2a3f-176">netmf</span></span> |
| <span data-ttu-id="d2a3f-177">Silverlight</span><span class="sxs-lookup"><span data-stu-id="d2a3f-177">Silverlight</span></span>                | <span data-ttu-id="d2a3f-178">sl4</span><span class="sxs-lookup"><span data-stu-id="d2a3f-178">sl4</span></span><br><span data-ttu-id="d2a3f-179">sl5</span><span class="sxs-lookup"><span data-stu-id="d2a3f-179">sl5</span></span> |
| <span data-ttu-id="d2a3f-180">Windows Phone</span><span class="sxs-lookup"><span data-stu-id="d2a3f-180">Windows Phone</span></span>              | <span data-ttu-id="d2a3f-181">webové části [wp7]</span><span class="sxs-lookup"><span data-stu-id="d2a3f-181">wp [wp7]</span></span><br><span data-ttu-id="d2a3f-182">wp7</span><span class="sxs-lookup"><span data-stu-id="d2a3f-182">wp7</span></span><br><span data-ttu-id="d2a3f-183">wp75</span><span class="sxs-lookup"><span data-stu-id="d2a3f-183">wp75</span></span><br><span data-ttu-id="d2a3f-184">wp8</span><span class="sxs-lookup"><span data-stu-id="d2a3f-184">wp8</span></span><br><span data-ttu-id="d2a3f-185">wp81</span><span class="sxs-lookup"><span data-stu-id="d2a3f-185">wp81</span></span><br><span data-ttu-id="d2a3f-186">wpa81</span><span class="sxs-lookup"><span data-stu-id="d2a3f-186">wpa81</span></span> |
| <span data-ttu-id="d2a3f-187">Univerzální platforma pro Windows</span><span class="sxs-lookup"><span data-stu-id="d2a3f-187">Universal Windows Platform</span></span> | <span data-ttu-id="d2a3f-188">uap [uap10.0]</span><span class="sxs-lookup"><span data-stu-id="d2a3f-188">uap [uap10.0]</span></span><br><span data-ttu-id="d2a3f-189">uap10.0 [win10] [netcore50]</span><span class="sxs-lookup"><span data-stu-id="d2a3f-189">uap10.0 [win10] [netcore50]</span></span> |

## <a name="how-to-specify-target-frameworks"></a><span data-ttu-id="d2a3f-190">Určení cílové rozhraní</span><span class="sxs-lookup"><span data-stu-id="d2a3f-190">How to specify target frameworks</span></span>

<span data-ttu-id="d2a3f-191">Cílové rozhraní jsou určené v souboru projektu.</span><span class="sxs-lookup"><span data-stu-id="d2a3f-191">Target frameworks are specified in your project file.</span></span> <span data-ttu-id="d2a3f-192">Pokud je zadána jedné cílové rozhraní, použijte **TargetFramework** elementu.</span><span class="sxs-lookup"><span data-stu-id="d2a3f-192">When a single target framework is specified, use the **TargetFramework** element.</span></span> <span data-ttu-id="d2a3f-193">Následující soubor projektu aplikace konzoly ukazuje, jak cílí na .NET Core 2.0:</span><span class="sxs-lookup"><span data-stu-id="d2a3f-193">The following console app project file demonstrates how to target .NET Core 2.0:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.0</TargetFramework>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="d2a3f-194">Pokud zadáte více cílové rozhraní, může podmíněně odkazujete na sestavení pro každé cílové rozhraní.</span><span class="sxs-lookup"><span data-stu-id="d2a3f-194">When you specify multiple target frameworks, you may conditionally reference assemblies for each target framework.</span></span> <span data-ttu-id="d2a3f-195">V kódu, můžete podmíněně zkompilovat proti tyto sestavení pomocí preprocesoru symboly s *if potom else* logiku.</span><span class="sxs-lookup"><span data-stu-id="d2a3f-195">In your code, you can conditionally compile against those assemblies by using preprocessor symbols with *if-then-else* logic.</span></span>

<span data-ttu-id="d2a3f-196">Následující soubor projektu knihovny cílem rozhraní API z Standard .NET (`netstandard1.4`) a rozhraní API rozhraní .NET Framework (`net40` a `net45`).</span><span class="sxs-lookup"><span data-stu-id="d2a3f-196">The following library project file targets APIs of .NET Standard (`netstandard1.4`) and APIs of the .NET Framework (`net40` and `net45`).</span></span> <span data-ttu-id="d2a3f-197">Použijte množném čísle **TargetFrameworks** element s více cílové architektury.</span><span class="sxs-lookup"><span data-stu-id="d2a3f-197">Use the plural **TargetFrameworks** element with multiple target frameworks.</span></span> <span data-ttu-id="d2a3f-198">Poznámka: Jak `Condition` atributy patří balíčky závisí na implementaci při kompilaci knihovny pro dvě TFMs Framework .NET:</span><span class="sxs-lookup"><span data-stu-id="d2a3f-198">Note how the `Condition` attributes include implementation-specific packages when the library is compiled for the two .NET Framework TFMs:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFrameworks>netstandard1.4;net40;net45</TargetFrameworks>
  </PropertyGroup>

  <!-- Conditionally obtain references for the .NET Framework 4.0 target -->
  <ItemGroup Condition=" '$(TargetFramework)' == 'net40' ">
    <Reference Include="System.Net" />
  </ItemGroup>

  <!-- Conditionally obtain references for the .NET Framework 4.5 target -->
  <ItemGroup Condition=" '$(TargetFramework)' == 'net45' ">
    <Reference Include="System.Net.Http" />
    <Reference Include="System.Threading.Tasks" />
  </ItemGroup>

</Project>
```

<span data-ttu-id="d2a3f-199">V rámci knihovny nebo aplikací zápisu podmíněného kód mohl zkompilovat pro každé cílové rozhraní:</span><span class="sxs-lookup"><span data-stu-id="d2a3f-199">Within your library or app, you write conditional code to compile for each target framework:</span></span>

```csharp
public class MyClass
{
    static void Main()
    {
#if NET40
        Console.WriteLine("Target framework: .NET Framework 4.0");
#elif NET45  
        Console.WriteLine("Target framework: .NET Framework 4.5");
#else
        Console.WriteLine("Target framework: .NET Standard 1.4");
#endif
    }
}
```

<span data-ttu-id="d2a3f-200">Systém sestavení si je vědoma preprocesoru symboly představující cílové rozhraní ukazuje [podporované target framework verze](#supported-target-framework-versions) tabulky.</span><span class="sxs-lookup"><span data-stu-id="d2a3f-200">The build system is aware of preprocessor symbols representing the target frameworks shown in the [Supported target framework versions](#supported-target-framework-versions) table.</span></span> <span data-ttu-id="d2a3f-201">Pokud používáte symbol, který představuje .NET Standard nebo .NET Core TFM, nahraďte podtržítkem tečky a změnit malých písmen na velká písmena (například symbol pro `netstandard1.4` je `NETSTANDARD1_4`).</span><span class="sxs-lookup"><span data-stu-id="d2a3f-201">When using a symbol that represents a .NET Standard or .NET Core TFM, replace the dot with an underscore and change lowercase letters to uppercase (for example, the symbol for `netstandard1.4` is `NETSTANDARD1_4`).</span></span>

<span data-ttu-id="d2a3f-202">Úplný seznam preprocesoru symboly pro cílové rozhraní .NET Core je:</span><span class="sxs-lookup"><span data-stu-id="d2a3f-202">The complete list of preprocessor symbols for .NET Core target frameworks is:</span></span>

[!INCLUDE [Preprocessor symbols](~/includes/preprocessor-symbols.md)]

## <a name="deprecated-target-frameworks"></a><span data-ttu-id="d2a3f-203">Nepoužívané cílové rozhraní</span><span class="sxs-lookup"><span data-stu-id="d2a3f-203">Deprecated target frameworks</span></span>

<span data-ttu-id="d2a3f-204">Následující cílové architektury jsou zastaralé.</span><span class="sxs-lookup"><span data-stu-id="d2a3f-204">The following target frameworks are deprecated.</span></span> <span data-ttu-id="d2a3f-205">Balíčky cílené na tyto cílové rozhraní měli migrovat na uvedené nahrazení.</span><span class="sxs-lookup"><span data-stu-id="d2a3f-205">Packages targeting these target frameworks should migrate to the indicated replacements.</span></span>

| <span data-ttu-id="d2a3f-206">Nepoužívané TFM</span><span class="sxs-lookup"><span data-stu-id="d2a3f-206">Deprecated TFM</span></span>                                                                             | <span data-ttu-id="d2a3f-207">Nahrazení</span><span class="sxs-lookup"><span data-stu-id="d2a3f-207">Replacement</span></span> |
| ------------------------------------------------------------------------------------------ | ----------- |
| <span data-ttu-id="d2a3f-208">aspnet50</span><span class="sxs-lookup"><span data-stu-id="d2a3f-208">aspnet50</span></span><br><span data-ttu-id="d2a3f-209">aspnetcore50</span><span class="sxs-lookup"><span data-stu-id="d2a3f-209">aspnetcore50</span></span><br><span data-ttu-id="d2a3f-210">dnxcore50</span><span class="sxs-lookup"><span data-stu-id="d2a3f-210">dnxcore50</span></span><br><span data-ttu-id="d2a3f-211">dnx</span><span class="sxs-lookup"><span data-stu-id="d2a3f-211">dnx</span></span><br><span data-ttu-id="d2a3f-212">dnx45</span><span class="sxs-lookup"><span data-stu-id="d2a3f-212">dnx45</span></span><br><span data-ttu-id="d2a3f-213">dnx451</span><span class="sxs-lookup"><span data-stu-id="d2a3f-213">dnx451</span></span><br><span data-ttu-id="d2a3f-214">dnx452</span><span class="sxs-lookup"><span data-stu-id="d2a3f-214">dnx452</span></span>                  | <span data-ttu-id="d2a3f-215">netcoreapp</span><span class="sxs-lookup"><span data-stu-id="d2a3f-215">netcoreapp</span></span>  |
| <span data-ttu-id="d2a3f-216">DotNet.</span><span class="sxs-lookup"><span data-stu-id="d2a3f-216">dotnet</span></span><br><span data-ttu-id="d2a3f-217">dotnet50</span><span class="sxs-lookup"><span data-stu-id="d2a3f-217">dotnet50</span></span><br><span data-ttu-id="d2a3f-218">dotnet51</span><span class="sxs-lookup"><span data-stu-id="d2a3f-218">dotnet51</span></span><br><span data-ttu-id="d2a3f-219">dotnet52</span><span class="sxs-lookup"><span data-stu-id="d2a3f-219">dotnet52</span></span><br><span data-ttu-id="d2a3f-220">dotnet53</span><span class="sxs-lookup"><span data-stu-id="d2a3f-220">dotnet53</span></span><br><span data-ttu-id="d2a3f-221">dotnet54</span><span class="sxs-lookup"><span data-stu-id="d2a3f-221">dotnet54</span></span><br><span data-ttu-id="d2a3f-222">dotnet55</span><span class="sxs-lookup"><span data-stu-id="d2a3f-222">dotnet55</span></span><br><span data-ttu-id="d2a3f-223">dotnet56</span><span class="sxs-lookup"><span data-stu-id="d2a3f-223">dotnet56</span></span> | <span data-ttu-id="d2a3f-224">monikerů netstandard</span><span class="sxs-lookup"><span data-stu-id="d2a3f-224">netstandard</span></span> |
| <span data-ttu-id="d2a3f-225">netcore50</span><span class="sxs-lookup"><span data-stu-id="d2a3f-225">netcore50</span></span>                                                                                  | <span data-ttu-id="d2a3f-226">uap10.0</span><span class="sxs-lookup"><span data-stu-id="d2a3f-226">uap10.0</span></span>     |
| <span data-ttu-id="d2a3f-227">Win</span><span class="sxs-lookup"><span data-stu-id="d2a3f-227">win</span></span>                                                                                        | <span data-ttu-id="d2a3f-228">netcore45</span><span class="sxs-lookup"><span data-stu-id="d2a3f-228">netcore45</span></span>   |
| <span data-ttu-id="d2a3f-229">win8</span><span class="sxs-lookup"><span data-stu-id="d2a3f-229">win8</span></span>                                                                                       | <span data-ttu-id="d2a3f-230">netcore45</span><span class="sxs-lookup"><span data-stu-id="d2a3f-230">netcore45</span></span>   |
| <span data-ttu-id="d2a3f-231">win81</span><span class="sxs-lookup"><span data-stu-id="d2a3f-231">win81</span></span>                                                                                      | <span data-ttu-id="d2a3f-232">netcore451</span><span class="sxs-lookup"><span data-stu-id="d2a3f-232">netcore451</span></span>  |
| <span data-ttu-id="d2a3f-233">win10</span><span class="sxs-lookup"><span data-stu-id="d2a3f-233">win10</span></span>                                                                                      | <span data-ttu-id="d2a3f-234">uap10.0</span><span class="sxs-lookup"><span data-stu-id="d2a3f-234">uap10.0</span></span>     |
| <span data-ttu-id="d2a3f-235">winrt</span><span class="sxs-lookup"><span data-stu-id="d2a3f-235">winrt</span></span>                                                                                      | <span data-ttu-id="d2a3f-236">netcore45</span><span class="sxs-lookup"><span data-stu-id="d2a3f-236">netcore45</span></span>   |

## <a name="see-also"></a><span data-ttu-id="d2a3f-237">Viz také</span><span class="sxs-lookup"><span data-stu-id="d2a3f-237">See also</span></span>

[<span data-ttu-id="d2a3f-238">Balíčky, Metapackages a architektury</span><span class="sxs-lookup"><span data-stu-id="d2a3f-238">Packages, Metapackages and Frameworks</span></span>](~/docs/core/packages.md)  
[<span data-ttu-id="d2a3f-239">Vývoj knihovny s křížové nástrojů platformy</span><span class="sxs-lookup"><span data-stu-id="d2a3f-239">Developing Libraries with Cross Platform Tools</span></span>](~/docs/core/tutorials/libraries.md)  
[<span data-ttu-id="d2a3f-240">Standardní rozhraní .NET</span><span class="sxs-lookup"><span data-stu-id="d2a3f-240">.NET Standard</span></span>](~/docs/standard/net-standard.md)  
[<span data-ttu-id="d2a3f-241">Správa verzí rozhraní .NET core</span><span class="sxs-lookup"><span data-stu-id="d2a3f-241">.NET Core Versioning</span></span>](~/docs/core/versions/index.md)  
[<span data-ttu-id="d2a3f-242">úložiště GitHub DotNet nebo standard</span><span class="sxs-lookup"><span data-stu-id="d2a3f-242">dotnet/standard GitHub repository</span></span>](https://github.com/dotnet/standard)  
[<span data-ttu-id="d2a3f-243">Úložiště GitHub nástroje NuGet</span><span class="sxs-lookup"><span data-stu-id="d2a3f-243">NuGet Tools GitHub Repository</span></span>](https://github.com/joelverhagen/NuGetTools)  
[<span data-ttu-id="d2a3f-244">Profily Framework v rozhraní .NET</span><span class="sxs-lookup"><span data-stu-id="d2a3f-244">Framework Profiles in .NET</span></span>](http://blog.stephencleary.com/2012/05/framework-profiles-in-net.html)
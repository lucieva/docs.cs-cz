---
title: Portování do .NET Core – analýza závislostí třetích stran
description: Zjistěte, jak analýza závislostí třetích stran k portu projektu z rozhraní .NET Framework do .NET Core.
author: cartermp
ms.author: mairaw
ms.date: 02/15/2018
ms.openlocfilehash: 06d8d36d8369680c54af4d16513b2b871b57079c
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/18/2018
ms.locfileid: "46000996"
---
# <a name="analyze-your-third-party-dependencies"></a>Analýza závislostí třetích stran

Pokud hledáte přeneste kód do .NET Core nebo .NET Standard, je prvním krokem v procesu přenosem pochopit závislostí třetích stran. Závislostí třetích stran jsou buď [balíčky NuGet](#analyze-referenced-nuget-packages-on-your-project) nebo [knihovny DLL](#analyze-dependencies-that-arent-nuget-packages) se odkazuje v projektu. Vyhodnotit každý závislosti a vytvořte plán řešení nepředvídaných událostí pro závislosti, které nejsou kompatibilní s .NET Core. V tomto článku se dozvíte, jak určit, zda závislost je kompatibilní s .NET Core.

## <a name="analyze-referenced-nuget-packages-in-your-project"></a>Analýza odkazované balíčky NuGet ve vašem projektu

Pokud už odkazuje na balíčky NuGet ve vašem projektu, musíte ověřit, pokud jsou kompatibilní s .NET Core.
Existují dva způsoby, jak to udělat:

* [Pomocí Průzkumníku balíčků NuGet aplikace](#analyze-nuget-packages-using-nuget-package-explorer) (nejspolehlivější způsob).
* [Použití webu nuget.org](#analyze-nuget-packages-using-nugetorg).

Po analýze balíčků, pokud nejsou kompatibilní s .NET Core a pouze cílové rozhraní .NET Framework, můžete zkontrolovat Pokud [režim kompatibility rozhraní .NET Framework](#net-framework-compatibility-mode) pomáhá s přenosem procesem.

### <a name="analyze-nuget-packages-using-nuget-package-explorer"></a>Analýza balíčků NuGet pomocí Průzkumníku balíčků NuGet

Balíček NuGet je sám sadu složek, které obsahují specifické pro platformu sestavení. Proto je potřeba zkontrolovat, zda je složka, která obsahuje sestavení s kompatibilní uvnitř balíčku.

Nejjednodušší způsob, jak kontrolovat složky balíčku NuGet je použít [NuGet – Průzkumník balíčků](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) nástroj. Po instalaci, postupujte následovně Chcete-li zobrazit názvy složek:

1. Otevřete v Průzkumníku balíčků NuGet.
2. Klikněte na tlačítko **otevřít balíček z online datového kanálu**.
3. Vyhledejte název balíčku.
4. Ve výsledcích hledání vyberte název balíčku a klikněte na tlačítko **otevřete**.
5. Rozbalte *lib* složky na pravé straně a podívejte se na názvy složek.

Vyhledejte složku s žádným z následujících názvů:

```
netstandard1.0
netstandard1.1
netstandard1.2
netstandard1.3
netstandard1.4
netstandard1.5
netstandard1.6
netstandard2.0
netcoreapp1.0
netcoreapp1.1
netcoreapp2.0
netcoreapp2.1
portable-net45-win8
portable-win8-wpa8
portable-net451-win81
portable-net45-win8-wpa8-wpa81
```

Tyto hodnoty jsou [Monikery cílového rozhraní (Tfm)](../../standard/frameworks.md) , která mapují na verzích [.NET Standard](../../standard/net-standard.md), .NET Core a tradiční profily Přenosná knihovna tříd (PCL), které jsou kompatibilní s .NET Core.

> [!IMPORTANT]
> Při prohlížení Tfm, které podporuje balíčku, Všimněte si, že `netcoreapp*`, zatímco kompatibilní, je pro projekty .NET Core pouze a ne pro projekty .NET Standard.
> Knihovnu, která se zaměřuje pouze `netcoreapp*` a ne `netstandard*` může používat jenom jiné aplikace .NET Core.

Existují také některé starší verze Tfm používaných pro předběžné verze sady .NET Core, který může být také kompatibilní:

```
dnxcore50
dotnet5.0
dotnet5.1
dotnet5.2
dotnet5.3
dotnet5.4
dotnet5.5
```

Zatímco tyto Tfm pravděpodobně fungovat s vaším kódem, není nijak zaručena kompatibilita. Balíčky s těmito Tfm byly vytvořeny s balíčky v předběžné verzi .NET Core. Poznamenejte si při (nebo pokud) balíčků s využitím těchto Tfm se aktualizují na základě .NET Standard.

> [!NOTE]
> Chcete-li používat balíčky cílí na tradiční PCL nebo cíl předběžnou verzi .NET Core, musíte použít `PackageTargetFallback` MSBuild element v souboru projektu.
> Další informace o tomto prvku MSBuild naleznete v tématu [ `PackageTargetFallback` ](../tools/csproj.md#packagetargetfallback).

### <a name="analyze-nuget-packages-using-nugetorg"></a>Analýza balíčků NuGet pomocí nuget.org

Alternativně můžete zobrazit Tfm, které podporuje každý balíček na [nuget.org](https://www.nuget.org/) pod **závislosti** na stránce balíček.

Ačkoli použití webu je jednodušší způsob ověření kompatibility, **závislosti** informace nejsou k dispozici na webu pro všechny balíčky.

### <a name="net-framework-compatibility-mode"></a>Režim kompatibility rozhraní .NET framework

Po analýze balíčky NuGet, můžete zjistit, že pouze cílí na rozhraní .NET Framework, stejně jako většinu balíčků NuGet.

Počínaje rozhraním .NET Standard 2.0, byla zavedena režimu kompatibility rozhraní .NET Framework. Tento režim kompatibility umožňuje odkazovat na knihovny rozhraní .NET Framework projekty .NET Standard a .NET Core. Odkazování na knihovny rozhraní .NET Framework nefunguje pro všechny projekty, třeba když knihovny používá Windows Presentation Foundation (WPF) rozhraní API, ale jeho odblokovat mnoho scénářů přenosem.

Při odkazu na balíčky NuGet, které se zaměřují rozhraní .NET Framework ve vašem projektu, například [Huitian.PowerCollections](https://www.nuget.org/packages/Huitian.PowerCollections), zobrazí upozornění záložní balíčku ([NU1701](/nuget/reference/errors-and-warnings#nu1701)) podobně jako v následujícím příkladu:

`NU1701: Package ‘Huitian.PowerCollections 1.0.0’ was restored using ‘.NETFramework,Version=v4.6.1’ instead of the project target framework ‘.NETStandard,Version=v2.0’. This package may not be fully compatible with your project.`

Že upozornění se zobrazí, když přidáte balíček a pokaždé, když vytváříte Ujistěte se, že při testování s využitím projektu daného balíčku. Pokud váš projekt pracuje podle očekávání, můžete potlačit tohoto upozornění úpravou vlastnosti balíčku v sadě Visual Studio nebo ruční úpravou souboru projektu v váš oblíbený editor kódu.

Chcete-li potlačit upozornění úpravou souboru projektu, vyhledejte `PackageReference` položky balíčku, kterou chcete potlačit upozornění pro a přidat `NoWarn` atribut. `NoWarn` Atribut přijímá čárkami oddělený seznam všech upozornění ID. Následující příklad ukazuje, jak můžete potlačit `NU1701` pro upozornění `Huitian.PowerCollections` balíčku tak, že ručně upravíte soubor projektu:

```xml
<ItemGroup>
  <PackageReference Include="Huitian.PowerCollections" Version="1.0.0" NoWarn="NU1701" />
</ItemGroup>
```

Další informace o tom, jak potlačení upozornění kompilátoru v sadě Visual Studio najdete v tématu [potlačení upozornění pro balíčky NuGet](/visualstudio/ide/how-to-suppress-compiler-warnings#suppressing-warnings-for-nuget-packages).

### <a name="what-to-do-when-your-nuget-package-dependency-doesnt-run-on-net-core"></a>Co dělat, když vaše závislost balíčku NuGet není spuštěna v rozhraní .NET Core

Existuje několik věcí, které můžete provést, pokud závisí na balíčku NuGet není spuštěna v rozhraní .NET Core:

1. Pokud je projekt open source a hostovaná někde, např. GitHub, můžete zapojit vývojáře přímo.
2. Můžete kontaktovat přímo na autora [nuget.org](https://www.nuget.org/). Vyhledejte balíček a klikněte na tlačítko **kontakt vlastníky** na levé straně stránky daného balíčku.
3. Můžete vyhledat jinému balíčku, který běží na .NET Core, který provede stejné úkoly, jako balíček, který jste používali.
4. Pokuste se, že balíček dělal sami psát kód.
5. Závislost na balíčku byste mohli eliminovat alespoň změnou funkci vaší aplikace, dokud nebude k dispozici kompatibilní verzi balíčku.

Mějte na paměti, že programu open source projektu a Vydavatel balíčku NuGet se často dobrovolníků. Přispívají, protože záleží danou doménu, dělat zdarma a často mají různé denní úlohy. Proto buďte s vědomím, která při kontaktování moct požádat o podporu .NET Core.

Pokud váš problém s žádným z výše uvedených nelze vyřešit, budete muset port až po .NET Core později.

Tým .NET chcete zjistit, které knihovny jsou nejdůležitější pro podporu s .NET Core. Můžete poslat e-mailu dotnet@microsoft.com knihovny, který chcete použít.

## <a name="analyze-dependencies-that-arent-nuget-packages"></a>Analýza závislosti, které nejsou balíčky NuGet

Může mít závislost, která není balíček NuGet, jako je například knihovny DLL v systému souborů. Jediný způsob, jak určit přenositelnost dané závislosti je spustit [.NET Portability Analyzeru](https://github.com/Microsoft/dotnet-apiport) nástroj. Nástroj můžete analyzovat sestavení, které jsou cíleny rozhraní .NET Framework a identifikovat rozhraní API, která nejsou přenositelnost na jiné platformy .NET, jako je .NET Core. Nástroj můžete spustit jako konzolové aplikace v jazyce nebo [rozšíření sady Visual Studio](../../standard/analyzers/portability-analyzer.md).

## <a name="next-steps"></a>Další kroky

Pokud jste přenesení do knihovny, přečtěte si [přenos knihoven](libraries.md).

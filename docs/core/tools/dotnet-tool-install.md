---
title: Instalace nástrojů DotNet příkaz – rozhraní příkazového řádku .NET Core
description: Nástroj dotnet nainstalovat příkaz nainstaluje zadaný globální nástroji .NET Core na počítači.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: aad5a3e815936749d90f40975a8b13d34e89386c
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/04/2018
ms.locfileid: "43512192"
---
# <a name="dotnet-tool-install"></a>Instalace nástrojů DotNet

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a>Název

`dotnet tool install` -Nainstaluje zadaný [globální nástroje .NET Core](global-tools.md) na svém počítači.

## <a name="synopsis"></a>Souhrn

```console
dotnet tool install <PACKAGE_NAME> <-g|--global> [--add-source] [--configfile] [--framework] [-v|--verbosity] [--version]
dotnet tool install <PACKAGE_NAME> <--tool-path> [--add-source] [--configfile] [--framework] [-v|--verbosity] [--version]
dotnet tool install <-h|--help>
```

## <a name="description"></a>Popis

`dotnet tool install` Příkaz poskytuje způsob, jak k instalaci globální nástroje .NET Core na počítači. Chcete-li použít příkaz, potřebujete buď určete, jestli má uživatel celou instalaci pomocí `--global` možnost nebo můžete zadat cestu k ho nainstalovat pomocí `--tool-path` možnost.

Globální nástroje jsou nainstalovány v následujících adresářích ve výchozím nastavení při zadání `-g` (nebo `--global`) možnost:

| OPERAČNÍ SYSTÉM          | Cesta                          |
|-------------|-------------------------------|
| Linux nebo macOS | `$HOME/.dotnet/tools`         |
| Windows     | `%USERPROFILE%\.dotnet\tools` |

## <a name="arguments"></a>Arguments

`PACKAGE_NAME`

Název nebo ID, která nástroj obsahuje, .NET Core globální instalace balíčku NuGet.

## <a name="options"></a>Možnosti

`--add-source <SOURCE>`

Přidá další zdroj balíčku NuGet pro použití během instalace.

`--configfile <FILE>`

Konfigurace NuGet (*nuget.config*) soubor se má použít.

`--framework <FRAMEWORK>`

Určuje, [cílovou architekturu](../../standard/frameworks.md) instalace nástroje pro. Ve výchozím nastavení .NET Core SDK se pokusí zvolte nejvhodnější cílovou architekturu.

`-g|--global`

Určuje, že instalace je uživatel široké. Nelze kombinovat s `--tool-path` možnost. Pokud nezadáte tuto možnost, je nutné zadat `--tool-path` možnost.

`-h|--help`

Vytiskne krátký nápovědy pro příkaz.

`--tool-path <PATH>`

Určuje umístění, kam se má nainstalovat nástroj globální. Cesta může být absolutní nebo relativní. Pokud cesta neexistuje, příkaz se pokusí se ji vytvořit. Nelze kombinovat s `--global` možnost. Pokud nezadáte tuto možnost, je nutné zadat `--global` možnost.

`-v|--verbosity <LEVEL>`

Nastaví úroveň podrobností příkazu. Povolené hodnoty jsou `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, a `diag[nostic]`.

`--version <VERSION_NUMBER>`

Verze nástroje k instalaci. Ve výchozím nastavení je nainstalovaná nejnovější verze stabilní balíček. Tuto možnost použijte, chcete-li nainstalovat verzi preview nebo starší verze nástroje.

## <a name="examples"></a>Příklady

Nainstaluje [dotnetsay](https://www.nuget.org/packages/dotnetsay/) globální nástroj ve výchozím umístění:

`dotnet tool install -g dotnetsay`

Nainstaluje [dotnetsay](https://www.nuget.org/packages/dotnetsay/) globální nástroj v určité složce Windows:

`dotnet tool install dotnetsay --tool-path c:\global-tools`

Nainstaluje [dotnetsay](https://www.nuget.org/packages/dotnetsay/) globální nástroj v určité složce Linux nebo macOS:

`dotnet tool install dotnetsay --tool-path ~/bin`

Nainstaluje verzi 2.0.0 [dotnetsay](https://www.nuget.org/packages/dotnetsay/) globální nástroje:

`dotnet tool install -g dotnetsay --version 2.0.0`

## <a name="see-also"></a>Viz také:

* [Globální nástroje .NET core](global-tools.md)
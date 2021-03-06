---
title: příkaz push DotNet nuget – rozhraní příkazového řádku .NET Core
description: Příkaz dotnet nuget nabízených odešle balíček na server a publikuje ji.
author: karann-msft
ms.author: mairaw
ms.date: 09/04/2018
ms.openlocfilehash: b9c0fad886cd1234325c58bf61b1a010bce421d9
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/28/2018
ms.locfileid: "50200019"
---
# <a name="dotnet-nuget-push"></a>DotNet nuget push

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>Název

`dotnet nuget push` -Odešle balíček na server a publikuje ji.

## <a name="synopsis"></a>Souhrn

# <a name="net-core-21tabnetcore21"></a>[.NET core 2.1](#tab/netcore21)
```
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [-k|--api-key] [-n|--no-symbols]
    [--no-service-endpoint] [-s|--source] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```
# <a name="net-core-20tabnetcore20"></a>[.NET core 2.0](#tab/netcore20)
```
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [-k|--api-key] [-n|--no-symbols]
    [-s|--source] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[.NET core 1.x](#tab/netcore1x)
```
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [-k|--api-key] [-n|--no-symbols]
    [-s|--source] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```
---

## <a name="description"></a>Popis

`dotnet nuget push` Příkaz odešle balíček na server a publikuje ji. Příkaz nabízených oznámení pomocí serveru a přihlašovací údaje podrobnosti nacházející se v konfiguračním souboru systému NuGet nebo řetězec konfigurační soubory. Další informace o konfiguračních souborů naleznete v tématu [konfigurace chování Nugetu](/nuget/consume-packages/configuring-nuget-behavior). Výchozí konfigurace NuGet se získá načítání *%AppData%\NuGet\NuGet.config* (Windows) nebo *$HOME/.local/share* (Linux/macOS), pak všechny načítání *nuget.config*nebo *.nuget\nuget.config* od kořenové jednotky a končí v aktuálním adresáři.

## <a name="arguments"></a>Arguments

`ROOT`

Určuje cestu souboru pro balíček, který má být vložena.

## <a name="options"></a>Možnosti

# <a name="net-core-21tabnetcore21"></a>[.NET core 2.1](#tab/netcore21)

`-d|--disable-buffering`

Zakáže ukládání do vyrovnávací paměti při odesílání na server HTTP (S) ke snížení využití paměti.

`--force-english-output`

Přinutí aplikaci běžet v invariantní, základem je angličtina jazyková verze.

`-h|--help`

Vytiskne krátký nápovědy pro příkaz.

`-k|--api-key <API_KEY>`

Klíč rozhraní API pro server.

`-n|--no-symbols`

Nelze vložit symboly (i když je k dispozici).

`--no-service-endpoint`

"Api/v2/balíček" nemá připojení k zdrojová adresa URL.

`-s|--source <SOURCE>`

Určuje adresu URL serveru. Tato možnost je vyžadována, pokud `DefaultPushSource` konfigurační hodnota je nastavena v konfiguračním souboru NuGet.

`-sk|--symbol-api-key <API_KEY>`

Klíč rozhraní API pro server symbolů.

`-ss|--symbol-source <SOURCE>`

Určuje adresu URL serveru symbolů.

`-t|--timeout <TIMEOUT>`

Určuje časový limit pro odesílání na server v řádu sekund. Výchozí hodnota je 300 sekund (5 minut). Zadání 0 (nula sekund) použije výchozí hodnotu.

# <a name="net-core-20tabnetcore20"></a>[.NET core 2.0](#tab/netcore20)

`-d|--disable-buffering`

Zakáže ukládání do vyrovnávací paměti při odesílání na server HTTP (S) ke snížení využití paměti.

`--force-english-output`

Přinutí aplikaci běžet v invariantní, základem je angličtina jazyková verze.

`-h|--help`

Vytiskne krátký nápovědy pro příkaz.

`-k|--api-key <API_KEY>`

Klíč rozhraní API pro server.

`-n|--no-symbols`

Nelze vložit symboly (i když je k dispozici).

`-s|--source <SOURCE>`

Určuje adresu URL serveru. Tato možnost je vyžadována, pokud `DefaultPushSource` konfigurační hodnota je nastavena v konfiguračním souboru NuGet.

`-sk|--symbol-api-key <API_KEY>`

Klíč rozhraní API pro server symbolů.

`-ss|--symbol-source <SOURCE>`

Určuje adresu URL serveru symbolů.

`-t|--timeout <TIMEOUT>`

Určuje časový limit pro odesílání na server v řádu sekund. Výchozí hodnota je 300 sekund (5 minut). Zadání 0 (nula sekund) použije výchozí hodnotu.

# <a name="net-core-1xtabnetcore1x"></a>[.NET core 1.x](#tab/netcore1x)

`-d|--disable-buffering`

Zakáže ukládání do vyrovnávací paměti při odesílání na server HTTP (S) ke snížení využití paměti.

`--force-english-output`

Přinutí aplikaci běžet v invariantní, základem je angličtina jazyková verze.

`-h|--help`

Vytiskne krátký nápovědy pro příkaz.

`-k|--api-key <API_KEY>`

Klíč rozhraní API pro server.

`-n|--no-symbols`

Nelze vložit symboly (i když je k dispozici).

`-s|--source <SOURCE>`

Určuje adresu URL serveru. Tato možnost je vyžadována, pokud `DefaultPushSource` konfigurační hodnota je nastavena v konfiguračním souboru NuGet.

`-sk|--symbol-api-key <API_KEY>`

Klíč rozhraní API pro server symbolů.

`-ss|--symbol-source <SOURCE>`

Určuje adresu URL serveru symbolů.

`-t|--timeout <TIMEOUT>`

Určuje časový limit pro odesílání na server v řádu sekund. Výchozí hodnota je 300 sekund (5 minut). Zadání 0 (nula sekund) použije výchozí hodnotu.

---

## <a name="examples"></a>Příklady

Nabízených oznámení *foo.nupkg* nabízených oznámení na výchozí zdroj určení klíče rozhraní API:

`dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a`

Push *foo.nupkg* ke zdroji vlastní nabízené `https://customsource`, určení klíče rozhraní API:

`dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s https://customsource/`

Nabízených oznámení *foo.nupkg* pro výchozí zdroj nabízených oznámení:

`dotnet nuget push foo.nupkg`

Nabízených oznámení *foo.symbols.nupkg* pro výchozí zdroj symboly:

`dotnet nuget push foo.symbols.nupkg`

Nabízených oznámení *foo.nupkg* ke zdroji nabízené výchozí zadání časového limitu 360 druhé:

`dotnet nuget push foo.nupkg --timeout 360`

Nabízených oznámení všem *.nupkg* soubory v aktuálním adresáři pro výchozí zdroj nabízených oznámení:

`dotnet nuget push *.nupkg`

---
title: Návratové hodnoty Main() (Průvodce programováním v C#)
ms.date: 08/02/2017
helpviewer_keywords:
- Main method [C#], return values
ms.assetid: c2f5a1d8-1676-4bea-bc7e-44a97e72d5bc
ms.openlocfilehash: ea63bedd207a9904a5f6aa656ed19469394290fa
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/29/2018
ms.locfileid: "50205205"
---
# <a name="main-return-values-c-programming-guide"></a>Návratové hodnoty Main() (C# Programming Guide)

`Main` Metoda může vrátit `void`:

[!code-csharp[csProgGuideMain#12](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-return-values_1.cs)]

Můžete také vrátit `int`:

[!code-csharp[csProgGuideMain#13](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-return-values_2.cs)]

Pokud se návratová hodnota z `Main` nepoužívá vrácení `void` umožňuje kód o něco jednodušší. Vrací celé číslo, ale umožňuje programu předávat informace o stavu do jiných programů nebo skriptů, které vyvolají spustitelný soubor. Hodnota vrácená z `Main` je považován za ukončovací kód procesu. Následující příklad ukazuje, jak se návratová hodnota z `Main` je přístupný.

## <a name="example"></a>Příklad

Tento příklad používá [.NET Core](../../../core/index.md) nástroje příkazového řádku. Pokud nejste obeznámeni s nástroji příkazového řádku .NET Core, můžete o nich informace v tomto [tématu Začínáme Get](../../../core/tutorials/using-with-xplat-cli.md).

Upravit `Main` metoda *program.cs* následujícím způsobem:

[!code-csharp[csProgGuideMain#14](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-return-values_3.cs)]

Pokud program je spuštěn ve Windows, libovolná hodnota vrácená z `Main` funkce je uložen v proměnné prostředí. Tato proměnná prostředí se dá načíst pomocí `ERRORLEVEL` z dávkového souboru, nebo `$LastExitCode` z powershellu.

Můžete vytvářet aplikace pomocí [rozhraní příkazového řádku dotnet](../../../core/tools/dotnet.md) `dotnet build` příkazu.

Dále vytvořte skript Powershellu pro spuštění aplikace a zobrazí výsledek. Vložte následující kód do textového souboru a uložte ho jako `test.ps1` ve složce, která obsahuje projekt. Spusťte skript prostředí powershell zadáním `test.ps1` řádku powershellu.

Protože kód vrátí hodnotu 0, dávkový soubor se hlásí úspěch. Pokud změníte MainReturnValTest.cs vrátí nenulovou hodnotu a potom znovu zkompilujete program, ale následné spuštění powershellového skriptu oznámí selhání.

```powershell
dotnet run
if ($LastExitCode -eq 0) {
    Write-Host "Execution succeeded"
} else
{
    Write-Host "Execution Failed"
}
Write-Host "Return value = " $LastExitCode
```

## <a name="sample-output"></a>Ukázkový výstup

```txt
Execution succeeded
Return value = 0
```

## <a name="async-main-return-values"></a>Hlavní asynchronní návratové hodnoty

Asynchronní hlavní vrátit hodnoty přesunout často používaný kód pro volání asynchronních metod `Main` kód generovaný kompilátorem. Dříve byste museli napsat tento konstruktor pro volání asynchronní kód a ujistěte se, že váš program byl dokončen asynchronní operace:

```csharp
public static void Main()
{
    AsyncConsoleWork().GetAwaiter().GetResult();
}

private static async Task<int> AsyncConsoleWork()
{
    // Main body here
    return 0;
}
```

Teď to lze nahradit:

[!code-csharp[AsyncMain](../../../../samples/snippets/csharp/main-arguments/program.cs#AsyncMain)]

Výhodou novou syntaxi je, že kompilátor vždy generovat správný kód.

## <a name="compiler-generated-code"></a>Kód generovaný kompilátorem

Pokud vstupní bod aplikace vrátí `Task` nebo `Task<int>`, kompilátor vygeneruje nový vstupní bod, který volá metodu vstupního bodu, která je deklarována v kódu aplikace. Za předpokladu, že tento vstupní bod se nazývá `$GeneratedMain`, kompilátor generuje následující kód pro tyto vstupní body:

- `static Task Main()` výsledky v kompilátoru generování ekvivalent `private static void $GeneratedMain() => Main().GetAwaiter().GetResult();`
- `static Task Main(string[])` výsledky v kompilátoru generování ekvivalent `private static void $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`
- `static Task<int> Main()` výsledky v kompilátoru generování ekvivalent `private static int $GeneratedMain() => Main().GetAwaiter().GetResult();`
- `static Task<int> Main(string[])` výsledky v kompilátoru generování ekvivalent `private static int $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`

> [!NOTE]
>Pokud se používá v příkladech `async` modifikátor `Main` metoda, kompilátor vygeneruje stejný kód.

## <a name="see-also"></a>Viz také
- [Průvodce programováním v jazyce C#](../../programming-guide/index.md)
- [Referenční dokumentace jazyka C#](../index.md)
- [Argumenty Main() a příkazového řádku](index.md)
- [Postupy: Zobrazení argumentů příkazového řádku](../../programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)
- [Postupy: Přístup k argumentům příkazového řádku pomocí příkazu foreach](../../programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)

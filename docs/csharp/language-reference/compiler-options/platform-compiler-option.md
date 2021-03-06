---
title: -platform (možnosti kompilátoru C#)
ms.date: 07/20/2015
f1_keywords:
- /platform
helpviewer_keywords:
- platform compiler option [C#]
- -platform compiler option [C#]
- /platform compiler option [C#]
ms.assetid: c290ff5e-47f4-4a85-9bb3-9c2525b0be04
ms.openlocfilehash: f52192087eb7b73ee930eea073e0c5716ad8c636
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/04/2018
ms.locfileid: "43507589"
---
# <a name="-platform-c-compiler-options"></a>-platform (možnosti kompilátoru C#)
Určuje, jaké verze Common Language Runtime (CLR) můžete spustit sestavení.  
  
## <a name="syntax"></a>Syntaxe  
  
```console  
-platform:string  
```  
  
#### <a name="parameters"></a>Parametry  
 `string`  
 anycpu (výchozí), anycpu32bitpreferred, ARM, x 64, x86 nebo Itanium.  
  
## <a name="remarks"></a>Poznámky  
  
-   **anycpu** (výchozí) kompiluje sestavení pro spouštěn na libovolné platformě. Vaše aplikace běží jako 64bitový proces, kdykoli je to možné a spadne zpět na 32bitovém základě když pouze tento režim je k dispozici.  
  
-   **anycpu32bitpreferred** zkompiluje vaše sestavení pro spouštěn na libovolné platformě. Vaše aplikace běží v režimu 32-bit na systémy, které podporují 64bitové a 32bitové aplikace. Můžete použít tuto možnost pouze pro projekty, které se zaměřují na rozhraní .NET Framework 4.5.  
  
-   **ARM** kompiluje sestavení ke spuštění v počítači, který má procesor Advanced RISC Machine (ARM).  
  
-   **x64** kompiluje sestavení ke spuštění v 64bitovém modulu CLR na počítači, který podporuje AMD64 nebo EM64T instrukční sadu.  
  
-   **x86** kompiluje sestavení ke spuštění v 32 bitů, které je kompatibilní x86 CLR.  
  
-   **Itanium** kompiluje sestavení ke spuštění v 64bitovém modulu CLR na počítači s procesorem Itanium.  
  
 V operačním systému Windows 64-bit:  
  
-   Sestavení zkompilovaná **-platform: x 86** spouštět na 32-bit CLR spuštěna v modulu WOW64.  
  
-   Knihovna DLL zkompilovaná **– platforma: anycpu** provede na stejném modulu CLR jako proces, do které je načten.  
  
-   Spustitelné soubory, které jsou kompilovány pomocí **-platform: anycpu** spuštění v 64bitovém modulu CLR.  
  
-   Spustitelné soubory zkompilovaná **-platform: anycpu32bitpreferred** spouštět na 32-bit modulu CLR.  
  
 **Anycpu32bitpreferred** nastavení platí jenom pro spustitelný soubor (. Soubory EXE) a vyžaduje rozhraní .NET Framework 4.5.  
  
 Další informace o vývoji aplikací pro spuštění v operačním systému Windows 64-bit, naleznete v tématu [64bitové aplikace](../../../framework/64-bit-apps.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Nastavení tohoto parametru kompilátoru ve vývojovém prostředí Visual Studio  
  
1.  Otevřít **vlastnosti** stránky pro projekt.  
  
2.  Klikněte na tlačítko **sestavení** stránku vlastností.  
  
3.  Upravit **Cílová platforma** vlastnost a pro projekty, které jsou cíleny na rozhraní .NET Framework 4.5, zaškrtněte nebo zrušte zaškrtnutí **preferovat 32bitovou verzi** zaškrtávací políčko.  
  
 **Poznámka: - platform** není k dispozici ve vývojovém prostředí sady Visual C# Express.  
  
 Informace o tom, jak prostřednictvím kódu programu nastavení tohoto parametru kompilátoru najdete v tématu <xref:VSLangProj80.CSharpProjectConfigurationProperties3.PlatformTarget%2A>.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje způsob použití **-platform** možnost určit, že aplikace by měla spustit 64bitový modul CLR v operačním systému Windows 64-bit.  
  
```console  
csc -platform:anycpu filename.cs  
```  
  
## <a name="see-also"></a>Viz také  

- [Možnosti kompilátoru jazyka C#](index.md)  
- [Správa vlastností projektů a řešení](/visualstudio/ide/managing-project-and-solution-properties)

---
title: -sdkpath
ms.date: 07/20/2015
f1_keywords:
- sdkpath
- -sdkpath
helpviewer_keywords:
- -sdkpath compiler option [Visual Basic]
- /sdkpath compiler option [Visual Basic]
- sdkpath compiler option [Visual Basic]
ms.assetid: fec8a3f1-b791-4a37-8af7-344859f8212d
ms.openlocfilehash: bf665082f079901ec45122ce7797090b7519fafe
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/28/2018
ms.locfileid: "50200846"
---
# <a name="-sdkpath"></a>-sdkpath
Určuje umístění knihovny mscorlib.dll a Microsoft.VisualBasic.dll.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
-sdkpath:path  
```  
  
## <a name="arguments"></a>Arguments  
 `path`  
 Adresáře, který obsahuje verze knihovny mscorlib.dll a Microsoft.VisualBasic.dll používat pro kompilaci. Tato cesta není ověřená, dokud jej načíst. Název adresáře uzavřete do uvozovek ("") Pokud obsahuje mezery.  
  
## <a name="remarks"></a>Poznámky  
 Tato možnost informuje kompilátor jazyka Visual Basic se načíst knihovnu mscorlib.dll a Microsoft.VisualBasic.dll soubory z jiné než výchozí umístění. `-sdkpath` Možnost byla navržena pro použití s [- netcf](../../../visual-basic/reference/command-line-compiler/netcf.md). [!INCLUDE[Compact](~/includes/compact-md.md)] Používá různé verze těchto podporu knihoven a vyhněte se použití typů a jazykových funkcí na zařízeních, nebyla nalezena.  
  
> [!NOTE]
>  `-sdkpath` Možnost není k dispozici v rámci vývojového prostředí sady Visual Studio; je k dispozici jenom při kompilaci z příkazového řádku. `-sdkpath` Nastavena možnost při načtení projektu Visual Basic zařízení.  
  
 Můžete určit, že kompilátor by měl kompilovat bez odkazu na knihovnu Runtime jazyka Visual Basic pomocí `-vbruntime` – možnost kompilátoru. Další informace najdete v tématu [- vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md).  
  
## <a name="example"></a>Příklad  
 Následující kód zkompiluje `Myfile.vb` s [!INCLUDE[Compact](~/includes/compact-md.md)], použití verze knihovny Mscorlib.dll a Microsoft.VisualBasic.dll součástí výchozí instalační adresář [!INCLUDE[Compact](~/includes/compact-md.md)] na jednotce C:. Obvykle byste použili nejnovější verzi [!INCLUDE[Compact](~/includes/compact-md.md)].  
  
```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a>Viz také  
 [Kompilátor příkazového řádku jazyka Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Příkazové řádky ukázkové kompilace](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [-netcf](../../../visual-basic/reference/command-line-compiler/netcf.md)  
 [-vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)

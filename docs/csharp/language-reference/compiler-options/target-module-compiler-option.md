---
title: "-target: module (možnosti kompilátoru C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /target:module
helpviewer_keywords:
- -target compiler options [C#], /target:module
- target compiler options [C#], /target:module
- /target compiler options [C#], /target:module
ms.assetid: 9af1e4fa-c749-44e7-ae58-90a3d05d4e72
caps.latest.revision: "11"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 2b54ea9085ecc23d4a535d440d0634c997f22615
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="targetmodule-c-compiler-options"></a><span data-ttu-id="fc440-102">/target:module (Možnosti kompilátoru C#)</span><span class="sxs-lookup"><span data-stu-id="fc440-102">/target:module (C# Compiler Options)</span></span>
<span data-ttu-id="fc440-103">Tato možnost způsobí, že kompilátor není generování manifestu sestavení.</span><span class="sxs-lookup"><span data-stu-id="fc440-103">This option causes the compiler to not generate an assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc440-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="fc440-104">Syntax</span></span>  
  
```console  
/target:module  
```  
  
## <a name="remarks"></a><span data-ttu-id="fc440-105">Poznámky</span><span class="sxs-lookup"><span data-stu-id="fc440-105">Remarks</span></span>  
 <span data-ttu-id="fc440-106">Ve výchozím nastavení bude mít vytvořené kompilace pomocí této možnosti výstupního souboru rozšíření .netmodule.</span><span class="sxs-lookup"><span data-stu-id="fc440-106">By default, the output file created by compiling with this option will have an extension of .netmodule.</span></span>  
  
 <span data-ttu-id="fc440-107">Soubor, který nemá manifest sestavení nelze načíst pomocí modulu CLR rozhraní .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fc440-107">A file that does not have an assembly manifest cannot be loaded by the .NET Framework common language runtime.</span></span> <span data-ttu-id="fc440-108">Však takový soubor může být součástí manifestu sestavení pomocí [/addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="fc440-108">However, such a file can be incorporated into the assembly manifest of an assembly by means of [/addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md).</span></span>  
  
 <span data-ttu-id="fc440-109">Pokud je vytvořen více než jeden modul v jedné kompilaci [interní](../../../csharp/language-reference/keywords/internal.md) typy v jeden modul bude k dispozici pro jiné moduly v kompilace.</span><span class="sxs-lookup"><span data-stu-id="fc440-109">If more than one module is created in a single compilation, [internal](../../../csharp/language-reference/keywords/internal.md) types in one module will be available to other modules in the compilation.</span></span> <span data-ttu-id="fc440-110">Pokud kód odkazuje jeden modul `internal` typy v jiný modul, pak oba moduly musí být začleněny do manifestu sestavení pomocí **/addmodule**.</span><span class="sxs-lookup"><span data-stu-id="fc440-110">When code in one module references `internal` types in another module, then both modules must be incorporated into an assembly manifest, by means of **/addmodule**.</span></span>  
  
 <span data-ttu-id="fc440-111">Vytvoření modulu není podporováno ve vývojovém prostředí sady Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fc440-111">Creating a module is not supported in the Visual Studio development environment.</span></span>  
  
 <span data-ttu-id="fc440-112">Informace o tom, jak nastavení této možnosti kompilátoru programu najdete v tématu <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="fc440-112">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc440-113">Příklad</span><span class="sxs-lookup"><span data-stu-id="fc440-113">Example</span></span>  
 <span data-ttu-id="fc440-114">Kompilace `in.cs`, vytváření `in.netmodule`:</span><span class="sxs-lookup"><span data-stu-id="fc440-114">Compile `in.cs`, creating `in.netmodule`:</span></span>  
  
```console  
csc /target:module in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="fc440-115">Viz také</span><span class="sxs-lookup"><span data-stu-id="fc440-115">See Also</span></span>  
 [<span data-ttu-id="fc440-116">/ target (možnosti kompilátoru C#)</span><span class="sxs-lookup"><span data-stu-id="fc440-116">/target (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/target-compiler-option.md)  
 [<span data-ttu-id="fc440-117">Možnosti kompilátoru C#</span><span class="sxs-lookup"><span data-stu-id="fc440-117">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
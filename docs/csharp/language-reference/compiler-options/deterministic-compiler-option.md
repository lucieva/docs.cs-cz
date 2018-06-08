---
title: -deterministickou (možnosti kompilátoru C#)
ms.date: 04/12/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /deterministic
helpviewer_keywords:
- -deterministic compiler option [C#]
- deterministic compiler option [C#]
- /deterministic compiler option [C#]
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f6dd597f726b5bbc40feb4cc6f5b03acabd92f4a
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/27/2018
---
# <a name="-deterministic"></a><span data-ttu-id="93947-102">-deterministickou</span><span class="sxs-lookup"><span data-stu-id="93947-102">-deterministic</span></span>

<span data-ttu-id="93947-103">Způsobí, že kompilátoru vytvoření sestavení jejichž bajtů pro bajtový výstup je stejný jako napříč kompilace pro identické vstupy.</span><span class="sxs-lookup"><span data-stu-id="93947-103">Causes the compiler to produce an assembly whose byte-for-byte output is identical across compilations for identical inputs.</span></span> 

## <a name="syntax"></a><span data-ttu-id="93947-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="93947-104">Syntax</span></span>

```
-deterministic
```

## <a name="remarks"></a><span data-ttu-id="93947-105">Poznámky</span><span class="sxs-lookup"><span data-stu-id="93947-105">Remarks</span></span>

<span data-ttu-id="93947-106">Ve výchozím nastavení je výstup kompilátoru danou sadu vstupy jedinečné, vzhledem k tomu, že kompilátor přidá časovým razítkem a identifikátor GUID, který se generují z náhodných čísel.</span><span class="sxs-lookup"><span data-stu-id="93947-106">By default, compiler output from a given set of inputs is unique, since the compiler adds a timestamp and a GUID that is generated from random numbers.</span></span> <span data-ttu-id="93947-107">Použijete `-deterministic` možnost k vytvoření *deterministickou sestavení*, jeden jejichž binární obsah je stejný jako napříč kompilace vstup zůstává stejné.</span><span class="sxs-lookup"><span data-stu-id="93947-107">You use the `-deterministic` option to produce a *deterministic assembly*, one whose binary content is identical across compilations as long as the input remains the same.</span></span>

<span data-ttu-id="93947-108">Kompilátor zvažuje následující vstupy pro účely determinism:</span><span class="sxs-lookup"><span data-stu-id="93947-108">The compiler considers the following inputs for the purpose of determinism:</span></span>

- <span data-ttu-id="93947-109">Pořadí parametrů příkazového řádku.</span><span class="sxs-lookup"><span data-stu-id="93947-109">The sequence of command-line parameters.</span></span>
- <span data-ttu-id="93947-110">Obsah souboru kompilátoru .rsp odezvy.</span><span class="sxs-lookup"><span data-stu-id="93947-110">The contents of the compiler's .rsp response file.</span></span>
- <span data-ttu-id="93947-111">Přesné verze kompilátoru použít a jeho odkazované sestavení.</span><span class="sxs-lookup"><span data-stu-id="93947-111">The precise version of the compiler used, and its referenced assemblies.</span></span>
- <span data-ttu-id="93947-112">Cesty k aktuálnímu adresáři.</span><span class="sxs-lookup"><span data-stu-id="93947-112">The current directory path.</span></span>
- <span data-ttu-id="93947-113">Binární obsah všech souborů explicitně předaný kompilátor přímo ani nepřímo, včetně:</span><span class="sxs-lookup"><span data-stu-id="93947-113">The binary contents of all files explicitly passed to the compiler either directly or indirectly, including:</span></span>
    - <span data-ttu-id="93947-114">Zdrojové soubory</span><span class="sxs-lookup"><span data-stu-id="93947-114">Source files</span></span>
    - <span data-ttu-id="93947-115">Odkazovaná sestavení</span><span class="sxs-lookup"><span data-stu-id="93947-115">Referenced assemblies</span></span>
    - <span data-ttu-id="93947-116">Odkazovaná moduly</span><span class="sxs-lookup"><span data-stu-id="93947-116">Referenced modules</span></span>
    - <span data-ttu-id="93947-117">Prostředky</span><span class="sxs-lookup"><span data-stu-id="93947-117">Resources</span></span>
    - <span data-ttu-id="93947-118">Soubor klíče silným názvem</span><span class="sxs-lookup"><span data-stu-id="93947-118">The strong name key file</span></span>
    - <span data-ttu-id="93947-119">@ soubory odezvy</span><span class="sxs-lookup"><span data-stu-id="93947-119">@ response files</span></span>
    - <span data-ttu-id="93947-120">Analyzátory</span><span class="sxs-lookup"><span data-stu-id="93947-120">Analyzers</span></span>
    - <span data-ttu-id="93947-121">Sady pravidel</span><span class="sxs-lookup"><span data-stu-id="93947-121">Rulesets</span></span>
    - <span data-ttu-id="93947-122">Další soubory, které může být používán analyzátory</span><span class="sxs-lookup"><span data-stu-id="93947-122">Additional files that may be used by analyzers</span></span>
- <span data-ttu-id="93947-123">Aktuální jazykové verze (pro jazyk, ve které diagnostiky a výjimky zprávy vytváří).</span><span class="sxs-lookup"><span data-stu-id="93947-123">The current culture (for the language in which diagnostics and exception messages are produced).</span></span>
- <span data-ttu-id="93947-124">Výchozí kódování (nebo aktuální znakovou stránku) Pokud není zadán kódování.</span><span class="sxs-lookup"><span data-stu-id="93947-124">The default encoding (or the current code page) if the encoding is not specified.</span></span>
- <span data-ttu-id="93947-125">Existence, neexistence a obsah souborů na cesty hledání kompilátoru (zadaný, například `/lib` nebo `/recurse`).</span><span class="sxs-lookup"><span data-stu-id="93947-125">The existence, non-existence, and contents of files on the compiler's search paths (specified, for example, by `/lib` or `/recurse`).</span></span>
- <span data-ttu-id="93947-126">Platforma CLR, na kterém je spuštěna kompilátoru.</span><span class="sxs-lookup"><span data-stu-id="93947-126">The CLR platform on which the compiler is run.</span></span>
- <span data-ttu-id="93947-127">Hodnota `%LIBPATH%`, což může ovlivnit načítání závislostí analyzátor.</span><span class="sxs-lookup"><span data-stu-id="93947-127">The value of `%LIBPATH%`, which can affect analyzer dependency loading.</span></span>

<span data-ttu-id="93947-128">Pokud jsou veřejně dostupné zdroje, deterministickou kompilace lze použít pro stanovení, zda se binární kompiluje z důvěryhodného zdroje.</span><span class="sxs-lookup"><span data-stu-id="93947-128">When sources are publicly available, deterministic compilation can be used for establishing whether a binary is compiled from a trusted source.</span></span> <span data-ttu-id="93947-129">Také může být užitečné v systému průběžné sestavení pro určení, jestli není potřeba provést kroky sestavení, které jsou závislé na změny binární.</span><span class="sxs-lookup"><span data-stu-id="93947-129">It can also be useful in a continuous build system for determining whether build steps that are dependent on changes to a binary need to be executed.</span></span> 

## <a name="see-also"></a><span data-ttu-id="93947-130">Viz také</span><span class="sxs-lookup"><span data-stu-id="93947-130">See Also</span></span>  
 [<span data-ttu-id="93947-131">Možnosti kompilátoru jazyka C#</span><span class="sxs-lookup"><span data-stu-id="93947-131">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="93947-132">Správa vlastností projektů a řešení</span><span class="sxs-lookup"><span data-stu-id="93947-132">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
---
title: "-errorreport (možnosti kompilátoru C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /errorreport
helpviewer_keywords:
- -errorreport compiler option [C#]
- errorreport compiler option [C#]
- /errorreport compiler option [C#]
ms.assetid: bd0e7493-b79d-4369-9c3f-ba26ebdfbedf
caps.latest.revision: "35"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3063a29452d90a09d5904d2a598b62530104d739
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="errorreport-c-compiler-options"></a><span data-ttu-id="df172-102">/errorreport (Možnosti kompilátoru C#)</span><span class="sxs-lookup"><span data-stu-id="df172-102">/errorreport (C# Compiler Options)</span></span>
<span data-ttu-id="df172-103">Tato možnost nabízí pohodlný způsob, jak chybu interní kompilátoru C# nahlásit společnosti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="df172-103">This option provides a convenient way to report a C# internal compiler error to Microsoft.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="df172-104">Chyba vytváření sestav nastavení, která učiníte v sadě Visual Studio v systému Windows Vista a Windows Server 2008, nepotlačí nastavení provedená prostřednictvím systému Windows (zasílání chyb).</span><span class="sxs-lookup"><span data-stu-id="df172-104">On Windows Vista and Windows Server 2008, the error reporting settings that you make for Visual Studio do not override the settings made through Windows Error Reporting (WER).</span></span> <span data-ttu-id="df172-105">Nastavení WER vždy mají přednost před nastavením hlášení chyb sady Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="df172-105">WER settings always take precedence over Visual Studio error reporting settings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df172-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="df172-106">Syntax</span></span>  
  
```console  
/errorreport:{ none | prompt | queue | send }  
```  
  
## <a name="arguments"></a><span data-ttu-id="df172-107">Arguments</span><span class="sxs-lookup"><span data-stu-id="df172-107">Arguments</span></span>  
 <span data-ttu-id="df172-108">**None**</span><span class="sxs-lookup"><span data-stu-id="df172-108">**none**</span></span>  
 <span data-ttu-id="df172-109">Zprávy o chybách interní kompilátoru nebudou shromažďovány nebo odesílány do společnosti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="df172-109">Reports about internal compiler errors will not be collected or sent to Microsoft.</span></span>  
  
 <span data-ttu-id="df172-110">**řádku**</span><span class="sxs-lookup"><span data-stu-id="df172-110">**prompt**</span></span>  
 <span data-ttu-id="df172-111">Dotaz, zda chcete poslat zprávu, když obdrží vnitřní chyby kompilátoru.</span><span class="sxs-lookup"><span data-stu-id="df172-111">Prompts you to send a report when you receive an internal compiler error.</span></span> <span data-ttu-id="df172-112">**řádku** je výchozí hodnota při kompilaci aplikace ve vývojovém prostředí.</span><span class="sxs-lookup"><span data-stu-id="df172-112">**prompt** is the default when you compile an application in the development environment.</span></span>  
  
 <span data-ttu-id="df172-113">**fronty**</span><span class="sxs-lookup"><span data-stu-id="df172-113">**queue**</span></span>  
 <span data-ttu-id="df172-114">Fronty zprávy o chybách.</span><span class="sxs-lookup"><span data-stu-id="df172-114">Queues the error report.</span></span> <span data-ttu-id="df172-115">Při přihlášení s přihlašovacími údaji správce může hlásit případných selhání od posledního přihlášení.</span><span class="sxs-lookup"><span data-stu-id="df172-115">When you log on with administrative credentials, you can report any failures since the last time that you were logged on.</span></span> <span data-ttu-id="df172-116">Nebudou vyzváni k odeslání zpráv o selhání více než jednou za tři dny.</span><span class="sxs-lookup"><span data-stu-id="df172-116">You will not be prompted to send reports for failures more than once every three days.</span></span> <span data-ttu-id="df172-117">**fronty** při kompilaci aplikace na příkazovém řádku je výchozí hodnota.</span><span class="sxs-lookup"><span data-stu-id="df172-117">**queue** is the default when you compile an application at the command line.</span></span>  
  
 <span data-ttu-id="df172-118">**Odeslat**</span><span class="sxs-lookup"><span data-stu-id="df172-118">**send**</span></span>  
 <span data-ttu-id="df172-119">Zprávy o chybách interní kompilátoru automaticky odesílá společnosti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="df172-119">Automatically sends reports of internal compiler errors to Microsoft.</span></span> <span data-ttu-id="df172-120">Chcete-li tuto možnost, musíte nejprve souhlasit s zásad shromažďování dat Microsoft.</span><span class="sxs-lookup"><span data-stu-id="df172-120">To enable this option, you must first agree to the Microsoft data collection policy.</span></span> <span data-ttu-id="df172-121">Při prvním zadáte **/errorreport:send** v počítači, bude zpráva kompilátoru odkáže na web, který obsahuje zásady shromažďování dat společnosti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="df172-121">The first time that you specify **/errorreport:send** on a computer, a compiler message will refer you to a Web site that contains the Microsoft data collection policy.</span></span>  
    
## <a name="remarks"></a><span data-ttu-id="df172-122">Poznámky</span><span class="sxs-lookup"><span data-stu-id="df172-122">Remarks</span></span>  
 <span data-ttu-id="df172-123">Vnitřní chyba kompilátoru (LED) nastává kompilátor nemůže zpracovat soubor zdrojového kódu.</span><span class="sxs-lookup"><span data-stu-id="df172-123">An internal compiler error (ICE) results when the compiler cannot process a source code file.</span></span> <span data-ttu-id="df172-124">Když dojde LED, kompilátor nevytváří výstupní soubor nebo užitečnou diagnostiku, můžete použít k opravě kódu.</span><span class="sxs-lookup"><span data-stu-id="df172-124">When an ICE occurs, the compiler does not produce an output file or any useful diagnostic that you can use to fix your code.</span></span>  
  
 <span data-ttu-id="df172-125">V předchozích verzích při přijetí LED, jste vyzváni ke kontaktování oddělení Microsoft Product Support Services nahlásit problém.</span><span class="sxs-lookup"><span data-stu-id="df172-125">In previous releases, when you received an ICE, you were encouraged to contact Microsoft Product Support Services to report the problem.</span></span> <span data-ttu-id="df172-126">Pomocí **/errorreport**, můžete zadat informace LED týmu Visual C#.</span><span class="sxs-lookup"><span data-stu-id="df172-126">By using **/errorreport**, you can provide ICE information to the Visual C# team.</span></span> <span data-ttu-id="df172-127">Zprávy o chybách může pomoct zlepšit budoucí vydání kompilátoru.</span><span class="sxs-lookup"><span data-stu-id="df172-127">Your error reports can help improve future compiler releases.</span></span>  
  
 <span data-ttu-id="df172-128">Schopnost uživatele odesílat zprávy závisí na oprávnění zásad počítače a uživatele.</span><span class="sxs-lookup"><span data-stu-id="df172-128">A user's ability to send reports depends on computer and user policy permissions.</span></span>  
  
 <span data-ttu-id="df172-129">Další informace o ladění chyb naleznete v tématu [Popis zotavení po havárii. Watson pro systém Windows (Drwtsn32.exe)](http://go.microsoft.com/fwlink/?LinkId=147286).</span><span class="sxs-lookup"><span data-stu-id="df172-129">For more information about error debugger, see [Description of the Dr. Watson for Windows (Drwtsn32.exe) Tool](http://go.microsoft.com/fwlink/?LinkId=147286).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="df172-130">Nastavení tohoto parametru kompilátoru ve vývojovém prostředí Visual Studio</span><span class="sxs-lookup"><span data-stu-id="df172-130">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="df172-131">Otevření projektu **vlastnosti** stránky.</span><span class="sxs-lookup"><span data-stu-id="df172-131">Open the project's **Properties** page.</span></span> <span data-ttu-id="df172-132">Další informace najdete v tématu [stránka sestavení, Návrhář projektu (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span><span class="sxs-lookup"><span data-stu-id="df172-132">For more information, see [Build Page, Project Designer (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span></span>  
  
2.  <span data-ttu-id="df172-133">Klikněte **sestavení** stránku vlastností.</span><span class="sxs-lookup"><span data-stu-id="df172-133">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="df172-134">Klikněte **Upřesnit** tlačítko.</span><span class="sxs-lookup"><span data-stu-id="df172-134">Click the **Advanced** button.</span></span>  
  
4.  <span data-ttu-id="df172-135">Změnit **interní hlášení chyb kompilátoru** vlastnost.</span><span class="sxs-lookup"><span data-stu-id="df172-135">Modify the **Internal Compiler Error Reporting** property.</span></span>  
  
 <span data-ttu-id="df172-136">Informace o tom, jak nastavení této možnosti kompilátoru programu najdete v tématu <xref:VSLangProj80.CSharpProjectConfigurationProperties3.ErrorReport%2A>.</span><span class="sxs-lookup"><span data-stu-id="df172-136">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.ErrorReport%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df172-137">Viz také</span><span class="sxs-lookup"><span data-stu-id="df172-137">See Also</span></span>  
 [<span data-ttu-id="df172-138">Možnosti kompilátoru C#</span><span class="sxs-lookup"><span data-stu-id="df172-138">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
---
title: "Začínáme s inkoustem"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- procedural code in lieu of XAML [WPF]
- gradient brush [WPF], animating colors of
- XAML [WPF], procedural code in lieu of
- animation [WPF], gradient brush colors
- brushes [WPF], animating colors of
ms.assetid: 760332dd-594a-475d-865b-01659db8cab7
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: dc8ffe9ad68060d9dfbcafe99133a736237a2bb3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="getting-started-with-ink"></a><span data-ttu-id="458be-102">Začínáme s inkoustem</span><span class="sxs-lookup"><span data-stu-id="458be-102">Getting Started with Ink</span></span>
<span data-ttu-id="458be-103">Zařadit digitálního do svých aplikací je jednodušší než kdy dřív.</span><span class="sxs-lookup"><span data-stu-id="458be-103">Incorporating digital ink into your applications is easier than ever.</span></span> <span data-ttu-id="458be-104">Element Ink byla vyvinuta ze se nezbytným důsledkem metodu COM a systém Windows Forms programování k dosažení úplné integrace do [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="458be-104">Ink has evolved from being a corollary to the COM and Windows Forms method of programming to achieving full integration into the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span> <span data-ttu-id="458be-105">Není nutné k instalaci modulu runtime knihovny nebo samostatné sady SDK.</span><span class="sxs-lookup"><span data-stu-id="458be-105">You do not need to install separate SDKs or runtime libraries.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="458be-106">Požadavky</span><span class="sxs-lookup"><span data-stu-id="458be-106">Prerequisites</span></span>  
 <span data-ttu-id="458be-107">Pokud chcete použít v následujících příkladech, je nutné nejprve nainstalovat Microsoft Visual Studio 2005 a [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)].</span><span class="sxs-lookup"><span data-stu-id="458be-107">To use the following examples, you must first install Microsoft Visual Studio 2005 and the [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)].</span></span> <span data-ttu-id="458be-108">Musíte taky vědět, jak pro psaní aplikací pro [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="458be-108">You should also understand how to write applications for the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span> <span data-ttu-id="458be-109">Další informace o začátcích se [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], najdete v části [návod: Můj první desktopová aplikace WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).</span><span class="sxs-lookup"><span data-stu-id="458be-109">For more information about getting started with the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], see [Walkthrough: My first WPF desktop application](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>  
  
## <a name="quick-start"></a><span data-ttu-id="458be-110">Rychlý Start</span><span class="sxs-lookup"><span data-stu-id="458be-110">Quick Start</span></span>  
 <span data-ttu-id="458be-111">Tato část vám pomůže psát jednoduché [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplikace, která shromažďuje rukopisu.</span><span class="sxs-lookup"><span data-stu-id="458be-111">This section helps you write a simple [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application that collects ink.</span></span>  
  
 <span data-ttu-id="458be-112">Pokud jste tak již neučinili, nainstalujte Microsoft Visual Studio 2005 a [!INCLUDE[TLA#tla_winfxsdk](../../../../includes/tlasharptla-winfxsdk-md.md)].</span><span class="sxs-lookup"><span data-stu-id="458be-112">If you haven't already done so, install Microsoft Visual Studio 2005 and the [!INCLUDE[TLA#tla_winfxsdk](../../../../includes/tlasharptla-winfxsdk-md.md)].</span></span> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="458be-113">aplikace obvykle musí být zkompilovány, abyste mohli zobrazit i v případě, že se skládat pouze z [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="458be-113"> applications usually must be compiled before you can view them, even if they consist entirely of [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="458be-114">Ale [!INCLUDE[TLA#tla_winfxsdk](../../../../includes/tlasharptla-winfxsdk-md.md)] zahrnuje aplikace, aplikaci XamlPad, navržená tak, aby proces implementace [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]– na základě uživatelského rozhraní.</span><span class="sxs-lookup"><span data-stu-id="458be-114">However, the [!INCLUDE[TLA#tla_winfxsdk](../../../../includes/tlasharptla-winfxsdk-md.md)] includes an application, XamlPad, designed to speed up the process of implementing a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-based UI.</span></span> <span data-ttu-id="458be-115">Tuto aplikaci můžete použít k zobrazení a pustíte do optimalizace s první několik ukázky v tomto dokumentu.</span><span class="sxs-lookup"><span data-stu-id="458be-115">You can use that application to view and tinker with the first few samples in this document.</span></span> <span data-ttu-id="458be-116">Proces vytváření kompilované aplikace [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] je popsané dál v tomto dokumentu.</span><span class="sxs-lookup"><span data-stu-id="458be-116">The process of creating compiled applications from [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] is covered later in this document.</span></span>  
  
 <span data-ttu-id="458be-117">Chcete-li spustit aplikaci XAMLPad, klikněte na tlačítko **spustit** nabídky, přejděte na příkaz **všechny programy**, přejděte na **Microsoft Winndows SDK**, přejděte na příkaz **nástroje**a klikněte na tlačítko **Aplikaci XAMLPad**.</span><span class="sxs-lookup"><span data-stu-id="458be-117">To launch XAMLPad, click the **Start** menu, point to **All Programs**, point to **Microsoft Winndows SDK**, point to **Tools**, and click **XAMLPad**.</span></span> <span data-ttu-id="458be-118">V podokně vykreslování vykreslí aplikaci XAMLPad XAML kód napsaný v podokně kódu.</span><span class="sxs-lookup"><span data-stu-id="458be-118">In the rendering pane, XAMLPad renders the XAML code written in the code pane.</span></span> <span data-ttu-id="458be-119">Můžete upravit kód XAML a změny se okamžitě zobrazí v podokně vykreslování.</span><span class="sxs-lookup"><span data-stu-id="458be-119">You can edit the XAML code, and the changes immediately appear in the rendering pane.</span></span>  
  
#### <a name="got-ink"></a><span data-ttu-id="458be-120">Máte rukopisu?</span><span class="sxs-lookup"><span data-stu-id="458be-120">Got Ink?</span></span>  
 <span data-ttu-id="458be-121">Spuštění prvního [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplikace, která podporuje rukopisu:</span><span class="sxs-lookup"><span data-stu-id="458be-121">To start your first [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application that supports ink:</span></span>  
  
1.  <span data-ttu-id="458be-122">Otevřete sadu Microsoft Visual Studio 2005</span><span class="sxs-lookup"><span data-stu-id="458be-122">Open Microsoft Visual Studio 2005</span></span>  
  
2.  <span data-ttu-id="458be-123">Vytvořte novou **aplikace WPF (Windows)**</span><span class="sxs-lookup"><span data-stu-id="458be-123">Create a new **Windows Application (WPF)**</span></span>  
  
3.  <span data-ttu-id="458be-124">Typ `<InkCanvas/>` mezi `<Grid>` značky</span><span class="sxs-lookup"><span data-stu-id="458be-124">Type `<InkCanvas/>` between the `<Grid>` tags</span></span>  
  
4.  <span data-ttu-id="458be-125">Stiskněte klávesu **F5** ke spuštění aplikace v ladicím programu</span><span class="sxs-lookup"><span data-stu-id="458be-125">Press **F5** to launch your application in the debugger</span></span>  
  
5.  <span data-ttu-id="458be-126">Pomocí pera nebo myš, zápis **hello, world** v okně</span><span class="sxs-lookup"><span data-stu-id="458be-126">Using a stylus or mouse, write **hello world** in the window</span></span>  
  
 <span data-ttu-id="458be-127">Napsání ekvivalentní rukopisu "hello, world" aplikace s pouze 12 stisknutí kláves!</span><span class="sxs-lookup"><span data-stu-id="458be-127">You've written the ink equivalent of a "hello world" application with only 12 keystrokes!</span></span>  
  
#### <a name="spice-up-your-application"></a><span data-ttu-id="458be-128">Okořeňte do vaší aplikace</span><span class="sxs-lookup"><span data-stu-id="458be-128">Spice Up Your Application</span></span>  
 <span data-ttu-id="458be-129">Umožňuje využít výhod některé funkce [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="458be-129">Let’s take advantage of some features of the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span>  <span data-ttu-id="458be-130">Nahraďte všechno mezi otevření \<okno > a zavření \</Window > značky s následující kód k získání štětce přechodu pozadí na vaší ploše rukopisu.</span><span class="sxs-lookup"><span data-stu-id="458be-130">Replace everything between the opening \<Window> and closing \</Window> tags with the following markup to get a gradient brush background on your inking surface.</span></span>  
  
 [!code-xaml[DigitalInkTopics#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml#1)]  
[!code-xaml[DigitalInkTopics#1a](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml#1a)]  
  
#### <a name="using-animation"></a><span data-ttu-id="458be-131">Pomocí animace</span><span class="sxs-lookup"><span data-stu-id="458be-131">Using Animation</span></span>  
 <span data-ttu-id="458be-132">Cvičně si můžeme animace barvy štětce přechodu.</span><span class="sxs-lookup"><span data-stu-id="458be-132">For fun, let's animate the colors of the gradient brush.</span></span> <span data-ttu-id="458be-133">Přidejte následující [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] po zavření `</InkCanvas>` značky, ale před uzavírací `</Page>` značky.</span><span class="sxs-lookup"><span data-stu-id="458be-133">Add the following [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] after the closing `</InkCanvas>` tag but before the closing `</Page>` tag.</span></span>  
  
 [!code-xaml[DigitalInkTopics#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml#2)]  
  
#### <a name="adding-some-code-behind-the-xaml"></a><span data-ttu-id="458be-134">Přidání některé kódu XAML</span><span class="sxs-lookup"><span data-stu-id="458be-134">Adding Some Code Behind the XAML</span></span>  
 <span data-ttu-id="458be-135">Při XAML lze velmi snadno návrh uživatelského rozhraní, musí všechny reálné aplikaci přidat kód pro zpracování událostí.</span><span class="sxs-lookup"><span data-stu-id="458be-135">While XAML makes it very easy to design the user interface, any real-world application needs to add code to handle events.</span></span> <span data-ttu-id="458be-136">Zde je jednoduchý příklad, který zvětší rukopisu v reakci na klikněte pravým tlačítkem myši:</span><span class="sxs-lookup"><span data-stu-id="458be-136">Here is a simple example that zooms in on the ink in response to a right-click from a mouse:</span></span>  
  
 <span data-ttu-id="458be-137">Nastavte `MouseRightButtonUp` obslužné rutiny ve vaší [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="458be-137">Set the `MouseRightButtonUp` handler in your [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]:</span></span>  
  
 [!code-xaml[DigitalInkTopics#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#3)]  
  
 <span data-ttu-id="458be-138">V Průzkumníku řešení v sadě Visual Studio rozbalte Windows1.xaml a otevřete soubor modelu code-behind, Window1.xaml.cs nebo Window1.xaml.vb, pokud používáte Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="458be-138">In Visual Studio’s Solution Explorer, expand Windows1.xaml and open the code-behind file, Window1.xaml.cs or Window1.xaml.vb if you are using Visual Basic.</span></span> <span data-ttu-id="458be-139">Přidejte následující kód obslužné rutiny událostí:</span><span class="sxs-lookup"><span data-stu-id="458be-139">Add the following event handler code:</span></span>  
  
 [!code-csharp[DigitalInkTopics#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml.cs#4)]
 [!code-vb[DigitalInkTopics#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window2.xaml.vb#4)]  
  
 <span data-ttu-id="458be-140">Nyní spusťte aplikaci.</span><span class="sxs-lookup"><span data-stu-id="458be-140">Now, run your application.</span></span> <span data-ttu-id="458be-141">Přidat rukopisu a pak klikněte pravým tlačítkem myši nebo provést ekvivalent stiskněte a podržte pomocí pera.</span><span class="sxs-lookup"><span data-stu-id="458be-141">Add some ink and then right-click with the mouse or perform a press-and-hold equivalent with a stylus.</span></span>  
  
#### <a name="using-procedural-code-instead-of-xaml"></a><span data-ttu-id="458be-142">Použití procedurální kódu místo XAML</span><span class="sxs-lookup"><span data-stu-id="458be-142">Using Procedural Code Instead of XAML</span></span>  
 <span data-ttu-id="458be-143">Můžete přístup k veškerým [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] funkce z procedurální kódu.</span><span class="sxs-lookup"><span data-stu-id="458be-143">You can access all [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] features from procedural code.</span></span> <span data-ttu-id="458be-144">Tady je "Hello rukopisu World" aplikaci pro [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , nepoužívá žádné [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] vůbec.</span><span class="sxs-lookup"><span data-stu-id="458be-144">Here is a "Hello Ink World" application for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] that doesn’t use any [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] at all.</span></span> <span data-ttu-id="458be-145">Vložte kód pod do prázdné aplikace konzoly v sadě Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="458be-145">Paste the code below into an empty Console Application in Visual Studio.</span></span> <span data-ttu-id="458be-146">Přidejte odkazy na sestavení PresentationCore PresentationFramework a WindowsBase a sestavte aplikaci stisknutím **F5**:</span><span class="sxs-lookup"><span data-stu-id="458be-146">Add references to the PresentationCore, PresentationFramework, and WindowsBase assemblies, and build the application by pressing **F5**:</span></span>  
  
 [!code-csharp[InkCanvasConsoleApp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasConsoleApp/CSharp/Program.cs#1)]
 [!code-vb[InkCanvasConsoleApp#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InkCanvasConsoleApp/VisualBasic/Module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="458be-147">Viz také</span><span class="sxs-lookup"><span data-stu-id="458be-147">See Also</span></span>  
 [<span data-ttu-id="458be-148">Digitálního pera</span><span class="sxs-lookup"><span data-stu-id="458be-148">Digital Ink</span></span>](../../../../docs/framework/wpf/advanced/digital-ink.md)  
 [<span data-ttu-id="458be-149">Shromažďování rukopisu</span><span class="sxs-lookup"><span data-stu-id="458be-149">Collecting Ink</span></span>](../../../../docs/framework/wpf/advanced/collecting-ink.md)  
 [<span data-ttu-id="458be-150">Rozpoznávání rukopisu</span><span class="sxs-lookup"><span data-stu-id="458be-150">Handwriting Recognition</span></span>](../../../../docs/framework/wpf/advanced/handwriting-recognition.md)  
 [<span data-ttu-id="458be-151">Ukládání rukopisu</span><span class="sxs-lookup"><span data-stu-id="458be-151">Storing Ink</span></span>](../../../../docs/framework/wpf/advanced/storing-ink.md)
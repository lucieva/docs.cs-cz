---
title: "Návod: Ukládání aplikačních dat do mezipaměti v aplikaci WPF"
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
- walkthroughs [WPF], caching
- caching [.NET Framework]
- caching [WPF]
ms.assetid: dac2c9ce-042b-4d23-91eb-28f584415cef
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7c04a2860b46460065a09de3dafedc7010753d36
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-caching-application-data-in-a-wpf-application"></a><span data-ttu-id="37bd3-102">Návod: Ukládání aplikačních dat do mezipaměti v aplikaci WPF</span><span class="sxs-lookup"><span data-stu-id="37bd3-102">Walkthrough: Caching Application Data in a WPF Application</span></span>
<span data-ttu-id="37bd3-103">Ukládání do mezipaměti umožňuje ukládání dat v paměti pro rychlý přístup.</span><span class="sxs-lookup"><span data-stu-id="37bd3-103">Caching enables you to store data in memory for rapid access.</span></span> <span data-ttu-id="37bd3-104">Když je znovu přístupu k datům, aplikací můžete získat data z mezipaměti místo toho je načítání z původního zdroje.</span><span class="sxs-lookup"><span data-stu-id="37bd3-104">When the data is accessed again, applications can get the data from the cache instead retrieving it from the original source.</span></span> <span data-ttu-id="37bd3-105">Tím lze vylepšit výkon a škálovatelnost.</span><span class="sxs-lookup"><span data-stu-id="37bd3-105">This can improve performance and scalability.</span></span> <span data-ttu-id="37bd3-106">Navíc díky ukládání dat do mezipaměti k dispozici při zdroj dat je dočasně nedostupný.</span><span class="sxs-lookup"><span data-stu-id="37bd3-106">In addition, caching makes data available when the data source is temporarily unavailable.</span></span>  
  
 <span data-ttu-id="37bd3-107">[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Poskytuje třídy, které vám umožní používat ukládání do mezipaměti v [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] aplikace.</span><span class="sxs-lookup"><span data-stu-id="37bd3-107">The [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] provides classes that enable you to use caching in [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] applications.</span></span> <span data-ttu-id="37bd3-108">Tyto třídy jsou umístěné v <xref:System.Runtime.Caching> oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="37bd3-108">These classes are located in the <xref:System.Runtime.Caching> namespace.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="37bd3-109"><xref:System.Runtime.Caching> Je nového v oboru názvů [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37bd3-109">The <xref:System.Runtime.Caching> namespace is new in the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span> <span data-ttu-id="37bd3-110">Tento obor názvů umožňuje ukládání do mezipaměti je k dispozici pro všechny [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] aplikace.</span><span class="sxs-lookup"><span data-stu-id="37bd3-110">This namespace makes caching is available to all [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] applications.</span></span> <span data-ttu-id="37bd3-111">V předchozích verzích [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], ukládání do mezipaměti byla k dispozici pouze v <xref:System.Web> obor názvů a proto vyžaduje závislost na třídy technologie ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="37bd3-111">In previous versions of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], caching was available only in the <xref:System.Web> namespace and therefore required a dependency on ASP.NET classes.</span></span>  
  
 <span data-ttu-id="37bd3-112">Tento postup vám ukáže, jak používat funkci ukládání do mezipaměti, který je k dispozici v [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] jako součást [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] aplikace.</span><span class="sxs-lookup"><span data-stu-id="37bd3-112">This walkthrough shows you how to use the caching functionality that is available in the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] as part of a [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="37bd3-113">V tomto návodu mezipaměti obsahu textového souboru.</span><span class="sxs-lookup"><span data-stu-id="37bd3-113">In the walkthrough, you cache the contents of a text file.</span></span>  
  
 <span data-ttu-id="37bd3-114">Tento návod obsahuje následující úlohy:</span><span class="sxs-lookup"><span data-stu-id="37bd3-114">Tasks illustrated in this walkthrough include the following:</span></span>  
  
-   <span data-ttu-id="37bd3-115">Vytvoření projektu aplikace WPF.</span><span class="sxs-lookup"><span data-stu-id="37bd3-115">Creating a WPF application project.</span></span>  
  
-   <span data-ttu-id="37bd3-116">Přidání odkazu na [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37bd3-116">Adding a reference to the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
-   <span data-ttu-id="37bd3-117">Inicializace mezipaměti.</span><span class="sxs-lookup"><span data-stu-id="37bd3-117">Initializing a cache.</span></span>  
  
-   <span data-ttu-id="37bd3-118">Přidání položky mezipaměti obsahující obsah textového souboru.</span><span class="sxs-lookup"><span data-stu-id="37bd3-118">Adding a cache entry that contains the contents of a text file.</span></span>  
  
-   <span data-ttu-id="37bd3-119">Poskytuje zásadu vyřazení položky mezipaměti.</span><span class="sxs-lookup"><span data-stu-id="37bd3-119">Providing an eviction policy for the cache entry.</span></span>  
  
-   <span data-ttu-id="37bd3-120">Sledování cestu k souboru v mezipaměti a oznamování instance mezipaměti o změny monitorovaných položek.</span><span class="sxs-lookup"><span data-stu-id="37bd3-120">Monitoring the path of the cached file and notifying the cache instance about changes to the monitored item.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="37bd3-121">Požadavky</span><span class="sxs-lookup"><span data-stu-id="37bd3-121">Prerequisites</span></span>  
 <span data-ttu-id="37bd3-122">K dokončení tohoto návodu, budete potřebovat:</span><span class="sxs-lookup"><span data-stu-id="37bd3-122">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="37bd3-123">Microsoft [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37bd3-123">Microsoft [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].</span></span>  
  
-   <span data-ttu-id="37bd3-124">Textový soubor, který obsahuje malou část textu.</span><span class="sxs-lookup"><span data-stu-id="37bd3-124">A text file that contains a small amount of text.</span></span> <span data-ttu-id="37bd3-125">(Obsah textového souboru se zobrazí v okně se zprávou.) Kód popsaných v tomto návodu se předpokládá, že pracujete s následující soubor:</span><span class="sxs-lookup"><span data-stu-id="37bd3-125">(You will display the contents of the text file in a message box.) The code illustrated in the walkthrough assumes that you are working with the following file:</span></span>  
  
     `c:\cache\cacheText.txt`  
  
     <span data-ttu-id="37bd3-126">Můžete však použít libovolný textový soubor a provést změny malý kód v tomto návodu.</span><span class="sxs-lookup"><span data-stu-id="37bd3-126">However, you can use any text file and make small changes to the code in this walkthrough.</span></span>  
  
## <a name="creating-a-wpf-application-project"></a><span data-ttu-id="37bd3-127">Vytvoření projektu aplikace WPF</span><span class="sxs-lookup"><span data-stu-id="37bd3-127">Creating a WPF Application Project</span></span>  
 <span data-ttu-id="37bd3-128">Začněte vytvořením projektu aplikace WPF.</span><span class="sxs-lookup"><span data-stu-id="37bd3-128">You will start by creating a WPF application project.</span></span>  
  
#### <a name="to-create-a-wpf-application"></a><span data-ttu-id="37bd3-129">Vytvoření aplikace WPF</span><span class="sxs-lookup"><span data-stu-id="37bd3-129">To create a WPF application</span></span>  
  
1.  <span data-ttu-id="37bd3-130">Spustit [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37bd3-130">Start [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].</span></span>  
  
2.  <span data-ttu-id="37bd3-131">V **soubor** nabídky, klikněte na tlačítko **nový**a potom klikněte na **nový projekt**.</span><span class="sxs-lookup"><span data-stu-id="37bd3-131">In the **File** menu, click **New**, and then click **New Project**.</span></span>  
  
     <span data-ttu-id="37bd3-132">**Nový projekt** se zobrazí dialogové okno.</span><span class="sxs-lookup"><span data-stu-id="37bd3-132">The **New Project** dialog box is displayed.</span></span>  
  
3.  <span data-ttu-id="37bd3-133">V části **nainstalovaných šablonách**, vyberte programovací jazyk, který chcete použít (**jazyka Visual Basic** nebo **Visual C#**).</span><span class="sxs-lookup"><span data-stu-id="37bd3-133">Under **Installed Templates**, select the programming language you want to use (**Visual Basic** or **Visual C#**).</span></span>  
  
4.  <span data-ttu-id="37bd3-134">V **nový projekt** dialogové okno, vyberte **aplikaci WPF**.</span><span class="sxs-lookup"><span data-stu-id="37bd3-134">In the **New Project** dialog box, select **WPF Application**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="37bd3-135">Pokud se nezobrazí **aplikaci WPF** šablony, ujistěte se, že jsou cílení na verzi [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] podporující WPF.</span><span class="sxs-lookup"><span data-stu-id="37bd3-135">If you do not see the **WPF Application** template, make sure that you are targeting a version of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] that supports WPF.</span></span> <span data-ttu-id="37bd3-136">V **nový projekt** dialogové okno, vyberte [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] ze seznamu.</span><span class="sxs-lookup"><span data-stu-id="37bd3-136">In the **New Project** dialog box, select [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] from the list.</span></span>  
  
5.  <span data-ttu-id="37bd3-137">V **název** textové pole, zadejte název pro svůj projekt.</span><span class="sxs-lookup"><span data-stu-id="37bd3-137">In the **Name** text box, enter a name for your project.</span></span> <span data-ttu-id="37bd3-138">Například můžete zadat **WPFCaching**.</span><span class="sxs-lookup"><span data-stu-id="37bd3-138">For example, you can enter **WPFCaching**.</span></span>  
  
6.  <span data-ttu-id="37bd3-139">Vyberte **vytvořit adresář pro řešení** zaškrtávací políčko.</span><span class="sxs-lookup"><span data-stu-id="37bd3-139">Select the **Create directory for solution** check box.</span></span>  
  
7.  <span data-ttu-id="37bd3-140">Click **OK**.</span><span class="sxs-lookup"><span data-stu-id="37bd3-140">Click **OK**.</span></span>  
  
     <span data-ttu-id="37bd3-141">WPF Designer se otevře v **návrhu** zobrazení a zobrazí MainWindow.xaml soubor.</span><span class="sxs-lookup"><span data-stu-id="37bd3-141">The WPF Designer opens in **Design** view and displays the MainWindow.xaml file.</span></span> [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]<span data-ttu-id="37bd3-142">vytvoří **Můj projekt** složka, soubor Application.xaml a soubor MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="37bd3-142"> creates the **My Project** folder, the Application.xaml file, and the MainWindow.xaml file.</span></span>  
  
## <a name="targeting-the-net-framework-and-adding-a-reference-to-the-caching-assemblies"></a><span data-ttu-id="37bd3-143">Cílení na rozhraní .NET Framework a přidáním odkazu na ukládání do mezipaměti sestavení</span><span class="sxs-lookup"><span data-stu-id="37bd3-143">Targeting the .NET Framework and Adding a Reference to the Caching Assemblies</span></span>  
 <span data-ttu-id="37bd3-144">Ve výchozím nastavení, cílové aplikace WPF [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37bd3-144">By default, WPF applications target the [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)].</span></span> <span data-ttu-id="37bd3-145">Použít <xref:System.Runtime.Caching> oboru názvů v aplikaci WPF, aplikace musí mít jako cíl [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] (není [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)]) a musí obsahovat odkaz na obor názvů.</span><span class="sxs-lookup"><span data-stu-id="37bd3-145">To use the <xref:System.Runtime.Caching> namespace in a WPF application, the application must target the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] (not the [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)]) and must include a reference to the namespace.</span></span>  
  
 <span data-ttu-id="37bd3-146">Proto je dalším krokem je změnit cíl rozhraní .NET Framework a přidat odkaz na <xref:System.Runtime.Caching> oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="37bd3-146">Therefore, the next step is to change the .NET Framework target and add a reference to the <xref:System.Runtime.Caching> namespace.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="37bd3-147">Postup pro změnu cílové rozhraní .NET Framework se liší v projektu jazyka Visual Basic a v projektu jazyka Visual C#.</span><span class="sxs-lookup"><span data-stu-id="37bd3-147">The procedure for changing the .NET Framework target is different in a Visual Basic project and in a Visual C# project.</span></span>  
  
#### <a name="to-change-the-target-net-framework-in-visual-basic"></a><span data-ttu-id="37bd3-148">Chcete-li změnit cíl rozhraní .NET Framework v jazyce Visual Basic</span><span class="sxs-lookup"><span data-stu-id="37bd3-148">To change the target .NET Framework in Visual Basic</span></span>  
  
1.  <span data-ttu-id="37bd3-149">V **Průzkumníka řešení**, klikněte pravým tlačítkem na název projektu a pak klikněte na tlačítko **vlastnosti**.</span><span class="sxs-lookup"><span data-stu-id="37bd3-149">In **Solutions Explorer**, right-click the project name, and then click **Properties**.</span></span>  
  
     <span data-ttu-id="37bd3-150">Zobrazí se okno Vlastnosti pro aplikaci.</span><span class="sxs-lookup"><span data-stu-id="37bd3-150">The properties window for the application is displayed.</span></span>  
  
2.  <span data-ttu-id="37bd3-151">Klikněte **zkompilovat** kartě.</span><span class="sxs-lookup"><span data-stu-id="37bd3-151">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="37bd3-152">V dolní části okna klikněte na tlačítko **Upřesnit možnosti kompilace...** .</span><span class="sxs-lookup"><span data-stu-id="37bd3-152">At the bottom of the window, click **Advanced Compile Options…**.</span></span>  
  
     <span data-ttu-id="37bd3-153">**Upřesnit nastavení kompilátoru** se zobrazí dialogové okno.</span><span class="sxs-lookup"><span data-stu-id="37bd3-153">The **Advanced Compiler Settings** dialog box is displayed.</span></span>  
  
4.  <span data-ttu-id="37bd3-154">V **cílové rozhraní (všechny konfigurace)** seznamu, vyberte [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37bd3-154">In the **Target framework (all configurations)** list, select [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span> <span data-ttu-id="37bd3-155">(Nevybírejte [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)].)</span><span class="sxs-lookup"><span data-stu-id="37bd3-155">(Do not select [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)].)</span></span>  
  
5.  <span data-ttu-id="37bd3-156">Click **OK**.</span><span class="sxs-lookup"><span data-stu-id="37bd3-156">Click **OK**.</span></span>  
  
     <span data-ttu-id="37bd3-157">**Změnit cílový Framework** se zobrazí dialogové okno.</span><span class="sxs-lookup"><span data-stu-id="37bd3-157">The **Target Framework Change** dialog box is displayed.</span></span>  
  
6.  <span data-ttu-id="37bd3-158">V **změnit cílový Framework** dialogové okno, klikněte na tlačítko **Ano**.</span><span class="sxs-lookup"><span data-stu-id="37bd3-158">In the **Target Framework Change** dialog box, click **Yes**.</span></span>  
  
     <span data-ttu-id="37bd3-159">Projekt se zavře a pak znovu otevřete.</span><span class="sxs-lookup"><span data-stu-id="37bd3-159">The project is closed and is then reopened.</span></span>  
  
7.  <span data-ttu-id="37bd3-160">Přidáte odkaz na sestavení ukládání do mezipaměti pomocí následujících kroků:</span><span class="sxs-lookup"><span data-stu-id="37bd3-160">Add a reference to the caching assembly by following these steps:</span></span>  
  
    1.  <span data-ttu-id="37bd3-161">V **Průzkumníku řešení**, klikněte pravým tlačítkem na název projektu a pak klikněte na tlačítko **přidat odkaz na**.</span><span class="sxs-lookup"><span data-stu-id="37bd3-161">In **Solution Explorer**, right-click the name of the project and then click **Add Reference**.</span></span>  
  
    2.  <span data-ttu-id="37bd3-162">Vyberte **.NET** vyberte `System.Runtime.Caching`a potom klikněte na **OK**.</span><span class="sxs-lookup"><span data-stu-id="37bd3-162">Select the **.NET** tab, select `System.Runtime.Caching`, and then click **OK**.</span></span>  
  
#### <a name="to-change-the-target-net-framework-in-a-visual-c-project"></a><span data-ttu-id="37bd3-163">Chcete-li změnit cíl rozhraní .NET Framework v projektu jazyka Visual C#</span><span class="sxs-lookup"><span data-stu-id="37bd3-163">To change the target .NET Framework in a Visual C# project</span></span>  
  
1.  <span data-ttu-id="37bd3-164">V **Průzkumníku řešení**, klikněte pravým tlačítkem na název projektu a pak klikněte na tlačítko **vlastnosti**.</span><span class="sxs-lookup"><span data-stu-id="37bd3-164">In **Solution Explorer**, right-click the project name and then click **Properties**.</span></span>  
  
     <span data-ttu-id="37bd3-165">Zobrazí se okno Vlastnosti pro aplikaci.</span><span class="sxs-lookup"><span data-stu-id="37bd3-165">The properties window for the application is displayed.</span></span>  
  
2.  <span data-ttu-id="37bd3-166">Klikněte **aplikace** kartě.</span><span class="sxs-lookup"><span data-stu-id="37bd3-166">Click the **Application** tab.</span></span>  
  
3.  <span data-ttu-id="37bd3-167">V **cílové rozhraní** seznamu, vyberte [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37bd3-167">In the **Target framework** list, select [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span> <span data-ttu-id="37bd3-168">(Nevybírejte **rozhraní .NET Framework 4 Client Profile**.)</span><span class="sxs-lookup"><span data-stu-id="37bd3-168">(Do not select **.NET Framework 4 Client Profile**.)</span></span>  
  
4.  <span data-ttu-id="37bd3-169">Přidáte odkaz na sestavení ukládání do mezipaměti pomocí následujících kroků:</span><span class="sxs-lookup"><span data-stu-id="37bd3-169">Add a reference to the caching assembly by following these steps:</span></span>  
  
    1.  <span data-ttu-id="37bd3-170">Klikněte pravým tlačítkem myši **odkazy** složku a pak klikněte na tlačítko **přidat odkaz na**.</span><span class="sxs-lookup"><span data-stu-id="37bd3-170">Right-click the **References** folder and then click **Add Reference**.</span></span>  
  
    2.  <span data-ttu-id="37bd3-171">Vyberte **.NET** vyberte `System.Runtime.Caching`a potom klikněte na **OK**.</span><span class="sxs-lookup"><span data-stu-id="37bd3-171">Select the **.NET** tab, select `System.Runtime.Caching`, and then click **OK**.</span></span>  
  
## <a name="adding-a-button-to-the-wpf-window"></a><span data-ttu-id="37bd3-172">Přidání tlačítka do okna WPF</span><span class="sxs-lookup"><span data-stu-id="37bd3-172">Adding a Button to the WPF Window</span></span>  
 <span data-ttu-id="37bd3-173">V dalším kroku přidáte ovládacího prvku tlačítko a vytvoření obslužné rutiny události pro tlačítka `Click` událostí.</span><span class="sxs-lookup"><span data-stu-id="37bd3-173">Next, you will add a button control and create an event handler for the button's `Click` event.</span></span> <span data-ttu-id="37bd3-174">Kód pro později přidáte tak, aby po kliknutí na tlačítko, jsou do mezipaměti a zobrazí obsah textového souboru.</span><span class="sxs-lookup"><span data-stu-id="37bd3-174">Later you will add code to so when you click the button, the contents of the text file are cached and displayed.</span></span>  
  
#### <a name="to-add-a-button-control"></a><span data-ttu-id="37bd3-175">Přidání ovládacího prvku tlačítko</span><span class="sxs-lookup"><span data-stu-id="37bd3-175">To add a button control</span></span>  
  
1.  <span data-ttu-id="37bd3-176">V **Průzkumníku**, poklikejte na soubor MainWindow.xaml ho otevřete.</span><span class="sxs-lookup"><span data-stu-id="37bd3-176">In **Solution Explorer**, double-click the MainWindow.xaml file to open it.</span></span>  
  
2.  <span data-ttu-id="37bd3-177">Z **sada nástrojů**v části **běžných ovládacích prvků WPF**, přetáhněte ji `Button` řídit k `MainWindow` okno.</span><span class="sxs-lookup"><span data-stu-id="37bd3-177">From the **Toolbox**, under **Common WPF Controls**, drag a `Button` control to the `MainWindow` window.</span></span>  
  
3.  <span data-ttu-id="37bd3-178">V **vlastnosti** nastavte `Content` vlastnost `Button` řídit k **získat mezipaměti**.</span><span class="sxs-lookup"><span data-stu-id="37bd3-178">In the **Properties** window, set the `Content` property of the `Button` control to **Get Cache**.</span></span>  
  
## <a name="initializing-the-cache-and-caching-an-entry"></a><span data-ttu-id="37bd3-179">Inicializace mezipaměti a ukládání do mezipaměti položku</span><span class="sxs-lookup"><span data-stu-id="37bd3-179">Initializing the Cache and Caching an Entry</span></span>  
 <span data-ttu-id="37bd3-180">Dále přidáte kód, který provádět následující úlohy:</span><span class="sxs-lookup"><span data-stu-id="37bd3-180">Next, you will add the code to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="37bd3-181">Vytvoření instance třídy mezipaměti – to znamená, že vytvoříte instanci novou <xref:System.Runtime.Caching.MemoryCache> objektu.</span><span class="sxs-lookup"><span data-stu-id="37bd3-181">Create an instance of the cache class—that is, you will instantiate a new <xref:System.Runtime.Caching.MemoryCache> object.</span></span>  
  
-   <span data-ttu-id="37bd3-182">Zadejte, že mezipaměť používá <xref:System.Runtime.Caching.HostFileChangeMonitor> objekt, který chcete sledovat změny v textovém souboru.</span><span class="sxs-lookup"><span data-stu-id="37bd3-182">Specify that the cache uses a <xref:System.Runtime.Caching.HostFileChangeMonitor> object to monitor changes in the text file.</span></span>  
  
-   <span data-ttu-id="37bd3-183">Čtení textového souboru a jeho obsah do mezipaměti jako položku mezipaměti.</span><span class="sxs-lookup"><span data-stu-id="37bd3-183">Read the text file and cache its contents as a cache entry.</span></span>  
  
-   <span data-ttu-id="37bd3-184">Zobrazte obsah v mezipaměti textového souboru.</span><span class="sxs-lookup"><span data-stu-id="37bd3-184">Display the contents of the cached text file.</span></span>  
  
#### <a name="to-create-the-cache-object"></a><span data-ttu-id="37bd3-185">Chcete-li vytvořit objekt mezipaměti</span><span class="sxs-lookup"><span data-stu-id="37bd3-185">To create the cache object</span></span>  
  
1.  <span data-ttu-id="37bd3-186">Dvakrát klikněte na tlačítko, které jste právě přidali, aby bylo možné vytvořit obslužnou rutinu události v souboru MainWindow.xaml.cs nebo MainWindow.Xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="37bd3-186">Double-click the button you just added in order to create an event handler in the MainWindow.xaml.cs or MainWindow.Xaml.vb file.</span></span>  
  
2.  <span data-ttu-id="37bd3-187">V horní části souboru (před deklaraci třídy), přidejte následující `Imports` (Visual Basic) nebo `using` příkazy (C#):</span><span class="sxs-lookup"><span data-stu-id="37bd3-187">At the top of the file (before the class declaration), add the following `Imports` (Visual Basic) or `using` (C#) statements:</span></span>  
  
    ```csharp  
    using System.Runtime.Caching;  
    using System.IO;  
    ```  
  
    ```vb  
    Imports System.Runtime.Caching  
    Imports System.IO  
    ```  
  
3.  <span data-ttu-id="37bd3-188">V obslužné rutině přidejte následující kód k vytvoření instance objektu mezipaměti:</span><span class="sxs-lookup"><span data-stu-id="37bd3-188">In the event handler, add the following code to instantiate the cache object:</span></span>  
  
    ```csharp  
    ObjectCache cache = MemoryCache.Default;  
    ```  
  
    ```vb  
    Dim cache As ObjectCache = MemoryCache.Default  
    ```  
  
     <span data-ttu-id="37bd3-189"><xref:System.Runtime.Caching.ObjectCache> Třída je předdefinovaný třídu, která poskytuje mezipaměti objektů v paměti.</span><span class="sxs-lookup"><span data-stu-id="37bd3-189">The <xref:System.Runtime.Caching.ObjectCache> class is a built-in class that provides an in-memory object cache.</span></span>  
  
4.  <span data-ttu-id="37bd3-190">Přidejte následující kód ke čtení obsahu položky mezipaměti s názvem `filecontents`:</span><span class="sxs-lookup"><span data-stu-id="37bd3-190">Add the following code to read the contents of a cache entry named `filecontents`:</span></span>  
  
    ```vb  
    Dim fileContents As String = TryCast(cache("filecontents"), String)  
    ```  
  
    ```csharp  
    string fileContents = cache["filecontents"] as string;  
    ```  
  
5.  <span data-ttu-id="37bd3-191">Přidejte následující kód, který zkontrolujte, zda položka mezipaměti s názvem `filecontents` existuje:</span><span class="sxs-lookup"><span data-stu-id="37bd3-191">Add the following code to check whether the cache entry named `filecontents` exists:</span></span>  
  
    ```vb  
    If fileContents Is Nothing Then  
  
    End If  
    ```  
  
    ```csharp  
    if (fileContents == null)  
    {  
  
    }  
    ```  
  
     <span data-ttu-id="37bd3-192">Pokud určená položka mezipaměti neexistuje, musíte čtení textového souboru a přidejte jej jako položku mezipaměti do mezipaměti.</span><span class="sxs-lookup"><span data-stu-id="37bd3-192">If the specified cache entry does not exist, you must read the text file and add it as a cache entry to the cache.</span></span>  
  
6.  <span data-ttu-id="37bd3-193">V `if/then` blokovat, přidejte následující kód k vytvoření nové <xref:System.Runtime.Caching.CacheItemPolicy> objekt, který určuje, že položky mezipaměti vyprší po 10 sekundách.</span><span class="sxs-lookup"><span data-stu-id="37bd3-193">In the `if/then` block, add the following code to create a new <xref:System.Runtime.Caching.CacheItemPolicy> object that specifies that the cache entry expires after 10 seconds.</span></span>  
  
    ```vb  
    Dim policy As New CacheItemPolicy()  
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0)  
    ```  
  
    ```csharp  
    CacheItemPolicy policy = new CacheItemPolicy();  
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0);  
    ```  
  
     <span data-ttu-id="37bd3-194">Pokud je zadaný žádné informace o vyřazení nebo vypršení platnosti, výchozí hodnota je <xref:System.Runtime.Caching.ObjectCache.InfiniteAbsoluteExpiration>, což znamená, že položky mezipaměti vyprší na základě nikdy pouze na absolutním čase.</span><span class="sxs-lookup"><span data-stu-id="37bd3-194">If no eviction or expiration information is provided, the default is <xref:System.Runtime.Caching.ObjectCache.InfiniteAbsoluteExpiration>, which means the cache entries never expire based only on an absolute time.</span></span> <span data-ttu-id="37bd3-195">Místo toho platnost položky mezipaměti jenom v případě, že je přetížení paměti.</span><span class="sxs-lookup"><span data-stu-id="37bd3-195">Instead, cache entries expire only when there is memory pressure.</span></span> <span data-ttu-id="37bd3-196">Jako osvědčený postup je vhodné vždy explicitně zadat absolutní nebo vedlejší vypršení platnosti.</span><span class="sxs-lookup"><span data-stu-id="37bd3-196">As a best practice, you should always explicitly provide either an absolute or a siding expiration.</span></span>  
  
7.  <span data-ttu-id="37bd3-197">Uvnitř `if/then` blokovat a následující kód, který jste přidali v předchozím kroku, přidejte následující kód k vytvoření kolekce cest souborů, které chcete monitorovat a přidejte cestu k textovému souboru do kolekce:</span><span class="sxs-lookup"><span data-stu-id="37bd3-197">Inside the `if/then` block and following the code you added in the previous step, add the following code to create a collection for the file paths that you want to monitor, and to add the path of the text file to the collection:</span></span>  
  
    ```vb  
    Dim filePaths As New List(Of String)()  
    filePaths.Add("c:\cache\cacheText.txt")  
    ```  
  
    ```csharp  
    List<string> filePaths = new List<string>();  
    filePaths.Add("c:\\cache\\cacheText.txt");  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="37bd3-198">Pokud není textový soubor, který chcete použít `c:\cache\cacheText.txt`, zadejte cestu k umístění textového souboru, kterou chcete použít.</span><span class="sxs-lookup"><span data-stu-id="37bd3-198">If the text file you want to use is not `c:\cache\cacheText.txt`, specify the path where the text file is that you want to use.</span></span>  
  
8.  <span data-ttu-id="37bd3-199">Následující kód, který jste přidali v předchozím kroku, přidejte následující kód přidejte nový <xref:System.Runtime.Caching.HostFileChangeMonitor> objektu do kolekce změny monitoruje položky mezipaměti:</span><span class="sxs-lookup"><span data-stu-id="37bd3-199">Following the code that you added in the previous step, add the following code to add a new <xref:System.Runtime.Caching.HostFileChangeMonitor> object to the collection of change monitors for the cache entry:</span></span>  
  
    ```vb  
    policy.ChangeMonitors.Add(New HostFileChangeMonitor(filePaths))  
    ```  
  
    ```csharp  
    policy.ChangeMonitors.Add(new HostFileChangeMonitor(filePaths));  
    ```  
  
     <span data-ttu-id="37bd3-200"><xref:System.Runtime.Caching.HostFileChangeMonitor> Objekt monitoruje cesta k textovému souboru a upozorní mezipaměti, pokud dojde ke změnám.</span><span class="sxs-lookup"><span data-stu-id="37bd3-200">The <xref:System.Runtime.Caching.HostFileChangeMonitor> object monitors the text file's path and notifies the cache if changes occur.</span></span> <span data-ttu-id="37bd3-201">V tomto příkladu položky mezipaměti vyprší, pokud se změní obsah souboru.</span><span class="sxs-lookup"><span data-stu-id="37bd3-201">In this example, the cache entry will expire if the content of the file changes.</span></span>  
  
9. <span data-ttu-id="37bd3-202">Následující kód, který jste přidali v předchozím kroku přidejte následující kód ke čtení obsahu textového souboru:</span><span class="sxs-lookup"><span data-stu-id="37bd3-202">Following the code that you added in the previous step, add the following code to read the contents of the text file:</span></span>  
  
    ```vb  
    fileContents = File.ReadAllText("c:\cache\cacheText.txt") & vbCrLf & DateTime.Now.ToString()  
    ```  
  
    ```csharp  
    fileContents = File.ReadAllText("c:\\cache\\cacheText.txt") + + "\n" + DateTime.Now;   
    ```  
  
     <span data-ttu-id="37bd3-203">Datum a čas časové razítko je přidat tak, že nebudete moci zobrazit, když vyprší platnost položky mezipaměti.</span><span class="sxs-lookup"><span data-stu-id="37bd3-203">The date and time timestamp is added so that you will be able to see when the cache entry expires.</span></span>  
  
10. <span data-ttu-id="37bd3-204">Následující kód, který jste přidali v předchozím kroku, přidejte následující kód pro vložení do objektu mezipaměti jako obsah souboru <xref:System.Runtime.Caching.CacheItem> instance:</span><span class="sxs-lookup"><span data-stu-id="37bd3-204">Following the code that you added in the previous step, add the following code to insert the contents of the file into the cache object as a <xref:System.Runtime.Caching.CacheItem> instance:</span></span>  
  
    ```vb  
    cache.Set("filecontents", fileContents, policy)  
    ```  
  
    ```csharp  
    cache.Set("filecontents", fileContents, policy);  
    ```  
  
     <span data-ttu-id="37bd3-205">Zadejte informace o tom, jak by měla být položky mezipaměti pomocí předání vyřazena <xref:System.Runtime.Caching.CacheItemPolicy> objekt, který jste vytvořili dříve jako parametr.</span><span class="sxs-lookup"><span data-stu-id="37bd3-205">You specify information about how the cache entry should be evicted by passing the <xref:System.Runtime.Caching.CacheItemPolicy> object that you created earlier as a parameter.</span></span>  
  
11. <span data-ttu-id="37bd3-206">Po `if/then` blokovat, přidejte následující kód k zobrazení souborů uložených v mezipaměti obsahu v okně se zprávou:</span><span class="sxs-lookup"><span data-stu-id="37bd3-206">After the `if/then` block, add the following code to display the cached file content in a message box:</span></span>  
  
    ```vb  
    MessageBox.Show(fileContents)  
    ```  
  
    ```csharp  
    MessageBox.Show(fileContents);  
    ```  
  
12. <span data-ttu-id="37bd3-207">V **sestavení** nabídky, klikněte na tlačítko **sestavení WPFCaching** k sestavení projektu.</span><span class="sxs-lookup"><span data-stu-id="37bd3-207">In the **Build** menu, click **Build WPFCaching** to build your project.</span></span>  
  
## <a name="testing-caching-in-the-wpf-application"></a><span data-ttu-id="37bd3-208">Testování ukládání do mezipaměti v aplikaci WPF</span><span class="sxs-lookup"><span data-stu-id="37bd3-208">Testing Caching in the WPF Application</span></span>  
 <span data-ttu-id="37bd3-209">Nyní můžete aplikaci otestovat.</span><span class="sxs-lookup"><span data-stu-id="37bd3-209">You can now test the application.</span></span>  
  
#### <a name="to-test-caching-in-the-wpf-application"></a><span data-ttu-id="37bd3-210">K testování ukládání do mezipaměti v aplikaci WPF</span><span class="sxs-lookup"><span data-stu-id="37bd3-210">To test caching in the WPF application</span></span>  
  
1.  <span data-ttu-id="37bd3-211">Stisknutím kombinace kláves CTRL + F5 a spusťte aplikaci.</span><span class="sxs-lookup"><span data-stu-id="37bd3-211">Press CTRL+F5 to run the application.</span></span>  
  
     <span data-ttu-id="37bd3-212">`MainWindow` Zobrazí se okno.</span><span class="sxs-lookup"><span data-stu-id="37bd3-212">The `MainWindow` window is displayed.</span></span>  
  
2.  <span data-ttu-id="37bd3-213">Klikněte na tlačítko **získat mezipaměti**.</span><span class="sxs-lookup"><span data-stu-id="37bd3-213">Click **Get Cache**.</span></span>  
  
     <span data-ttu-id="37bd3-214">Obsah uložený v mezipaměti z textového souboru se zobrazí v okně se zprávou.</span><span class="sxs-lookup"><span data-stu-id="37bd3-214">The cached content from the text file is displayed in a message box.</span></span> <span data-ttu-id="37bd3-215">Všimněte si, časové razítko souboru.</span><span class="sxs-lookup"><span data-stu-id="37bd3-215">Notice the timestamp on the file.</span></span>  
  
3.  <span data-ttu-id="37bd3-216">Zavřete okno se zprávou a pak klikněte na tlačítko **získat mezipaměti** znovu**.**</span><span class="sxs-lookup"><span data-stu-id="37bd3-216">Close the message box and then click **Get Cache** again**.**</span></span>  
  
     <span data-ttu-id="37bd3-217">Časové razítko je beze změny.</span><span class="sxs-lookup"><span data-stu-id="37bd3-217">The timestamp is unchanged.</span></span> <span data-ttu-id="37bd3-218">To znamená, že se zobrazí obsah v mezipaměti.</span><span class="sxs-lookup"><span data-stu-id="37bd3-218">This indicates the cached content is displayed.</span></span>  
  
4.  <span data-ttu-id="37bd3-219">Počkejte 10 sekund nebo více a pak klikněte na tlačítko **získat mezipaměti** znovu.</span><span class="sxs-lookup"><span data-stu-id="37bd3-219">Wait 10 seconds or more and then click **Get Cache** again.</span></span>  
  
     <span data-ttu-id="37bd3-220">Tento čas se zobrazí nový časové razítko.</span><span class="sxs-lookup"><span data-stu-id="37bd3-220">This time a new timestamp is displayed.</span></span> <span data-ttu-id="37bd3-221">To znamená, že zásady umožňují vypršení platnosti položky mezipaměti a že se zobrazí nový obsah v mezipaměti.</span><span class="sxs-lookup"><span data-stu-id="37bd3-221">This indicates that the policy let the cache entry expire and that new cached content is displayed.</span></span>  
  
5.  <span data-ttu-id="37bd3-222">V textovém editoru otevřete textový soubor, který jste vytvořili.</span><span class="sxs-lookup"><span data-stu-id="37bd3-222">In a text editor, open the text file that you created.</span></span> <span data-ttu-id="37bd3-223">Zatím neprovádějte žádné změny.</span><span class="sxs-lookup"><span data-stu-id="37bd3-223">Do not make any changes yet.</span></span>  
  
6.  <span data-ttu-id="37bd3-224">Zavřete okno se zprávou a pak klikněte na tlačítko **získat mezipaměti** znovu**.**</span><span class="sxs-lookup"><span data-stu-id="37bd3-224">Close the message box and then click **Get Cache** again**.**</span></span>  
  
     <span data-ttu-id="37bd3-225">Všimněte si znovu časové razítko.</span><span class="sxs-lookup"><span data-stu-id="37bd3-225">Notice the timestamp again.</span></span>  
  
7.  <span data-ttu-id="37bd3-226">Změňte na textový soubor a pak soubor uložte.</span><span class="sxs-lookup"><span data-stu-id="37bd3-226">Make a change to the text file and then save the file.</span></span>  
  
8.  <span data-ttu-id="37bd3-227">Zavřete okno se zprávou a pak klikněte na tlačítko **získat mezipaměti** znovu.</span><span class="sxs-lookup"><span data-stu-id="37bd3-227">Close the message box and then click **Get Cache** again.</span></span>  
  
     <span data-ttu-id="37bd3-228">Toto okno se zprávou obsahuje aktualizovaný obsah z textového souboru a nové časové razítko.</span><span class="sxs-lookup"><span data-stu-id="37bd3-228">This message box contains the updated content from the text file and a new timestamp.</span></span> <span data-ttu-id="37bd3-229">To znamená, že soubor hostitele sledování změn vyřazování položky mezipaměti okamžitě, pokud jste změnili soubor, i když kdyby vypršel absolutní časový limit.</span><span class="sxs-lookup"><span data-stu-id="37bd3-229">This indicates that the host-file change monitor evicted the cache entry immediately when you changed the file, even though the absolute timeout period had not expired.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="37bd3-230">Může se prodloužit doba vyřazení na 20 sekund nebo více času pro vás k provedení změny v souboru.</span><span class="sxs-lookup"><span data-stu-id="37bd3-230">You can increase the eviction time to 20 seconds or more to allow more time for you to make a change in the file.</span></span>  
  
## <a name="code-example"></a><span data-ttu-id="37bd3-231">Příklad kódu</span><span class="sxs-lookup"><span data-stu-id="37bd3-231">Code Example</span></span>  
 <span data-ttu-id="37bd3-232">Po dokončení tohoto průvodce, kód pro projekt, který jste vytvořili bude vypadat podobně jako v následujícím příkladu.</span><span class="sxs-lookup"><span data-stu-id="37bd3-232">After you have completed this walkthrough, the code for the project you created will resemble the following example.</span></span>  
  
 [!code-csharp[CachingWPFApplications#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CachingWPFApplications/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[CachingWPFApplications#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CachingWPFApplications/VisualBasic/MainWindow.xaml.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="37bd3-233">Viz také</span><span class="sxs-lookup"><span data-stu-id="37bd3-233">See Also</span></span>  
 <xref:System.Runtime.Caching.MemoryCache>  
 <xref:System.Runtime.Caching.ObjectCache>  
 <xref:System.Runtime.Caching>  
 [<span data-ttu-id="37bd3-234">Ukládání do mezipaměti v aplikacích .NET Framework</span><span class="sxs-lookup"><span data-stu-id="37bd3-234">Caching in .NET Framework Applications</span></span>](../../../../docs/framework/performance/caching-in-net-framework-applications.md)
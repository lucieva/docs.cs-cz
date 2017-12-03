---
title: "Filtrování výstupu My.Application.Log (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- My.Log object, filtering output
- My.Application.Log object, filtering output
- application event logs, output filtering
ms.assetid: 2c0a457a-38a4-49e1-934d-a51320b7b4ca
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 90fd445227e0c8290ad63fccf807d6d7bdf43ccd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-filtering-myapplicationlog-output-visual-basic"></a><span data-ttu-id="0a30c-102">Návod: Filtrování výstupu My.Application.Log (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0a30c-102">Walkthrough: Filtering My.Application.Log Output (Visual Basic)</span></span>
<span data-ttu-id="0a30c-103">Tento návod ukazuje, jak změnit výchozí filtrování protokolování `My.Application.Log` objektu, k řízení, jaké informace jsou předány z `Log` objektu do posluchače a jaké informace jsou zapsány posluchači.</span><span class="sxs-lookup"><span data-stu-id="0a30c-103">This walkthrough demonstrates how to change the default log filtering for the `My.Application.Log` object, to control what information is passed from the `Log` object to the listeners and what information is written by the listeners.</span></span> <span data-ttu-id="0a30c-104">I po vytvoření aplikace, můžete změnit chování protokolování, protože informace o konfiguraci je uložené v konfiguračním souboru aplikace.</span><span class="sxs-lookup"><span data-stu-id="0a30c-104">You can change the logging behavior even after building the application, because the configuration information is stored in the application's configuration file.</span></span>  
  
## <a name="getting-started"></a><span data-ttu-id="0a30c-105">Začínáme</span><span class="sxs-lookup"><span data-stu-id="0a30c-105">Getting Started</span></span>  
 <span data-ttu-id="0a30c-106">Každá zpráva, které `My.Application.Log` zápisy má přidruženou úroveň závažnosti, které filtrování mechanismy používají k řízení výstup protokolu.</span><span class="sxs-lookup"><span data-stu-id="0a30c-106">Each message that `My.Application.Log` writes has an associated severity level, which filtering mechanisms use to control the log output.</span></span> <span data-ttu-id="0a30c-107">Tato ukázková aplikace používá `My.Application.Log` metody k zápisu několik protokolování zpráv s různou úrovní závažnosti.</span><span class="sxs-lookup"><span data-stu-id="0a30c-107">This sample application uses `My.Application.Log` methods to write several log messages with different severity levels.</span></span>  
  
#### <a name="to-build-the-sample-application"></a><span data-ttu-id="0a30c-108">K vytvoření ukázkové aplikace</span><span class="sxs-lookup"><span data-stu-id="0a30c-108">To build the sample application</span></span>  
  
1.  <span data-ttu-id="0a30c-109">Otevřete nový [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] projekt aplikace Windows.</span><span class="sxs-lookup"><span data-stu-id="0a30c-109">Open a new [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Windows Application project.</span></span>  
  
2.  <span data-ttu-id="0a30c-110">Přidání tlačítka s názvem Button1 do Form1.</span><span class="sxs-lookup"><span data-stu-id="0a30c-110">Add a button named Button1 to Form1.</span></span>  
  
3.  <span data-ttu-id="0a30c-111">V <xref:System.Windows.Forms.Control.Click> obslužné rutiny události pro Button1, přidejte následující kód:</span><span class="sxs-lookup"><span data-stu-id="0a30c-111">In the <xref:System.Windows.Forms.Control.Click> event handler for Button1, add the following code:</span></span>  
  
     [!code-vb[VbVbcnMyApplicationLogFiltering#1](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/walkthrough-filtering-my-application-log-output_1.vb)]  
  
4.  <span data-ttu-id="0a30c-112">Spusťte aplikaci v ladicím programu.</span><span class="sxs-lookup"><span data-stu-id="0a30c-112">Run the application in the debugger.</span></span>  
  
5.  <span data-ttu-id="0a30c-113">Stiskněte klávesu **Button1**.</span><span class="sxs-lookup"><span data-stu-id="0a30c-113">Press **Button1**.</span></span>  
  
     <span data-ttu-id="0a30c-114">Aplikace zapisuje do souboru pro výstup a protokolu ladění aplikace následující informace.</span><span class="sxs-lookup"><span data-stu-id="0a30c-114">The application writes the following information to the application's debug output and log file.</span></span>  
  
     `DefaultSource Information: 0 : In Button1_Click`  
  
     `DefaultSource Error: 2 : Error in the application.`  
  
6.  <span data-ttu-id="0a30c-115">Zavřete aplikaci.</span><span class="sxs-lookup"><span data-stu-id="0a30c-115">Close the application.</span></span>  
  
     <span data-ttu-id="0a30c-116">Informace o tom, jak zobrazit okno výstup ladění aplikace najdete v tématu [výstup – okno](/visualstudio/ide/reference/output-window).</span><span class="sxs-lookup"><span data-stu-id="0a30c-116">For information on how to view the application's debug output window, see [Output Window](/visualstudio/ide/reference/output-window).</span></span> <span data-ttu-id="0a30c-117">Informace o umístění souboru protokolu aplikace naleznete v tématu [návod: určení kam objekt My.Application.Log zapisuje informace](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md).</span><span class="sxs-lookup"><span data-stu-id="0a30c-117">For information on the location of the application's log file, see [Walkthrough: Determining Where My.Application.Log Writes Information](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0a30c-118">Ve výchozím nastavení aplikace vyprázdnění výstupní soubor protokolu, po ukončení aplikace.</span><span class="sxs-lookup"><span data-stu-id="0a30c-118">By default, the application flushes the log-file output when the application closes.</span></span>  
  
     <span data-ttu-id="0a30c-119">V příkladu výše, druhé volání <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A> metoda a volání <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A> metoda vytvoří protokolový výstup, při prvním a posledním volání `WriteEntry` metoda nepodporují.</span><span class="sxs-lookup"><span data-stu-id="0a30c-119">In the example above, the second call to the <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A> method and the call to the <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A> method produces log output, while the first and last calls to the `WriteEntry` method do not.</span></span> <span data-ttu-id="0a30c-120">Důvodem je, že úrovně závažnosti `WriteEntry` a `WriteException` jsou "Informace" a "Chyba" by jsou povolené oba tyto `My.Application.Log` objektu výchozí filtrování protokolu.</span><span class="sxs-lookup"><span data-stu-id="0a30c-120">This is because the severity levels of `WriteEntry` and `WriteException` are "Information" and "Error", both of which are allowed by the `My.Application.Log` object's default log filtering.</span></span> <span data-ttu-id="0a30c-121">Události se úrovně závažnosti "Start" a "Stop" však nebudou moci generovala výstup protokolu.</span><span class="sxs-lookup"><span data-stu-id="0a30c-121">However, events with "Start" and "Stop" severity levels are prevented from producing log output.</span></span>  
  
## <a name="filtering-for-all-myapplicationlog-listeners"></a><span data-ttu-id="0a30c-122">Filtrování pro všechny naslouchací procesy My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="0a30c-122">Filtering for All My.Application.Log Listeners</span></span>  
 <span data-ttu-id="0a30c-123">`My.Application.Log` Objektu používá <xref:System.Diagnostics.SourceSwitch> s názvem `DefaultSwitch` řídit, která zprávy se předává z `WriteEntry` a `WriteException` metody pro naslouchací procesy protokolu.</span><span class="sxs-lookup"><span data-stu-id="0a30c-123">The `My.Application.Log` object uses a <xref:System.Diagnostics.SourceSwitch> named `DefaultSwitch` to control which messages it passes from the `WriteEntry` and `WriteException` methods to the log listeners.</span></span> <span data-ttu-id="0a30c-124">Můžete nakonfigurovat `DefaultSwitch` v konfiguračním souboru aplikace podle nastavení její hodnoty na jednu z <xref:System.Diagnostics.SourceLevels> hodnot výčtu.</span><span class="sxs-lookup"><span data-stu-id="0a30c-124">You can configure `DefaultSwitch` in the application's configuration file by setting its value to one of the <xref:System.Diagnostics.SourceLevels> enumeration values.</span></span> <span data-ttu-id="0a30c-125">Ve výchozím nastavení jeho hodnota je "Informace".</span><span class="sxs-lookup"><span data-stu-id="0a30c-125">By default, its value is "Information".</span></span>  
  
 <span data-ttu-id="0a30c-126">Tato tabulka ukazuje úrovně závažnosti, pro protokol zapsat zprávu do naslouchací procesy, danou konkrétní `DefaultSwitch` nastavení.</span><span class="sxs-lookup"><span data-stu-id="0a30c-126">This table shows the severity level required for Log to write a message to the listeners, given a particular `DefaultSwitch` setting.</span></span>  
  
|<span data-ttu-id="0a30c-127">Hodnota DefaultSwitch</span><span class="sxs-lookup"><span data-stu-id="0a30c-127">DefaultSwitch Value</span></span>|<span data-ttu-id="0a30c-128">Závažnost zprávy, které jsou potřebné pro výstup</span><span class="sxs-lookup"><span data-stu-id="0a30c-128">Message severity required for output</span></span>|  
|---|---| 
|`Critical`|`Critical`|  
|`Error`|<span data-ttu-id="0a30c-129">`Critical`nebo`Error`</span><span class="sxs-lookup"><span data-stu-id="0a30c-129">`Critical` or `Error`</span></span>|  
|`Warning`|<span data-ttu-id="0a30c-130">`Critical`, `Error`, nebo`Warning`</span><span class="sxs-lookup"><span data-stu-id="0a30c-130">`Critical`, `Error`, or `Warning`</span></span>|  
|`Information`|<span data-ttu-id="0a30c-131">`Critical`, `Error`, `Warning`, nebo`Information`</span><span class="sxs-lookup"><span data-stu-id="0a30c-131">`Critical`, `Error`, `Warning`, or `Information`</span></span>|  
|`Verbose`|<span data-ttu-id="0a30c-132">`Critical`, `Error`, `Warning`, `Information`, nebo`Verbose`</span><span class="sxs-lookup"><span data-stu-id="0a30c-132">`Critical`, `Error`, `Warning`, `Information`, or `Verbose`</span></span>|  
|`ActivityTracing`|<span data-ttu-id="0a30c-133">`Start`, `Stop`, `Suspend`, `Resume`, nebo`Transfer`</span><span class="sxs-lookup"><span data-stu-id="0a30c-133">`Start`, `Stop`, `Suspend`, `Resume`, or `Transfer`</span></span>|  
|`All`|<span data-ttu-id="0a30c-134">Jsou povoleny všechny zprávy.</span><span class="sxs-lookup"><span data-stu-id="0a30c-134">All messages are allowed.</span></span>|  
|`Off`|<span data-ttu-id="0a30c-135">Všechny zprávy jsou zablokované.</span><span class="sxs-lookup"><span data-stu-id="0a30c-135">All messages are blocked.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="0a30c-136">`WriteEntry` a `WriteException` každá z metod má přetížení, která neurčuje úroveň závažnosti.</span><span class="sxs-lookup"><span data-stu-id="0a30c-136">The `WriteEntry` and `WriteException` methods each have an overload that does not specify a severity level.</span></span> <span data-ttu-id="0a30c-137">Implicitní úroveň závažnosti pro `WriteEntry` přetížení je "Informace" a implicitní úroveň závažnosti pro `WriteException` přetížení je "Chyba".</span><span class="sxs-lookup"><span data-stu-id="0a30c-137">The implicit severity level for the `WriteEntry` overload is "Information", and the implicit severity level for the `WriteException` overload is "Error".</span></span>  
  
 <span data-ttu-id="0a30c-138">Tato tabulka vysvětluje protokolový výstup v předchozím příkladu: s výchozím `DefaultSwitch` nastavení "Informace", volat pouze druhý na `WriteEntry` metoda a volání `WriteException` metoda výstup protokolu produktu.</span><span class="sxs-lookup"><span data-stu-id="0a30c-138">This table explains the log output shown in the previous example: with the default `DefaultSwitch` setting of "Information", only the second call to the `WriteEntry` method and the call to the `WriteException` method produce log output.</span></span>  
  
#### <a name="to-log-only-activity-tracing-events"></a><span data-ttu-id="0a30c-139">Protokolování událostí trasování pouze aktivity</span><span class="sxs-lookup"><span data-stu-id="0a30c-139">To log only activity tracing events</span></span>  
  
1.  <span data-ttu-id="0a30c-140">Klikněte pravým tlačítkem na app.config v **Průzkumníku řešení** a vyberte **otevřete**.</span><span class="sxs-lookup"><span data-stu-id="0a30c-140">Right-click app.config in the **Solution Explorer** and select **Open**.</span></span>  
  
     <span data-ttu-id="0a30c-141">-nebo-</span><span class="sxs-lookup"><span data-stu-id="0a30c-141">-or-</span></span>  
  
     <span data-ttu-id="0a30c-142">Pokud není dostupný žádný soubor app.config:</span><span class="sxs-lookup"><span data-stu-id="0a30c-142">If there is no app.config file:</span></span>  
  
    1.  <span data-ttu-id="0a30c-143">Na **projektu** nabídce zvolte **přidat novou položku**.</span><span class="sxs-lookup"><span data-stu-id="0a30c-143">On the **Project** menu, choose **Add New Item**.</span></span>  
  
    2.  <span data-ttu-id="0a30c-144">Z **přidat novou položku** dialogovém okně vyberte **konfigurační soubor aplikace**.</span><span class="sxs-lookup"><span data-stu-id="0a30c-144">From the **Add New Item** dialog box, choose **Application Configuration File**.</span></span>  
  
    3.  <span data-ttu-id="0a30c-145">Klikněte na tlačítko **přidat**.</span><span class="sxs-lookup"><span data-stu-id="0a30c-145">Click **Add**.</span></span>  
  
2.  <span data-ttu-id="0a30c-146">Vyhledejte `<switches>` oddíl, což je v `<system.diagnostics>` oddíl, což je v nejvyšší úrovně `<configuration>` části.</span><span class="sxs-lookup"><span data-stu-id="0a30c-146">Locate the `<switches>` section, which is in the `<system.diagnostics>` section, which is in the top-level `<configuration>` section.</span></span>  
  
3.  <span data-ttu-id="0a30c-147">Najděte element, který přidá `DefaultSwitch` ke kolekci přepínačů.</span><span class="sxs-lookup"><span data-stu-id="0a30c-147">Find the element that adds `DefaultSwitch` to the collection of switches.</span></span> <span data-ttu-id="0a30c-148">By měl vypadat podobně jako tento element:</span><span class="sxs-lookup"><span data-stu-id="0a30c-148">It should look similar to this element:</span></span>  
  
     `<add name="DefaultSwitch" value="Information" />`  
  
4.  <span data-ttu-id="0a30c-149">Změňte hodnotu `value` atributu na hodnotu "ActivityTracing".</span><span class="sxs-lookup"><span data-stu-id="0a30c-149">Change the value of the `value` attribute to "ActivityTracing".</span></span>  
  
5.  <span data-ttu-id="0a30c-150">Obsah souboru app.config by měl vypadat přibližně následující kód XML:</span><span class="sxs-lookup"><span data-stu-id="0a30c-150">The content of the app.config file should be similar to the following XML:</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <system.diagnostics>  
        <sources>  
          <!-- This section configures My.Application.Log -->  
          <source name="DefaultSource" switchName="DefaultSwitch">  
            <listeners>  
              <add name="FileLog"/>  
            </listeners>  
          </source>  
        </sources>  
        <switches>  
          <add name="DefaultSwitch" value="ActivityTracing" />  
        </switches>  
        <sharedListeners>  
          <add name="FileLog"  
               type="Microsoft.VisualBasic.Logging.FileLogTraceListener,   
                     Microsoft.VisualBasic, Version=8.0.0.0,   
                     Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a,   
                     processorArchitecture=MSIL"   
               initializeData="FileLogWriter"/>  
        </sharedListeners>  
      </system.diagnostics>  
    </configuration>  
    ```  
  
6.  <span data-ttu-id="0a30c-151">Spusťte aplikaci v ladicím programu.</span><span class="sxs-lookup"><span data-stu-id="0a30c-151">Run the application in the debugger.</span></span>  
  
7.  <span data-ttu-id="0a30c-152">Stiskněte klávesu **Button1**.</span><span class="sxs-lookup"><span data-stu-id="0a30c-152">Press **Button1**.</span></span>  
  
     <span data-ttu-id="0a30c-153">Aplikace zapisuje do souboru pro výstup a protokolu ladění aplikace následující informace:</span><span class="sxs-lookup"><span data-stu-id="0a30c-153">The application writes the following information to the application's debug output and log file:</span></span>  
  
     `DefaultSource Start: 4 : Entering Button1_Click`  
  
     `DefaultSource Stop: 5 : Leaving Button1_Click`  
  
8.  <span data-ttu-id="0a30c-154">Zavřete aplikaci.</span><span class="sxs-lookup"><span data-stu-id="0a30c-154">Close the application.</span></span>  
  
9. <span data-ttu-id="0a30c-155">Změňte hodnotu `value` zpět na "Informace".</span><span class="sxs-lookup"><span data-stu-id="0a30c-155">Change the value of the `value` attribute back to "Information".</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0a30c-156">`DefaultSwitch` Přepínač pouze ovládací prvky pro nastavení `My.Application.Log`.</span><span class="sxs-lookup"><span data-stu-id="0a30c-156">The `DefaultSwitch` switch setting controls only `My.Application.Log`.</span></span> <span data-ttu-id="0a30c-157">Nemění jak [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.Diagnostics.Trace?displayProperty=nameWithType> a <xref:System.Diagnostics.Debug?displayProperty=nameWithType> chovat třídy.</span><span class="sxs-lookup"><span data-stu-id="0a30c-157">It does not change how the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.Diagnostics.Trace?displayProperty=nameWithType> and <xref:System.Diagnostics.Debug?displayProperty=nameWithType> classes behave.</span></span>  
  
## <a name="individual-filtering-for-myapplicationlog-listeners"></a><span data-ttu-id="0a30c-158">Jednotlivé filtrování pro naslouchací procesy My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="0a30c-158">Individual Filtering For My.Application.Log Listeners</span></span>  
 <span data-ttu-id="0a30c-159">Předchozí příklad ukazuje, jak změnit filtrování pro všechny `My.Application.Log` výstup.</span><span class="sxs-lookup"><span data-stu-id="0a30c-159">The previous example shows how to change the filtering for all `My.Application.Log` output.</span></span> <span data-ttu-id="0a30c-160">Tento příklad ukazuje, jak filtrovat naslouchací proces vlastní protokol.</span><span class="sxs-lookup"><span data-stu-id="0a30c-160">This example demonstrates how to filter an individual log listener.</span></span> <span data-ttu-id="0a30c-161">Ve výchozím nastavení má aplikace dva naslouchací procesy tento zápis výstupu ladění aplikace a soubor protokolu.</span><span class="sxs-lookup"><span data-stu-id="0a30c-161">By default, an application has two listeners that write to the application's debug output and the log file.</span></span>  
  
 <span data-ttu-id="0a30c-162">Konfigurační soubor řídí chování součástí naslouchajících protokolům tím, že každé z nich má filtr, který je podobný přepínač pro `My.Application.Log`.</span><span class="sxs-lookup"><span data-stu-id="0a30c-162">The configuration file controls the behavior of the log listeners by allowing each one to have a filter, which is similar to a switch for `My.Application.Log`.</span></span> <span data-ttu-id="0a30c-163">Naslouchací proces protokolu výstup zprávu, pouze pokud je povolena závažnost zprávy pomocí obou protokolové `DefaultSwitch` a naslouchací proces protokolu filtru.</span><span class="sxs-lookup"><span data-stu-id="0a30c-163">A log listener will output a message only if the message's severity is allowed by both the log's `DefaultSwitch` and the log listener's filter.</span></span>  
  
 <span data-ttu-id="0a30c-164">Tento příklad ukazuje, jak konfigurovat filtrování pro nové naslouchání ladění a přidejte ho do `Log` objektu.</span><span class="sxs-lookup"><span data-stu-id="0a30c-164">This example demonstrates how to configure filtering for a new debug listener and add it to the `Log` object.</span></span> <span data-ttu-id="0a30c-165">Naslouchací proces výchozí ladění, měla by být odebrána z `Log` objektu, aby bylo zřejmé, že zprávy ladění pocházejí z nové naslouchací proces ladění.</span><span class="sxs-lookup"><span data-stu-id="0a30c-165">The default debug listener should be removed from the `Log` object, so it is clear that the debug messages come from the new debug listener.</span></span>  
  
#### <a name="to-log-only-activity-tracing-events"></a><span data-ttu-id="0a30c-166">Do protokolu pouze události trasování aktivit</span><span class="sxs-lookup"><span data-stu-id="0a30c-166">To log only activity-tracing events</span></span>  
  
1.  <span data-ttu-id="0a30c-167">Klikněte pravým tlačítkem na app.config v **Průzkumníku řešení** a zvolte **otevřete**.</span><span class="sxs-lookup"><span data-stu-id="0a30c-167">Right-click app.config in the **Solution Explorer** and choose **Open**.</span></span>  
  
     <span data-ttu-id="0a30c-168">-nebo-</span><span class="sxs-lookup"><span data-stu-id="0a30c-168">-or-</span></span>  
  
     <span data-ttu-id="0a30c-169">Pokud není dostupný žádný soubor app.config:</span><span class="sxs-lookup"><span data-stu-id="0a30c-169">If there is no app.config file:</span></span>  
  
    1.  <span data-ttu-id="0a30c-170">Na **projektu** nabídce zvolte **přidat novou položku**.</span><span class="sxs-lookup"><span data-stu-id="0a30c-170">On the **Project** menu, choose **Add New Item**.</span></span>  
  
    2.  <span data-ttu-id="0a30c-171">Z **přidat novou položku** dialogovém okně vyberte **konfigurační soubor aplikace**.</span><span class="sxs-lookup"><span data-stu-id="0a30c-171">From the **Add New Item** dialog box, choose **Application Configuration File**.</span></span>  
  
    3.  <span data-ttu-id="0a30c-172">Klikněte na tlačítko **přidat**.</span><span class="sxs-lookup"><span data-stu-id="0a30c-172">Click **Add**.</span></span>  
  
2.  <span data-ttu-id="0a30c-173">Klikněte pravým tlačítkem na app.config v **Průzkumníku řešení**.</span><span class="sxs-lookup"><span data-stu-id="0a30c-173">Right-click app.config in **Solution Explorer**.</span></span> <span data-ttu-id="0a30c-174">Zvolte **otevřete**.</span><span class="sxs-lookup"><span data-stu-id="0a30c-174">Choose **Open**.</span></span>  
  
3.  <span data-ttu-id="0a30c-175">Vyhledejte `<listeners>` v části `<source>` část s `name` atributu "DefaultSource", který je v části `<sources>` části.</span><span class="sxs-lookup"><span data-stu-id="0a30c-175">Locate the `<listeners>` section, in the `<source>` section with the `name` attribute "DefaultSource", which is under the `<sources>` section.</span></span> <span data-ttu-id="0a30c-176">`<sources>` Část je pod `<system.diagnostics>` oddílem se v nejvyšší úrovně `<configuration>` části.</span><span class="sxs-lookup"><span data-stu-id="0a30c-176">The `<sources>` section is under the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>  
  
4.  <span data-ttu-id="0a30c-177">Přidejte tento element na `<listeners>` části:</span><span class="sxs-lookup"><span data-stu-id="0a30c-177">Add this element to the `<listeners>` section:</span></span>  
  
    ```xml  
    <!-- Remove the default debug listener. -->  
    <remove name="Default"/>  
    <!-- Add a filterable debug listener. -->  
    <add name="NewDefault"/>  
    ```  
  
5.  <span data-ttu-id="0a30c-178">Vyhledejte `<sharedListeners>` v části `<system.diagnostics>` oddílem se v nejvyšší úrovně `<configuration>` části.</span><span class="sxs-lookup"><span data-stu-id="0a30c-178">Locate the `<sharedListeners>` section, in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>  
  
6.  <span data-ttu-id="0a30c-179">Přidejte tento element do `<sharedListeners>` části:</span><span class="sxs-lookup"><span data-stu-id="0a30c-179">Add this element to that `<sharedListeners>` section:</span></span>  
  
    ```xml  
    <add name="NewDefault"   
         type="System.Diagnostics.DefaultTraceListener,   
               System, Version=2.0.0.0, Culture=neutral,   
               PublicKeyToken=b77a5c561934e089,   
               processorArchitecture=MSIL">  
        <filter type="System.Diagnostics.EventTypeFilter"   
                initializeData="Error" />  
    </add>  
    ```  
  
     <span data-ttu-id="0a30c-180"><xref:System.Diagnostics.EventTypeFilter> Filtru má jednu z <xref:System.Diagnostics.SourceLevels> výčtové hodnoty jako jeho `initializeData` atribut.</span><span class="sxs-lookup"><span data-stu-id="0a30c-180">The <xref:System.Diagnostics.EventTypeFilter> filter takes one of the <xref:System.Diagnostics.SourceLevels> enumeration values as its `initializeData` attribute.</span></span>  
  
7.  <span data-ttu-id="0a30c-181">Obsah souboru app.config by měl vypadat přibližně následující kód XML:</span><span class="sxs-lookup"><span data-stu-id="0a30c-181">The content of the app.config file should be similar to the following XML:</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <system.diagnostics>  
        <sources>  
          <!-- This section configures My.Application.Log -->  
          <source name="DefaultSource" switchName="DefaultSwitch">  
            <listeners>  
              <add name="FileLog"/>  
              <!-- Remove the default debug listener. -->  
              <remove name="Default"/>  
              <!-- Add a filterable debug listener. -->  
              <add name="NewDefault"/>  
            </listeners>  
          </source>  
        </sources>  
        <switches>  
          <add name="DefaultSwitch" value="Information" />  
        </switches>  
        <sharedListeners>  
          <add name="FileLog"  
               type="Microsoft.VisualBasic.Logging.FileLogTraceListener,   
                     Microsoft.VisualBasic, Version=8.0.0.0,   
                     Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a,   
                     processorArchitecture=MSIL"   
               initializeData="FileLogWriter"/>  
          <add name="NewDefault"   
               type="System.Diagnostics.DefaultTraceListener,   
                     System, Version=2.0.0.0, Culture=neutral,   
                     PublicKeyToken=b77a5c561934e089,   
                     processorArchitecture=MSIL">  
            <filter type="System.Diagnostics.EventTypeFilter"   
                    initializeData="Error" />  
          </add>  
        </sharedListeners>  
      </system.diagnostics>  
    </configuration>  
    ```  
  
8.  <span data-ttu-id="0a30c-182">Spusťte aplikaci v ladicím programu.</span><span class="sxs-lookup"><span data-stu-id="0a30c-182">Run the application in the debugger.</span></span>  
  
9. <span data-ttu-id="0a30c-183">Stiskněte klávesu **Button1**.</span><span class="sxs-lookup"><span data-stu-id="0a30c-183">Press **Button1**.</span></span>  
  
     <span data-ttu-id="0a30c-184">Aplikace zapisuje do souboru protokolu aplikace následující informace:</span><span class="sxs-lookup"><span data-stu-id="0a30c-184">The application writes the following information to the application's log file:</span></span>  
  
     `Default Information: 0 : In Button1_Click`  
  
     `Default Error: 2 : Error in the application.`  
  
     <span data-ttu-id="0a30c-185">Aplikace zapíše méně informací výstupu ladění aplikace z důvodu více omezující filtrování.</span><span class="sxs-lookup"><span data-stu-id="0a30c-185">The application writes less information to the application's debug output because of the more restrictive filtering.</span></span>  
  
     `Default Error   2   Error`  
  
10. <span data-ttu-id="0a30c-186">Zavřete aplikaci.</span><span class="sxs-lookup"><span data-stu-id="0a30c-186">Close the application.</span></span>  
  
 <span data-ttu-id="0a30c-187">Další informace o změně nastavení protokolování po nasazení najdete v tématu [práce s protokoly aplikací](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md).</span><span class="sxs-lookup"><span data-stu-id="0a30c-187">For more information about changing log settings after deployment, see [Working with Application Logs](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a30c-188">Viz také</span><span class="sxs-lookup"><span data-stu-id="0a30c-188">See Also</span></span>  
 [<span data-ttu-id="0a30c-189">Návod: Zjištění, kam objekt My.Application.Log zapisuje informace</span><span class="sxs-lookup"><span data-stu-id="0a30c-189">Walkthrough: Determining Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)  
 [<span data-ttu-id="0a30c-190">Návod: Změna místa, kam objekt My.Application.Log zapisuje informace</span><span class="sxs-lookup"><span data-stu-id="0a30c-190">Walkthrough: Changing Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)  
 [<span data-ttu-id="0a30c-191">Návod: Vytváření vlastních součástí naslouchajících protokolům</span><span class="sxs-lookup"><span data-stu-id="0a30c-191">Walkthrough: Creating Custom Log Listeners</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-creating-custom-log-listeners.md)  
 [<span data-ttu-id="0a30c-192">Postupy: zápis zpráv protokolu</span><span class="sxs-lookup"><span data-stu-id="0a30c-192">How to: Write Log Messages</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md)  
 [<span data-ttu-id="0a30c-193">Trasování – přepínače</span><span class="sxs-lookup"><span data-stu-id="0a30c-193">Trace Switches</span></span>](../../../../framework/debug-trace-profile/trace-switches.md)  
 [<span data-ttu-id="0a30c-194">Protokolování informací z aplikace</span><span class="sxs-lookup"><span data-stu-id="0a30c-194">Logging Information from the Application</span></span>](../../../../visual-basic/developing-apps/programming/log-info/logging-information-from-the-application.md)
---
title: "Přidávání tiskových sestav do aplikací v jazyce Visual Studio"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- printing [Visual Studio], reports
- reports [Visual Basic], printing in Visual Studio
ms.assetid: 93928405-ef41-495e-bce2-9d43d5a7080a
caps.latest.revision: "27"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4ce2a8b12d8202a9f201a82b0d4a571249210d48
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/22/2017
---
# <a name="adding-printable-reports-to-visual-studio-applications"></a><span data-ttu-id="2de50-102">Přidávání tiskových sestav do aplikací v jazyce Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2de50-102">Adding Printable Reports to Visual Studio Applications</span></span>
<span data-ttu-id="2de50-103">Visual Studio podporuje celou řadu řešení pro sestavy můžete přidat bohaté data sestavy do aplikace Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="2de50-103">Visual Studio supports a variety of reporting solutions to help you add rich data reporting to your Visual Basic applications.</span></span> <span data-ttu-id="2de50-104">Můžete vytvořit a přidat sestav pomocí ovládacích prvků prohlížeče sestav, Crystal Reports nebo SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="2de50-104">You can create and add reports using ReportViewer controls, Crystal Reports, or SQL Server Reporting Services.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2de50-105">SQL Server Reporting Services je součástí systému SQL Server 2005, nikoli Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2de50-105">SQL Server Reporting Services is part of SQL Server 2005 rather than Visual Studio.</span></span> <span data-ttu-id="2de50-106">Služba Reporting Services není nainstalován v počítači, pokud jste nainstalovali systém SQL Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2de50-106">Reporting Services not installed on your system unless you have installed SQL Server 2005.</span></span>  
  
## <a name="overview-of-microsoft-reporting-technology-in-visual-basic-applications"></a><span data-ttu-id="2de50-107">Přehled služby Microsoft Reporting technologie v aplikacích jazyka Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2de50-107">Overview of Microsoft Reporting Technology in Visual Basic Applications</span></span>  
 <span data-ttu-id="2de50-108">Vyberte z následujících dvou přístupů pomocí služby Microsoft reporting technologii ve vaší aplikaci:</span><span class="sxs-lookup"><span data-stu-id="2de50-108">Choose from the following approaches to use a Microsoft reporting technology in your application:</span></span>  
  
-   <span data-ttu-id="2de50-109">Přidejte jednu nebo více instancí ovládacího prvku prohlížeče sestav do aplikace Windows Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="2de50-109">Add one or more instances of a ReportViewer control to a Visual Basic Windows application.</span></span>  
  
-   <span data-ttu-id="2de50-110">Integrace prostřednictvím kódu programu SQL Server Reporting Services tak, že volání webové službě Server sestav.</span><span class="sxs-lookup"><span data-stu-id="2de50-110">Integrate SQL Server Reporting Services programmatically by making calls to the Report Server Web service.</span></span>  
  
-   <span data-ttu-id="2de50-111">Pomocí ovládacího prvku prohlížeče sestav a Microsoft SQL Server 2005 Reporting Services společně pomocí ovládacího prvku jako prohlížeč sestav a server sestav jako procesoru.</span><span class="sxs-lookup"><span data-stu-id="2de50-111">Use the ReportViewer control and Microsoft SQL Server 2005 Reporting Services together, using the control as a report viewer and a report server as a report processor.</span></span> <span data-ttu-id="2de50-112">(Všimněte si, SQL Server 2005 verzí služby Reporting Services musíte použít, pokud chcete použít server sestav a ovládací prvek prohlížeče sestav společně).</span><span class="sxs-lookup"><span data-stu-id="2de50-112">(Note that you must use the SQL Server 2005 version of Reporting Services if you want to use a report server and the ReportViewer control together).</span></span>  
  
## <a name="using-reportviewer-controls"></a><span data-ttu-id="2de50-113">Použití ovládacích prvků prohlížeče sestav</span><span class="sxs-lookup"><span data-stu-id="2de50-113">Using ReportViewer Controls</span></span>  
 <span data-ttu-id="2de50-114">Přidání ovládacího prvku prohlížeče sestav do formuláře v aplikaci je nejjednodušší způsob, jak funkce sestavy do aplikace Windows Visual Basic pro vložení.</span><span class="sxs-lookup"><span data-stu-id="2de50-114">The easiest way to embed report functionality into a Visual Basic Windows application is to add the ReportViewer control to a form in your application.</span></span> <span data-ttu-id="2de50-115">Ovládací prvek přidá sestavy zpracování možnosti přímo do vaší aplikace a obsahuje integrovaný návrhář sestav tak, že můžete vytvořit sestavy pomocí dat z libovolného objektu dat ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="2de50-115">The control adds report processing capabilities directly to your application and provides an integrated report designer so that you can build reports using data from any ADO.NET data object.</span></span> <span data-ttu-id="2de50-116">Rozhraní API plné zajišťují programový přístup k ovládacímu prvku a sestavy tak, aby můžete nakonfigurovat spuštění funkce.</span><span class="sxs-lookup"><span data-stu-id="2de50-116">A full-featured API provides programmatic access to the control and reports so that you can configure run-time functionality.</span></span>  
  
 <span data-ttu-id="2de50-117">Prohlížeče sestav poskytuje předdefinované sestavy zpracování a možnost zobrazení v ovládacím prvku jeden, volně distribuovatelného data.</span><span class="sxs-lookup"><span data-stu-id="2de50-117">ReportViewer provides built-in report processing and viewing capability in a single, freely distributable data control.</span></span> <span data-ttu-id="2de50-118">Zvolte ReportViewer pokud vyžadujete funkci následující sestavy:</span><span class="sxs-lookup"><span data-stu-id="2de50-118">Choose ReportViewer controls if you require the following report functionality:</span></span>  
  
-   <span data-ttu-id="2de50-119">Zpracování v aplikaci klienta sestav.</span><span class="sxs-lookup"><span data-stu-id="2de50-119">Report processing in the client application.</span></span> <span data-ttu-id="2de50-120">Zpracované sestavy se zobrazí v oblasti zobrazení poskytované ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="2de50-120">A processed report appears in a view area provided by the control.</span></span>  
  
-   <span data-ttu-id="2de50-121">Datová vazba na tabulky dat ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="2de50-121">Data binding to ADO.NET data tables.</span></span> <span data-ttu-id="2de50-122">Můžete vytvořit sestavy, které využívají <xref:System.Data.DataTable> instance zadaný do ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="2de50-122">You can create reports that consume <xref:System.Data.DataTable> instances supplied to the control.</span></span> <span data-ttu-id="2de50-123">Můžete také navázat přímo na obchodní objekty.</span><span class="sxs-lookup"><span data-stu-id="2de50-123">You can also bind directly to business objects.</span></span>  
  
-   <span data-ttu-id="2de50-124">Distribuovatelné ovládací prvky, které můžete zahrnout do vaší aplikace.</span><span class="sxs-lookup"><span data-stu-id="2de50-124">Redistributable controls that you can include in your application.</span></span>  
  
-   <span data-ttu-id="2de50-125">Funkcionalita modulu runtime například navigaci na stránce, tisk, vyhledávání a export formátů.</span><span class="sxs-lookup"><span data-stu-id="2de50-125">Runtime functionality such as page navigation, printing, searching, and export formats.</span></span> <span data-ttu-id="2de50-126">Panelu nástrojů prohlížeče sestav poskytuje podporu pro tyto operace.</span><span class="sxs-lookup"><span data-stu-id="2de50-126">A ReportViewer toolbar provides support for these operations.</span></span>  
  
 <span data-ttu-id="2de50-127">Použití ovládacího prvku prohlížeče sestav, můžete přetáhnout z **Data** části nástrojů Visual Studio do formuláře v aplikaci Windows Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="2de50-127">To use the ReportViewer control, you can drag it from the **Data** section of the Visual Studio Toolbox onto a form in your Visual Basic Windows application.</span></span>  
  
### <a name="creating-reports-in-visual-studio-for-reportviewer-controls"></a><span data-ttu-id="2de50-128">Vytváření sestav v sadě Visual Studio pro ovládací prvky prohlížeče sestav</span><span class="sxs-lookup"><span data-stu-id="2de50-128">Creating Reports in Visual Studio for ReportViewer Controls</span></span>  
 <span data-ttu-id="2de50-129">Chcete-li vytvořit sestavu, která běží v prohlížeče sestav, přidejte **sestavy** šablony do projektu.</span><span class="sxs-lookup"><span data-stu-id="2de50-129">To build a report that runs in ReportViewer, add a **Report** template to your project.</span></span> <span data-ttu-id="2de50-130">Visual Studio vytvoří soubor definice sestav (.rdlc) klienta, přidá soubor do projektu a otevře integrovaný návrhář sestav v pracovním prostoru Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2de50-130">Visual Studio creates a client report definition file (.rdlc), adds the file to your project, and opens an integrated report designer in the Visual Studio workspace.</span></span>  
  
 <span data-ttu-id="2de50-131">Návrhář sestav Visual Studio se integruje s **zdroje dat** okno.</span><span class="sxs-lookup"><span data-stu-id="2de50-131">The Visual Studio Report Designer integrates with the **Data Sources** window.</span></span> <span data-ttu-id="2de50-132">Když přetáhněte pole ze **zdroje dat** časové období pro sestavu, Návrhář sestav zkopíruje metadata o zdroji dat do souboru definice sestavy.</span><span class="sxs-lookup"><span data-stu-id="2de50-132">When you drag a field from the **Data Sources** window to the report, the Report Designer copies metadata about the data source into the report definition file.</span></span> <span data-ttu-id="2de50-133">Tato metadata pomocí ovládacího prvku prohlížeče sestav slouží k automatickému generování kódu datové vazby.</span><span class="sxs-lookup"><span data-stu-id="2de50-133">This metadata is used by the ReportViewer control to automatically generate data-binding code.</span></span>  
  
 <span data-ttu-id="2de50-134">Návrhář sestav Visual Studio neobsahuje funkce Náhled sestavy.</span><span class="sxs-lookup"><span data-stu-id="2de50-134">The Visual Studio Report Designer does not include report preview functionality.</span></span> <span data-ttu-id="2de50-135">Zobrazit náhled sestavy, spusťte aplikaci a náhled sestavy jej.</span><span class="sxs-lookup"><span data-stu-id="2de50-135">To preview your report, run the application and preview the report embedded in it.</span></span>  
  
|<span data-ttu-id="2de50-136">Chcete-li přidat funkce základní sestavy do vaší aplikace</span><span class="sxs-lookup"><span data-stu-id="2de50-136">To add basic report functionality to your application</span></span>|  
|---|    
|<span data-ttu-id="2de50-137">1.  Přetáhněte ovládací prvek prohlížeče sestav z **Data** kartě **sada nástrojů** do formuláře.</span><span class="sxs-lookup"><span data-stu-id="2de50-137">1.  Drag a ReportViewer control from the **Data** tab of the **Toolbox** onto your form.</span></span><br /><span data-ttu-id="2de50-138">2.  Na **projektu** nabídce zvolte **přidat novou položku**.</span><span class="sxs-lookup"><span data-stu-id="2de50-138">2.  On the **Project** menu, choose **Add New Item**.</span></span> <span data-ttu-id="2de50-139">V **přidat novou položku** dialogové okno, vyberte **sestavy** ikonu a klikněte na tlačítko **přidat**.</span><span class="sxs-lookup"><span data-stu-id="2de50-139">In the **Add New Item** dialog box, select the **Report** icon and click **Add**.</span></span><br />     <span data-ttu-id="2de50-140">Návrhář sestav se otevře ve vývojovém prostředí, a soubor sestav (.rdlc) je přidán do projektu.</span><span class="sxs-lookup"><span data-stu-id="2de50-140">The Report Designer opens in the development environment, and a report (.rdlc) file is added to the project.</span></span><br /><span data-ttu-id="2de50-141">3.  Přetáhněte položky sestavy z **sada nástrojů** na rozložení sestavy a seřadit je podle potřeby.</span><span class="sxs-lookup"><span data-stu-id="2de50-141">3.  Drag report items from the **Toolbox** on the report layout and arrange them as you want.</span></span><br /><span data-ttu-id="2de50-142">4.  Přetáhněte pole ze **zdroje dat** okno na položky sestavy v rozložení sestavy.</span><span class="sxs-lookup"><span data-stu-id="2de50-142">4.  Drag fields from the **Data Sources** window to the report items in the report layout.</span></span>|  
  
## <a name="using-reporting-services-in-visual-basic-applications"></a><span data-ttu-id="2de50-143">Použití služby Reporting Services v aplikacích jazyka Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2de50-143">Using Reporting Services in Visual Basic Applications</span></span>  
 <span data-ttu-id="2de50-144">Na serveru vytváření sestav technologie, která je součástí systému SQL Server Reporting Services je.</span><span class="sxs-lookup"><span data-stu-id="2de50-144">Reporting Services is a server-based reporting technology that is included with SQL Server.</span></span> <span data-ttu-id="2de50-145">Služba Reporting Services zahrnuje další funkce, které nejsou k dispozici v ovládací prvky prohlížeče sestav.</span><span class="sxs-lookup"><span data-stu-id="2de50-145">Reporting Services includes additional features that are not found in the ReportViewer controls.</span></span> <span data-ttu-id="2de50-146">Vyberte služby Reporting Services, pokud budete potřebovat některé z následujících funkcí:</span><span class="sxs-lookup"><span data-stu-id="2de50-146">Choose Reporting Services if you require any of the following features:</span></span>  
  
-   <span data-ttu-id="2de50-147">Nasazení s více instancemi a zpracování serveru sestav, který poskytuje lepší výkon pro komplexní nebo dlouhotrvající sestavy a pro sestavy vysoký počet aktivit.</span><span class="sxs-lookup"><span data-stu-id="2de50-147">Scale-out deployment and server-side report processing that provides improved performance for complex or long-running reports and for high-volume report activity.</span></span>  
  
-   <span data-ttu-id="2de50-148">Integrované dat a zpracování sestavy, se podpora pro ovládací prvky vlastních sestav a bohaté vykreslování výstupní formáty.</span><span class="sxs-lookup"><span data-stu-id="2de50-148">Integrated data and report processing, with support for custom report controls and rich rendering output formats.</span></span>  
  
-   <span data-ttu-id="2de50-149">Naplánovat, zpracování sestav tak, aby můžete zadat přesně dobu spuštění sestavy.</span><span class="sxs-lookup"><span data-stu-id="2de50-149">Scheduled report processing so that you can specify exactly when reports are run.</span></span>  
  
-   <span data-ttu-id="2de50-150">Distribuce sestav prostřednictvím e-mailu nebo do umístění sdílené složky souborů.</span><span class="sxs-lookup"><span data-stu-id="2de50-150">Subscriber-based report distribution through e-mail or to file share locations.</span></span>  
  
-   <span data-ttu-id="2de50-151">Vykazování ad hoc tak, aby obchodní uživatelé můžete vytvořit sestavy, podle potřeby.</span><span class="sxs-lookup"><span data-stu-id="2de50-151">Ad hoc reporting so that business users can create reports as needed.</span></span>  
  
-   <span data-ttu-id="2de50-152">Řízené daty předplatná, která se bude směrovat výstup vlastních sestav dynamické seznam příjemců.</span><span class="sxs-lookup"><span data-stu-id="2de50-152">Data-driven subscriptions that route customized report output to a dynamic list of recipients.</span></span>  
  
-   <span data-ttu-id="2de50-153">Vlastní rozšíření pro zpracování dat, doručení sestavy, vlastní ověřování a vykreslování sestavy.</span><span class="sxs-lookup"><span data-stu-id="2de50-153">Custom extensions for data processing, report delivery, custom authentication, and report rendering.</span></span>  
  
 <span data-ttu-id="2de50-154">Server sestav je implementovaný jako webovou službu.</span><span class="sxs-lookup"><span data-stu-id="2de50-154">The report server is implemented as Web service.</span></span> <span data-ttu-id="2de50-155">Kód aplikace musí obsahovat volání webové služby pro přístup k sestavám a další metadata.</span><span class="sxs-lookup"><span data-stu-id="2de50-155">Your application code must include calls to the Web service to access reports and other metadata.</span></span> <span data-ttu-id="2de50-156">Webová služba poskytuje úplný programový přístup k instanci serveru sestav.</span><span class="sxs-lookup"><span data-stu-id="2de50-156">The Web service provides complete programmatic access to a report server instance.</span></span>  
  
 <span data-ttu-id="2de50-157">Vzhledem k tomu, že služby Reporting Services je technologie vytváření sestav založené na webu, výchozí prohlížeč zobrazí sestavy, které jsou generovány ve formátu HTML.</span><span class="sxs-lookup"><span data-stu-id="2de50-157">Because Reporting Services is a Web-based reporting technology, the default viewer shows reports that are rendered in HTML format.</span></span> <span data-ttu-id="2de50-158">Pokud nechcete použít HTML jako výchozí formát prezentace sestav, budete muset napsat vlastní prohlížeč sestav pro vaši aplikaci.</span><span class="sxs-lookup"><span data-stu-id="2de50-158">If you do not want to use HTML as the default report presentation format, you will have to write a custom report viewer for your application.</span></span>  
  
### <a name="creating-reports-in-visual-studio-for-reporting-services"></a><span data-ttu-id="2de50-159">Vytváření sestav v sadě Visual Studio pro služby vytváření sestav</span><span class="sxs-lookup"><span data-stu-id="2de50-159">Creating Reports in Visual Studio for Reporting Services</span></span>  
 <span data-ttu-id="2de50-160">Pro vytváření sestav, které běží na serveru sestav, vytváření definice sestavy (.rdl) souborů v sadě Visual Studio prostřednictvím Business Intelligence Development Studio, který je součástí systému SQL Server 2005.</span><span class="sxs-lookup"><span data-stu-id="2de50-160">To build reports that run on a report server, you create report definition (.rdl) files in Visual Studio through the Business Intelligence Development Studio, which is included with SQL Server 2005.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2de50-161">Musí mít systém SQL Server 2005, aby bylo možné používat SQL Server Reporting Services a Business Intelligence Development Studio.</span><span class="sxs-lookup"><span data-stu-id="2de50-161">You must have SQL Server 2005 installed in order to use SQL Server Reporting Services and the Business Intelligence Development Studio.</span></span>  
  
 <span data-ttu-id="2de50-162">Business Intelligence Development Studio. Přidá šablony projektů, které jsou specifické pro součásti systému SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2de50-162">The Business Intelligence Development Studio adds project templates that are specific to SQL Server components.</span></span> <span data-ttu-id="2de50-163">K vytváření sestav, můžete z **projektu serveru sestav** nebo **Průvodce projektem Report Server** šablony.</span><span class="sxs-lookup"><span data-stu-id="2de50-163">To create reports, you can choose from the **Report Server Project** or **Report Server Project Wizard** templates.</span></span> <span data-ttu-id="2de50-164">Můžete zadat připojení ke zdroji dat a dotazy na celou řadu typy zdrojů dat, včetně systému SQL Server, Oracle, služby Analysis Services, XML a SQL Server Integration Services.</span><span class="sxs-lookup"><span data-stu-id="2de50-164">You can specify data source connections and queries to a variety of data source types, including SQL Server, Oracle, Analysis Services, XML, and SQL Server Integration Services.</span></span> <span data-ttu-id="2de50-165">A **Data** kartě **rozložení** kartě a **Preview** kartě umožňují definovat data, vytvářet rozložení sestavy a prohlédnout sestava všechno ve stejném pracovním prostoru.</span><span class="sxs-lookup"><span data-stu-id="2de50-165">A **Data** tab, **Layout** tab, and **Preview** tab allow you to define data, create a report layout, and preview the report all in the same workspace.</span></span>  
  
 <span data-ttu-id="2de50-166">Definice sestavy, které vytvoříte pro ovládací prvek nebo server sestav lze znovu použít v obou technologií.</span><span class="sxs-lookup"><span data-stu-id="2de50-166">Report definitions that you build for the control or the report server can be reused in either technology.</span></span>  
  
|<span data-ttu-id="2de50-167">Chcete-li vytvořit sestavu, která běží na serveru sestav</span><span class="sxs-lookup"><span data-stu-id="2de50-167">To create a report that runs on a report server</span></span>|  
|---|    
|<span data-ttu-id="2de50-168">1.  Na **soubor** nabídce zvolte **nový**.</span><span class="sxs-lookup"><span data-stu-id="2de50-168">1.  On the **File** menu, choose **New**.</span></span><br />     <span data-ttu-id="2de50-169">**Nový projekt** otevře se dialogové okno.</span><span class="sxs-lookup"><span data-stu-id="2de50-169">The **New Project** dialog box opens.</span></span><br /><span data-ttu-id="2de50-170">2.  V **typy projektů** podokně klikněte na tlačítko **projekty Business Intelligence**.</span><span class="sxs-lookup"><span data-stu-id="2de50-170">2.  In the **Project types** pane, click **Business Intelligence Projects**.</span></span><br /><span data-ttu-id="2de50-171">3.  V podokně šablon vyberte **projektu serveru sestav** nebo **Průvodce projektem Report Server**.</span><span class="sxs-lookup"><span data-stu-id="2de50-171">3.  In the Templates pane, select **Report Server Project** or **Report Server Project Wizard**.</span></span>|  
  
## <a name="using-reportviewer-controls-and-sql-server-reporting-services-together"></a><span data-ttu-id="2de50-172">Pomocí ovládacích prvků prohlížeče sestav a SQL Server Reporting Services</span><span class="sxs-lookup"><span data-stu-id="2de50-172">Using ReportViewer Controls and SQL Server Reporting Services Together</span></span>  
 <span data-ttu-id="2de50-173">Ovládací prvky prohlížeče sestav a SQL Server 2005 Reporting Services můžete použít společně ve stejné aplikaci.</span><span class="sxs-lookup"><span data-stu-id="2de50-173">The ReportViewer controls and SQL Server 2005 Reporting Services can be used together in the same application.</span></span>  
  
-   <span data-ttu-id="2de50-174">Ovládací prvek prohlížeče sestav poskytuje prohlížeč, který se používá k zobrazení sestavy v aplikaci.</span><span class="sxs-lookup"><span data-stu-id="2de50-174">The ReportViewer control provides a viewer that is used to display reports in your application.</span></span>  
  
-   <span data-ttu-id="2de50-175">Služba Reporting Services poskytuje sestavy a provádí veškeré zpracování na vzdáleném serveru.</span><span class="sxs-lookup"><span data-stu-id="2de50-175">Reporting Services provides the reports and performs all processing on a remote server.</span></span>  
  
 <span data-ttu-id="2de50-176">Ovládací prvek prohlížeče sestav lze nakonfigurovat k zobrazení sestavy, které jsou uloženy a zpracovány na vzdálený server sestav služby Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="2de50-176">The ReportViewer control can be configured to show reports that are stored and processed on a remote Reporting Services report server.</span></span> <span data-ttu-id="2de50-177">Tento typ konfigurace se nazývá *režim vzdálené zpracování*.</span><span class="sxs-lookup"><span data-stu-id="2de50-177">This type of configuration is called *remote processing mode*.</span></span> <span data-ttu-id="2de50-178">Ovládací prvek v režimu vzdálené zpracování požadavků sestavu, která je uložena na serveru vzdáleného sestav.</span><span class="sxs-lookup"><span data-stu-id="2de50-178">In remote processing mode, the control requests a report that is stored on a remote report server.</span></span> <span data-ttu-id="2de50-179">Server sestav provádí zpracování sestavy, zpracování dat a vykreslování sestavy.</span><span class="sxs-lookup"><span data-stu-id="2de50-179">The report server performs all report processing, data processing, and report rendering.</span></span> <span data-ttu-id="2de50-180">Dokončené, sestavené sestavy se vrátí do ovládacího prvku a zobrazí v oblasti zobrazení.</span><span class="sxs-lookup"><span data-stu-id="2de50-180">A finished, rendered report is returned to the control and displayed in the view area.</span></span>  
  
 <span data-ttu-id="2de50-181">Sestavy, které běží na serveru sestav další podporu exportovat formátů, jinou parametrizaci sestava, použijte typy zdrojů dat, které jsou podporovány serverem sestav a jsou přístupné prostřednictvím modelu autorizace na základě rolí na server sestav.</span><span class="sxs-lookup"><span data-stu-id="2de50-181">Reports that run on a report server support additional export formats, have a different report parameterization implementation, use the data source types that are supported by the report server, and are accessed through the role-based authorization model on the report server.</span></span>  
  
 <span data-ttu-id="2de50-182">Pro použití režimu vzdálené zpracování, zadejte adresu URL a cestu k serveru sestav při konfiguraci ovládacího prvku prohlížeče sestav.</span><span class="sxs-lookup"><span data-stu-id="2de50-182">To use remote processing mode, specify the URL and path to a server report when configuring the ReportViewer control.</span></span>
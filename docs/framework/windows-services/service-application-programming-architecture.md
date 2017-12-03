---
title: "Architektura programování aplikace služby"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ServiceController components, programming architecture
- ServiceBase class, service states
- Windows Service applications, code model
- services, programming architecture
- ServiceController class
- services, states
- ServiceProcessInstaller class, service application code model
- Windows Service applications, states
ms.assetid: 83230026-d068-4174-97ff-e264c896eb2f
caps.latest.revision: "15"
author: ghogen
ms.author: ghogen
manager: douge
ms.openlocfilehash: e9c16f2e603a3ce9bbc59be4e01aa492239d2c63
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="service-application-programming-architecture"></a><span data-ttu-id="b0a75-102">Architektura programování aplikace služby</span><span class="sxs-lookup"><span data-stu-id="b0a75-102">Service Application Programming Architecture</span></span>
<span data-ttu-id="b0a75-103">Aplikace služby systému Windows jsou založené na třídu, která dědí z <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> třídy.</span><span class="sxs-lookup"><span data-stu-id="b0a75-103">Windows Service applications are based on a class that inherits from the <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="b0a75-104">Přepsání metody z této třídy a definovat funkce pro ně k určení chování služby.</span><span class="sxs-lookup"><span data-stu-id="b0a75-104">You override methods from this class and define functionality for them to determine how your service behaves.</span></span>  
  
 <span data-ttu-id="b0a75-105">Hlavní třídy účastnící se vytváření služby jsou:</span><span class="sxs-lookup"><span data-stu-id="b0a75-105">The main classes involved in service creation are:</span></span>  
  
-   <span data-ttu-id="b0a75-106"><xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType>– Můžete přepsat metody ze <xref:System.ServiceProcess.ServiceBase> třídy při vytváření služby a zadejte kód, určit, jak funkce služby v tomto zděděná třída.</span><span class="sxs-lookup"><span data-stu-id="b0a75-106"><xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> — You override methods from the <xref:System.ServiceProcess.ServiceBase> class when creating a service and define the code to determine how your service functions in this inherited class.</span></span>  
  
-   <span data-ttu-id="b0a75-107"><xref:System.ServiceProcess.ServiceProcessInstaller?displayProperty=nameWithType>a <xref:System.ServiceProcess.ServiceInstaller?displayProperty=nameWithType> – tyto třídy slouží k instalaci a odinstalaci služby.</span><span class="sxs-lookup"><span data-stu-id="b0a75-107"><xref:System.ServiceProcess.ServiceProcessInstaller?displayProperty=nameWithType> and <xref:System.ServiceProcess.ServiceInstaller?displayProperty=nameWithType> —You use these classes to install and uninstall your service.</span></span>  
  
 <span data-ttu-id="b0a75-108">Kromě toho třída s názvem <xref:System.ServiceProcess.ServiceController> lze použít k manipulaci s samotné služby.</span><span class="sxs-lookup"><span data-stu-id="b0a75-108">In addition, a class named <xref:System.ServiceProcess.ServiceController> can be used to manipulate the service itself.</span></span> <span data-ttu-id="b0a75-109">Tato třída není zahrnut do vytváření služby, ale lze spustit a zastavit službu, předejte příkazy k němu a vrátit řadu výčty.</span><span class="sxs-lookup"><span data-stu-id="b0a75-109">This class is not involved in the creation of a service, but can be used to start and stop the service, pass commands to it, and return a series of enumerations.</span></span>  
  
## <a name="defining-your-services-behavior"></a><span data-ttu-id="b0a75-110">Definování chování služby</span><span class="sxs-lookup"><span data-stu-id="b0a75-110">Defining Your Service's Behavior</span></span>  
 <span data-ttu-id="b0a75-111">Ve třídě služby přepsat funkce základní třídy, které určují, co se stane při změně stavu služby ve správci řízení služeb.</span><span class="sxs-lookup"><span data-stu-id="b0a75-111">In your service class, you override base class functions that determine what happens when the state of your service is changed in the Services Control Manager.</span></span> <span data-ttu-id="b0a75-112"><xref:System.ServiceProcess.ServiceBase> Třída poskytuje následující metody, které pokud chcete přidat vlastní chování můžete přepsat.</span><span class="sxs-lookup"><span data-stu-id="b0a75-112">The <xref:System.ServiceProcess.ServiceBase> class exposes the following methods, which you can override to add custom behavior.</span></span>  
  
|<span data-ttu-id="b0a75-113">Metoda</span><span class="sxs-lookup"><span data-stu-id="b0a75-113">Method</span></span>|<span data-ttu-id="b0a75-114">Přepsání nastavení za účelem</span><span class="sxs-lookup"><span data-stu-id="b0a75-114">Override to</span></span>|  
|------------|-----------------|  
|<xref:System.ServiceProcess.ServiceBase.OnStart%2A>|<span data-ttu-id="b0a75-115">Označuje, jaké akce by měla být provedena při spuštění služby.</span><span class="sxs-lookup"><span data-stu-id="b0a75-115">Indicate what actions should be taken when your service starts running.</span></span> <span data-ttu-id="b0a75-116">V tomto postupu pro vaši službu pro práci užitečné musíte napsat kód.</span><span class="sxs-lookup"><span data-stu-id="b0a75-116">You must write code in this procedure for your service to perform useful work.</span></span>|  
|<xref:System.ServiceProcess.ServiceBase.OnPause%2A>|<span data-ttu-id="b0a75-117">Označuje, co by měl stane, když vaše služba je pozastavena.</span><span class="sxs-lookup"><span data-stu-id="b0a75-117">Indicate what should happen when your service is paused.</span></span>|  
|<xref:System.ServiceProcess.ServiceBase.OnStop%2A>|<span data-ttu-id="b0a75-118">Označuje, co by měl stane, když se zastaví služby.</span><span class="sxs-lookup"><span data-stu-id="b0a75-118">Indicate what should happen when your service stops running.</span></span>|  
|<xref:System.ServiceProcess.ServiceBase.OnContinue%2A>|<span data-ttu-id="b0a75-119">Označuje, co by měl stane, když vaše služba obnoví normální fungování po jejím pozastavení.</span><span class="sxs-lookup"><span data-stu-id="b0a75-119">Indicate what should happen when your service resumes normal functioning after being paused.</span></span>|  
|<xref:System.ServiceProcess.ServiceBase.OnShutdown%2A>|<span data-ttu-id="b0a75-120">Označuje, co by měl stane těsně před systému vypíná, pokud vaše služba běží v daném čase.</span><span class="sxs-lookup"><span data-stu-id="b0a75-120">Indicate what should happen just prior to your system shutting down, if your service is running at that time.</span></span>|  
|<xref:System.ServiceProcess.ServiceBase.OnCustomCommand%2A>|<span data-ttu-id="b0a75-121">Označuje, co by měl stane, když vaše služba přijímá vlastního příkazu.</span><span class="sxs-lookup"><span data-stu-id="b0a75-121">Indicate what should happen when your service receives a custom command.</span></span> <span data-ttu-id="b0a75-122">Další informace o vlastní příkazy v MSDN online.</span><span class="sxs-lookup"><span data-stu-id="b0a75-122">For more information on custom commands, see MSDN online.</span></span>|  
|<xref:System.ServiceProcess.ServiceBase.OnPowerEvent%2A>|<span data-ttu-id="b0a75-123">Označuje, jak má služba odpovědět odeslaná událostí řízení spotřeby, jako je nízký stav baterie nebo pozastavený operaci.</span><span class="sxs-lookup"><span data-stu-id="b0a75-123">Indicate how the service should respond when a power management event is received, such as a low battery or suspended operation.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="b0a75-124">Tyto metody představují stavy, které služba prochází přes v celé jeho životnosti; přechody služby z jednoho stavu na další.</span><span class="sxs-lookup"><span data-stu-id="b0a75-124">These methods represent states that the service moves through in its lifetime; the service transitions from one state to the next.</span></span> <span data-ttu-id="b0a75-125">Například se nikdy získat službu reagovat na <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> příkazu před <xref:System.ServiceProcess.ServiceBase.OnStart%2A> byla volána.</span><span class="sxs-lookup"><span data-stu-id="b0a75-125">For example, you will never get the service to respond to an <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> command before <xref:System.ServiceProcess.ServiceBase.OnStart%2A> has been called.</span></span>  
  
 <span data-ttu-id="b0a75-126">Existuje několik vlastnosti a metody, které jsou pro ně.</span><span class="sxs-lookup"><span data-stu-id="b0a75-126">There are several other properties and methods that are of interest.</span></span> <span data-ttu-id="b0a75-127">Mezi ně patří:</span><span class="sxs-lookup"><span data-stu-id="b0a75-127">These include:</span></span>  
  
-   <span data-ttu-id="b0a75-128"><xref:System.ServiceProcess.ServiceBase.Run%2A> Metodu <xref:System.ServiceProcess.ServiceBase> třídy.</span><span class="sxs-lookup"><span data-stu-id="b0a75-128">The <xref:System.ServiceProcess.ServiceBase.Run%2A> method on the <xref:System.ServiceProcess.ServiceBase> class.</span></span> <span data-ttu-id="b0a75-129">Toto je hlavní vstupní bod pro službu.</span><span class="sxs-lookup"><span data-stu-id="b0a75-129">This is the main entry point for the service.</span></span> <span data-ttu-id="b0a75-130">Když vytváříte službu pomocí šablony služeb systému Windows, kód je vložen do vaší aplikace `Main` metodu pro spuštění služby.</span><span class="sxs-lookup"><span data-stu-id="b0a75-130">When you create a service using the Windows Service template, code is inserted in your application's `Main` method to run the service.</span></span> <span data-ttu-id="b0a75-131">Tento kód vypadá takto:</span><span class="sxs-lookup"><span data-stu-id="b0a75-131">This code looks like this:</span></span>  
  
     [!code-csharp[VbRadconService#6](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#6)]
     [!code-vb[VbRadconService#6](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#6)]  
  
    > [!NOTE]
    >  <span data-ttu-id="b0a75-132">Tyto příklady použití pole typu <xref:System.ServiceProcess.ServiceBase>, do které každá služba, která obsahuje aplikaci lze přidat a pak všechny služby, lze spustit společně.</span><span class="sxs-lookup"><span data-stu-id="b0a75-132">These examples use an array of type <xref:System.ServiceProcess.ServiceBase>, into which each service your application contains can be added, and then all of the services can be run together.</span></span> <span data-ttu-id="b0a75-133">Pokud vytváříte jen jedné služby, ale může rozhodnete použít pole a jednoduše deklarovat nový objekt, který dědí z <xref:System.ServiceProcess.ServiceBase> a spusťte jej.</span><span class="sxs-lookup"><span data-stu-id="b0a75-133">If you are only creating a single service, however, you might choose not to use the array and simply declare a new object inheriting from <xref:System.ServiceProcess.ServiceBase> and then run it.</span></span> <span data-ttu-id="b0a75-134">Příklad, naleznete v části [postupy: zápis služeb prostřednictvím kódu programu](../../../docs/framework/windows-services/how-to-write-services-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="b0a75-134">For an example, see [How to: Write Services Programmatically](../../../docs/framework/windows-services/how-to-write-services-programmatically.md).</span></span>  
  
-   <span data-ttu-id="b0a75-135">Řadu vlastnosti <xref:System.ServiceProcess.ServiceBase> třídy.</span><span class="sxs-lookup"><span data-stu-id="b0a75-135">A series of properties on the <xref:System.ServiceProcess.ServiceBase> class.</span></span> <span data-ttu-id="b0a75-136">Tyto určují, jaké metody lze volat na vaši službu.</span><span class="sxs-lookup"><span data-stu-id="b0a75-136">These determine what methods can be called on your service.</span></span> <span data-ttu-id="b0a75-137">Například když <xref:System.ServiceProcess.ServiceBase.CanStop%2A> je nastavena na `true`, <xref:System.ServiceProcess.ServiceBase.OnStop%2A> nelze volat metodu vaší služby.</span><span class="sxs-lookup"><span data-stu-id="b0a75-137">For example, when the <xref:System.ServiceProcess.ServiceBase.CanStop%2A> property is set to `true`, the <xref:System.ServiceProcess.ServiceBase.OnStop%2A> method on your service can be called.</span></span> <span data-ttu-id="b0a75-138">Když <xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A> je nastavena na `true`, <xref:System.ServiceProcess.ServiceBase.OnPause%2A> a <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> lze volat metody.</span><span class="sxs-lookup"><span data-stu-id="b0a75-138">When the <xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A> property is set to `true`, the <xref:System.ServiceProcess.ServiceBase.OnPause%2A> and <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> methods can be called.</span></span> <span data-ttu-id="b0a75-139">Když nastavíte jednu z těchto vlastností na `true`, pak by měly přepsat a definovat zpracování pro související metody.</span><span class="sxs-lookup"><span data-stu-id="b0a75-139">When you set one of these properties to `true`, you should then override and define processing for the associated methods.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b0a75-140">Služby musí přepsat alespoň <xref:System.ServiceProcess.ServiceBase.OnStart%2A> a <xref:System.ServiceProcess.ServiceBase.OnStop%2A> být užitečné.</span><span class="sxs-lookup"><span data-stu-id="b0a75-140">Your service must override at least <xref:System.ServiceProcess.ServiceBase.OnStart%2A> and <xref:System.ServiceProcess.ServiceBase.OnStop%2A> to be useful.</span></span>  
  
 <span data-ttu-id="b0a75-141">Můžete také použít komponenty s názvem <xref:System.ServiceProcess.ServiceController> řídí chování existující službu a komunikovat s.</span><span class="sxs-lookup"><span data-stu-id="b0a75-141">You can also use a component called the <xref:System.ServiceProcess.ServiceController> to communicate with and control the behavior of an existing service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0a75-142">Viz také</span><span class="sxs-lookup"><span data-stu-id="b0a75-142">See Also</span></span>  
 [<span data-ttu-id="b0a75-143">Úvod do aplikace služby systému Windows</span><span class="sxs-lookup"><span data-stu-id="b0a75-143">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [<span data-ttu-id="b0a75-144">Postupy: vytváření služeb systému Windows</span><span class="sxs-lookup"><span data-stu-id="b0a75-144">How to: Create Windows Services</span></span>](../../../docs/framework/windows-services/how-to-create-windows-services.md)
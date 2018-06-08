---
title: Vytvořte odolné služby, které jsou připravené pro cloud. Zapojení přechodných chyb v cloudu
description: Modernizovat existující aplikace .NET s kontejnery cloudu Azure a Windows | Vytvořte odolné služby, které jsou připravené pro cloud. Zapojení přechodných chyb v cloudu
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/30/2018
ms.openlocfilehash: 1df21d0f647b96c315686921276be3526f66bbc8
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/10/2018
---
# <a name="build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud"></a><span data-ttu-id="57ea6-105">Vytvářet odolné služby, které jsou připravené pro cloud: zapojení přechodných chyb v cloudu</span><span class="sxs-lookup"><span data-stu-id="57ea6-105">Build resilient services ready for the cloud: Embrace transient failures in the cloud</span></span>

<span data-ttu-id="57ea6-106">Odolnost proti chybám je možnost obnovení v případě selhání a i nadále fungovat.</span><span class="sxs-lookup"><span data-stu-id="57ea6-106">Resiliency is the ability to recover from failures and continue to function.</span></span> <span data-ttu-id="57ea6-107">Odolnost proti chybám není o zamezení selhání, ale přijímá fakt, že dojde k selhání a pak reagovat na ně způsobem, který zabraňuje výpadku nebo ztráty dat.</span><span class="sxs-lookup"><span data-stu-id="57ea6-107">Resiliency is not about avoiding failures, but accepting the fact that failures will occur, and then responding to them in a way that avoids downtime or data loss.</span></span> <span data-ttu-id="57ea6-108">Cílem odolnosti je pro návrat aplikace plně funkčního stavu po selhání.</span><span class="sxs-lookup"><span data-stu-id="57ea6-108">The goal of resiliency is to return the application to a fully functioning state after a failure.</span></span>

<span data-ttu-id="57ea6-109">Když minimálně implementuje model na základě softwaru odolnosti, nikoli model založené na hardwaru, je aplikace připravená pro cloud.</span><span class="sxs-lookup"><span data-stu-id="57ea6-109">Your application is ready for the cloud when, at a minimum, it implements a software-based model of resiliency, rather than a hardware-based model.</span></span> <span data-ttu-id="57ea6-110">Cloudové aplikace musí použít částečný chyby, ke kterým dojde jistě.</span><span class="sxs-lookup"><span data-stu-id="57ea6-110">Your cloud application must embrace the partial failures that will certainly occur.</span></span> <span data-ttu-id="57ea6-111">Navrhujete nebo částečně Refaktorovat aplikace zajistit odolnost proti chybám s očekávanou částečné chybami.</span><span class="sxs-lookup"><span data-stu-id="57ea6-111">Design or partially refactor your application to achieve resiliency with expected partial failures.</span></span> <span data-ttu-id="57ea6-112">Ho by se měly navrhovat zvládnout částečné selhání jako přechodný síťový výpadky a uzly nebo chybám v cloudu virtuálních počítačů.</span><span class="sxs-lookup"><span data-stu-id="57ea6-112">It should be designed to cope with partial failures, like transient network outages and nodes, or VMs crashing in the cloud.</span></span> <span data-ttu-id="57ea6-113">I kontejnery přesouvá na jiný uzel v clusteru služby orchestrator může způsobit občasné krátké chyby v aplikaci.</span><span class="sxs-lookup"><span data-stu-id="57ea6-113">Even containers being moved to a different node within an orchestrator cluster can cause intermittent short failures within the application.</span></span>

## <a name="handling-partial-failure"></a><span data-ttu-id="57ea6-114">Částečné selhání zpracování</span><span class="sxs-lookup"><span data-stu-id="57ea6-114">Handling partial failure</span></span>

<span data-ttu-id="57ea6-115">V aplikaci založené na cloudu je všudypřítomné riziko částečné selhání.</span><span class="sxs-lookup"><span data-stu-id="57ea6-115">In a cloud-based application, there's an ever-present risk of partial failure.</span></span> <span data-ttu-id="57ea6-116">Například jeden web instance nebo kontejner může selhat nebo může být k dispozici nebo po krátkou dobu reagovat.</span><span class="sxs-lookup"><span data-stu-id="57ea6-116">For instance, a single website instance or a container might fail, or it might be unavailable or unresponsive for a short time.</span></span> <span data-ttu-id="57ea6-117">Nebo může dojít k selhání jednoho virtuálního počítače nebo serveru.</span><span class="sxs-lookup"><span data-stu-id="57ea6-117">Or, a single VM or server might crash.</span></span>

<span data-ttu-id="57ea6-118">Protože služby a klienti jsou samostatné procesy, nemusí být schopné reagovat včas na žádost klienta služby.</span><span class="sxs-lookup"><span data-stu-id="57ea6-118">Because clients and services are separate processes, a service might not be able to respond in a timely manner to a client's request.</span></span> <span data-ttu-id="57ea6-119">Služby mohou být přetížené a reagovat na požadavky pomalu nebo nemusí být dostupný po krátkou dobu z důvodu problémů se sítí.</span><span class="sxs-lookup"><span data-stu-id="57ea6-119">The service might be overloaded and respond slowly to requests, or it might not be accessible for a short time because of network issues.</span></span>

<span data-ttu-id="57ea6-120">Představte si třeba monolitický aplikace .NET, který přistupuje k databázi v databázi SQL Azure.</span><span class="sxs-lookup"><span data-stu-id="57ea6-120">For example, consider a monolithic .NET application that accesses a database in Azure SQL Database.</span></span> <span data-ttu-id="57ea6-121">Pokud databáze Azure SQL nebo na jiné služby třetích stran reagovat pro brief čas (Azure SQL database může přesunout do jiného uzlu nebo server a být reagovat na několik sekund), když se uživatel pokusí o provádět žádné akce, může dojít k selhání aplikace a zobra w výjimku ve stejnou chvíli.</span><span class="sxs-lookup"><span data-stu-id="57ea6-121">If the Azure SQL database or any other third-party service is unresponsive for a brief time (an Azure SQL database might be moved to a different node or server, and be unresponsive for a few seconds), when the user tries to do any action, the application might crash and show an exception at the same moment.</span></span>

<span data-ttu-id="57ea6-122">Informace o podobném scénáři může dojít v aplikaci, která využívá služeb HTTP.</span><span class="sxs-lookup"><span data-stu-id="57ea6-122">A similar scenario might occur in an app that consumes HTTP services.</span></span> <span data-ttu-id="57ea6-123">V síti nebo samotnou službu nemusí být k dispozici v cloudu během krátké, přechodné chybě.</span><span class="sxs-lookup"><span data-stu-id="57ea6-123">The network or the service itself might not be available in the cloud during a short, transient failure.</span></span>

<span data-ttu-id="57ea6-124">Odolné aplikace zobrazený v obrázek 4 – 9 by měla implementovat techniky, jako je "opakování s exponenciálního omezení rychlosti" umožnit aplikaci příležitost pro zpracování přechodných chyb v prostředky.</span><span class="sxs-lookup"><span data-stu-id="57ea6-124">A resilient application like the one shown in Figure 4-9 should implement techniques like "retries with exponential backoff" to give the application an opportunity to handle transient failures in resources.</span></span> <span data-ttu-id="57ea6-125">"Okruh moduly dělení" měli použít také v aplikacích.</span><span class="sxs-lookup"><span data-stu-id="57ea6-125">You also should use "circuit breakers" in your applications.</span></span> <span data-ttu-id="57ea6-126">Jistič zastaví aplikace v pokusu o přístup k prostředku, pokud je ve skutečnosti dlouhodobé selhání.</span><span class="sxs-lookup"><span data-stu-id="57ea6-126">A circuit breaker stops an application from trying to access a resource when it's actually a long-term failure.</span></span> <span data-ttu-id="57ea6-127">Pomocí jistič aplikace zabraňuje vzniku rozptylových odepření služby na sebe sama.</span><span class="sxs-lookup"><span data-stu-id="57ea6-127">By using a circuit breaker, the application avoids provoking a denial of service to itself.</span></span>

![Částečné selhání zpracovávaných opakování s exponenciálního omezení rychlosti](./media/image9.png)

> <span data-ttu-id="57ea6-129">**Obrázek 4 – 9.**</span><span class="sxs-lookup"><span data-stu-id="57ea6-129">**Figure 4-9.**</span></span> <span data-ttu-id="57ea6-130">Částečné selhání zpracovávaných opakování s exponenciálního omezení rychlosti</span><span class="sxs-lookup"><span data-stu-id="57ea6-130">Partial failures handled by retries with exponential backoff</span></span>

<span data-ttu-id="57ea6-131">Tyto postupy můžete použít v HTTP prostředky i v databázi prostředků.</span><span class="sxs-lookup"><span data-stu-id="57ea6-131">You can use these techniques both in HTTP resources and in database resources.</span></span> <span data-ttu-id="57ea6-132">Obrázek 4 – 9 aplikace je založena na vrstvě 3 architekturu, proto musíte těchto postupů na úrovni služby (HTTP) a na úrovni vrstvy dat (TCP).</span><span class="sxs-lookup"><span data-stu-id="57ea6-132">In Figure 4-9, the application is based on a 3-tier architecture, so you need these techniques at the services level (HTTP) and at the data tier level (TCP).</span></span> <span data-ttu-id="57ea6-133">V monolitický aplikaci, která používá jenom jedna aplikace vrstvu kromě databáze (žádná další služby nebo mikroslužeb) zpracování přechodných chyb na úrovni připojení databáze může být dost.</span><span class="sxs-lookup"><span data-stu-id="57ea6-133">In a monolithic application that uses only a single app tier in addition to the database (no additional services or microservices), handling transient failures at the database connection level might be enough.</span></span> <span data-ttu-id="57ea6-134">Tento scénář je vyžadován pouze konkrétní konfigurací připojení k databázi.</span><span class="sxs-lookup"><span data-stu-id="57ea6-134">In that scenario, just a particular configuration of the database connection is required.</span></span>

<span data-ttu-id="57ea6-135">Při implementaci odolné komunikaci, která přístup k databázi, v závislosti na verzi rozhraní .NET, které používáte, může být přehledné (například [s Entity Framework 6 nebo novější](https://msdn.microsoft.com/library/dn456835(v=vs.113).aspx), bude stačit konfigurace připojení k databázi).</span><span class="sxs-lookup"><span data-stu-id="57ea6-135">When implementing resilient communications that access the database, depending on the version of .NET you are using, it can be straightforward (for example, [with Entity Framework 6 or later](https://msdn.microsoft.com/library/dn456835(v=vs.113).aspx), it's just a matter of configuring the database connection).</span></span> <span data-ttu-id="57ea6-136">Nebo možná budete muset používat další knihovny jako [přechodné chyby zpracování bloku aplikace](https://msdn.microsoft.com/library/hh680934(v=pandp.50).aspx) (u starších verzí rozhraní .NET), nebo i implementovat vlastní knihovny.</span><span class="sxs-lookup"><span data-stu-id="57ea6-136">Or, you might need to use additional libraries like the [Transient Fault Handling Application Block](https://msdn.microsoft.com/library/hh680934(v=pandp.50).aspx) (for earlier versions of .NET), or even implement your own library.</span></span>

<span data-ttu-id="57ea6-137">Při implementaci HTTP opakování a moduly dělení okruh, doporučení pro .NET je používat [Polly](https://github.com/App-vNext/Polly) knihovny, která cílí na rozhraní .NET Framework 4.0, rozhraní .NET Framework 4.5 a standardní 1.1 rozhraní .NET, včetně podpory .NET Core.</span><span class="sxs-lookup"><span data-stu-id="57ea6-137">When implementing HTTP retries and circuit breakers, the recommendation for .NET is to use the [Polly](https://github.com/App-vNext/Polly) library, which targets .NET Framework 4.0, .NET Framework 4.5, and .NET Standard 1.1, which includes .NET Core support.</span></span>

<span data-ttu-id="57ea6-138">Pokud chcete dozvědět, jak implementovat strategie pro zpracování částečné selhání v cloudu, najdete v následujících odkazů.</span><span class="sxs-lookup"><span data-stu-id="57ea6-138">To learn how to implement strategies for handling partial failures in the cloud, see the following references.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="57ea6-139">Další zdroje</span><span class="sxs-lookup"><span data-stu-id="57ea6-139">Additional resources</span></span>

-   <span data-ttu-id="57ea6-140">**Implementace odolné komunikace pro zpracování částečné selhání**</span><span class="sxs-lookup"><span data-stu-id="57ea6-140">**Implementing resilient communication to handle partial failure**</span></span>

    [https://docs.microsoft.com/dotnet/standard/microservices-architecture/implement-resilient-applications/partial-failure-strategies](../../microservices-architecture/implement-resilient-applications/partial-failure-strategies.md)

-   <span data-ttu-id="57ea6-141">**Entity Framework, připojení odolnost proti chybám a zkuste to znovu logiku (verze 6 nebo novější)**</span><span class="sxs-lookup"><span data-stu-id="57ea6-141">**Entity Framework connection resiliency and retry logic (version 6 and later)**</span></span>

    [https://msdn.microsoft.com/library/dn456835(v=vs.113).aspx](https://msdn.microsoft.com/library/dn456835(v=vs.113).aspx)

-   <span data-ttu-id="57ea6-142">**Blok přechodná chyba zpracování aplikace**</span><span class="sxs-lookup"><span data-stu-id="57ea6-142">**The Transient Fault Handling Application Block**</span></span>

-   [https://msdn.microsoft.com/library/hh680934(v=pandp.50).aspx](https://msdn.microsoft.com/library/hh680934(v=pandp.50).aspx)

-   <span data-ttu-id="57ea6-143">**Knihovna Polly pro odolné komunikaci pomocí protokolu HTTP**</span><span class="sxs-lookup"><span data-stu-id="57ea6-143">**Polly library for resilient HTTP communication**</span></span>

    https://github.com/App-vNext/Polly

>[!div class="step-by-step"]
<span data-ttu-id="57ea6-144">[Předchozí](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[další](modernize-your-apps-with-monitoring-and-telemetry.md)</span><span class="sxs-lookup"><span data-stu-id="57ea6-144">[Previous](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[Next](modernize-your-apps-with-monitoring-and-telemetry.md)</span></span>
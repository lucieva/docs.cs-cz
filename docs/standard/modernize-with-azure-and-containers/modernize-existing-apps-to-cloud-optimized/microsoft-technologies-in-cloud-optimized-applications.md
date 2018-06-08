---
title: Technologie Microsoftu v aplikacích optimalizovaných Cloudů
description: Modernizovat existující aplikace .NET s kontejnery cloudu Azure a Windows | Technologie Microsoftu v aplikacích optimalizovaných Cloudů
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: ece366ee3918124bb60e367d3c7447c1d4555c72
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/10/2018
---
# <a name="microsoft-technologies-in-cloud-optimized-applications"></a><span data-ttu-id="ccf06-103">Technologie Microsoftu v aplikacích optimalizovaných cloudů</span><span class="sxs-lookup"><span data-stu-id="ccf06-103">Microsoft technologies in cloud-optimized applications</span></span>

<span data-ttu-id="ccf06-104">Následující seznam popisuje nástroje, technologií a řešení, které jsou rozpoznána jako požadavky optimalizovaný pro cloudové aplikace.</span><span class="sxs-lookup"><span data-stu-id="ccf06-104">The following list describes the tools, technologies, and solutions that are recognized as requirements for Cloud-Optimized apps.</span></span> <span data-ttu-id="ccf06-105">Elementy optimalizovaných Cloudů může přijmout selektivně nebo postupně, v závislosti na vašich priorit.</span><span class="sxs-lookup"><span data-stu-id="ccf06-105">You can adopt Cloud-Optimized elements selectively or gradually, depending on your priorities.</span></span>

-   <span data-ttu-id="ccf06-106">**Infrastruktura cloudu**: infrastruktury, který poskytuje výpočetní platforma, operačního systému, sítě a úložiště.</span><span class="sxs-lookup"><span data-stu-id="ccf06-106">**Cloud infrastructure**: The infrastructure that provides the compute platform, operating system, network, and storage.</span></span> <span data-ttu-id="ccf06-107">Microsoft Azure je nastavený na této úrovni.</span><span class="sxs-lookup"><span data-stu-id="ccf06-107">Microsoft Azure is positioned at this level.</span></span>

-   <span data-ttu-id="ccf06-108">**Modul runtime**: Tato vrstva nabízí prostředí pro spuštění aplikace.</span><span class="sxs-lookup"><span data-stu-id="ccf06-108">**Runtime**: This layer provides the environment for the application to run.</span></span> <span data-ttu-id="ccf06-109">Pokud používáte kontejnery, tato vrstva obvykle podle [modulu Docker](https://docs.docker.com/engine/), spuštěné v hostitelích Linux nebo na hostitelích systému Windows.</span><span class="sxs-lookup"><span data-stu-id="ccf06-109">If you are using containers, this layer usually is based on [Docker Engine](https://docs.docker.com/engine/), running either on Linux hosts or on Windows hosts.</span></span> <span data-ttu-id="ccf06-110">([Windows kontejnery](https://docs.microsoft.com/virtualization/windowscontainers/about/) jsou podporované od verze systému Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="ccf06-110">([Windows Containers](https://docs.microsoft.com/virtualization/windowscontainers/about/) are supported beginning with Windows Server 2016.</span></span> <span data-ttu-id="ccf06-111">Kontejnery Windows je nejlepší volbou pro existující aplikace rozhraní .NET Framework, které běží v systému Windows.)</span><span class="sxs-lookup"><span data-stu-id="ccf06-111">Windows Containers is the best choice for existing .NET Framework applications that run on Windows.)</span></span>

-   <span data-ttu-id="ccf06-112">**Spravované cloudové**: Pokud si zvolíte možnost spravovanou cloudovou, se můžete vyhnout se nákladům a složitým Správa a podpora základní infrastrukturu, virtuální počítače, opravy operačního systému a konfiguraci sítě.</span><span class="sxs-lookup"><span data-stu-id="ccf06-112">**Managed cloud**: When you choose a managed cloud option, you can avoid the expense and complexity of managing and supporting the underlying infrastructure, VMs, OS patches, and networking configuration.</span></span> <span data-ttu-id="ccf06-113">Pokud si zvolíte migrace pomocí IaaS, jste odpovědni pro všechny tyto úlohy a souvisejících nákladů.</span><span class="sxs-lookup"><span data-stu-id="ccf06-113">If you choose to migrate by using IaaS, you are responsible for all of these tasks, and for associated costs.</span></span> <span data-ttu-id="ccf06-114">V možnosti spravované cloudu spravovat jenom aplikace a služby, které vyvíjíte.</span><span class="sxs-lookup"><span data-stu-id="ccf06-114">In a managed cloud option, you manage only the applications and services that you develop.</span></span> <span data-ttu-id="ccf06-115">Poskytovatel cloudové služby obvykle spravuje nic jiného.</span><span class="sxs-lookup"><span data-stu-id="ccf06-115">The cloud service provider typically manages everything else.</span></span> <span data-ttu-id="ccf06-116">Příklady spravované cloudové služby v Azure [Azure SQL Database](https://azure.microsoft.com/services/sql-database), [Azure Redis Cache](https://azure.microsoft.com/services/cache/), [Azure Cosmos DB](https://azure.microsoft.com/services/cosmos-db/), [Azure Storage](https://azure.microsoft.com/services/storage/), [Azure Database pro databázi MySQL](https://azure.microsoft.com/services/mysql/), [databáze Azure pro PostgreSQL](https://azure.microsoft.com/services/postgresql/), [Azure Active Directory](https://azure.microsoft.com/services/active-directory/)a spravovat výpočetní služby, jako je [škálování virtuálních počítačů Nastaví](https://azure.microsoft.com/services/virtual-machine-scale-sets/), [Azure Service Fabric](https://azure.microsoft.com/services/service-fabric/), [Azure App Service](https://azure.microsoft.com/services/app-service/), a [Azure Kubernetes Service](https://azure.microsoft.com/services/container-service/).</span><span class="sxs-lookup"><span data-stu-id="ccf06-116">Examples of managed cloud services in Azure include [Azure SQL Database](https://azure.microsoft.com/services/sql-database), [Azure Redis Cache](https://azure.microsoft.com/services/cache/), [Azure Cosmos DB](https://azure.microsoft.com/services/cosmos-db/), [Azure Storage](https://azure.microsoft.com/services/storage/), [Azure Database for MySQL](https://azure.microsoft.com/services/mysql/), [Azure Database for PostgreSQL](https://azure.microsoft.com/services/postgresql/), [Azure Active Directory](https://azure.microsoft.com/services/active-directory/), and managed compute services like [VM scale sets](https://azure.microsoft.com/services/virtual-machine-scale-sets/), [Azure Service Fabric](https://azure.microsoft.com/services/service-fabric/), [Azure App Service](https://azure.microsoft.com/services/app-service/), and [Azure Kubernetes Service](https://azure.microsoft.com/services/container-service/).</span></span>

-   <span data-ttu-id="ccf06-117">**Vývoj aplikací**: můžete vybrat z mnoha jazycích při sestavování aplikací, které běží v kontejnerech.</span><span class="sxs-lookup"><span data-stu-id="ccf06-117">**Application development**: You can choose from many languages when you build applications that run in containers.</span></span> <span data-ttu-id="ccf06-118">Tato příručka se zaměřuje na [.NET](https://www.microsoft.com/net), ale můžete vyvíjet aplikace založené na kontejneru pomocí jiných jazyků, jako je pružiny Node.js, Python, nebo Java, nebo přejděte.</span><span class="sxs-lookup"><span data-stu-id="ccf06-118">This guide focuses on [.NET](https://www.microsoft.com/net), but, you can develop container-based apps by using other languages, like Node.js, Python, Spring/Java, or Go.</span></span>

-   <span data-ttu-id="ccf06-119">**Monitorování, telemetrie, protokolování a auditování**: možnost sledování a audit aplikací a kontejnerů, které běží v cloudu je důležité pro každou aplikaci, optimalizovaných Cloudů.</span><span class="sxs-lookup"><span data-stu-id="ccf06-119">**Monitoring, telemetry, logging, and auditing**: The ability to monitor and audit applications and containers that are running in the cloud is critical for any Cloud-Optimized application.</span></span> <span data-ttu-id="ccf06-120">[Azure Application Insights](https://azure.microsoft.com/services/application-insights/) a [Microsoft Operations Management Suite](https://www.microsoft.com/cloud-platform/operations-management-suite) hlavní nástroje Microsoft, které poskytují sledování a auditování pro optimalizovaný pro cloudové aplikace.</span><span class="sxs-lookup"><span data-stu-id="ccf06-120">[Azure Application Insights](https://azure.microsoft.com/services/application-insights/) and [Microsoft Operations Management Suite](https://www.microsoft.com/cloud-platform/operations-management-suite) are the main Microsoft tools that provide monitoring and auditing for Cloud-Optimized apps.</span></span>

-   <span data-ttu-id="ccf06-121">**Zřizování**: nástrojům pro automatizaci můžete zřídit infrastruktury a nasadit aplikace do prostředí s více (produkční, testování, pracovní).</span><span class="sxs-lookup"><span data-stu-id="ccf06-121">**Provisioning**: Automation tools help you provision the infrastructure and deploy an application to multiple environments (production, testing, staging).</span></span> <span data-ttu-id="ccf06-122">Nástroje jako Chef nebo Puppet slouží ke správě konfigurace a prostředí dané aplikace.</span><span class="sxs-lookup"><span data-stu-id="ccf06-122">You can use tools like Chef and Puppet to manage an application's configuration and environment.</span></span> <span data-ttu-id="ccf06-123">Tuto vrstvu lze také implementovat pomocí jednodušší a více direct přístupy.</span><span class="sxs-lookup"><span data-stu-id="ccf06-123">This layer also can be implemented by using simpler and more direct approaches.</span></span> <span data-ttu-id="ccf06-124">Například můžete nasadit přímo pomocí rozhraní příkazového řádku Azure (Azure CLI) nástrojů a pak použijte průběžné nasazování a release management kanály v [Visual Studio Team Services](https://www.visualstudio.com/team-services/).</span><span class="sxs-lookup"><span data-stu-id="ccf06-124">For example, you can deploy directly by using Azure command-line interface (Azure CLI) tooling, and then use the continuous deployment and release management pipelines in [Visual Studio Team Services](https://www.visualstudio.com/team-services/).</span></span>

-   <span data-ttu-id="ccf06-125">**Životní cyklus aplikace**: [Visual Studio Team Services](https://www.visualstudio.com/team-services/) a dalších nástrojů, jako je volaných, jsou integrované automatizační servery, které vám pomohou implementovat CI/CD kanály, včetně správy verzí.</span><span class="sxs-lookup"><span data-stu-id="ccf06-125">**Application lifecycle**: [Visual Studio Team Services](https://www.visualstudio.com/team-services/) and other tools, like Jenkins, are built automation servers that help you implement CI/CD pipelines, including release management.</span></span>

<span data-ttu-id="ccf06-126">V dalších částech této kapitoly a související návody zaměřuje konkrétně na podrobnosti o vrstvě runtime (Windows kontejnery).</span><span class="sxs-lookup"><span data-stu-id="ccf06-126">The next sections of this chapter, and the related walkthroughs, focus specifically on details about the runtime layer (Windows Containers).</span></span> <span data-ttu-id="ccf06-127">Pokyny popisuje způsoby, jak můžete nasadit kontejnery Windows na Windows Server 2016 (nebo novější verze) virtuálních počítačů a instancí Azure kontejneru.</span><span class="sxs-lookup"><span data-stu-id="ccf06-127">The guidance describes the ways you can deploy Windows Containers on Windows Server 2016 (and later versions) VMs and Azure Container Instances.</span></span> <span data-ttu-id="ccf06-128">Také vysvětluje pokročilejší PaaS platformách, jako je Azure App Service a orchestrator jako Azure Service Fabric a Kubernetes služby Azure.</span><span class="sxs-lookup"><span data-stu-id="ccf06-128">It also covers more advanced PaaS platforms like Azure App Service and orchestrator like Azure Service Fabric and Azure Kubernetes Service.</span></span>

## <a name="monolithic-applications-can-be-cloud-optimized"></a><span data-ttu-id="ccf06-129">Monolitický aplikace *můžete* být optimalizovaných Cloudů</span><span class="sxs-lookup"><span data-stu-id="ccf06-129">Monolithic applications *can* be Cloud-Optimized</span></span>

<span data-ttu-id="ccf06-130">Je důležité, abyste měli na očích které monolitický aplikace (aplikace, které nejsou založené na mikroslužeb) *můžete* optimalizovaných Cloudů aplikacemi.</span><span class="sxs-lookup"><span data-stu-id="ccf06-130">It's important to highlight that monolithic applications (applications that are not based on microservices) *can* be Cloud-Optimized applications.</span></span> <span data-ttu-id="ccf06-131">Můžete sestavit a pracovat monolitický aplikací využívajících cloud computing modelu pomocí kombinace kontejnery, nastavené průběžné doručování a DevOps.</span><span class="sxs-lookup"><span data-stu-id="ccf06-131">You can build and operate monolithic applications that take advantage of the cloud computing model by using a combination of containers, continuous delivery, and DevOps.</span></span> <span data-ttu-id="ccf06-132">Pokud stávající aplikaci monolitický správné pro obchodní cíle, můžete ho modernizovat a nastavit jej jako optimalizovaných Cloudů.</span><span class="sxs-lookup"><span data-stu-id="ccf06-132">If an existing monolithic application is right for your business goals, you can modernize it and make it Cloud-Optimized.</span></span>

<span data-ttu-id="ccf06-133">Podobně pokud monolitický aplikace mohou být optimalizované cloudové aplikace, architektury, které složitější jako vícevrstvé aplikace může také být modernized jako optimalizovaný pro cloudové aplikace.</span><span class="sxs-lookup"><span data-stu-id="ccf06-133">Similarly, if monolithic applications can be Cloud-Optimized applications, other, more complex architectures like N-Tier applications can also be modernized as Cloud-Optimized applications.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="ccf06-134">[Předchozí](reasons-to-modernize-existing-net-apps-to-cloud-optimized-applications.md)
[další](what-about-cloud-native-applications.md)</span><span class="sxs-lookup"><span data-stu-id="ccf06-134">[Previous](reasons-to-modernize-existing-net-apps-to-cloud-optimized-applications.md)
[Next](what-about-cloud-native-applications.md)</span></span>
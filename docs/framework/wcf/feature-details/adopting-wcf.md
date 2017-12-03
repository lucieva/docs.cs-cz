---
title: "Přijetí WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 49ba71e2-9468-4082-84c5-cf8daf95e34a
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 15fc02882148054fe53534c75905f51cfffe68fe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="adopting-windows-communication-foundation"></a><span data-ttu-id="30f0e-102">Přijetí WCF</span><span class="sxs-lookup"><span data-stu-id="30f0e-102">Adopting Windows Communication Foundation</span></span>
<span data-ttu-id="30f0e-103">Můžete použít [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] pro nový vývoj, když budete pokračovat, chcete-li zachovat stávající aplikace vyvinuté pomocí technologie ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="30f0e-103">You can choose to use [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] for new development, while continuing to maintain existing applications developed using ASP.NET.</span></span> <span data-ttu-id="30f0e-104">Protože [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] je by měla být nejvhodnější volbou pro usnadnění komunikace s aplikace vytvořené pomocí rozhraní .NET Framework v žádném scénáři, mohl sloužit jako standardní nástroj pro širokou škálu problémy s komunikací softwaru způsobem řešení aby nelze ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="30f0e-104">Because [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] is intended to be the most suitable choice for facilitating communication with applications built with the .NET Framework in any scenario, it can serve as a standard tool for solving a wide variety of software communications problems in a way that ASP.NET cannot.</span></span>  
  
 <span data-ttu-id="30f0e-105">Nové [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] mohou být aplikace nasazeny na počítačích, stejný jako stávající webových služeb ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="30f0e-105">New [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications can be deployed on the same machines as existing ASP.NET Web services.</span></span> <span data-ttu-id="30f0e-106">Pokud existujících webových služeb ASP.NET použijte verzi rozhraní .NET Framework verze 2.0, pak můžete použít nástroj ASP.NET IIS Registration selektivně nasazení rozhraní .NET Framework 2.0 do aplikace služby IIS, ve kterém nové [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] aplikace jsou pro hostování.</span><span class="sxs-lookup"><span data-stu-id="30f0e-106">If the existing ASP.NET Web services use a version of the .NET Framework prior to version 2.0, then you can use the ASP.NET IIS Registration Tool to selectively deploy the .NET Framework 2.0 to IIS applications in which new [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications are to be hosted.</span></span> <span data-ttu-id="30f0e-107">Tento nástroj je popsána v [ASP.NET IIS Registration Tool (Aspnet_regiis.exe)](http://go.microsoft.com/fwlink/?LinkId=94687), a je součástí uživatelské rozhraní konzoly pro správu služby IIS 6.0.</span><span class="sxs-lookup"><span data-stu-id="30f0e-107">That tool is documented at [ASP.NET IIS Registration Tool (Aspnet_regiis.exe)](http://go.microsoft.com/fwlink/?LinkId=94687), and has a user interface built into the IIS 6.0 management console.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="30f0e-108">slouží k přidání nových funkcí do existující webových služeb ASP.NET přidáním [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] služby, které jsou nakonfigurovány na spuštění v režimu kompatibility ASP.NET do stávajících aplikací ASP.NET – webové služby ve službě IIS.</span><span class="sxs-lookup"><span data-stu-id="30f0e-108"> can be used to add new features to existing ASP.NET Web services by adding [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services configured to run in ASP.NET compatibility mode to existing ASP.NET Web service applications in IIS.</span></span> <span data-ttu-id="30f0e-109">Z důvodu režimu kompatibility ASP.NET, kód pro nové [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] služby můžete používat a aktualizovat stejné informace o stavu aplikace jako existující kódu ASP.NET pomocí <xref:System.Web.HttpContext> třídy.</span><span class="sxs-lookup"><span data-stu-id="30f0e-109">Because of ASP.NET compatibility mode, the code for the new [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services can access and update the same application state information as the pre-existing ASP.NET code, by using the <xref:System.Web.HttpContext> class.</span></span> <span data-ttu-id="30f0e-110">Aplikace můžou taky sdílet stejné knihovny tříd.</span><span class="sxs-lookup"><span data-stu-id="30f0e-110">The applications can also share the same class libraries.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="30f0e-111">Klienti mohou používat webových služeb ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="30f0e-111"> clients can use ASP.NET Web services.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="30f0e-112">služby, které jsou nakonfigurované <xref:System.ServiceModel.BasicHttpBinding> mohou být využívána klienty webové služby ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="30f0e-112"> services that are configured with the <xref:System.ServiceModel.BasicHttpBinding> can be used by ASP.NET Web service clients.</span></span> <span data-ttu-id="30f0e-113">ASP.NET – webové služby může existovat společně s [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] aplikace, a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] lze použít i pro přidání funkcí do existující webové služby ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="30f0e-113">ASP.NET Web services can co-exist with [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications, and [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] can even be used to add features to existing ASP.NET Web services.</span></span> <span data-ttu-id="30f0e-114">Všechny tyto způsoby zadané ve kterém [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] a webových služeb ASP.NET je možné společně použít, můžete chtít migrace webových služeb ASP.NET na [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] pouze v případě, že budete potřebovat funkce, které jsou poskytovány [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] a není webových služeb ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="30f0e-114">Given all of these ways in which [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] and ASP.NET Web services can be used together, you may want to migrate ASP.NET Web services to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] only if you require features that are provided by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] and not ASP.NET Web services.</span></span>  
  
 <span data-ttu-id="30f0e-115">I v několika případech, kdy je nezbytné pečlivě zvažte, že migrace kód z jednoho technologie do jiného je málokdy správný přístup.</span><span class="sxs-lookup"><span data-stu-id="30f0e-115">Even in the few cases where it is necessary, carefully consider that migrating code from one technology to another is seldom the correct approach.</span></span> <span data-ttu-id="30f0e-116">Důvodem pro přijetí nové technologie je splňují nové požadavky, které nelze splnit s dřívější technologie a v takovém případě správný krokem je návrhu nové řešení ke splnění nově rozšířit sadu požadavků.</span><span class="sxs-lookup"><span data-stu-id="30f0e-116">The reason for adopting the new technology is to meet new requirements that cannot be met with the earlier technology, and in that case, the correct thing to do is to design a new solution to meet the newly-expanded set of requirements.</span></span> <span data-ttu-id="30f0e-117">Nové výhody návrhu z vašich zkušeností s stávajícího systému a moudrý získávají vzhledem k tomu, že byla navržená tak, že systému.</span><span class="sxs-lookup"><span data-stu-id="30f0e-117">The new design benefits from your experience with the existing system and from wisdom gained since that system was designed.</span></span> <span data-ttu-id="30f0e-118">Nový design použít také veškeré funkce nové technologie a ne reprodukci staré návrhu na nové platformě.</span><span class="sxs-lookup"><span data-stu-id="30f0e-118">The new design can also use the full capabilities of the new technologies rather than reproducing the old design on the new platform.</span></span> <span data-ttu-id="30f0e-119">Po vytváření prototypů klíčové prvky nového návrhu bude jednodušší opětovné použití kódu z existujícího systému v rámci nového.</span><span class="sxs-lookup"><span data-stu-id="30f0e-119">After prototyping key elements of the new design, it becomes easier to re-use code from the existing system within the new one.</span></span>  
  
 <span data-ttu-id="30f0e-120">V několika případech, kde Portování ze ASP.NET Web služeb na [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] je správným řešením v následujícím oddílu najdete některé pokyny o tom, jak pokračovat.</span><span class="sxs-lookup"><span data-stu-id="30f0e-120">For the few cases where porting from ASP.NET Web services to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] is the correct solution, the following section provides some guidance on how to proceed.</span></span> <span data-ttu-id="30f0e-121">Není Rady, jak migrovat služby a jak migraci klientů.</span><span class="sxs-lookup"><span data-stu-id="30f0e-121">There is advice on how to migrate services, and how to migrate clients.</span></span>  
  
 <span data-ttu-id="30f0e-122">Dokončení analýzy o tom, jak migrovat existující webové služby ASP.NET na WCF najdete v tématu [webových služeb ASP.NET a Windows Communication Foundation](http://go.microsoft.com/fwlink/?LinkID=71761).</span><span class="sxs-lookup"><span data-stu-id="30f0e-122">For a complete analysis on how to migrate existing ASP.NET Web Services to WCF please see [ASP.NET Web Services and the Windows Communication Foundation](http://go.microsoft.com/fwlink/?LinkID=71761).</span></span> <span data-ttu-id="30f0e-123">Tato část popisuje, jak implementovat kompatibilní služby WCF z metadat pro vás webovou službu ASP.NET a postup migrace kódu klienta a služby webové technologie ASP.NET do [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="30f0e-123">This section describes how to implement a compliant WCF service from the metadata for you ASP.NET Web Service, and how to migrate ASP.NET Web service and client code to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30f0e-124">Viz také</span><span class="sxs-lookup"><span data-stu-id="30f0e-124">See Also</span></span>  
 [<span data-ttu-id="30f0e-125">Postupy: načtení metadat a implementovat kompatibilní služby</span><span class="sxs-lookup"><span data-stu-id="30f0e-125">How to: Retrieve Metadata and Implement a Compliant Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-retrieve-metadata-and-implement-a-compliant-service.md)  
 [<span data-ttu-id="30f0e-126">Postupy: migrace kódu webové služby ASP.NET do služby Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="30f0e-126">How to: Migrate ASP.NET Web Service Code to the Windows Communication Foundation</span></span>](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-to-wcf.md)  
 [<span data-ttu-id="30f0e-127">Postupy: migrace kódu klienta služby technologie ASP.NET do služby Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="30f0e-127">How to: Migrate ASP.NET Web Service Client Code to the Windows Communication Foundation</span></span>](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-client-to-wcf.md)
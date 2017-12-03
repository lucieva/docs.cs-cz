---
title: Hostitel WPF (PresentationHost.exe)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WPF Host application [WPF]
- PresentationHost.exe
ms.assetid: 3215bfa1-722c-4ac8-a7c5-bdd02d30afbd
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8b7662213d7204675de7e8681b6fc8141f04dd21
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/22/2017
---
# <a name="wpf-host-presentationhostexe"></a><span data-ttu-id="cf4bd-102">Hostitel WPF (PresentationHost.exe)</span><span class="sxs-lookup"><span data-stu-id="cf4bd-102">WPF Host (PresentationHost.exe)</span></span>
[!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]<span data-ttu-id="cf4bd-103">Hostitel (PresentationHost.exe) je aplikace, která umožňuje [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] aplikace pro hostování v prohlížečích kompatibilní (včetně [!INCLUDE[TLA#tla_ie6](../../../../includes/tlasharptla-ie6-md.md)] a novější).</span><span class="sxs-lookup"><span data-stu-id="cf4bd-103"> Host (PresentationHost.exe) is the application that enables [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applications to be hosted in compatible browsers (including [!INCLUDE[TLA#tla_ie6](../../../../includes/tlasharptla-ie6-md.md)] and later).</span></span> <span data-ttu-id="cf4bd-104">Ve výchozím nastavení [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] hostitele je registrován jako prostředí a [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] hostované prohlížečem obslužné rutiny pro [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] obsah, který zahrnuje:</span><span class="sxs-lookup"><span data-stu-id="cf4bd-104">By default, [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] Host is registered as the shell and [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] handler for browser-hosted [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] content, which includes:</span></span>  
  
-   <span data-ttu-id="cf4bd-105">Přijít (– nezkompilovaný) [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] soubory (XAML).</span><span class="sxs-lookup"><span data-stu-id="cf4bd-105">Loose (uncompiled) [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files (.xaml).</span></span>  
  
-   [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)]<span data-ttu-id="cf4bd-106">(.xbap).</span><span class="sxs-lookup"><span data-stu-id="cf4bd-106"> (.xbap).</span></span>  
  
 <span data-ttu-id="cf4bd-107">Pro tyto typy souborů [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] hostitele:</span><span class="sxs-lookup"><span data-stu-id="cf4bd-107">For files of these types, [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] Host:</span></span>  
  
-   <span data-ttu-id="cf4bd-108">Spustí zaregistrovanou [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] obslužné rutiny pro hostitele [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] obsah.</span><span class="sxs-lookup"><span data-stu-id="cf4bd-108">Launches the registered [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] handler to host the [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] content.</span></span>  
  
-   <span data-ttu-id="cf4bd-109">Načte správné verze požadované [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] a [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] sestavení.</span><span class="sxs-lookup"><span data-stu-id="cf4bd-109">Loads the right versions of the required [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] and [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] assemblies.</span></span>  
  
-   <span data-ttu-id="cf4bd-110">Zajišťuje, že příslušná úroveň oprávnění pro danou zónu nasazení jsou na místě.</span><span class="sxs-lookup"><span data-stu-id="cf4bd-110">Ensures the appropriate permission levels for the zone of deployment are in place.</span></span>  
  
 <span data-ttu-id="cf4bd-111">Toto téma popisuje parametry příkazového řádku, které lze použít s PresentationHost.exe.</span><span class="sxs-lookup"><span data-stu-id="cf4bd-111">This topic describes the command line parameters that can be used with PresentationHost.exe.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="cf4bd-112">Použití</span><span class="sxs-lookup"><span data-stu-id="cf4bd-112">Usage</span></span>  
 `PresentationHost.exe [parameters] uri|filename`  
  
## <a name="parameters"></a><span data-ttu-id="cf4bd-113">Parametry</span><span class="sxs-lookup"><span data-stu-id="cf4bd-113">Parameters</span></span>  
  
|<span data-ttu-id="cf4bd-114">Parametr</span><span class="sxs-lookup"><span data-stu-id="cf4bd-114">Parameter</span></span>|<span data-ttu-id="cf4bd-115">Popis</span><span class="sxs-lookup"><span data-stu-id="cf4bd-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cf4bd-116">filename</span><span class="sxs-lookup"><span data-stu-id="cf4bd-116">filename</span></span>|<span data-ttu-id="cf4bd-117">Cesta k souboru chcete aktivovat.</span><span class="sxs-lookup"><span data-stu-id="cf4bd-117">The path of the file to be activated.</span></span> <span data-ttu-id="cf4bd-118">Může být také [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cf4bd-118">Can also be a [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>|  
|<span data-ttu-id="cf4bd-119">-ladění</span><span class="sxs-lookup"><span data-stu-id="cf4bd-119">-debug</span></span>|<span data-ttu-id="cf4bd-120">Při aktivaci aplikace, nebudou ho pro potvrzení a spustit z úložiště.</span><span class="sxs-lookup"><span data-stu-id="cf4bd-120">When activating an application, does not commit it to or run it from the store.</span></span> <span data-ttu-id="cf4bd-121">Funguje pouze když je aktivován místního souboru.</span><span class="sxs-lookup"><span data-stu-id="cf4bd-121">This only works when a local file is activated.</span></span>|  
|<span data-ttu-id="cf4bd-122">-debugSecurityZoneURL \<adresa url ></span><span class="sxs-lookup"><span data-stu-id="cf4bd-122">-debugSecurityZoneURL \<url></span></span>|<span data-ttu-id="cf4bd-123">Použít s [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] hodnotu udávající PresentationHost.exe, že aplikace by měla ladit, jako kdyby byly nasazeny ze zadaného [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cf4bd-123">Used with a [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] value to indicate to PresentationHost.exe that an application should be debugged as if it were deployed from the specified [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)].</span></span> <span data-ttu-id="cf4bd-124">Určuje zóny nasazení a lokality původu.</span><span class="sxs-lookup"><span data-stu-id="cf4bd-124">This determines both the deployment zone and the site of origin.</span></span>|  
|<span data-ttu-id="cf4bd-125">-Vložení</span><span class="sxs-lookup"><span data-stu-id="cf4bd-125">-embedding</span></span>|<span data-ttu-id="cf4bd-126">Vyžaduje OLE.</span><span class="sxs-lookup"><span data-stu-id="cf4bd-126">Required by OLE.</span></span> <span data-ttu-id="cf4bd-127">Pokud `-event` nebo `-debug` jsou parametr zadán, není nutné zadávat `-embedding` parametr, protože tento parametr je nastaven interně.</span><span class="sxs-lookup"><span data-stu-id="cf4bd-127">If the `-event` or `-debug` parameter are specified, it is not necessary to specify the `-embedding` parameter, since that parameter is set internally.</span></span>|  
|<span data-ttu-id="cf4bd-128">-událostí \<eventname ></span><span class="sxs-lookup"><span data-stu-id="cf4bd-128">-event \<eventname></span></span>|<span data-ttu-id="cf4bd-129">Otevřete událost s tímto názvem a signalizován ho PresentationHost.exe je inicializována a připravena hostitel [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] obsah.</span><span class="sxs-lookup"><span data-stu-id="cf4bd-129">Open the event with this name and signal it when PresentationHost.exe is initialized and ready to host [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] content.</span></span> <span data-ttu-id="cf4bd-130">PresentationHost.exe bude ukončen. Pokud došlo k chybě při otevírání události, jako třeba když ho dosud nebyla vytvořena.</span><span class="sxs-lookup"><span data-stu-id="cf4bd-130">PresentationHost.exe will terminate if there was an error opening the event, such as if it has not already been created.</span></span>|  
|<span data-ttu-id="cf4bd-131">-launchApplication \<adresa url ></span><span class="sxs-lookup"><span data-stu-id="cf4bd-131">-launchApplication \<url></span></span>|<span data-ttu-id="cf4bd-132">Spouští samostatný [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] aplikace ze zadané adresy URL.</span><span class="sxs-lookup"><span data-stu-id="cf4bd-132">Launches a standalone [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] application from the specified URL.</span></span> [!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)]<span data-ttu-id="cf4bd-133">a jsou použity zásady zabezpečení WinINet týkající se aplikací .NET.</span><span class="sxs-lookup"><span data-stu-id="cf4bd-133"> and WinINet security policy concerning .NET applications are applied.</span></span>|  
  
## <a name="scenarios"></a><span data-ttu-id="cf4bd-134">Scénáře</span><span class="sxs-lookup"><span data-stu-id="cf4bd-134">Scenarios</span></span>  
  
### <a name="shell-handler"></a><span data-ttu-id="cf4bd-135">Obslužná rutina prostředí</span><span class="sxs-lookup"><span data-stu-id="cf4bd-135">Shell Handler</span></span>  
 `PresentationHost.exe example.xbap`  
  
### <a name="mime-handler"></a><span data-ttu-id="cf4bd-136">Obslužná rutina MIME</span><span class="sxs-lookup"><span data-stu-id="cf4bd-136">MIME Handler</span></span>  
 `PresentationHost.exe -embedding example.xbap`  
  
### <a name="visual-studio-debugging"></a><span data-ttu-id="cf4bd-137">Ladění v sadě Visual Studio</span><span class="sxs-lookup"><span data-stu-id="cf4bd-137">Visual Studio Debugging</span></span>  
 `PresentationHost.exe -debug example.xbap`  
  
### <a name="visual-studio-debugging-in-zone"></a><span data-ttu-id="cf4bd-138">Ladění v zóně sady Visual Studio</span><span class="sxs-lookup"><span data-stu-id="cf4bd-138">Visual Studio Debugging In Zone</span></span>  
 `PresentationHost.exe -debug -debugSecurityZoneURL http://www.example.com c:\folderpath\example.xbap`  
  
## <a name="see-also"></a><span data-ttu-id="cf4bd-139">Viz také</span><span class="sxs-lookup"><span data-stu-id="cf4bd-139">See Also</span></span>  
 [<span data-ttu-id="cf4bd-140">Zabezpečení</span><span class="sxs-lookup"><span data-stu-id="cf4bd-140">Security</span></span>](../../../../docs/framework/wpf/security-wpf.md)
---
title: "Postupy: Zjištění instalovaného modulu plugin WPF pro Firefox"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- plug-in for Firefox [WPF]
- detecting Firefox installation [WPF]
- checking for the Firefox plug-in [WPF]
- Firefox [WPF], detecting installation
- detecting whether the WPF plug-in for Firefox is installed [WPF]
ms.assetid: 5f839373-e3fb-44f1-88ad-4a0761f02189
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3012afc118420a83c869785d26c28f1eee969cb3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed"></a><span data-ttu-id="31634-102">Postupy: Zjištění instalovaného modulu plugin WPF pro Firefox</span><span class="sxs-lookup"><span data-stu-id="31634-102">How to: Detect Whether the WPF Plug-In for Firefox Is Installed</span></span>
<span data-ttu-id="31634-103">[!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] Modulu plug-in pro Firefox umožňuje [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] a ztrátě souborů XAML pro spouštění v prohlížeči Mozilla Firefox.</span><span class="sxs-lookup"><span data-stu-id="31634-103">The [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] plug-in for Firefox enables [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] and loose XAML files to run in the Mozilla Firefox browser.</span></span> <span data-ttu-id="31634-104">Toto téma obsahuje skript napsaný v HTML a JavaScript, který mohou správci zjistit, zda je nainstalována WPF modulu plug-in pro Firefox.</span><span class="sxs-lookup"><span data-stu-id="31634-104">This topic provides a script written in HTML and JavaScript that administrators can use to determine whether the WPF plug-in for Firefox is installed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="31634-105">Další informace o instalaci, nasazování a zjišťování [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], najdete v části [instalaci rozhraní .NET Framework pro vývojáře](../../../../docs/framework/install/guide-for-developers.md).</span><span class="sxs-lookup"><span data-stu-id="31634-105">For more information about installing, deploying, and detecting the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], see [Install the .NET Framework for developers](../../../../docs/framework/install/guide-for-developers.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="31634-106">Příklad</span><span class="sxs-lookup"><span data-stu-id="31634-106">Example</span></span>  
 <span data-ttu-id="31634-107">Když [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] je nainstalovaná, klientský počítač je nakonfigurován v grafickém subsystému WPF, která se modul plug-in pro Firefox.</span><span class="sxs-lookup"><span data-stu-id="31634-107">When the [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] is installed, the client computer is configured with a WPF plug-in for Firefox.</span></span> <span data-ttu-id="31634-108">Následující ukázkový skript kontroluje pro modul plug-in WPF Firefox a poté zobrazí zprávu příslušný stav.</span><span class="sxs-lookup"><span data-stu-id="31634-108">The following example script checks for the WPF plug-in for Firefox and then displays an appropriate status message.</span></span>  
  
```  
<HTML>  
  
  <HEAD>  
    <TITLE>Test for the WPF plug-in for Firefox</TITLE>  
    <META HTTP-EQUIV="Content-Type" CONTENT="text/html; charset=utf-8" />  
    <SCRIPT type="text/javascript">  
    <!--  
    function OnLoad()  
    {  
  
       // Check for the WPF plug-in for Firefox and report  
       var msg = "The WPF plug-in for Firefox is ";  
       var wpfPlugin = navigator.plugins["Windows Presentation Foundation"];  
       if( wpfPlugin != null ) {  
          document.writeln(msg + " installed.");  
       }  
       else {  
          document.writeln(msg + " not installed. Please install or reinstall the .NET Framework 3.5.");  
       }  
    }  
    -->  
    </SCRIPT>  
  </HEAD>  
  
  <BODY onload="OnLoad()" />  
  
</HTML>  
```  
  
 <span data-ttu-id="31634-109">Pokud kontrolu pro modul plug-in WPF Firefox úspěšné, se zobrazí následující zprávu:</span><span class="sxs-lookup"><span data-stu-id="31634-109">If the check for the WPF plug-in for Firefox is successful, the following status message is displayed:</span></span>  
  
 `The WPF plug-in for Firefox is installed.`  
  
 <span data-ttu-id="31634-110">Jinak se zobrazí následující zprávu:</span><span class="sxs-lookup"><span data-stu-id="31634-110">Otherwise, the following status message is displayed:</span></span>  
  
 `The WPF plug-in for Firefox is not installed. Please install or reinstall the .NET Framework 3.5.`  
  
## <a name="see-also"></a><span data-ttu-id="31634-111">Viz také</span><span class="sxs-lookup"><span data-stu-id="31634-111">See Also</span></span>  
 [<span data-ttu-id="31634-112">Zjistit, zda je nainstalována rozhraní .NET Framework 3.0</span><span class="sxs-lookup"><span data-stu-id="31634-112">Detect Whether the .NET Framework 3.0 Is Installed</span></span>](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-net-framework-3-0-is-installed.md)  
 [<span data-ttu-id="31634-113">Zjistit, zda je nainstalována rozhraní .NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="31634-113">Detect Whether the .NET Framework 3.5 Is Installed</span></span>](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-net-framework-3-5-is-installed.md)  
 [<span data-ttu-id="31634-114">Přehled aplikace prohlížeče WPF XAML</span><span class="sxs-lookup"><span data-stu-id="31634-114">WPF XAML Browser Applications Overview</span></span>](../../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md)
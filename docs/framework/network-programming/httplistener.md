---
title: HttpListener
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: HTTP
ms.assetid: 5b89d3fb-3c9a-49e2-af1f-c34c020c68ac
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: ca0a22ff1d06485658da75a46bd408a12a3a964c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="httplistener"></a><span data-ttu-id="2bd87-102">HttpListener</span><span class="sxs-lookup"><span data-stu-id="2bd87-102">HttpListener</span></span>
<span data-ttu-id="2bd87-103"><xref:System.Net.HttpListener> Třída poskytuje prostřednictvím kódu programu řízené naslouchací proces protokolu HTTP.</span><span class="sxs-lookup"><span data-stu-id="2bd87-103">The <xref:System.Net.HttpListener> class provides a programmatically controlled HTTP protocol listener.</span></span> <span data-ttu-id="2bd87-104">Naslouchací proces je aktivní po dobu jeho existence <xref:System.Net.HttpListener> objekt a běží v rámci vaší aplikace.</span><span class="sxs-lookup"><span data-stu-id="2bd87-104">The listener is active for the lifetime of the <xref:System.Net.HttpListener> object and runs within your application.</span></span>  
  
## <a name="httpsys"></a><span data-ttu-id="2bd87-105">HTTP. SYS</span><span class="sxs-lookup"><span data-stu-id="2bd87-105">HTTP.SYS</span></span>  
 <span data-ttu-id="2bd87-106"><xref:System.Net.HttpListener> Třída je postavená na HTTP.sys, což je naslouchací proces režimu jádra, která zpracovává veškeré přenosy dat protokolu HTTP pro systém Windows.</span><span class="sxs-lookup"><span data-stu-id="2bd87-106">The <xref:System.Net.HttpListener> class is built on top of HTTP.sys, which is the kernel mode listener that handles all HTTP traffic for Windows.</span></span> <span data-ttu-id="2bd87-107">Ovladač HTTP.sys poskytuje správu připojení, omezení šířky pásma a protokolování webového serveru.</span><span class="sxs-lookup"><span data-stu-id="2bd87-107">HTTP.sys provides connection management, bandwidth throttling, and Web server logging.</span></span> <span data-ttu-id="2bd87-108">Použití `HttpCfg.exe` nástroje pro přidání certifikáty SSL.</span><span class="sxs-lookup"><span data-stu-id="2bd87-108">Use the `HttpCfg.exe` tool to add SSL certificates.</span></span> <span data-ttu-id="2bd87-109">Další informace najdete v dokumentaci na [HttpCfg.exe](http://go.microsoft.com/fwlink/?LinkID=178284) nástroj v [Server](http://go.microsoft.com/fwlink/?LinkID=178285) dokumentaci.</span><span class="sxs-lookup"><span data-stu-id="2bd87-109">For more information, see the documentation on the [HttpCfg.exe](http://go.microsoft.com/fwlink/?LinkID=178284) tool in the [Server](http://go.microsoft.com/fwlink/?LinkID=178285) documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bd87-110">Viz také</span><span class="sxs-lookup"><span data-stu-id="2bd87-110">See Also</span></span>  
 <xref:System.Net.HttpListener>  
 <xref:System.Net.HttpWebRequest>  
 <xref:System.Net.HttpWebResponse>  
 [<span data-ttu-id="2bd87-111">HTTP Server</span><span class="sxs-lookup"><span data-stu-id="2bd87-111">HTTP Server</span></span>](http://go.microsoft.com/fwlink/?LinkID=178285)  
 [<span data-ttu-id="2bd87-112">Vylepšení zabezpečení v Internetové informační</span><span class="sxs-lookup"><span data-stu-id="2bd87-112">Security Enhancements in Internet Information</span></span>](http://go.microsoft.com/fwlink/?LinkID=178286)  
 [<span data-ttu-id="2bd87-113">Ukázka HttpListener ASPX hostitele aplikace</span><span class="sxs-lookup"><span data-stu-id="2bd87-113">HttpListener ASPX Host Application Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=179560)  
 [<span data-ttu-id="2bd87-114">Ukázka HttpListener technologie</span><span class="sxs-lookup"><span data-stu-id="2bd87-114">HttpListener Technology Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=179558)  
 [<span data-ttu-id="2bd87-115">Síťové programování ukázky</span><span class="sxs-lookup"><span data-stu-id="2bd87-115">Network Programming Samples</span></span>](../../../docs/framework/network-programming/network-programming-samples.md)
---
title: HTTP
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- protocols, HTTP
- sending data, HTTP
- HttpWebResponse class, sending and receiving data
- HTTP
- receiving data, HTTP
- application protocols, HTTP
- Internet, HTTP
- network resources, HTTP
- HTTP, about HTTP
- HttpWebRequest class, sending and receiving data
ms.assetid: 985fe5d8-eb71-4024-b361-41fbdc1618d8
caps.latest.revision: "10"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 701ff252380ef93dbe3668c8aca73f08a8425d6b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="http"></a><span data-ttu-id="bea52-102">HTTP</span><span class="sxs-lookup"><span data-stu-id="bea52-102">HTTP</span></span>
<span data-ttu-id="bea52-103">Rozhraní .NET Framework poskytuje komplexní podporu pro protokol HTTP, který tvoří většina všechny přenosy z Internetu, se <xref:System.Net.HttpWebRequest> a <xref:System.Net.HttpWebResponse> třídy.</span><span class="sxs-lookup"><span data-stu-id="bea52-103">The .NET Framework provides comprehensive support for the HTTP protocol, which makes up the majority of all Internet traffic, with the <xref:System.Net.HttpWebRequest> and <xref:System.Net.HttpWebResponse> classes.</span></span> <span data-ttu-id="bea52-104">Tyto třídy odvozené od <xref:System.Net.WebRequest> a <xref:System.Net.WebResponse>, jsou vráceny ve výchozím nastavení vždy, když statickou metodu <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> zaznamená identifikátor URI začínající "http" nebo "https".</span><span class="sxs-lookup"><span data-stu-id="bea52-104">These classes, derived from <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse>, are returned by default whenever the static method <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> encounters a URI beginning with "http" or "https".</span></span> <span data-ttu-id="bea52-105">Ve většině případů **WebRequest** a **WebResponse** třídy poskytují všechny možnosti, které je potřeba provést žádost, ale pokud budete potřebovat přístup k funkce specifické pro HTTP, které jsou zveřejněné jako vlastnosti, které přiřazení typu Tyto třídy **HttpWebRequest** nebo **HttpWebResponse**.</span><span class="sxs-lookup"><span data-stu-id="bea52-105">In most cases, the **WebRequest** and **WebResponse** classes provide all that is necessary to make the request, but if you need access to the HTTP-specific features exposed as properties, you can typecast these classes to **HttpWebRequest** or **HttpWebResponse**.</span></span>  
  
 <span data-ttu-id="bea52-106">**HttpWebRequest** a **HttpWebResponse** zapouzdřují standardní transakce požadavku a odpovědi HTTP a poskytovat přístup k společné hlavičky HTTP.</span><span class="sxs-lookup"><span data-stu-id="bea52-106">**HttpWebRequest** and **HttpWebResponse** encapsulate a standard HTTP request-and-response transaction and provide access to common HTTP headers.</span></span> <span data-ttu-id="bea52-107">Tyto třídy také podporují většinu funkcí HTTP 1.1, včetně zřetězení příkazů, odesílání a přijímání dat v bloky dat, ověřování, předběžné ověření, šifrování, podpora proxy, se ověřování certifikátu serveru a správu připojení.</span><span class="sxs-lookup"><span data-stu-id="bea52-107">These classes also support most HTTP 1.1 features, including pipelining, sending and receiving data in chunks, authentication, preauthentication, encryption, proxy support, server certificate validation, and connection management.</span></span> <span data-ttu-id="bea52-108">Vlastní hlavičky a není zajišťováno prostřednictvím vlastnosti můžete ukládat a přistupovat prostřednictvím **hlavičky** vlastnost.</span><span class="sxs-lookup"><span data-stu-id="bea52-108">Custom headers and headers not provided through properties can be stored in and accessed through the **Headers** property.</span></span>  
  
 <span data-ttu-id="bea52-109">**HttpWebRequest** je výchozí třídy používané **WebRequest** a není potřeba před můžete předat identifikátor URI pro být zaregistrován **WebRequest.Create** metoda.</span><span class="sxs-lookup"><span data-stu-id="bea52-109">**HttpWebRequest** is the default class used by **WebRequest** and does not need to be registered before you can pass a URI to the **WebRequest.Create** method.</span></span>  
  
 <span data-ttu-id="bea52-110">Můžete použít aplikaci držet se přesměrování HTTP automaticky nastavením <xref:System.Net.HttpWebRequest.AllowAutoRedirect%2A> vlastnost **true** (výchozí).</span><span class="sxs-lookup"><span data-stu-id="bea52-110">You can make your application follow HTTP redirects automatically by setting the <xref:System.Net.HttpWebRequest.AllowAutoRedirect%2A> property to **true** (the default).</span></span> <span data-ttu-id="bea52-111">Aplikace bude přesměrovávat požadavky a <xref:System.Net.HttpWebResponse.ResponseUri%2A> vlastnost **HttpWebResponse** bude obsahovat skutečné webového prostředku, který odpověděl na žádost.</span><span class="sxs-lookup"><span data-stu-id="bea52-111">The application will redirect requests, and the <xref:System.Net.HttpWebResponse.ResponseUri%2A> property of **HttpWebResponse** will contain the actual Web resource that responded to the request.</span></span> <span data-ttu-id="bea52-112">Pokud nastavíte **AllowAutoRedirect** k **false**, aplikace musí být schopna zpracovávat přesměrování jako chyby protokolu HTTP.</span><span class="sxs-lookup"><span data-stu-id="bea52-112">If you set **AllowAutoRedirect** to **false**, your application must be able to handle redirects as HTTP protocol errors.</span></span>  
  
 <span data-ttu-id="bea52-113">Aplikace obdrží zachytávání chyb protokolu HTTP <xref:System.Net.WebException> s <xref:System.Net.WebException.Status%2A> nastavena na <xref:System.Net.WebExceptionStatus>.</span><span class="sxs-lookup"><span data-stu-id="bea52-113">Applications receive HTTP protocol errors by catching a <xref:System.Net.WebException> with the <xref:System.Net.WebException.Status%2A> set to <xref:System.Net.WebExceptionStatus>.</span></span> <span data-ttu-id="bea52-114"><xref:System.Net.WebException.Response%2A> Vlastnost obsahuje **WebResponse** odeslaných serverem a označuje skutečného došlo k chybě protokolu HTTP.</span><span class="sxs-lookup"><span data-stu-id="bea52-114">The <xref:System.Net.WebException.Response%2A> property contains the **WebResponse** sent by the server and indicates the actual HTTP error encountered.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bea52-115">Viz také</span><span class="sxs-lookup"><span data-stu-id="bea52-115">See Also</span></span>  
 [<span data-ttu-id="bea52-116">Přístup k Internetu prostřednictvím proxy serveru</span><span class="sxs-lookup"><span data-stu-id="bea52-116">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)  
 [<span data-ttu-id="bea52-117">Pomocí protokolů aplikací</span><span class="sxs-lookup"><span data-stu-id="bea52-117">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)  
 [<span data-ttu-id="bea52-118">Postupy: přístup k vlastnosti specifické pro protokol HTTP</span><span class="sxs-lookup"><span data-stu-id="bea52-118">How to: Access HTTP-Specific Properties</span></span>](../../../docs/framework/network-programming/how-to-access-http-specific-properties.md)
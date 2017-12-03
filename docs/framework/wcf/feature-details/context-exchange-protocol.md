---
title: "Protokol kontextové výměny"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3dfd38e0-ae52-491c-94f4-7a862b9843d4
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 582ff24f9f7935f6bbb143685826fc10df1ab432
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="context-exchange-protocol"></a><span data-ttu-id="6ccd0-102">Protokol kontextové výměny</span><span class="sxs-lookup"><span data-stu-id="6ccd0-102">Context Exchange Protocol</span></span>
<span data-ttu-id="6ccd0-103">Tato část popisuje protokol kontextové výměny byla zavedená v [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] verzi.</span><span class="sxs-lookup"><span data-stu-id="6ccd0-103">This section describes the context exchange protocol introduced in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)][!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] release.</span></span> <span data-ttu-id="6ccd0-104">Tento protokol umožňuje kanálem klienta přijmout kontextu poskytl služby a použijte ho pro všechny následné žádosti do této služby, odešlou přes stejnou instanci kanálu klienta.</span><span class="sxs-lookup"><span data-stu-id="6ccd0-104">This protocol allows the client channel to accept a context supplied by a service and apply it to all subsequent requests to that service sent over the same client channel instance.</span></span> <span data-ttu-id="6ccd0-105">Implementace protokol kontextové výměny můžete použít jednu z následujících dvou mechanismů rozšíření kontextu mezi serverem a klientem: soubory cookie protokolu HTTP nebo hlavičku protokolu SOAP.</span><span class="sxs-lookup"><span data-stu-id="6ccd0-105">The implementation of the context exchange protocol can use one of the following two mechanisms to propagate the context between the server and the client: HTTP cookies or a SOAP header.</span></span>  
  
 <span data-ttu-id="6ccd0-106">Protokol kontextové výměny je implementována ve vlastním kanálu vrstvě.</span><span class="sxs-lookup"><span data-stu-id="6ccd0-106">The context exchange protocol is implemented in a custom channel layer.</span></span> <span data-ttu-id="6ccd0-107">Kanál komunikuje kontext do a z aplikace pomocí vrstvy <xref:System.ServiceModel.Channels.ContextMessageProperty> vlastnost.</span><span class="sxs-lookup"><span data-stu-id="6ccd0-107">The channel communicates the context to and from the application layer using a <xref:System.ServiceModel.Channels.ContextMessageProperty> property.</span></span> <span data-ttu-id="6ccd0-108">Hodnota kontextu pro přenos mezi koncovými body, je buď serializovanou jako hlavičku protokolu SOAP ve vrstvě kanálu nebo převést na nebo z vlastnosti zprávy, které představují požadavku HTTP a odpovědí.</span><span class="sxs-lookup"><span data-stu-id="6ccd0-108">For transmission between endpoints, the value of the context is either serialized as a SOAP header at the channel layer, or converted to or from the message properties that represent a HTTP request and response.</span></span> <span data-ttu-id="6ccd0-109">V takovém případě se očekává, že jeden z základní vrstvy kanálu převádí vlastnosti zprávy požadavku a odpovědi HTTP z soubory cookie HTTP, v uvedeném pořadí.</span><span class="sxs-lookup"><span data-stu-id="6ccd0-109">In the latter case, it is expected that one of the underlying channel layers converts the HTTP request and response message properties to and from HTTP cookies, respectively.</span></span> <span data-ttu-id="6ccd0-110">Volba používáno k výměně kontextu se provádí pomocí <xref:System.ServiceModel.Channels.ContextExchangeMechanism> vlastnost <xref:System.ServiceModel.Channels.ContextBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="6ccd0-110">The choice of the mechanism used to exchange the context is done using the <xref:System.ServiceModel.Channels.ContextExchangeMechanism> property on the <xref:System.ServiceModel.Channels.ContextBindingElement>.</span></span> <span data-ttu-id="6ccd0-111">Platné hodnoty jsou `HttpCookie` nebo `SoapHeader`.</span><span class="sxs-lookup"><span data-stu-id="6ccd0-111">Valid values are `HttpCookie` or `SoapHeader`.</span></span>  
  
 <span data-ttu-id="6ccd0-112">Na straně klienta mohou instanci kanál pracovat ve dvou režimech na základě nastavení na vlastnost kanál <xref:System.ServiceModel.Channels.IContextManager.Enabled%2A>.</span><span class="sxs-lookup"><span data-stu-id="6ccd0-112">On the client, an instance of a channel can operate in two modes based on the settings on the channel property, <xref:System.ServiceModel.Channels.IContextManager.Enabled%2A>.</span></span>  
  
## <a name="mode-1-channel-context-management"></a><span data-ttu-id="6ccd0-113">Režim 1: Správa kontextu kanál</span><span class="sxs-lookup"><span data-stu-id="6ccd0-113">Mode 1: Channel Context Management</span></span>  
 <span data-ttu-id="6ccd0-114">Toto je výchozí režim kde <xref:System.ServiceModel.Channels.IContextManager.Enabled%2A> je nastaven na `true`.</span><span class="sxs-lookup"><span data-stu-id="6ccd0-114">This is the default mode where <xref:System.ServiceModel.Channels.IContextManager.Enabled%2A> is set to `true`.</span></span> <span data-ttu-id="6ccd0-115">V tomto režimu kanálu kontextu spravuje kontextu a ukládá do mezipaměti kontextu během celé jeho životnosti.</span><span class="sxs-lookup"><span data-stu-id="6ccd0-115">In this mode the context channel manages the context and caches the context during its lifetime.</span></span> <span data-ttu-id="6ccd0-116">Kontext se dá načíst z tohoto kanálu prostřednictvím vlastnosti kanálu `IContextManager` voláním `GetContext` metoda.</span><span class="sxs-lookup"><span data-stu-id="6ccd0-116">Context can be retrieved from the channel through channel property `IContextManager` by calling the `GetContext` method.</span></span> <span data-ttu-id="6ccd0-117">Kanál může být také předem inicializovaný s konkrétní kontext před otevíráte voláním `SetContext` metodu vlastnosti kanálu.</span><span class="sxs-lookup"><span data-stu-id="6ccd0-117">The channel can also be pre-initialized with specific context before being opened by calling the `SetContext` method on the channel property.</span></span> <span data-ttu-id="6ccd0-118">Po inicializaci kanálu s kontextem nelze obnovit.</span><span class="sxs-lookup"><span data-stu-id="6ccd0-118">Once the channel is initialized with context it cannot be reset.</span></span>  
  
 <span data-ttu-id="6ccd0-119">Následuje seznam výstupních podmínek v tomto režimu:</span><span class="sxs-lookup"><span data-stu-id="6ccd0-119">The following is a list of invariants in this mode:</span></span>  
  
-   <span data-ttu-id="6ccd0-120">Žádný pokus o resetování kontextu pomocí `SetContext` po otevřenou vyvolá kanál <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="6ccd0-120">Any attempt to reset the context using `SetContext` after the channel has been opened throws an <xref:System.InvalidOperationException>.</span></span>  
  
-   <span data-ttu-id="6ccd0-121">Jakýkoli pokus o odeslání kontext pomocí <xref:System.ServiceModel.Channels.ContextMessageProperty> v odchozí zprávy vyvolá <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="6ccd0-121">Any attempt to send context by using the <xref:System.ServiceModel.Channels.ContextMessageProperty> in an outgoing message throws an <xref:System.InvalidOperationException>.</span></span>  
  
-   <span data-ttu-id="6ccd0-122">Pokud je přijata zpráva ze serveru s konkrétní kontext, když kanál již byl inicializován s konkrétní kontext, výsledkem <xref:System.ServiceModel.ProtocolException>.</span><span class="sxs-lookup"><span data-stu-id="6ccd0-122">If a message is received from server with a specific context, when the channel has already been initialized with a specific context, this results in a <xref:System.ServiceModel.ProtocolException>.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6ccd0-123">Je vhodné přijmout počáteční kontext ze serveru pouze v případě, že otevření kanálu bez kontextu explicitně nastaven.</span><span class="sxs-lookup"><span data-stu-id="6ccd0-123">It is appropriate to receive an initial context from the server only if the channel is opened without any context set explicitly.</span></span>  
  
-   <span data-ttu-id="6ccd0-124"><xref:System.ServiceModel.Channels.ContextMessageProperty> Na příchozí zprávy je vždy hodnotu null.</span><span class="sxs-lookup"><span data-stu-id="6ccd0-124">The <xref:System.ServiceModel.Channels.ContextMessageProperty> on incoming message is always null.</span></span>  
  
## <a name="mode-2-application-context-management"></a><span data-ttu-id="6ccd0-125">Režim 2: Správa kontextu aplikací</span><span class="sxs-lookup"><span data-stu-id="6ccd0-125">Mode 2: Application Context Management</span></span>  
 <span data-ttu-id="6ccd0-126">Toto je režim při <xref:System.ServiceModel.Channels.IContextManager.Enabled%2A> je nastaven na `false`.</span><span class="sxs-lookup"><span data-stu-id="6ccd0-126">This is the mode when <xref:System.ServiceModel.Channels.IContextManager.Enabled%2A> is set to `false`.</span></span> <span data-ttu-id="6ccd0-127">V tomto režimu kanálu kontextu nespravuje kontextu.</span><span class="sxs-lookup"><span data-stu-id="6ccd0-127">In this mode the context channel does not manage context.</span></span> <span data-ttu-id="6ccd0-128">Je zodpovědností aplikace načíst, spravovat a použít kontext pomocí <xref:System.ServiceModel.Channels.ContextMessageProperty>.</span><span class="sxs-lookup"><span data-stu-id="6ccd0-128">It is the application's responsibility to retrieve, manage and apply context by using the <xref:System.ServiceModel.Channels.ContextMessageProperty>.</span></span> <span data-ttu-id="6ccd0-129">Jakýkoli pokus o volání `GetContext` nebo `SetContext` vede <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="6ccd0-129">Any attempt to call `GetContext` or `SetContext` results in an <xref:System.InvalidOperationException>.</span></span>  
  
 <span data-ttu-id="6ccd0-130">Bez ohledu na to, ve kterém režimu je zvolen kanálu klienta podporuje <xref:System.ServiceModel.Channels.IRequestChannel>, <xref:System.ServiceModel.Channels.IRequestSessionChannel>, a <xref:System.ServiceModel.Channels.IDuplexSessionChannel> zprávy vzory exchange.</span><span class="sxs-lookup"><span data-stu-id="6ccd0-130">No matter which mode is chosen the client channel factory supports <xref:System.ServiceModel.Channels.IRequestChannel>, <xref:System.ServiceModel.Channels.IRequestSessionChannel>, and <xref:System.ServiceModel.Channels.IDuplexSessionChannel> message exchange patterns.</span></span>  
  
 <span data-ttu-id="6ccd0-131">Ve službě, je zodpovědná za převod kontext dodaný klientem na příchozí zprávy do instance kanálu <xref:System.ServiceModel.Channels.ContextMessageProperty>.</span><span class="sxs-lookup"><span data-stu-id="6ccd0-131">On the service, an instance of the channel is responsible for converting the context supplied by the client on incoming messages to the <xref:System.ServiceModel.Channels.ContextMessageProperty>.</span></span> <span data-ttu-id="6ccd0-132">Vlastnosti zprávy lze přistupovat pomocí aplikační vrstvu nebo jinými kanály další nahoru v zásobníku volání.</span><span class="sxs-lookup"><span data-stu-id="6ccd0-132">The message property can then be accessed by the application layer or other channels further up in the call stack.</span></span> <span data-ttu-id="6ccd0-133">Kanály služby také povolit aplikační vrstvy zadat novou hodnotu kontextu mohly rozšířit zpět do klienta připojením <xref:System.ServiceModel.Channels.ContextMessageProperty> zprávu s odpovědí.</span><span class="sxs-lookup"><span data-stu-id="6ccd0-133">The service channels also allow the application layer to specify a new context value to be propagated back to the client by attaching a <xref:System.ServiceModel.Channels.ContextMessageProperty> to the response message.</span></span> <span data-ttu-id="6ccd0-134">Tato vlastnost je převést hlavičky SOAP nebo souboru cookie HTTP, který obsahuje kontext, který závisí na konfiguraci vazby.</span><span class="sxs-lookup"><span data-stu-id="6ccd0-134">This property is converted to the SOAP header or HTTP cookie that contains the context, which depends on the configuration of the binding.</span></span> <span data-ttu-id="6ccd0-135">Tato služba podporuje kanál naslouchání <xref:System.ServiceModel.Channels.IReplyChannel>, <xref:System.ServiceModel.Channels.IReplySessionChannel>, a <xref:System.ServiceModel.Channels.IReplySessionChannel> zprávy vzory exchange.</span><span class="sxs-lookup"><span data-stu-id="6ccd0-135">The service channel listener supports <xref:System.ServiceModel.Channels.IReplyChannel>, <xref:System.ServiceModel.Channels.IReplySessionChannel>, and <xref:System.ServiceModel.Channels.IReplySessionChannel> message exchange patterns.</span></span>  
  
 <span data-ttu-id="6ccd0-136">Protokol kontextové výměny představuje novou `wsc:Context` hlavičky SOAP pro reprezentaci informace o kontextu, když HTTP soubory cookie nepoužívají rozšíření kontextu.</span><span class="sxs-lookup"><span data-stu-id="6ccd0-136">The context exchange protocol introduces a new `wsc:Context` SOAP header to represent the context information when HTTP cookies are not used to propagate the context.</span></span> <span data-ttu-id="6ccd0-137">Schéma záhlaví kontext umožňuje pro libovolný počet podřízených elementů, každý s klíči řetězce a obsah řetězce.</span><span class="sxs-lookup"><span data-stu-id="6ccd0-137">The context header schema allows for any number of child elements, each with a string key and string content.</span></span> <span data-ttu-id="6ccd0-138">Následuje příklad hlavičky kontextu.</span><span class="sxs-lookup"><span data-stu-id="6ccd0-138">The following is an example of a context header.</span></span>  
  
 `<Context xmlns="http://schemas.microsoft.com/ws/2006/05/context">`  
  
 `<property name="myContext">context-2</property>`  
  
 `</Context>`  
  
 <span data-ttu-id="6ccd0-139">Když v `HttpCookie` režimu, soubory cookie jsou nastavené pomocí `SetCookie` záhlaví.</span><span class="sxs-lookup"><span data-stu-id="6ccd0-139">When in `HttpCookie` mode, cookies are set using the `SetCookie` header.</span></span> <span data-ttu-id="6ccd0-140">Název souboru cookie je `WscContext`.</span><span class="sxs-lookup"><span data-stu-id="6ccd0-140">The cookie name is `WscContext`.</span></span> <span data-ttu-id="6ccd0-141">Hodnota souboru cookie, který je Base64, pomocí kódování `wsc:Context` záhlaví.</span><span class="sxs-lookup"><span data-stu-id="6ccd0-141">The value of the cookie is the Base64 encoding of the `wsc:Context` header.</span></span> <span data-ttu-id="6ccd0-142">Tato hodnota je uzavřena v uvozovkách.</span><span class="sxs-lookup"><span data-stu-id="6ccd0-142">This value is enclosed in quotes.</span></span>  
  
 <span data-ttu-id="6ccd0-143">Hodnota kontextu musí být chráněný proti úpravy při přenosu ze stejného důvodu jsou chráněné WS-Addressing hlavičky – hlavička se používá k určení, kam chcete odeslat žádost o služby.</span><span class="sxs-lookup"><span data-stu-id="6ccd0-143">The value of the context must be protected from modification while in transit for the same reason WS-Addressing headers are protected – the header is used to determine where to dispatch the request to on the service.</span></span> <span data-ttu-id="6ccd0-144">`wsc:Context` Záhlaví je proto potřeba digitálně podepsaný nebo podepsat a zašifrovat na úrovni protokolu SOAP nebo přenos při vazby nabízí možnost ochrany zprávy.</span><span class="sxs-lookup"><span data-stu-id="6ccd0-144">The `wsc:Context` header is therefore required to be digitally signed or signed and encrypted at either the SOAP or transport level when the binding offers message protection capability.</span></span> <span data-ttu-id="6ccd0-145">Pokud soubory cookie protokolu HTTP se používá k šíření kontextu, by měl být chráněn pomocí zabezpečení přenosu.</span><span class="sxs-lookup"><span data-stu-id="6ccd0-145">When HTTP cookies are used to propagate context, they should be protected using transport security.</span></span>  
  
 <span data-ttu-id="6ccd0-146">Koncové body služby, které vyžadují podporu pro protokol kontextové výměny může být explicitní v publikované zásad.</span><span class="sxs-lookup"><span data-stu-id="6ccd0-146">Service endpoints that require support for the context exchange protocol can make it explicit in the published policy.</span></span> <span data-ttu-id="6ccd0-147">Dva nové výrazy zásad byly zavedeny představují požadavek pro klienta pro podporu protokol kontextové výměny na úrovni protokolu SOAP nebo povolení souborů cookie podpory protokolu HTTP.</span><span class="sxs-lookup"><span data-stu-id="6ccd0-147">Two new policy assertions have been introduced to represent the requirement for the client to support the context exchange protocol at the SOAP level or to enable HTTP cookie support.</span></span> <span data-ttu-id="6ccd0-148">Generování těchto kontrolních výrazů do zásady ve službě se řídí hodnota <xref:System.ServiceModel.Channels.ContextBindingElement.ContextExchangeMechanism%2A> vlastnost následujícím způsobem:</span><span class="sxs-lookup"><span data-stu-id="6ccd0-148">Generation of these assertions into the policy on the service is controlled by the value of the <xref:System.ServiceModel.Channels.ContextBindingElement.ContextExchangeMechanism%2A> property as follows:</span></span>  
  
-   <span data-ttu-id="6ccd0-149">Pro <xref:System.ServiceModel.Channels.ContextExchangeMechanism.ContextSoapHeader>, je generována následující kontrolní výraz:</span><span class="sxs-lookup"><span data-stu-id="6ccd0-149">For <xref:System.ServiceModel.Channels.ContextExchangeMechanism.ContextSoapHeader>, the following assertion is generated:</span></span>  
  
    ```xml  
    <IncludeContext   
    xmlns="http://schemas.microsoft.com/ws/2006/05/context"  
    protectionLevel="Sign" />  
    ```  
  
-   <span data-ttu-id="6ccd0-150">Pro <xref:System.ServiceModel.Channels.ContextExchangeMechanism.HttpCookie>, je generována následující kontrolní výraz:</span><span class="sxs-lookup"><span data-stu-id="6ccd0-150">For <xref:System.ServiceModel.Channels.ContextExchangeMechanism.HttpCookie>, the following assertion is generated:</span></span>  
  
    ```xml  
    <HttpUseCookie xmlns="http://schemas.xmlsoap.org/soap/http"/>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="6ccd0-151">Viz také</span><span class="sxs-lookup"><span data-stu-id="6ccd0-151">See Also</span></span>  
 [<span data-ttu-id="6ccd0-152">Průvodce interoperabilitou protokolů webových služeb</span><span class="sxs-lookup"><span data-stu-id="6ccd0-152">Web Services Protocols Interoperability Guide</span></span>](../../../../docs/framework/wcf/feature-details/web-services-protocols-interoperability-guide.md)
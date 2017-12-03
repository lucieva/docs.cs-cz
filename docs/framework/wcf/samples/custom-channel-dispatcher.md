---
title: "Dispečer vlastního kanálu"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 813acf03-9661-4d57-a3c7-eeab497321c6
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5814850b3d5a25f5f3c118e732930168f9489d9d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="custom-channel-dispatcher"></a><span data-ttu-id="6a3cf-102">Dispečer vlastního kanálu</span><span class="sxs-lookup"><span data-stu-id="6a3cf-102">Custom Channel Dispatcher</span></span>
<span data-ttu-id="6a3cf-103">Tato ukázka ukazuje, jak vytvořit kanál zásobníku vlastní způsobem implementací <xref:System.ServiceModel.ServiceHostBase> přímo a jak vytvořit vlastní kanál dispečera v prostředí hostitele webu.</span><span class="sxs-lookup"><span data-stu-id="6a3cf-103">This sample demonstrates how to build the channel stack in a custom way by implementing <xref:System.ServiceModel.ServiceHostBase> directly and how to create a custom channel dispatcher in Web host environment.</span></span> <span data-ttu-id="6a3cf-104">Dispečera kanál komunikuje s <xref:System.ServiceModel.Channels.IChannelListener> tak, aby přijímal zprávy kanály a načte z zásobníku kanálu.</span><span class="sxs-lookup"><span data-stu-id="6a3cf-104">The channel dispatcher interacts with <xref:System.ServiceModel.Channels.IChannelListener> to accept channels and retrieves messages from the channel stack.</span></span> <span data-ttu-id="6a3cf-105">Tato ukázka také poskytuje základní ukázka, jak vytvořit kanál zásobníku v prostředí webové hostitele pomocí <xref:System.ServiceModel.Activation.VirtualPathExtension>.</span><span class="sxs-lookup"><span data-stu-id="6a3cf-105">This sample also provides a basic sample to show how to build a channel stack in a Web host environment by using <xref:System.ServiceModel.Activation.VirtualPathExtension>.</span></span>  
  
## <a name="custom-servicehostbase"></a><span data-ttu-id="6a3cf-106">Vlastní ServiceHostBase</span><span class="sxs-lookup"><span data-stu-id="6a3cf-106">Custom ServiceHostBase</span></span>  
 <span data-ttu-id="6a3cf-107">Tato ukázka implementuje základní typ <xref:System.ServiceModel.ServiceHostBase> místo <xref:System.ServiceModel.ServiceHost> abychom ukázali, jak nahradit [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] zásobník implementace vlastní zprávu zpracování vrstvu nad zásobníku kanálu.</span><span class="sxs-lookup"><span data-stu-id="6a3cf-107">This sample implements the base type <xref:System.ServiceModel.ServiceHostBase> instead of <xref:System.ServiceModel.ServiceHost> to demonstrate how to replace the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] stack implementation with a custom message handling layer on top of the channel stack.</span></span> <span data-ttu-id="6a3cf-108">Potlačení virtuální metody <xref:System.ServiceModel.ServiceHostBase.InitializeRuntime%2A> k vytvoření naslouchacího procesu kanálu a dispečera kanálu.</span><span class="sxs-lookup"><span data-stu-id="6a3cf-108">You override the virtual method <xref:System.ServiceModel.ServiceHostBase.InitializeRuntime%2A> to build channel listeners and the channel dispatcher.</span></span>  
  
 <span data-ttu-id="6a3cf-109">K implementaci hostované webové služby, získat rozšíření služby <xref:System.ServiceModel.Activation.VirtualPathExtension> z <xref:System.ServiceModel.ServiceHostBase.Extensions%2A> kolekce a přidejte ho do <xref:System.ServiceModel.Channels.BindingParameterCollection> tak, aby přenosové vrstvy umí nakonfigurovat naslouchací proces kanálu nástroje na základě hostitelských nastaveních prostředí, který je Internetové informační služby (IIS) nebo nastavení služby Aktivace procesů systému Windows (WAS).</span><span class="sxs-lookup"><span data-stu-id="6a3cf-109">To implement a Web-hosted service, get the service extension <xref:System.ServiceModel.Activation.VirtualPathExtension> from the <xref:System.ServiceModel.ServiceHostBase.Extensions%2A> collection and add it to the <xref:System.ServiceModel.Channels.BindingParameterCollection> so that the transport layer knows how to configure the channel listener based on the hosting environment settings, that is, the Internet Information Services (IIS)/Windows Process Activation Service (WAS) settings.</span></span>  
  
## <a name="custom-channel-dispatcher"></a><span data-ttu-id="6a3cf-110">Dispečer vlastního kanálu</span><span class="sxs-lookup"><span data-stu-id="6a3cf-110">Custom Channel Dispatcher</span></span>  
 <span data-ttu-id="6a3cf-111">Dispečer vlastního kanálu rozšiřuje typ <xref:System.ServiceModel.Dispatcher.ChannelDispatcherBase>.</span><span class="sxs-lookup"><span data-stu-id="6a3cf-111">The custom channel dispatcher extends the type <xref:System.ServiceModel.Dispatcher.ChannelDispatcherBase>.</span></span> <span data-ttu-id="6a3cf-112">Tento typ implementuje programovací logiku vrstvy kanálu.</span><span class="sxs-lookup"><span data-stu-id="6a3cf-112">This type implements the channel-layer programming logic.</span></span> <span data-ttu-id="6a3cf-113">V této ukázce pouze <xref:System.ServiceModel.Channels.IReplyChannel> je podporována pro vzorce výměny zpráv požadavku a odpovědi, ale dispečer vlastního kanálu lze snadno rozšířit na jiné typy kanálu.</span><span class="sxs-lookup"><span data-stu-id="6a3cf-113">In this sample, only <xref:System.ServiceModel.Channels.IReplyChannel> is supported for request-reply message exchange pattern, but the custom channel dispatcher can be easily extended to other channel types.</span></span>  
  
 <span data-ttu-id="6a3cf-114">Dispečera prvním otevření naslouchací proces kanálu nástroje a potom přijímá kanál odpověď typu singleton.</span><span class="sxs-lookup"><span data-stu-id="6a3cf-114">The dispatcher first opens the channel listener and then accepts the singleton reply channel.</span></span> <span data-ttu-id="6a3cf-115">S kanálem začne odesílat zprávy (počet požadavků) v nekonečné smyčce.</span><span class="sxs-lookup"><span data-stu-id="6a3cf-115">With the channel, it starts to send messages (requests) in an infinite loop.</span></span> <span data-ttu-id="6a3cf-116">Pro každý požadavek vytvoří zprávu odpovědi a odešle ho zpátky do klienta.</span><span class="sxs-lookup"><span data-stu-id="6a3cf-116">For each request, it creates a reply message and sends it back to the client.</span></span>  
  
## <a name="creating-a-response-message"></a><span data-ttu-id="6a3cf-117">Vytváření zprávu odpovědi</span><span class="sxs-lookup"><span data-stu-id="6a3cf-117">Creating a Response Message</span></span>  
 <span data-ttu-id="6a3cf-118">Zpracování zpráv je implementován v typu `MyServiceManager`.</span><span class="sxs-lookup"><span data-stu-id="6a3cf-118">The message processing is implemented in the type `MyServiceManager`.</span></span> <span data-ttu-id="6a3cf-119">V `HandleRequest` metody `Action` záhlaví zprávy nejdřív zkontroluje se zda žádost je podporováno.</span><span class="sxs-lookup"><span data-stu-id="6a3cf-119">In the `HandleRequest` method, the `Action` header of the message is first checked to see whether the request is supported.</span></span> <span data-ttu-id="6a3cf-120">Předdefinované akce SOAP "http://tempuri.org/HelloWorld/Hello" je definována k poskytnutí filtrování zprávy.</span><span class="sxs-lookup"><span data-stu-id="6a3cf-120">A predefined SOAP action "http://tempuri.org/HelloWorld/Hello" is defined to provide message filtering.</span></span> <span data-ttu-id="6a3cf-121">Toto je podobný koncept kontraktu služby ve [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementace <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="6a3cf-121">This is similar to the service contract concept in the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementation of <xref:System.ServiceModel.ServiceHost>.</span></span>  
  
 <span data-ttu-id="6a3cf-122">Pro správnou velikost akce SOAP ukázku načte data pro požadovaný zprávu a vygeneruje odpovídající odpověď na žádost o podobná co je vidět v <xref:System.ServiceModel.ServiceHost> případu.</span><span class="sxs-lookup"><span data-stu-id="6a3cf-122">For the correct SOAP action case, the sample retrieves the requested message data and generates a corresponding response to the request similar to what is seen in the <xref:System.ServiceModel.ServiceHost> case.</span></span>  
  
 <span data-ttu-id="6a3cf-123">Speciálně zpracovává operaci HTTP GET, ve kterém můžete vyhledat službu z prohlížeče, zobrazí se, že zdařilo vrácením vlastní zprávu ve formátu HTML, v tomto případě.</span><span class="sxs-lookup"><span data-stu-id="6a3cf-123">You specially handled the HTTP-GET verb by returning a custom HTML message, in this, case so that you can browse the service from a browser to see that it is compiled correctly.</span></span> <span data-ttu-id="6a3cf-124">Pokud akce SOAP neodpovídá, Odeslat chybu zpět zpráva indikující, že tento požadavek není podporován.</span><span class="sxs-lookup"><span data-stu-id="6a3cf-124">If the SOAP action does not match, send a fault message back to indicate that the request is not supported.</span></span>  
  
 <span data-ttu-id="6a3cf-125">Klient Tato ukázka je z něj normální [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] klienta, který nepředpokládá nic ze služby.</span><span class="sxs-lookup"><span data-stu-id="6a3cf-125">The client of this sample is a normal [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client that does not assume anything from the service.</span></span> <span data-ttu-id="6a3cf-126">Ano, službu speciálně navržené tak, aby odpovídaly, co můžete získat z něj normální [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] <xref:System.ServiceModel.ServiceHost> implementace.</span><span class="sxs-lookup"><span data-stu-id="6a3cf-126">So, the service is specially designed to match what you get from a normal [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<xref:System.ServiceModel.ServiceHost> implementation.</span></span> <span data-ttu-id="6a3cf-127">V důsledku toho je v klientovi požadováno pouze kontraktu služby.</span><span class="sxs-lookup"><span data-stu-id="6a3cf-127">As a result, only a service contract is required on the client.</span></span>  
  
## <a name="using-the-sample"></a><span data-ttu-id="6a3cf-128">Pomocí vzorku</span><span class="sxs-lookup"><span data-stu-id="6a3cf-128">Using the sample</span></span>  
 <span data-ttu-id="6a3cf-129">Spuštění klienta aplikace přímo vytvoří následující výstup.</span><span class="sxs-lookup"><span data-stu-id="6a3cf-129">Running the client application directly produces the following output.</span></span>  
  
```Output  
Client is talking to a request/reply WCF service.   
Type what you want to say to the server: Howdy  
Server replied: You said: Howdy. Message id: 1  
Server replied: You said: Howdy. Message id: 2  
Server replied: You said: Howdy. Message id: 3  
Server replied: You said: Howdy. Message id: 4  
Server replied: You said: Howdy. Message id: 5  
```  
  
 <span data-ttu-id="6a3cf-130">Můžete také vyhledat službu z prohlížeče tak, aby na serveru získá zpracovat zprávu HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="6a3cf-130">You can also browse the service from a browser so that an HTTP-GET message gets processed on the server.</span></span> <span data-ttu-id="6a3cf-131">Toto je dobře formátovaný text HTML získá zpět.</span><span class="sxs-lookup"><span data-stu-id="6a3cf-131">This gets you well-formatted HTML text back.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6a3cf-132">Ukázky může být již nainstalována na váš počítač.</span><span class="sxs-lookup"><span data-stu-id="6a3cf-132">The samples may already be installed on your machine.</span></span> <span data-ttu-id="6a3cf-133">Před pokračováním zkontrolovat na následující adresář (výchozí).</span><span class="sxs-lookup"><span data-stu-id="6a3cf-133">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="6a3cf-134">Pokud tento adresář neexistuje, přejděte na [Windows Communication Foundation (WCF) a ukázky Windows Workflow Foundation (WF) pro rozhraní .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) ke stažení všechny [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] a [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ukázky.</span><span class="sxs-lookup"><span data-stu-id="6a3cf-134">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6a3cf-135">Tato ukázka se nachází v následujícím adresáři.</span><span class="sxs-lookup"><span data-stu-id="6a3cf-135">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\CustomChannelDispatcher`
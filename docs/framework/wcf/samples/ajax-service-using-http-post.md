---
title: "Služba AJAX, která používá HTTP POST"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1ac80f20-ac1c-4ed1-9850-7e49569ff44e
caps.latest.revision: "28"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 004bb41ad1662ddd6518c25acc1cac36dda3339c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="ajax-service-using-http-post"></a><span data-ttu-id="ac6af-102">Služba AJAX, která používá HTTP POST</span><span class="sxs-lookup"><span data-stu-id="ac6af-102">AJAX Service Using HTTP POST</span></span>
<span data-ttu-id="ac6af-103">Tento příklad ukazuje, jak používat [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] vytvořit [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] asynchronní JavaScript a XML (AJAX) službu, která používá HTTP POST.</span><span class="sxs-lookup"><span data-stu-id="ac6af-103">This sample demonstrates how to use [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] to create an [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Asynchronous JavaScript and XML (AJAX) service that uses HTTP POST.</span></span> <span data-ttu-id="ac6af-104">Služby AJAX je ten, který lze přistupovat pomocí základního kódu jazyka JavaScript z webového prohlížeče klienta.</span><span class="sxs-lookup"><span data-stu-id="ac6af-104">An AJAX service is one that you can access by using basic JavaScript code from a Web browser client.</span></span> <span data-ttu-id="ac6af-105">Tato ukázka je založena na [základní služba AJAX](../../../../docs/framework/wcf/samples/basic-ajax-service.md) ukázku; jediným rozdílem mezi dvěma vzorky je použití HTTP POST namísto metody GET protokolu HTTP.</span><span class="sxs-lookup"><span data-stu-id="ac6af-105">This sample builds on the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) sample; the only difference between the two samples is the use of HTTP POST instead of HTTP GET.</span></span>  
  
 <span data-ttu-id="ac6af-106">Podpora jazyka AJAX v [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] je optimalizovaný pro použití s pomocí prvku ASP.NET AJAX `ScriptManager` ovládací prvek.</span><span class="sxs-lookup"><span data-stu-id="ac6af-106">AJAX support in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] is optimized for use with ASP.NET AJAX through the `ScriptManager` control.</span></span> <span data-ttu-id="ac6af-107">Příklad použití [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] pomocí prvku ASP.NET AJAX, najdete v článku [Ajax ukázky](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).</span><span class="sxs-lookup"><span data-stu-id="ac6af-107">For an example of using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] with ASP.NET AJAX, see the [Ajax Samples](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ac6af-108">V postupu a sestavení pokynech k instalaci této ukázce jsou umístěné na konci tohoto tématu.</span><span class="sxs-lookup"><span data-stu-id="ac6af-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="ac6af-109">Služba v následující ukázce je [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] služby s žádné kódu pro konkrétní jazyk AJAX.</span><span class="sxs-lookup"><span data-stu-id="ac6af-109">The service in the following sample is a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service with no AJAX-specific code.</span></span>  
  
 <span data-ttu-id="ac6af-110">Pokud <xref:System.ServiceModel.Web.WebInvokeAttribute> atribut se používá u určité operace, nebo <xref:System.ServiceModel.Web.WebGetAttribute> atribut není použit, bude použita výchozí akce HTTP (dále jen "příspěvek").</span><span class="sxs-lookup"><span data-stu-id="ac6af-110">If the <xref:System.ServiceModel.Web.WebInvokeAttribute> attribute is applied on an operation, or the <xref:System.ServiceModel.Web.WebGetAttribute> attribute is not applied, the default HTTP verb ("POST") is used.</span></span> <span data-ttu-id="ac6af-111">Požadavky POST jsou těžší vytvořit než požadavky GET, ale nejsou v mezipaměti; pomocí požadavků POST pro všechny operace, kde není vhodná ukládání do mezipaměti.</span><span class="sxs-lookup"><span data-stu-id="ac6af-111">POST requests are harder to construct than GET requests, but they are not cached; use POST requests for all operations where caching is not appropriate.</span></span>  
  
```  
[ServiceContract(Namespace = "PostAjaxService")]  
    public interface ICalculator  
    {        [WebInvoke]  
        double Add(double n1, double n2);  
        //Other operations omitted…  
    }  
```  
  
 <span data-ttu-id="ac6af-112">Vytvoření AJAX koncový bod služby pomocí <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, jen jako ukázka základní služba AJAX.</span><span class="sxs-lookup"><span data-stu-id="ac6af-112">Create an AJAX endpoint on the service by using the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, just as in the Basic AJAX Service sample.</span></span>  
  
 <span data-ttu-id="ac6af-113">Na rozdíl od požadavky GET nemohou vyvolat POST služby z prohlížeče.</span><span class="sxs-lookup"><span data-stu-id="ac6af-113">Unlike GET requests, you cannot invoke POST services from the browser.</span></span> <span data-ttu-id="ac6af-114">Například přejdete na http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200 dojde k chybě, protože služba POST očekává `n1` a `n2` parametry pro odeslání v textu zprávy – ve formátu JSON – a není v adrese URL.</span><span class="sxs-lookup"><span data-stu-id="ac6af-114">For example, navigating to http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200 results in an error, because the POST service expects the `n1` and `n2` parameters to be sent in the message body—in the JSON format—and not in the URL.</span></span>  
  
 <span data-ttu-id="ac6af-115">Klient PostAjaxClientPage.aspx webová stránka obsahuje kód ASP.NET k vyvolání služby vždy, když uživatel klikne na jednu operaci tlačítek na stránce.</span><span class="sxs-lookup"><span data-stu-id="ac6af-115">The client Web page PostAjaxClientPage.aspx contains ASP.NET code to invoke the service whenever the user clicks one of the operation buttons on the page.</span></span> <span data-ttu-id="ac6af-116">Služba odpovídá stejným způsobem jako v [základní služba AJAX](../../../../docs/framework/wcf/samples/basic-ajax-service.md) ukázku s požadavek GET.</span><span class="sxs-lookup"><span data-stu-id="ac6af-116">The service responds in the same way as in the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) sample, with the GET request.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ac6af-117">Ukázky může být již nainstalován ve vašem počítači.</span><span class="sxs-lookup"><span data-stu-id="ac6af-117">The samples may already be installed on your computer.</span></span> <span data-ttu-id="ac6af-118">Před pokračováním zkontrolovat na následující adresář (výchozí).</span><span class="sxs-lookup"><span data-stu-id="ac6af-118">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ac6af-119">Pokud tento adresář neexistuje, přejděte na [Windows Communication Foundation (WCF) a ukázky Windows Workflow Foundation (WF) pro rozhraní .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) ke stažení všechny [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] a [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ukázky.</span><span class="sxs-lookup"><span data-stu-id="ac6af-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ac6af-120">Tato ukázka se nachází v následujícím adresáři.</span><span class="sxs-lookup"><span data-stu-id="ac6af-120">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\PostAjaxService`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="ac6af-121">Pokud chcete nastavit, sestavit a spustit ukázku</span><span class="sxs-lookup"><span data-stu-id="ac6af-121">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="ac6af-122">Ujistěte se, že provádíte pokynů pro instalaci [jednorázové postup nastavení pro ukázky Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ac6af-122">Ensure that you perform the setup instructions [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="ac6af-123">Sestavte řešení PostAjaxService.sln, jak je popsáno v [vytváření ukázky Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ac6af-123">Build the solution PostAjaxService.sln as described in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="ac6af-124">Přejděte na http://localhost/ServiceModelSamples/PostAjaxClientPage.aspx (neotevírejte PostAjaxClientPage.aspx v prohlížeči z adresáře projektu).</span><span class="sxs-lookup"><span data-stu-id="ac6af-124">Navigate to http://localhost/ServiceModelSamples/PostAjaxClientPage.aspx (do not open PostAjaxClientPage.aspx in the browser from the project directory).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac6af-125">Viz také</span><span class="sxs-lookup"><span data-stu-id="ac6af-125">See Also</span></span>
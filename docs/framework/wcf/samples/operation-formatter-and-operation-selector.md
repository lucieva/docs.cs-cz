---
title: "Formátovací modul a selektor operace"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1c27e9fe-11f8-4377-8140-828207b98a0e
caps.latest.revision: "19"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c0e2dbd255a1fbadbd5dd4cd7e676b75e659fe2a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="operation-formatter-and-operation-selector"></a><span data-ttu-id="f074f-102">Formátovací modul a selektor operace</span><span class="sxs-lookup"><span data-stu-id="f074f-102">Operation Formatter and Operation Selector</span></span>
<span data-ttu-id="f074f-103">Tento příklad ukazuje, jak [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] body rozšiřitelnosti lze povolit data zpráv do jiného formátu z co [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] očekává.</span><span class="sxs-lookup"><span data-stu-id="f074f-103">This sample demonstrates how [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] extensibility points can be used to allow message data in a different format from what [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] expects.</span></span> <span data-ttu-id="f074f-104">Ve výchozím nastavení [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] formátování očekávat parametry metody, které mají být zahrnuty v části `soap:body` elementu.</span><span class="sxs-lookup"><span data-stu-id="f074f-104">By default, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] formatters expect method parameters to be included under the `soap:body` element.</span></span> <span data-ttu-id="f074f-105">Ukázka ukazuje, jak implementovat vlastní operaci formátování, které analyzuje data parametr z řetězce dotazu HTTP GET místo a vyvolá metody pomocí tato data.</span><span class="sxs-lookup"><span data-stu-id="f074f-105">The sample shows how to implement a custom operation formatter that parses parameter data from an HTTP GET query string instead and invokes methods using that data.</span></span>  
  
 <span data-ttu-id="f074f-106">Ukázka je založena na [Začínáme](../../../../docs/framework/wcf/samples/getting-started-sample.md), který implementuje `ICalculator` kontrakt služby.</span><span class="sxs-lookup"><span data-stu-id="f074f-106">The sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), which implements the `ICalculator` service contract.</span></span> <span data-ttu-id="f074f-107">Ho ukazuje, jak přidat, odečíst násobkem a dělení zprávy můžete změnit tak, aby požadavky klienta na server pomocí metody GET protokolu HTTP a HTTP POST s POX zprávy pro klienta a serveru odpovědi.</span><span class="sxs-lookup"><span data-stu-id="f074f-107">It shows how Add, Subtract, Multiply, and Divide messages can be changed to use HTTP GET for client-to-server requests and HTTP POST with POX messages for server-to-client responses.</span></span>  
  
 <span data-ttu-id="f074f-108">Uděláte to tak, ukázka poskytuje následující:</span><span class="sxs-lookup"><span data-stu-id="f074f-108">To do so, the sample provides the following:</span></span>  
  
-   <span data-ttu-id="f074f-109">`QueryStringFormatter`, který implementuje <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> a <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter> pro klienta a serveru, v uvedeném pořadí a zpracovává data v řetězci dotazu.</span><span class="sxs-lookup"><span data-stu-id="f074f-109">`QueryStringFormatter`, which implements <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> and <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter> for the client and server, respectively, and processes the data in the query string.</span></span>  
  
-   <span data-ttu-id="f074f-110">`UriOperationSelector`, který implementuje <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> na serveru k provedení operace odesílání na základě názvu operace v požadavek GET.</span><span class="sxs-lookup"><span data-stu-id="f074f-110">`UriOperationSelector`, which implements <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> on the server to perform operation dispatch based on the operation name in the GET request.</span></span>  
  
-   <span data-ttu-id="f074f-111">`EnableHttpGetRequestsBehavior`koncový bod chování (a odpovídající konfigurace), k modulu runtime přidává selektor potřebné operace.</span><span class="sxs-lookup"><span data-stu-id="f074f-111">`EnableHttpGetRequestsBehavior` endpoint behavior (and corresponding configuration), which adds the necessary operation selector to the runtime.</span></span>  
  
-   <span data-ttu-id="f074f-112">Ukazuje, jak nové formátování operaci vložení do modulu runtime.</span><span class="sxs-lookup"><span data-stu-id="f074f-112">Shows how to insert a new operation formatter into the runtime.</span></span>  
  
-   <span data-ttu-id="f074f-113">V této ukázce klienta a služby jsou konzolové aplikace (.exe).</span><span class="sxs-lookup"><span data-stu-id="f074f-113">In this sample, both the client and the service are console applications (.exe).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f074f-114">V postupu a sestavení pokynech k instalaci této ukázce jsou umístěné na konci tohoto tématu.</span><span class="sxs-lookup"><span data-stu-id="f074f-114">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
## <a name="key-concepts"></a><span data-ttu-id="f074f-115">Klíčové koncepty</span><span class="sxs-lookup"><span data-stu-id="f074f-115">Key Concepts</span></span>  
 <span data-ttu-id="f074f-116">`QueryStringFormatter`-Formátovací modul je součástí v [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] který zodpovídá za převodu zprávy na pole objektů parametr a pole objektů parametr do zprávy.</span><span class="sxs-lookup"><span data-stu-id="f074f-116">`QueryStringFormatter` - The operation formatter is the component in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] that is responsible for converting a message into an array of parameter objects and an array of parameter objects into a message.</span></span> <span data-ttu-id="f074f-117">To se provádí na straně klienta pomocí <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> rozhraní a na serveru s <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter> rozhraní.</span><span class="sxs-lookup"><span data-stu-id="f074f-117">This is done on the client using the <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> interface and on the server with the <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter> interface.</span></span> <span data-ttu-id="f074f-118">Povolit uživatelům získat zprávy požadavku a odpovědi z těchto rozhraní `Serialize` a `Deserialize` metody.</span><span class="sxs-lookup"><span data-stu-id="f074f-118">These interfaces enable users to get the request and response messages from the `Serialize` and `Deserialize` methods.</span></span>  
  
 <span data-ttu-id="f074f-119">V této ukázce `QueryStringFormatter` implementuje obě tato rozhraní a je implementována na klientovi a serveru.</span><span class="sxs-lookup"><span data-stu-id="f074f-119">In this sample, `QueryStringFormatter` implements both of these interfaces and is implemented on the client and server.</span></span>  
  
 <span data-ttu-id="f074f-120">Žádost:</span><span class="sxs-lookup"><span data-stu-id="f074f-120">Request:</span></span>  
  
-   <span data-ttu-id="f074f-121">Ukázce se používá <xref:System.ComponentModel.TypeConverter> – třída parametru data ve zprávě požadavku převést do a z řetězce.</span><span class="sxs-lookup"><span data-stu-id="f074f-121">The sample uses the <xref:System.ComponentModel.TypeConverter> class to convert parameter data in the request message to and from strings.</span></span> <span data-ttu-id="f074f-122">Pokud <xref:System.ComponentModel.TypeConverter> není k dispozici pro konkrétní typ, vrátí formátování ukázka výjimku.</span><span class="sxs-lookup"><span data-stu-id="f074f-122">If a <xref:System.ComponentModel.TypeConverter> is not available for a specific type, the sample formatter throws an exception.</span></span>  
  
-   <span data-ttu-id="f074f-123">V `IClientMessageFormatter.SerializeRequest` metody na straně klienta, formátování vytvoří identifikátor URI s příslušnou adresu a připojí název operace jako příponu.</span><span class="sxs-lookup"><span data-stu-id="f074f-123">In the `IClientMessageFormatter.SerializeRequest` method on the client, the formatter creates a URI with the appropriate To address and appends the operation name as a suffix.</span></span> <span data-ttu-id="f074f-124">Tento název se používá k odeslání do příslušné operaci na serveru.</span><span class="sxs-lookup"><span data-stu-id="f074f-124">This name is used to dispatch to the appropriate operation on the server.</span></span> <span data-ttu-id="f074f-125">Potom provede pole objektů parametr a serializuje data parametru řetězce dotazu identifikátoru URI pomocí názvy parametrů a hodnot pomocí převedeny <xref:System.ComponentModel.TypeConverter> třídy.</span><span class="sxs-lookup"><span data-stu-id="f074f-125">It then takes the array of parameter objects and serializes the parameter data to the URI query string using parameter names and the values converted by the <xref:System.ComponentModel.TypeConverter> class.</span></span> <span data-ttu-id="f074f-126"><xref:System.ServiceModel.Channels.MessageHeaders.To%2A> a <xref:System.ServiceModel.Channels.MessageProperties.Via%2A> vlastností pak nastavení tento identifikátor URI.</span><span class="sxs-lookup"><span data-stu-id="f074f-126">The <xref:System.ServiceModel.Channels.MessageHeaders.To%2A> and <xref:System.ServiceModel.Channels.MessageProperties.Via%2A> properties are then set to this URI.</span></span> <span data-ttu-id="f074f-127"><xref:System.ServiceModel.Channels.MessageProperties>je přístupné přes <xref:System.ServiceModel.Channels.Message.Properties%2A> vlastnost.</span><span class="sxs-lookup"><span data-stu-id="f074f-127"><xref:System.ServiceModel.Channels.MessageProperties> is accessed through the <xref:System.ServiceModel.Channels.Message.Properties%2A> property.</span></span>  
  
-   <span data-ttu-id="f074f-128">V `IDispatchMessageFormatter.DeserializeRequest` načte formátovací modul metoda na serveru, `Via` URI ve vlastnostech příchozí zpráva požadavku.</span><span class="sxs-lookup"><span data-stu-id="f074f-128">In the `IDispatchMessageFormatter.DeserializeRequest` method on the server, the formatter retrieves the `Via` URI in the incoming request message properties.</span></span> <span data-ttu-id="f074f-129">Ho analyzuje dvojice název hodnota v řetězci dotazu identifikátoru URI do názvy parametrů a hodnoty a využije k vyplnění pole parametry předané do metodu názvy parametrů a hodnoty.</span><span class="sxs-lookup"><span data-stu-id="f074f-129">It parses the name-value pairs in the URI query string into parameter names and values and uses the parameter names and values to populate the array of parameters passed into the method.</span></span> <span data-ttu-id="f074f-130">Všimněte si, že operace odesílání již došlo, proto je přípona názvu operaci je ignorován v této metodě.</span><span class="sxs-lookup"><span data-stu-id="f074f-130">Note that operation dispatch has already occurred, so the operation name suffix is ignored in this method.</span></span>  
  
 <span data-ttu-id="f074f-131">Odpověď:</span><span class="sxs-lookup"><span data-stu-id="f074f-131">Response:</span></span>  
  
-   <span data-ttu-id="f074f-132">V této ukázce metody GET protokolu HTTP se používá pouze pro požadavek.</span><span class="sxs-lookup"><span data-stu-id="f074f-132">In this sample, HTTP GET is used only for the request.</span></span> <span data-ttu-id="f074f-133">Formátovací modul deleguje odesílání odpovědi na původní formátovací modul, který by byl použit ke generování zprávu XML.</span><span class="sxs-lookup"><span data-stu-id="f074f-133">The formatter delegates the sending of the response to the original formatter that would have been used to generate an XML message.</span></span> <span data-ttu-id="f074f-134">Jedním z cílů tohoto příkladu je zobrazit, jak se dají implementovat delegování formátování.</span><span class="sxs-lookup"><span data-stu-id="f074f-134">One of the goals of this sample is to show how such a delegating formatter can be implemented.</span></span>  
  
### <a name="uripathsuffixoperationselector-class"></a><span data-ttu-id="f074f-135">UriPathSuffixOperationSelector – třída</span><span class="sxs-lookup"><span data-stu-id="f074f-135">UriPathSuffixOperationSelector Class</span></span>  
 <span data-ttu-id="f074f-136"><xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> Rozhraní umožňuje uživatelům implementovat vlastní logiku, pro kterou operaci by měl určitou zprávu odeslat.</span><span class="sxs-lookup"><span data-stu-id="f074f-136">The <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> interface enables users to implement their own logic for which operation a particular message should be dispatched.</span></span>  
  
 <span data-ttu-id="f074f-137">V této ukázce `UriPathSuffixOperationSelector` na serveru a vyberte příslušnou operaci, protože název operace je obsažena v identifikátoru URI HTTP GET, nikoli hlavičku akce ve zprávě, musí být implementována.</span><span class="sxs-lookup"><span data-stu-id="f074f-137">In this sample, `UriPathSuffixOperationSelector` must be implemented on the server to select the appropriate operation because the operation name is included in the HTTP GET URI rather than an action header in the message.</span></span> <span data-ttu-id="f074f-138">Ukázka je nastavit a Povolit jenom velká a malá písmena operaci názvy.</span><span class="sxs-lookup"><span data-stu-id="f074f-138">The sample is set up to allow only case-insensitive operation names.</span></span>  
  
 <span data-ttu-id="f074f-139">`SelectOperation` Metoda přijímá příchozí zprávy a vyhledá `Via` URI v vlastností.</span><span class="sxs-lookup"><span data-stu-id="f074f-139">The `SelectOperation` method takes the incoming message and looks up the `Via` URI in its message properties.</span></span> <span data-ttu-id="f074f-140">Extrahuje příponu názvu operace z identifikátoru URI, vyhledává interní tabulku se získat název operace, který by měl být odeslaných zprávu a vrátí název této operace.</span><span class="sxs-lookup"><span data-stu-id="f074f-140">It extracts the operation name suffix from the URI, looks up an internal table to get the operation name that the message should be dispatched to, and returns that operation name.</span></span>  
  
### <a name="enablehttpgetrequestsbehavior-class"></a><span data-ttu-id="f074f-141">EnableHttpGetRequestsBehavior – třída</span><span class="sxs-lookup"><span data-stu-id="f074f-141">EnableHttpGetRequestsBehavior Class</span></span>  
 <span data-ttu-id="f074f-142">`UriPathSuffixOperationSelector` Součást se dá nastavit prostřednictvím kódu programu, nebo prostřednictvím chování koncového bodu.</span><span class="sxs-lookup"><span data-stu-id="f074f-142">The `UriPathSuffixOperationSelector` component can be set up programmatically or through an endpoint behavior.</span></span> <span data-ttu-id="f074f-143">Ukázka implementuje `EnableHttpGetRequestsBehavior` chování, který je uveden v konfiguračním souboru aplikace služby.</span><span class="sxs-lookup"><span data-stu-id="f074f-143">The sample implements the `EnableHttpGetRequestsBehavior` behavior, which is specified in service’s application configuration file.</span></span>  
  
 <span data-ttu-id="f074f-144">Na serveru:</span><span class="sxs-lookup"><span data-stu-id="f074f-144">On the server:</span></span>  
  
 <span data-ttu-id="f074f-145"><xref:System.ServiceModel.Dispatcher.DispatchRuntime.OperationSelector%2A> Je nastaven na <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> implementace.</span><span class="sxs-lookup"><span data-stu-id="f074f-145">The <xref:System.ServiceModel.Dispatcher.DispatchRuntime.OperationSelector%2A> is set to the <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> implementation.</span></span>  
  
 <span data-ttu-id="f074f-146">Ve výchozím nastavení [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] používá filtr adres přesnou shodu.</span><span class="sxs-lookup"><span data-stu-id="f074f-146">By default, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses an exact-match address filter.</span></span> <span data-ttu-id="f074f-147">Identifikátor URI na příchozí zpráva obsahuje příponu názvu operaci následuje řetězec dotazu, který obsahuje parametr data, takže chování koncového bodu také změní filtr adres jako předponu odpovídají filtru.</span><span class="sxs-lookup"><span data-stu-id="f074f-147">The URI on the incoming message contains an operation name suffix followed by a query string that contains parameter data, so the endpoint behavior also changes the address filter to be a prefix match filter.</span></span> <span data-ttu-id="f074f-148">Použije [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] <xref:System.ServiceModel.Dispatcher.PrefixEndpointAddressMessageFilter> pro tento účel.</span><span class="sxs-lookup"><span data-stu-id="f074f-148">It uses the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<xref:System.ServiceModel.Dispatcher.PrefixEndpointAddressMessageFilter> for this purpose.</span></span>  
  
### <a name="installing-operation-formatters"></a><span data-ttu-id="f074f-149">Instalace operace formátování</span><span class="sxs-lookup"><span data-stu-id="f074f-149">Installing operation formatters</span></span>  
 <span data-ttu-id="f074f-150">Operace chování, které určují formátovací moduly jsou jedinečné.</span><span class="sxs-lookup"><span data-stu-id="f074f-150">Operation behaviors that specify formatters are unique.</span></span> <span data-ttu-id="f074f-151">Jeden takové chování je vždy implementováno ve výchozím nastavení pro každou operaci vytvoření formátování potřebné operace.</span><span class="sxs-lookup"><span data-stu-id="f074f-151">One such behavior is always implemented by default for every operation to create the necessary operation formatter.</span></span> <span data-ttu-id="f074f-152">Ale tyto chování vypadat podobně jako jakékoli jiné operace chování; nejsou osobní jiných atributem.</span><span class="sxs-lookup"><span data-stu-id="f074f-152">However, these behaviors look like just another operation behavior; they are not identifiable by any other attribute.</span></span> <span data-ttu-id="f074f-153">K instalaci nahrazení chování, implementace vyhledejte konkrétní formátování chování, které jsou nainstalované ve [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] typ zavaděč ve výchozím nastavení a nahraďte ji nebo přidat kompatibilní chování má spustit po výchozí chování.</span><span class="sxs-lookup"><span data-stu-id="f074f-153">To install a replacement behavior, the implementation must look for specific formatter behaviors that are installed by the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] type loader by default and either replace it or add a compatible behavior to run after the default behavior.</span></span>  
  
 <span data-ttu-id="f074f-154">Tyto operace formátování chování se dá nastavit prostřednictvím kódu programu před voláním <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A?displayProperty=nameWithType> nebo zadáním operaci chování, které se spustí až po výchozí nastavení.</span><span class="sxs-lookup"><span data-stu-id="f074f-154">These operation formatters behaviors can be set up programmatically prior to calling <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A?displayProperty=nameWithType> or by specifying an operation behavior that is executed after the default one.</span></span> <span data-ttu-id="f074f-155">Ale ji nelze snadno nastavit tak, že chování koncového bodu (a proto konfigurace) protože modelu chování neumožňuje chování k upravit popis stromové struktuře a nahradit jiného chování.</span><span class="sxs-lookup"><span data-stu-id="f074f-155">However, it cannot easily be set up by an endpoint behavior (and therefore by configuration) because the behavior model does not allow a behavior to replace other behaviors or otherwise modify the description tree.</span></span>  
  
 <span data-ttu-id="f074f-156">Na straně klienta:</span><span class="sxs-lookup"><span data-stu-id="f074f-156">On the client:</span></span>  
  
 <span data-ttu-id="f074f-157"><xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> Implementace, musí být implementována, aby mohli převést požadavky na požadavky HTTP GET a delegovat na původní formátování odpovědi.</span><span class="sxs-lookup"><span data-stu-id="f074f-157">The <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> implementation must be implemented so that it can convert the requests into HTTP GET requests and delegate to the original formatter for responses.</span></span> <span data-ttu-id="f074f-158">To se provádí volání `EnableHttpGetRequestsBehavior.ReplaceFormatterBehavior` metodu helper.</span><span class="sxs-lookup"><span data-stu-id="f074f-158">This is done by calling the `EnableHttpGetRequestsBehavior.ReplaceFormatterBehavior` helper method.</span></span>  
  
 <span data-ttu-id="f074f-159">To je třeba provést před voláním `CreateChannel`.</span><span class="sxs-lookup"><span data-stu-id="f074f-159">This must be done before calling `CreateChannel`.</span></span>  
  
```  
void ReplaceFormatterBehavior(OperationDescription operationDescription, EndpointAddress address)  
{  
    // Remove the DataContract behavior if it is present.  
    IOperationBehavior formatterBehavior = operationDescription.Behaviors.Remove<DataContractSerializerOperationBehavior>();  
    if (formatterBehavior == null)  
    {  
        // Remove the XmlSerializer behavior if it is present.  
        formatterBehavior = operationDescription.Behaviors.Remove<XmlSerializerOperationBehavior>();  
        ...  
    }  
  
    // Remember what the innerFormatterBehavior was.  
    DelegatingFormatterBehavior delegatingFormatterBehavior = new DelegatingFormatterBehavior(address);  
    delegatingFormatterBehavior.InnerFormatterBehavior = formatterBehavior;  
   operationDescription.Behaviors.Add(delegatingFormatterBehavior);  
}  
```  
  
 <span data-ttu-id="f074f-160">Na serveru:</span><span class="sxs-lookup"><span data-stu-id="f074f-160">On the server:</span></span>  
  
-   <span data-ttu-id="f074f-161"><xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter> Rozhraní musí být implementována, aby mohli číst požadavky HTTP GET a delegovat na původní formátovací modul pro zápis odpovědi.</span><span class="sxs-lookup"><span data-stu-id="f074f-161">The <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter> interface must be implemented so that it can read HTTP GET requests and delegate to the original formatter for writing responses.</span></span> <span data-ttu-id="f074f-162">To se provádí volání stejné `EnableHttpGetRequestsBehavior.ReplaceFormatterBehavior` Pomocná metoda jako klient (viz předchozí ukázka kódu).</span><span class="sxs-lookup"><span data-stu-id="f074f-162">This is done by calling the same `EnableHttpGetRequestsBehavior.ReplaceFormatterBehavior` helper method as the client (see the previous code sample).</span></span>  
  
-   <span data-ttu-id="f074f-163">To je třeba provést před <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> je volána.</span><span class="sxs-lookup"><span data-stu-id="f074f-163">This must be done before <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> is called.</span></span> <span data-ttu-id="f074f-164">V této ukázce ukážeme, jak je ručně změnit formátování před voláním <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.</span><span class="sxs-lookup"><span data-stu-id="f074f-164">In this sample, we show how the formatter is manually modified before calling <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.</span></span> <span data-ttu-id="f074f-165">Jiný způsob, jak dosáhnout samé je na odvození třídy z <xref:System.ServiceModel.ServiceHost> který zpřístupňuje volání `EnableHttpGetRequestsBehavior.ReplaceFormatterBehavior` před otevřením (viz prosím hostování dokumentace a ukázky příklady).</span><span class="sxs-lookup"><span data-stu-id="f074f-165">Another way to achieve the same thing is to derive a class from <xref:System.ServiceModel.ServiceHost> that makes the calls to `EnableHttpGetRequestsBehavior.ReplaceFormatterBehavior` before opening (please see hosting documentation and samples for examples).</span></span>  
  
### <a name="user-experience"></a><span data-ttu-id="f074f-166">Činnost koncového uživatele</span><span class="sxs-lookup"><span data-stu-id="f074f-166">User experience</span></span>  
 <span data-ttu-id="f074f-167">Na serveru:</span><span class="sxs-lookup"><span data-stu-id="f074f-167">On the server:</span></span>  
  
-   <span data-ttu-id="f074f-168">Server `ICalculator` implementace není potřeba změnit.</span><span class="sxs-lookup"><span data-stu-id="f074f-168">The server `ICalculator` implementation does not need to change.</span></span>  
  
-   <span data-ttu-id="f074f-169">App.config služby musíte použít vlastní POX vazby, která nastavuje `messageVersion` atribut `textMessageEncoding` element `None`.</span><span class="sxs-lookup"><span data-stu-id="f074f-169">The App.config for the service must use a custom POX binding that sets the `messageVersion` attribute of the `textMessageEncoding` element to `None`.</span></span>  
  
    ```xml  
    <bindings>  
      <customBinding>  
        <binding name="poxBinding">  
          <textMessageEncoding messageVersion="None" />  
          <httpTransport />  
        </binding>  
      </customBinding>  
    </bindings>  
    ```  
  
-   <span data-ttu-id="f074f-170">App.config pro službu musíte zadat také vlastní `EnableHttpGetRequestsBehavior` tak, že ho přidáte do části rozšíření chování a jeho použití.</span><span class="sxs-lookup"><span data-stu-id="f074f-170">The App.config for the service also must specify the custom `EnableHttpGetRequestsBehavior` by adding it to the behavior extensions section and using it.</span></span>  
  
    ```xml  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="enableHttpGetRequestsBehavior">  
          <enableHttpGetRequests />  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
  
    <extensions>  
      <behaviorExtensions>  
        <!-- Enabling HTTP GET requests: Behavior Extension -->  
        <add   
          name="enableHttpGetRequests"           type="Microsoft.ServiceModel.Samples.EnableHttpGetRequestsBehaviorElement, QueryStringFormatter, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
      </behaviorExtensions>  
    </extensions>  
    ```  
  
-   <span data-ttu-id="f074f-171">Přidání formátovacích modulů operaci před voláním <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.</span><span class="sxs-lookup"><span data-stu-id="f074f-171">Add operation formatters before calling <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.</span></span>  
  
 <span data-ttu-id="f074f-172">Na straně klienta:</span><span class="sxs-lookup"><span data-stu-id="f074f-172">On the client:</span></span>  
  
-   <span data-ttu-id="f074f-173">Implementace klienta není potřeba změnit.</span><span class="sxs-lookup"><span data-stu-id="f074f-173">The client implementation does not need to change.</span></span>  
  
-   <span data-ttu-id="f074f-174">App.config pro klienta, musíte použít vlastní POX vazby, která nastavuje `messageVersion` atribut `textMessageEncoding` element `None`.</span><span class="sxs-lookup"><span data-stu-id="f074f-174">The App.config for the client must use a custom POX binding that sets the `messageVersion` attribute of the `textMessageEncoding` element to `None`.</span></span> <span data-ttu-id="f074f-175">Jeden rozdíl ze služby je, že klient musí povolit ruční adresování tak, aby odchozí adresu můžete upravit.</span><span class="sxs-lookup"><span data-stu-id="f074f-175">One difference from the service is that the client must enable manual addressing so that the outgoing To address can be modified.</span></span>  
  
    ```xml  
    <bindings>  
      <customBinding>  
        <binding name="poxBinding">  
          <textMessageEncoding messageVersion="None" />  
          <httpTransport manualAddressing="True" />  
        </binding>  
      </customBinding>  
    </bindings>  
    ```  
  
-   <span data-ttu-id="f074f-176">App.config pro klienta, musíte zadat stejné vlastní `EnableHttpGetRequestsBehavior` jako server.</span><span class="sxs-lookup"><span data-stu-id="f074f-176">The App.config for the client must specify the same custom `EnableHttpGetRequestsBehavior` as the server.</span></span>  
  
-   <span data-ttu-id="f074f-177">Přidání formátovacích modulů operaci před voláním <xref:System.ServiceModel.ChannelFactory%601.CreateChannel>.</span><span class="sxs-lookup"><span data-stu-id="f074f-177">Add operation formatters before calling <xref:System.ServiceModel.ChannelFactory%601.CreateChannel>.</span></span>  
  
 <span data-ttu-id="f074f-178">Když spustíte ukázku, operace požadavky a odpovědi se zobrazí v okně konzoly klienta.</span><span class="sxs-lookup"><span data-stu-id="f074f-178">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="f074f-179">Všechny čtyři operace (přidat, odečíst, násobení a dělení) musí být úspěšné.</span><span class="sxs-lookup"><span data-stu-id="f074f-179">All four operations (Add, Subtract, Multiply, and Divide) must succeed.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f074f-180">Ukázky může být již nainstalována na váš počítač.</span><span class="sxs-lookup"><span data-stu-id="f074f-180">The samples may already be installed on your machine.</span></span> <span data-ttu-id="f074f-181">Před pokračováním zkontrolovat na následující adresář (výchozí).</span><span class="sxs-lookup"><span data-stu-id="f074f-181">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="f074f-182">Pokud tento adresář neexistuje, přejděte na [Windows Communication Foundation (WCF) a ukázky Windows Workflow Foundation (WF) pro rozhraní .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) ke stažení všechny [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] a [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ukázky.</span><span class="sxs-lookup"><span data-stu-id="f074f-182">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f074f-183">Tato ukázka se nachází v následujícím adresáři.</span><span class="sxs-lookup"><span data-stu-id="f074f-183">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Formatters\QuieryStringFormatter`  
  
##### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="f074f-184">Pokud chcete nastavit, sestavit a spustit ukázku</span><span class="sxs-lookup"><span data-stu-id="f074f-184">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="f074f-185">Ujistěte se, že jste provedli [jednorázové postup nastavení pro ukázky Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="f074f-185">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="f074f-186">Sestavte řešení, postupujte podle pokynů v [vytváření ukázky Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="f074f-186">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="f074f-187">Spustit ukázku v konfiguraci s jednou nebo mezi počítači, postupujte podle pokynů v [spuštění ukázky Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="f074f-187">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f074f-188">Viz také</span><span class="sxs-lookup"><span data-stu-id="f074f-188">See Also</span></span>
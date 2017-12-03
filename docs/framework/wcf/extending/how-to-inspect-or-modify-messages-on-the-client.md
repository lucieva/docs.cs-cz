---
title: "Postupy: Kontrola nebo úprava zprávy na straně klienta"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b8256335-f1c2-419f-b862-9f220ccad84c
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 164e19891e576b6d310839a1221ad8ed0d315444
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-inspect-or-modify-messages-on-the-client"></a><span data-ttu-id="b5341-102">Postupy: Kontrola nebo úprava zprávy na straně klienta</span><span class="sxs-lookup"><span data-stu-id="b5341-102">How to: Inspect or Modify Messages on the Client</span></span>
<span data-ttu-id="b5341-103">Můžete zkontrolovat nebo upravit příchozích nebo odchozích zpráv mezi [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] klienta implementací <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType> a jejich vložení do modulu runtime klienta.</span><span class="sxs-lookup"><span data-stu-id="b5341-103">You can inspect or modify the incoming or outgoing messages across a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client by implementing a <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType> and inserting it into the client runtime.</span></span> <span data-ttu-id="b5341-104">Další informace najdete v tématu [rozšíření klienti](../../../../docs/framework/wcf/extending/extending-clients.md).</span><span class="sxs-lookup"><span data-stu-id="b5341-104">For more information, see [Extending Clients](../../../../docs/framework/wcf/extending/extending-clients.md).</span></span> <span data-ttu-id="b5341-105">Ekvivalentní funkce služby je <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b5341-105">The equivalent feature on the service is the <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b5341-106">Kompletní příklad najdete v článku [inspektoři zpráv](../../../../docs/framework/wcf/samples/message-inspectors.md) ukázka.</span><span class="sxs-lookup"><span data-stu-id="b5341-106">For a complete code example see the [Message Inspectors](../../../../docs/framework/wcf/samples/message-inspectors.md) sample.</span></span>  
  
### <a name="to-inspect-or-modify-messages"></a><span data-ttu-id="b5341-107">Chcete-li zkontrolovat nebo upravit zprávy</span><span class="sxs-lookup"><span data-stu-id="b5341-107">To inspect or modify messages</span></span>  
  
1.  <span data-ttu-id="b5341-108">Implementace <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType> rozhraní.</span><span class="sxs-lookup"><span data-stu-id="b5341-108">Implement the <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType> interface.</span></span>  
  
2.  <span data-ttu-id="b5341-109">Implementace <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType> nebo <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> v závislosti na oboru, ve kterém chcete vložit inspector zpráv klienta.</span><span class="sxs-lookup"><span data-stu-id="b5341-109">Implement a <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType> or <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> depending upon the scope at which you want to insert the client message inspector.</span></span> <span data-ttu-id="b5341-110"><xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>Umožňuje změnit chování na úrovni koncového bodu.</span><span class="sxs-lookup"><span data-stu-id="b5341-110"><xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType> allows you to change behavior at the endpoint level.</span></span> <span data-ttu-id="b5341-111"><xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType>Umožňuje změnit chování na úrovni kontrakt.</span><span class="sxs-lookup"><span data-stu-id="b5341-111"><xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> allows you to change behavior at the contract level.</span></span>  
  
3.  <span data-ttu-id="b5341-112">Vložit chování před voláním <xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=nameWithType> nebo <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> metodu <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b5341-112">Insert the behavior prior to calling the <xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=nameWithType> or the <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> method on the <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b5341-113">Podrobnosti najdete v tématu [konfigurace a rozšíření modulu Runtime s chováním](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).</span><span class="sxs-lookup"><span data-stu-id="b5341-113">For details, see [Configuring and Extending the Runtime with Behaviors](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5341-114">Příklad</span><span class="sxs-lookup"><span data-stu-id="b5341-114">Example</span></span>  
 <span data-ttu-id="b5341-115">Následující příklady kódu zobrazit v pořadí:</span><span class="sxs-lookup"><span data-stu-id="b5341-115">The following code examples show, in order:</span></span>  
  
-   <span data-ttu-id="b5341-116">Implementace inspector klienta.</span><span class="sxs-lookup"><span data-stu-id="b5341-116">A client inspector implementation.</span></span>  
  
-   <span data-ttu-id="b5341-117">Chování koncového bodu, která vloží funkci Kontrola.</span><span class="sxs-lookup"><span data-stu-id="b5341-117">An endpoint behavior that inserts the inspector.</span></span>  
  
-   <span data-ttu-id="b5341-118">A <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>-odvozené třídy, který umožňuje přidat chování v konfiguračním souboru.</span><span class="sxs-lookup"><span data-stu-id="b5341-118">A <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>- derived class that allows you to add the behavior in a configuration file.</span></span>  
  
-   <span data-ttu-id="b5341-119">Konfigurační soubor, který přidává chování koncového bodu, která vloží inspector zpráv klienta do modulu runtime klienta.</span><span class="sxs-lookup"><span data-stu-id="b5341-119">A configuration file that adds the endpoint behavior which inserts the client message inspector into the client runtime.</span></span>  
  
```csharp  
// Client message inspector  
public class SimpleMessageInspector : IClientMessageInspector  
{  
    public void AfterReceiveReply(ref System.ServiceModel.Channels.Message reply, object correlationState)  
    {  
        // Implement this method to inspect/modify messages after a message  
        // is received but prior to passing it back to the client   
        Console.WriteLine("AfterReceiveReply called");  
    }  
  
    public object BeforeSendRequest(ref System.ServiceModel.Channels.Message request, IClientChannel channel)  
    {  
        // Implement this method to inspect/modify messages before they   
        // are sent to the service  
        Console.WriteLine("BeforeSendRequest called");  
        return null;  
    }  
}  
```  
  
```csharp  
// Endpoint behavior  
public class SimpleEndpointBehavior : IEndpointBehavior  
{  
    public void AddBindingParameters(ServiceEndpoint endpoint, System.ServiceModel.Channels.BindingParameterCollection bindingParameters)  
    {  
         // No implementation necessary  
    }  
  
    public void ApplyClientBehavior(ServiceEndpoint endpoint, ClientRuntime clientRuntime)  
    {  
        clientRuntime.MessageInspectors.Add(new SimpleMessageInspector());  
    }  
  
    public void ApplyDispatchBehavior(ServiceEndpoint endpoint, EndpointDispatcher endpointDispatcher)  
    {  
         // No implementation necessary  
    }  
  
    public void Validate(ServiceEndpoint endpoint)  
    {  
         // No implementation necessary  
    }  
}  
```  
  
```csharp  
// Configuration element   
public class SimpleBehaviorExtensionElement : BehaviorExtensionElement  
{  
    public override Type BehaviorType  
    {  
        get { return typeof(SimpleEndpointBehavior); }  
    }  
  
    protected override object CreateBehavior()  
    {  
         // Create the  endpoint behavior that will insert the message  
         // inspector into the client runtime  
        return new SimpleEndpointBehavior();  
    }  
}  
```  
  
```xml
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
    <system.serviceModel>  
        <client>  
            <endpoint address="http://localhost:8080/SimpleService/"   
                      binding="wsHttpBinding"  
                      contract="ServiceReference1.IService1"  
                      name="WSHttpBinding_IService1"/>  
        </client>  
  
      <behaviors>  
        <endpointBehaviors>  
          <behavior name="clientInspectorsAdded">  
            <simpleBehaviorExtension />  
          </behavior>  
        </endpointBehaviors>  
      </behaviors>  
      <extensions>  
        <behaviorExtensions>  
          <add  
            name="simpleBehaviorExtension"  
            type="SimpleServiceLib.SimpleBehaviorExtensionElement, Host, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null"/>  
        </behaviorExtensions>  
      </extensions>  
    </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b5341-120">Viz také</span><span class="sxs-lookup"><span data-stu-id="b5341-120">See Also</span></span>  
 <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>  
 <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>  
 [<span data-ttu-id="b5341-121">Konfigurace a rozšíření modulu Runtime s chováním</span><span class="sxs-lookup"><span data-stu-id="b5341-121">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
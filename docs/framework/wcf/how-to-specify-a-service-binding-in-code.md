---
title: "Postupy: Zadání vazby služby v kódu"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 67ab5dd8-79c1-4e62-aa75-828ea918a53a
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 64d33b268c736b3dba333b767bee7fedb487397b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-a-service-binding-in-code"></a><span data-ttu-id="2fc0c-102">Postupy: Zadání vazby služby v kódu</span><span class="sxs-lookup"><span data-stu-id="2fc0c-102">How to: Specify a Service Binding in Code</span></span>
<span data-ttu-id="2fc0c-103">V tomto příkladu `ICalculator` kontrakt je definována pro službu kalkulačky, služba se implementuje v `CalculatorService` třídě a následně svůj koncový bod je definována v kódu, kde je zadán, že musí používat službu <xref:System.ServiceModel.BasicHttpBinding> třídy.</span><span class="sxs-lookup"><span data-stu-id="2fc0c-103">In this example, an `ICalculator` contract is defined for a calculator service, the service is implemented in the `CalculatorService` class, and then its endpoint is defined in code, where it is specified that the service must use the <xref:System.ServiceModel.BasicHttpBinding> class.</span></span>  
  
 <span data-ttu-id="2fc0c-104">Obvykle je osvědčeným postupem zadejte vazby a informace o adrese deklarativně v konfiguraci, nikoli imperativní v kódu.</span><span class="sxs-lookup"><span data-stu-id="2fc0c-104">It is usually the best practice to specify the binding and address information declaratively in configuration rather than imperatively in code.</span></span> <span data-ttu-id="2fc0c-105">Definování koncové body v kódu obvykle není praktické protože jsou obvykle liší od těch, které používá při služby je vyvíjen vazeb a adresy pro v nasazené službě.</span><span class="sxs-lookup"><span data-stu-id="2fc0c-105">Defining endpoints in code is usually not practical because the bindings and addresses for a deployed service are typically different from those used while the service is being developed.</span></span> <span data-ttu-id="2fc0c-106">Obecně platí udržování vazby a adresování informace mimo kód jim umožňuje změnit bez nutnosti znovu zkompiluje nebo znovu nasadit aplikaci.</span><span class="sxs-lookup"><span data-stu-id="2fc0c-106">More generally, keeping the binding and addressing information out of the code allows them to change without having to recompile or redeploy the application.</span></span>  
  
 <span data-ttu-id="2fc0c-107">Popis toho, jak nakonfigurovat tuto službu pomocí konfigurace – elementy místo kód, najdete v části [postupy: zadání vazby služby v konfiguraci](../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="2fc0c-107">For a description of how to configure this service using configuration elements instead of code, see [How to: Specify a Service Binding in Configuration](../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).</span></span>  
  
### <a name="to-specify-in-code-to-use-the-basichttpbinding-for-the-service"></a><span data-ttu-id="2fc0c-108">Pokud chcete zadat do kódu pro použití BasicHttpBinding pro službu</span><span class="sxs-lookup"><span data-stu-id="2fc0c-108">To specify in code to use the BasicHttpBinding for the service</span></span>  
  
1.  <span data-ttu-id="2fc0c-109">Definování kontraktu služby pro typ služby.</span><span class="sxs-lookup"><span data-stu-id="2fc0c-109">Define a service contract for the type of service.</span></span>  
  
     [!code-csharp[C_HowTo_CodeServiceBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#1)]
     [!code-vb[C_HowTo_CodeServiceBinding#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#1)]  
  
2.  <span data-ttu-id="2fc0c-110">Implementujte kontrakt služby v třídě služby.</span><span class="sxs-lookup"><span data-stu-id="2fc0c-110">Implement the service contract in a service class.</span></span>  
  
     [!code-csharp[C_HowTo_CodeServiceBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#2)]
     [!code-vb[C_HowTo_CodeServiceBinding#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#2)]  
  
3.  <span data-ttu-id="2fc0c-111">V hostitelských aplikaci vytvořte základní adresu pro tuto službu a vazby pro použití se službou.</span><span class="sxs-lookup"><span data-stu-id="2fc0c-111">In the hosting application, create the base address for the service and the binding to use with the service.</span></span>  
  
     [!code-csharp[C_HowTo_CodeServiceBinding#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#3)]
     [!code-vb[C_HowTo_CodeServiceBinding#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#3)]  
  
4.  <span data-ttu-id="2fc0c-112">Vytvořte hostitele služby, přidat koncový bod a pak otevřete hostitele.</span><span class="sxs-lookup"><span data-stu-id="2fc0c-112">Create the host for the service, add the endpoint, and then open the host.</span></span>  
  
     [!code-csharp[C_HowTo_CodeServiceBinding#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#4)]
     [!code-vb[C_HowTo_CodeServiceBinding#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#4)]  
  
### <a name="to-modify-the-default-values-of-the-binding-properties"></a><span data-ttu-id="2fc0c-113">Chcete-li změnit výchozí hodnoty vlastností vazby</span><span class="sxs-lookup"><span data-stu-id="2fc0c-113">To modify the default values of the binding properties</span></span>  
  
1.  <span data-ttu-id="2fc0c-114">K úpravě jeden z výchozí hodnoty vlastností <xref:System.ServiceModel.BasicHttpBinding> třídy, nastavte hodnotu vlastnosti o vazbě na novou hodnotu před vytvořením hostitele.</span><span class="sxs-lookup"><span data-stu-id="2fc0c-114">To modify one of the default property values of the <xref:System.ServiceModel.BasicHttpBinding> class, set the property value on the binding to the new value before creating the host.</span></span> <span data-ttu-id="2fc0c-115">Například změnit výchozí časový limit pro otevření a zavření hodnoty 1 minuta na 2 minuty, použijte následující příkaz.</span><span class="sxs-lookup"><span data-stu-id="2fc0c-115">For example, to change the default open and close timeout values of 1 minute to 2 minutes, use the following.</span></span>  
  
     [!code-csharp[C_HowTo_CodeServiceBinding#5](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#5)]
     [!code-vb[C_HowTo_CodeServiceBinding#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="2fc0c-116">Viz také</span><span class="sxs-lookup"><span data-stu-id="2fc0c-116">See Also</span></span>  
 [<span data-ttu-id="2fc0c-117">Používání vazeb ke konfiguraci služeb a klientů</span><span class="sxs-lookup"><span data-stu-id="2fc0c-117">Using Bindings to Configure Services and Clients</span></span>](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="2fc0c-118">Zadání adresy koncového bodu</span><span class="sxs-lookup"><span data-stu-id="2fc0c-118">Specifying an Endpoint Address</span></span>](../../../docs/framework/wcf/specifying-an-endpoint-address.md)
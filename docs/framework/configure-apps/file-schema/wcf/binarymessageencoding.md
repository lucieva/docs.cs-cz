---
title: '&lt;binaryMessageEncoding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e4ae3cd4-6b67-4ce1-af4b-9400e0a38dba
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4e1314347dfb83fb0631ebaa98b4d35bb0ac402f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/02/2017
---
# <a name="ltbinarymessageencodinggt"></a><span data-ttu-id="c77ed-102">&lt;binaryMessageEncoding&gt;</span><span class="sxs-lookup"><span data-stu-id="c77ed-102">&lt;binaryMessageEncoding&gt;</span></span>
<span data-ttu-id="c77ed-103">Definuje kodéru zprávy v binární, která kóduje zprávy Windows Communication Foundation (WCF) v binárním v drátové síti.</span><span class="sxs-lookup"><span data-stu-id="c77ed-103">Defines a binary message encoder that encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span>  
  
 <span data-ttu-id="c77ed-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="c77ed-104">\<system.serviceModel></span></span>  
<span data-ttu-id="c77ed-105">\<vazby ></span><span class="sxs-lookup"><span data-stu-id="c77ed-105">\<bindings></span></span>  
<span data-ttu-id="c77ed-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="c77ed-106">\<customBinding></span></span>  
<span data-ttu-id="c77ed-107">\<Vazba ></span><span class="sxs-lookup"><span data-stu-id="c77ed-107">\<binding></span></span>  
<span data-ttu-id="c77ed-108">\<binaryMessageEncoding ></span><span class="sxs-lookup"><span data-stu-id="c77ed-108">\<binaryMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c77ed-109">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="c77ed-109">Syntax</span></span>  
  
```xml  
<binaryMessageEncoding   
      maxReadPoolSize="Integer"  
   maxSessionSize="Integer"   
   maxWritePoolSize="Integer"   messageVersion="Soap11Addressing10/Soap12Addressing10" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c77ed-110">Atributy a elementy</span><span class="sxs-lookup"><span data-stu-id="c77ed-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c77ed-111">Následující části popisují atributy, podřízené prvky a nadřazené prvky.</span><span class="sxs-lookup"><span data-stu-id="c77ed-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c77ed-112">Atributy</span><span class="sxs-lookup"><span data-stu-id="c77ed-112">Attributes</span></span>  
  
|<span data-ttu-id="c77ed-113">Atribut</span><span class="sxs-lookup"><span data-stu-id="c77ed-113">Attribute</span></span>|<span data-ttu-id="c77ed-114">Popis</span><span class="sxs-lookup"><span data-stu-id="c77ed-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c77ed-115">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="c77ed-115">maxReadPoolSize</span></span>|<span data-ttu-id="c77ed-116">Celé číslo, které definuje počet zpráv lze číst souběžně bez přidělení nového čtečky.</span><span class="sxs-lookup"><span data-stu-id="c77ed-116">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="c77ed-117">Větší velikosti fondu se systém odolnější vůči špičky aktivity za cenu větší pracovní sady.</span><span class="sxs-lookup"><span data-stu-id="c77ed-117">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="c77ed-118">Výchozí hodnota je 64.</span><span class="sxs-lookup"><span data-stu-id="c77ed-118">The default is 64.</span></span>|  
|<span data-ttu-id="c77ed-119">maxSessionSize</span><span class="sxs-lookup"><span data-stu-id="c77ed-119">maxSessionSize</span></span>|<span data-ttu-id="c77ed-120">Kladné celé číslo, které nastavuje velikost v bajtech vyrovnávací paměti používané pro kódování.</span><span class="sxs-lookup"><span data-stu-id="c77ed-120">A positive integer that sets the size, in bytes, of the buffer used for encoding.</span></span> <span data-ttu-id="c77ed-121">Větší vyrovnávací paměť zvyšuje rychlost kódování za cenu velikost pracovní sady.</span><span class="sxs-lookup"><span data-stu-id="c77ed-121">A larger buffer increases encoding speed at the expense of the size of the working set.</span></span> <span data-ttu-id="c77ed-122">Výchozí hodnota je 2048.</span><span class="sxs-lookup"><span data-stu-id="c77ed-122">The default is 2048.</span></span>|  
|<span data-ttu-id="c77ed-123">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="c77ed-123">maxWritePoolSize</span></span>|<span data-ttu-id="c77ed-124">Celé číslo, které definuje počet zpráv lze najednou odeslat bez přiděluje nový zapisovače.</span><span class="sxs-lookup"><span data-stu-id="c77ed-124">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="c77ed-125">Větší velikosti fondu se systém odolnější vůči špičky aktivity za cenu větší pracovní sady.</span><span class="sxs-lookup"><span data-stu-id="c77ed-125">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="c77ed-126">Výchozí hodnota je 16.</span><span class="sxs-lookup"><span data-stu-id="c77ed-126">The default is 16.</span></span>|  
|<span data-ttu-id="c77ed-127">verze messageVersion</span><span class="sxs-lookup"><span data-stu-id="c77ed-127">messageVersion</span></span>|<span data-ttu-id="c77ed-128">Určuje zprávu protokolu SOAP a WS-Addressing verze, které se nepoužívají nebo se očekává.</span><span class="sxs-lookup"><span data-stu-id="c77ed-128">Specifies the SOAP message and WS-Addressing versions that are used or expected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c77ed-129">Podřízené elementy</span><span class="sxs-lookup"><span data-stu-id="c77ed-129">Child Elements</span></span>  
  
|<span data-ttu-id="c77ed-130">Prvek</span><span class="sxs-lookup"><span data-stu-id="c77ed-130">Element</span></span>|<span data-ttu-id="c77ed-131">Popis</span><span class="sxs-lookup"><span data-stu-id="c77ed-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c77ed-132">\<readerQuotas ></span><span class="sxs-lookup"><span data-stu-id="c77ed-132">\<readerQuotas></span></span>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="c77ed-133">Definuje omezení na složitosti protokolu SOAP zprávy, které lze zpracovat koncovými body, které jsou konfigurovány pomocí této vazby.</span><span class="sxs-lookup"><span data-stu-id="c77ed-133">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="c77ed-134">Tento element je typu <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="c77ed-134">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c77ed-135">Nadřazené elementy</span><span class="sxs-lookup"><span data-stu-id="c77ed-135">Parent Elements</span></span>  
  
|<span data-ttu-id="c77ed-136">Prvek</span><span class="sxs-lookup"><span data-stu-id="c77ed-136">Element</span></span>|<span data-ttu-id="c77ed-137">Popis</span><span class="sxs-lookup"><span data-stu-id="c77ed-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c77ed-138">\<Vazba ></span><span class="sxs-lookup"><span data-stu-id="c77ed-138">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="c77ed-139">Definuje všechny možnosti vazba vlastní vazby.</span><span class="sxs-lookup"><span data-stu-id="c77ed-139">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c77ed-140">Poznámky</span><span class="sxs-lookup"><span data-stu-id="c77ed-140">Remarks</span></span>  
 <span data-ttu-id="c77ed-141">Proces transformace zprávu do pořadí bajtů kódování je.</span><span class="sxs-lookup"><span data-stu-id="c77ed-141">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="c77ed-142">Dekódování je zpětné proces.</span><span class="sxs-lookup"><span data-stu-id="c77ed-142">Decoding is the reverse process.</span></span> <span data-ttu-id="c77ed-143">Windows Communication Foundation (WCF) zahrnuje tři typy kódování pro protokolu SOAP zprávy: Text, Binary a zpráva přenosu optimalizace mechanismus (MTOM).</span><span class="sxs-lookup"><span data-stu-id="c77ed-143">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="c77ed-144">`binaryMessageEncoding` Element Určuje binární formát, .NET pro formát XML a má možností, které určují kódování znaků a verzi protokolu SOAP a adresování WS má být použit.</span><span class="sxs-lookup"><span data-stu-id="c77ed-144">The `binaryMessageEncoding` element specifies the .NET Binary Format for XML and has options to specify the character encoding and the SOAP and WS-Addressing version to be used.</span></span> <span data-ttu-id="c77ed-145">Kodér zprávy v binární kódování zpráv Windows Communication Foundation (WCF) v binárním v drátové síti.</span><span class="sxs-lookup"><span data-stu-id="c77ed-145">The binary message encoder encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span> <span data-ttu-id="c77ed-146">Když toto kódování výsledkem velmi rychlé přenos zpráv, interoperabilita založené na protokolu WS-* dojde ke ztrátě standardů.</span><span class="sxs-lookup"><span data-stu-id="c77ed-146">While this encoding results in very fast transmission of messages, interoperability based on the WS-* standards is lost.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c77ed-147">Příklad</span><span class="sxs-lookup"><span data-stu-id="c77ed-147">Example</span></span>  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="211"  
   maxWritePoolSize="2132"  
   maxSessionSize="3141" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="c77ed-148">Viz také</span><span class="sxs-lookup"><span data-stu-id="c77ed-148">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.BinaryMessageEncodingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>  
 <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>  
 [<span data-ttu-id="c77ed-149">Kódování zpráv</span><span class="sxs-lookup"><span data-stu-id="c77ed-149">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)  
 [<span data-ttu-id="c77ed-150">Výběr kodéru zprávy</span><span class="sxs-lookup"><span data-stu-id="c77ed-150">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 [<span data-ttu-id="c77ed-151">Vazby</span><span class="sxs-lookup"><span data-stu-id="c77ed-151">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="c77ed-152">Rozšiřování vazeb</span><span class="sxs-lookup"><span data-stu-id="c77ed-152">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="c77ed-153">Vlastní vazby</span><span class="sxs-lookup"><span data-stu-id="c77ed-153">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="c77ed-154">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="c77ed-154">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
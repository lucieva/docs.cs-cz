---
title: "220 – MessageSentToTransport"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aef4e781-240b-45bc-bff8-400053037e71
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7bc3b784dca090ed768711728a054782e06c7b10
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/02/2017
---
# <a name="220---messagesenttotransport"></a><span data-ttu-id="b1402-102">220 – MessageSentToTransport</span><span class="sxs-lookup"><span data-stu-id="b1402-102">220 - MessageSentToTransport</span></span>
## <a name="properties"></a><span data-ttu-id="b1402-103">Vlastnosti</span><span class="sxs-lookup"><span data-stu-id="b1402-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b1402-104">ID</span><span class="sxs-lookup"><span data-stu-id="b1402-104">Id</span></span>|<span data-ttu-id="b1402-105">220</span><span class="sxs-lookup"><span data-stu-id="b1402-105">220</span></span>|  
|<span data-ttu-id="b1402-106">Klíčová slova</span><span class="sxs-lookup"><span data-stu-id="b1402-106">Keywords</span></span>|<span data-ttu-id="b1402-107">EndToEndMonitoring, řešení potíží s ServiceModel</span><span class="sxs-lookup"><span data-stu-id="b1402-107">EndToEndMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="b1402-108">úroveň</span><span class="sxs-lookup"><span data-stu-id="b1402-108">Level</span></span>|<span data-ttu-id="b1402-109">Informace o</span><span class="sxs-lookup"><span data-stu-id="b1402-109">Information</span></span>|  
|<span data-ttu-id="b1402-110">Kanál</span><span class="sxs-lookup"><span data-stu-id="b1402-110">Channel</span></span>|<span data-ttu-id="b1402-111">Aplikaci Microsoft Windows Server – aplikace nebo analytické</span><span class="sxs-lookup"><span data-stu-id="b1402-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b1402-112">Popis</span><span class="sxs-lookup"><span data-stu-id="b1402-112">Description</span></span>  
 <span data-ttu-id="b1402-113">Tato událost je vygenerované při modelu služby odešle zprávu do přenosu.</span><span class="sxs-lookup"><span data-stu-id="b1402-113">This event is emitted when the Service Model sends a message to the transport.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b1402-114">Tato událost nebude vygenerované pro jednosměrné přenosy.</span><span class="sxs-lookup"><span data-stu-id="b1402-114">This event will not be emitted for one-way transports.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b1402-115">Zpráva</span><span class="sxs-lookup"><span data-stu-id="b1402-115">Message</span></span>  
 <span data-ttu-id="b1402-116">Dispečer poslali zprávu o přenos.</span><span class="sxs-lookup"><span data-stu-id="b1402-116">The Dispatcher sent a message to the transport.</span></span> <span data-ttu-id="b1402-117">ID korelace == '%1'.</span><span class="sxs-lookup"><span data-stu-id="b1402-117">Correlation ID == '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b1402-118">Podrobnosti</span><span class="sxs-lookup"><span data-stu-id="b1402-118">Details</span></span>  
  
|<span data-ttu-id="b1402-119">Název položky dat</span><span class="sxs-lookup"><span data-stu-id="b1402-119">Data Item Name</span></span>|<span data-ttu-id="b1402-120">Datová položka – Typ</span><span class="sxs-lookup"><span data-stu-id="b1402-120">Data Item Type</span></span>|<span data-ttu-id="b1402-121">Popis</span><span class="sxs-lookup"><span data-stu-id="b1402-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b1402-122">ID korelace</span><span class="sxs-lookup"><span data-stu-id="b1402-122">Correlation ID</span></span>|`xs:GUID`|<span data-ttu-id="b1402-123">Aktivita ID použít ke korelaci `MessageSentToTransport` událostí ze služby nebo klienta na jeho odpovídající `MessageReceivedFromTransport` na druhém konci.</span><span class="sxs-lookup"><span data-stu-id="b1402-123">The activity ID used to correlate a `MessageSentToTransport` event from a service or client to its corresponding `MessageReceivedFromTransport` on the other end.</span></span>|  
|<span data-ttu-id="b1402-124">HostReference</span><span class="sxs-lookup"><span data-stu-id="b1402-124">HostReference</span></span>|`xs:string`|<span data-ttu-id="b1402-125">Pro hostované webové služby v tomto poli jednoznačně identifikuje v hierarchii webové služby.</span><span class="sxs-lookup"><span data-stu-id="b1402-125">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="b1402-126">Formát je definovaný jako "virtuální cesta aplikace název webu &#124; Virtuální cesta služby &#124; ServiceName}.</span><span class="sxs-lookup"><span data-stu-id="b1402-126">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="b1402-127">Příklad: "Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="b1402-127">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="b1402-128">Domény aplikace</span><span class="sxs-lookup"><span data-stu-id="b1402-128">AppDomain</span></span>|`xs:string`|<span data-ttu-id="b1402-129">Řetězec vrácený AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="b1402-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
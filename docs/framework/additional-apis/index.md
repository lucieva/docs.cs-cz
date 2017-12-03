---
title: "Rozhraní API a knihovny další – třída"
ms.custom: 
ms.date: 04/12/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e3bb7a7c53cbca8bbd4026b46ce59589cef22382
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="additional-class-libraries-and-apis"></a><span data-ttu-id="69bd3-102">Rozhraní API a knihovny další – třída</span><span class="sxs-lookup"><span data-stu-id="69bd3-102">Additional class libraries and APIs</span></span>

<span data-ttu-id="69bd3-103">Rozhraní .NET Framework je neustále vyvíjejí a za účelem zlepšení vývoj pro různé platformy nebo zavést nové funkce již v rané fázi pro naše zákazníky, vydáváme nové funkce vzdálenou správu (OOB).</span><span class="sxs-lookup"><span data-stu-id="69bd3-103">The .NET Framework is constantly evolving and in order to improve cross-platform development or to introduce new functionality early to our customers, we release new features out of band (OOB).</span></span> <span data-ttu-id="69bd3-104">Toto téma obsahuje seznam projektů OOB, které poskytujeme dokumentaci.</span><span class="sxs-lookup"><span data-stu-id="69bd3-104">This topic lists the OOB projects that we provide documentation for.</span></span>  
  
<span data-ttu-id="69bd3-105">Kromě toho některé knihovny cíle specifické platformy nebo implementace rozhraní .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="69bd3-105">In addition, some libraries target specific platforms or implementations of the .NET Framework.</span></span> <span data-ttu-id="69bd3-106">Například <xref:System.Text.CodePagesEncodingProvider> třída provede kódování kódu stránky k dispozici pro aplikace UWP vyvinuté pomocí rozhraní .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="69bd3-106">For example, the <xref:System.Text.CodePagesEncodingProvider> class makes code page encodings available to UWP apps developed using the .NET Framework.</span></span> <span data-ttu-id="69bd3-107">Toto téma obsahuje také tyto knihovny.</span><span class="sxs-lookup"><span data-stu-id="69bd3-107">This topic lists these libraries as well.</span></span>  
  
## <a name="oob-projects"></a><span data-ttu-id="69bd3-108">Projekty OOB</span><span class="sxs-lookup"><span data-stu-id="69bd3-108">OOB projects</span></span>
  
| <span data-ttu-id="69bd3-109">Project</span><span class="sxs-lookup"><span data-stu-id="69bd3-109">Project</span></span> | <span data-ttu-id="69bd3-110">Popis</span><span class="sxs-lookup"><span data-stu-id="69bd3-110">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | <span data-ttu-id="69bd3-111">Poskytuje kolekcí, které jsou vlákno bezpečné a zaručenou nikdy změnit jejich obsah.</span><span class="sxs-lookup"><span data-stu-id="69bd3-111">Provides collections that are thread safe and guaranteed to never change their contents.</span></span> |
| <xref:System.Net.Http.WinHttpHandler> | <span data-ttu-id="69bd3-112">Poskytuje obslužné rutiny zpráv pro <xref:System.Net.Http.HttpClient> založené na rozhraní WinHTTP systému Windows.</span><span class="sxs-lookup"><span data-stu-id="69bd3-112">Provides a message handler for <xref:System.Net.Http.HttpClient> based on the WinHTTP interface of Windows.</span></span> |
| [<span data-ttu-id="69bd3-113">System.Numerics.Vectors</span><span class="sxs-lookup"><span data-stu-id="69bd3-113">System.Numerics.Vectors</span></span>](https://msdn.microsoft.com/library/mt452176.aspx) | <span data-ttu-id="69bd3-114">Poskytuje knihovnu vektoru typy, které můžete využít výhod SIMD hardwarové akcelerace.</span><span class="sxs-lookup"><span data-stu-id="69bd3-114">Provides a library of vector types that can take advantage of SIMD hardware-based acceleration.</span></span>| 
| <xref:System.Threading.Tasks.Dataflow> | <span data-ttu-id="69bd3-115">Knihovna toku dat TPL poskytuje součásti toku dat a pomáhá tak zvýšit robustnost aplikací s povolenými souběžnosti.</span><span class="sxs-lookup"><span data-stu-id="69bd3-115">The TPL Dataflow Library provides dataflow components to help increase the robustness of concurrency-enabled applications.</span></span> |  

## <a name="platform-specific-libraries"></a><span data-ttu-id="69bd3-116">Specifické pro platformu knihovny</span><span class="sxs-lookup"><span data-stu-id="69bd3-116">Platform-specific libraries</span></span>
  
| <span data-ttu-id="69bd3-117">Project</span><span class="sxs-lookup"><span data-stu-id="69bd3-117">Project</span></span> | <span data-ttu-id="69bd3-118">Popis</span><span class="sxs-lookup"><span data-stu-id="69bd3-118">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | <span data-ttu-id="69bd3-119">Rozšiřuje <xref:System.Text.EncodingProvider> třídy pro zpřístupnění kódování stránky kód pro aplikace, které cílí na univerzální platformu Windows.</span><span class="sxs-lookup"><span data-stu-id="69bd3-119">Extends the <xref:System.Text.EncodingProvider> class to make code page encodings available to apps that target the Universal Windows Platform.</span></span> |  
  
## <a name="private-apis"></a><span data-ttu-id="69bd3-120">Soukromé rozhraní API</span><span class="sxs-lookup"><span data-stu-id="69bd3-120">Private APIs</span></span>  

<span data-ttu-id="69bd3-121">Tato rozhraní API podpory produktu infrastruktury a nejsou určené/podporované pro použití přímo z vašeho kódu.</span><span class="sxs-lookup"><span data-stu-id="69bd3-121">These APIs support the product infrastructure and are not intended/supported to be used directly from your code.</span></span>  
  
| <span data-ttu-id="69bd3-122">Název rozhraní API</span><span class="sxs-lookup"><span data-stu-id="69bd3-122">API Name</span></span> |
| -------- |
| [<span data-ttu-id="69bd3-123">System.Net.Connection – třída</span><span class="sxs-lookup"><span data-stu-id="69bd3-123">System.Net.Connection Class</span></span>](../../../docs/framework/additional-apis/connection.md) |
| [<span data-ttu-id="69bd3-124">System.Net.Connection.m\_WriteList pole</span><span class="sxs-lookup"><span data-stu-id="69bd3-124">System.Net.Connection.m\_WriteList Field</span></span>](../../../docs/framework/additional-apis/m_writelist.md) |
| [<span data-ttu-id="69bd3-125">System.Net.ConnectionGroup – třída</span><span class="sxs-lookup"><span data-stu-id="69bd3-125">System.Net.ConnectionGroup Class</span></span>](../../../docs/framework/additional-apis/connectiongroup.md) |
| [<span data-ttu-id="69bd3-126">System.Net.ConnectionGroup.m\_ConnectionList pole</span><span class="sxs-lookup"><span data-stu-id="69bd3-126">System.Net.ConnectionGroup.m\_ConnectionList Field</span></span>](../../../docs/framework/additional-apis/m_connectionlist.md) |
| [<span data-ttu-id="69bd3-127">System.Net.HttpWebRequest. \_HttpResponse pole</span><span class="sxs-lookup"><span data-stu-id="69bd3-127">System.Net.HttpWebRequest.\_HttpResponse Field</span></span>](../../../docs/framework/additional-apis/_httpresponse.md) |
| [<span data-ttu-id="69bd3-128">System.Net.HttpWebRequest. \_AutoRedirects pole</span><span class="sxs-lookup"><span data-stu-id="69bd3-128">System.Net.HttpWebRequest.\_AutoRedirects Field</span></span>](../../../docs/framework/additional-apis/_autoredirects.md) |
| [<span data-ttu-id="69bd3-129">System.Net.ServicePoint.m\_ConnectionGroupList pole</span><span class="sxs-lookup"><span data-stu-id="69bd3-129">System.Net.ServicePoint.m\_ConnectionGroupList Field</span></span>](../../../docs/framework/additional-apis/m_connectiongrouplist.md) |
| [<span data-ttu-id="69bd3-130">System.Net.ServicePointManager.s\_ServicePointTable pole</span><span class="sxs-lookup"><span data-stu-id="69bd3-130">System.Net.ServicePointManager.s\_ServicePointTable Field</span></span>](../../../docs/framework/additional-apis/s_servicepointtable.md) |
| [<span data-ttu-id="69bd3-131">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes pole</span><span class="sxs-lookup"><span data-stu-id="69bd3-131">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field</span></span>](../../../docs/framework/additional-apis/s-isdebuggercheckdisabledfortestpurposes-field.md) |
| [<span data-ttu-id="69bd3-132">System.Windows.Forms.Design.DataMemberFieldEditor – třída</span><span class="sxs-lookup"><span data-stu-id="69bd3-132">System.Windows.Forms.Design.DataMemberFieldEditor Class</span></span>](../../../docs/framework/additional-apis/datamemberfieldeditor-class.md) |
| [<span data-ttu-id="69bd3-133">System.Windows.Forms.Design.DataMemberListEditor – třída</span><span class="sxs-lookup"><span data-stu-id="69bd3-133">System.Windows.Forms.Design.DataMemberListEditor Class</span></span>](../../../docs/framework/additional-apis/datamemberlisteditor-class.md) |
  
## <a name="see-also"></a><span data-ttu-id="69bd3-134">Viz také</span><span class="sxs-lookup"><span data-stu-id="69bd3-134">See also</span></span>

[<span data-ttu-id="69bd3-135">Rozhraní .NET Framework a Out-of-Band verze</span><span class="sxs-lookup"><span data-stu-id="69bd3-135">The .NET Framework and Out-of-Band Releases</span></span>](../../../docs/framework/get-started/the-net-framework-and-out-of-band-releases.md)
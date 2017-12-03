---
title: "Zařazování dat se spoluprací COM"
ms.custom: 
ms.date: 09/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- COM interop, data marshaling
- marshaling data, COM interop
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2def27790a1727bda524b8c14a93f7b78127a569
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="marshaling-data-with-com-interop"></a><span data-ttu-id="66d0e-102">Zařazování dat se spoluprací COM</span><span class="sxs-lookup"><span data-stu-id="66d0e-102">Marshaling Data with COM Interop</span></span>
<span data-ttu-id="66d0e-103">Zprostředkovatel komunikace s objekty COM poskytuje podporu pro používání objektů COM ze spravovaného kódu i vystavení spravovaných objektů modelu COM.</span><span class="sxs-lookup"><span data-stu-id="66d0e-103">COM interop provides support for both using COM objects from managed code and exposing managed objects to COM.</span></span> <span data-ttu-id="66d0e-104">Podpora zařazování dat do a z modelu COM je rozsáhlá a poskytuje téměř vždy správné chování zařazování.</span><span class="sxs-lookup"><span data-stu-id="66d0e-104">Support for marshaling data to and from COM is extensive and almost always provides the correct marshaling behavior.</span></span>  
  
 <span data-ttu-id="66d0e-105">[!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] Zahrnuje následující nástroje zprostředkovatele komunikace s objekty COM:</span><span class="sxs-lookup"><span data-stu-id="66d0e-105">The [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] includes the following COM interop tools:</span></span>  
  
-   <span data-ttu-id="66d0e-106">[Zadejte Importér knihovny (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md), která převede sestavení vzájemné spolupráce COM knihovny typů.</span><span class="sxs-lookup"><span data-stu-id="66d0e-106">[Type Library Importer (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md), which converts a COM type library to an interop assembly.</span></span> <span data-ttu-id="66d0e-107">Zprostředkovatel komunikace s objekty zařazování služby z tohoto sestavení generuje obálky, které provádějí dat – zařazování mezi spravovanými a nespravovanými paměti.</span><span class="sxs-lookup"><span data-stu-id="66d0e-107">From this assembly, the interop marshaling service generates wrappers that perform data marshaling between managed and unmanaged memory.</span></span>  
  
-   <span data-ttu-id="66d0e-108">[Zadejte Export knihovny (Tlbexp.exe)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), který vytváří knihovnu COM typu ze sestavení a generuje obálky, který provádí zařazování při volání metody.</span><span class="sxs-lookup"><span data-stu-id="66d0e-108">[Type Library Exporter (Tlbexp.exe)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), which produces a COM type library from an assembly and generates a wrapper that performs marshaling during method calls.</span></span>  
  
 <span data-ttu-id="66d0e-109">V následujících částech propojit témata, která popisují procesy pro přizpůsobení spolupráce obálky při můžete (nebo musí) zadáte vláken s informací o další typu.</span><span class="sxs-lookup"><span data-stu-id="66d0e-109">The following sections link to topics that describe the processes for customizing interop wrappers when you can (or must) supply the marshaler with additional type information.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="66d0e-110">V tomto oddílu</span><span class="sxs-lookup"><span data-stu-id="66d0e-110">In This Section</span></span>  
<span data-ttu-id="66d0e-111">[Postupy: ruční vytváření obálek](how-to-create-wrappers-manually.md) </span><span class="sxs-lookup"><span data-stu-id="66d0e-111">[How to: Create Wrappers Manually](how-to-create-wrappers-manually.md) </span></span>  
<span data-ttu-id="66d0e-112">Popisuje, jak ručně vytvořit obálky COM v spravované zdrojového kódu.</span><span class="sxs-lookup"><span data-stu-id="66d0e-112">Describes how to create a COM wrapper manually in managed source code.</span></span> 
 
 [<span data-ttu-id="66d0e-113">Postupy: migrace spravovaného kódu DCOM do WCF</span><span class="sxs-lookup"><span data-stu-id="66d0e-113">How to: Migrate Managed-Code DCOM to WCF</span></span>](../../../docs/framework/interop/how-to-migrate-managed-code-dcom-to-wcf.md)  
 <span data-ttu-id="66d0e-114">Popisuje postup migrace spravovaného kódu DCOM do WCF nejbezpečnější řešení.</span><span class="sxs-lookup"><span data-stu-id="66d0e-114">Describes how to migrate managed DCOM code to WCF for the most secure solution.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="66d0e-115">Související oddíly</span><span class="sxs-lookup"><span data-stu-id="66d0e-115">Related Sections</span></span>  
 <span data-ttu-id="66d0e-116">[COM datové typy](https://msdn.microsoft.com/en-us/library/sak564ww(v=vs.100).aspx)</span><span class="sxs-lookup"><span data-stu-id="66d0e-116">[COM Data Types](https://msdn.microsoft.com/en-us/library/sak564ww(v=vs.100).aspx)</span></span>  
 <span data-ttu-id="66d0e-117">Poskytuje odpovídající spravovanými a nespravovanými datové typy.</span><span class="sxs-lookup"><span data-stu-id="66d0e-117">Provides corresponding managed and unmanaged data types.</span></span>  
  
 <span data-ttu-id="66d0e-118">[COM – obálky s možností přizpůsobení](https://msdn.microsoft.com/en-us/library/3bwc828w(v=vs.100).aspx)</span><span class="sxs-lookup"><span data-stu-id="66d0e-118">[Customizing COM Callable Wrappers](https://msdn.microsoft.com/en-us/library/3bwc828w(v=vs.100).aspx)</span></span>  
 <span data-ttu-id="66d0e-119">Popisuje, jak explicitně zařazování datové typy pomocí <xref:System.Runtime.InteropServices.MarshalAsAttribute> atribut v době návrhu.</span><span class="sxs-lookup"><span data-stu-id="66d0e-119">Describes how to explicitly marshal data types using the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute at design time.</span></span>  
  
 <span data-ttu-id="66d0e-120">[Běhové obálky s možností přizpůsobení](https://msdn.microsoft.com/en-us/library/e753eftz(v=vs.100).aspx)</span><span class="sxs-lookup"><span data-stu-id="66d0e-120">[Customizing Runtime Callable Wrappers](https://msdn.microsoft.com/en-us/library/e753eftz(v=vs.100).aspx)</span></span>  
 <span data-ttu-id="66d0e-121">Popisuje, jak upravit chování zařazování typy v sestavení spolupráce a jak definovat typy modelu COM ručně.</span><span class="sxs-lookup"><span data-stu-id="66d0e-121">Describes how to adjust the marshaling behavior of types in an interop assembly and how to define COM types manually.</span></span>  
  
 <span data-ttu-id="66d0e-122">[Interoperabilita modelů COM Upřesnit](https://msdn.microsoft.com/en-us/library/bd9cdfyx(v=vs.100).aspx)</span><span class="sxs-lookup"><span data-stu-id="66d0e-122">[Advanced COM Interoperability](https://msdn.microsoft.com/en-us/library/bd9cdfyx(v=vs.100).aspx)</span></span>  
 <span data-ttu-id="66d0e-123">Obsahuje odkazy na další informace o zahrnutí komponenty modelu COM do své aplikace rozhraní .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="66d0e-123">Provides links to more information about incorporating COM components into your .NET Framework application.</span></span>  
  
 <span data-ttu-id="66d0e-124">[Sestavení na typ souhrn konverze knihovny](https://msdn.microsoft.com/en-us/library/xk1120c3(v=vs.100).aspx)</span><span class="sxs-lookup"><span data-stu-id="66d0e-124">[Assembly to Type Library Conversion Summary](https://msdn.microsoft.com/en-us/library/xk1120c3(v=vs.100).aspx)</span></span>  
 <span data-ttu-id="66d0e-125">Popisuje sestavení na typ procesu převodu export knihovny.</span><span class="sxs-lookup"><span data-stu-id="66d0e-125">Describes the assembly to type library export conversion process.</span></span>  
  
 <span data-ttu-id="66d0e-126">[Knihovny typů pro souhrn konverze sestavení](https://msdn.microsoft.com/en-us/library/k83zzh38(v=vs.100).aspx)</span><span class="sxs-lookup"><span data-stu-id="66d0e-126">[Type Library to Assembly Conversion Summary](https://msdn.microsoft.com/en-us/library/k83zzh38(v=vs.100).aspx)</span></span>  
 <span data-ttu-id="66d0e-127">Popisuje knihovny typů pro převod importu sestavení.</span><span class="sxs-lookup"><span data-stu-id="66d0e-127">Describes the type library to assembly import conversion process.</span></span>  
  
 <span data-ttu-id="66d0e-128">[Spolupráce pomocí obecných typů](https://msdn.microsoft.com/en-us/library/ms229590(v=vs.100).aspx)</span><span class="sxs-lookup"><span data-stu-id="66d0e-128">[Interoperating Using Generic Types](https://msdn.microsoft.com/en-us/library/ms229590(v=vs.100).aspx)</span></span>  
 <span data-ttu-id="66d0e-129">Popisuje akce, které jsou podporovány při použití obecných typů pro interoperabilita modelů COM.</span><span class="sxs-lookup"><span data-stu-id="66d0e-129">Describes which actions are supported when using generic types for COM interoperability.</span></span>
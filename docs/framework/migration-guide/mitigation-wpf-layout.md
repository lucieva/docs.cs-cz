---
title: "Omezení rizik: Rozložení WPF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 805ffd7f-8d1e-427e-a648-601ca8ec37a5
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d3ba5ac792169cc076f9621025f35444281cec6e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="mitigation-wpf-layout"></a><span data-ttu-id="a630b-102">Omezení rizik: Rozložení WPF</span><span class="sxs-lookup"><span data-stu-id="a630b-102">Mitigation: WPF Layout</span></span>
<span data-ttu-id="a630b-103">Rozložení ovládacích prvků WPF můžou trochu změnit.</span><span class="sxs-lookup"><span data-stu-id="a630b-103">The layout of WPF controls can change slightly.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="a630b-104">Dopad</span><span class="sxs-lookup"><span data-stu-id="a630b-104">Impact</span></span>  
 <span data-ttu-id="a630b-105">V důsledku této změny:</span><span class="sxs-lookup"><span data-stu-id="a630b-105">As a result of this change:</span></span>  
  
-   <span data-ttu-id="a630b-106">Šířky nebo výšky elementů může zvětšit nebo zmenšit o maximálně jeden bod.</span><span class="sxs-lookup"><span data-stu-id="a630b-106">The width or height of elements may grow or shrink by at most one pixel.</span></span>  
  
-   <span data-ttu-id="a630b-107">Umístění objektu můžete přesunout tak, že maximálně jeden pixel.</span><span class="sxs-lookup"><span data-stu-id="a630b-107">The placement of an object can move by at most one pixel.</span></span>  
  
-   <span data-ttu-id="a630b-108">Zarovnaný elementy lze vypnout center o maximálně jeden bod vodorovně nebo svisle.</span><span class="sxs-lookup"><span data-stu-id="a630b-108">Centered elements can be vertically or horizontally off center by at most one pixel.</span></span>  
  
 <span data-ttu-id="a630b-109">Ve výchozím nastavení je toto nové rozložení povolená jenom pro aplikace, které cílí na rozhraní .NET Framework 4.6.</span><span class="sxs-lookup"><span data-stu-id="a630b-109">By default, this new layout is enabled only for apps that target the .NET Framework 4.6.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="a630b-110">Zmírnění</span><span class="sxs-lookup"><span data-stu-id="a630b-110">Mitigation</span></span>  
 <span data-ttu-id="a630b-111">Vzhledem k tomu, že tato změna se obvykle eliminovat výstřižek pravé nebo dolní části ovládacích prvků WPF v vysoké DPIs, aplikace, které cílí na starší verze rozhraní .NET Framework, ale jsou spuštěny v rozhraní .NET Framework 4.6 se můžete rozhodnout do této nové chování přidáním následující řádek na `<runtime>` v souboru app.config:</span><span class="sxs-lookup"><span data-stu-id="a630b-111">Since this modification tends to eliminate clipping of the right or bottom of WPF controls at high DPIs, apps that target earlier versions of the .NET Framework but are running on the .NET Framework 4.6 can opt into this new behavior by adding the following line to the `<runtime>` section of the app.config file:</span></span>  
  
```xml  
<AppContextSwitchOverrides value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false" />  
```  
  
 <span data-ttu-id="a630b-112">Aplikace, které cílí na rozhraní .NET Framework 4.6 ale ovládacích prvků WPF k vykreslení pomocí předchozí algoritmus rozložení, aby se to lze provést přidáním následující řádek do `<runtime>` v souboru app.config:</span><span class="sxs-lookup"><span data-stu-id="a630b-112">Apps that target the .NET Framework 4.6 but want WPF controls to render using the previous layout algorithm can do so by adding the following line to the  `<runtime>` section of the app.config file:</span></span>  
  
```xml  
<AppContextSwitchOverrides value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=true" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="a630b-113">Viz také</span><span class="sxs-lookup"><span data-stu-id="a630b-113">See Also</span></span>  
 [<span data-ttu-id="a630b-114">Odlišnosti ve změnách cílení</span><span class="sxs-lookup"><span data-stu-id="a630b-114">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)
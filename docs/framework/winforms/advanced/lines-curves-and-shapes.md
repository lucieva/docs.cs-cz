---
title: "Čáry, křivky a obrazce"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- shapes [Windows Forms], filling
- splines [Windows Forms], drawing
- shapes. drawing
- lines [Windows Forms], drawing
- curves [Windows Forms], drawing
ms.assetid: ace6e8d4-4e94-486b-9681-758a6667dc7f
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2caa77285ebe327adc690b26baeb58aa800627fb
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/22/2017
---
# <a name="lines-curves-and-shapes"></a><span data-ttu-id="d5c59-102">Čáry, křivky a obrazce</span><span class="sxs-lookup"><span data-stu-id="d5c59-102">Lines, Curves, and Shapes</span></span>
<span data-ttu-id="d5c59-103">Část vektorové grafiky [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] se používá k kreslení čar, kreslení křivek a k vykreslení a vyplnění obrazců.</span><span class="sxs-lookup"><span data-stu-id="d5c59-103">The vector graphics portion of [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] is used to draw lines, draw curves, and to draw and fill shapes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d5c59-104">V tomto oddílu</span><span class="sxs-lookup"><span data-stu-id="d5c59-104">In This Section</span></span>  
 [<span data-ttu-id="d5c59-105">Přehled vektorové grafiky</span><span class="sxs-lookup"><span data-stu-id="d5c59-105">Vector Graphics Overview</span></span>](../../../../docs/framework/winforms/advanced/vector-graphics-overview.md)  
 <span data-ttu-id="d5c59-106">Popisuje vektorová grafika.</span><span class="sxs-lookup"><span data-stu-id="d5c59-106">Discusses vector graphics.</span></span>  
  
 [<span data-ttu-id="d5c59-107">Pera, čáry a obdélníky v GDI +</span><span class="sxs-lookup"><span data-stu-id="d5c59-107">Pens, Lines, and Rectangles in GDI+</span></span>](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)  
 <span data-ttu-id="d5c59-108">Popisuje, kreslení čáry a obdélníky.</span><span class="sxs-lookup"><span data-stu-id="d5c59-108">Discusses drawing lines and rectangles.</span></span>  
  
 [<span data-ttu-id="d5c59-109">Elipsy a oblouky v rozhraní GDI +</span><span class="sxs-lookup"><span data-stu-id="d5c59-109">Ellipses and Arcs in GDI+</span></span>](../../../../docs/framework/winforms/advanced/ellipses-and-arcs-in-gdi.md)  
 <span data-ttu-id="d5c59-110">Definuje oblouky a tři tečky a identifikuje třídy potřebné k vykreslení je.</span><span class="sxs-lookup"><span data-stu-id="d5c59-110">Defines arcs and ellipses and identifies the classes needed to draw them.</span></span>  
  
 [<span data-ttu-id="d5c59-111">Mnohoúhelníky v GDI +</span><span class="sxs-lookup"><span data-stu-id="d5c59-111">Polygons in GDI+</span></span>](../../../../docs/framework/winforms/advanced/polygons-in-gdi.md)  
 <span data-ttu-id="d5c59-112">Definuje mnohoúhelníky a identifikuje třídy potřebné k vykreslení je.</span><span class="sxs-lookup"><span data-stu-id="d5c59-112">Defines polygons and identifies the classes needed to draw them.</span></span>  
  
 [<span data-ttu-id="d5c59-113">Základní křivky v GDI +</span><span class="sxs-lookup"><span data-stu-id="d5c59-113">Cardinal Splines in GDI+</span></span>](../../../../docs/framework/winforms/advanced/cardinal-splines-in-gdi.md)  
 <span data-ttu-id="d5c59-114">Definuje základní křivky vyhlazení a identifikuje třídy potřebné k vykreslení je.</span><span class="sxs-lookup"><span data-stu-id="d5c59-114">Defines cardinal splines and identifies the classes needed to draw them.</span></span>  
  
 [<span data-ttu-id="d5c59-115">Bézierovy křivky v GDI +</span><span class="sxs-lookup"><span data-stu-id="d5c59-115">Bézier Splines in GDI+</span></span>](../../../../docs/framework/winforms/advanced/bezier-splines-in-gdi.md)  
 <span data-ttu-id="d5c59-116">Definuje Bézierovy křivky a identifikuje třídy potřebné k vykreslení je.</span><span class="sxs-lookup"><span data-stu-id="d5c59-116">Defines Bezier splines and identifies the classes needed to draw them.</span></span>  
  
 [<span data-ttu-id="d5c59-117">Cesty grafiky v GDI +</span><span class="sxs-lookup"><span data-stu-id="d5c59-117">Graphics Paths in GDI+</span></span>](../../../../docs/framework/winforms/advanced/graphics-paths-in-gdi.md)  
 <span data-ttu-id="d5c59-118">Popisuje cesty a postup vytvoření a jejich vykreslení.</span><span class="sxs-lookup"><span data-stu-id="d5c59-118">Describes paths and how to create and draw them.</span></span>  
  
 [<span data-ttu-id="d5c59-119">Štětce a vyplněné obrazce v GDI +</span><span class="sxs-lookup"><span data-stu-id="d5c59-119">Brushes and Filled Shapes in GDI+</span></span>](../../../../docs/framework/winforms/advanced/brushes-and-filled-shapes-in-gdi.md)  
 <span data-ttu-id="d5c59-120">Popisuje typy štětce a jejich použití.</span><span class="sxs-lookup"><span data-stu-id="d5c59-120">Describes brush types and how to use them.</span></span>  
  
 [<span data-ttu-id="d5c59-121">Otevřené a uzavřené křivky v GDI +</span><span class="sxs-lookup"><span data-stu-id="d5c59-121">Open and Closed Curves in GDI+</span></span>](../../../../docs/framework/winforms/advanced/open-and-closed-curves-in-gdi.md)  
 <span data-ttu-id="d5c59-122">Definuje otevřené a uzavřené křivky a jak kreslení a zadejte je.</span><span class="sxs-lookup"><span data-stu-id="d5c59-122">Defines open and closed curves and how to draw and fill them.</span></span>  
  
 [<span data-ttu-id="d5c59-123">Oblasti v GDI +</span><span class="sxs-lookup"><span data-stu-id="d5c59-123">Regions in GDI+</span></span>](../../../../docs/framework/winforms/advanced/regions-in-gdi.md)  
 <span data-ttu-id="d5c59-124">Popisuje metody přidružené k oblasti.</span><span class="sxs-lookup"><span data-stu-id="d5c59-124">Describes the methods associated with regions.</span></span>  
  
 [<span data-ttu-id="d5c59-125">Omezení kreslicí plochy v GDI +</span><span class="sxs-lookup"><span data-stu-id="d5c59-125">Restricting the Drawing Surface in GDI+</span></span>](../../../../docs/framework/winforms/advanced/restricting-the-drawing-surface-in-gdi.md)  
 <span data-ttu-id="d5c59-126">Popisuje výstřižek a způsobu jeho použití.</span><span class="sxs-lookup"><span data-stu-id="d5c59-126">Describes clipping and how to use it.</span></span>  
  
 [<span data-ttu-id="d5c59-127">Vyhlazení u čar a křivek</span><span class="sxs-lookup"><span data-stu-id="d5c59-127">Antialiasing with Lines and Curves</span></span>](../../../../docs/framework/winforms/advanced/antialiasing-with-lines-and-curves.md)  
 <span data-ttu-id="d5c59-128">Definuje vyhlazení a způsob použití vyhlazení při kreslení čar a křivek.</span><span class="sxs-lookup"><span data-stu-id="d5c59-128">Defines antialiasing and how use antialiasing when drawing lines and curves.</span></span>
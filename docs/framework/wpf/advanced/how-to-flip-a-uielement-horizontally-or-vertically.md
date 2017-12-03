---
title: "Postupy: Překlopení prvku UIElement vodorovně nebo svisle"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- flipping UIElements [WPF]
- UIElements [WPF], flipping
ms.assetid: 02c6730f-65c0-40d5-a553-4cb663721882
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 84d1360246141cfa565d669fff108e3e4db3ce33
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-flip-a-uielement-horizontally-or-vertically"></a><span data-ttu-id="af0c1-102">Postupy: Překlopení prvku UIElement vodorovně nebo svisle</span><span class="sxs-lookup"><span data-stu-id="af0c1-102">How to: Flip a UIElement Horizontally or Vertically</span></span>
<span data-ttu-id="af0c1-103">Tento příklad ukazuje, jak používat <xref:System.Windows.Media.ScaleTransform> k převrácení <xref:System.Windows.UIElement> vodorovně nebo svisle.</span><span class="sxs-lookup"><span data-stu-id="af0c1-103">This example shows how to use a <xref:System.Windows.Media.ScaleTransform> to flip a <xref:System.Windows.UIElement> horizontally or vertically.</span></span> <span data-ttu-id="af0c1-104">V tomto příkladu <xref:System.Windows.Controls.Button> ovládací prvek (typ <xref:System.Windows.UIElement>) je obráceně použitím <xref:System.Windows.Media.ScaleTransform> k jeho <xref:System.Windows.UIElement.RenderTransform%2A> vlastnost.</span><span class="sxs-lookup"><span data-stu-id="af0c1-104">In this example, a <xref:System.Windows.Controls.Button> control (a type of <xref:System.Windows.UIElement>) is flipped by applying a <xref:System.Windows.Media.ScaleTransform> to its <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="af0c1-105">Příklad</span><span class="sxs-lookup"><span data-stu-id="af0c1-105">Example</span></span>  
 <span data-ttu-id="af0c1-106">Následující obrázek znázorňuje tlačítko k převrácení.</span><span class="sxs-lookup"><span data-stu-id="af0c1-106">The following illustration shows the button to flip.</span></span>  
  
 <span data-ttu-id="af0c1-107">![Tlačítko s žádná transformace](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonflipbeforeflip.gif "graphicsmm_buttonflipbeforeflip")</span><span class="sxs-lookup"><span data-stu-id="af0c1-107">![A button with no transform](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonflipbeforeflip.gif "graphicsmm_buttonflipbeforeflip")</span></span>  
<span data-ttu-id="af0c1-108">Prvků uživatelského rozhraní k převrácení</span><span class="sxs-lookup"><span data-stu-id="af0c1-108">The UIElement to flip</span></span>  
  
 <span data-ttu-id="af0c1-109">Následující zobrazuje kód, který vytvoří tlačítko.</span><span class="sxs-lookup"><span data-stu-id="af0c1-109">The following shows the code that creates the button.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMButtonWithoutFlip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmbuttonwithoutflip)]  
  
## <a name="example"></a><span data-ttu-id="af0c1-110">Příklad</span><span class="sxs-lookup"><span data-stu-id="af0c1-110">Example</span></span>  
 <span data-ttu-id="af0c1-111">Chcete-li na tlačítko Překlopit vodorovně, vytvořte <xref:System.Windows.Media.ScaleTransform> a nastavit jeho <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> vlastnost na hodnotu -1.</span><span class="sxs-lookup"><span data-stu-id="af0c1-111">To flip the button horizontally, create a <xref:System.Windows.Media.ScaleTransform> and set its <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> property to -1.</span></span> <span data-ttu-id="af0c1-112">Použít <xref:System.Windows.Media.ScaleTransform> na tlačítko <xref:System.Windows.UIElement.RenderTransform%2A> vlastnost.</span><span class="sxs-lookup"><span data-stu-id="af0c1-112">Apply the <xref:System.Windows.Media.ScaleTransform> to the button's <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMFlipButtonExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmflipbuttonexample1)]  
  
 <span data-ttu-id="af0c1-113">![Tlačítko překlopení vodorovně o &#40; 0,0 &#41; ] (../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonfliphorizontalflip-displaced.gif "graphicsmm_buttonfliphorizontalflip_displaced")</span><span class="sxs-lookup"><span data-stu-id="af0c1-113">![A button flipped horizontally about &#40;0,0&#41;](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonfliphorizontalflip-displaced.gif "graphicsmm_buttonfliphorizontalflip_displaced")</span></span>  
<span data-ttu-id="af0c1-114">Tlačítko po použití metody ScaleTransform</span><span class="sxs-lookup"><span data-stu-id="af0c1-114">The button after applying the ScaleTransform</span></span>  
  
## <a name="example"></a><span data-ttu-id="af0c1-115">Příklad</span><span class="sxs-lookup"><span data-stu-id="af0c1-115">Example</span></span>  
 <span data-ttu-id="af0c1-116">Jak je vidět na předchozím obrázku, tlačítko byl obráceně, ale také byl přesunut.</span><span class="sxs-lookup"><span data-stu-id="af0c1-116">As you can see from the previous illustration, the button was flipped, but it was also moved.</span></span> <span data-ttu-id="af0c1-117">Je to způsobeno tlačítko byl obráceně z levého horního rohu.</span><span class="sxs-lookup"><span data-stu-id="af0c1-117">That's because the button was flipped from its top left corner.</span></span> <span data-ttu-id="af0c1-118">K převrácení tlačítko na místě, kterou chcete použít <xref:System.Windows.Media.ScaleTransform> jeho Center, ne jeho rohu.</span><span class="sxs-lookup"><span data-stu-id="af0c1-118">To flip the button in place, you want to apply the <xref:System.Windows.Media.ScaleTransform> to its center, not its corner.</span></span> <span data-ttu-id="af0c1-119">Snadný způsob, jak použít <xref:System.Windows.Media.ScaleTransform> tlačítka center je nastaven na tlačítko <xref:System.Windows.UIElement.RenderTransformOrigin%2A> vlastnost 0,5, 0,5.</span><span class="sxs-lookup"><span data-stu-id="af0c1-119">An easy way to apply the <xref:System.Windows.Media.ScaleTransform> to the buttons center is to set the button's <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property to 0.5, 0.5.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMFlipButtonExample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmflipbuttonexample2)]  
  
 <span data-ttu-id="af0c1-120">![Tlačítko překlopení vodorovně o jeho center](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonfliphorizontalflip-inplace.gif "graphicsmm_buttonfliphorizontalflip_inplace")</span><span class="sxs-lookup"><span data-stu-id="af0c1-120">![A button flipped horizontally about its center](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonfliphorizontalflip-inplace.gif "graphicsmm_buttonfliphorizontalflip_inplace")</span></span>  
<span data-ttu-id="af0c1-121">Tlačítko s RenderTransformOrigin 0,5, 0,5</span><span class="sxs-lookup"><span data-stu-id="af0c1-121">The button with a RenderTransformOrigin of 0.5, 0.5</span></span>  
  
## <a name="example"></a><span data-ttu-id="af0c1-122">Příklad</span><span class="sxs-lookup"><span data-stu-id="af0c1-122">Example</span></span>  
 <span data-ttu-id="af0c1-123">Chcete-li na tlačítko Překlopit svisle, nastavte <xref:System.Windows.Media.ScaleTransform> objektu <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> vlastnost místo jeho <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> vlastnost.</span><span class="sxs-lookup"><span data-stu-id="af0c1-123">To flip the button vertically, set the <xref:System.Windows.Media.ScaleTransform> object's <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> property instead of its <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> property.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMVerticalFlipButtonExample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmverticalflipbuttonexample2)]  
  
 <span data-ttu-id="af0c1-124">![Tlačítko překlopení svisle o jeho center](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonflipverticalflip-inplace.gif "graphicsmm_buttonflipverticalflip_inplace")</span><span class="sxs-lookup"><span data-stu-id="af0c1-124">![A button flipped vertically about its center](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonflipverticalflip-inplace.gif "graphicsmm_buttonflipverticalflip_inplace")</span></span>  
<span data-ttu-id="af0c1-125">Tlačítko svisle přetočený</span><span class="sxs-lookup"><span data-stu-id="af0c1-125">The vertically flipped button</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af0c1-126">Viz také</span><span class="sxs-lookup"><span data-stu-id="af0c1-126">See Also</span></span>  
 [<span data-ttu-id="af0c1-127">Transformuje – přehled</span><span class="sxs-lookup"><span data-stu-id="af0c1-127">Transforms Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
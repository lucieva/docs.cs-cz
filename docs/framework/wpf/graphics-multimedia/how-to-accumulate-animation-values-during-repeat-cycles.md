---
title: "Postupy: Kumulování hodnot animace při opakujících se cyklech"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- accumulating animation values across repeating cycles [WPF]
- animation [WPF], accumulating values across repeating cycles
ms.assetid: 548df369-c7cc-4dab-b569-08b95ced2e7e
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4abe19f4548ed41eb19ae4dffb37b832a7df71d2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-accumulate-animation-values-during-repeat-cycles"></a><span data-ttu-id="ea521-102">Postupy: Kumulování hodnot animace při opakujících se cyklech</span><span class="sxs-lookup"><span data-stu-id="ea521-102">How to: Accumulate Animation Values During Repeat Cycles</span></span>
<span data-ttu-id="ea521-103">Tento příklad ukazuje způsob použití <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> vlastnost hromadit hodnoty animace napříč opakovaných cyklů.</span><span class="sxs-lookup"><span data-stu-id="ea521-103">This example shows how to use the <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> property to accumulate animation values across repeating cycles.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ea521-104">Příklad</span><span class="sxs-lookup"><span data-stu-id="ea521-104">Example</span></span>  
 <span data-ttu-id="ea521-105">Použití <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> vlastnost hromadit základní hodnoty animace napříč opakovaných cyklů.</span><span class="sxs-lookup"><span data-stu-id="ea521-105">Use the <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> property to accumulate base values of an animation across repeating cycles.</span></span> <span data-ttu-id="ea521-106">Například pokud nastavíte animace opakování 9 časy (<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> = "9 x") a nastavte vlastnosti, která má animace 10 až 15 (z = 10 k = 15), vlastnost animuje od 10 do 15 první cyklu od 15 do 20 druhý cyklu , z 20 až 25 během třetí cyklu a tak dále.</span><span class="sxs-lookup"><span data-stu-id="ea521-106">For example, if you set an animation to repeat 9 times (<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> = "9x") and you set the property to animate between 10 and 15 (From = 10 To = 15), the property animates from 10 to 15 during the first cycle, from 15 to 20 during the second cycle, from 20 to 25 during the third cycle, and so on.</span></span> <span data-ttu-id="ea521-107">Proto každý cyklus animace používá koncovou hodnotu animace z předchozího cyklu animace jako svou základní hodnotu.</span><span class="sxs-lookup"><span data-stu-id="ea521-107">Hence, each animation cycle uses the ending animation value from the previous animation cycle as its base value.</span></span>  
  
 <span data-ttu-id="ea521-108">Můžete použít `IsCumulative` vlastnost nejzákladnější animace a většina klíčových snímků animace.</span><span class="sxs-lookup"><span data-stu-id="ea521-108">You can use the `IsCumulative` property with most basic animations and most key frame animations.</span></span> <span data-ttu-id="ea521-109">Další informace najdete v tématu [animace přehled](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) a [klíč rámce animací přehled](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ea521-109">For more information, see [Animation Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) and [Key-Frame Animations Overview](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).</span></span>  
  
 <span data-ttu-id="ea521-110">Následující příklad ukazuje toto chování animace šířku čtyři obdélníky.</span><span class="sxs-lookup"><span data-stu-id="ea521-110">The following example shows this behavior by animating the width of four rectangles.</span></span> <span data-ttu-id="ea521-111">Příklad:</span><span class="sxs-lookup"><span data-stu-id="ea521-111">The example:</span></span>  
  
-   <span data-ttu-id="ea521-112">Animuje první rámeček s <xref:System.Windows.Media.Animation.DoubleAnimation> a nastaví <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> vlastnost `true`.</span><span class="sxs-lookup"><span data-stu-id="ea521-112">Animates the first rectangle with <xref:System.Windows.Media.Animation.DoubleAnimation> and sets the <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> property to `true`.</span></span>  
  
-   <span data-ttu-id="ea521-113">Animuje druhý rámeček s <xref:System.Windows.Media.Animation.DoubleAnimation> a nastaví <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> vlastnost, která má výchozí hodnotu `false`.</span><span class="sxs-lookup"><span data-stu-id="ea521-113">Animates the second rectangle with <xref:System.Windows.Media.Animation.DoubleAnimation> and sets the <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> property to the default value of `false`.</span></span>  
  
-   <span data-ttu-id="ea521-114">Animuje třetí rámeček s <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> a nastaví <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> vlastnost `true`.</span><span class="sxs-lookup"><span data-stu-id="ea521-114">Animates the third rectangle with <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> and sets the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> property to `true`.</span></span>  
  
-   <span data-ttu-id="ea521-115">Animuje poslední rámeček s <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> a nastaví <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> vlastnost `false`.</span><span class="sxs-lookup"><span data-stu-id="ea521-115">Animates the last rectangle with <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> and sets the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> property to `false`.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#IsCumulativeWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsCumulativeExample.xaml#iscumulativewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="ea521-116">Viz také</span><span class="sxs-lookup"><span data-stu-id="ea521-116">See Also</span></span>  
 [<span data-ttu-id="ea521-117">Přidejte hodnotu animace výstup do animace počáteční hodnota</span><span class="sxs-lookup"><span data-stu-id="ea521-117">Add an Animation Output Value to an Animation Starting Value</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-add-an-animation-output-value-to-an-animation-starting-value.md)  
 [<span data-ttu-id="ea521-118">Opakování animace</span><span class="sxs-lookup"><span data-stu-id="ea521-118">Repeat an Animation</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-repeat-an-animation.md)  
 [<span data-ttu-id="ea521-119">Animace – přehled</span><span class="sxs-lookup"><span data-stu-id="ea521-119">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="ea521-120">Přehled animací jednotlivých klíč</span><span class="sxs-lookup"><span data-stu-id="ea521-120">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="ea521-121">Postupy: témata</span><span class="sxs-lookup"><span data-stu-id="ea521-121">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
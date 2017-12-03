---
title: "Postupy: Kreslení neprůhledných a poloprůhledných čar"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drawing [Windows Forms], lines
- transparency [Windows Forms], lines
- lines [Windows Forms], drawing alpha blended
- alpha blending [Windows Forms], drawing lines
ms.assetid: 8f2508af-f495-4223-b5cc-646cbbb520eb
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ea65fd836a6e6fc00472f6139a0700ea859545cc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-opaque-and-semitransparent-lines"></a><span data-ttu-id="701ec-102">Postupy: Kreslení neprůhledných a poloprůhledných čar</span><span class="sxs-lookup"><span data-stu-id="701ec-102">How to: Draw Opaque and Semitransparent Lines</span></span>
<span data-ttu-id="701ec-103">Při nakreslení čáry, je nutné předat <xref:System.Drawing.Pen> do objektu <xref:System.Drawing.Graphics.DrawLine%2A> metodu <xref:System.Drawing.Graphics> třídy.</span><span class="sxs-lookup"><span data-stu-id="701ec-103">When you draw a line, you must pass a <xref:System.Drawing.Pen> object to the <xref:System.Drawing.Graphics.DrawLine%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="701ec-104">Jeden z parametrů <xref:System.Drawing.Pen.%23ctor%2A> konstruktor je <xref:System.Drawing.Color> objektu.</span><span class="sxs-lookup"><span data-stu-id="701ec-104">One of the parameters of the <xref:System.Drawing.Pen.%23ctor%2A> constructor is a <xref:System.Drawing.Color> object.</span></span> <span data-ttu-id="701ec-105">Kreslení neprůhledných řádku, nastavte komponentu alfa barvy na 255.</span><span class="sxs-lookup"><span data-stu-id="701ec-105">To draw an opaque line, set the alpha component of the color to 255.</span></span> <span data-ttu-id="701ec-106">Kreslení poloprůhledných čáry, nastavte na jakoukoli hodnotu od 1 do 254 komponentu alfa.</span><span class="sxs-lookup"><span data-stu-id="701ec-106">To draw a semitransparent line, set the alpha component to any value from 1 through 254.</span></span>  
  
 <span data-ttu-id="701ec-107">Při kreslení poloprůhledných řádku na pozadí, barvu čáry je smíšený s barvy pozadí.</span><span class="sxs-lookup"><span data-stu-id="701ec-107">When you draw a semitransparent line over a background, the color of the line is blended with the colors of the background.</span></span> <span data-ttu-id="701ec-108">Komponentu alfa Určuje, jak jsou kombinované barvy řádku a pozadí; hodnoty alfa téměř 0 umístěte další váhy barvy pozadí a hodnoty alfa téměř 255 umístit další váhy na barvu čáry.</span><span class="sxs-lookup"><span data-stu-id="701ec-108">The alpha component specifies how the line and background colors are mixed; alpha values near 0 place more weight on the background colors, and alpha values near 255 place more weight on the line color.</span></span>  
  
## <a name="example"></a><span data-ttu-id="701ec-109">Příklad</span><span class="sxs-lookup"><span data-stu-id="701ec-109">Example</span></span>  
 <span data-ttu-id="701ec-110">V následujícím příkladu nevykresluje rastrový obrázek a poté nakreslí tři řádky, které používají bitovou mapu jako pozadí.</span><span class="sxs-lookup"><span data-stu-id="701ec-110">The following example draws a bitmap and then draws three lines that use the bitmap as a background.</span></span> <span data-ttu-id="701ec-111">První řádek používá alfa součást 255, takže je plné krytí.</span><span class="sxs-lookup"><span data-stu-id="701ec-111">The first line uses an alpha component of 255, so it is opaque.</span></span> <span data-ttu-id="701ec-112">Druhý a třetí řádky použít alfa součást 128, tak, aby byly poloprůhledných; Zobrazí se obrázek pozadí prostřednictvím řádky.</span><span class="sxs-lookup"><span data-stu-id="701ec-112">The second and third lines use an alpha component of 128, so they are semitransparent; you can see the background image through the lines.</span></span> <span data-ttu-id="701ec-113">Příkaz, který nastaví <xref:System.Drawing.Graphics.CompositingQuality%2A> vlastnost způsobí, že prolnutí pro ve třetím řádku provést ve spojení s korekce gama.</span><span class="sxs-lookup"><span data-stu-id="701ec-113">The statement that sets the <xref:System.Drawing.Graphics.CompositingQuality%2A> property causes the blending for the third line to be done in conjunction with gamma correction.</span></span>  
  
 <span data-ttu-id="701ec-114">Následující obrázek znázorňuje výstup následující kód.</span><span class="sxs-lookup"><span data-stu-id="701ec-114">The following illustration shows the output of the following code.</span></span>  
  
 <span data-ttu-id="701ec-115">![Neprůhledných a poloprůhledných](../../../../docs/framework/winforms/advanced/media/compqualline.png "compqualline")</span><span class="sxs-lookup"><span data-stu-id="701ec-115">![Opaque and Semitransparent](../../../../docs/framework/winforms/advanced/media/compqualline.png "compqualline")</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.AlphaBlending#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="701ec-116">Probíhá kompilace kódu</span><span class="sxs-lookup"><span data-stu-id="701ec-116">Compiling the Code</span></span>  
 <span data-ttu-id="701ec-117">V předchozím příkladu je určen k použití s modelem Windows Forms a vyžaduje <xref:System.Windows.Forms.PaintEventArgs> `e`, což je parametr <xref:System.Windows.Forms.Control.Paint> obslužné rutiny události.</span><span class="sxs-lookup"><span data-stu-id="701ec-117">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="701ec-118">Viz také</span><span class="sxs-lookup"><span data-stu-id="701ec-118">See Also</span></span>  
 [<span data-ttu-id="701ec-119">Alfa míchání čar a výplní</span><span class="sxs-lookup"><span data-stu-id="701ec-119">Alpha Blending Lines and Fills</span></span>](../../../../docs/framework/winforms/advanced/alpha-blending-lines-and-fills.md)  
 [<span data-ttu-id="701ec-120">Postupy: poskytnout vlastní ovládací prvek průhledné pozadí</span><span class="sxs-lookup"><span data-stu-id="701ec-120">How to: Give Your Control a Transparent Background</span></span>](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md)  
 [<span data-ttu-id="701ec-121">Postupy: kreslení pomocí neprůhledných a poloprůhledných štětců</span><span class="sxs-lookup"><span data-stu-id="701ec-121">How to: Draw with Opaque and Semitransparent Brushes</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-with-opaque-and-semitransparent-brushes.md)
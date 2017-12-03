---
title: "Postupy: kreslení jedné B &#233; zier křivkový"
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
- Bezier splines [Windows Forms], drawing
- drawing [Windows Forms], Bezier splines
ms.assetid: f4f3fe30-f0a6-4743-ac91-11310cebea9f
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0ebdba9e01824cc764a6ab759da049add180ba83
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-a-single-b233zier-spline"></a><span data-ttu-id="8b8d0-102">Postupy: kreslení jedné B &#233; zier křivkový</span><span class="sxs-lookup"><span data-stu-id="8b8d0-102">How to: Draw a Single B&#233;zier Spline</span></span>
<span data-ttu-id="8b8d0-103">Bézierovy křivky je definována čtyři body: počáteční bod, dvě kontrolních bodů a koncový bod.</span><span class="sxs-lookup"><span data-stu-id="8b8d0-103">A Bézier spline is defined by four points: a start point, two control points, and an endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b8d0-104">Příklad</span><span class="sxs-lookup"><span data-stu-id="8b8d0-104">Example</span></span>  
 <span data-ttu-id="8b8d0-105">Následující příklad kreslení Bézierovy křivky se počáteční bod (10, 100) a koncového bodu (200, 100).</span><span class="sxs-lookup"><span data-stu-id="8b8d0-105">The following example draws a Bézier spline with start point (10, 100) and endpoint (200, 100).</span></span> <span data-ttu-id="8b8d0-106">Ovládací prvek body jsou (100, 10) a (150 150).</span><span class="sxs-lookup"><span data-stu-id="8b8d0-106">The control points are (100, 10) and (150, 150).</span></span>  
  
 <span data-ttu-id="8b8d0-107">Následující obrázek znázorňuje výsledné Bézierovy křivky společně s jeho počáteční bod, kontrolní body a koncového bodu.</span><span class="sxs-lookup"><span data-stu-id="8b8d0-107">The following illustration shows the resulting Bézier spline along with its start point, control points, and endpoint.</span></span> <span data-ttu-id="8b8d0-108">Na obrázku také ukazuje konvexní trup křivky, který je vytvořen propojením čtyři body s přímky mnohoúhelníku.</span><span class="sxs-lookup"><span data-stu-id="8b8d0-108">The illustration also shows the spline's convex hull, which is a polygon formed by connecting the four points with straight lines.</span></span>  
  
 <span data-ttu-id="8b8d0-109">![Bézierovy křivky](../../../../docs/framework/winforms/advanced/media/bezierspline1.png "BezierSpline1")</span><span class="sxs-lookup"><span data-stu-id="8b8d0-109">![Bezier Spline](../../../../docs/framework/winforms/advanced/media/bezierspline1.png "BezierSpline1")</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8b8d0-110">Probíhá kompilace kódu</span><span class="sxs-lookup"><span data-stu-id="8b8d0-110">Compiling the Code</span></span>  
 <span data-ttu-id="8b8d0-111">V předchozím příkladu je určen k použití s modelem Windows Forms a vyžaduje <xref:System.Windows.Forms.PaintEventArgs> `e`, což je parametr <xref:System.Windows.Forms.Control.Paint> obslužné rutiny události.</span><span class="sxs-lookup"><span data-stu-id="8b8d0-111">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b8d0-112">Viz také</span><span class="sxs-lookup"><span data-stu-id="8b8d0-112">See Also</span></span>  
 <xref:System.Drawing.Graphics.DrawBezier%2A>  
 [<span data-ttu-id="8b8d0-113">Bézierovy křivky v GDI +</span><span class="sxs-lookup"><span data-stu-id="8b8d0-113">Bézier Splines in GDI+</span></span>](../../../../docs/framework/winforms/advanced/bezier-splines-in-gdi.md)  
 [<span data-ttu-id="8b8d0-114">Postupy: kreslení sekvence Bézierových křivek</span><span class="sxs-lookup"><span data-stu-id="8b8d0-114">How to: Draw a Sequence of Bézier Splines</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-sequence-of-bezier-splines.md)
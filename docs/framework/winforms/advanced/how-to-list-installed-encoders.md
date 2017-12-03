---
title: "Postupy: Vypsání seznamu instalovaných kodérů"
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
- image codecs [Windows Forms], listing
- image encoders [Windows Forms], listing
ms.assetid: 49e8e4e9-7a67-42d9-86bf-08821cdc282e
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 70f913acb2620b5c01e1aec1f1eb98b041b82a59
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-list-installed-encoders"></a><span data-ttu-id="40f64-102">Postupy: Vypsání seznamu instalovaných kodérů</span><span class="sxs-lookup"><span data-stu-id="40f64-102">How to: List Installed Encoders</span></span>
<span data-ttu-id="40f64-103">Můžete zobrazit seznam kodérů dostupné v počítači, chcete-li zjistit, jestli vaše aplikace můžete uložit do formátu souboru z bitové kopie.</span><span class="sxs-lookup"><span data-stu-id="40f64-103">You may want to list the image encoders available on a computer, to determine whether your application can save to a particular image file format.</span></span> <span data-ttu-id="40f64-104"><xref:System.Drawing.Imaging.ImageCodecInfo> Třída poskytuje <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> statických metod, aby mohla určit, která image kodéry jsou k dispozici.</span><span class="sxs-lookup"><span data-stu-id="40f64-104">The <xref:System.Drawing.Imaging.ImageCodecInfo> class provides the <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> static methods so that you can determine which image encoders are available.</span></span> <span data-ttu-id="40f64-105"><xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A>Vrátí pole <xref:System.Drawing.Imaging.ImageCodecInfo> objekty.</span><span class="sxs-lookup"><span data-stu-id="40f64-105"><xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> returns an array of <xref:System.Drawing.Imaging.ImageCodecInfo> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="40f64-106">Příklad</span><span class="sxs-lookup"><span data-stu-id="40f64-106">Example</span></span>  
 <span data-ttu-id="40f64-107">Následující příklad kódu Vypíše seznam nainstalovaných kodéry a jejich hodnoty vlastností.</span><span class="sxs-lookup"><span data-stu-id="40f64-107">The following code example outputs the list of installed encoders and their property values.</span></span>  
  
 [!code-csharp[UsingImageEncodersDecoders#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#1)]
 [!code-vb[UsingImageEncodersDecoders#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="40f64-108">Probíhá kompilace kódu</span><span class="sxs-lookup"><span data-stu-id="40f64-108">Compiling the Code</span></span>  
 <span data-ttu-id="40f64-109">Tento příklad vyžaduje:</span><span class="sxs-lookup"><span data-stu-id="40f64-109">This example requires:</span></span>  
  
-   <span data-ttu-id="40f64-110">Aplikace Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="40f64-110">A Windows Forms application.</span></span>  
  
-   <span data-ttu-id="40f64-111">A <xref:System.Windows.Forms.PaintEventArgs>, což je parametr <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="40f64-111">A <xref:System.Windows.Forms.PaintEventArgs>, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40f64-112">Viz také</span><span class="sxs-lookup"><span data-stu-id="40f64-112">See Also</span></span>  
 [<span data-ttu-id="40f64-113">Postupy: vypsání seznamu instalovaných dekodérů</span><span class="sxs-lookup"><span data-stu-id="40f64-113">How to: List Installed Decoders</span></span>](../../../../docs/framework/winforms/advanced/how-to-list-installed-decoders.md)  
 [<span data-ttu-id="40f64-114">Použití kodérů a dekodérů ve spravovaném GDI +</span><span class="sxs-lookup"><span data-stu-id="40f64-114">Using Image Encoders and Decoders in Managed GDI+</span></span>](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)
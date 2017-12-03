---
title: "Postupy: Vykreslení obrázků pomocí GDI+"
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
- cpp
helpviewer_keywords:
- images [Windows Forms], creating
- GDI+, rendering existing images
ms.assetid: c128b79a-3e31-47d8-9e66-3470f570a056
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9c0b4c128667cab04ca8ed015b44dae60d11b474
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-render-images-with-gdi"></a><span data-ttu-id="e0522-102">Postupy: Vykreslení obrázků pomocí GDI+</span><span class="sxs-lookup"><span data-stu-id="e0522-102">How to: Render Images with GDI+</span></span>
<span data-ttu-id="e0522-103">Můžete použít [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] vykreslování obrázků, které existují jako soubory ve svých aplikacích.</span><span class="sxs-lookup"><span data-stu-id="e0522-103">You can use [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] to render images that exist as files in your applications.</span></span> <span data-ttu-id="e0522-104">To uděláte tak, že vytvoříte nový objekt <xref:System.Drawing.Image> – třída (například <xref:System.Drawing.Bitmap>), vytváření <xref:System.Drawing.Graphics> objektu, který odkazuje na kreslicí plochy, kterou chcete použít a volání <xref:System.Drawing.Graphics.DrawImage%2A> metodu <xref:System.Drawing.Graphics> objektu.</span><span class="sxs-lookup"><span data-stu-id="e0522-104">You do this by creating a new object of an <xref:System.Drawing.Image> class (such as <xref:System.Drawing.Bitmap>), creating a <xref:System.Drawing.Graphics> object that refers to the drawing surface you want to use, and calling the <xref:System.Drawing.Graphics.DrawImage%2A> method of the <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="e0522-105">Obrázek se vykresluje do kreslicí plochy reprezentována graphics – třída.</span><span class="sxs-lookup"><span data-stu-id="e0522-105">The image will be painted onto the drawing surface represented by the graphics class.</span></span> <span data-ttu-id="e0522-106">Můžete použít Editor obrázků můžete vytvářet a upravovat soubory obrázků v době návrhu a vykreslit pomocí [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] za běhu.</span><span class="sxs-lookup"><span data-stu-id="e0522-106">You can use the Image Editor to create and edit image files at design time, and render them with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] at run time.</span></span> <span data-ttu-id="e0522-107">Další informace najdete v tématu [Editor obrázků pro ikony](/cpp/windows/image-editor-for-icons).</span><span class="sxs-lookup"><span data-stu-id="e0522-107">For more information, see [Image Editor for Icons](/cpp/windows/image-editor-for-icons).</span></span>  
  
### <a name="to-render-an-image-with-gdi"></a><span data-ttu-id="e0522-108">K vykreslení bitovou kopii pomocí GDI +</span><span class="sxs-lookup"><span data-stu-id="e0522-108">To render an image with GDI+</span></span>  
  
1.  <span data-ttu-id="e0522-109">Vytvořte objekt reprezentující bitovou kopii, kterou chcete zobrazit.</span><span class="sxs-lookup"><span data-stu-id="e0522-109">Create an object representing the image you want to display.</span></span> <span data-ttu-id="e0522-110">Tento objekt musí být členem skupiny třídu, která dědí z <xref:System.Drawing.Image>, jako například <xref:System.Drawing.Bitmap> nebo <xref:System.Drawing.Imaging.Metafile>.</span><span class="sxs-lookup"><span data-stu-id="e0522-110">This object must be a member of a class that inherits from <xref:System.Drawing.Image>, such as <xref:System.Drawing.Bitmap> or <xref:System.Drawing.Imaging.Metafile>.</span></span> <span data-ttu-id="e0522-111">Je uveden příklad:</span><span class="sxs-lookup"><span data-stu-id="e0522-111">An example is shown:</span></span>  
  
    ```vb  
    ' Uses the System.Environment.GetFolderPath to get the path to the   
    ' current user's MyPictures folder.  
    Dim myBitmap as New Bitmap _  
       (System.Environment.GetFolderPath _  
          (System.Environment.SpecialFolder.MyPictures))  
    ```  
  
    ```csharp  
    // Uses the System.Environment.GetFolderPath to get the path to the   
    // current user's MyPictures folder.  
    Bitmap myBitmap = new Bitmap  
       (System.Environment.GetFolderPath  
          (System.Environment.SpecialFolder.MyPictures));  
    ```  
  
    ```cpp  
    // Uses the System.Environment.GetFolderPath to get the path to the   
    // current user's MyPictures folder.  
    Bitmap^ myBitmap = gcnew Bitmap  
       (System::Environment::GetFolderPath  
          (System::Environment::SpecialFolder::MyPictures));  
    ```  
  
2.  <span data-ttu-id="e0522-112">Vytvoření <xref:System.Drawing.Graphics> objekt, který reprezentuje kreslicí plochy, kterou chcete použít.</span><span class="sxs-lookup"><span data-stu-id="e0522-112">Create a <xref:System.Drawing.Graphics> object that represents the drawing surface you want to use.</span></span> <span data-ttu-id="e0522-113">Další informace najdete v tématu [postupy: vytváření grafických objektů pro kreslení](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md).</span><span class="sxs-lookup"><span data-stu-id="e0522-113">For more information, see [How to: Create Graphics Objects for Drawing](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md).</span></span>  
  
    ```vb  
    ' Creates a Graphics object that represents the drawing surface of   
    ' Button1.  
    Dim g as Graphics = Button1.CreateGraphics  
    ```  
  
    ```csharp  
    // Creates a Graphics object that represents the drawing surface of   
    // Button1.  
    Graphics g = Button1.CreateGraphics();  
    ```  
  
    ```cpp  
    // Creates a Graphics object that represents the drawing surface of   
    // Button1.  
    Graphics^ g = button1->CreateGraphics();  
    ```  
  
3.  <span data-ttu-id="e0522-114">Volání <xref:System.Drawing.Graphics.DrawImage%2A> objektu grafiky k vykreslení bitovou kopii.</span><span class="sxs-lookup"><span data-stu-id="e0522-114">Call the <xref:System.Drawing.Graphics.DrawImage%2A> of your graphics object to render the image.</span></span> <span data-ttu-id="e0522-115">Musíte zadat bitovou kopii, které se mají vykreslovat i souřadnice, kde má být vykreslen.</span><span class="sxs-lookup"><span data-stu-id="e0522-115">You must specify both the image to be drawn, and the coordinates where it is to be drawn.</span></span>  
  
    ```vb  
    g.DrawImage(myBitmap, 1, 1)  
    ```  
  
    ```csharp  
    g.DrawImage(myBitmap, 1, 1);  
    ```  
  
    ```cpp  
    g->DrawImage(myBitmap, 1, 1);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e0522-116">Viz také</span><span class="sxs-lookup"><span data-stu-id="e0522-116">See Also</span></span>  
 [<span data-ttu-id="e0522-117">Začínáme s programováním grafiky</span><span class="sxs-lookup"><span data-stu-id="e0522-117">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [<span data-ttu-id="e0522-118">Postupy: vytváření grafických objektů pro kreslení</span><span class="sxs-lookup"><span data-stu-id="e0522-118">How to: Create Graphics Objects for Drawing</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [<span data-ttu-id="e0522-119">Pera, čáry a obdélníky v GDI +</span><span class="sxs-lookup"><span data-stu-id="e0522-119">Pens, Lines, and Rectangles in GDI+</span></span>](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)  
 [<span data-ttu-id="e0522-120">Postupy: kreslení textu ve formuláři Windows</span><span class="sxs-lookup"><span data-stu-id="e0522-120">How to: Draw Text on a Windows Form</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-text-on-a-windows-form.md)  
 [<span data-ttu-id="e0522-121">Grafika a kreslení v systému Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e0522-121">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="e0522-122">Kreslení čar nebo uzavřených obrázků</span><span class="sxs-lookup"><span data-stu-id="e0522-122">Drawing Lines or Closed Figures</span></span>](/cpp/windows/drawing-lines-or-closed-figures-image-editor-for-icons)  
 [<span data-ttu-id="e0522-123">Editor obrázků pro ikony</span><span class="sxs-lookup"><span data-stu-id="e0522-123">Image Editor for Icons</span></span>](/cpp/windows/image-editor-for-icons)
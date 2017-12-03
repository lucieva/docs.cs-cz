---
title: "Vytvoření třídy Game1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 47932ce3-2ba5-476f-a26b-3ddfd5226f27
caps.latest.revision: "8"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 1e4fd15013f10667b397e010fff56b7bc6a0f641
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="creating-the-game1-class"></a><span data-ttu-id="2f7b1-102">Vytvoření třídy Game1</span><span class="sxs-lookup"><span data-stu-id="2f7b1-102">Creating the Game1 Class</span></span>
<span data-ttu-id="2f7b1-103">Jak se všechny projekty Microsoft XNA Game1 třída odvozená z [Microsoft.Xna.Framework.Game](http://msdn.microsoft.com/library/microsoft.xna.framework.game.aspx) třídy, která poskytuje základní grafické zařízení inicializace, herní logiku a generování kódu pro XNA hry.</span><span class="sxs-lookup"><span data-stu-id="2f7b1-103">As with all Microsoft XNA projects, the Game1 class derives from the [Microsoft.Xna.Framework.Game](http://msdn.microsoft.com/library/microsoft.xna.framework.game.aspx) class, which provides basic graphics device initialization, game logic, and rendering code for XNA games.</span></span> <span data-ttu-id="2f7b1-104">Třídy Game1 je docela jednoduchá, protože většinu práce v GamePiece a GamePieceCollection třídy.</span><span class="sxs-lookup"><span data-stu-id="2f7b1-104">The Game1 class is fairly simple because most of the work in done in the GamePiece and GamePieceCollection classes.</span></span>  
  
## <a name="creating-the-code"></a><span data-ttu-id="2f7b1-105">Vytváření kódu</span><span class="sxs-lookup"><span data-stu-id="2f7b1-105">Creating the Code</span></span>  
 <span data-ttu-id="2f7b1-106">Soukromé členy pro třídu obsahovat **GamePieceCollection** objekt pro uložení herní částí [GraphicsDeviceManager](http://msdn.microsoft.com/library/microsoft.xna.framework.graphicsdevicemanager.aspx) objekt a [SpriteBatch](http://msdn.microsoft.com/library/microsoft.xna.framework.graphics.spritebatch.aspx) objekt použitý k vykreslení herní částí.</span><span class="sxs-lookup"><span data-stu-id="2f7b1-106">The private members for the class consist of a **GamePieceCollection** object to hold the game pieces, a [GraphicsDeviceManager](http://msdn.microsoft.com/library/microsoft.xna.framework.graphicsdevicemanager.aspx) object, and a [SpriteBatch](http://msdn.microsoft.com/library/microsoft.xna.framework.graphics.spritebatch.aspx) object used to render game pieces.</span></span>  
  
 [!code-csharp[ManipulationXNA#_Game1_PrivateMembers](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_privatemembers)]  
  
 <span data-ttu-id="2f7b1-107">Během inicializace herní instalace těchto objektů.</span><span class="sxs-lookup"><span data-stu-id="2f7b1-107">During game initialization, these objects are instantiated.</span></span>  
  
 [!code-csharp[ManipulationXNA#_Game1_ConstructorInitialize](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_constructorinitialize)]  
  
 <span data-ttu-id="2f7b1-108">Když [LoadContent](http://msdn.microsoft.com/library/microsoft.xna.framework.game.loadcontent.aspx) metoda je volána, herní součásti jsou vytvořeny a přiřazeny **GamePieceCollection** objektu.</span><span class="sxs-lookup"><span data-stu-id="2f7b1-108">When the [LoadContent](http://msdn.microsoft.com/library/microsoft.xna.framework.game.loadcontent.aspx) method is called, the game pieces are created and assigned to the **GamePieceCollection** object.</span></span> <span data-ttu-id="2f7b1-109">Existují dva typy herní částí.</span><span class="sxs-lookup"><span data-stu-id="2f7b1-109">There are two types of game pieces.</span></span> <span data-ttu-id="2f7b1-110">Měřítko pro vytvořené se mírně změní, které existují některé menší a některé větší částí.</span><span class="sxs-lookup"><span data-stu-id="2f7b1-110">The scale factor for the pieces is changed slightly so that there are some smaller and some larger pieces.</span></span>  
  
 [!code-csharp[ManipulationXNA#_Game1_LoadContent](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_loadcontent)]  
  
 <span data-ttu-id="2f7b1-111">[Aktualizace](http://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) metoda je volána opakovaně rozhraním XNA Framework spuštěného příslušnou hru.</span><span class="sxs-lookup"><span data-stu-id="2f7b1-111">The [Update](http://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) method is called repeatedly by the XNA Framework while the game is running.</span></span> <span data-ttu-id="2f7b1-112">[Aktualizace](http://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) volání metod **ProcessInertia** a **UpdateFromMouse** metody na příslušnou hru část kolekce.</span><span class="sxs-lookup"><span data-stu-id="2f7b1-112">The [Update](http://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) method calls the **ProcessInertia** and the **UpdateFromMouse** methods on the game piece collection.</span></span> <span data-ttu-id="2f7b1-113">Tyto metody jsou popsané v [vytvoření třídy Gamepiececollection](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md).</span><span class="sxs-lookup"><span data-stu-id="2f7b1-113">These methods are described in [Creating the GamePieceCollection Class](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md).</span></span>  
  
 [!code-csharp[ManipulationXNA#_Game1_UpdateGame](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_updategame)]  
  
 <span data-ttu-id="2f7b1-114">[Kreslení](http://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) metoda zkratka opakovaně rozhraním XNA Framework spuštěného příslušnou hru.</span><span class="sxs-lookup"><span data-stu-id="2f7b1-114">The [Draw](http://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) method is also called repeatedly by the XNA Framework while the game is running.</span></span> <span data-ttu-id="2f7b1-115">[Kreslení](http://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) metoda provádí vykreslování kameny voláním **kreslení** metodu **GamePieceCollection** objektu.</span><span class="sxs-lookup"><span data-stu-id="2f7b1-115">The [Draw](http://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) method performs the rendering of game pieces by calling the **Draw** method of the **GamePieceCollection** object.</span></span> <span data-ttu-id="2f7b1-116">Tato metoda je popsaná v[vytvoření třídy Gamepiececollection](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md).</span><span class="sxs-lookup"><span data-stu-id="2f7b1-116">This method is described in[Creating the GamePieceCollection Class](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md).</span></span>  
  
 [!code-csharp[ManipulationXNA#_Game1_DrawGame](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/game1.cs#_game1_drawgame)]  
  
## <a name="see-also"></a><span data-ttu-id="2f7b1-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="2f7b1-117">See Also</span></span>  
 [<span data-ttu-id="2f7b1-118">Manipulace a nečinnosti</span><span class="sxs-lookup"><span data-stu-id="2f7b1-118">Manipulations and Inertia</span></span>](../../../docs/framework/common-client-technologies/manipulations-and-inertia.md)  
 [<span data-ttu-id="2f7b1-119">Použití manipulace a nečinnosti v aplikaci XNA</span><span class="sxs-lookup"><span data-stu-id="2f7b1-119">Using Manipulations and Inertia in an XNA Application</span></span>](../../../docs/framework/common-client-technologies/use-manipulations-and-inertia-in-an-xna-application.md)  
 [<span data-ttu-id="2f7b1-120">Vytvoření třídy Gamepiece</span><span class="sxs-lookup"><span data-stu-id="2f7b1-120">Creating the GamePiece Class</span></span>](../../../docs/framework/common-client-technologies/creating-the-gamepiece-class.md)  
 [<span data-ttu-id="2f7b1-121">Vytvoření třídy Gamepiececollection</span><span class="sxs-lookup"><span data-stu-id="2f7b1-121">Creating the GamePieceCollection Class</span></span>](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md)  
 [<span data-ttu-id="2f7b1-122">Výpis úplného kódu</span><span class="sxs-lookup"><span data-stu-id="2f7b1-122">Full Code Listings</span></span>](../../../docs/framework/common-client-technologies/full-code-listings.md)
---
title: "Postupy: Změna uživatelského nastavení v jazyce Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- user settings [Visual Basic], changing in Visual Basic
- user settings
- My.Settings object [Visual Basic], changing user settings
- examples [Visual Basic], changing user settings
ms.assetid: 41250181-c594-4854-9988-8183b9eb03cf
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: db35a5d63938fcc508c23af5588957d8dc518676
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-change-user-settings-in-visual-basic"></a><span data-ttu-id="e0020-102">Postupy: Změna uživatelského nastavení v jazyce Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e0020-102">How to: Change User Settings in Visual Basic</span></span>
<span data-ttu-id="e0020-103">Uživatelské nastavení můžete změnit přiřazením nové hodnoty pro vlastnosti nastavení na `My.Settings` objektu.</span><span class="sxs-lookup"><span data-stu-id="e0020-103">You can change a user setting by assigning a new value to the setting's property on the `My.Settings` object.</span></span>  
  
 <span data-ttu-id="e0020-104">`My.Settings` Objekt zpřístupňuje každé nastavení vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="e0020-104">The `My.Settings` object exposes each setting as a property.</span></span> <span data-ttu-id="e0020-105">Název vlastnosti je stejný jako název nastavení a typ vlastnosti je stejný jako typ nastavení.</span><span class="sxs-lookup"><span data-stu-id="e0020-105">The property name is the same as the setting name, and the property type is the same as the setting type.</span></span> <span data-ttu-id="e0020-106">Toto nastavení **oboru** Určuje, zda je vlastnost jen pro čtení: vlastnost pro **aplikace**-oboru nastavení je jen pro čtení, při vlastnost pro **uživatele**-oboru nastavení je pro čtení a zápis.</span><span class="sxs-lookup"><span data-stu-id="e0020-106">The setting's **Scope** determines if the property is read-only: The property for an **Application**-scope setting is read-only, while the property for a **User**-scope setting is read-write.</span></span> <span data-ttu-id="e0020-107">Další informace najdete v tématu [My.Settings – objekt](../../../../visual-basic/language-reference/objects/my-settings-object.md).</span><span class="sxs-lookup"><span data-stu-id="e0020-107">For more information, see [My.Settings Object](../../../../visual-basic/language-reference/objects/my-settings-object.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e0020-108">I když můžete změnit a uložit hodnoty uživatelského nastavení v době běhu, nastavení aplikace jsou jen pro čtení a nedá se změnit prostřednictvím kódu programu.</span><span class="sxs-lookup"><span data-stu-id="e0020-108">Although you can change and save the values of user-scope settings at run time, application-scope settings are read-only and cannot be changed programmatically.</span></span> <span data-ttu-id="e0020-109">Nastavení aplikace můžete změnit, když vytvoříte aplikaci pomocí **Návrhář projektu** nebo úpravou konfiguračního souboru aplikace.</span><span class="sxs-lookup"><span data-stu-id="e0020-109">You can change application-scope settings when you create the application by using the **Project Designer** or by editing the application's configuration file.</span></span> <span data-ttu-id="e0020-110">Další informace najdete v tématu [Správa nastavení aplikace (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span><span class="sxs-lookup"><span data-stu-id="e0020-110">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e0020-111">Příklad</span><span class="sxs-lookup"><span data-stu-id="e0020-111">Example</span></span>  
 <span data-ttu-id="e0020-112">Tento příklad změní hodnotu `Nickname` nastavení uživatele.</span><span class="sxs-lookup"><span data-stu-id="e0020-112">This example changes the value of the `Nickname` user setting.</span></span>  
  
 [!code-vb[VbVbalrMyResources#7](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-change-user-settings_1.vb)]  
  
 <span data-ttu-id="e0020-113">Pro tento příklad fungoval, musí mít vaše aplikace `Nickname` nastavení uživatele, typu `String`.</span><span class="sxs-lookup"><span data-stu-id="e0020-113">For this example to work, your application must have a `Nickname` user setting, of type `String`.</span></span>  
  
 <span data-ttu-id="e0020-114">Při vypnutí aplikace, aplikace uloží uživatelská nastavení.</span><span class="sxs-lookup"><span data-stu-id="e0020-114">The application saves the user settings when the application shuts down.</span></span> <span data-ttu-id="e0020-115">Chcete-li uložit nastavení okamžitě, zavolejte `My.Settings.Save` metoda.</span><span class="sxs-lookup"><span data-stu-id="e0020-115">To save the settings immediately, call the `My.Settings.Save` method.</span></span> <span data-ttu-id="e0020-116">Další informace najdete v tématu [postupy: zachování uživatelského nastavení v jazyce Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md).</span><span class="sxs-lookup"><span data-stu-id="e0020-116">For more information, see [How to: Persist User Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0020-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="e0020-117">See Also</span></span>  
 [<span data-ttu-id="e0020-118">My.Settings – objekt</span><span class="sxs-lookup"><span data-stu-id="e0020-118">My.Settings Object</span></span>](../../../../visual-basic/language-reference/objects/my-settings-object.md)  
 [<span data-ttu-id="e0020-119">Postupy: čtení nastavení aplikace v jazyce Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e0020-119">How to: Read Application Settings in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)  
 [<span data-ttu-id="e0020-120">Postupy: zachovaly uživatelská nastavení v jazyce Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e0020-120">How to: Persist User Settings in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)  
 [<span data-ttu-id="e0020-121">Postupy: vytváření mřížek vlastností pro uživatelská nastavení v jazyce Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e0020-121">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)  
 [<span data-ttu-id="e0020-122">Správa nastavení aplikace (.NET)</span><span class="sxs-lookup"><span data-stu-id="e0020-122">Managing Application Settings (.NET)</span></span>](/visualstudio/ide/managing-application-settings-dotnet)
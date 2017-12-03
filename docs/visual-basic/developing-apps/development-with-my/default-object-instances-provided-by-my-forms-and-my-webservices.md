---
title: "Výchozí instance objektů poskytované třídami My.Forms a My.WebServices (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- My.WebServices object [Visual Basic], developing applications
- My.Forms object [Visual Basic], developing applications
- rapid application development (RAD), My.Forms
- rapid application development (RAD), My.WebServices
ms.assetid: de930027-9108-4f0c-b97c-5e7db4d6ef79
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 44265c3f6f38a001192a8d92f2fbb6edeaca21cb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="default-object-instances-provided-by-myforms-and-mywebservices-visual-basic"></a><span data-ttu-id="75877-102">Výchozí instance objektů poskytované třídami My.Forms a My.WebServices (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="75877-102">Default Object Instances Provided by My.Forms and My.WebServices (Visual Basic)</span></span>
<span data-ttu-id="75877-103">[My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md) a [My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md) objekty poskytují přístup k formulářů, zdroje dat a webové služby XML používá vaše aplikace.</span><span class="sxs-lookup"><span data-stu-id="75877-103">The [My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md) and [My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md) objects provide access to forms, data sources, and XML Web services used by your application.</span></span> <span data-ttu-id="75877-104">Je to tím, že poskytuje kolekce *výchozí instance* každé z těchto objektů.</span><span class="sxs-lookup"><span data-stu-id="75877-104">They do this by providing collections of *default instances* of each of these objects.</span></span>  
  
## <a name="default-instances"></a><span data-ttu-id="75877-105">Výchozí instance</span><span class="sxs-lookup"><span data-stu-id="75877-105">Default Instances</span></span>  
 <span data-ttu-id="75877-106">Výchozí instance je instance třídy, která je k dispozici modulem runtime a nemusí být deklarována a vytvořena pomocí `Dim` a `New` příkazy.</span><span class="sxs-lookup"><span data-stu-id="75877-106">A default instance is an instance of the class that is provided by the runtime and does not need to be declared and instantiated using the `Dim` and `New` statements.</span></span> <span data-ttu-id="75877-107">Následující příklad ukazuje, jak vám může deklarovat a vytvořili instanci <xref:System.Windows.Forms.Form> třídu s názvem `Form1`, a jak je nyní možné získat výchozí instanci tohoto <xref:System.Windows.Forms.Form> třídy prostřednictvím `My.Forms`.</span><span class="sxs-lookup"><span data-stu-id="75877-107">The following example demonstrates how you might have declared and instantiated an instance of a <xref:System.Windows.Forms.Form> class called `Form1`, and how you are now able to get a default instance of this <xref:System.Windows.Forms.Form> class through `My.Forms`.</span></span>  
  
 [!code-vb[VbVbcnMy#5](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/default-object-instances-provided-by-my-forms-and-my-webservices_1.vb)]  
  
 [!code-vb[VbVbcnMy#6](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/default-object-instances-provided-by-my-forms-and-my-webservices_2.vb)]  
  
 <span data-ttu-id="75877-108">`My.Forms` Objekt vrátí kolekci výchozí instance pro každý `Form` třídu, která existuje v projektu.</span><span class="sxs-lookup"><span data-stu-id="75877-108">The `My.Forms` object returns a collection of default instances for every `Form` class that exists in your project.</span></span> <span data-ttu-id="75877-109">Podobně `My.WebServices` poskytuje výchozí instanci třídy proxy pro každou webovou službu, že jste vytvořili odkaz na ve vaší aplikaci.</span><span class="sxs-lookup"><span data-stu-id="75877-109">Similarly, `My.WebServices` provides a default instance of the proxy class for every Web service that you have created a reference to in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75877-110">Viz také</span><span class="sxs-lookup"><span data-stu-id="75877-110">See Also</span></span>  
 [<span data-ttu-id="75877-111">My.Forms – objekt</span><span class="sxs-lookup"><span data-stu-id="75877-111">My.Forms Object</span></span>](../../../visual-basic/language-reference/objects/my-forms-object.md)  
 [<span data-ttu-id="75877-112">My.WebServices – objekt</span><span class="sxs-lookup"><span data-stu-id="75877-112">My.WebServices Object</span></span>](../../../visual-basic/language-reference/objects/my-webservices-object.md)  
 [<span data-ttu-id="75877-113">Jak Moje závisí na typu projektu</span><span class="sxs-lookup"><span data-stu-id="75877-113">How My Depends on Project Type</span></span>](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
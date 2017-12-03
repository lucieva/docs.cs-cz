---
title: "Postupy: Deklarace vlastnosti se smíšenými úrovněmi přístupu (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- access levels [Visual Basic], properties
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- mixed access levels
- Visual Basic code, properties
- properties [Visual Basic], access levels
- Property statement [Visual Basic], declaring mixed access levels
ms.assetid: fdbb2d97-279a-4956-b26c-cbdfbc34915a
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 90fe20303f6f2ed692e54e44ee8cc65897531543
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-declare-a-property-with-mixed-access-levels-visual-basic"></a><span data-ttu-id="ac475-102">Postupy: Deklarace vlastnosti se smíšenými úrovněmi přístupu (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ac475-102">How to: Declare a Property with Mixed Access Levels (Visual Basic)</span></span>
<span data-ttu-id="ac475-103">Pokud chcete `Get` a `Set` postupů na vlastnost, která má mít různé úrovně přístupu, můžete použít na úrovni mírnější `Property` prohlášení a více omezující úroveň buď `Get` nebo `Set` příkaz.</span><span class="sxs-lookup"><span data-stu-id="ac475-103">If you want the `Get` and `Set` procedures on a property to have different access levels, you can use the more permissive level in the `Property` statement and the more restrictive level in either the `Get` or `Set` statement.</span></span> <span data-ttu-id="ac475-104">Pokud chcete, aby určité části kódu, abyste mohli získat hodnotu vlastnosti a některé další části kódu, abyste mohli změnit hodnotu použijete u vlastnosti smíšenými úrovněmi přístupu.</span><span class="sxs-lookup"><span data-stu-id="ac475-104">You use mixed access levels on a property when you want certain parts of the code to be able to get the property's value, and certain other parts of the code to be able to change the value.</span></span>  
  
 <span data-ttu-id="ac475-105">Další informace o úrovních přístupu najdete v tématu [úrovně v jazyce Visual Basic přístupu](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="ac475-105">For more information on access levels, see [Access levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
### <a name="to-declare-a-property-with-mixed-access-levels"></a><span data-ttu-id="ac475-106">Deklarace vlastnosti se smíšenými úrovněmi přístupu</span><span class="sxs-lookup"><span data-stu-id="ac475-106">To declare a property with mixed access levels</span></span>  
  
1.  <span data-ttu-id="ac475-107">Deklarovat vlastnost běžným způsobem a zadejte méně omezující úroveň přístupu (například `Public`) v `Property` příkaz.</span><span class="sxs-lookup"><span data-stu-id="ac475-107">Declare the property in the normal way, and specify the less restrictive access level (such as `Public`) in the `Property` statement.</span></span>  
  
2.  <span data-ttu-id="ac475-108">Deklarovat buď `Get` nebo `Set` postup zadání více omezující úroveň přístupu (například `Friend`).</span><span class="sxs-lookup"><span data-stu-id="ac475-108">Declare either the `Get` or the `Set` procedure specifying the more restrictive access level (such as `Friend`).</span></span>  
  
3.  <span data-ttu-id="ac475-109">Nezadávejte procesu další úroveň přístupu.</span><span class="sxs-lookup"><span data-stu-id="ac475-109">Do not specify an access level on the other property procedure.</span></span> <span data-ttu-id="ac475-110">Úroveň přístupu, které jsou deklarované v předpokládá `Property` příkaz.</span><span class="sxs-lookup"><span data-stu-id="ac475-110">It assumes the access level declared in the `Property` statement.</span></span> <span data-ttu-id="ac475-111">Můžete omezit přístup jenom jeden z postupů vlastnost.</span><span class="sxs-lookup"><span data-stu-id="ac475-111">You can restrict access on only one of the property procedures.</span></span>  
  
     [!code-vb[VbVbcnProcedures#10](./codesnippet/VisualBasic/how-to-declare-a-property-with-mixed-access-levels_1.vb)]  
  
     <span data-ttu-id="ac475-112">V předchozím příkladu `Get` procedura nemá stejný `Protected` přístup jako vlastnost samostatně, při `Set` procedura nemá `Private` přístup.</span><span class="sxs-lookup"><span data-stu-id="ac475-112">In the preceding example, the `Get` procedure has the same `Protected` access as the property itself, while the `Set` procedure has `Private` access.</span></span> <span data-ttu-id="ac475-113">Třída odvozená z `employee` můžete přečíst `salary` hodnotu, ale jenom `employee` ho může nastavit třídy.</span><span class="sxs-lookup"><span data-stu-id="ac475-113">A class derived from `employee` can read the `salary` value, but only the `employee` class can set it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac475-114">Viz také</span><span class="sxs-lookup"><span data-stu-id="ac475-114">See Also</span></span>  
 [<span data-ttu-id="ac475-115">Postupy</span><span class="sxs-lookup"><span data-stu-id="ac475-115">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="ac475-116">Procedury vlastností</span><span class="sxs-lookup"><span data-stu-id="ac475-116">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="ac475-117">Parametry a argumenty procedury</span><span class="sxs-lookup"><span data-stu-id="ac475-117">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="ac475-118">Property – příkaz</span><span class="sxs-lookup"><span data-stu-id="ac475-118">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [<span data-ttu-id="ac475-119">Rozdíly mezi vlastnostmi a proměnnými v jazyce Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ac475-119">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)  
 [<span data-ttu-id="ac475-120">Postupy: vytvoření vlastnosti</span><span class="sxs-lookup"><span data-stu-id="ac475-120">How to: Create a Property</span></span>](./how-to-create-a-property.md)  
 [<span data-ttu-id="ac475-121">Postupy: volání procedury vlastnosti</span><span class="sxs-lookup"><span data-stu-id="ac475-121">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)  
 [<span data-ttu-id="ac475-122">Postupy: deklarace a volání výchozí vlastnosti v jazyce Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ac475-122">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)  
 [<span data-ttu-id="ac475-123">Postupy: vložení hodnoty do vlastnosti</span><span class="sxs-lookup"><span data-stu-id="ac475-123">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)  
 [<span data-ttu-id="ac475-124">Postupy: získání hodnoty z vlastnosti</span><span class="sxs-lookup"><span data-stu-id="ac475-124">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
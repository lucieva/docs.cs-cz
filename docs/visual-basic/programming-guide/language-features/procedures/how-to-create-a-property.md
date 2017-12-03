---
title: "Postupy: Vytvoření vlastnosti (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, properties
- properties [Visual Basic]
ms.assetid: 4d229712-6be8-4c5c-bac5-06995ce9185a
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d140e6a10061f7fabe3d12c6cce5d0c201e103d6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-property-visual-basic"></a><span data-ttu-id="cf98e-102">Postupy: Vytvoření vlastnosti (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cf98e-102">How to: Create a Property (Visual Basic)</span></span>
<span data-ttu-id="cf98e-103">Uzavřete definici vlastnosti mezi `Property` příkaz a `End Property` příkaz.</span><span class="sxs-lookup"><span data-stu-id="cf98e-103">You enclose a property definition between a `Property` statement and an `End Property` statement.</span></span> <span data-ttu-id="cf98e-104">V rámci této definici definujete `Get` postupu `Set` postup nebo obojí.</span><span class="sxs-lookup"><span data-stu-id="cf98e-104">Within this definition you define a `Get` procedure, a `Set` procedure, or both.</span></span> <span data-ttu-id="cf98e-105">Všechny vlastnosti kódu je v rámci těchto postupů.</span><span class="sxs-lookup"><span data-stu-id="cf98e-105">All the property's code lies within these procedures.</span></span>  
  
 <span data-ttu-id="cf98e-106">`Get` Postup načte hodnotu vlastnosti a `Set` postup ukládá hodnotu.</span><span class="sxs-lookup"><span data-stu-id="cf98e-106">The `Get` procedure retrieves the property's value, and the `Set` procedure stores a value.</span></span> <span data-ttu-id="cf98e-107">Pokud chcete vlastnost, která má mít přístup pro čtení a zápis, je nutné zadat oba procesy.</span><span class="sxs-lookup"><span data-stu-id="cf98e-107">If you want the property to have read/write access, you must define both procedures.</span></span> <span data-ttu-id="cf98e-108">Pro vlastnost jen pro čtení, můžete definovat jenom `Get`, a pro vlastnost jen pro zápis, můžete definovat jenom `Set`.</span><span class="sxs-lookup"><span data-stu-id="cf98e-108">For a read-only property, you define only `Get`, and for a write-only property, you define only `Set`.</span></span>  
  
### <a name="to-create-a-property"></a><span data-ttu-id="cf98e-109">K vytvoření vlastnosti</span><span class="sxs-lookup"><span data-stu-id="cf98e-109">To create a property</span></span>  
  
1.  <span data-ttu-id="cf98e-110">Mimo vlastnost nebo postup, použijte [Property – příkaz](../../../../visual-basic/language-reference/statements/property-statement.md), za nímž následují `End Property` příkaz.</span><span class="sxs-lookup"><span data-stu-id="cf98e-110">Outside any property or procedure, use a [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md), followed by an `End Property` statement.</span></span>  
  
2.  <span data-ttu-id="cf98e-111">Pokud vlastnost přijímá parametry, postupujte podle kroků `Property` – klíčové slovo s názvem postup, pak se seznam parametrů v závorkách.</span><span class="sxs-lookup"><span data-stu-id="cf98e-111">If the property takes parameters, follow the `Property` keyword with the name of the procedure, then the parameter list in parentheses.</span></span>  
  
3.  <span data-ttu-id="cf98e-112">Postupujte podle závorkách s `As` klauzule zadat datový typ hodnoty vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="cf98e-112">Follow the parentheses with an `As` clause to specify the data type of the property's value.</span></span> <span data-ttu-id="cf98e-113">Musíte zadat typ dat i pro vlastnost jen pro zápis.</span><span class="sxs-lookup"><span data-stu-id="cf98e-113">You must specify the data type even for a write-only property.</span></span>  
  
4.  <span data-ttu-id="cf98e-114">Přidat `Get` a `Set` postupy, podle potřeby.</span><span class="sxs-lookup"><span data-stu-id="cf98e-114">Add `Get` and `Set` procedures, as appropriate.</span></span> <span data-ttu-id="cf98e-115">Najdete v následujících pokynů.</span><span class="sxs-lookup"><span data-stu-id="cf98e-115">See the following directions.</span></span>  
  
### <a name="to-create-a-get-procedure-that-retrieves-a-property-value"></a><span data-ttu-id="cf98e-116">Chcete-li vytvořit Get procedury, která načte hodnotu vlastnosti</span><span class="sxs-lookup"><span data-stu-id="cf98e-116">To create a Get procedure that retrieves a property value</span></span>  
  
1.  <span data-ttu-id="cf98e-117">Mezi `Property` a `End Property` příkazy, zápisu [získat příkaz](../../../../visual-basic/language-reference/statements/get-statement.md), za nímž následují `End Get` příkaz.</span><span class="sxs-lookup"><span data-stu-id="cf98e-117">Between the `Property` and `End Property` statements, write a [Get Statement](../../../../visual-basic/language-reference/statements/get-statement.md), followed by an `End Get` statement.</span></span> <span data-ttu-id="cf98e-118">Není nutné definovat všechny parametry `Get` postupu.</span><span class="sxs-lookup"><span data-stu-id="cf98e-118">You do not need to define any parameters for the `Get` procedure.</span></span>  
  
2.  <span data-ttu-id="cf98e-119">Umístěte příkazy kód pro načtení vlastnosti na hodnotu mezi `Get` a `End Get` příkazy.</span><span class="sxs-lookup"><span data-stu-id="cf98e-119">Place the code statements to retrieve the property's value between the `Get` and `End Get` statements.</span></span> <span data-ttu-id="cf98e-120">Tento kód mohou zahrnovat jiné výpočty a manipulace dat kromě generování a vrací hodnotu vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="cf98e-120">This code can include other calculations and data manipulations in addition to generating and returning the property's value.</span></span>  
  
3.  <span data-ttu-id="cf98e-121">Použití `Return` příkaz vrátit hodnotu vlastnosti volání kódu.</span><span class="sxs-lookup"><span data-stu-id="cf98e-121">Use a `Return` statement to return the property's value to the calling code.</span></span>  
  
 <span data-ttu-id="cf98e-122">Musíte napsat `Get` postup pro vlastnost pro čtení a zápis a pro vlastnost jen pro čtení.</span><span class="sxs-lookup"><span data-stu-id="cf98e-122">You must write a `Get` procedure for a read-write property and for a read-only property.</span></span> <span data-ttu-id="cf98e-123">Nesmí definovat `Get` postup pro vlastnost jen pro zápis.</span><span class="sxs-lookup"><span data-stu-id="cf98e-123">You must not define a `Get` procedure for a write-only property.</span></span>  
  
### <a name="to-create-a-set-procedure-that-writes-a-propertys-value"></a><span data-ttu-id="cf98e-124">K vytvoření procedury Set, vlastnosti na hodnotu zapíše</span><span class="sxs-lookup"><span data-stu-id="cf98e-124">To create a Set procedure that writes a property's value</span></span>  
  
1.  <span data-ttu-id="cf98e-125">Mezi `Property` a `End Property` příkazy, zápisu [příkaz Set](../../../../visual-basic/language-reference/statements/set-statement.md), za nímž následují `End Set` příkaz.</span><span class="sxs-lookup"><span data-stu-id="cf98e-125">Between the `Property` and `End Property` statements, write a [Set Statement](../../../../visual-basic/language-reference/statements/set-statement.md), followed by an `End Set` statement.</span></span>  
  
2.  <span data-ttu-id="cf98e-126">V `Set` prohlášení, postupujte podle `Set` – klíčové slovo s seznam parametrů v závorkách.</span><span class="sxs-lookup"><span data-stu-id="cf98e-126">In the `Set` statement, follow the `Set` keyword with a parameter list in parentheses.</span></span> <span data-ttu-id="cf98e-127">Tento seznam parametr musí obsahovat alespoň hodnotu parametru pro hodnotu předaná volající kód.</span><span class="sxs-lookup"><span data-stu-id="cf98e-127">This parameter list must include at least a value parameter for the value passed by the calling code.</span></span> <span data-ttu-id="cf98e-128">Výchozí název pro tento parametr hodnotu je `Value`, ale podle potřeby můžete použít jiný název.</span><span class="sxs-lookup"><span data-stu-id="cf98e-128">The default name for this value parameter is `Value`, but you can use a different name if appropriate.</span></span> <span data-ttu-id="cf98e-129">Parametr musí mít stejný datový typ. jako samotné vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="cf98e-129">The value parameter must have the same data type as the property itself.</span></span>  
  
3.  <span data-ttu-id="cf98e-130">Umístěte příkazy kód pro ukládání hodnot ve vlastnosti mezi `Set` a `End Set` příkazy.</span><span class="sxs-lookup"><span data-stu-id="cf98e-130">Place the code statements to store a value in the property between the `Set` and `End Set` statements.</span></span> <span data-ttu-id="cf98e-131">Tento kód mohou zahrnovat jiné výpočty a manipulace dat kromě ověření a ukládání hodnotu vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="cf98e-131">This code can include other calculations and data manipulations in addition to validating and storing the property's value.</span></span>  
  
4.  <span data-ttu-id="cf98e-132">Použijte parametr hodnotu tak, aby přijímal hodnota zadaná volání kódem.</span><span class="sxs-lookup"><span data-stu-id="cf98e-132">Use the value parameter to accept the value supplied by the calling code.</span></span> <span data-ttu-id="cf98e-133">Můžete buď uložení této hodnoty přímo v příkazu přiřazení nebo použít ve výrazu k výpočtu interní hodnota, která má být uložen.</span><span class="sxs-lookup"><span data-stu-id="cf98e-133">You can either store this value directly in an assignment statement, or use it in an expression to calculate the internal value to be stored.</span></span>  
  
 <span data-ttu-id="cf98e-134">Musíte napsat `Set` postup pro vlastnost pro čtení a zápis a pro vlastnost jen pro zápis.</span><span class="sxs-lookup"><span data-stu-id="cf98e-134">You must write a `Set` procedure for a read-write property and for a write-only property.</span></span> <span data-ttu-id="cf98e-135">Nesmí definovat `Set` postup pro vlastnost jen pro čtení.</span><span class="sxs-lookup"><span data-stu-id="cf98e-135">You must not define a `Set` procedure for a read-only property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf98e-136">Příklad</span><span class="sxs-lookup"><span data-stu-id="cf98e-136">Example</span></span>  
 <span data-ttu-id="cf98e-137">Následující příklad vytvoří vlastnost pro čtení a zápis, která ukládá jméno a příjmení jako dvě základní názvy, křestní jméno a příjmení.</span><span class="sxs-lookup"><span data-stu-id="cf98e-137">The following example creates a read/write property that stores a full name as two constituent names, the first name and the last name.</span></span> <span data-ttu-id="cf98e-138">Při volání kód čte `fullName`, `Get` postup kombinuje dva základní názvy a vrátí úplný název.</span><span class="sxs-lookup"><span data-stu-id="cf98e-138">When the calling code reads `fullName`, the `Get` procedure combines the two constituent names and returns the full name.</span></span> <span data-ttu-id="cf98e-139">Při volání kód přiřadí nový úplný název, `Set` postup pokusí rozdělit na dvě základní názvy.</span><span class="sxs-lookup"><span data-stu-id="cf98e-139">When the calling code assigns a new full name, the `Set` procedure attempts to break it into two constituent names.</span></span> <span data-ttu-id="cf98e-140">Pokud nenajde mezeru, uloží jej všechny jako křestní jméno.</span><span class="sxs-lookup"><span data-stu-id="cf98e-140">If it does not find a space, it stores it all as the first name.</span></span>  
  
 [!code-vb[VbVbcnProcedures#8](./codesnippet/VisualBasic/how-to-create-a-property_1.vb)]  
  
 <span data-ttu-id="cf98e-141">Následující příklad ukazuje typické volání procedury vlastnosti z `fullName`.</span><span class="sxs-lookup"><span data-stu-id="cf98e-141">The following example shows typical calls to the property procedures of `fullName`.</span></span> <span data-ttu-id="cf98e-142">První volání nastaví hodnotu vlastnosti a obnoví druhé volání.</span><span class="sxs-lookup"><span data-stu-id="cf98e-142">The first call sets the property value and the second call retrieves it.</span></span>  
  
 [!code-vb[VbVbcnProcedures#9](./codesnippet/VisualBasic/how-to-create-a-property_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="cf98e-143">Viz také</span><span class="sxs-lookup"><span data-stu-id="cf98e-143">See Also</span></span>  
 [<span data-ttu-id="cf98e-144">Postupy</span><span class="sxs-lookup"><span data-stu-id="cf98e-144">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="cf98e-145">Procedury vlastností</span><span class="sxs-lookup"><span data-stu-id="cf98e-145">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="cf98e-146">Parametry a argumenty procedury</span><span class="sxs-lookup"><span data-stu-id="cf98e-146">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="cf98e-147">Rozdíly mezi vlastnostmi a proměnnými v jazyce Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cf98e-147">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)  
 [<span data-ttu-id="cf98e-148">Postupy: deklarace vlastnosti se smíšenými úrovněmi přístupu</span><span class="sxs-lookup"><span data-stu-id="cf98e-148">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)  
 [<span data-ttu-id="cf98e-149">Postupy: volání procedury vlastnosti</span><span class="sxs-lookup"><span data-stu-id="cf98e-149">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)  
 [<span data-ttu-id="cf98e-150">Postupy: deklarace a volání výchozí vlastnosti v jazyce Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cf98e-150">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)  
 [<span data-ttu-id="cf98e-151">Postupy: vložení hodnoty do vlastnosti</span><span class="sxs-lookup"><span data-stu-id="cf98e-151">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)  
 [<span data-ttu-id="cf98e-152">Postupy: získání hodnoty z vlastnosti</span><span class="sxs-lookup"><span data-stu-id="cf98e-152">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
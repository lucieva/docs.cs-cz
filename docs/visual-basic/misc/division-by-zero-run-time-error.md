---
title: "Chyba dělení nulou (Visual Basic Runtime)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID11
ms.assetid: 5b9bc5d6-792e-48bc-a974-012e07ad95f3
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9a913e3b55b38430c0908f77aac79cb342e78719
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="division-by-zero-visual-basic-run-time-error"></a><span data-ttu-id="0e1a9-102">Chyba dělení nulou (Visual Basic Runtime)</span><span class="sxs-lookup"><span data-stu-id="0e1a9-102">Division by zero (Visual Basic Run-Time Error)</span></span>
<span data-ttu-id="0e1a9-103">Výraz, který používá jako dělitel má nulovou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="0e1a9-103">An expression being used as a divisor has a value of zero.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0e1a9-104">Oprava této chyby</span><span class="sxs-lookup"><span data-stu-id="0e1a9-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="0e1a9-105">Zkontrolujte, zda proměnné ve výrazu.</span><span class="sxs-lookup"><span data-stu-id="0e1a9-105">Check the spelling of variables in the expression.</span></span> <span data-ttu-id="0e1a9-106">Chybný název proměnné můžete vytvořit implicitně číselné proměnné, která je inicializováno na nulu.</span><span class="sxs-lookup"><span data-stu-id="0e1a9-106">A misspelled variable name can implicitly create a numeric variable that is initialized to zero.</span></span>  
  
2.  <span data-ttu-id="0e1a9-107">Zkontrolujte předchozí operace na proměnné ve výrazu, především těch, které jsou předány do procesu jako argumenty z další postupy.</span><span class="sxs-lookup"><span data-stu-id="0e1a9-107">Check previous operations on variables in the expression, especially those passed into the procedure as arguments from other procedures.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e1a9-108">Viz také</span><span class="sxs-lookup"><span data-stu-id="0e1a9-108">See Also</span></span>  
 [<span data-ttu-id="0e1a9-109">Předávání argumentů podle hodnoty a podle Reference</span><span class="sxs-lookup"><span data-stu-id="0e1a9-109">Passing Arguments by Value and by Reference</span></span>](../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="0e1a9-110">Parametr předávání mechanismus změny v jazyce Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0e1a9-110">Parameter Passing Mechanism Changes in Visual Basic</span></span>](http://msdn.microsoft.com/en-us/0fa2b0dc-aa1c-4797-bbd6-aa13c611cab2)
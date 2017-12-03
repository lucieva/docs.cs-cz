---
title: "Pokyny pro návrh pro výjimky"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- exceptions [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], exceptions
- errors [.NET Framework], exceptions
- reporting errors
ms.assetid: bc177b2f-7528-4ae4-83db-aacfb04b86d0
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 30ee456632070f778d51d7fb40475a795a0f620b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="design-guidelines-for-exceptions"></a><span data-ttu-id="2da73-102">Pokyny pro návrh pro výjimky</span><span class="sxs-lookup"><span data-stu-id="2da73-102">Design Guidelines for Exceptions</span></span>
<span data-ttu-id="2da73-103">Zpracovávání výjimek v jazyce má mnoho výhod oproti zasílání zpráv o chybách na základě vrátit hodnotu.</span><span class="sxs-lookup"><span data-stu-id="2da73-103">Exception handling has many advantages over return-value-based error reporting.</span></span> <span data-ttu-id="2da73-104">Dobrý framework návrhu pomáhá výhody výjimek vývojáře aplikace.</span><span class="sxs-lookup"><span data-stu-id="2da73-104">Good framework design helps the application developer realize the benefits of exceptions.</span></span> <span data-ttu-id="2da73-105">Tato část popisuje výhody výjimky a uvede pokyny pro efektivním použitím.</span><span class="sxs-lookup"><span data-stu-id="2da73-105">This section discusses the benefits of exceptions and presents guidelines for using them effectively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2da73-106">V tomto oddílu</span><span class="sxs-lookup"><span data-stu-id="2da73-106">In This Section</span></span>  
 [<span data-ttu-id="2da73-107">Vyvolání výjimek</span><span class="sxs-lookup"><span data-stu-id="2da73-107">Exception Throwing</span></span>](../../../docs/standard/design-guidelines/exception-throwing.md)  
 [<span data-ttu-id="2da73-108">Použití typů standardní výjimky</span><span class="sxs-lookup"><span data-stu-id="2da73-108">Using Standard Exception Types</span></span>](../../../docs/standard/design-guidelines/using-standard-exception-types.md)  
 [<span data-ttu-id="2da73-109">Výjimky a výkonu</span><span class="sxs-lookup"><span data-stu-id="2da73-109">Exceptions and Performance</span></span>](../../../docs/standard/design-guidelines/exceptions-and-performance.md)  
 <span data-ttu-id="2da73-110">*Části © 2005, 2009 Microsoft Corporation. Všechna práva vyhrazena.*</span><span class="sxs-lookup"><span data-stu-id="2da73-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="2da73-111">*Provedení podle oprávnění Pearson Education, Inc. z [pokynů pro návrh Framework: konvence, Idioms a vzory pro jedno použití knihovny .NET, 2. vydání](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina a Abrams Brada publikovaná 22 Oct 2008 pomocí Designing Effective jako součást vývoj řady Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="2da73-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2da73-112">Viz také</span><span class="sxs-lookup"><span data-stu-id="2da73-112">See Also</span></span>  
 [<span data-ttu-id="2da73-113">Pokyny pro návrh Framework</span><span class="sxs-lookup"><span data-stu-id="2da73-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
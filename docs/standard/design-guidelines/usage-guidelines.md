---
title: "Pokyny týkající se používání"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: class library design guidelines [.NET Framework], usage guidelines
ms.assetid: 42215ffa-a099-4a26-b14e-fb2bdb6f95b7
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: df0d1c5f8bff9d4cb546378f281a44c696246553
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="usage-guidelines"></a><span data-ttu-id="df055-102">Pokyny týkající se používání</span><span class="sxs-lookup"><span data-stu-id="df055-102">Usage Guidelines</span></span>
<span data-ttu-id="df055-103">Tato část obsahuje pokyny k používání běžné typy v rozhraní API pro veřejně přístupná.</span><span class="sxs-lookup"><span data-stu-id="df055-103">This section contains guidelines for using common types in publicly accessible APIs.</span></span> <span data-ttu-id="df055-104">Zabývá přímého použití předdefinované Framework typů (např. atributy serializace) a přetížení běžných operátorů.</span><span class="sxs-lookup"><span data-stu-id="df055-104">It deals with direct usage of built-in Framework types (e.g., serialization attributes) and overloading common operators.</span></span>  
  
 <span data-ttu-id="df055-105"><xref:System.IDisposable?displayProperty=nameWithType> Rozhraní není zahrnutý v této části, ale je podrobněji [Dispose vzor](../../../docs/standard/design-guidelines/dispose-pattern.md) části.</span><span class="sxs-lookup"><span data-stu-id="df055-105">The <xref:System.IDisposable?displayProperty=nameWithType> interface is not covered in this section, but is discussed in the [Dispose Pattern](../../../docs/standard/design-guidelines/dispose-pattern.md) section.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="df055-106">Pokyny a další informace o o další běžné vestavěné typy rozhraní .NET Framework, najdete v referenčních tématech pro následující: <xref:System.DateTime?displayProperty=nameWithType>, <xref:System.DateTimeOffset?displayProperty=nameWithType>, <xref:System.ICloneable?displayProperty=nameWithType>, <xref:System.IComparable%601?displayProperty=nameWithType>, <xref:System.IEquatable%601?displayProperty=nameWithType>, <xref:System.Nullable%601?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType> , <xref:System.Uri?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="df055-106">For guidelines and additional information about about other common, built-in .NET Framework types, see the reference topics for the following: <xref:System.DateTime?displayProperty=nameWithType>, <xref:System.DateTimeOffset?displayProperty=nameWithType>, <xref:System.ICloneable?displayProperty=nameWithType>, <xref:System.IComparable%601?displayProperty=nameWithType>, <xref:System.IEquatable%601?displayProperty=nameWithType>, <xref:System.Nullable%601?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="df055-107">V tomto oddílu</span><span class="sxs-lookup"><span data-stu-id="df055-107">In This Section</span></span>  
 [<span data-ttu-id="df055-108">Pole</span><span class="sxs-lookup"><span data-stu-id="df055-108">Arrays</span></span>](../../../docs/standard/design-guidelines/arrays.md)  
 [<span data-ttu-id="df055-109">Atributy</span><span class="sxs-lookup"><span data-stu-id="df055-109">Attributes</span></span>](../../../docs/standard/design-guidelines/attributes.md)  
 [<span data-ttu-id="df055-110">Kolekce</span><span class="sxs-lookup"><span data-stu-id="df055-110">Collections</span></span>](/cpp/mfc/collections)  
 [<span data-ttu-id="df055-111">Serializace</span><span class="sxs-lookup"><span data-stu-id="df055-111">Serialization</span></span>](../../../docs/standard/design-guidelines/serialization.md)  
 [<span data-ttu-id="df055-112">System.Xml využití</span><span class="sxs-lookup"><span data-stu-id="df055-112">System.Xml Usage</span></span>](../../../docs/standard/design-guidelines/system-xml-usage.md)  
 [<span data-ttu-id="df055-113">Operátory rovnosti</span><span class="sxs-lookup"><span data-stu-id="df055-113">Equality Operators</span></span>](../../../docs/standard/design-guidelines/equality-operators.md)  
 <span data-ttu-id="df055-114">*Části © 2005, 2009 Microsoft Corporation. Všechna práva vyhrazena.*</span><span class="sxs-lookup"><span data-stu-id="df055-114">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="df055-115">*Provedení podle oprávnění Pearson Education, Inc. z [pokynů pro návrh Framework: konvence, Idioms a vzory pro jedno použití knihovny .NET, 2. vydání](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina a Abrams Brada publikovaná 22 Oct 2008 pomocí Designing Effective jako součást vývoj řady Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="df055-115">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df055-116">Viz také</span><span class="sxs-lookup"><span data-stu-id="df055-116">See Also</span></span>  
 [<span data-ttu-id="df055-117">Pokyny pro návrh Framework</span><span class="sxs-lookup"><span data-stu-id="df055-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
---
title: "Zabezpečení na základě rolí"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- role-based security, about role-based security
- user authentication, principals
- principals [.NET Framework]
- security [.NET Framework], role-based
- permissions [.NET Framework], principals
- authentication [.NET Framework], principals
- role-based security, principals
ms.assetid: 578cc32b-5654-4d8b-9d8c-ebcbc5c75390
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 83a3f58fc13eb1aaacb99a3f35c3149d78451c23
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="role-based-security"></a><span data-ttu-id="3d3a3-102">Zabezpečení na základě rolí</span><span class="sxs-lookup"><span data-stu-id="3d3a3-102">Role-Based Security</span></span>
<span data-ttu-id="3d3a3-103">Role se často používají v finanční nebo obchodní aplikace k vynucení zásad.</span><span class="sxs-lookup"><span data-stu-id="3d3a3-103">Roles are often used in financial or business applications to enforce policy.</span></span> <span data-ttu-id="3d3a3-104">Aplikace může například uložit omezení na velikost zpracovávané v závislosti na tom, zda uživatel zadal žádost je členem zadané roli transakce.</span><span class="sxs-lookup"><span data-stu-id="3d3a3-104">For example, an application might impose limits on the size of the transaction being processed depending on whether the user making the request is a member of a specified role.</span></span> <span data-ttu-id="3d3a3-105">Úředníci mohou být autorizace k provádění transakcí, které jsou menší než zadaná prahová hodnota, vedoucí mohou mít vyšší limit a místopředsedové mohou mít stále vyšší limit (nebo vůbec žádné omezení).</span><span class="sxs-lookup"><span data-stu-id="3d3a3-105">Clerks might have authorization to process transactions that are less than a specified threshold, supervisors might have a higher limit, and vice-presidents might have a still higher limit (or no limit at all).</span></span> <span data-ttu-id="3d3a3-106">Na základě rolí zabezpečení mohou sloužit také pokud aplikace vyžaduje více schválení pro dokončení akce.</span><span class="sxs-lookup"><span data-stu-id="3d3a3-106">Role-based security can also be used when an application requires multiple approvals to complete an action.</span></span> <span data-ttu-id="3d3a3-107">Takovém případě může být nákupní systém, ve kterém můžete každý zaměstnanec generovat nákupní žádost, ale pouze nákupní agent můžete převést tuto žádost nákupní objednávka, který lze odeslat buď do jiného dodavatele.</span><span class="sxs-lookup"><span data-stu-id="3d3a3-107">Such a case might be a purchasing system in which any employee can generate a purchase request, but only a purchasing agent can convert that request into a purchase order that can be sent to a supplier.</span></span>  
  
 <span data-ttu-id="3d3a3-108">Zabezpečení na základě rolí rozhraní .NET framework podporuje autorizaci tím, že informace o objekt, který je vytvořený z přidružených identity, k dispozici pro aktuální vlákno.</span><span class="sxs-lookup"><span data-stu-id="3d3a3-108">.NET Framework role-based security supports authorization by making information about the principal, which is constructed from an associated identity, available to the current thread.</span></span> <span data-ttu-id="3d3a3-109">Identitu (a objekt, který pomáhá definovat) může být buď založené na účet systému Windows nebo být vlastní identity, které nejsou na účet systému Windows.</span><span class="sxs-lookup"><span data-stu-id="3d3a3-109">The identity (and the principal it helps to define) can be either based on a Windows account or be a custom identity unrelated to a Windows account.</span></span> <span data-ttu-id="3d3a3-110">Aplikace rozhraní .NET framework můžete provést rozhodnutí o autorizaci na základě identity objektu zabezpečení nebo členství v rolích nebo obojí.</span><span class="sxs-lookup"><span data-stu-id="3d3a3-110">.NET Framework applications can make authorization decisions based on the principal's identity or role membership, or both.</span></span> <span data-ttu-id="3d3a3-111">Role je pojmenovanou sadu objektů, které mají stejná práva s ohledem na zabezpečení (například pokladní nebo správce).</span><span class="sxs-lookup"><span data-stu-id="3d3a3-111">A role is a named set of principals that have the same privileges with respect to security (such as a teller or a manager).</span></span> <span data-ttu-id="3d3a3-112">Objekt zabezpečení může být členem jedné nebo více rolí.</span><span class="sxs-lookup"><span data-stu-id="3d3a3-112">A principal can be a member of one or more roles.</span></span> <span data-ttu-id="3d3a3-113">Proto aplikace můžete použít členství v rolích k určení, zda objekt zabezpečení má oprávnění provést požadovanou akci.</span><span class="sxs-lookup"><span data-stu-id="3d3a3-113">Therefore, applications can use role membership to determine whether a principal is authorized to perform a requested action.</span></span>  
  
 <span data-ttu-id="3d3a3-114">Snadné použití a konzistence poskytnout zabezpečení přístupu kódu, zabezpečení na základě rolí rozhraní .NET Framework poskytuje <xref:System.Security.Permissions.PrincipalPermission?displayProperty=nameWithType> objekty, které umožňují modul common language runtime k autorizaci způsobem, který je podobný kódu přístup kontroly zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="3d3a3-114">To provide ease of use and consistency with code access security, .NET Framework role-based security provides <xref:System.Security.Permissions.PrincipalPermission?displayProperty=nameWithType> objects that enable the common language runtime to perform authorization in a way that is similar to code access security checks.</span></span> <span data-ttu-id="3d3a3-115"><xref:System.Security.Permissions.PrincipalPermission> Třída reprezentuje identitu nebo roli, které objekt zabezpečení musí odpovídat a je kompatibilní s kontrolami deklarativní a naléhavé zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="3d3a3-115">The <xref:System.Security.Permissions.PrincipalPermission> class represents the identity or role that the principal must match and is compatible with both declarative and imperative security checks.</span></span> <span data-ttu-id="3d3a3-116">Můžete také přímý přístup objektu zabezpečení informací o identitě a provádět role a identity zkontroluje ve vašem kódu v případě potřeby.</span><span class="sxs-lookup"><span data-stu-id="3d3a3-116">You can also access a principal's identity information directly and perform role and identity checks in your code when needed.</span></span>  
  
 <span data-ttu-id="3d3a3-117">Rozhraní .NET Framework poskytuje podporu na základě rolí zabezpečení, který je flexibilní a rozšiřitelný dost pro potřeby široké spektrum aplikace.</span><span class="sxs-lookup"><span data-stu-id="3d3a3-117">The .NET Framework provides role-based security support that is flexible and extensible enough to meet the needs of a wide spectrum of applications.</span></span> <span data-ttu-id="3d3a3-118">Můžete spolupracovat se stávající infrastrukturou ověřování, jako je například služby COM + 1.0, nebo vytvořte vlastní ověřování systému.</span><span class="sxs-lookup"><span data-stu-id="3d3a3-118">You can choose to interoperate with existing authentication infrastructures, such as COM+ 1.0 Services, or to create a custom authentication system.</span></span> <span data-ttu-id="3d3a3-119">Zabezpečení na základě role je zvlášť vhodné pro použití v aplikacích ASP.NET Web, které jsou zpracovávány především na serveru.</span><span class="sxs-lookup"><span data-stu-id="3d3a3-119">Role-based security is particularly well-suited for use in ASP.NET Web applications, which are processed primarily on the server.</span></span> <span data-ttu-id="3d3a3-120">Zabezpečení na základě rolí rozhraní .NET Framework však lze použít na klienta nebo serveru.</span><span class="sxs-lookup"><span data-stu-id="3d3a3-120">However, .NET Framework role-based security can be used on either the client or the server.</span></span>  
  
 <span data-ttu-id="3d3a3-121">Před čtením této části, ujistěte se, že rozumíte materiálu uvedenému v [klíčové koncepty zabezpečení](../../../docs/standard/security/key-security-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="3d3a3-121">Before reading this section, make sure that you understand the material presented in [Key Security Concepts](../../../docs/standard/security/key-security-concepts.md).</span></span>  
  
## <a name="related-topics"></a><span data-ttu-id="3d3a3-122">Související témata</span><span class="sxs-lookup"><span data-stu-id="3d3a3-122">Related Topics</span></span>  
  
|<span data-ttu-id="3d3a3-123">Název</span><span class="sxs-lookup"><span data-stu-id="3d3a3-123">Title</span></span>|<span data-ttu-id="3d3a3-124">Popis</span><span class="sxs-lookup"><span data-stu-id="3d3a3-124">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="3d3a3-125">Hlavní a objekty Identity</span><span class="sxs-lookup"><span data-stu-id="3d3a3-125">Principal and Identity Objects</span></span>](../../../docs/standard/security/principal-and-identity-objects.md)|<span data-ttu-id="3d3a3-126">Vysvětluje, jak nastavit a spravovat Windows a obecné identity a objekty zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="3d3a3-126">Explains how to set up and manage both Windows and generic identities and principals.</span></span>|  
|[<span data-ttu-id="3d3a3-127">Klíčové koncepty zabezpečení</span><span class="sxs-lookup"><span data-stu-id="3d3a3-127">Key Security Concepts</span></span>](../../../docs/standard/security/key-security-concepts.md)|<span data-ttu-id="3d3a3-128">Představuje základní koncepty, které je třeba porozumět před použitím zabezpečení rozhraní .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3d3a3-128">Introduces fundamental concepts you must understand before using .NET Framework security.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="3d3a3-129">Odkaz</span><span class="sxs-lookup"><span data-stu-id="3d3a3-129">Reference</span></span>  
 <xref:System.Security.Permissions.PrincipalPermission?displayProperty=nameWithType>
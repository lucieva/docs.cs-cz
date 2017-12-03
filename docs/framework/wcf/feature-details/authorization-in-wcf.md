---
title: Autorizace ve WCF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- authorization [WCF]
- security [WCF], authorization
ms.assetid: 8ea0b552-af65-45b0-a157-c6c111b8ce5e
caps.latest.revision: "15"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a0c2afafa1d645ec0e95b7b41ff8389873969c89
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="authorization-in-wcf"></a><span data-ttu-id="207ad-102">Autorizace ve WCF</span><span class="sxs-lookup"><span data-stu-id="207ad-102">Authorization in WCF</span></span>
<span data-ttu-id="207ad-103">Autorizace je proces řízení přístupu a oprávnění k prostředkům, jako jsou služby nebo soubory.</span><span class="sxs-lookup"><span data-stu-id="207ad-103">Authorization is the process of controlling access and rights to resources, such as services or files.</span></span> <span data-ttu-id="207ad-104">Témata v této části popisují, jak to provést základní v [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] mnoha různými způsoby.</span><span class="sxs-lookup"><span data-stu-id="207ad-104">The topics in this section show you how to perform this basic task in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] in a variety of ways.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="207ad-105">V tomto oddílu</span><span class="sxs-lookup"><span data-stu-id="207ad-105">In This Section</span></span>  
 [<span data-ttu-id="207ad-106">Mechanismy řízení přístupu</span><span class="sxs-lookup"><span data-stu-id="207ad-106">Access Control Mechanisms</span></span>](../../../../docs/framework/wcf/feature-details/access-control-mechanisms.md)  
 <span data-ttu-id="207ad-107">Poskytuje stručný obrys mechanismy ověřování ve [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]a navrhované používá.</span><span class="sxs-lookup"><span data-stu-id="207ad-107">Provides a brief outline of the authorization mechanisms in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], and suggested uses.</span></span>  
  
 [<span data-ttu-id="207ad-108">Postupy: omezení přístupu pomocí třídy PrincipalPermissionAttribute</span><span class="sxs-lookup"><span data-stu-id="207ad-108">How to: Restrict Access with the PrincipalPermissionAttribute Class</span></span>](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)  
 <span data-ttu-id="207ad-109">Proces omezení přístupu ke službě se zobrazuje <xref:System.Security.Permissions.PrincipalPermissionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="207ad-109">Shows the process of restricting access to a service with the <xref:System.Security.Permissions.PrincipalPermissionAttribute>.</span></span>  
  
 [<span data-ttu-id="207ad-110">Postupy: použití zprostředkovatele rolí ASP.NET se službou</span><span class="sxs-lookup"><span data-stu-id="207ad-110">How to: Use the ASP.NET Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)  
 <span data-ttu-id="207ad-111">Provede konfiguraci této služby ji používat funkci poskytovatele role zapnout [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="207ad-111">Walks through the configuration of a service to enable it to use the role provider feature of [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].</span></span>  
  
 [<span data-ttu-id="207ad-112">Postupy: použití zprostředkovatele rolí Správce autorizací ASP.NET se službou</span><span class="sxs-lookup"><span data-stu-id="207ad-112">How to: Use the ASP.NET Authorization Manager Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md)  
 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]<span data-ttu-id="207ad-113">Správce autorizací můžete použít ke správě ověřování pro webovou stránku.</span><span class="sxs-lookup"><span data-stu-id="207ad-113"> can use the Authorization Manager to manage authorization for a Web site.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="207ad-114">Podobně můžete využít [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]/Authorization správce kombinaci pro ověřování klientů.</span><span class="sxs-lookup"><span data-stu-id="207ad-114"> can similarly leverage the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]/Authorization Manager combination for authorization of clients.</span></span>  
  
 [<span data-ttu-id="207ad-115">Správa deklarací a autorizace s modelem Identity</span><span class="sxs-lookup"><span data-stu-id="207ad-115">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)  
 <span data-ttu-id="207ad-116">Vysvětluje základy používání infrastruktury modelu Identity pro ověřování založené na deklaracích identity.</span><span class="sxs-lookup"><span data-stu-id="207ad-116">Explains the basics of using the Identity Model infrastructure for claims-based authorization.</span></span>  
  
 [<span data-ttu-id="207ad-117">Delegace a zosobnění</span><span class="sxs-lookup"><span data-stu-id="207ad-117">Delegation and Impersonation</span></span>](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)  
 <span data-ttu-id="207ad-118">Vysvětluje rozdíl mezi delegace a zosobnění.</span><span class="sxs-lookup"><span data-stu-id="207ad-118">Explains the difference between delegation and impersonation.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="207ad-119">Odkaz</span><span class="sxs-lookup"><span data-stu-id="207ad-119">Reference</span></span>  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel.Description.PrincipalPermissionMode>  
  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>  
  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
  
## <a name="related-sections"></a><span data-ttu-id="207ad-120">Související oddíly</span><span class="sxs-lookup"><span data-stu-id="207ad-120">Related Sections</span></span>  
 [<span data-ttu-id="207ad-121">Ověřování</span><span class="sxs-lookup"><span data-stu-id="207ad-121">Authentication</span></span>](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="207ad-122">Viz také</span><span class="sxs-lookup"><span data-stu-id="207ad-122">See Also</span></span>  
 [<span data-ttu-id="207ad-123">Přehled zabezpečení</span><span class="sxs-lookup"><span data-stu-id="207ad-123">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="207ad-124">Model zabezpečení pro Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="207ad-124">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
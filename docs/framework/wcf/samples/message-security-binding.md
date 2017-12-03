---
title: "Vazby zabezpečení zpráv"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a4570ce7-864e-461b-85d8-0f7bcc53c2c8
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: ca1ce99fae09ef7d3c9ad3ea47984b671cadb27c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="message-security-binding"></a><span data-ttu-id="def45-102">Vazby zabezpečení zpráv</span><span class="sxs-lookup"><span data-stu-id="def45-102">Message Security Binding</span></span>
<span data-ttu-id="def45-103">Tato část obsahuje příklady vysvětlující vazby zabezpečení zpráv ve službách systému Windows v [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="def45-103">This section contains samples that demonstrate message security binding in Windows Services in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="def45-104">V tomto oddílu</span><span class="sxs-lookup"><span data-stu-id="def45-104">In This Section</span></span>  
 [<span data-ttu-id="def45-105">Zabezpečení zpráv anonymní</span><span class="sxs-lookup"><span data-stu-id="def45-105">Message Security Anonymous</span></span>](../../../../docs/framework/wcf/samples/message-security-anonymous.md)  
 <span data-ttu-id="def45-106">Tento příklad ukazuje, jak implementovat [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] aplikace používající zabezpečení na úrovni zpráv bez jakéhokoli ověřování klienta, ale která vyžaduje server ověřování pomocí certifikátu X.509 serveru.</span><span class="sxs-lookup"><span data-stu-id="def45-106">This sample demonstrates how to implement a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] application that uses message-level security with no client authentication but that requires server authentication using the server's X.509 certificate.</span></span>  
  
 [<span data-ttu-id="def45-107">Certifikát zabezpečení zprávy</span><span class="sxs-lookup"><span data-stu-id="def45-107">Message Security Certificate</span></span>](../../../../docs/framework/wcf/samples/message-security-certificate.md)  
 <span data-ttu-id="def45-108">Tento příklad znázorňuje implementaci aplikace, která používá WS-zabezpečení X.509 v3 s ověřováním pomocí certifikátu pro klienta a vyžaduje ověření serveru pomocí serveru certifikát X.509 v3.</span><span class="sxs-lookup"><span data-stu-id="def45-108">This sample demonstrates how to implement an application that uses WS-Security with X.509 v3 certificate authentication for the client and requires server authentication using the server's X.509 v3 certificate.</span></span>  
  
 [<span data-ttu-id="def45-109">Uživatelské jméno zabezpečení zprávy</span><span class="sxs-lookup"><span data-stu-id="def45-109">Message Security User Name</span></span>](../../../../docs/framework/wcf/samples/message-security-user-name.md)  
 <span data-ttu-id="def45-110">Tento příklad znázorňuje implementaci aplikace, která využívá WS-zabezpečení pomocí uživatelského jména ověřování klienta a vyžaduje server ověřování pomocí certifikátu x.509 v3 serveru.</span><span class="sxs-lookup"><span data-stu-id="def45-110">This sample demonstrates how to implement an application that uses WS-Security with username authentication for the client and requires server authentication using the server's X.509v3 certificate.</span></span>  
  
 [<span data-ttu-id="def45-111">Zabezpečení zpráv – Windows</span><span class="sxs-lookup"><span data-stu-id="def45-111">Message Security Windows</span></span>](../../../../docs/framework/wcf/samples/message-security-windows.md)  
 <span data-ttu-id="def45-112">Tento příklad ukazuje, jak nakonfigurovat <xref:System.ServiceModel.WSHttpBinding> vazba k zabezpečení na úrovni zpráv pomocí ověřování systému Windows.</span><span class="sxs-lookup"><span data-stu-id="def45-112">This sample demonstrates how to configure a <xref:System.ServiceModel.WSHttpBinding> binding to use message-level security with Windows authentication.</span></span>
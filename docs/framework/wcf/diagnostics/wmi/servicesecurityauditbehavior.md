---
title: ServiceSecurityAuditBehavior
ms.date: 03/30/2017
ms.assetid: 2c5809e7-5364-44ce-bc71-848be4672e2a
ms.openlocfilehash: e8b24877c2d76a3f2f90c27ae83374c7bca1328b
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2018
ms.locfileid: "50181157"
---
# <a name="servicesecurityauditbehavior"></a>ServiceSecurityAuditBehavior
ServiceSecurityAuditBehavior  
  
## <a name="syntax"></a>Syntaxe  
  
```csharp  
class ServiceSecurityAuditBehavior : Behavior  
{  
  string AuditLogLocation;  
  string MessageAuthenticationAuditLevel;  
  string ServiceAuthorizationAuditLevel;  
  boolean SuppressAuditFailure;  
};  
```  
  
## <a name="methods"></a>Metody  
 Třída ServiceSecurityAuditBehavior nedefinuje žádné metody.  
  
## <a name="properties"></a>Vlastnosti  
 Třída ServiceSecurityAuditBehavior má následující vlastnosti:  
  
### <a name="auditloglocation"></a>AuditLogLocation  
 Datový typ: řetězec  
  
 Přístup k typu: jen pro čtení  
  
 Umístění auditovacího protokolu.  
  
### <a name="messageauthenticationauditlevel"></a>MessageAuthenticationAuditLevel  
 Datový typ: řetězec  
  
 Přístup k typu: jen pro čtení  
  
 Typ úrovně ověření zprávy, která se používá k zaznamenání událostí auditu.  
  
### <a name="serviceauthorizationauditlevel"></a>ServiceAuthorizationAuditLevel  
 Datový typ: řetězec  
  
 Přístup k typu: jen pro čtení  
  
 Typy událostí autorizace, které jsou zaznamenány v protokolu auditu.  
  
### <a name="suppressauditfailure"></a>SuppressAuditFailure  
 Datový typ: boolean  
  
 Přístup k typu: jen pro čtení  
  
 Logická hodnota, která určuje vlastnosti pro zamlčené chyby psaní do auditovacího protokolu.  
  
## <a name="requirements"></a>Požadavky  
  
|SOUBOR MOF|Deklarované v Servicemodel.mof.|  
|---------|-----------------------------------|  
|Obor názvů|Definované v root\ServiceModel|  
  
## <a name="see-also"></a>Viz také  
 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>

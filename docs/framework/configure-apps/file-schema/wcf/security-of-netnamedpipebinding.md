---
title: '&lt;security&gt; – &lt;netNamedPipeBinding&gt;'
ms.date: 03/30/2017
ms.assetid: bb3cb022-637e-49fd-92e8-6766038affa7
ms.openlocfilehash: 4a80a8337a5b98ff30de60afbe4438e0d91b946b
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2018
ms.locfileid: "50185677"
---
# <a name="ltsecuritygt-of-ltnetnamedpipebindinggt"></a>&lt;security&gt; – &lt;netNamedPipeBinding&gt;
Definuje nastavení zabezpečení pro vazbu.  
  
 \<system.ServiceModel>  
\<vazby >  
\<netNamedPipeBinding>  
\<Vytvoření vazby >  
\<zabezpečení >  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<netNamedPipeBinding>  
      <binding>  
            <security mode="None/Transport">  
                        <transport protectionLevel="None/Sign/EncryptAndSign" />  
            </security>  
      </binding>  
</netNamedPipeBinding>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|režim|Určuje typ zabezpečení, který se použije pro tuto vazbu. Platné hodnoty patří:<br /><br /> -Žádný: Zakáže zabezpečení.<br />-Přenos: Zabezpečení je k dispozici pomocí základního zabezpečení přenosu na základě. Je možné kontrolovat úroveň ochrany s tímto režimem.<br />– Výchozí hodnota je přenos. Tento atribut je typu <xref:System.ServiceModel.NetNamedPipeSecurityMode>.|  
  
### <a name="child-elements"></a>Podřízené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|transport|Definuje nastavení zabezpečení pro přenos. Tento prvek je typu <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.|  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|vazba|Prvek vazby [ \<netNamedPipeBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netnamedpipebinding.md).|  
  
## <a name="see-also"></a>Viz také  
 <xref:System.ServiceModel.NetNamedPipeSecurity>  
 <xref:System.ServiceModel.NetNamedPipeBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement>  
 [Zabezpečení služeb a klientů](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [Výběr typu přihlašovacích údajů](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [Vazby](../../../../../docs/framework/wcf/bindings.md)  
 [Konfigurace vazeb poskytovaných systémem](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [Používání vazeb ke konfiguraci služeb a klientů](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [\<Vytvoření vazby >](../../../../../docs/framework/misc/binding.md)

---
title: '&lt;serviceCertificate&gt; – &lt;serviceCredentials&gt;'
ms.date: 03/30/2017
ms.assetid: 597ae6d5-4938-4950-9f5e-b2280e816182
ms.openlocfilehash: 3bd6d392b15c37e22fd2a3639c99396e0e3d1749
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/03/2018
ms.locfileid: "32750866"
---
# <a name="ltservicecertificategt-of-ltservicecredentialsgt"></a>&lt;serviceCertificate&gt; – &lt;serviceCredentials&gt;
Zadejte certifikát X.509, který se použije k ověřování klientů pomocí režim zabezpečení zprávy.  
  
 \<system.ServiceModel>  
\<chování >  
\<serviceBehaviors >  
\<chování >  
\<– serviceCredentials >  
\<serviceCertificate >  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<serviceCertificate findValue="String"   
    storeLocation="LocalMachine/CurrentUser"  
    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`findValue`|Řetězec, který obsahuje hodnotu k vyhledání v úložišti certifikátů X.509. Typ obsažený v atributu musí splňovat požadavky na zadaný X509FindType. Výchozí hodnota je prázdný řetězec.|  
|`storeLocation`|Určuje umístění úložiště certifikátů X.509, který klient používá k ověření certifikátu serveru proti. Platné hodnoty patří:<br /><br /> -LocalMachine: úložiště certifikátů přiřazené k místnímu počítači.<br />-CurrentUser: úložiště certifikátů přiřazená aktuálnímu uživateli.<br /><br /> Výchozí hodnota je v místním počítači.|  
|`storeName`|Určuje název úložiště certifikátu X.509 otevřete. Platné hodnoty patří:<br /><br /> -Adresáře: Úložiště certifikátů pro ostatní uživatele.<br />-AuthRoot: Certifikát úložiště pro třetí strany certifikační autority (CA).<br />-CertificatAuthority: Úložiště certifikátů pro zprostředkující certifikační autority (CA).<br />-Nepovolené: Certifikát úložiště pro odvolané certifikáty.<br />-: Úložiště certifikátů my Pro osobní certifikáty.<br />-Root: Úložiště certifikátů pro důvěryhodné kořenové certifikační autority (CA).<br />-TrustedPeople: Úložiště certifikátů přímo důvěryhodných osob a prostředky.<br />-TrustedPublisher: Úložiště certifikátů pro přímo důvěryhodné vydavatele.<br /><br /> Výchozí hodnota je můj.|  
|`x509FindType`|Definuje typ vyhledávání X.509 provést. Platné hodnoty patří:<br /><br /> -FindByThumbprint<br />-FindBySubjectName.<br />-FindBySubjectDistinguishedName<br />-FindByIssuerName<br />-FindByIssuerDistinguishedName<br />-FindBySerialNumber<br />-FindByTimeValid<br />-FindByTimeNotYetValid<br />-FindByTemplateName<br />-FindByApplicationPolicy<br />-FindByCertificatePolicy<br />-FindByExtension<br />-FindByKeyUsage<br />-FindBySubjectKeyIdentifier<br /><br /> Typ obsažený v `findValue` atributu musí splňovat požadavky na zadaný X509FindType.<br /><br /> Výchozí hodnota je FindBySubjectDistinguishedName.|  
  
### <a name="child-elements"></a>Podřízené elementy  
 Žádné  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[\<– serviceCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|Určí pověření, které mají být použity v ověřování služby, a ověření přihlašovacích údajů klienta související nastavení.|  
  
## <a name="remarks"></a>Poznámky  
 Tento prvek slouží k určení certifikát X.509, který se použije k ověřování klientů pomocí režim zabezpečení zprávy. Pokud používáte certifikát, který se bude pravidelně obnovovat, se změní jeho kryptografický otisk. V takovém případě použijte název subjektu, jako `x509FindType` vzhledem k tomu, že certifikát můžete ho znova vydat se stejným názvem subjektu.  
  
 Další informace o použití elementu najdete v tématu [postupy: určení hodnot přihlašovacích údajů klienta](../../../../../docs/framework/wcf/how-to-specify-client-credential-values.md).  
  
## <a name="see-also"></a>Viz také  
 <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.ServiceCertificate%2A>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>  
 <xref:System.ServiceModel.Description.ServiceCredentials.ServiceCertificate%2A>  
 [Postupy: Zadání hodnot přihlašovacích údajů klienta](../../../../../docs/framework/wcf/how-to-specify-client-credential-values.md)  
 [Chování zabezpečení](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)

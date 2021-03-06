---
title: 'Postupy: Zadání hodnot přihlašovacích údajů klienta'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 82293d7f-471a-4549-8f19-0be890e7b074
ms.openlocfilehash: 9625400b855492ead12a5a2f1fa74f10164f6cdd
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/07/2018
ms.locfileid: "33806641"
---
# <a name="how-to-specify-client-credential-values"></a>Postupy: Zadání hodnot přihlašovacích údajů klienta
Pomocí služby Windows Communication Foundation (WCF), službu určit, jak ověření klienta ke službě. Službu můžete například stanovení, ověření klienta s certifikátem.  
  
### <a name="to-determine-the-client-credential-type"></a>K určení typu pověření klienta  
  
1.  Načtení metadat z koncového bodu služby metadat. Metadata se obvykle skládá z dva soubory: kód klienta na programovací jazyk podle vašeho výběru (výchozí hodnota je Visual C#) a konfigurační soubor XML. Jeden způsob, jak načíst metadata je použití nástroje Svcutil.exe vrátí kód klienta a konfigurace klienta. Další informace najdete v tématu [načítání metadat](../../../docs/framework/wcf/feature-details/retrieving-metadata.md) a [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).  
  
2.  Otevřete konfigurační soubor XML. Pokud používáte nástroje Svcutil.exe, výchozí název souboru je Output.config.  
  
3.  Najít  **\<zabezpečení >** element s **režimu** atribut (**< režim zabezpečení =** `MessageOrTransport` **>** kde `MessageOrTransport` je nastavena na jeden z režimů zabezpečení.  
  
4.  Najděte podřízený element, který odpovídá hodnotě režimu. Například, pokud režim je nastaven na **zpráva**, Najít  **\<zpráva >** obsažené v elementu  **\<zabezpečení >** element.  
  
5.  Poznamenejte si hodnotu přiřazenou **clientCredentialType** atribut. Skutečná hodnota závisí na režimu, který se používá, přenos nebo zprávy.  
  
 Následující kód ukazuje konfigurace pro klienta pomocí zabezpečení zpráv a které vyžadují certifikát pro ověření klienta.  
  
```xml  
<security mode="Message">  
    <transport clientCredentialType="Windows" proxyCredentialType="None"  
        realm="" />  
     <message clientCredentialType="Certificate" negotiateServiceCredential="true"  
    algorithmSuite="Default" establishSecurityContext="true" />  
</security>  
```  
  
## <a name="example-tcp-transport-mode-with-certificate-as-client-credential"></a>Příklad: Režim přenosu protokolu TCP s certifikátem jako pověření klienta  
 Tento příklad nastaví režim zabezpečení pro režim přenosu a nastaví hodnotu přihlašovacích údajů klienta s certifikátem X.509. Následující postupy ukazují, jak nastavit hodnotu přihlašovacích údajů klienta na straně klienta v kódu a konfigurace. Předpokladem je, že jste použili [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) vrátit metadata (kódu a konfigurace) ze služby. Další informace najdete v tématu [postupy: vytvoření klienta](../../../docs/framework/wcf/how-to-create-a-wcf-client.md).  
  
#### <a name="to-specify-the-client-credential-value-on-the-client-in-code"></a>Zadejte hodnotu přihlašovacích údajů klienta na straně klienta v kódu  
  
1.  Použití [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) pro generování kódu a konfigurace ze služby.  
  
2.  Vytvoření instance klienta WCF pomocí generovaného kódu.  
  
3.  U třídy klienta nastavena <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> vlastnost <xref:System.ServiceModel.ClientBase%601> třída na odpovídající hodnotu. Tento příklad nastaví vlastnost na certifikát X.509 pomocí <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> metodu <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential> třídy.  
  
     [!code-csharp[c_TcpService#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_tcpservice/cs/source.cs#4)]
     [!code-vb[c_TcpService#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_tcpservice/vb/source.vb#4)]  
  
     Můžete použít libovolnou výčtech <xref:System.Security.Cryptography.X509Certificates.X509FindType> třídy. Název předmětu je zde použita v případě, že certifikát mění (z důvodu datum vypršení platnosti). Použití v názvu subjektu umožňuje infrastruktury vyhledejte certifikát znovu.  
  
#### <a name="to-specify-the-client-credential-value-on-the-client-in-configuration"></a>Zadejte hodnotu přihlašovacích údajů klienta v klientském počítači v konfiguraci  
  
1.  Přidat [ \<chování >](../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) elementu, který chcete [ \<chování >](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element.  
  
2.  Přidat [ \<clientCredentials >](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elementu, který chcete [ \<chování >](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element. Nastavte požadované `name` atribut na odpovídající hodnotu.  
  
3.  Přidat [ \<clientCertificate >](../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md) elementu, který chcete [ \<clientCredentials >](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) element.  
  
4.  Nastavte následující atributy odpovídající hodnoty: `storeLocation`, `storeName`, `x509FindType`, a `findValue`, jak je znázorněno v následujícím kódu. Další informace o certifikátech najdete v tématu [práce s certifikáty](../../../docs/framework/wcf/feature-details/working-with-certificates.md).  
  
    ```xml  
    <behaviors>  
       <endpointBehaviors>  
          <behavior name="endpointCredentialBehavior">  
            <clientCredentials>  
              <clientCertificate findValue="Contoso.com"   
                                 storeLocation="LocalMachine"  
                                 storeName="TrustedPeople"  
                                 x509FindType="FindBySubjectName" />  
            </clientCredentials>  
          </behavior>  
       </endpointBehaviors>  
    </behaviors>  
    ```  
  
5.  Při konfiguraci klienta, určete chování, a to nastavením `behaviorConfiguration` atribut `<endpoint>` elementu, jak je znázorněno v následujícím kódu. Koncový bod elementu je podřízená [ \<klienta >](../../../docs/framework/configure-apps/file-schema/wcf/client.md) element. Také, zadejte název konfigurace vazeb nastavením `bindingConfiguration` atribut vazby pro klienta. Pokud používáte generovaného konfiguračního souboru, název vazby je automaticky vytvořen. V tomto příkladu je název `"tcpBindingWithCredential"`.  
  
    ```xml  
    <client>  
      <endpoint name =""  
                address="net.tcp://contoso.com:8036/aloha"  
                binding="netTcpBinding"  
                bindingConfiguration="tcpBindingWithCredential"  
                behaviorConfiguration="endpointCredentialBehavior" />  
    </client>  
    ```  
  
## <a name="see-also"></a>Viz také  
 <xref:System.ServiceModel.NetTcpBinding>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>  
 <xref:System.ServiceModel.ClientBase%601>  
 <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>  
 [Programování zabezpečení WCF](../../../docs/framework/wcf/feature-details/programming-wcf-security.md)  
 [Výběr typu přihlašovacích údajů](../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [Nástroj metadat modelu služby (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)  
 [Práce s certifikáty](../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [Postupy: Vytvoření klienta](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 [\<netTcpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)  
 [\<zabezpečení >](../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)  
 [\<Zpráva >](../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-nettcpbinding.md)  
 [\<chování >](../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)  
 [\<chování >](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)  
 [\<clientCertificate >](../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)  
 [\<clientCredentials >](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)

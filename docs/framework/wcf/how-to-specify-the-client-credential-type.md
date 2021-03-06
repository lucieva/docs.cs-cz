---
title: 'Postupy: Určení typu pověření klienta'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security credentials, adding to SOAP messages
- WCF, security
ms.assetid: 10f51bee-5f92-4c1a-9126-fa5418535d8f
ms.openlocfilehash: 5e1ff85d8a0bd45c87786f98c2cafe06472052b0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/04/2018
ms.locfileid: "33499334"
---
# <a name="how-to-specify-the-client-credential-type"></a>Postupy: Určení typu pověření klienta
Po nastavení režimu zabezpečení (přenos nebo zpráv), máte možnost nastavení klienta typ přihlašovacích údajů. Tato vlastnost určuje, jaký typ přihlašovacích údajů klient musí poskytnout službě pro ověření. Další informace o nastavení režimu zabezpečení (nezbytným krokem před nastavením klienta typ přihlašovacích údajů) najdete v tématu [postupy: nastavení režimu zabezpečení](../../../docs/framework/wcf/how-to-set-the-security-mode.md).  
  
### <a name="to-set-the-client-credential-type-in-code"></a>Chcete-li nastavit typ přihlašovacích údajů klienta v kódu  
  
1.  Vytvoření instance vazby, který bude používán službou. Tento příklad používá <xref:System.ServiceModel.WSHttpBinding> vazby.  
  
2.  Nastavte <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> vlastnost na odpovídající hodnotu. Tento příklad používá režim zprávy.  
  
3.  Nastavte <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> vlastnost na odpovídající hodnotu. Tento příklad nastaví ho na použití ověřování systému Windows (<xref:System.ServiceModel.MessageCredentialType.Windows>).  
  
     [!code-csharp[c_ProgrammingSecurity#14](../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#14)]
     [!code-vb[c_ProgrammingSecurity#14](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#14)]  
  
### <a name="to-set-the-client-credential-type-in-configuration"></a>Chcete-li nastavit typ přihlašovacích údajů klienta v konfiguraci  
  
1.  Přidat [ \<system.serviceModel >](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element konfiguračního souboru.  
  
2.  Jako podřízený element přidat [ \<vazby >](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) element.  
  
3.  Přidejte příslušné vazby. Tento příklad používá [ \<wsHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) element.  
  
4.  Přidat [ \<vazby >](../../../docs/framework/misc/binding.md) elementu a sadu `name` atribut na odpovídající hodnotu. Tento příklad používá název "SecureBinding".  
  
5.  Přidat `<security>` vazby. Nastavte `mode` atribut na odpovídající hodnotu. Tento příklad ji nastaví na `"Message"`.  
  
6.  Přidat buď `<message>` nebo `<transport>` elementu, počítáno od režim zabezpečení. Nastavte `clientCredentialType` atribut na odpovídající hodnotu. Tento příklad používá `"Windows"`.  
  
    ```xml  
    <system.serviceModel>  
      <bindings>  
        <wsHttpBinding>  
          <binding name="SecureBinding">  
            <security mode="Message">  
                 <message clientCredentialType="Windows" />  
             </security>  
          </binding>  
        </wsHttpBinding>  
      </bindings>  
    </system.serviceModel>  
    ```  
  
## <a name="see-also"></a>Viz také  
 [Zabezpečení služeb](../../../docs/framework/wcf/securing-services.md)  
 [Postupy: Nastavení režimu zabezpečení](../../../docs/framework/wcf/how-to-set-the-security-mode.md)

---
title: '&lt;textMessageEncoding&gt;'
ms.date: 03/30/2017
ms.assetid: e6d834d0-356e-45eb-b530-bbefbb9ec3f0
ms.openlocfilehash: e684c21c0b1360a9b270214ebe7b3ad00b42657f
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/06/2018
ms.locfileid: "43861957"
---
# <a name="lttextmessageencodinggt"></a>&lt;textMessageEncoding&gt;
Určuje kódování znaků a verzování zprávy použité pro textově založené zprávy XML.  
  
 \<system.serviceModel>  
\<vazby >  
\<třídě customBinding >  
\<Vytvoření vazby >  
\<textMessageEncoding >  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<textMessageEncoding maxReadPoolSize="Integer"  
   maxWritePoolSize="Integer"  
   messageVersion="Soap11Addressing10/Soap12Addressing10"  
      writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|maxReadPoolSize|Celé číslo, které určuje, kolik zpráv lze souběžně číst bez přidělení nových čtecích zařízení. Větší velikosti fondů byl systém odolnější vůči špičky aktivity za cenu větší pracovní sadu. Výchozí hodnota je 64.|  
|maxWritePoolSize|Celé číslo, které určuje, kolik zpráv lze souběžně odesílat bez přidělení nových modulů pro zápis. Větší velikosti fondů byl systém odolnější vůči špičky aktivity za cenu větší pracovní sadu. Výchozí hodnota je 16.|  
|verze messageVersion|Určuje verzi protokolu SOAP zprávy odesílané pomocí vazby. Platné hodnoty jsou<br /><br /> -Soap11Addressing10<br />-Soap12Addressing10<br /><br /> Výchozí hodnota je Soap12Addressing10. Tento atribut je typu <xref:System.ServiceModel.Channels.MessageVersion>.|  
|writeEncoding|Určuje znakovou sadu kódování pro vysílání zpráv z vazby. Platné hodnoty jsou<br /><br /> -UnicodeFffeTextEncoding: Kódování BigEndian kódování Unicode<br />-Utf16TextEncoding: Kódování Unicode<br />-Utf8TextEncoding: kódování 8bitové<br /><br /> Výchozí hodnota je Utf8TextEncoding. Tento atribut je typu <xref:System.Text.Encoding>.|  
  
### <a name="child-elements"></a>Podřízené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[\<readerQuotas>](https://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|Definuje omezení složitosti zpráv SOAP, které mohou být zpracovány koncovými body nakonfigurovaným s touto vazbou. Tento prvek je typu <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.|  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[\<Vytvoření vazby >](../../../../../docs/framework/misc/binding.md)|Definuje všechny možnosti vázání pro vlastní vazbu.|  
  
## <a name="remarks"></a>Poznámky  
 Kódování je proces transformace zprávu do sekvence bajtů. Dekódování je opačný proces. Windows Communication Foundation (WCF) zahrnuje tři typy kódování zprávy protokolu SOAP: Text, binární soubor a zpráv přenosu optimalizace mechanismus (MTOM).  
  
 Kódování textu reprezentována `textMessageEncoding` prvek je interaktivní, ale nejméně efektivní kodéru zpráv XML.  Kodér textu vytvoří textových zpráv na lince. Zprávy vytvořené v tomto kodéru jsou vhodné pro WS-* na základě spolupráce. Webová služba nebo klient webové služby obecně by rozuměla textové XML. Přenášení velkých bloků binárních dat jako text je však nejméně efektivní způsob pro kódování zpráv XML.  
  
## <a name="example"></a>Příklad  
  
```xml  
<textMessageEncoding maxReadPoolSize="211"  
    maxWritePoolSize="2132"  
    messageVersion="Soap12Addressing10"  
    textEncoding="utf-8" />  
```  
  
## <a name="see-also"></a>Viz také  
 <xref:System.ServiceModel.Configuration.TextMessageEncodingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>  
 <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>  
 [Výběr kodéru zprávy](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 [Kódování zpráv](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)  
 [Vazby](../../../../../docs/framework/wcf/bindings.md)  
 [Rozšíření vazeb](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [Vlastní vazby](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [\<třídě customBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)

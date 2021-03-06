---
title: Programování na úrovni kanálu klienta
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3b787719-4e77-4e77-96a6-5b15a11b995a
ms.openlocfilehash: ff399a2f3a4b86404695502fb002ee6920bea758
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/04/2018
---
# <a name="client-channel-level-programming"></a>Programování na úrovni kanálu klienta
Toto téma popisuje, jak psát aplikace klienta Windows Communication Foundation (WCF) bez použití <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType> třídy a jeho přidružený objekt modelu.  
  
## <a name="sending-messages"></a>Zasílání zpráv  
 Aby byl připraven k odesílání zpráv a přijímat a zpracovávat odpovědi, jsou požadovány následující kroky:  
  
1.  Vytvoření vazby.  
  
2.  Vytvoření postupu kanálu.  
  
3.  Vytvoření kanálu.  
  
4.  Odeslání požadavku a odpovědi pro čtení.  
  
5.  Zavřete všechny objekty kanálu.  
  
#### <a name="creating-a-binding"></a>Vytváření vazby  
 Podobně jako přijímající případ (najdete v části [programování na úrovni služby kanálů](../../../../docs/framework/wcf/extending/service-channel-level-programming.md)), odesílání zpráv spustí tak, že vytvoříte vazbu. Tento příklad vytvoří novou <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> a přidá <xref:System.ServiceModel.Channels.HttpTransportBindingElement?displayProperty=nameWithType> k jeho elementy kolekce.  
  
#### <a name="building-a-channelfactory"></a>Vytváření ChannelFactory  
 Místo vytváření <xref:System.ServiceModel.Channels.IChannelListener?displayProperty=nameWithType>, momentálně se nám vytvořit <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType> voláním <xref:System.ServiceModel.ChannelFactory.CreateFactory%2A?displayProperty=nameWithType> na vazby, kde parametr typu je <xref:System.ServiceModel.Channels.IRequestChannel?displayProperty=nameWithType>. Při naslouchacího procesu kanálu se používá na straně, která čeká na příchozí zprávy, objekty Factory kanál používá na straně, který iniciuje komunikace k vytvoření kanálu. Stejně jako naslouchací procesy kanál objekty Factory kanál musí být otevřeno nejprve předtím, než mohou být použity.  
  
#### <a name="creating-a-channel"></a>Vytvoření kanálu  
 Potom říkáme <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A?displayProperty=nameWithType> k vytvoření <xref:System.ServiceModel.Channels.IRequestChannel>. Toto volání má adresu koncového bodu, se kterým chcete komunikovat pomocí nového kanálu vytváří. Jakmile jsme kanál, jsme zavolat otevřete vložit soubor do stavu připraven na komunikaci. V závislosti na povaze přenos volání otevřete mohou iniciovat připojení ke koncovému bodu cílový nebo může nedělat nic vůbec v síti.  
  
#### <a name="sending-a-request-and-reading-the-reply"></a>Odesílání požadavku a odpovědi pro čtení  
 Po máme otevřenou kanál, můžeme vytvořit zprávu a použijete metodu požadavku kanálu k odeslání požadavku a čekat na odpověď opět online. Po návratu tato metoda máme odpovědi, která jsme může číst a zjistěte, co byla odpověď pro koncový bod.  
  
#### <a name="closing-objects"></a>Zavírání objektů  
 Aby se zabránilo úniku prostředky, můžeme zavřít objekty použitých při komunikaci, pokud už je potřeba.  
  
 Následující příklad kódu ukazuje základní klient používá k odeslání zprávy a čtení odpovědi kanálu.  
  
 [!code-csharp[ChannelProgrammingBasic#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/channelprogrammingbasic/cs/clientprogram.cs#2)]
 [!code-vb[ChannelProgrammingBasic#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/channelprogrammingbasic/vb/clientprogram.vb#2)]

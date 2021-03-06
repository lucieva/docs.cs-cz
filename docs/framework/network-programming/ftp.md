---
title: FTP
ms.date: 03/30/2017
helpviewer_keywords:
- FTP
ms.assetid: 9b43f8b4-89d7-46a7-89fc-71aca916dd32
ms.openlocfilehash: 0f35cb5c106d041a771d17a6e528cbbc1d38042b
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2018
ms.locfileid: "50187670"
---
# <a name="ftp"></a>FTP
Rozhraní .NET Framework poskytuje komplexní podporu pro protokolu FTP se <xref:System.Net.FtpWebRequest> a <xref:System.Net.FtpWebResponse> třídy. Tyto třídy jsou odvozeny z <xref:System.Net.WebRequest> a <xref:System.Net.WebResponse>. Ve většině případů <xref:System.Net.WebRequest> a <xref:System.Net.WebResponse> třídy poskytují vše, co je to nezbytně nutné k požadavku, ale pokud potřebujete přístup k FTP funkcím vystavena jako vlastnosti, můžete přetypovat na tyto třídy <xref:System.Net.FtpWebRequest> nebo <xref:System.Net.FtpWebResponse>.  
  
## <a name="examples"></a>Příklady  
 Další informace naleznete v následujících tématech: [postupy: stahování souborů přes FTP](../../../docs/framework/network-programming/how-to-download-files-with-ftp.md), [postupy: nahrávání souborů s využitím protokolu FTP](../../../docs/framework/network-programming/how-to-upload-files-with-ftp.md), a [postupy: výpis obsahu adresáře s využitím protokolu FTP](../../../docs/framework/network-programming/how-to-list-directory-contents-with-ftp.md).  
  
## <a name="ftp-and-proxies"></a>FTP a proxy servery  
 Pokud proxy server (určená <xref:System.Net.FtpWebRequest.Proxy%2A> vlastnost) je proxy server HTTP, pak pouze <xref:System.Net.WebRequestMethods.Ftp.DownloadFile>, <xref:System.Net.WebRequestMethods.Ftp.ListDirectory>, a <xref:System.Net.WebRequestMethods.Ftp.ListDirectoryDetails> příkazy jsou podporovány.  
  
## <a name="see-also"></a>Viz také  
 [Přístup k internetu přes proxy server](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)  
 [Ukázky programování sítě](../../../docs/framework/network-programming/network-programming-samples.md)  
 [Ukázka technologie klienta FTP](https://go.microsoft.com/fwlink/?LinkID=179557)  
 [Ukázka technologie Průzkumníka serveru FTP](https://go.microsoft.com/fwlink/?LinkID=179569)  
 [Použití aplikačních protokolů](../../../docs/framework/network-programming/using-application-protocols.md)

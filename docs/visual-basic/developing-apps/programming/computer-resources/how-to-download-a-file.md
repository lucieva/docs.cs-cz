---
title: 'Postupy: Stažení souboru v jazyce Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- downloading Internet resources [Visual Basic], files
- downloading files [Visual Basic]
- remote computers [Visual Basic], downloading from
- files [Visual Basic], downloading
- files [Visual Basic], transferring
ms.assetid: ac479f81-c0e2-4b99-af73-217f446b73da
ms.openlocfilehash: b0dc95674e17a7aba9b04a8b7e0b82c9c97c4180
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/01/2018
ms.locfileid: "43385546"
---
# <a name="how-to-download-a-file-in-visual-basic"></a>Postupy: Stažení souboru v jazyce Visual Basic
<xref:Microsoft.VisualBasic.Devices.Network.DownloadFile%2A> Metodu je možné stáhnout soubor vzdálené a uloží je do určitého umístění. Pokud `ShowUI` parametr je nastaven na `True`, zobrazí se dialogové okno zobrazuje průběh stahování a uživatelé si můžou na zrušení operace. Ve výchozím nastavení nejsou přepsány existující soubory se stejným názvem. Pokud chcete přepsat existující soubory, nastavte `overwrite` parametr `True`.  
  
 Následující podmínky mohou způsobit výjimku:  
  
-   Název disku je neplatný (<xref:System.ArgumentException>).  
  
-   Nebyla zadána potřebné ověřovací (<xref:System.UnauthorizedAccessException> nebo <xref:System.Security.SecurityException>).  
  
-   Server neobjeví odpověď během zadaného `connectionTimeout` (<xref:System.TimeoutException>).  
  
-   Požadavek se zamítne na webu (<xref:System.Net.WebException>).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
> [!IMPORTANT]
>  Nečiňte rozhodnutí o obsahu souboru na základě jeho názvu. Například soubor Form1.vb nemusí být zdrojový soubor jazyka Visual Basic. Před použitím dat ve své aplikaci ověřte všechny vstupy. Soubor nemusí mít obsah, jaký očekáváte, a metody pro čtení z tohoto souboru mohou selhat.  
  
### <a name="to-download-a-file"></a>Ke stažení souboru  
  
-   Použití `DownloadFile` metoda ke stažení souboru, zadáte umístění cílového souboru jako řetězec nebo identifikátor URI a zadání umístění, kam chcete soubor uložit. Tento příklad stáhne soubor `WineList.txt` z `http://www.cohowinery.com/downloads` a ukládá ji do `C:\Documents and Settings\All Users\Documents`:  
  
     [!code-vb[VbResourceTasks#9](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-download-a-file_1.vb)]  
  
### <a name="to-download-a-file-specifying-a-time-out-interval"></a>Ke stažení souboru, intervalem časového limitu  
  
-   Použití `DownloadFile` metoda ke stažení souboru, určení umístění cílového souboru jako řetězec nebo identifikátor URI, zadáte umístění, kam chcete uložit soubor a intervalem časového limitu v milisekundách (výchozí hodnota je 1000). Tento příklad stáhne soubor `WineList.txt` z `http://www.cohowinery.com/downloads` a ukládá ji do `C:\Documents and Settings\All Users\Documents`, intervalem časového limitu 500 MS:  
  
     [!code-vb[VbResourceTasks#10](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-download-a-file_2.vb)]  
  
### <a name="to-download-a-file-supplying-a-user-name-and-password"></a>Ke stažení souboru, zadávání uživatelského jména a hesla  
  
-   Použití `DownLoadFile` metoda ke stažení souboru, zadáte umístění cílového souboru jako řetězec nebo identifikátor URI a určení umístění, kam chcete uložit soubor, uživatelské jméno a heslo. Tento příklad stáhne soubor `WineList.txt` z `http://www.cohowinery.com/downloads` a ukládá ji do `C:\Documents and Settings\All Users\Documents`, s uživatelským jménem `anonymous` a heslo necháte prázdné.  
  
     [!code-vb[VbResourceTasks#11](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-download-a-file_3.vb)]  
  
    > [!IMPORTANT]
    >  Protokol FTP používá `DownLoadFile` metoda odesílá informace, včetně hesel ve formátu prostého textu a neměli byste používat k přenosu citlivých informací.  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualBasic.Devices.Network>  
 <xref:Microsoft.VisualBasic.Devices.Network.DownloadFile%2A>  
 [Postupy: Nahrání souboru](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-upload-a-file.md)  
 [Postupy: Analýza cest k souborům](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)

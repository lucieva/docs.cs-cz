---
title: Odpovědnosti pro vývojáře přepisování výchozího chování
ms.date: 03/30/2017
ms.assetid: c6909ddd-e053-46a8-980c-0e12a9797be1
ms.openlocfilehash: 90b8eedcc80c330a39efe97b6427beebeca913f9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/04/2018
ms.locfileid: "33365251"
---
# <a name="responsibilities-of-the-developer-in-overriding-default-behavior"></a>Odpovědnosti pro vývojáře přepisování výchozího chování
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] nevynucuje následující požadavky, ale není definován chování, pokud nejsou splněny tyto požadavky.  
  
-   Přepsání metody nesmějí provádět volání <xref:System.Data.Linq.DataContext.SubmitChanges%2A> nebo <xref:System.Data.Linq.Table%601.Attach%2A>. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] vyvolá výjimku, pokud tyto metody jsou volány v přepsání metody.  
  
-   Přepsání metody nelze použít ke spuštění, potvrzení nebo zastavte transakce. <xref:System.Data.Linq.DataContext.SubmitChanges%2A> Operace v rámci transakce. Vnitřní vnořené transakce může narušovat vnější transakci. Přepsání metody zatížení můžete spustit transakci, až poté, co se určit, že operace neprobíhá v <xref:System.Transactions.Transaction>.  
  
-   Přepsání metody se očekává postupujte podle příslušných optimistickou metodu souběžného mapování. Očekává se vyvolá metodu přepsání <xref:System.Data.Linq.ChangeConflictException> došlo ke konfliktu optimistickou metodu souběžného v případech. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] zachytí výjimku, aby mohl správně zpracovávat <xref:System.Data.Linq.DataContext.SubmitChanges%2A> možnost k dispozici na <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.  
  
-   Vytvoření (`Insert`) a `Update` přepsání metody se očekávají zpět hodnoty generované sloupce odpovídající členové objektu po úspěšném dokončení operace.  
  
     Například pokud `Order.OrderID` je namapovaná na sloupec identity (*autoincrement* primární klíč), pak se `InsertOrder()` přepsání metody musí načíst ID generované databáze a nastavte `Order.OrderID` člen tohoto ID. Časové razítko členy, musí být aktualizovány na časové razítko generované hodnoty a ujistěte se, že jsou aktualizované objekty konzistentní. Chyba potřebný k šíření hodnoty generované databáze může způsobit nekonzistence mezi databází a objekty sledovanými <xref:System.Data.Linq.DataContext>.  
  
-   Je zodpovědností uživatele k vyvolání správné dynamické rozhraní API. Například v aktualizaci potlačí metodu, jenom <xref:System.Data.Linq.DataContext.ExecuteDynamicUpdate%2A> lze volat. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] zjistit nebo ověřte, zda vyvolanou metodu dynamické odpovídá příslušné operace. Pokud nepoužitelných metoda je volána (například <xref:System.Data.Linq.DataContext.ExecuteDynamicDelete%2A> pro objekt aktualizovat), výsledky nejsou definovány.  
  
-   Nakonec přepsání metoda očekává se stanovené operaci provést. Sémantika [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] operací, jako je přes načítání, odložené načítání, a <xref:System.Data.Linq.DataContext.SubmitChanges%2A>) vyžadují přepsání poskytnout stanovené službu. Například zatížení přepsat, který právě vrátí prázdnou kolekci bez kontroly, že obsah v databázi pravděpodobně povede k nekonzistentní data.  
  
## <a name="see-also"></a>Viz také  
 [Přizpůsobení operací vložení, aktualizace a odstranění](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)

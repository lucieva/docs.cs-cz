---
title: N-vrstvé a vzdálené aplikace s LINQ to SQL
ms.date: 03/30/2017
ms.assetid: 854a1cdd-53cb-45f5-83ca-63962a9b3598
ms.openlocfilehash: 10eec92dcb9fdc5329f2cf19336ccc11f8bd181a
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/02/2018
ms.locfileid: "48032579"
---
# <a name="n-tier-and-remote-applications-with-linq-to-sql"></a>N-vrstvé a vzdálené aplikace s LINQ to SQL
Můžete vytvářet n vrstvá nebo vícevrstvé aplikace, které používají [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Obvykle [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] kontext dat, tříd entit a logiky konstrukce dotazů jsou umístěny ve střední vrstvě jako vrstva přístupu k datům (DAL). Obchodní logika a veškerých dat, dočasné je zcela implementovat v částečné třídy a metody entity a kontext dat, nebo se dá implementovat v samostatné třídy.

 Klient nebo prezentační vrstvy volá metody na střední vrstvě pro vzdálené rozhraní a DAL na dané úrovni spustí dotazy nebo uložené procedury, které jsou mapovány na <xref:System.Data.Linq.DataContext> metody. Střední vrstva vrací data klientů obvykle jako reprezentace XML entity nebo objekty proxy.

 Ve střední vrstvě entity jsou vytvořeny pomocí kontext dat, který sleduje jejich stavu a spravuje pro odložené načítání z a odeslání změn do databáze. Tyto entity jsou "připojené" k `DataContext`. Ale po entity, které se odesílají na jinou vrstvu prostřednictvím serializace, budou odpojená, což znamená, že `DataContext` se už ke sledování jejich stavu. Entity, které klient posílá zpět aktualizací musíte znova připojit ke kontextu dat před [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] můžete odeslat změny do databáze. Klient je odpovědný za poskytnutí původní hodnoty a/nebo časová razítka zpět do střední vrstvy, pokud jsou požadované kontroly optimistické souběžnosti.

 V aplikacích ASP.NET <xref:System.Web.UI.WebControls.LinqDataSource> spravuje většinu Tato složitost. Další informace najdete v tématu [NIB: Přehled ovládacího prvku webového serveru zdroje dat LinqDataSource](https://msdn.microsoft.com/library/104cfc3f-7385-47d3-8a51-830dfa791136).

## <a name="additional-resources"></a>Další prostředky
 Další informace o tom, jak implementovat n vrstvé aplikace, které používají [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], naleznete v následujících tématech:

-   [N-vrstvé nastavení LINQ to SQL s ASP.NET](../../../../../../docs/framework/data/adonet/sql/linq/linq-to-sql-n-tier-with-aspnet.md)

-   [N-vrstvé nastavení LINQ to SQL s webovými službami](../../../../../../docs/framework/data/adonet/sql/linq/linq-to-sql-n-tier-with-web-services.md) 

-   [Implementace N-vrstvé obchodní logiky](../../../../../../docs/framework/data/adonet/sql/linq/implementing-business-logic-linq-to-sql.md)

-   [Operace načítání dat a vytvoření, aktualizace a odstranění v N-úrovňových aplikacích (LINQ to SQL)](../../../../../../docs/framework/data/adonet/sql/linq/data-retrieval-and-cud-operations-in-n-tier-applications.md)

 Další informace o n vrstvé aplikace, které používají datové sady ADO.NET naleznete v tématu [práce s datovými sadami ve vícevrstvých aplikacích](/visualstudio/data-tools/work-with-datasets-in-n-tier-applications).

## <a name="see-also"></a>Viz také
 [Základní informace](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)

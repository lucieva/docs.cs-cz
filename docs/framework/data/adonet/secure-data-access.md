---
title: Zabezpečený přístup k datům
ms.date: 03/30/2017
ms.assetid: 473ebd69-21a3-4627-b95e-4e04d035c56f
ms.openlocfilehash: e5bb96a091dcd64f12d086d864643d00c34d8f17
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2018
ms.locfileid: "50185937"
---
# <a name="secure-data-access"></a>Zabezpečený přístup k datům
Chcete-li psát bezpečný kód ADO.NET, budete muset pochopit mechanizmy zabezpečení k dispozici v základní úložiště dat nebo databázi. Také je potřeba zvážit důsledky zabezpečení jiných funkcích nebo komponenty, které vaše aplikace může obsahovat.  
  
## <a name="authentication-authorization-and-permissions"></a>Ověřování, autorizace a oprávnění  
 Při připojování k serveru Microsoft SQL Server, můžete použít ověřování Windows, označované také jako integrované zabezpečení, které používá identity aktuální aktivního uživatele Windows namísto předání ID uživatele a heslo. Ověřování Windows je důrazně doporučujeme, protože přihlašovací údaje uživatele nejsou zveřejněné v připojovacím řetězci. Pokud pro připojení k serveru SQL Server nemůže používat ověřování Windows, zvažte vytvoření připojovací řetězce za běhu pomocí <xref:System.Data.SqlClient.SqlConnectionStringBuilder>.  
  
 Přihlašovací údaje použité pro ověřování musí být zpracována různě v závislosti na typu aplikace. Například v aplikaci Windows Forms, uživatel může být vyzváni k zadání ověřovacích informací nebo přihlašovacích údajů uživatele Windows je možné. Však webovou aplikaci často přistupuje k datům pomocí pověření podle samotná aplikace, nikoli podle uživatele.  
  
 Po ověření uživatele oboru jejich akce závisí na, které jste udělili oprávnění k nim. Vždy postupujte podle principu nejnižší úrovně oprávnění a udělit pouze oprávnění, která jsou naprosto nezbytná.  
  
 Další informace najdete v tématu následující prostředky.  
  
|Prostředek|Popis|  
|--------------|-----------------|  
|[Ochrana informací o připojení](../../../../docs/framework/data/adonet/protecting-connection-information.md)|Popisuje osvědčené postupy zabezpečení a techniky pro ochranu informací o připojení, jako je třeba použití chráněné konfigurace šifrování připojovací řetězce.|  
|[Doporučení pro strategií přístupu dat](https://msdn.microsoft.com/library/72411f32-d12a-4de8-b961-e54fca7faaf5)|Poskytuje doporučení pro přístup k datům a provádění databázových operací.|  
|[Tvůrci připojovacích řetězců](../../../../docs/framework/data/adonet/connection-string-builders.md)|Popisuje, jak sestavit připojovací řetězce ze vstupu uživatele v době běhu.|  
|[Přehled zabezpečení SQL Serveru](../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)|Popisuje architekturu zabezpečení systému SQL Server.|  
  
## <a name="parameterized-commands-and-sql-injection"></a>Příkazy s parametry a útok prostřednictvím injektáže SQL  
 Používat příkazy s parametry pomáhá chránit před útoky prostřednictvím injektáže SQL, ve kterých útočník "vkládá" příkaz do příkazu SQL tohoto ohrožení zabezpečení na serveru. Příkazy s parametry pomáhalo chránit před útoky prostřednictvím injektáže SQL tím, že zajišťuje, že hodnoty přijatých z externího zdroje jsou předány jako pouze hodnoty a není součástí příkazu jazyka Transact-SQL. V důsledku toho příkazy Transact-SQL, které jsou vloženy do hodnoty nebudou provedeny ve zdroji dat. Místo toho jsou vyhodnoceny výhradně jako hodnotu parametru. Kromě výhod zabezpečení příkazy s parametry poskytují vhodnou metodu pro uspořádání hodnoty předané s příkazem jazyka Transact-SQL nebo uloženou proceduru.  
  
 Další informace o použití příkazy s parametry najdete v následující prostředky.  
  
|Prostředek|Popis|  
|--------------|-----------------|  
|[Parametry adaptéru dat](../../../../docs/framework/data/adonet/dataadapter-parameters.md)|Popisuje, jak používat parametry `DataAdapter`.|  
|[Úpravy dat pomocí uložených procedur](../../../../docs/framework/data/adonet/modifying-data-with-stored-procedures.md)|Popisuje, jak určit parametry a získat návratovou hodnotu.|  
|[Správa oprávnění pomocí uložených procedur na SQL Serveru](../../../../docs/framework/data/adonet/sql/managing-permissions-with-stored-procedures-in-sql-server.md)|Popisuje způsob použití uložených procedur SQL serveru k zapouzdření přístup k datům.|  
  
## <a name="script-exploits"></a>Zneužití skriptu  
 Zneužití skriptu je jiná forma vkládání, který používá škodlivé znaků vložen do webové stránky. Prohlížeč nelze ověřit vložené znaky a zpracuje je v rámci stránky.  
  
 Další informace najdete v tématu následující prostředky.  
  
|Prostředek|Popis|  
|--------------|-----------------|  
|[Přehled zneužití skriptu](https://msdn.microsoft.com/library/772c7312-211a-4eb3-8d6e-eec0aa1dcc07)|Popisuje, jak můžete chránit proti skriptování a příkazu jazyka SQL zneužití.|  
  
## <a name="probing-attacks"></a>Zjišťování útoků  
 Informace z výjimky, jako je například název serveru, databáze nebo tabulky, útočníci často používají k připojení útoku na systém. Protože výjimky může obsahovat specifické informace o aplikaci nebo zdroj dat, můžete pomoct chránit vaše aplikace a zdroj dat lépe chráněné zveřejněním pouze základní informace o klientovi.  
  
 Další informace najdete v tématu následující prostředky.  
  
|Prostředek|Popis|  
|--------------|-----------------|  
|[Základy zpracování výjimek](../../../../docs/standard/exceptions/exception-handling-fundamentals.md)|Popisuje základní formy konstrukce try/catch/finally strukturované zpracování výjimek.|  
|[Doporučené postupy pro výjimky](../../../../docs/standard/exceptions/best-practices-for-exceptions.md)|Popisuje osvědčené postupy pro zpracování výjimek.|  
  
## <a name="protecting-microsoft-access-and-excel-data-sources"></a>Ochrana aplikace Microsoft Access a zdroje dat aplikace Excel  
 Aplikace Microsoft Access a Microsoft Excel může fungovat jako úložiště dat pro aplikaci ADO.NET při požadavky na zabezpečení jsou minimální, nebo neexistuje. Platí pro dětí jejich funkce zabezpečení, ale byste se neměli spoléhat na více než bránit meddling uninformed uživatelé. Fyzických datových souborů pro přístup a Excel existovat v systému souborů a musí být přístupný pro všechny uživatele. Díky tomu je zranitelný vůči útokům, které může vést ke ztrátě odcizení nebo data, protože soubory můžete snadno zkopírovat ani změnit. Když je potřeba robustního zabezpečení, pomocí SQL Server nebo jiné databáze na serveru kde fyzické datové soubory nejsou čitelné ze systému souborů.  
  
 Další informace o ochraně přístupu a Excelových dat najdete v následující prostředky.  
  
|Prostředek|Popis|  
|--------------|-----------------|  
|[Důležité informace a pokyny pro Access 2007](https://go.microsoft.com/fwlink/?LinkId=98354)|Popisuje postupy zabezpečení pro Access 2007 takové šifrování souborů, Správa hesel, převodu databáze na nové formáty ACCDB a ACCDE a pomocí jiné možnosti zabezpečení.|  
|[Pomáhá chránit databázi aplikace Access s zabezpečení individuální (MDB)](https://go.microsoft.com/fwlink/?LinkId=47697)|Platí pro přístup k 2003. Obsahuje pokyny pro implementaci zabezpečení na úrovni uživatele k ochraně dat v 2003 přístup.|  
|[Principy Role pracovní skupiny souborů informací o zabezpečení přístupu](https://support.microsoft.com/kb/305542)|Popisuje role a vztah informační soubor pracovní skupiny v zabezpečení přístupu 2003.|  
|[Často nejčastější dotazy o Microsoft zabezpečení přístupu pro aplikace Microsoft Access verze 2.0 až 2000](https://go.microsoft.com/fwlink/?LinkId=47698)|Verzi ke stažení aplikace Microsoft Access Security – nejčastější dotazy.|  
|[Řešení zabezpečení a ochrany](https://go.microsoft.com/fwlink/?LinkId=47703)|Představuje řešení běžných problémů se zabezpečením v aplikaci Excel 2003.|  
  
## <a name="enterprise-services"></a>Enterprise Services  
 COM + obsahuje vlastní model zabezpečení, která se spoléhá na účty systému Windows NT a zosobnění, procesu nebo vlákna. <xref:System.EnterpriseServices> Obor názvů obsahuje obálky, která umožňují aplikacím .NET pro integraci spravovaného kódu pomocí modelu COM + služeb zabezpečení prostřednictvím <xref:System.EnterpriseServices.ServicedComponent> třídy.  
  
 Další informace najdete v následujících prostředků.  
  
|Prostředek|Popis|  
|--------------|-----------------|  
|[Na základě rolí zabezpečení COM + a rozhraní .NET Framework](https://msdn.microsoft.com/library/02ab22ef-e5e2-4d29-b33a-6e03d94c4981)|Tento článek popisuje postup pro integraci spravovaného kódu zabezpečení služby COM +.|  
  
## <a name="interoperating-with-unmanaged-code"></a>Spolupráce s nespravovaným kódem  
 Rozhraní .NET Framework poskytuje pro interakci s nespravovaným kódem, včetně modelu COM komponenty modelu COM + služby, externí knihovny typů a řadě služeb operačního systému. Práce s nespravovaným kódem zahrnuje přejít mimo zónu zabezpečení pro spravovaný kód. Váš kód a jakýkoli kód, který volá musí mít povolení pro nespravovaný kód (<xref:System.Security.Permissions.SecurityPermission> s <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode> příznak zadán). Nespravovaný kód můžou představovat ohrožení zabezpečení nežádoucí na vaší aplikace. Proto byste se měli vyhnout spolupráce s nespravovaným kódem, pokud to není nezbytně nutné.  
  
 Další informace najdete v tématu následující prostředky.  
  
|Prostředek|Popis|  
|--------------|-----------------|  
|[Spolupráce s nespravovaným kódem](../../../../docs/framework/interop/index.md)|Obsahuje témata popisující, jak k vystavení komponent COM pro rozhraní .NET Framework a jak k vystavení součástí .NET Framework do modelu COM.|  
|[Rozšířená interoperabilita modelu COM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx)|Obsahuje Pokročilá témata, jako je například primárních sestavení vzájemné spolupráce, práce s vlákny a vlastní zařazování.|  
  
## <a name="see-also"></a>Viz také  
 [Zabezpečení aplikací ADO.NET](../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [SQL Server – zabezpečení](../../../../docs/framework/data/adonet/sql/sql-server-security.md)  
 [Doporučení pro strategií přístupu dat](https://msdn.microsoft.com/library/72411f32-d12a-4de8-b961-e54fca7faaf5)  
 [Ochrana informací o připojení](../../../../docs/framework/data/adonet/protecting-connection-information.md)  
 [Tvůrci připojovacích řetězců](../../../../docs/framework/data/adonet/connection-string-builders.md)  
 [ADO.NET spravovaných zprostředkovatelích a datové sady pro vývojáře](https://go.microsoft.com/fwlink/?LinkId=217917)

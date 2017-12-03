---
title: "Připojovací řetězce v technologii ADO.NET"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 745c5f95-2f02-4674-b378-6d51a7ec2490
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: bd787373b869c31727cfc0d027b6b98774b0d630
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="connection-strings-in-adonet"></a><span data-ttu-id="bbdc0-102">Připojovací řetězce v technologii ADO.NET</span><span class="sxs-lookup"><span data-stu-id="bbdc0-102">Connection Strings in ADO.NET</span></span>
<span data-ttu-id="bbdc0-103">Rozhraní .NET Framework 2.0 zavedl nové funkce pro práci s připojovací řetězce, včetně zavedení nových klíčových slov do Tvůrce třídy řetězec připojení, které usnadňují vytváření řetězců platné připojení v době běhu.</span><span class="sxs-lookup"><span data-stu-id="bbdc0-103">The .NET Framework 2.0 introduced new capabilities for working with connection strings, including the introduction of new keywords to the connection string builder classes, which facilitate creating valid connection strings at run time.</span></span>  
  
 <span data-ttu-id="bbdc0-104">Připojovací řetězec obsahuje inicializace informace, které se předá jako parametr ze zprostředkovatele dat pro zdroj dat.</span><span class="sxs-lookup"><span data-stu-id="bbdc0-104">A connection string contains initialization information that is passed as a parameter from a data provider to a data source.</span></span> <span data-ttu-id="bbdc0-105">Syntaxe závisí na poskytovateli dat a připojovací řetězec je analyzovat při pokusu o otevření připojení.</span><span class="sxs-lookup"><span data-stu-id="bbdc0-105">The syntax depends on the data provider, and the connection string is parsed during the attempt to open a connection.</span></span> <span data-ttu-id="bbdc0-106">Chyby syntaxe generování výjimek spuštění, ale jiné chyby dojít pouze po zdroj dat obdrží informace o připojení.</span><span class="sxs-lookup"><span data-stu-id="bbdc0-106">Syntax errors generate a run-time exception, but other errors occur only after the data source receives connection information.</span></span> <span data-ttu-id="bbdc0-107">Po ověření, zdroj dat použije možnosti zadaný v připojovacím řetězci a otevře připojení.</span><span class="sxs-lookup"><span data-stu-id="bbdc0-107">Once validated, the data source applies the options specified in the connection string and opens the connection.</span></span>  
  
 <span data-ttu-id="bbdc0-108">Formát připojovací řetězec je oddělený středníkem seznam párů klíč/hodnota parametru:</span><span class="sxs-lookup"><span data-stu-id="bbdc0-108">The format of a connection string is a semicolon-delimited list of key/value parameter pairs:</span></span>  
  
 `keyword1=value; keyword2=value;`  
  
 <span data-ttu-id="bbdc0-109">Klíčová slova nejsou velká a malá písmena a mezery mezi páry klíč/hodnota jsou ignorovány.</span><span class="sxs-lookup"><span data-stu-id="bbdc0-109">Keywords are not case sensitive, and spaces between key/value pairs are ignored.</span></span> <span data-ttu-id="bbdc0-110">Hodnoty mohou být velká a malá písmena, v závislosti na zdroji dat.</span><span class="sxs-lookup"><span data-stu-id="bbdc0-110">However, values may be case sensitive, depending on the data source.</span></span> <span data-ttu-id="bbdc0-111">Všechny hodnoty obsahující středníkem, apostrofech nebo dvojité uvozovky musí být uzavřena v uvozovkách.</span><span class="sxs-lookup"><span data-stu-id="bbdc0-111">Any values containing a semicolon, single quotation marks, or double quotation marks must be enclosed in double quotation marks.</span></span>  
  
 <span data-ttu-id="bbdc0-112">Platný připojovací řetězec syntaxe závisí na poskytovateli a vývoj v průběhu let z dřívějších rozhraní API jako ODBC událostí.</span><span class="sxs-lookup"><span data-stu-id="bbdc0-112">Valid connection string syntax depends on the provider, and has evolved over the years from earlier APIs like ODBC.</span></span> <span data-ttu-id="bbdc0-113">Zprostředkovatel dat .NET Framework pro SQL Server (SqlClient) zahrnuje mnoho prvků z starší syntaxe a je obecně flexibilnější s běžné syntaxi připojovacího řetězce.</span><span class="sxs-lookup"><span data-stu-id="bbdc0-113">The .NET Framework Data Provider for SQL Server (SqlClient) incorporates many elements from older syntax and is generally more flexible with common connection string syntax.</span></span> <span data-ttu-id="bbdc0-114">Jsou často stejně platný synonyma pro elementy syntaxe připojovacího řetězce, ale některé syntaxe a pravopisné chyby může způsobit problémy.</span><span class="sxs-lookup"><span data-stu-id="bbdc0-114">There are frequently equally valid synonyms for connection string syntax elements, but some syntax and spelling errors can cause problems.</span></span> <span data-ttu-id="bbdc0-115">Například "`Integrated Security=true`" je platná, zatímco "`IntegratedSecurity=true`" dojde k chybě.</span><span class="sxs-lookup"><span data-stu-id="bbdc0-115">For example, "`Integrated Security=true`" is valid, whereas "`IntegratedSecurity=true`" causes an error.</span></span> <span data-ttu-id="bbdc0-116">Kromě toho připojovací řetězce s vytvořeným za běhu z neověřený vstup uživatele může vést k útokům vkládání řetězce, ohrožující zabezpečení ve zdroji dat.</span><span class="sxs-lookup"><span data-stu-id="bbdc0-116">In addition, connection strings constructed at run time from unvalidated user input can lead to string injection attacks, jeopardizing security at the data source.</span></span>  
  
 <span data-ttu-id="bbdc0-117">K řešení těchto problémů, ADO.NET 2.0 zavedl nový Tvůrci řetězců pro připojení pro každého zprostředkovatele dat .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bbdc0-117">To address these problems, ADO.NET 2.0 introduced new connection string builders for each .NET Framework data provider.</span></span> <span data-ttu-id="bbdc0-118">Klíčová slova jsou zveřejněné jako vlastnosti, povolení syntaxi připojovacího řetězce k ověření před odesláním ke zdroji dat.</span><span class="sxs-lookup"><span data-stu-id="bbdc0-118">Keywords are exposed as properties, enabling connection string syntax to be validated before submission to the data source.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bbdc0-119">V tomto oddílu</span><span class="sxs-lookup"><span data-stu-id="bbdc0-119">In This Section</span></span>  
 [<span data-ttu-id="bbdc0-120">Tvůrci řetězců pro připojení</span><span class="sxs-lookup"><span data-stu-id="bbdc0-120">Connection String Builders</span></span>](../../../../docs/framework/data/adonet/connection-string-builders.md)  
 <span data-ttu-id="bbdc0-121">Ukazuje, jak používat `ConnectionStringBuilder` třídy vytvořit platný připojovací řetězce na dobu běhu.</span><span class="sxs-lookup"><span data-stu-id="bbdc0-121">Demonstrates how to use the `ConnectionStringBuilder` classes to construct valid connection strings at run time.</span></span>  
  
 [<span data-ttu-id="bbdc0-122">Připojovací řetězce a konfigurační soubory</span><span class="sxs-lookup"><span data-stu-id="bbdc0-122">Connection Strings and Configuration Files</span></span>](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md)  
 <span data-ttu-id="bbdc0-123">Demonstruje způsob ukládání a načítání připojovací řetězce v konfiguračních souborech.</span><span class="sxs-lookup"><span data-stu-id="bbdc0-123">Demonstrates how to store and retrieve connection strings in configuration files.</span></span>  
  
 [<span data-ttu-id="bbdc0-124">Syntaxi připojovacího řetězce</span><span class="sxs-lookup"><span data-stu-id="bbdc0-124">Connection String Syntax</span></span>](../../../../docs/framework/data/adonet/connection-string-syntax.md)  
 <span data-ttu-id="bbdc0-125">Popisuje postup konfigurace specifický pro zprostředkovatele připojovací řetězce pro `SqlClient`, `OracleClient`, `OleDb`, a `Odbc`.</span><span class="sxs-lookup"><span data-stu-id="bbdc0-125">Describes how to configure provider-specific connection strings for `SqlClient`, `OracleClient`, `OleDb`, and `Odbc`.</span></span>  
  
 [<span data-ttu-id="bbdc0-126">Ochrana informací o připojení</span><span class="sxs-lookup"><span data-stu-id="bbdc0-126">Protecting Connection Information</span></span>](../../../../docs/framework/data/adonet/protecting-connection-information.md)  
 <span data-ttu-id="bbdc0-127">Ukazuje techniky pro ochranu informace, které slouží k připojení ke zdroji dat.</span><span class="sxs-lookup"><span data-stu-id="bbdc0-127">Demonstrates techniques for protecting information used to connect to a data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbdc0-128">Viz také</span><span class="sxs-lookup"><span data-stu-id="bbdc0-128">See Also</span></span>  
 [<span data-ttu-id="bbdc0-129">Připojení ke zdroji dat</span><span class="sxs-lookup"><span data-stu-id="bbdc0-129">Connecting to a Data Source</span></span>](/cpp/data/odbc/connecting-to-a-data-source)  
 [<span data-ttu-id="bbdc0-130">ADO.NET spravované zprostředkovatelé a středisku pro vývojáře datové sady</span><span class="sxs-lookup"><span data-stu-id="bbdc0-130">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
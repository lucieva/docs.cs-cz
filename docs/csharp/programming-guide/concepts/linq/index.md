---
title: Language-Integrated Query (LINQ) (C#)
ms.date: 02/02/2017
ms.assetid: 19dd1782-905b-4a9d-a3e9-618453037fa2
ms.openlocfilehash: 108dc60285e51ab4cd703e668127a4ffd5fc1c74
ms.sourcegitcommit: fd8d4587cc26e53f0e27e230d6e27d828ef4306b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/16/2018
ms.locfileid: "49347809"
---
# <a name="language-integrated-query-linq"></a>Language Integrated Query (LINQ)

Language Integrated Query (LINQ) je název pro sadu technologií, v závislosti na integraci schopnosti příkazů jazyka přímo do jazyka C#. Tradičně dotazů na data jsou vyjádřené jako jednoduchý řetězce bez kontrolu typu v kompilaci čas nebo podporu technologie IntelliSense. Kromě toho budete muset učit jazyk dotazu pro každý typ zdroje dat: SQL databáze, dokumenty XML, různé webové služby a tak dále. S dotazy LINQ dotaz, který je typů prvotřídní jazykové konstrukce, stejně jako třídy, metody a události.

Pro vývojáře, který zapíše dotazy je většina viditelnou část "language-integrated" LINQ výrazu dotazu. Výrazy dotazů jsou napsané v deklarativní *syntaxe dotazu*. Pomocí syntaxe dotazu, můžete provádět filtrování, řazení a seskupení operací u zdrojů dat s minimálním kódu. Použijte stejné vzorce výrazu základního dotazu pro dotazování a transformaci dat v SQL Database, ADO .NET datové sady, dokumentů XML a datových proudů a kolekcí .NET.

Následující příklad znázorňuje operaci úplného dotazu. Dokončení operace zahrnuje vytvoření zdroje dat, definující výraz dotazu a zpracování dotazu v `foreach` příkazu.

[!code-csharp[csProgGuideLINQ#11](../../../../../samples/snippets/csharp/concepts/linq/index_1.cs)]

## <a name="query-expression-overview"></a>Přehled výrazu dotazu

-   Výrazy dotazu lze použít k dotazování a transformaci dat z libovolného zdroje data povolenými LINQ. Pomocí jediného dotazu můžete například načtení dat z SQL database a vytvořit datový proud XML jako výstup.  
  
-   Výrazy dotazu představují snadný na hlavní server, protože používají řadu známých konstrukcí jazyka C#.  
  
-   Proměnné ve výrazu dotazu jsou všechny silného typu, ale v mnoha případech není nutné explicitně zadat typ, protože kompilátor může odvodit ho. Další informace najdete v tématu [vztahy typů v LINQ dotaz operace](type-relationships-in-linq-query-operations.md).  
  
-   Dotaz není spuštěn, dokud neprovedete iteraci v proměnné dotazu, například v `foreach` příkazu. Další informace najdete v tématu [Úvod do dotazů LINQ](introduction-to-linq-queries.md).  
  
-   V době kompilace jsou výrazy dotazu převedeny na volání metody standardního operátoru dotazu podle pravidel specifikace jazyka C#. Jakýkoli dotaz, který lze vyjádřit pomocí syntaxe dotazu lze také vyjádřit pomocí syntaxe metody. Ale ve většině případů je syntaxe dotazu čitelný a výstižně. Další informace najdete v tématu [specifikace jazyka C#](~/_csharplang/spec/expressions.md#query-expressions) a [přehled standardních operátorů dotazu](standard-query-operators-overview.md).  
  
-   Zpravidla při psaní dotazů LINQ, doporučujeme použít syntaxi dotazů, kdykoli je to možné a syntaxe využívající metody kdykoli je to zapotřebí. Neexistuje žádné sémantické nebo výkonu rozdíl mezi dvě různými formami jiný. Výrazy dotazů jsou často čitelnější než ekvivalentní výrazy, které jsou napsané v syntaxe metody.  
  
-   Některé operace, například dotazování <xref:System.Linq.Enumerable.Count%2A> nebo <xref:System.Linq.Enumerable.Max%2A>, mít žádná klauzule výrazu dotazu odpovídá a proto musí být vyjádřena jako volání metody. Syntaxe využívající metody můžete kombinovat pomocí syntaxe dotazu různými způsoby. Další informace najdete v tématu [syntaxe využívající dotazy a syntaxe využívající metody v LINQ](query-syntax-and-method-syntax-in-linq.md).  
  
-   Výrazy dotazu může být zkompilován na stromy výrazů nebo na delegáty, v závislosti na typu použitého dotazu. <xref:System.Collections.Generic.IEnumerable%601> dotazy jsou kompilovány do delegátů. <xref:System.Linq.IQueryable> a <xref:System.Linq.IQueryable%601> dotazy se kompilují na stromy výrazů. Další informace najdete v tématu [stromů výrazů](../../../expression-trees.md).  

## <a name="next-steps"></a>Další kroky

Další informace o dotazech technologie LINQ, začněte se seznamovat s některé základní pojmy v [základy výrazů dotazů](../../../linq/query-expression-basics.md), a pak si můžete přečíst dokumentaci k technologie LINQ, který vás zajímá:   
-   Dokumenty XML: [LINQ to XML](linq-to-xml.md)  
  
-   ADO.NET Entity Framework: [technologii LINQ to entities](../../../../framework/data/adonet/ef/language-reference/linq-to-entities.md)  
  
-   Kolekce .NET, soubory, řetězce a tak dále: [LINQ na objekty](linq-to-objects.md)

Získání hlubší pochopení LINQ obecně získáte [LINQ v JAZYKU C#](../../../linq/linq-in-csharp.md).

Pokud chcete začít pracovat s dotazy LINQ v C#, najdete v kurzu [práce s jazykem LINQ](../../../tutorials/working-with-linq.md).




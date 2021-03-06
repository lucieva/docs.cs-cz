---
title: Vstupní znakovou sadu (entita SQL)
ms.date: 03/30/2017
ms.assetid: 13d291d3-e6bc-4719-b953-758b61a590b6
ms.openlocfilehash: 5e7886215cac2d9363a9ed68cd03a0fce4374055
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/03/2018
ms.locfileid: "32764694"
---
# <a name="input-character-set-entity-sql"></a>Vstupní znakovou sadu (entita SQL)
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] přijme kódovaný v UTF-16 znaků UNICODE.  
  
 Textové literály může obsahovat libovolný znak UTF-16 uzavřená do jednoduchých uvozovek. Například N '文字列リテラル'. Při porovnání textové literály, použijí se původní hodnoty UTF-16. Například N'ABC, se liší v japonské a Latin kódové stránky.  
  
 Komentáře mohou obsahovat libovolný znak UTF-16.  
  
 Identifikátory uvozené řídicími znaky může obsahovat libovolný znak UTF-16 uzavřeny do hranatých závorek. Například [エスケープされた識別子]. Porovnání identifikátory uvozené UTF-16 nejsou rozlišována malá a velká písmena. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] zpracovává verzích písmena, která zobrazí stejné, ale jsou z jiné znakové stránky jako jiné znaky. Například je ekvivalentní [abc] [ABC], pokud odpovídající znaky ze stejné znaková stránka. Pokud stejný dva identifikátory z jiné znakové stránky, jsou to ale není ekvivalentní.  
  
 Prázdné místo je libovolný znak prázdné znaky znakové sady UTF-16.  
  
 Nový řádek je všechny normalizovaný znak nového řádku UTF-16. Například '\n' a '\r\n, jsou považovány za znaky nového řádku, ale '\r' není znak nového řádku.  
  
 Klíčová slova, výrazy a interpunkční znaménka, může být libovolný znak UTF-16, který normalizuje k Latin. Například vyberte v japonské znaková stránka je platný – klíčové slovo.  
  
 Klíčová slova, výrazy a interpunkce lze pouze znaky latinky. `SELECT` v japonské kódová stránka není klíčové slovo. +,-, *, /, =, (,), ", [,] a dalších jazyk konstrukce není v uvozovkách zde lze pouze znaky latinky.  
  
 Jednoduché identifikátory lze pouze znaky latinky. Tím je zabráněno nejednoznačnosti při porovnávání, protože se pak porovnávají původní hodnoty. Například by být ABC liší v japonské a Latin kódové stránky.  
  
## <a name="see-also"></a>Viz také  
 [Přehled Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)

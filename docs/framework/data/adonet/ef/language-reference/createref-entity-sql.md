---
title: CREATEREF (entita SQL)
ms.date: 03/30/2017
ms.assetid: 489828cf-a335-4449-9360-b0d92eec5481
ms.openlocfilehash: 44954dcc1f3407a768ba23fe87ac4b4abcf1bac5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/03/2018
ms.locfileid: "32761334"
---
# <a name="createref-entity-sql"></a>CREATEREF (entita SQL)
Fabricates odkazy na entity v element entityset.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
CreateRef(entityset_identifier, row_typed_expression)  
```  
  
## <a name="arguments"></a>Arguments  
 `entityset_identifier`  
 Identifikátor objektu entityset není řetězcový literál.  
  
 `row_typed_expression`  
 Výraz typu řádek, který odpovídá na klíčové vlastnosti typu entity.  
  
## <a name="remarks"></a>Poznámky  
 `row_typed_expression` musí být strukturálně ekvivalentní typ klíče pro entitu. To znamená musí mít stejný počet a typy polí ve stejném pořadí jako klíče entit.  
  
 V následujícím příkladu objednávek a BadOrders jsou oba objekty entitysets typu pořadí a Id se považuje za jednu klíčovou vlastnost pořadí. Příklad ukazuje, jak jsme může vytvořit odkaz na entitu v BadOrders. Všimněte si, že může být dangling odkaz.  Odkaz na tedy nemusí ve skutečnosti identifikovat konkrétní entity. V takových případech `DEREF` operace na tento odkaz, vrátí hodnotu null.  
  
```  
select CreateRef(LOB.BadOrders, row(o.Id))   
from LOB.Orders as o   
```  
  
## <a name="example"></a>Příklad  
 Následující dotaz Entity SQL pomocí operátoru CREATEREF vyrobit odkazy na entity v sadu entit. Dotaz je založen na modelu prodej AdventureWorks. Pro zkompilování a spuštění tohoto dotazu, postupujte takto:  
  
1.  Postupujte podle pokynů v [postup: provedení dotazu tohoto vrátí výsledky StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Předat jako argument pro následující dotaz `ExecuteStructuralTypeQuery` metoda:  
  
 [!code-csharp[DP EntityServices Concepts 2#CREATEREF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#createref)]  
  
## <a name="see-also"></a>Viz také  
 [Reference k Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [DEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md)  
 [KEY](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)  
 [REF](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md)

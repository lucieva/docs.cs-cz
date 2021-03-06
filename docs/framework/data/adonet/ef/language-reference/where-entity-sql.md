---
title: KDE (entita SQL)
ms.date: 03/30/2017
ms.assetid: a8e1061e-0028-4a6f-8f19-b9f48e96c4b8
ms.openlocfilehash: 43c038e9ff0acfdeff88492aa2ca34fbf4ada94a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/03/2018
ms.locfileid: "32764311"
---
# <a name="where-entity-sql"></a>KDE (entita SQL)
Přímo po použití klauzule WHERE [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md) klauzule.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
[ WHERE expression ]  
```  
  
## <a name="arguments"></a>Arguments  
 `expression`  
 Typem logická hodnota.  
  
## <a name="remarks"></a>Poznámky  
 Klauzule WHERE obsahuje stejnou sémantiku, jak je popsáno pro [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]. Omezuje objekty vyprodukované výrazu dotazu omezením elementy kolekcí zdroje na ty, které předat podmínku.  
  
```  
select c from cs as c where e  
```  
  
 Výraz `e` musí být typu logická hodnota.  
  
 Klauzule WHERE se použije přímo po klauzuli FROM a před jakoukoli seskupení, řazení nebo projekce probíhá. Všechny názvy elementů, které jsou definované v klauzuli FROM jsou viditelné pro výraz klauzule WHERE.  
  
## <a name="see-also"></a>Viz také  
 [Reference k Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [Výrazy dotazu](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)

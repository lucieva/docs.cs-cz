---
title: 'Model Entity Data Model: obory názvů'
ms.date: 03/30/2017
ms.assetid: 98ab4226-bb9f-44e7-af46-61a9b1a4e47c
ms.openlocfilehash: 0fdb007e70b7dd2e4a812d711cb6348e3f563bad
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/03/2018
ms.locfileid: "32765227"
---
# <a name="entity-data-model-namespaces"></a>Model Entity Data Model: obory názvů
Obor názvů v modelu Entity Data Model (EDM) je abstraktní kontejner pro [typy entit](../../../../docs/framework/data/adonet/entity-type.md), [komplexní typy](../../../../docs/framework/data/adonet/complex-type.md), a [přidružení](../../../../docs/framework/data/adonet/association-type.md). Obory názvů v modelu EDM jsou podobná obory názvů v programovacím jazyce: poskytují kontext pro objekty, které obsahují a poskytují způsob k rozlišení objekty, které mají stejný název (ale jsou obsaženy v různých oborech názvů).  
  
## <a name="example"></a>Příklad  
 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) používá specifické pro doménu jazyka (DSL) nazývaného konceptuálního schématu definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) k definování konceptuálních modelech. Následující kód CSDL obor názvů používá k identifikaci typ, který je definován v různých konceptuálním modelu. V příkladu je definován typ entity (`Publisher`), má vlastnost komplexního typu (`Address`) importovány z `ExtendedBooksModel` oboru názvů. Všimněte si, že `Using` element označuje, zda byla naimportována obor názvů. Všimněte si také, že typ `Address` vlastnost je definovaná pomocí plně kvalifikovaným názvem (`ExtendedBooksModel.Address`), což indikuje, že tento typ je definována v `ExtendedBooksModel` oboru názvů.  
  
 [!code-xml[EDM_Example_Model#ImportedNamespace](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books6.edmx#importednamespace)]  
  
## <a name="see-also"></a>Viz také  
 [Koncepty modelu EDM (Entity Data Model)](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [Model EDM (Entity Data Model)](../../../../docs/framework/data/adonet/entity-data-model.md)

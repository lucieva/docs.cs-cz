---
title: Typ entity
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a6dee9ab-9e4a-48f2-a169-3f79cc15821c
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 1b84ff5a55cff4548539e81b16406e234dcb43f9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="entity-type"></a><span data-ttu-id="3f5a7-102">Typ entity</span><span class="sxs-lookup"><span data-stu-id="3f5a7-102">entity type</span></span>
<span data-ttu-id="3f5a7-103">*Typ entity* je základní stavební blok pro popisující strukturu dat s Entity Data Model (EDM).</span><span class="sxs-lookup"><span data-stu-id="3f5a7-103">The *entity type* is the fundamental building block for describing the structure of data with the Entity Data Model (EDM).</span></span> <span data-ttu-id="3f5a7-104">Typ entity v konceptuálním modelu představuje strukturu nejvyšší úrovně koncepty, jako jsou zákazníci nebo objednávky.</span><span class="sxs-lookup"><span data-stu-id="3f5a7-104">In a conceptual model, an entity type represents the structure of top-level concepts, such as customers or orders.</span></span> <span data-ttu-id="3f5a7-105">Typ entity je šablona pro instance typu entity.</span><span class="sxs-lookup"><span data-stu-id="3f5a7-105">An entity type is a template for entity type instances.</span></span> <span data-ttu-id="3f5a7-106">Každá šablona obsahuje následující informace:</span><span class="sxs-lookup"><span data-stu-id="3f5a7-106">Each template contains the following information:</span></span>  
  
-   <span data-ttu-id="3f5a7-107">Jedinečný název.</span><span class="sxs-lookup"><span data-stu-id="3f5a7-107">A unique name.</span></span> <span data-ttu-id="3f5a7-108">(Povinné).</span><span class="sxs-lookup"><span data-stu-id="3f5a7-108">(Required.)</span></span>  
  
-   <span data-ttu-id="3f5a7-109">[Klíč entity](../../../../docs/framework/data/adonet/entity-key.md) definované jednu nebo více vlastností.</span><span class="sxs-lookup"><span data-stu-id="3f5a7-109">An [entity key](../../../../docs/framework/data/adonet/entity-key.md) defined by one or more properties.</span></span> <span data-ttu-id="3f5a7-110">(Povinné).</span><span class="sxs-lookup"><span data-stu-id="3f5a7-110">(Required.)</span></span>  
  
-   <span data-ttu-id="3f5a7-111">Data ve formě [vlastnosti](../../../../docs/framework/data/adonet/property.md).</span><span class="sxs-lookup"><span data-stu-id="3f5a7-111">Data in the form of [properties](../../../../docs/framework/data/adonet/property.md).</span></span> <span data-ttu-id="3f5a7-112">(Volitelné).</span><span class="sxs-lookup"><span data-stu-id="3f5a7-112">(Optional.)</span></span>  
  
-   <span data-ttu-id="3f5a7-113">[Navigační vlastnosti](../../../../docs/framework/data/adonet/navigation-property.md) které umožňují pro navigaci z jednoho [end](../../../../docs/framework/data/adonet/association-end.md) z [přidružení](../../../../docs/framework/data/adonet/association-type.md) na druhém konci.</span><span class="sxs-lookup"><span data-stu-id="3f5a7-113">[Navigation properties](../../../../docs/framework/data/adonet/navigation-property.md) that allow for navigation from one [end](../../../../docs/framework/data/adonet/association-end.md) of an [association](../../../../docs/framework/data/adonet/association-type.md) to the other end.</span></span> <span data-ttu-id="3f5a7-114">(Volitelné)</span><span class="sxs-lookup"><span data-stu-id="3f5a7-114">(Optional)</span></span>  
  
 <span data-ttu-id="3f5a7-115">V aplikaci představuje instanci typu entity na konkrétní objekt (například konkrétního zákazníka nebo pořadí).</span><span class="sxs-lookup"><span data-stu-id="3f5a7-115">In an application, an instance of an entity type represents a specific object (such as a specific customer or order).</span></span> <span data-ttu-id="3f5a7-116">Každá instance typu entity, musí mít jedinečnou [klíč entity](../../../../docs/framework/data/adonet/entity-key.md) v rámci [sady entit](../../../../docs/framework/data/adonet/entity-set.md).</span><span class="sxs-lookup"><span data-stu-id="3f5a7-116">Each instance of an entity type must have a unique [entity key](../../../../docs/framework/data/adonet/entity-key.md) within an [entity set](../../../../docs/framework/data/adonet/entity-set.md).</span></span>  
  
 <span data-ttu-id="3f5a7-117">Dvě instance typu entity jsou považovány za shodné, pouze v případě, že jsou stejného typu a hodnoty jejich klíče entity jsou stejné.</span><span class="sxs-lookup"><span data-stu-id="3f5a7-117">Two entity type instances are considered equal only if they are of the same type and the values of their entity keys are the same.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f5a7-118">Příklad</span><span class="sxs-lookup"><span data-stu-id="3f5a7-118">Example</span></span>  
 <span data-ttu-id="3f5a7-119">Následující diagram znázorňuje Koncepční model se tři typy entit: `Book`, `Publisher`, a `Author`:</span><span class="sxs-lookup"><span data-stu-id="3f5a7-119">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`:</span></span>  
  
 <span data-ttu-id="3f5a7-120">![Ukázkový Model](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span><span class="sxs-lookup"><span data-stu-id="3f5a7-120">![Example Model](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span></span>  
  
 <span data-ttu-id="3f5a7-121">Všimněte si, že vlastnosti každého typu entity, které tvoří svůj klíč entity, jsou označeny "(klíč)".</span><span class="sxs-lookup"><span data-stu-id="3f5a7-121">Note that the properties of each entity type that make up its entity key are denoted with "(Key)".</span></span>  
  
 <span data-ttu-id="3f5a7-122">[ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) používá specifické pro doménu jazyka (DSL) nazývaného konceptuálního schématu definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) k definování konceptuálních modelech.</span><span class="sxs-lookup"><span data-stu-id="3f5a7-122">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="3f5a7-123">Definuje následující CSDL `Book` typ entity, které jsou uvedené v diagramu výše:</span><span class="sxs-lookup"><span data-stu-id="3f5a7-123">The following CSDL defines the `Book` entity type shown in the diagram above:</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
## <a name="see-also"></a><span data-ttu-id="3f5a7-124">Viz také</span><span class="sxs-lookup"><span data-stu-id="3f5a7-124">See Also</span></span>  
 [<span data-ttu-id="3f5a7-125">Entity Data Model klíčové koncepty</span><span class="sxs-lookup"><span data-stu-id="3f5a7-125">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="3f5a7-126">Datového modelu entity</span><span class="sxs-lookup"><span data-stu-id="3f5a7-126">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)  
 [<span data-ttu-id="3f5a7-127">omezující vlastnost</span><span class="sxs-lookup"><span data-stu-id="3f5a7-127">facet</span></span>](../../../../docs/framework/data/adonet/facet.md)
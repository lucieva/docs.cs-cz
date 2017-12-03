---
title: "konce přidružení sady"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fe4bf1d3-047a-4a37-98c5-a66e70811346
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 20810eddda98403d244f6104807504489dde71cc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="association-set-end"></a><span data-ttu-id="28ca0-102">konce přidružení sady</span><span class="sxs-lookup"><span data-stu-id="28ca0-102">association set end</span></span>
<span data-ttu-id="28ca0-103">*Nastavená přidružení end* identifikuje [typ entity](../../../../docs/framework/data/adonet/entity-type.md) a [sady entit](../../../../docs/framework/data/adonet/entity-set.md) na konci [sadu přidružení](../../../../docs/framework/data/adonet/association-set.md).</span><span class="sxs-lookup"><span data-stu-id="28ca0-103">An *association set end* identifies the [entity type](../../../../docs/framework/data/adonet/entity-type.md) and the [entity set](../../../../docs/framework/data/adonet/entity-set.md) at the end of an [association set](../../../../docs/framework/data/adonet/association-set.md).</span></span> <span data-ttu-id="28ca0-104">Přidružení sady končí jsou definované jako součást sady přidružení; sadu přidružení musí mít přesně dva sadu zakončení.</span><span class="sxs-lookup"><span data-stu-id="28ca0-104">Association set ends are defined as part of an association set; an association set must have exactly two association set ends.</span></span>  
  
 <span data-ttu-id="28ca0-105">Definici sady end přidružení obsahuje následující informace:</span><span class="sxs-lookup"><span data-stu-id="28ca0-105">An association set end definition contains the following information:</span></span>  
  
-   <span data-ttu-id="28ca0-106">Jeden z typů entity účastní přidružení nastavit.</span><span class="sxs-lookup"><span data-stu-id="28ca0-106">One of the entity types involved in the association set.</span></span> <span data-ttu-id="28ca0-107">(Povinné)</span><span class="sxs-lookup"><span data-stu-id="28ca0-107">(Required)</span></span>  
  
-   <span data-ttu-id="28ca0-108">Sada entit pro typ entity účastní sadu přidružení.</span><span class="sxs-lookup"><span data-stu-id="28ca0-108">The entity set for the entity type involved in the association set.</span></span> <span data-ttu-id="28ca0-109">(Povinné)</span><span class="sxs-lookup"><span data-stu-id="28ca0-109">(Required)</span></span>  
  
## <a name="example"></a><span data-ttu-id="28ca0-110">Příklad</span><span class="sxs-lookup"><span data-stu-id="28ca0-110">Example</span></span>  
 <span data-ttu-id="28ca0-111">Následující diagram znázorňuje Koncepční model se dvě přidružení: `WrittenBy` a `PublishedBy`.</span><span class="sxs-lookup"><span data-stu-id="28ca0-111">The diagram below shows a conceptual model with two associations: `WrittenBy` and `PublishedBy`.</span></span>  
  
 <span data-ttu-id="28ca0-112">![Ukázkový Model](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span><span class="sxs-lookup"><span data-stu-id="28ca0-112">![Example Model](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span></span>  
  
 <span data-ttu-id="28ca0-113">Následující diagram znázorňuje sadu přidružení (`PublishedBy`) a dvě sady entit (`Books` a `Publishers`) na základě konceptuálního modelu uvedené výše.</span><span class="sxs-lookup"><span data-stu-id="28ca0-113">The following diagram shows an association set (`PublishedBy`) and two entity sets (`Books` and `Publishers`) based on the conceptual model shown above.</span></span> <span data-ttu-id="28ca0-114">Elementy end přidružení sady jsou `Books` a `Publishers` sady entit.</span><span class="sxs-lookup"><span data-stu-id="28ca0-114">The association set ends are the `Books` and `Publishers` entity sets.</span></span> <span data-ttu-id="28ca0-115">BI v `Books` sady entit představuje instanci `Book` typ entity v době běhu.</span><span class="sxs-lookup"><span data-stu-id="28ca0-115">Bi in the `Books` entity set represents an instance of the `Book` entity type at run time.</span></span> <span data-ttu-id="28ca0-116">Podobně, představuje Pj `Publisher` instance v `Publishers` sady entit.</span><span class="sxs-lookup"><span data-stu-id="28ca0-116">Similarly, Pj represents a `Publisher` instance in the `Publishers` entity set.</span></span> <span data-ttu-id="28ca0-117">BiPj představuje instanci `PublishedBy` přidružení v `PublishedBy` sadu přidružení.</span><span class="sxs-lookup"><span data-stu-id="28ca0-117">BiPj represents an instance of the `PublishedBy` association in the `PublishedBy` association set.</span></span>  
  
 <span data-ttu-id="28ca0-118">![Nastaví příklad](../../../../docs/framework/data/adonet/media/setsexample.gif "SetsExample")</span><span class="sxs-lookup"><span data-stu-id="28ca0-118">![Sets Example](../../../../docs/framework/data/adonet/media/setsexample.gif "SetsExample")</span></span>  
  
 <span data-ttu-id="28ca0-119">[ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) používá DSL, kterému se říká jazyk definice konceptuálního schématu ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) k definování konceptuálních modelech.</span><span class="sxs-lookup"><span data-stu-id="28ca0-119">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a DSL called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="28ca0-120">Následující CSDL definuje jednu sadu pro každé přidružení v diagramu výše přidružení kontejner entity.</span><span class="sxs-lookup"><span data-stu-id="28ca0-120">The following CSDL defines an entity container with one association set for each association in the diagram above.</span></span> <span data-ttu-id="28ca0-121">Všimněte si, že zakončení sady jsou definovány v rámci každé definici sady přidružení.</span><span class="sxs-lookup"><span data-stu-id="28ca0-121">Note that association set ends are defined as part of each association set definition.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
## <a name="see-also"></a><span data-ttu-id="28ca0-122">Viz také</span><span class="sxs-lookup"><span data-stu-id="28ca0-122">See Also</span></span>  
 [<span data-ttu-id="28ca0-123">Entity Data Model klíčové koncepty</span><span class="sxs-lookup"><span data-stu-id="28ca0-123">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="28ca0-124">Datového modelu entity</span><span class="sxs-lookup"><span data-stu-id="28ca0-124">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
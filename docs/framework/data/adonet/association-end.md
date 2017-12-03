---
title: "end přidružení"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2c345213-0296-4d90-ac6d-cef179798a75
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 7ceb6d40a47c73c4580a8fc33acc3c395a2c5a06
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="association-end"></a><span data-ttu-id="f6b2c-102">end přidružení</span><span class="sxs-lookup"><span data-stu-id="f6b2c-102">association end</span></span>
<span data-ttu-id="f6b2c-103">*End přidružení* identifikuje [typ entity](../../../../docs/framework/data/adonet/entity-type.md) na jednom konci [přidružení](../../../../docs/framework/data/adonet/association-type.md) a počet entit, zadejte instancí, které může existovat na tomto konci tohoto přidružení.</span><span class="sxs-lookup"><span data-stu-id="f6b2c-103">An *association end* identifies the [entity type](../../../../docs/framework/data/adonet/entity-type.md) on one end of an [association](../../../../docs/framework/data/adonet/association-type.md) and the number of entity type instances that can exist at that end of an association.</span></span> <span data-ttu-id="f6b2c-104">Zakončení přidružení jsou definované jako součást přidružení; přidružení musí mít přesně dva elementy end přidružení.</span><span class="sxs-lookup"><span data-stu-id="f6b2c-104">Association ends are defined as part of an association; an association must have exactly two association ends.</span></span> <span data-ttu-id="f6b2c-105">[Navigační vlastnosti](../../../../docs/framework/data/adonet/navigation-property.md) povolit pro navigaci z elementu end přidružení jeden na druhý.</span><span class="sxs-lookup"><span data-stu-id="f6b2c-105">[Navigation properties](../../../../docs/framework/data/adonet/navigation-property.md) allow for navigation from one association end to the other.</span></span>  
  
 <span data-ttu-id="f6b2c-106">Definici end přidružení obsahuje následující informace:</span><span class="sxs-lookup"><span data-stu-id="f6b2c-106">An association end definition contains the following information:</span></span>  
  
-   <span data-ttu-id="f6b2c-107">Jeden z typů entity účastní přidružení.</span><span class="sxs-lookup"><span data-stu-id="f6b2c-107">One of the entity types involved in the association.</span></span> <span data-ttu-id="f6b2c-108">(Povinné)</span><span class="sxs-lookup"><span data-stu-id="f6b2c-108">(Required)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f6b2c-109">Pro danou přidružení může být pro každý element end přidružení zadaný typ entity stejné.</span><span class="sxs-lookup"><span data-stu-id="f6b2c-109">For a given association, the entity type specified for each association end can be the same.</span></span> <span data-ttu-id="f6b2c-110">Tím se vytvoří vlastní přidružení.</span><span class="sxs-lookup"><span data-stu-id="f6b2c-110">This creates a self-association.</span></span>  
  
-   <span data-ttu-id="f6b2c-111">[Násobnost end přidružení](../../../../docs/framework/data/adonet/association-end-multiplicity.md) určující počet instancí typ entity, které mohou být na jednom konci přidružení.</span><span class="sxs-lookup"><span data-stu-id="f6b2c-111">An [association end multiplicity](../../../../docs/framework/data/adonet/association-end-multiplicity.md) that indicates the number of entity type instances that can be at one end of the association.</span></span> <span data-ttu-id="f6b2c-112">Násobnost end přidružení může mít hodnotu jedna (1), žádnou nebo jednu (0..1), nebo mnoho (*).</span><span class="sxs-lookup"><span data-stu-id="f6b2c-112">An association end multiplicity can have a value of one (1), zero or one (0..1), or many (*).</span></span>  
  
-   <span data-ttu-id="f6b2c-113">Název elementu end přidružení.</span><span class="sxs-lookup"><span data-stu-id="f6b2c-113">A name for the association end.</span></span> <span data-ttu-id="f6b2c-114">(Volitelné)</span><span class="sxs-lookup"><span data-stu-id="f6b2c-114">(Optional)</span></span>  
  
-   <span data-ttu-id="f6b2c-115">Informace o operacích, které se provádí na konci přidružení, jako je například cascade na odstranění.</span><span class="sxs-lookup"><span data-stu-id="f6b2c-115">Information about operations that are performed on the association end, such as cascade on delete.</span></span> <span data-ttu-id="f6b2c-116">(Volitelné)</span><span class="sxs-lookup"><span data-stu-id="f6b2c-116">(Optional)</span></span>  
  
## <a name="example"></a><span data-ttu-id="f6b2c-117">Příklad</span><span class="sxs-lookup"><span data-stu-id="f6b2c-117">Example</span></span>  
 <span data-ttu-id="f6b2c-118">Následující diagram znázorňuje Koncepční model se dvě přidružení: `PublishedBy` a `WrittenBy`.</span><span class="sxs-lookup"><span data-stu-id="f6b2c-118">The diagram below shows a conceptual model with two associations: `PublishedBy` and `WrittenBy`.</span></span> <span data-ttu-id="f6b2c-119">Přidružení končí pro `PublishedBy` jsou přidružení `Book` a `Publisher` typy entit.</span><span class="sxs-lookup"><span data-stu-id="f6b2c-119">The association ends for the `PublishedBy` association are the `Book` and `Publisher` entity types.</span></span> <span data-ttu-id="f6b2c-120">Násobnost `Publisher` koncový je jedna (1) a násobnosti atributu `Book` koncový je mnoho (*), označující, že vydavatel publikuje mnoho knihy a publikování knihy se jeden vydavatelem.</span><span class="sxs-lookup"><span data-stu-id="f6b2c-120">The multiplicity of the `Publisher` end is one (1) and the multiplicity of the `Book` end is many (*), indicating that a publisher publishes many books and a book is published by one publisher.</span></span>  
  
 <span data-ttu-id="f6b2c-121">![Ukázkový Model](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span><span class="sxs-lookup"><span data-stu-id="f6b2c-121">![Example Model](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span></span>  
  
 <span data-ttu-id="f6b2c-122">ADO.NET Entity Framework používá specifické pro doménu jazyka (DSL) nazývaného konceptuálního schématu definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) k definování konceptuálních modelech.</span><span class="sxs-lookup"><span data-stu-id="f6b2c-122">The ADO.NET Entity Framework uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="f6b2c-123">Definuje CSDL níže `PublishedBy` přidružení vidět v diagramu výše.</span><span class="sxs-lookup"><span data-stu-id="f6b2c-123">The CSDL below defines the `PublishedBy` association shown in the diagram above.</span></span> <span data-ttu-id="f6b2c-124">Všimněte si, že jsou zadané typu, názvu a násobnost konce každé přidružení podle atributů XML ( `Type`, `Role`, a `Multiplicity` atributy v uvedeném pořadí).</span><span class="sxs-lookup"><span data-stu-id="f6b2c-124">Note that the type, name, and multiplicity of each association end are specified by XML attributes (the `Type`, `Role`, and `Multiplicity` attributes, respectively).</span></span> <span data-ttu-id="f6b2c-125">Volitelné informace o operace provedené na element end je zadaný v elementu XML ( `OnDelete` element).</span><span class="sxs-lookup"><span data-stu-id="f6b2c-125">Optional information about operations performed on an end is specified in an XML element (the `OnDelete` element).</span></span> <span data-ttu-id="f6b2c-126">V takovém případě je-li vydavatel odstraněna, proto jsou všechny přidružené knih.</span><span class="sxs-lookup"><span data-stu-id="f6b2c-126">In this case, if a publisher is deleted, so are all associated books.</span></span>  
  
 [!code-xml[EDM_Example_Model#AssociationEnd](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#associationend)]  
  
## <a name="see-also"></a><span data-ttu-id="f6b2c-127">Viz také</span><span class="sxs-lookup"><span data-stu-id="f6b2c-127">See Also</span></span>  
 [<span data-ttu-id="f6b2c-128">Entity Data Model klíčové koncepty</span><span class="sxs-lookup"><span data-stu-id="f6b2c-128">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="f6b2c-129">Datového modelu entity</span><span class="sxs-lookup"><span data-stu-id="f6b2c-129">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
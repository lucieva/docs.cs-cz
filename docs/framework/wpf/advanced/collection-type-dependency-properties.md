---
title: "Vlastnosti závislostí typu kolekce"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- properties [WPF], dependency
- properties [WPF], collection-type
- dependency properties [WPF]
- collection-type properties [WPF]
ms.assetid: 99f96a42-3ab7-4f64-a16b-2e10d654e97c
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 11927efee2b8375550767d119e6b4a95b3ef7bd8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="collection-type-dependency-properties"></a><span data-ttu-id="e84c4-102">Vlastnosti závislostí typu kolekce</span><span class="sxs-lookup"><span data-stu-id="e84c4-102">Collection-Type Dependency Properties</span></span>
<span data-ttu-id="e84c4-103">Toto téma obsahuje pokyny a navrhované vzory pro implementaci vlastnost závislosti, kde je typ vlastnosti typu kolekce.</span><span class="sxs-lookup"><span data-stu-id="e84c4-103">This topic provides guidance and suggested patterns for how to implement a dependency property where the type of the property is a collection type.</span></span>  
  
 
  
<a name="implementing"></a>   
## <a name="implementing-a-collection-type-dependency-property"></a><span data-ttu-id="e84c4-104">Implementace vlastnost závislosti typ kolekce</span><span class="sxs-lookup"><span data-stu-id="e84c4-104">Implementing a Collection-Type Dependency Property</span></span>  
 <span data-ttu-id="e84c4-105">Pro vlastnost závislosti implementace vzor, který budete postupovat podle je obecně můžete definovat [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] vlastnost obálky, kde je zajištěna tuto vlastnost <xref:System.Windows.DependencyProperty> identifikátor místo pole nebo jiné konstrukce.</span><span class="sxs-lookup"><span data-stu-id="e84c4-105">For a dependency property in general, the implementation pattern that you follow is that you define a [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] property wrapper, where that property is backed by a <xref:System.Windows.DependencyProperty> identifier rather than a field or other construct.</span></span> <span data-ttu-id="e84c4-106">Provedením tohoto stejného vzoru při implementaci vlastnost typu kolekce.</span><span class="sxs-lookup"><span data-stu-id="e84c4-106">You follow this same pattern when you implement a collection-type property.</span></span> <span data-ttu-id="e84c4-107">Však vlastnost typu kolekce zavádí některé složitost se vzorem vždy, když se o typ, který je obsažen v rámci kolekce <xref:System.Windows.DependencyObject> nebo <xref:System.Windows.Freezable> odvozené třídy.</span><span class="sxs-lookup"><span data-stu-id="e84c4-107">However, a collection-type property introduces some complexity to the pattern whenever the type that is contained within the collection is itself a <xref:System.Windows.DependencyObject> or <xref:System.Windows.Freezable> derived class.</span></span>  
  
<a name="initializing"></a>   
## <a name="initializing-the-collection-beyond-the-default-value"></a><span data-ttu-id="e84c4-108">Inicializace kolekce překračuje výchozí hodnota</span><span class="sxs-lookup"><span data-stu-id="e84c4-108">Initializing the Collection Beyond the Default Value</span></span>  
 <span data-ttu-id="e84c4-109">Když vytvoříte vlastnost závislosti, nezadávejte vlastnost výchozí hodnotu jako hodnota počáteční pole.</span><span class="sxs-lookup"><span data-stu-id="e84c4-109">When you create a dependency property, you do not specify the property default value as the initial field value.</span></span> <span data-ttu-id="e84c4-110">Místo toho zadat výchozí hodnotu prostřednictvím metadata vlastnosti závislosti.</span><span class="sxs-lookup"><span data-stu-id="e84c4-110">Instead, you specify the default value through the dependency property metadata.</span></span> <span data-ttu-id="e84c4-111">Pokud je vaše vlastnost typu odkazu., výchozí hodnota zadaná v metadatech vlastnost závislosti není výchozí hodnotu na instanci; Místo toho je výchozí hodnotu, která platí pro všechny instance typu.</span><span class="sxs-lookup"><span data-stu-id="e84c4-111">If your property is a reference type, the default value specified in dependency property metadata is not a default value per instance; instead it is a default value that applies to all instances of the type.</span></span> <span data-ttu-id="e84c4-112">Musí být proto opatrní nechcete použít kolekci singulární statické definované metadata vlastnosti kolekce jako pracovní výchozí hodnota pro nově vytvořená instance stejného typu.</span><span class="sxs-lookup"><span data-stu-id="e84c4-112">Therefore you must be careful to not use the singular static collection defined by the collection property metadata as the working default value for newly created instances of your type.</span></span> <span data-ttu-id="e84c4-113">Místo toho je třeba se záměrně nastavena hodnota kolekce do kolekce jedinečný (instance) jako součást logiky konstruktor – třída.</span><span class="sxs-lookup"><span data-stu-id="e84c4-113">Instead, you must make sure that you deliberately set the collection value to a unique (instance) collection as part of your class constructor logic.</span></span> <span data-ttu-id="e84c4-114">V opačném případě bude vytvořená třídu neúmyslnému singleton.</span><span class="sxs-lookup"><span data-stu-id="e84c4-114">Otherwise you will have created an unintentional singleton class.</span></span>  
  
 <span data-ttu-id="e84c4-115">Podívejte se na následující příklad.</span><span class="sxs-lookup"><span data-stu-id="e84c4-115">Consider the following example.</span></span> <span data-ttu-id="e84c4-116">V následující části Tento příklad zobrazuje definici pro třídu `Aquarium`.</span><span class="sxs-lookup"><span data-stu-id="e84c4-116">The following section of the example shows the definition for a class `Aquarium`.</span></span> <span data-ttu-id="e84c4-117">Třída definuje vlastnost závislost typu kolekce `AquariumObjects`, Obecné, který používá <xref:System.Collections.Generic.List%601> zadejte s <xref:System.Windows.FrameworkElement> typ omezení.</span><span class="sxs-lookup"><span data-stu-id="e84c4-117">The class defines the collection type dependency property `AquariumObjects`, which uses the generic <xref:System.Collections.Generic.List%601> type with a <xref:System.Windows.FrameworkElement> type constraint.</span></span> <span data-ttu-id="e84c4-118">V <xref:System.Windows.DependencyProperty.Register%28System.String%2CSystem.Type%2CSystem.Type%2CSystem.Windows.PropertyMetadata%29> volání pro vlastnost závislosti, metadata vytvoří výchozí hodnotu na nové obecného <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="e84c4-118">In the <xref:System.Windows.DependencyProperty.Register%28System.String%2CSystem.Type%2CSystem.Type%2CSystem.Windows.PropertyMetadata%29> call for the dependency property, the metadata establishes the default value to be a new generic <xref:System.Collections.Generic.List%601>.</span></span>  
  
 [!code-csharp[PropertiesOvwSupport2#CollectionProblemDefinition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport2/CSharp/page.xaml.cs#collectionproblemdefinition)]
 [!code-vb[PropertiesOvwSupport2#CollectionProblemDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport2/visualbasic/page.xaml.vb#collectionproblemdefinition)]  
  
 <span data-ttu-id="e84c4-119">Ale pokud jste právě nechali kód, jak je znázorněno, tato jediný seznam Výchozí hodnota je sdílena pro všechny instance `Aquarium`.</span><span class="sxs-lookup"><span data-stu-id="e84c4-119">However, if you just left the code as shown, that single list default value is shared for all instances of `Aquarium`.</span></span> <span data-ttu-id="e84c4-120">Pokud jste spustili následující testovací kód, který se má zobrazit, jak by doložit dva samostatné `Aquarium` instance a přidejte jeden jiný `Fish` ke každému z nich, zobrazí se překvapivé výsledek:</span><span class="sxs-lookup"><span data-stu-id="e84c4-120">If you ran the following test code, which is intended to show how you would instantiate two separate `Aquarium` instances and add a single different `Fish` to each of them, you would see a surprising result:</span></span>  
  
 [!code-csharp[PropertiesOvwSupport#CollectionProblemTestCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#collectionproblemtestcode)]
 [!code-vb[PropertiesOvwSupport#CollectionProblemTestCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#collectionproblemtestcode)]  
  
 <span data-ttu-id="e84c4-121">Místo nutnosti započítává jako jeden Každá kolekce Každá kolekce má dva počet!</span><span class="sxs-lookup"><span data-stu-id="e84c4-121">Instead of each collection having a count of one, each collection has a count of two!</span></span> <span data-ttu-id="e84c4-122">Důvodem je, že každý `Aquarium` přidat jeho `Fish` do kolekce výchozí hodnotu, která je výsledkem volání jednoho konstruktor v metadatech a proto jsou sdílena mezi všechny instance.</span><span class="sxs-lookup"><span data-stu-id="e84c4-122">This is because each `Aquarium` added its `Fish` to the default value collection, which resulted from a single constructor call in the metadata and is therefore shared between all instances.</span></span> <span data-ttu-id="e84c4-123">Tato situace je téměř žádné co chcete použít.</span><span class="sxs-lookup"><span data-stu-id="e84c4-123">This situation is almost never what you want.</span></span>  
  
 <span data-ttu-id="e84c4-124">Chcete-li tento problém, musí vynulovat hodnotu vlastnosti závislosti kolekce k instanci jedinečný v rámci volání konstruktoru třídy.</span><span class="sxs-lookup"><span data-stu-id="e84c4-124">To correct this problem, you must reset the collection dependency property value to a unique instance, as part of the class constructor call.</span></span> <span data-ttu-id="e84c4-125">Protože vlastnost je vlastnost závislosti jen pro čtení, můžete použít <xref:System.Windows.DependencyObject.SetValue%28System.Windows.DependencyPropertyKey%2CSystem.Object%29> metodu a nastavit, pomocí <xref:System.Windows.DependencyPropertyKey> , je k dispozici pouze v rámci třídy.</span><span class="sxs-lookup"><span data-stu-id="e84c4-125">Because the property is a read-only dependency property, you use the <xref:System.Windows.DependencyObject.SetValue%28System.Windows.DependencyPropertyKey%2CSystem.Object%29> method to set it, using the <xref:System.Windows.DependencyPropertyKey> that is only accessible within the class.</span></span>  
  
 [!code-csharp[PropertiesOvwSupport#CollectionProblemCtor](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#collectionproblemctor)]
 [!code-vb[PropertiesOvwSupport#CollectionProblemCtor](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#collectionproblemctor)]  
  
 <span data-ttu-id="e84c4-126">Nyní, pokud jste spustili, že stejný kód test znovu, se může zobrazí více očekávané výsledky, kde každý `Aquarium` podporované svůj vlastní jedinečný kolekce.</span><span class="sxs-lookup"><span data-stu-id="e84c4-126">Now, if you ran that same test code again, you could see more expected results, where each `Aquarium` supported its own unique collection.</span></span>  
  
 <span data-ttu-id="e84c4-127">By mírné variace v tomto vzoru Pokud jste zvolili pro vaše kolekce vlastností se pro čtení a zápis.</span><span class="sxs-lookup"><span data-stu-id="e84c4-127">There would be a slight variation on this pattern if you chose to have your collection property be read-write.</span></span> <span data-ttu-id="e84c4-128">V takovém případě může volat přistupujícího objektu veřejná sada z konstruktoru udělat inicializaci, což by stále volání nonkey podpis <xref:System.Windows.DependencyObject.SetValue%28System.Windows.DependencyProperty%2CSystem.Object%29> v rámci vaší sady obálky, pomocí veřejné <xref:System.Windows.DependencyProperty> identifikátor.</span><span class="sxs-lookup"><span data-stu-id="e84c4-128">In that case, you could call the public set accessor from the constructor to do the initialization, which would still be calling the nonkey signature of <xref:System.Windows.DependencyObject.SetValue%28System.Windows.DependencyProperty%2CSystem.Object%29> within your set wrapper, using a public <xref:System.Windows.DependencyProperty> identifier.</span></span>  
  
## <a name="reporting-binding-value-changes-from-collection-properties"></a><span data-ttu-id="e84c4-129">Vytváření sestav vazby změnám hodnoty z vlastnosti kolekce</span><span class="sxs-lookup"><span data-stu-id="e84c4-129">Reporting Binding Value Changes from Collection Properties</span></span>  
 <span data-ttu-id="e84c4-130">Vlastnost kolekce, který je sám vlastnost závislosti automaticky nehlásí změny k jeho podvlastnosti.</span><span class="sxs-lookup"><span data-stu-id="e84c4-130">A collection property that is itself a dependency property does not automatically report changes to its subproperties.</span></span> <span data-ttu-id="e84c4-131">Při vytváření vazby na kolekci, může bránit vazbu z hlášení změn, proto zneplatnění některé scénáře datových vazeb.</span><span class="sxs-lookup"><span data-stu-id="e84c4-131">If you are creating bindings into a collection, this can prevent the binding from reporting changes, thus invalidating some data binding scenarios.</span></span> <span data-ttu-id="e84c4-132">Ale pokud používáte typ kolekce <xref:System.Windows.FreezableCollection%601> jako typ kolekce, pak dílčí vlastnosti změny obsažené elementů v kolekci jsou správně hlášené a vazba funguje podle očekávání.</span><span class="sxs-lookup"><span data-stu-id="e84c4-132">However, if you use the collection type <xref:System.Windows.FreezableCollection%601> as your collection type, then subproperty changes to contained elements in the collection are properly reported, and binding works as expected.</span></span>  
  
 <span data-ttu-id="e84c4-133">Chcete-li povolit vazby dílčí vlastnosti v objektu kolekce závislost, vytvořit kolekci jako typ <xref:System.Windows.FreezableCollection%601>, s omezením na typ pro tuto kolekci do jakéhokoli <xref:System.Windows.DependencyObject> odvozené třídy.</span><span class="sxs-lookup"><span data-stu-id="e84c4-133">To enable subproperty binding in a dependency object collection, create the collection property as type <xref:System.Windows.FreezableCollection%601>, with a type constraint for that collection to any <xref:System.Windows.DependencyObject> derived class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e84c4-134">Viz také</span><span class="sxs-lookup"><span data-stu-id="e84c4-134">See Also</span></span>  
 <xref:System.Windows.FreezableCollection%601>  
 [<span data-ttu-id="e84c4-135">XAML a vlastní třídy pro grafický subsystém WPF</span><span class="sxs-lookup"><span data-stu-id="e84c4-135">XAML and Custom Classes for WPF</span></span>](../../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)  
 [<span data-ttu-id="e84c4-136">Přehled vazba dat</span><span class="sxs-lookup"><span data-stu-id="e84c4-136">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="e84c4-137">Přehled vlastností závislostí</span><span class="sxs-lookup"><span data-stu-id="e84c4-137">Dependency Properties Overview</span></span>](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [<span data-ttu-id="e84c4-138">Vlastnosti vlastní závislosti</span><span class="sxs-lookup"><span data-stu-id="e84c4-138">Custom Dependency Properties</span></span>](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)  
 [<span data-ttu-id="e84c4-139">Metadata vlastnosti závislosti</span><span class="sxs-lookup"><span data-stu-id="e84c4-139">Dependency Property Metadata</span></span>](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md)
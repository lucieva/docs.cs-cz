---
title: "Rozšiřitelné objekty"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: extensible objects [WCF]
ms.assetid: bc88cefc-31fb-428e-9447-6d20a7d452af
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 24482f97f5869def79ce2a24d33b3f9345d1c7c3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="extensible-objects"></a><span data-ttu-id="4938e-102">Rozšiřitelné objekty</span><span class="sxs-lookup"><span data-stu-id="4938e-102">Extensible Objects</span></span>
<span data-ttu-id="4938e-103">Vzor extensible objektu se používá buď rozšířit existující třídy runtime s novými funkcemi nebo přidat nový stav na objekt.</span><span class="sxs-lookup"><span data-stu-id="4938e-103">The extensible object pattern is used to either extend existing runtime classes with new functionality or to add new state to an object.</span></span> <span data-ttu-id="4938e-104">Rozšíření, které jsou připojené k jednomu rozšiřitelné objekty, aktivujte velmi různých fází zpracování pro přístup k sdílení stavu a funkce, které jsou připojené k běžné extensible objekt, který bude mít přístup k chování.</span><span class="sxs-lookup"><span data-stu-id="4938e-104">Extensions, attached to one of the extensible objects, enable behaviors at very different stages in processing to access shared state and functionality attached to a common extensible object that they can access.</span></span>  
  
## <a name="the-iextensibleobjectt-pattern"></a><span data-ttu-id="4938e-105">IExtensibleObject\<T > vzor</span><span class="sxs-lookup"><span data-stu-id="4938e-105">The IExtensibleObject\<T> Pattern</span></span>  
 <span data-ttu-id="4938e-106">Existují tři rozhraní ve vzoru extensible objektu: <xref:System.ServiceModel.IExtensibleObject%601>, <xref:System.ServiceModel.IExtension%601>, a <xref:System.ServiceModel.IExtensionCollection%601>.</span><span class="sxs-lookup"><span data-stu-id="4938e-106">There are three interfaces in the extensible object pattern: <xref:System.ServiceModel.IExtensibleObject%601>, <xref:System.ServiceModel.IExtension%601>, and <xref:System.ServiceModel.IExtensionCollection%601>.</span></span>  
  
 <span data-ttu-id="4938e-107"><xref:System.ServiceModel.IExtensibleObject%601> Rozhraní je implementováno modulem typy, které umožňují <xref:System.ServiceModel.IExtension%601> objekty, které chcete přizpůsobit jejich funkce.</span><span class="sxs-lookup"><span data-stu-id="4938e-107">The <xref:System.ServiceModel.IExtensibleObject%601> interface is implemented by types that allow <xref:System.ServiceModel.IExtension%601> objects to customize their functionality.</span></span>  
  
 <span data-ttu-id="4938e-108">Rozšiřitelné objekty povolit dynamické agregace <xref:System.ServiceModel.IExtension%601> objekty.</span><span class="sxs-lookup"><span data-stu-id="4938e-108">Extensible objects allow dynamic aggregation of <xref:System.ServiceModel.IExtension%601> objects.</span></span> <span data-ttu-id="4938e-109"><xref:System.ServiceModel.IExtension%601>objekty jsou charakteristické následující rozhraní:</span><span class="sxs-lookup"><span data-stu-id="4938e-109"><xref:System.ServiceModel.IExtension%601> objects are characterized by the following interface:</span></span>  
  
```  
public interface IExtension<T>  
where T : IExtensibleObject<T>  
{  
    void Attach(T owner);  
    void Detach(T owner);  
}  
```  
  
 <span data-ttu-id="4938e-110">Omezení typu zaručuje, že rozšíření může být definovaný jenom pro třídy, které jsou <xref:System.ServiceModel.IExtensibleObject%601>.</span><span class="sxs-lookup"><span data-stu-id="4938e-110">The type restriction guarantees that extensions can only be defined for classes that are <xref:System.ServiceModel.IExtensibleObject%601>.</span></span> <span data-ttu-id="4938e-111"><xref:System.ServiceModel.IExtension%601.Attach%2A>a <xref:System.ServiceModel.IExtension%601.Detach%2A> poskytnout oznámení o agregace nebo členění.</span><span class="sxs-lookup"><span data-stu-id="4938e-111"><xref:System.ServiceModel.IExtension%601.Attach%2A> and <xref:System.ServiceModel.IExtension%601.Detach%2A> provide notification of aggregation or disaggregation.</span></span>  
  
 <span data-ttu-id="4938e-112">Je platná pro implementace omezit, když se může přidat nebo odebrat z vlastníka.</span><span class="sxs-lookup"><span data-stu-id="4938e-112">It is valid for implementations to restrict when they may be added and removed from an owner.</span></span> <span data-ttu-id="4938e-113">Například můžete zcela, zakáže odebrání zákaz přidávání nebo odebírání rozšíření, když jsou vlastníka nebo rozšíření v určitých stavu, zakáže přidávání do několika vlastníky souběžně nebo Povolit jenom jeden přidání následuje jeden odebrat.</span><span class="sxs-lookup"><span data-stu-id="4938e-113">For example, you can disallow removal entirely, disallowing adding or removing extensions when the owner or extension are in a certain state, disallow adding to multiple owners concurrently, or allow only a single addition followed by a single remove.</span></span>  
  
 <span data-ttu-id="4938e-114"><xref:System.ServiceModel.IExtension%601>všechny interakce s další standardní spravovaná rozhraní není určeno.</span><span class="sxs-lookup"><span data-stu-id="4938e-114"><xref:System.ServiceModel.IExtension%601> does not imply any interactions with other standard managed interfaces.</span></span> <span data-ttu-id="4938e-115">Konkrétně <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> metoda objektu vlastníka není odpojit normálně jejich rozšíření.</span><span class="sxs-lookup"><span data-stu-id="4938e-115">Specifically, the <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> method on the owner object does not normally detach its extensions.</span></span>  
  
 <span data-ttu-id="4938e-116">Při přidání rozšíření do kolekce, <xref:System.ServiceModel.IExtension%601.Attach%2A> je volána před přejde do kolekce.</span><span class="sxs-lookup"><span data-stu-id="4938e-116">When an extension is added to the collection, <xref:System.ServiceModel.IExtension%601.Attach%2A> is called before it goes into the collection.</span></span> <span data-ttu-id="4938e-117">Pokud rozšíření je odebrán z kolekce, <xref:System.ServiceModel.IExtension%601.Detach%2A> je volána po jejím odebrání.</span><span class="sxs-lookup"><span data-stu-id="4938e-117">When an extension is removed from the collection, <xref:System.ServiceModel.IExtension%601.Detach%2A> is called after it is removed.</span></span> <span data-ttu-id="4938e-118">To znamená (za předpokladu, že příslušné synchronizace) rozšíření Dal spočítat na nalezené pouze v kolekci bude během je mezi <xref:System.ServiceModel.IExtension%601.Attach%2A> a <xref:System.ServiceModel.IExtension%601.Detach%2A>.</span><span class="sxs-lookup"><span data-stu-id="4938e-118">This means (assuming appropriate synchronization) an extension can count on only being found in the collection while it is between <xref:System.ServiceModel.IExtension%601.Attach%2A> and <xref:System.ServiceModel.IExtension%601.Detach%2A>.</span></span>  
  
 <span data-ttu-id="4938e-119">Předaný objekt <xref:System.ServiceModel.IExtensionCollection%601.FindAll%60%601%2A> nebo <xref:System.ServiceModel.IExtensionCollection%601.Find%60%601%2A> nemusí být <xref:System.ServiceModel.IExtension%601> (například můžete předat libovolný objekt), ale je vrácená rozšíření <xref:System.ServiceModel.IExtension%601>.</span><span class="sxs-lookup"><span data-stu-id="4938e-119">The object passed to <xref:System.ServiceModel.IExtensionCollection%601.FindAll%60%601%2A> or <xref:System.ServiceModel.IExtensionCollection%601.Find%60%601%2A> need not be <xref:System.ServiceModel.IExtension%601> (for example, you can pass any object), but the returned extension is an <xref:System.ServiceModel.IExtension%601>.</span></span>  
  
 <span data-ttu-id="4938e-120">Pokud je bez přípony v kolekci <xref:System.ServiceModel.IExtension%601>, <xref:System.ServiceModel.IExtensionCollection%601.Find%60%601%2A> , vrátí hodnotu null, a <xref:System.ServiceModel.IExtensionCollection%601.FindAll%60%601%2A> vrátí prázdnou kolekci.</span><span class="sxs-lookup"><span data-stu-id="4938e-120">If no extension in the collection is an <xref:System.ServiceModel.IExtension%601>, <xref:System.ServiceModel.IExtensionCollection%601.Find%60%601%2A> returns null, and <xref:System.ServiceModel.IExtensionCollection%601.FindAll%60%601%2A> returns an empty collection.</span></span> <span data-ttu-id="4938e-121">Pokud se několik rozšíření implementovat <xref:System.ServiceModel.IExtension%601>, <xref:System.ServiceModel.IExtensionCollection%601.Find%60%601%2A> vrátí jeden z nich.</span><span class="sxs-lookup"><span data-stu-id="4938e-121">If multiple extensions implement <xref:System.ServiceModel.IExtension%601>, <xref:System.ServiceModel.IExtensionCollection%601.Find%60%601%2A> returns one of them.</span></span> <span data-ttu-id="4938e-122">Hodnota vrácená z <xref:System.ServiceModel.IExtensionCollection%601.FindAll%60%601%2A> je snímek.</span><span class="sxs-lookup"><span data-stu-id="4938e-122">The value returned from <xref:System.ServiceModel.IExtensionCollection%601.FindAll%60%601%2A> is a snapshot.</span></span>  
  
 <span data-ttu-id="4938e-123">Existují dva základní scénáře.</span><span class="sxs-lookup"><span data-stu-id="4938e-123">There are two main scenarios.</span></span> <span data-ttu-id="4938e-124">První scénář se používá <xref:System.ServiceModel.IExtensibleObject%601.Extensions%2A> vlastnost jako slovník na základě typu vložení stavu objektu povolení jiné součásti a vyhledejte ho pomocí daného typu.</span><span class="sxs-lookup"><span data-stu-id="4938e-124">The first scenario uses the <xref:System.ServiceModel.IExtensibleObject%601.Extensions%2A> property as a type-based dictionary to insert state on an object to enable another component to look it up using the type.</span></span>  
  
 <span data-ttu-id="4938e-125">Druhý scénář se používá <xref:System.ServiceModel.IExtension%601.Attach%2A> a <xref:System.ServiceModel.IExtension%601.Detach%2A> vlastnosti, které chcete povolit objekt zapojit se do vlastní chování, jako je registrace pro události, sledování přechodů mezi stavy a tak dále.</span><span class="sxs-lookup"><span data-stu-id="4938e-125">The second scenario uses the <xref:System.ServiceModel.IExtension%601.Attach%2A> and <xref:System.ServiceModel.IExtension%601.Detach%2A> properties to enable an object to participate in custom behavior, such as registering for events, watching state transitions, and so on.</span></span>  
  
 <span data-ttu-id="4938e-126"><xref:System.ServiceModel.IExtensionCollection%601> Rozhraní je kolekce <xref:System.ServiceModel.IExtension%601> objekty, které umožňují pro načítání <xref:System.ServiceModel.IExtension%601> podle jeho typu.</span><span class="sxs-lookup"><span data-stu-id="4938e-126">The <xref:System.ServiceModel.IExtensionCollection%601> interface is a collection of the <xref:System.ServiceModel.IExtension%601> objects that allow for retrieving the <xref:System.ServiceModel.IExtension%601> by its type.</span></span> <span data-ttu-id="4938e-127"><xref:System.ServiceModel.IExtensionCollection%601.Find%60%601%2A?displayProperty=nameWithType>Vrátí naposledy přidat objekt, který je <xref:System.ServiceModel.IExtension%601> daného typu.</span><span class="sxs-lookup"><span data-stu-id="4938e-127"><xref:System.ServiceModel.IExtensionCollection%601.Find%60%601%2A?displayProperty=nameWithType> returns the most recently added object that is an <xref:System.ServiceModel.IExtension%601> of that type.</span></span>  
  
### <a name="extensible-objects-in-windows-communication-foundation"></a><span data-ttu-id="4938e-128">Rozšiřitelné objekty ve službě Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="4938e-128">Extensible Objects in Windows Communication Foundation</span></span>  
 <span data-ttu-id="4938e-129">Existují čtyři rozšiřitelné objekty v [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="4938e-129">There are four extensible objects in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]:</span></span>  
  
-   <span data-ttu-id="4938e-130"><xref:System.ServiceModel.ServiceHostBase>– Toto je základní třída pro hostitele služby.</span><span class="sxs-lookup"><span data-stu-id="4938e-130"><xref:System.ServiceModel.ServiceHostBase> – This is the base class for the service’s host.</span></span>  <span data-ttu-id="4938e-131">Rozšíření této třídy lze použít k rozšíření chování <xref:System.ServiceModel.ServiceHostBase> sám sebe nebo ukládání stavu pro každou službu.</span><span class="sxs-lookup"><span data-stu-id="4938e-131">Extensions of this class can be used to extend the behavior of the <xref:System.ServiceModel.ServiceHostBase> itself or to store the state for each service.</span></span>  
  
-   <span data-ttu-id="4938e-132"><xref:System.ServiceModel.InstanceContext>– Tato třída připojí instance typu služby s modulem runtime služby.</span><span class="sxs-lookup"><span data-stu-id="4938e-132"><xref:System.ServiceModel.InstanceContext> – This class connects an instance of the service’s type with the service runtime.</span></span>  <span data-ttu-id="4938e-133">Obsahuje informace o instanci, jakož i odkaz na <xref:System.ServiceModel.InstanceContext>obsahující <xref:System.ServiceModel.ServiceHostBase>.</span><span class="sxs-lookup"><span data-stu-id="4938e-133">It contains information about the instance as well as a reference to the <xref:System.ServiceModel.InstanceContext>'s containing <xref:System.ServiceModel.ServiceHostBase>.</span></span> <span data-ttu-id="4938e-134">Rozšíření této třídy lze použít k rozšíření chování <xref:System.ServiceModel.InstanceContext> nebo ukládání stavu pro každou službu.</span><span class="sxs-lookup"><span data-stu-id="4938e-134">Extensions of this class can be used to extend the behavior of the <xref:System.ServiceModel.InstanceContext> or to store the state for each service.</span></span>  
  
-   <span data-ttu-id="4938e-135"><xref:System.ServiceModel.OperationContext>– Tato třída reprezentuje operaci informace, které shromažďuje modulu runtime pro každou operaci.</span><span class="sxs-lookup"><span data-stu-id="4938e-135"><xref:System.ServiceModel.OperationContext> – This class represents the operation information that the runtime gathers for each operation.</span></span>  <span data-ttu-id="4938e-136">To zahrnuje informace, jako je záhlaví příchozích zpráv, příchozí vlastnosti zprávy, příchozí identity zabezpečení a další informace.</span><span class="sxs-lookup"><span data-stu-id="4938e-136">This includes information such as the incoming message headers, the incoming message properties, the incoming security identity, and other information.</span></span>  <span data-ttu-id="4938e-137">Rozšíření této třídy můžete buď rozšířit chování <xref:System.ServiceModel.OperationContext> nebo uložit stav pro každou operaci.</span><span class="sxs-lookup"><span data-stu-id="4938e-137">Extensions of this class can either extend the behavior of <xref:System.ServiceModel.OperationContext> or store the state for each operation.</span></span>  
  
-   <span data-ttu-id="4938e-138"><xref:System.ServiceModel.IContextChannel>– Toto rozhraní umožňuje kontrola každý stav pro kanály a proxy servery, které jsou vytvořené [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] modulu runtime.</span><span class="sxs-lookup"><span data-stu-id="4938e-138"><xref:System.ServiceModel.IContextChannel> – This interface allows for the inspection of each state for the channels and proxies built by the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] runtime.</span></span>  <span data-ttu-id="4938e-139">Rozšíření této třídy můžete buď rozšířit chování <xref:System.ServiceModel.IClientChannel> nebo můžete použít k uložení stavu pro každý kanál.</span><span class="sxs-lookup"><span data-stu-id="4938e-139">Extensions of this class can either extend the behavior of <xref:System.ServiceModel.IClientChannel> or can use it to store the state for each channel.</span></span>  
  
-  
  
 <span data-ttu-id="4938e-140">Následující příklad kódu ukazuje použití jednoduchého rozšíření sledovat <xref:System.ServiceModel.InstanceContext> objekty.</span><span class="sxs-lookup"><span data-stu-id="4938e-140">The following code example shows the use of a simple extension to track <xref:System.ServiceModel.InstanceContext> objects.</span></span>  
  
 [!code-csharp[IInstanceContextInitializer#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/iinstancecontextinitializer/cs/initializer.cs#1)]  
  
## <a name="see-also"></a><span data-ttu-id="4938e-141">Viz také</span><span class="sxs-lookup"><span data-stu-id="4938e-141">See Also</span></span>  
 <xref:System.ServiceModel.IExtensibleObject%601>  
 <xref:System.ServiceModel.IExtension%601>  
 <xref:System.ServiceModel.IExtensionCollection%601>
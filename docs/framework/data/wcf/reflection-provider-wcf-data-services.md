---
title: "Reflexe zprostředkovatele (služby WCF Data Services)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WCF Data Services, providers
ms.assetid: ef5ba300-6d7c-455e-a7bd-d0cc6d211ad4
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 865fbf4195b9005e4fbc9ebf6b1e3140b11df85d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="reflection-provider-wcf-data-services"></a><span data-ttu-id="8fd56-102">Reflexe zprostředkovatele (služby WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="8fd56-102">Reflection Provider (WCF Data Services)</span></span>
<span data-ttu-id="8fd56-103">Kromě úniku dat z datového modelu prostřednictvím rozhraní Entity Framework [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] můžou zpřístupnit data, která není definován výhradně ve model na základě entity.</span><span class="sxs-lookup"><span data-stu-id="8fd56-103">In addition to exposing data from a data model through the Entity Framework, [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] can expose data that is not strictly defined in an entity-based model.</span></span> <span data-ttu-id="8fd56-104">Zprostředkovatel reflexe poskytuje data v třídy, které návratové typy, které implementují <xref:System.Linq.IQueryable%601> rozhraní.</span><span class="sxs-lookup"><span data-stu-id="8fd56-104">The reflection provider exposes data in classes that return types that implement the <xref:System.Linq.IQueryable%601> interface.</span></span> [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="8fd56-105">odvození datový model pro tyto třídy pomocí reflexe a může překládat adresy vytvářet dotazy na prostředky do jazyka integrovaného dotazu (LINQ) – na základě dotazů vůči zveřejněné <xref:System.Linq.IQueryable%601> typy.</span><span class="sxs-lookup"><span data-stu-id="8fd56-105"> uses reflection to infer a data model for these classes and can translate address-based queries against resources into language integrated query (LINQ)-based queries against the exposed <xref:System.Linq.IQueryable%601> types.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8fd56-106">Můžete použít <xref:System.Linq.Queryable.AsQueryable%2A> metodu pro návrat <xref:System.Linq.IQueryable%601> z libovolné třídy, který implementuje rozhraní <xref:System.Collections.Generic.IEnumerable%601> rozhraní.</span><span class="sxs-lookup"><span data-stu-id="8fd56-106">You can use the <xref:System.Linq.Queryable.AsQueryable%2A> method to return an <xref:System.Linq.IQueryable%601> interface from any class that implements the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="8fd56-107">To umožňuje nejvíce obecné typy kolekcí má být použit jako zdroj dat pro služby data.</span><span class="sxs-lookup"><span data-stu-id="8fd56-107">This enables most generic collection types to be used as a data source for your data service.</span></span>  
  
 <span data-ttu-id="8fd56-108">Reflexe poskytovatel podporuje hierarchie typů.</span><span class="sxs-lookup"><span data-stu-id="8fd56-108">The reflection provider supports type hierarchies.</span></span> <span data-ttu-id="8fd56-109">Další informace najdete v tématu [postupy: vytvoření služby Data pomocí poskytovatele reflexe](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="8fd56-109">For more information, see [How to: Create a Data Service Using the Reflection Provider](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md).</span></span>  
  
## <a name="inferring-the-data-model"></a><span data-ttu-id="8fd56-110">Odvození datový Model</span><span class="sxs-lookup"><span data-stu-id="8fd56-110">Inferring the Data Model</span></span>  
 <span data-ttu-id="8fd56-111">Když vytváříte službu data, zprostředkovatele odvodí datový model pomocí reflexe.</span><span class="sxs-lookup"><span data-stu-id="8fd56-111">When you create the data service, the provider infers the data model by using reflection.</span></span> <span data-ttu-id="8fd56-112">Následující seznam uvádí, jak zprostředkovatele reflexe odvodí datový model:</span><span class="sxs-lookup"><span data-stu-id="8fd56-112">The following list shows how the reflection provider infers the data model:</span></span>  
  
-   <span data-ttu-id="8fd56-113">Kontejneru entit – třída, která zveřejňuje data jako vlastnosti, které vracejí <xref:System.Linq.IQueryable%601> instance.</span><span class="sxs-lookup"><span data-stu-id="8fd56-113">Entity container - the class that exposes the data as properties that return an <xref:System.Linq.IQueryable%601> instance.</span></span> <span data-ttu-id="8fd56-114">Při adresování model dat na základě reflexe kontejneru entit představuje kořenový adresář služby.</span><span class="sxs-lookup"><span data-stu-id="8fd56-114">When you address a reflection-based data model, the entity container represents the root of the service.</span></span> <span data-ttu-id="8fd56-115">Kontejner – třída pouze jednu entitu je podporována pro daný obor názvů.</span><span class="sxs-lookup"><span data-stu-id="8fd56-115">Only one entity container class is supported for a given namespace.</span></span>  
  
-   <span data-ttu-id="8fd56-116">Nastaví entity – vlastnosti, které vracejí <xref:System.Linq.IQueryable%601> instance jsou považovány za sady entit.</span><span class="sxs-lookup"><span data-stu-id="8fd56-116">Entity sets - properties that return <xref:System.Linq.IQueryable%601> instances are treated as entity sets.</span></span> <span data-ttu-id="8fd56-117">Sad entit řešeny přímo jako prostředky v dotazu.</span><span class="sxs-lookup"><span data-stu-id="8fd56-117">Entity sets are addressed directly as resources in the query.</span></span> <span data-ttu-id="8fd56-118">Může vrátit pouze jednu vlastnost v kontejneru entit <xref:System.Linq.IQueryable%601> instanci daného typu.</span><span class="sxs-lookup"><span data-stu-id="8fd56-118">Only one property on the entity container can return an <xref:System.Linq.IQueryable%601> instance of a given type.</span></span>  
  
-   <span data-ttu-id="8fd56-119">Typy entit – typ `T` z <xref:System.Linq.IQueryable%601> , vrátí sady entit.</span><span class="sxs-lookup"><span data-stu-id="8fd56-119">Entity types - the type `T` of the <xref:System.Linq.IQueryable%601> that the entity set returns.</span></span> <span data-ttu-id="8fd56-120">Třídy, které jsou součástí hierarchie dědičnosti se přeložit poskytovatelem reflexe na ekvivalentní entity typu hierarchie.</span><span class="sxs-lookup"><span data-stu-id="8fd56-120">Classes that are part of an inheritance hierarchy are translated by the reflection provider into an equivalent entity type hierarchy.</span></span>  
  
-   <span data-ttu-id="8fd56-121">Klíče entit – třída každý data, která je typ entity, musí mít klíčovou vlastnost.</span><span class="sxs-lookup"><span data-stu-id="8fd56-121">Entity keys - each data class that is an entity type must have a key property.</span></span> <span data-ttu-id="8fd56-122">Tato vlastnost je opatřená <xref:System.Data.Services.Common.DataServiceKeyAttribute> atribut (`[DataServiceKeyAttribute]`).</span><span class="sxs-lookup"><span data-stu-id="8fd56-122">This property is attributed with the <xref:System.Data.Services.Common.DataServiceKeyAttribute> attribute (`[DataServiceKeyAttribute]`).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8fd56-123">Byste měli použít pouze <xref:System.Data.Services.Common.DataServiceKeyAttribute> atribut na vlastnost, která slouží k jednoznačné identifikaci instance typu entity.</span><span class="sxs-lookup"><span data-stu-id="8fd56-123">You should only apply the <xref:System.Data.Services.Common.DataServiceKeyAttribute> attribute to a property that can be used to uniquely identify an instance of the entity type.</span></span> <span data-ttu-id="8fd56-124">Tento atribut je ignorována, pokud se použije k navigační vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="8fd56-124">This attribute is ignored when applied to a navigation property.</span></span>  
  
-   <span data-ttu-id="8fd56-125">Vlastnosti typu entity - jiné než klíči entity zprostředkovatele reflexe zpracovává přístupný, bez indexer vlastnosti třídy, která je typ entity následujícím způsobem:</span><span class="sxs-lookup"><span data-stu-id="8fd56-125">Entity type properties - other than the entity key, the reflection provider treats the accessible, non-indexer properties of a class that is an entity type as follows:</span></span>  
  
    -   <span data-ttu-id="8fd56-126">Pokud vlastnost vrací primitivní typ, se předpokládá vlastnost jako vlastnost typu entity.</span><span class="sxs-lookup"><span data-stu-id="8fd56-126">If the property returns a primitive type, then the property is assumed to be a property of an entity type.</span></span>  
  
    -   <span data-ttu-id="8fd56-127">Pokud vlastnost vrátí typ, který je také typ entity, se předpokládá vlastnost jako vlastnost navigace, která představuje "1" Konec relace n: 1 nebo 1: 1.</span><span class="sxs-lookup"><span data-stu-id="8fd56-127">If the property returns a type that is also an entity type, then the property is assumed to be a navigation property that represents the "one" end of a many-to-one or one-to-one relationship.</span></span>  
  
    -   <span data-ttu-id="8fd56-128">Pokud vlastnost vrací <xref:System.Collections.Generic.IEnumerable%601> typu entity, pak vlastnost předpokládá se, že navigační vlastnost, která představuje "n" konec vztah jeden mnoho nebo n: n.</span><span class="sxs-lookup"><span data-stu-id="8fd56-128">If the property returns an <xref:System.Collections.Generic.IEnumerable%601> of an entity type, then the property is assumed to be a navigation property that represents the "many" end of a one-to-many or many-to-many relationship.</span></span>  
  
    -   <span data-ttu-id="8fd56-129">Pokud je návratový typ vlastnosti typ hodnoty, představuje vlastnost komplexního typu.</span><span class="sxs-lookup"><span data-stu-id="8fd56-129">If the return type of the property is a value type, then the property represents a complex type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8fd56-130">Na rozdíl od datový model, který je založen na modelu entity relační modely, které jsou založené na zprostředkovateli reflexe není srozumitelný relační data.</span><span class="sxs-lookup"><span data-stu-id="8fd56-130">Unlike a data model that is based on the entity-relational model, models that are based on the reflection provider do not understand relational data.</span></span> <span data-ttu-id="8fd56-131">Rozhraní Entity Framework by měl použít ke zveřejnění relačních dat prostřednictvím [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8fd56-131">You should use the Entity Framework to expose relational data through [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].</span></span>  
  
## <a name="data-type-mapping"></a><span data-ttu-id="8fd56-132">Mapování datového typu</span><span class="sxs-lookup"><span data-stu-id="8fd56-132">Data Type Mapping</span></span>  
 <span data-ttu-id="8fd56-133">Když datový model je odvozen z tříd rozhraní .NET Framework, primitivní typy v datovém modelu mapovány na rozhraní .NET Framework datové typy následujícím způsobem:</span><span class="sxs-lookup"><span data-stu-id="8fd56-133">When a data model is inferred from .NET Framework classes, the primitive types in the data model are mapped to .NET Framework data types as follows:</span></span>  
  
|<span data-ttu-id="8fd56-134">Datový typ rozhraní .NET framework</span><span class="sxs-lookup"><span data-stu-id="8fd56-134">.NET Framework data type</span></span>|<span data-ttu-id="8fd56-135">Typ modelu dat</span><span class="sxs-lookup"><span data-stu-id="8fd56-135">Data model type</span></span>|  
|------------------------------|---------------------|  
|<span data-ttu-id="8fd56-136"><xref:System.Byte>`[]`</span><span class="sxs-lookup"><span data-stu-id="8fd56-136"><xref:System.Byte> `[]`</span></span>|`Edm.Binary`|  
|<xref:System.Boolean>|`Edm.Boolean`|  
|<xref:System.Byte>|`Edm.Byte`|  
|<xref:System.DateTime>|`Edm.DateTime`|  
|<xref:System.Decimal>|`Edm.Decimal`|  
|<xref:System.Double>|`Edm.Double`|  
|<xref:System.Guid>|`Edm.Guid`|  
|<xref:System.Int16>|`Edm.Int16`|  
|<xref:System.Int32>|`Edm.Int32`|  
|<xref:System.Int64>|`Edm.Int64`|  
|<xref:System.SByte>|`Edm.SByte`|  
|<xref:System.Single>|`Edm.Single`|  
|<xref:System.String>|`Edm.String`|  
  
> [!NOTE]
>  <span data-ttu-id="8fd56-137">Typy s možnou hodnotou Null hodnot rozhraní .NET framework, jsou namapované na stejnou modelu typy dat, jako odpovídající typy hodnot, které nelze přiřadit hodnotu null.</span><span class="sxs-lookup"><span data-stu-id="8fd56-137">.NET Framework nullable value types are mapped to the same data model types as the corresponding value types that cannot be assigned a null.</span></span>  
  
## <a name="enabling-updates-in-the-data-model"></a><span data-ttu-id="8fd56-138">Povolení aktualizací v datovém modelu</span><span class="sxs-lookup"><span data-stu-id="8fd56-138">Enabling Updates in the Data Model</span></span>  
 <span data-ttu-id="8fd56-139">Chcete-li povolit aktualizace dat, který je zveřejněný prostřednictvím tento druh datový model, zprostředkovatel reflexe definuje <xref:System.Data.Services.IUpdatable> rozhraní.</span><span class="sxs-lookup"><span data-stu-id="8fd56-139">To allow updates to data that is exposed through this kind of data model, the reflection provider defines an <xref:System.Data.Services.IUpdatable> interface.</span></span> <span data-ttu-id="8fd56-140">Toto rozhraní dá pokyn službu data o tom, jak zachovat aktualizace zveřejněné typy.</span><span class="sxs-lookup"><span data-stu-id="8fd56-140">This interface instructs the data service on how to persist updates to the exposed types.</span></span> <span data-ttu-id="8fd56-141">Chcete-li aktualizace na prostředky, které jsou definovány v datovém modelu, musí implementovat třídu kontejneru entity <xref:System.Data.Services.IUpdatable> rozhraní.</span><span class="sxs-lookup"><span data-stu-id="8fd56-141">To enable updates to resources that are defined by the data model, the entity container class must implement the <xref:System.Data.Services.IUpdatable> interface.</span></span> <span data-ttu-id="8fd56-142">Příklad implementace <xref:System.Data.Services.IUpdatable> rozhraní najdete v tématu [postupy: vytvoření službu dat pomocí LINQ to SQL zdroj dat](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md).</span><span class="sxs-lookup"><span data-stu-id="8fd56-142">For an example of an implementation of the <xref:System.Data.Services.IUpdatable> interface, see [How to: Create a Data Service Using a LINQ to SQL Data Source](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md).</span></span>  
  
 <span data-ttu-id="8fd56-143"><xref:System.Data.Services.IUpdatable> Rozhraní vyžaduje, aby tak, aby aktualizace mohou být přeneseny do zdroje dat pomocí zprostředkovatele reflexe implementovat následující členy:</span><span class="sxs-lookup"><span data-stu-id="8fd56-143">The <xref:System.Data.Services.IUpdatable> interface requires that the following members be implemented so that updates can be propagated to the data source by using the reflection provider:</span></span>  
  
|<span data-ttu-id="8fd56-144">Člen</span><span class="sxs-lookup"><span data-stu-id="8fd56-144">Member</span></span>|<span data-ttu-id="8fd56-145">Popis</span><span class="sxs-lookup"><span data-stu-id="8fd56-145">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Data.Services.IUpdatable.AddReferenceToCollection%2A>|<span data-ttu-id="8fd56-146">Poskytuje funkce, které chcete přidat objekt do kolekce souvisejících objektů, které jsou přístupné z navigační vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="8fd56-146">Provides the functionality to add an object to a collection of related objects that are accessed from a navigation property.</span></span>|  
|<xref:System.Data.Services.IUpdatable.ClearChanges%2A>|<span data-ttu-id="8fd56-147">Poskytuje funkce, která zruší čekající změny v datech.</span><span class="sxs-lookup"><span data-stu-id="8fd56-147">Provides the functionality that cancels pending changes to the data.</span></span>|  
|<xref:System.Data.Services.IUpdatable.CreateResource%2A>|<span data-ttu-id="8fd56-148">Poskytuje funkce pro vytvoření nového prostředku v zadaném kontejneru.</span><span class="sxs-lookup"><span data-stu-id="8fd56-148">Provides the functionality to create a new resource in the specified container.</span></span>|  
|<xref:System.Data.Services.IUpdatable.DeleteResource%2A>|<span data-ttu-id="8fd56-149">Poskytuje funkce odstranění prostředku.</span><span class="sxs-lookup"><span data-stu-id="8fd56-149">Provides the functionality to delete a resource.</span></span>|  
|<xref:System.Data.Services.IUpdatable.GetResource%2A>|<span data-ttu-id="8fd56-150">Poskytuje funkce pro načtení prostředků, která je identifikovaná určitý dotazu a zadejte název.</span><span class="sxs-lookup"><span data-stu-id="8fd56-150">Provides the functionality to retrieve a resource that is identified by a specific query and type name.</span></span>|  
|<xref:System.Data.Services.IUpdatable.GetValue%2A>|<span data-ttu-id="8fd56-151">Poskytuje funkci, která vrátí hodnotu vlastnosti prostředku.</span><span class="sxs-lookup"><span data-stu-id="8fd56-151">Provides the functionality to return the value of a property of a resource.</span></span>|  
|<xref:System.Data.Services.IUpdatable.RemoveReferenceFromCollection%2A>|<span data-ttu-id="8fd56-152">Poskytuje funkce pro odebrat objekt do kolekce souvisejících objektů, které jsou k němu přistupovat z navigační vlastnost.</span><span class="sxs-lookup"><span data-stu-id="8fd56-152">Provides the functionality to remove an object to a collection of related objects accessed from a navigation property.</span></span>|  
|<xref:System.Data.Services.IUpdatable.ResetResource%2A>|<span data-ttu-id="8fd56-153">Poskytuje funkce se aktualizovat zadaný prostředek.</span><span class="sxs-lookup"><span data-stu-id="8fd56-153">Provides the functionality to update a specified resource.</span></span>|  
|<xref:System.Data.Services.IUpdatable.ResolveResource%2A>|<span data-ttu-id="8fd56-154">Poskytuje funkce vrátit prostředků, která je reprezentována instance určitý objekt.</span><span class="sxs-lookup"><span data-stu-id="8fd56-154">Provides the functionality to return the resource that is represented by a specific object instance.</span></span>|  
|<xref:System.Data.Services.IUpdatable.SaveChanges%2A>|<span data-ttu-id="8fd56-155">Poskytuje funkce pro všechny čekající změny uložte.</span><span class="sxs-lookup"><span data-stu-id="8fd56-155">Provides the functionality to save all pending changes.</span></span>|  
|<xref:System.Data.Services.IUpdatable.SetReference%2A>|<span data-ttu-id="8fd56-156">Poskytuje funkce pro nastavení odkazem na objekt v relaci pomocí navigační vlastnost.</span><span class="sxs-lookup"><span data-stu-id="8fd56-156">Provides the functionality to set a related object reference by using a navigation property.</span></span>|  
|<xref:System.Data.Services.IUpdatable.SetValue%2A>|<span data-ttu-id="8fd56-157">Poskytuje funkce pro nastavení hodnoty vlastnosti prostředku.</span><span class="sxs-lookup"><span data-stu-id="8fd56-157">Provides the functionality to set the value of the property of a resource.</span></span>|  
  
## <a name="handling-concurrency"></a><span data-ttu-id="8fd56-158">Zpracování souběžnosti</span><span class="sxs-lookup"><span data-stu-id="8fd56-158">Handling Concurrency</span></span>  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="8fd56-159">podporuje model optimistickou metodu souběžného tím, že vám definovat token souběžnosti pro entitu.</span><span class="sxs-lookup"><span data-stu-id="8fd56-159"> supports an optimistic concurrency model by enabling you to define a concurrency token for an entity.</span></span> <span data-ttu-id="8fd56-160">Tento token souběžnosti, která obsahuje jednu nebo více vlastností entity, se službou data používá k určení, zda data, která jsou požadována, aktualizovaných nebo odstraněných došlo ke změně.</span><span class="sxs-lookup"><span data-stu-id="8fd56-160">This concurrency token, which includes one or more properties of the entity, is used by the data service to determine whether a change has occurred in the data that is being requested, updated, or deleted.</span></span> <span data-ttu-id="8fd56-161">Pokud token hodnoty získané z eTag v žádosti se liší od aktuální hodnoty entity, je vyvolána výjimka službou data.</span><span class="sxs-lookup"><span data-stu-id="8fd56-161">When token values obtained from the eTag in the request differ from the current values of the entity, an exception is raised by the data service.</span></span> <span data-ttu-id="8fd56-162"><xref:System.Data.Services.ETagAttribute> Platí pro typ entity k definování token souběžnosti ve zprostředkovateli reflexe.</span><span class="sxs-lookup"><span data-stu-id="8fd56-162">The <xref:System.Data.Services.ETagAttribute> is applied to an entity type to define a concurrency token in the reflection provider.</span></span> <span data-ttu-id="8fd56-163">Token souběžnosti nemůže obsahovat vlastnost klíče nebo navigační vlastnost.</span><span class="sxs-lookup"><span data-stu-id="8fd56-163">The concurrency token cannot include a key property or a navigation property.</span></span> <span data-ttu-id="8fd56-164">Další informace najdete v tématu [aktualizaci dat služby](../../../../docs/framework/data/wcf/updating-the-data-service-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="8fd56-164">For more information, see [Updating the Data Service](../../../../docs/framework/data/wcf/updating-the-data-service-wcf-data-services.md).</span></span>  
  
## <a name="using-linq-to-sql-with-the-reflection-provider"></a><span data-ttu-id="8fd56-165">Technologie LINQ to SQL pomocí reflexe zprostředkovatele</span><span class="sxs-lookup"><span data-stu-id="8fd56-165">Using LINQ to SQL with the Reflection Provider</span></span>  
 <span data-ttu-id="8fd56-166">Protože ve výchozím nastavení jsou nativně podporovány rozhraní Entity Framework, je zprostředkovatel doporučené dat pro použití relačních dat s [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8fd56-166">Because the Entity Framework is natively supported by default, it is the recommended data provider for using relational data with [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].</span></span> <span data-ttu-id="8fd56-167">Můžete ale poskytovateli reflexe třídy SQL se službou dat pomocí LINQ.</span><span class="sxs-lookup"><span data-stu-id="8fd56-167">However, you can use the reflection provider to use LINQ to SQL classes with a data service.</span></span> <span data-ttu-id="8fd56-168"><xref:System.Data.Linq.Table%601> Způsobit sad, které se vrátí pomocí metody na <xref:System.Data.Linq.DataContext> generované LINQ to SQL Návrhář relací objektů (Návrhář relací objektů) implementace <xref:System.Linq.IQueryable%601> rozhraní.</span><span class="sxs-lookup"><span data-stu-id="8fd56-168">The <xref:System.Data.Linq.Table%601> result sets that are returned by methods on the <xref:System.Data.Linq.DataContext> generated by the LINQ to SQL Object Relational Designer (O/R Designer) implement the <xref:System.Linq.IQueryable%601> interface.</span></span> <span data-ttu-id="8fd56-169">To umožňuje reflexe zprostředkovatele, který má přístup k tyto metody a vrátit entity data ze systému SQL Server pomocí generované třídy LINQ to SQL.</span><span class="sxs-lookup"><span data-stu-id="8fd56-169">This enables the reflection provider to access these methods and return entity data from SQL Server by using the generated LINQ to SQL classes.</span></span> <span data-ttu-id="8fd56-170">Ale protože neimplementuje technologie LINQ to SQL <xref:System.Data.Services.IUpdatable> rozhraní, je nutné přidat konkrétní třídu, která rozšiřuje existující <xref:System.Data.Linq.DataContext> třídu přidat <xref:System.Data.Services.IUpdatable> implementace.</span><span class="sxs-lookup"><span data-stu-id="8fd56-170">However, because LINQ to SQL does not implement the <xref:System.Data.Services.IUpdatable> interface, you need to add a partial class that extends the existing <xref:System.Data.Linq.DataContext> partial class to add the <xref:System.Data.Services.IUpdatable> implementation.</span></span> <span data-ttu-id="8fd56-171">Další informace najdete v tématu [postupy: vytvoření službu dat pomocí LINQ to SQL zdroj dat](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md).</span><span class="sxs-lookup"><span data-stu-id="8fd56-171">For more information, see [How to: Create a Data Service Using a LINQ to SQL Data Source](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fd56-172">Viz také</span><span class="sxs-lookup"><span data-stu-id="8fd56-172">See Also</span></span>  
 [<span data-ttu-id="8fd56-173">Zprostředkovatelé dat služby</span><span class="sxs-lookup"><span data-stu-id="8fd56-173">Data Services Providers</span></span>](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)
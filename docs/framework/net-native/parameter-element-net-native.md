---
title: Element &lt;Parameter&gt; (.NET Native)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 22aaa1f3-596f-4733-93db-f4bcabcb5240
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f603f795682c7ea1f48e5d9356af6e0477246da1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="ltparametergt-element-net-native"></a><span data-ttu-id="a3a98-102">Element &lt;Parameter&gt; (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="a3a98-102">&lt;Parameter&gt; Element (.NET Native)</span></span>
<span data-ttu-id="a3a98-103">Reflexe zásada se vztahuje na typ argument předaný metodě.</span><span class="sxs-lookup"><span data-stu-id="a3a98-103">Applies reflection policy to the type of the argument passed to a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3a98-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="a3a98-104">Syntax</span></span>  
  
```xml  
<Parameter Name="parameter_name"  
           Activate="policy_type"  
           Browse="policy_type"  
           Dynamic="policy_type"  
           Serialize="policy_type"  
           DataContractSerializer="policy_type"  
           DataContractJsonSerializer="policy_type"  
           XmlSerializer="policy_type"  
           MarshalObject="policy_type"  
           MarshalDelegate="policy_type"  
           MarshalStructure="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a3a98-105">Atributy a elementy</span><span class="sxs-lookup"><span data-stu-id="a3a98-105">Attributes and Elements</span></span>  
 <span data-ttu-id="a3a98-106">Následující části popisují atributy, podřízené prvky a nadřazené prvky.</span><span class="sxs-lookup"><span data-stu-id="a3a98-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a3a98-107">Atributy</span><span class="sxs-lookup"><span data-stu-id="a3a98-107">Attributes</span></span>  
  
|<span data-ttu-id="a3a98-108">Atribut</span><span class="sxs-lookup"><span data-stu-id="a3a98-108">Attribute</span></span>|<span data-ttu-id="a3a98-109">Typ atributu</span><span class="sxs-lookup"><span data-stu-id="a3a98-109">Attribute type</span></span>|<span data-ttu-id="a3a98-110">Popis</span><span class="sxs-lookup"><span data-stu-id="a3a98-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="a3a98-111">Obecné</span><span class="sxs-lookup"><span data-stu-id="a3a98-111">General</span></span>|<span data-ttu-id="a3a98-112">Požadovaný atribut.</span><span class="sxs-lookup"><span data-stu-id="a3a98-112">Required attribute.</span></span> <span data-ttu-id="a3a98-113">Název parametru.</span><span class="sxs-lookup"><span data-stu-id="a3a98-113">The parameter name.</span></span> <span data-ttu-id="a3a98-114">Například pro podpis metody `String.CompareTo(Object value)`, hodnota `Name` atribut je "value".</span><span class="sxs-lookup"><span data-stu-id="a3a98-114">For example, for the method signature `String.CompareTo(Object value)`, the value of the `Name` attribute is "value".</span></span>|  
|`Activate`|<span data-ttu-id="a3a98-115">Reflexe</span><span class="sxs-lookup"><span data-stu-id="a3a98-115">Reflection</span></span>|<span data-ttu-id="a3a98-116">Nepovinný atribut.</span><span class="sxs-lookup"><span data-stu-id="a3a98-116">Optional attribute.</span></span> <span data-ttu-id="a3a98-117">Ovládací prvky runtime přístup k konstruktory povolit aktivace instancí.</span><span class="sxs-lookup"><span data-stu-id="a3a98-117">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="a3a98-118">Reflexe</span><span class="sxs-lookup"><span data-stu-id="a3a98-118">Reflection</span></span>|<span data-ttu-id="a3a98-119">Nepovinný atribut.</span><span class="sxs-lookup"><span data-stu-id="a3a98-119">Optional attribute.</span></span> <span data-ttu-id="a3a98-120">Ovládací prvky dotazování na informace o programu elementů, ale nepovolí žádné přístup k modulu runtime.</span><span class="sxs-lookup"><span data-stu-id="a3a98-120">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="a3a98-121">Reflexe</span><span class="sxs-lookup"><span data-stu-id="a3a98-121">Reflection</span></span>|<span data-ttu-id="a3a98-122">Nepovinný atribut.</span><span class="sxs-lookup"><span data-stu-id="a3a98-122">Optional attribute.</span></span> <span data-ttu-id="a3a98-123">Řídí přístup k modulu runtime pro všechny členy typu, včetně konstruktory, metody, polí, vlastnosti a události, chcete-li povolit dynamické programování.</span><span class="sxs-lookup"><span data-stu-id="a3a98-123">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="a3a98-124">Serializace</span><span class="sxs-lookup"><span data-stu-id="a3a98-124">Serialization</span></span>|<span data-ttu-id="a3a98-125">Nepovinný atribut.</span><span class="sxs-lookup"><span data-stu-id="a3a98-125">Optional attribute.</span></span> <span data-ttu-id="a3a98-126">Ovládací prvky runtime přístup k konstruktory, pole a vlastnosti, aby instance typu serializovat a deserializovat pomocí knihovny například serializátor Newtonsoft JSON.</span><span class="sxs-lookup"><span data-stu-id="a3a98-126">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="a3a98-127">Serializace</span><span class="sxs-lookup"><span data-stu-id="a3a98-127">Serialization</span></span>|<span data-ttu-id="a3a98-128">Nepovinný atribut.</span><span class="sxs-lookup"><span data-stu-id="a3a98-128">Optional attribute.</span></span> <span data-ttu-id="a3a98-129">Zásady pro serializaci, který používá ovládací prvky <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> třídy.</span><span class="sxs-lookup"><span data-stu-id="a3a98-129">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="a3a98-130">Serializace</span><span class="sxs-lookup"><span data-stu-id="a3a98-130">Serialization</span></span>|<span data-ttu-id="a3a98-131">Nepovinný atribut.</span><span class="sxs-lookup"><span data-stu-id="a3a98-131">Optional attribute.</span></span> <span data-ttu-id="a3a98-132">Zásady pro serializaci JSON, který používá ovládací prvky <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> třídy.</span><span class="sxs-lookup"><span data-stu-id="a3a98-132">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="a3a98-133">Serializace</span><span class="sxs-lookup"><span data-stu-id="a3a98-133">Serialization</span></span>|<span data-ttu-id="a3a98-134">Nepovinný atribut.</span><span class="sxs-lookup"><span data-stu-id="a3a98-134">Optional attribute.</span></span> <span data-ttu-id="a3a98-135">Zásady pro serializaci XML, který používá ovládací prvky <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> třídy.</span><span class="sxs-lookup"><span data-stu-id="a3a98-135">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="a3a98-136">Zprostředkovatel komunikace s objekty</span><span class="sxs-lookup"><span data-stu-id="a3a98-136">Interop</span></span>|<span data-ttu-id="a3a98-137">Nepovinný atribut.</span><span class="sxs-lookup"><span data-stu-id="a3a98-137">Optional attribute.</span></span> <span data-ttu-id="a3a98-138">Ovládací prvky zásady pro zařazování odkazové typy WinRT a COM.</span><span class="sxs-lookup"><span data-stu-id="a3a98-138">Controls policy for marshaling reference types to WinRT and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="a3a98-139">Zprostředkovatel komunikace s objekty</span><span class="sxs-lookup"><span data-stu-id="a3a98-139">Interop</span></span>|<span data-ttu-id="a3a98-140">Nepovinný atribut.</span><span class="sxs-lookup"><span data-stu-id="a3a98-140">Optional attribute.</span></span> <span data-ttu-id="a3a98-141">Ovládací prvky zásady pro zařazování delegáta typy jako ukazatelů na funkce do nativního kódu.</span><span class="sxs-lookup"><span data-stu-id="a3a98-141">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="a3a98-142">Zprostředkovatel komunikace s objekty</span><span class="sxs-lookup"><span data-stu-id="a3a98-142">Interop</span></span>|<span data-ttu-id="a3a98-143">Nepovinný atribut.</span><span class="sxs-lookup"><span data-stu-id="a3a98-143">Optional attribute.</span></span> <span data-ttu-id="a3a98-144">Ovládací prvky zásady pro zařazování typů hodnot do nativního kódu.</span><span class="sxs-lookup"><span data-stu-id="a3a98-144">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="a3a98-145">Atribut Name.</span><span class="sxs-lookup"><span data-stu-id="a3a98-145">Name attribute</span></span>  
  
|<span data-ttu-id="a3a98-146">Hodnota</span><span class="sxs-lookup"><span data-stu-id="a3a98-146">Value</span></span>|<span data-ttu-id="a3a98-147">Popis</span><span class="sxs-lookup"><span data-stu-id="a3a98-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a3a98-148">*parameter_name*</span><span class="sxs-lookup"><span data-stu-id="a3a98-148">*parameter_name*</span></span>|<span data-ttu-id="a3a98-149">Název parametru metody, pro které zásada platí.</span><span class="sxs-lookup"><span data-stu-id="a3a98-149">The name of the method parameter to which policy is applied.</span></span> <span data-ttu-id="a3a98-150">Například pro podpis metody `String.CompareTo(Object value)`, hodnota `Name` atribut je "value".</span><span class="sxs-lookup"><span data-stu-id="a3a98-150">For example, for the method signature `String.CompareTo(Object value)`, the value of the `Name` attribute is "value".</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="a3a98-151">Všechny ostatní atributy</span><span class="sxs-lookup"><span data-stu-id="a3a98-151">All other attributes</span></span>  
  
|<span data-ttu-id="a3a98-152">Hodnota</span><span class="sxs-lookup"><span data-stu-id="a3a98-152">Value</span></span>|<span data-ttu-id="a3a98-153">Popis</span><span class="sxs-lookup"><span data-stu-id="a3a98-153">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a3a98-154">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="a3a98-154">*policy_setting*</span></span>|<span data-ttu-id="a3a98-155">Nastavení, které chcete použít pro tento typ zásad.</span><span class="sxs-lookup"><span data-stu-id="a3a98-155">The setting to apply to this policy type.</span></span> <span data-ttu-id="a3a98-156">Možné hodnoty jsou `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, a `Required All`.</span><span class="sxs-lookup"><span data-stu-id="a3a98-156">Possible values are `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="a3a98-157">Další informace najdete v tématu [nastavení zásad direktivy modulu Runtime](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="a3a98-157">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a3a98-158">Podřízené elementy</span><span class="sxs-lookup"><span data-stu-id="a3a98-158">Child Elements</span></span>  
 <span data-ttu-id="a3a98-159">Žádné</span><span class="sxs-lookup"><span data-stu-id="a3a98-159">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a3a98-160">Nadřazené elementy</span><span class="sxs-lookup"><span data-stu-id="a3a98-160">Parent Elements</span></span>  
  
|<span data-ttu-id="a3a98-161">Prvek</span><span class="sxs-lookup"><span data-stu-id="a3a98-161">Element</span></span>|<span data-ttu-id="a3a98-162">Popis</span><span class="sxs-lookup"><span data-stu-id="a3a98-162">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a3a98-163">\<Metoda ></span><span class="sxs-lookup"><span data-stu-id="a3a98-163">\<Method></span></span>](../../../docs/framework/net-native/method-element-net-native.md)|<span data-ttu-id="a3a98-164">Platí zásady reflexe modulu runtime pro konstruktor nebo metoda.</span><span class="sxs-lookup"><span data-stu-id="a3a98-164">Applies runtime reflection policy to a constructor or method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a3a98-165">Poznámky</span><span class="sxs-lookup"><span data-stu-id="a3a98-165">Remarks</span></span>  
 <span data-ttu-id="a3a98-166">`<Parameter>` Element je podřízená [ \<metoda >](../../../docs/framework/net-native/method-element-net-native.md) element a se používá k aplikování zásad na konkrétní metoda parametr.</span><span class="sxs-lookup"><span data-stu-id="a3a98-166">The `<Parameter>` element is a child of the [\<Method>](../../../docs/framework/net-native/method-element-net-native.md) element and is used to apply policy to a particular method parameter.</span></span> <span data-ttu-id="a3a98-167">Je zadaný parametr konkrétní metody podle názvu a nikoli podle typu.</span><span class="sxs-lookup"><span data-stu-id="a3a98-167">The specific method parameter is specified by name rather than by type.</span></span> <span data-ttu-id="a3a98-168">Alespoň jeden atribut, který představuje typ zásad, například `Activate` nebo `Dynamic`, musí být přítomen.</span><span class="sxs-lookup"><span data-stu-id="a3a98-168">At least one attribute that represents a policy type, such as `Activate` or `Dynamic`, must be present.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3a98-169">Viz také</span><span class="sxs-lookup"><span data-stu-id="a3a98-169">See Also</span></span>  
 [<span data-ttu-id="a3a98-170">\<Metoda > elementu</span><span class="sxs-lookup"><span data-stu-id="a3a98-170">\<Method> Element</span></span>](../../../docs/framework/net-native/method-element-net-native.md)  
 [<span data-ttu-id="a3a98-171">Odkaz na soubor konfigurace modulu runtime direktivy (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="a3a98-171">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="a3a98-172">Nastavení zásad direktivy modulu runtime</span><span class="sxs-lookup"><span data-stu-id="a3a98-172">Runtime Directive Policy Settings</span></span>](../../../docs/framework/net-native/runtime-directive-policy-settings.md)  
 [<span data-ttu-id="a3a98-173">Elementy direktivy modulu runtime</span><span class="sxs-lookup"><span data-stu-id="a3a98-173">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
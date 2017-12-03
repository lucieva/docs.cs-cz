---
title: Element &lt;GenericParameter&gt; (.NET Native)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cbd49732-3615-49a5-a900-f96947cdc3e6
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c682c75d4be78e9219a32e2a92520e9f9bfff823
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="ltgenericparametergt-element-net-native"></a><span data-ttu-id="a71d4-102">Element &lt;GenericParameter&gt; (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="a71d4-102">&lt;GenericParameter&gt; Element (.NET Native)</span></span>
<span data-ttu-id="a71d4-103">Zásada se vztahuje na typ parametru obecný typ nebo metoda.</span><span class="sxs-lookup"><span data-stu-id="a71d4-103">Applies policy to the parameter type of a generic type or method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a71d4-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="a71d4-104">Syntax</span></span>  
  
```xml  
<GenericParameter Name="generic_parameter_name"  
                  Activate="policy_type"  
                  Browse="policy_type"  
                  Dynamic="policy_type"  
                  Serialize="policy_type" />  
                  DataContractSerializer="policy_type"  
                  DataContractJsonSerializer="policy_type"  
                  XmlSerializer="policy_type"  
                  MarshalObject="policy_type"  
                  MarshalDelegate="policy_type"  
                  MarshalStructure="policy_type"  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a71d4-105">Atributy a elementy</span><span class="sxs-lookup"><span data-stu-id="a71d4-105">Attributes and Elements</span></span>  
 <span data-ttu-id="a71d4-106">Následující části popisují atributy, podřízené prvky a nadřazené prvky.</span><span class="sxs-lookup"><span data-stu-id="a71d4-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a71d4-107">Atributy</span><span class="sxs-lookup"><span data-stu-id="a71d4-107">Attributes</span></span>  
  
|<span data-ttu-id="a71d4-108">Atribut</span><span class="sxs-lookup"><span data-stu-id="a71d4-108">Attribute</span></span>|<span data-ttu-id="a71d4-109">Typ atributu</span><span class="sxs-lookup"><span data-stu-id="a71d4-109">Attribute type</span></span>|<span data-ttu-id="a71d4-110">Popis</span><span class="sxs-lookup"><span data-stu-id="a71d4-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="a71d4-111">Obecné</span><span class="sxs-lookup"><span data-stu-id="a71d4-111">General</span></span>|<span data-ttu-id="a71d4-112">Požadovaný atribut.</span><span class="sxs-lookup"><span data-stu-id="a71d4-112">Required attribute.</span></span> <span data-ttu-id="a71d4-113">Název obecný parametr.</span><span class="sxs-lookup"><span data-stu-id="a71d4-113">The name of the generic parameter.</span></span> <span data-ttu-id="a71d4-114">Například pro obecný delegát <xref:System.Func%603>, hodnota `Name` atribut je "TResult" pro použití zásad runtime delegáta návratovou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="a71d4-114">For example, for the generic delegate <xref:System.Func%603>, the value of the `Name` attribute is "TResult" to apply runtime policy to the delegate's return value.</span></span>|  
|`Activate`|<span data-ttu-id="a71d4-115">Reflexe</span><span class="sxs-lookup"><span data-stu-id="a71d4-115">Reflection</span></span>|<span data-ttu-id="a71d4-116">Nepovinný atribut.</span><span class="sxs-lookup"><span data-stu-id="a71d4-116">Optional attribute.</span></span> <span data-ttu-id="a71d4-117">Ovládací prvky runtime přístup k konstruktory povolit aktivace instancí.</span><span class="sxs-lookup"><span data-stu-id="a71d4-117">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="a71d4-118">Reflexe</span><span class="sxs-lookup"><span data-stu-id="a71d4-118">Reflection</span></span>|<span data-ttu-id="a71d4-119">Nepovinný atribut.</span><span class="sxs-lookup"><span data-stu-id="a71d4-119">Optional attribute.</span></span> <span data-ttu-id="a71d4-120">Ovládací prvky dotazování na informace o programu elementů, ale nepovolí žádné přístup k modulu runtime.</span><span class="sxs-lookup"><span data-stu-id="a71d4-120">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="a71d4-121">Reflexe</span><span class="sxs-lookup"><span data-stu-id="a71d4-121">Reflection</span></span>|<span data-ttu-id="a71d4-122">Nepovinný atribut.</span><span class="sxs-lookup"><span data-stu-id="a71d4-122">Optional attribute.</span></span> <span data-ttu-id="a71d4-123">Řídí přístup k modulu runtime pro všechny členy typu, včetně konstruktory, metody, polí, vlastnosti a události, chcete-li povolit dynamické programování.</span><span class="sxs-lookup"><span data-stu-id="a71d4-123">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="a71d4-124">Serializace</span><span class="sxs-lookup"><span data-stu-id="a71d4-124">Serialization</span></span>|<span data-ttu-id="a71d4-125">Nepovinný atribut.</span><span class="sxs-lookup"><span data-stu-id="a71d4-125">Optional attribute.</span></span> <span data-ttu-id="a71d4-126">Ovládací prvky runtime přístup k konstruktory, pole a vlastnosti, aby instance typu serializovat a deserializovat pomocí knihovny například serializátor Newtonsoft JSON.</span><span class="sxs-lookup"><span data-stu-id="a71d4-126">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="a71d4-127">Serializace</span><span class="sxs-lookup"><span data-stu-id="a71d4-127">Serialization</span></span>|<span data-ttu-id="a71d4-128">Nepovinný atribut.</span><span class="sxs-lookup"><span data-stu-id="a71d4-128">Optional attribute.</span></span> <span data-ttu-id="a71d4-129">Zásady pro serializaci, který používá ovládací prvky <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> třídy.</span><span class="sxs-lookup"><span data-stu-id="a71d4-129">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="a71d4-130">Serializace</span><span class="sxs-lookup"><span data-stu-id="a71d4-130">Serialization</span></span>|<span data-ttu-id="a71d4-131">Nepovinný atribut.</span><span class="sxs-lookup"><span data-stu-id="a71d4-131">Optional attribute.</span></span> <span data-ttu-id="a71d4-132">Zásady pro serializaci JSON, který používá ovládací prvky <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> třídy.</span><span class="sxs-lookup"><span data-stu-id="a71d4-132">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="a71d4-133">Serializace</span><span class="sxs-lookup"><span data-stu-id="a71d4-133">Serialization</span></span>|<span data-ttu-id="a71d4-134">Nepovinný atribut.</span><span class="sxs-lookup"><span data-stu-id="a71d4-134">Optional attribute.</span></span> <span data-ttu-id="a71d4-135">Zásady pro serializaci XML, který používá ovládací prvky <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> třídy.</span><span class="sxs-lookup"><span data-stu-id="a71d4-135">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="a71d4-136">Zprostředkovatel komunikace s objekty</span><span class="sxs-lookup"><span data-stu-id="a71d4-136">Interop</span></span>|<span data-ttu-id="a71d4-137">Nepovinný atribut.</span><span class="sxs-lookup"><span data-stu-id="a71d4-137">Optional attribute.</span></span> <span data-ttu-id="a71d4-138">Ovládací prvky zásady pro zařazování odkazové typy prostředí Windows Runtime a COM.</span><span class="sxs-lookup"><span data-stu-id="a71d4-138">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="a71d4-139">Zprostředkovatel komunikace s objekty</span><span class="sxs-lookup"><span data-stu-id="a71d4-139">Interop</span></span>|<span data-ttu-id="a71d4-140">Nepovinný atribut.</span><span class="sxs-lookup"><span data-stu-id="a71d4-140">Optional attribute.</span></span> <span data-ttu-id="a71d4-141">Ovládací prvky zásady pro zařazování delegáta typy jako ukazatelů na funkce do nativního kódu.</span><span class="sxs-lookup"><span data-stu-id="a71d4-141">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="a71d4-142">Zprostředkovatel komunikace s objekty</span><span class="sxs-lookup"><span data-stu-id="a71d4-142">Interop</span></span>|<span data-ttu-id="a71d4-143">Nepovinný atribut.</span><span class="sxs-lookup"><span data-stu-id="a71d4-143">Optional attribute.</span></span> <span data-ttu-id="a71d4-144">Ovládací prvky zásady pro zařazování typů hodnot do nativního kódu.</span><span class="sxs-lookup"><span data-stu-id="a71d4-144">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="a71d4-145">Atribut Name.</span><span class="sxs-lookup"><span data-stu-id="a71d4-145">Name attribute</span></span>  
  
|<span data-ttu-id="a71d4-146">Hodnota</span><span class="sxs-lookup"><span data-stu-id="a71d4-146">Value</span></span>|<span data-ttu-id="a71d4-147">Popis</span><span class="sxs-lookup"><span data-stu-id="a71d4-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a71d4-148">*generic_parameter_name*</span><span class="sxs-lookup"><span data-stu-id="a71d4-148">*generic_parameter_name*</span></span>|<span data-ttu-id="a71d4-149">Požadovaný atribut.</span><span class="sxs-lookup"><span data-stu-id="a71d4-149">Required attribute.</span></span> <span data-ttu-id="a71d4-150">Název parametru obecného typu.</span><span class="sxs-lookup"><span data-stu-id="a71d4-150">The name of the generic type parameter.</span></span> <span data-ttu-id="a71d4-151">Například pro obecný delegát <xref:System.Func%603>, *generic_parameter_name* hodnotu "TResult" platí zásady modulu runtime pro delegáta návratovou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="a71d4-151">For example, for the generic delegate <xref:System.Func%603>, a *generic_parameter_name* value of "TResult" applies runtime policy to the delegate's return value.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="a71d4-152">Všechny ostatní atributy</span><span class="sxs-lookup"><span data-stu-id="a71d4-152">All other attributes</span></span>  
  
|<span data-ttu-id="a71d4-153">Hodnota</span><span class="sxs-lookup"><span data-stu-id="a71d4-153">Value</span></span>|<span data-ttu-id="a71d4-154">Popis</span><span class="sxs-lookup"><span data-stu-id="a71d4-154">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a71d4-155">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="a71d4-155">*policy_setting*</span></span>|<span data-ttu-id="a71d4-156">Nastavení, které chcete použít pro tento typ zásad.</span><span class="sxs-lookup"><span data-stu-id="a71d4-156">The setting to apply to this policy type.</span></span> <span data-ttu-id="a71d4-157">Možné hodnoty jsou `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, a `Required All`.</span><span class="sxs-lookup"><span data-stu-id="a71d4-157">Possible values are `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="a71d4-158">Další informace najdete v tématu [nastavení zásad direktivy modulu Runtime](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="a71d4-158">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a71d4-159">Podřízené elementy</span><span class="sxs-lookup"><span data-stu-id="a71d4-159">Child Elements</span></span>  
 <span data-ttu-id="a71d4-160">Žádné</span><span class="sxs-lookup"><span data-stu-id="a71d4-160">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a71d4-161">Nadřazené elementy</span><span class="sxs-lookup"><span data-stu-id="a71d4-161">Parent Elements</span></span>  
  
|<span data-ttu-id="a71d4-162">Prvek</span><span class="sxs-lookup"><span data-stu-id="a71d4-162">Element</span></span>|<span data-ttu-id="a71d4-163">Popis</span><span class="sxs-lookup"><span data-stu-id="a71d4-163">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a71d4-164">\<Metoda ></span><span class="sxs-lookup"><span data-stu-id="a71d4-164">\<Method></span></span>](../../../docs/framework/net-native/method-element-net-native.md)|<span data-ttu-id="a71d4-165">Platí zásady reflexe modulu runtime pro konstruktor nebo metoda.</span><span class="sxs-lookup"><span data-stu-id="a71d4-165">Applies runtime reflection policy to a constructor or method.</span></span>|  
|[<span data-ttu-id="a71d4-166">\<Typ ></span><span class="sxs-lookup"><span data-stu-id="a71d4-166">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="a71d4-167">Platí pro konkrétní typ, jako je například třídu nebo strukturu zásady reflexe modulu runtime.</span><span class="sxs-lookup"><span data-stu-id="a71d4-167">Applies runtime reflection policy to a particular type, such as a class or structure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a71d4-168">Poznámky</span><span class="sxs-lookup"><span data-stu-id="a71d4-168">Remarks</span></span>  
 <span data-ttu-id="a71d4-169">`<GenericParameter>` Prvek je podřízeným buď [ \<metoda >](../../../docs/framework/net-native/method-element-net-native.md) nebo [ \<typ >](../../../docs/framework/net-native/type-element-net-native.md) element a se používá k aplikování zásad na konkrétní obecného typu parametr, který je zadat jeho název v obecný typ nebo metoda podpis.</span><span class="sxs-lookup"><span data-stu-id="a71d4-169">The `<GenericParameter>` element is a child of either the [\<Method>](../../../docs/framework/net-native/method-element-net-native.md) or [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) element and is used to apply policy to a particular generic type parameter, which is specified by its name in the generic type or method signature.</span></span>  
  
 <span data-ttu-id="a71d4-170">`<GenericParameter>` Element je velmi užitečné při použití s serializátorů.</span><span class="sxs-lookup"><span data-stu-id="a71d4-170">The `<GenericParameter>` element is most useful when used with serializers.</span></span> <span data-ttu-id="a71d4-171">Následující příklad používá `<GenericParameter>` elementu, který chcete použít pro typ zásady `T` ve voláních serializátor NewtonSoft JSON [JsonConvert.DeserializeObject\<T > (String)](http://james.newtonking.com/json/help/index.html?topic=html/T_Newtonsoft_Json_JsonConvert.htm) přetížení metody.</span><span class="sxs-lookup"><span data-stu-id="a71d4-171">The following example uses the `<GenericParameter>` element to apply policy to the type `T` in calls to the NewtonSoft JSON serializer's [JsonConvert.DeserializeObject\<T>(String)](http://james.newtonking.com/json/help/index.html?topic=html/T_Newtonsoft_Json_JsonConvert.htm) method overloads.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Type Name="Newtonsoft.Json.JsonConvert" >  
      <Method Name="DeserializeObject{T}">  
         <GenericParameter Name="T" Serialize="Required All" />  
      </Method>  
   </Type>  
</Directives>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a71d4-172">Viz také</span><span class="sxs-lookup"><span data-stu-id="a71d4-172">See Also</span></span>  
 [<span data-ttu-id="a71d4-173">\<Metoda > elementu</span><span class="sxs-lookup"><span data-stu-id="a71d4-173">\<Method> Element</span></span>](../../../docs/framework/net-native/method-element-net-native.md)  
 [<span data-ttu-id="a71d4-174">\<Typ > elementu</span><span class="sxs-lookup"><span data-stu-id="a71d4-174">\<Type> Element</span></span>](../../../docs/framework/net-native/type-element-net-native.md)  
 [<span data-ttu-id="a71d4-175">Odkaz na soubor konfigurace modulu runtime direktivy (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="a71d4-175">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="a71d4-176">Nastavení zásad direktivy modulu runtime</span><span class="sxs-lookup"><span data-stu-id="a71d4-176">Runtime Directive Policy Settings</span></span>](../../../docs/framework/net-native/runtime-directive-policy-settings.md)  
 [<span data-ttu-id="a71d4-177">Elementy direktivy modulu runtime</span><span class="sxs-lookup"><span data-stu-id="a71d4-177">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
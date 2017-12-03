---
title: Element &lt;Field&gt; (.NET Native)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6a14125f-1a8d-41a1-8a32-659ca0ad12de
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9a3a928185146ac90ec4c3a905bf4f0e69e0e8d7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="ltfieldgt-element-net-native"></a><span data-ttu-id="4af7a-102">Element &lt;Field&gt; (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="4af7a-102">&lt;Field&gt; Element (.NET Native)</span></span>
<span data-ttu-id="4af7a-103">Platí zásady reflexe modulu runtime pro pole.</span><span class="sxs-lookup"><span data-stu-id="4af7a-103">Applies runtime reflection policy to a field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4af7a-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="4af7a-104">Syntax</span></span>  
  
```xml  
<Field Name="field_name"  
       Browse="policy_type"  
       Dynamic="policy_type"  
       Serialize="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4af7a-105">Atributy a elementy</span><span class="sxs-lookup"><span data-stu-id="4af7a-105">Attributes and Elements</span></span>  
 <span data-ttu-id="4af7a-106">Následující části popisují atributy, podřízené prvky a nadřazené prvky.</span><span class="sxs-lookup"><span data-stu-id="4af7a-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4af7a-107">Atributy</span><span class="sxs-lookup"><span data-stu-id="4af7a-107">Attributes</span></span>  
  
|<span data-ttu-id="4af7a-108">Atribut</span><span class="sxs-lookup"><span data-stu-id="4af7a-108">Attribute</span></span>|<span data-ttu-id="4af7a-109">Typ atributu</span><span class="sxs-lookup"><span data-stu-id="4af7a-109">Attribute type</span></span>|<span data-ttu-id="4af7a-110">Popis</span><span class="sxs-lookup"><span data-stu-id="4af7a-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="4af7a-111">Obecné</span><span class="sxs-lookup"><span data-stu-id="4af7a-111">General</span></span>|<span data-ttu-id="4af7a-112">Požadovaný atribut.</span><span class="sxs-lookup"><span data-stu-id="4af7a-112">Required attribute.</span></span> <span data-ttu-id="4af7a-113">Určuje název pole.</span><span class="sxs-lookup"><span data-stu-id="4af7a-113">Specifies the field name.</span></span>|  
|`Browse`|<span data-ttu-id="4af7a-114">Reflexe</span><span class="sxs-lookup"><span data-stu-id="4af7a-114">Reflection</span></span>|<span data-ttu-id="4af7a-115">Nepovinný atribut.</span><span class="sxs-lookup"><span data-stu-id="4af7a-115">Optional attribute.</span></span> <span data-ttu-id="4af7a-116">Ovládací prvky dotazování na informace o nebo vytváření výčtu pole, ale neumožňuje žádné dynamické přístup za běhu.</span><span class="sxs-lookup"><span data-stu-id="4af7a-116">Controls querying for information about or enumerating the field but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="4af7a-117">Reflexe</span><span class="sxs-lookup"><span data-stu-id="4af7a-117">Reflection</span></span>|<span data-ttu-id="4af7a-118">Nepovinný atribut.</span><span class="sxs-lookup"><span data-stu-id="4af7a-118">Optional attribute.</span></span> <span data-ttu-id="4af7a-119">Ovládací prvky runtime přístup do pole, které chcete povolit dynamické programování.</span><span class="sxs-lookup"><span data-stu-id="4af7a-119">Controls runtime access to the field to enable dynamic programming.</span></span> <span data-ttu-id="4af7a-120">Tato zásada zajistí, že pole můžete nastavit nebo načíst dynamicky za běhu.</span><span class="sxs-lookup"><span data-stu-id="4af7a-120">This policy ensures that a field can be set or retrieved dynamically at run time.</span></span>|  
|`Serialize`|<span data-ttu-id="4af7a-121">Serializace</span><span class="sxs-lookup"><span data-stu-id="4af7a-121">Serialization</span></span>|<span data-ttu-id="4af7a-122">Nepovinný atribut.</span><span class="sxs-lookup"><span data-stu-id="4af7a-122">Optional attribute.</span></span> <span data-ttu-id="4af7a-123">Určuje runtime přístup do pole, které chcete povolit instance typu bylo serializováno modulem knihovny například serializátor Newtonsoft JSON nebo má být použit pro datové vazby.</span><span class="sxs-lookup"><span data-stu-id="4af7a-123">Controls runtime access to a field to enable type instances to be serialized by libraries such as the Newtonsoft JSON serializer or to be used for data binding.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="4af7a-124">Atribut Name.</span><span class="sxs-lookup"><span data-stu-id="4af7a-124">Name attribute</span></span>  
  
|<span data-ttu-id="4af7a-125">Hodnota</span><span class="sxs-lookup"><span data-stu-id="4af7a-125">Value</span></span>|<span data-ttu-id="4af7a-126">Popis</span><span class="sxs-lookup"><span data-stu-id="4af7a-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4af7a-127">*method_name*</span><span class="sxs-lookup"><span data-stu-id="4af7a-127">*method_name*</span></span>|<span data-ttu-id="4af7a-128">Název pole.</span><span class="sxs-lookup"><span data-stu-id="4af7a-128">The field name.</span></span> <span data-ttu-id="4af7a-129">Typ pole je definován nadřazený [ \<typ >](../../../docs/framework/net-native/type-element-net-native.md) nebo [ \<TypeInstantiation >](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) element.</span><span class="sxs-lookup"><span data-stu-id="4af7a-129">The type of the field is defined by the parent [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) or [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="4af7a-130">Všechny ostatní atributy</span><span class="sxs-lookup"><span data-stu-id="4af7a-130">All other attributes</span></span>  
  
|<span data-ttu-id="4af7a-131">Hodnota</span><span class="sxs-lookup"><span data-stu-id="4af7a-131">Value</span></span>|<span data-ttu-id="4af7a-132">Popis</span><span class="sxs-lookup"><span data-stu-id="4af7a-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4af7a-133">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="4af7a-133">*policy_setting*</span></span>|<span data-ttu-id="4af7a-134">Nastavení, které chcete použít pro tento typ zásad pro pole.</span><span class="sxs-lookup"><span data-stu-id="4af7a-134">The setting to apply to this policy type for the field.</span></span> <span data-ttu-id="4af7a-135">Možné hodnoty jsou `Auto`, `Excluded`, `Included`, a `Required`.</span><span class="sxs-lookup"><span data-stu-id="4af7a-135">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="4af7a-136">Další informace najdete v tématu [nastavení zásad direktivy modulu Runtime](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="4af7a-136">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4af7a-137">Podřízené elementy</span><span class="sxs-lookup"><span data-stu-id="4af7a-137">Child Elements</span></span>  
 <span data-ttu-id="4af7a-138">Žádné</span><span class="sxs-lookup"><span data-stu-id="4af7a-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4af7a-139">Nadřazené elementy</span><span class="sxs-lookup"><span data-stu-id="4af7a-139">Parent Elements</span></span>  
  
|<span data-ttu-id="4af7a-140">Prvek</span><span class="sxs-lookup"><span data-stu-id="4af7a-140">Element</span></span>|<span data-ttu-id="4af7a-141">Popis</span><span class="sxs-lookup"><span data-stu-id="4af7a-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4af7a-142">\<Typ ></span><span class="sxs-lookup"><span data-stu-id="4af7a-142">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="4af7a-143">Reflexe zásada se vztahuje na typ a všechny její členy.</span><span class="sxs-lookup"><span data-stu-id="4af7a-143">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="4af7a-144">\<TypeInstantiation ></span><span class="sxs-lookup"><span data-stu-id="4af7a-144">\<TypeInstantiation></span></span>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|<span data-ttu-id="4af7a-145">Reflexe zásada se vztahuje na sestavené obecné typy a všechny její členy.</span><span class="sxs-lookup"><span data-stu-id="4af7a-145">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4af7a-146">Poznámky</span><span class="sxs-lookup"><span data-stu-id="4af7a-146">Remarks</span></span>  
 <span data-ttu-id="4af7a-147">Pokud pole zásady nejsou výslovně definované, dědí zásady modulu runtime objektů svého nadřízeného elementu.</span><span class="sxs-lookup"><span data-stu-id="4af7a-147">If a field's policy is not explicitly defined, it inherits the runtime policy of its parent element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4af7a-148">Viz také</span><span class="sxs-lookup"><span data-stu-id="4af7a-148">See Also</span></span>  
 [<span data-ttu-id="4af7a-149">Elementy direktivy modulu runtime</span><span class="sxs-lookup"><span data-stu-id="4af7a-149">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)  
 [<span data-ttu-id="4af7a-150">Odkaz na soubor konfigurace modulu runtime direktivy (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="4af7a-150">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="4af7a-151">Nastavení zásad direktivy modulu runtime</span><span class="sxs-lookup"><span data-stu-id="4af7a-151">Runtime Directive Policy Settings</span></span>](../../../docs/framework/net-native/runtime-directive-policy-settings.md)
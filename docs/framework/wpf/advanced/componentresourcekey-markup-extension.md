---
title: "ComponentResourceKey – rozšíření značek"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ComponentResourceKey
- ComponentResourceKeyExtension
helpviewer_keywords:
- ComponentResourceKey markup extension [WPF]
- XAML [WPF], ComponentResourceKey markup extension
ms.assetid: d6bcdbe6-61b3-40a7-b381-4e02185b5a85
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b7f959318c5991fea2df92ff8000e85345fb35ed
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="componentresourcekey-markup-extension"></a><span data-ttu-id="c2d3a-102">ComponentResourceKey – rozšíření značek</span><span class="sxs-lookup"><span data-stu-id="c2d3a-102">ComponentResourceKey Markup Extension</span></span>
<span data-ttu-id="c2d3a-103">Definuje a klíče pro prostředky, které jsou načteny z externí sestavení odkazuje.</span><span class="sxs-lookup"><span data-stu-id="c2d3a-103">Defines and references keys for resources that are loaded from external assemblies.</span></span> <span data-ttu-id="c2d3a-104">To umožňuje vyhledávání prostředků zadat typ cíle v sestavení, nikoli slovníku explicitní prostředků v sestavení nebo na třídu.</span><span class="sxs-lookup"><span data-stu-id="c2d3a-104">This enables a resource lookup to specify a target type in an assembly, rather than an explicit resource dictionary in an assembly or on a class.</span></span>  
  
## <a name="xaml-attribute-usage-setting-key-compact"></a><span data-ttu-id="c2d3a-105">Použití atributu XAML (nastavení klíč, compact)</span><span class="sxs-lookup"><span data-stu-id="c2d3a-105">XAML Attribute Usage (setting key, compact)</span></span>  
  
```xml  
<object x:Key="{ComponentResourceKey {x:Type targetTypeName}, targetID}" .../>  
```  
  
## <a name="xaml-attribute-usage-setting-key-verbose"></a><span data-ttu-id="c2d3a-106">Použití atributu XAML (nastavení klíč, verbose)</span><span class="sxs-lookup"><span data-stu-id="c2d3a-106">XAML Attribute Usage (setting key, verbose)</span></span>  
  
```xml  
<object x:Key="{ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}" .../>  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-compact"></a><span data-ttu-id="c2d3a-107">Použití atributu XAML (žádajícího prostředků, compact)</span><span class="sxs-lookup"><span data-stu-id="c2d3a-107">XAML Attribute Usage (requesting resource, compact)</span></span>  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey {x:Type targetTypeName}, targetID}}" .../>  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-verbose"></a><span data-ttu-id="c2d3a-108">Použití atributu XAML (žádajícího prostředků, verbose)</span><span class="sxs-lookup"><span data-stu-id="c2d3a-108">XAML Attribute Usage (requesting resource, verbose)</span></span>  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}}" .../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="c2d3a-109">Hodnoty XAML</span><span class="sxs-lookup"><span data-stu-id="c2d3a-109">XAML Values</span></span>  
  
|||  
|-|-|  
|`targetTypeName`|<span data-ttu-id="c2d3a-110">Název veřejnosti [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] typu, která je definována v sestavení prostředků.</span><span class="sxs-lookup"><span data-stu-id="c2d3a-110">The name of the public [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] type that is defined in the resource assembly.</span></span>|  
|`targetID`|<span data-ttu-id="c2d3a-111">Klíč pro prostředek.</span><span class="sxs-lookup"><span data-stu-id="c2d3a-111">The key for the resource.</span></span> <span data-ttu-id="c2d3a-112">Když jsou vyhledávat prostředky, `targetID` se podobá [x: Key – direktiva](../../../../docs/framework/xaml-services/x-key-directive.md) prostředku.</span><span class="sxs-lookup"><span data-stu-id="c2d3a-112">When resources are looked up, `targetID` will be analogous to the [x:Key Directive](../../../../docs/framework/xaml-services/x-key-directive.md) of the resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2d3a-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="c2d3a-113">Remarks</span></span>  
 <span data-ttu-id="c2d3a-114">Jak je vidět v použití výše uvedeného {`ComponentResourceKey`} využití rozšíření značek nachází na dvou místech:</span><span class="sxs-lookup"><span data-stu-id="c2d3a-114">As seen in the usages above, a {`ComponentResourceKey`} markup extension usage is found in two places:</span></span>  
  
-   <span data-ttu-id="c2d3a-115">Definice klíč v rámci slovník prostředků motiv, jaké poskytovala autorem ovládací prvek.</span><span class="sxs-lookup"><span data-stu-id="c2d3a-115">The definition of a key within a theme resource dictionary, as provided by a control author.</span></span>  
  
-   <span data-ttu-id="c2d3a-116">Přístup k prostředku motiv ze sestavení, když jsou retemplating ovládací prvek ale chcete použít hodnoty vlastností, které pocházejí z prostředků poskytovaných motivy ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="c2d3a-116">Accessing a theme resource from the assembly, when you are retemplating the control but want to use property values that come from resources provided by the control's themes.</span></span>  
  
 <span data-ttu-id="c2d3a-117">Pro odkazování na komponenty zdroje, které pocházejí z motivy, obvykle doporučujeme používat `{DynamicResource}` místo `{StaticResource}`.</span><span class="sxs-lookup"><span data-stu-id="c2d3a-117">For referencing component resources that come from themes, it is generally recommended that you use `{DynamicResource}` rather than `{StaticResource}`.</span></span> <span data-ttu-id="c2d3a-118">Můžete se podívat na využití.</span><span class="sxs-lookup"><span data-stu-id="c2d3a-118">This is shown in the usages.</span></span> <span data-ttu-id="c2d3a-119">`{DynamicResource}`doporučuje se, protože uživatel může změnit motiv sám sebe.</span><span class="sxs-lookup"><span data-stu-id="c2d3a-119">`{DynamicResource}` is recommended because the theme itself can be changed by the user.</span></span> <span data-ttu-id="c2d3a-120">Pokud chcete součást prostředků, která nejvíce odpovídá implementované záměr autora ovládacího prvku pro podporu motiv, měli byste povolit odkaz prostředků vaší součásti také být dynamické.</span><span class="sxs-lookup"><span data-stu-id="c2d3a-120">If you want the component resource that most closely matches the control author's intent for supporting a theme, you should enable your component resource reference to be dynamic also.</span></span>  
  
 <span data-ttu-id="c2d3a-121"><xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> Určuje typ, který existuje v cílové sestavení, kde je ve skutečnosti definován prostředek.</span><span class="sxs-lookup"><span data-stu-id="c2d3a-121">The <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> identifies a type that exists in the target assembly where the resource is actually defined.</span></span> <span data-ttu-id="c2d3a-122">A `ComponentResourceKey` můžete definovaný a použít nezávisle na přesně vědět, kde <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> je definován, ale server se musí přeložit typ prostřednictvím odkazované sestavení.</span><span class="sxs-lookup"><span data-stu-id="c2d3a-122">A `ComponentResourceKey` can be defined and used independently of knowing exactly where the <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> is defined, but eventually must resolve the type through referenced assemblies.</span></span>  
  
 <span data-ttu-id="c2d3a-123">Použití běžných pro <xref:System.Windows.ComponentResourceKey> je definovat klíče, které jsou pak zveřejněné jako členové třídy.</span><span class="sxs-lookup"><span data-stu-id="c2d3a-123">A common usage for <xref:System.Windows.ComponentResourceKey> is to define keys that are then exposed as members of a class.</span></span> <span data-ttu-id="c2d3a-124">Pro toto použití, můžete použít <xref:System.Windows.ComponentResourceKey> konstruktoru třídy, ne rozšíření značek.</span><span class="sxs-lookup"><span data-stu-id="c2d3a-124">For this usage, you use the <xref:System.Windows.ComponentResourceKey> class constructor, not the markup extension.</span></span> <span data-ttu-id="c2d3a-125">Další informace najdete v tématu <xref:System.Windows.ComponentResourceKey>, nebo "definování a odkazování na klíče pro motiv části zdroje tématu" [vytváření – Přehled ovládacího prvku](../../../../docs/framework/wpf/controls/control-authoring-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c2d3a-125">For more information, see <xref:System.Windows.ComponentResourceKey>, or the "Defining and Referencing Keys for Theme Resources" section of the topic [Control Authoring Overview](../../../../docs/framework/wpf/controls/control-authoring-overview.md).</span></span>  
  
 <span data-ttu-id="c2d3a-126">Pro vytvoření klíče i odkazy na s klíči prostředky, se běžně používá pro atribut syntaxe `ComponentResourceKey` – rozšíření značek.</span><span class="sxs-lookup"><span data-stu-id="c2d3a-126">For both establishing keys and referencing keyed resources, attribute syntax is commonly used for the `ComponentResourceKey` markup extension.</span></span>  
  
 <span data-ttu-id="c2d3a-127">Využívá compact syntaxi uvedenou <xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=nameWithType> konstruktor podpisu a poziční parametr využití rozšíření značek.</span><span class="sxs-lookup"><span data-stu-id="c2d3a-127">The compact syntax shown relies on the <xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=nameWithType> constructor signature and positional parameter usage of a markup extension.</span></span> <span data-ttu-id="c2d3a-128">V jakém pořadí `targetTypeName` a `targetID` mají je důležité.</span><span class="sxs-lookup"><span data-stu-id="c2d3a-128">The order in which the `targetTypeName` and `targetID` are given is important.</span></span> <span data-ttu-id="c2d3a-129">Podrobná syntaxe spoléhá na <xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=nameWithType> výchozí konstruktor a poté nastaví <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> a <xref:System.Windows.ComponentResourceKey.ResourceId%2A> způsobem, který je obdobou syntaxe true atributu v objektu elementu.</span><span class="sxs-lookup"><span data-stu-id="c2d3a-129">The verbose syntax relies on the <xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=nameWithType> default constructor, and then sets the <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> and <xref:System.Windows.ComponentResourceKey.ResourceId%2A> in a way that is analogous to a true attribute syntax on an object element.</span></span> <span data-ttu-id="c2d3a-130">V podrobná syntaxe není důležité pořadí, ve kterém jsou nastaveny vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="c2d3a-130">In the verbose syntax, the order in which the properties are set is not important.</span></span> <span data-ttu-id="c2d3a-131">Relace a mechanismy tyto dvě možnosti (compact a podrobné) je podrobně popsaná v další v tématu [rozšíření značek a WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="c2d3a-131">The relationship and mechanisms of these two alternatives (compact and verbose) is described in more detail in the topic [Markup Extensions and WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).</span></span>  
  
 <span data-ttu-id="c2d3a-132">Technicky hodnota `targetID` může být jakýkoli objekt, nemusí být řetězec.</span><span class="sxs-lookup"><span data-stu-id="c2d3a-132">Technically, the value for `targetID` can be any object, it does not have to be a string.</span></span> <span data-ttu-id="c2d3a-133">Nejběžnější využití v grafickém subsystému WPF je ale, chcete-li zarovnat `targetID` hodnotu s formuláři řetězce, které jsou a kde jsou platné v takové řetězce [XamlName – gramatika](../../../../docs/framework/xaml-services/xamlname-grammar.md).</span><span class="sxs-lookup"><span data-stu-id="c2d3a-133">However, the most common usage in WPF is to align the `targetID` value with forms that are strings, and where such strings are valid in the [XamlName Grammar](../../../../docs/framework/xaml-services/xamlname-grammar.md).</span></span>  
  
 <span data-ttu-id="c2d3a-134">`ComponentResourceKey`lze použít v syntaxi objekt elementu.</span><span class="sxs-lookup"><span data-stu-id="c2d3a-134">`ComponentResourceKey` can be used in object element syntax.</span></span> <span data-ttu-id="c2d3a-135">V takovém případě zadáte hodnotu i <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> a <xref:System.Windows.ComponentResourceKey.ResourceId%2A> vlastnosti je potřeba správně inicializovat rozšíření.</span><span class="sxs-lookup"><span data-stu-id="c2d3a-135">In this case, specifying the value of both the <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> and <xref:System.Windows.ComponentResourceKey.ResourceId%2A> properties is required to properly initialize the extension.</span></span>  
  
 <span data-ttu-id="c2d3a-136">V [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] čtečky implementace je definována zpracování pro toto rozšíření značek <xref:System.Windows.ComponentResourceKey> třídy.</span><span class="sxs-lookup"><span data-stu-id="c2d3a-136">In the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] reader implementation, the handling for this markup extension is defined by the <xref:System.Windows.ComponentResourceKey> class.</span></span>  
  
 <span data-ttu-id="c2d3a-137">`ComponentResourceKey`je rozšíření značek.</span><span class="sxs-lookup"><span data-stu-id="c2d3a-137">`ComponentResourceKey` is a markup extension.</span></span> <span data-ttu-id="c2d3a-138">Rozšíření značek jsou obvykle implementována v případě požadavku, aby díky použití řídicí sekvence mohly být hodnoty atributů něčím jiným než literálními hodnotami nebo názvy obslužných rutin, a tento požadavek má tak rozsáhlou platnost, že nestačí jednoduše použít převaděče typů pro určité typy nebo vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="c2d3a-138">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="c2d3a-139">Všechna rozšíření značek v [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] použít {a} znaků v jejich syntaxi atributů, což je konvence, podle kterého [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesor rozpozná, že rozšíření značek musí zpracovat atribut.</span><span class="sxs-lookup"><span data-stu-id="c2d3a-139">All markup extensions in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] use the { and } characters in their attribute syntax, which is the convention by which a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="c2d3a-140">Další informace najdete v tématu [rozšíření značek a WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="c2d3a-140">For more information, see [Markup Extensions and WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2d3a-141">Viz také</span><span class="sxs-lookup"><span data-stu-id="c2d3a-141">See Also</span></span>  
 <xref:System.Windows.ComponentResourceKey>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="c2d3a-142">Vytváření – Přehled ovládacího prvku</span><span class="sxs-lookup"><span data-stu-id="c2d3a-142">Control Authoring Overview</span></span>](../../../../docs/framework/wpf/controls/control-authoring-overview.md)  
 [<span data-ttu-id="c2d3a-143">Přehled XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="c2d3a-143">XAML Overview (WPF)</span></span>](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [<span data-ttu-id="c2d3a-144">Rozšíření značek a WPF XAML</span><span class="sxs-lookup"><span data-stu-id="c2d3a-144">Markup Extensions and WPF XAML</span></span>](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
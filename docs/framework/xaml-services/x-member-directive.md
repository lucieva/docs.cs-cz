---
title: "x:Member – direktiva"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4d8394ef-644c-4331-b6c5-be855d392980
caps.latest.revision: "5"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: eafb222dd5d3afcc751bae7799f0d17279aed14f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="xmember-directive"></a><span data-ttu-id="c54da-102">x:Member – direktiva</span><span class="sxs-lookup"><span data-stu-id="c54da-102">x:Member Directive</span></span>
<span data-ttu-id="c54da-103">Deklaruje člena XAML v kódu.</span><span class="sxs-lookup"><span data-stu-id="c54da-103">Declares a XAML member in markup.</span></span>  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="c54da-104">Použití elementu objektu XAML</span><span class="sxs-lookup"><span data-stu-id="c54da-104">XAML Object Element Usage</span></span>  
  
```  
<object x:Class="className">  
  <x:Members>  
    <x:Member Name="propertyName"/>  
    additionalMembers  
  </x:Members>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="c54da-105">Hodnoty XAML</span><span class="sxs-lookup"><span data-stu-id="c54da-105">XAML Values</span></span>  
  
|||  
|-|-|  
|`className`|<span data-ttu-id="c54da-106">Název základní třídy nebo částečné třídy pro produkční XAML.</span><span class="sxs-lookup"><span data-stu-id="c54da-106">Name of the backing class or partial class for the XAML production.</span></span>|  
|`memberName`|<span data-ttu-id="c54da-107">Název člena vlastnosti definovaný.</span><span class="sxs-lookup"><span data-stu-id="c54da-107">Member name of the property being defined.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c54da-108">Poznámky</span><span class="sxs-lookup"><span data-stu-id="c54da-108">Remarks</span></span>  
 <span data-ttu-id="c54da-109">V implementaci rozhraní .NET Framework XAML Services.</span><span class="sxs-lookup"><span data-stu-id="c54da-109">In the .NET Framework XAML Services implementation, .</span></span> <span data-ttu-id="c54da-110">`x:Member`nemá přímé typ zálohování, ale podporuje <xref:System.Windows.Markup.MemberDefinition> třídy.</span><span class="sxs-lookup"><span data-stu-id="c54da-110">`x:Member` does not have a direct type backing, but is supported by the <xref:System.Windows.Markup.MemberDefinition> class.</span></span> <span data-ttu-id="c54da-111">V datový proud uzlu XAML `x:Member` element je reprezentován jako člen s názvem `Member`, z oboru názvů jazyka XAML jazyka XAML.</span><span class="sxs-lookup"><span data-stu-id="c54da-111">In a XAML node stream, an `x:Member` element is represented as a member named `Member`, from the XAML language XAML namespace.</span></span> <span data-ttu-id="c54da-112">Člen `Member` obsahuje atributů deklarovaná značek.</span><span class="sxs-lookup"><span data-stu-id="c54da-112">The member `Member` holds attributes as declared by markup.</span></span>  
  
 <span data-ttu-id="c54da-113">Význam `Name` a `Type` nejsou přiřazeny na úrovni rozhraní .NET Framework XAML Services.</span><span class="sxs-lookup"><span data-stu-id="c54da-113">The meaning of `Name` and `Type` are not assigned at the .NET Framework XAML Services level.</span></span> <span data-ttu-id="c54da-114">Jsou uložené v počáteční datový proud uzlu XAML jako řetězcové hodnoty budou interpretovat později v části pravidla, která může být způsobené konkrétní rozhraní.</span><span class="sxs-lookup"><span data-stu-id="c54da-114">They are stored in the initial XAML node stream as string values, to be interpreted later under the rules that might be imposed by specific frameworks.</span></span> <span data-ttu-id="c54da-115">Význam může zarovnat na XAML název a typ jazyka XAML, což znamená, nebo může být pouze platné ve základní typ systému, v závislosti na implementaci.</span><span class="sxs-lookup"><span data-stu-id="c54da-115">The meaning might align to a XAML name and XAML type meaning, or might only be valid in a backing type system, depending on the implementation.</span></span>  
  
 <span data-ttu-id="c54da-116">Pro podporu praktické využití `x:Members` jako prostředek k zadávání definice člen v kódu, musí být přidružen třídu, která je možné upravit členy.</span><span class="sxs-lookup"><span data-stu-id="c54da-116">To support a practical usage of `x:Members` as a means to specify member definitions in markup, the members must be associated with a class that can be modified.</span></span> <span data-ttu-id="c54da-117">Je určený model, který `x:Members` existuje jako člena typu, který určuje `x:Class`.</span><span class="sxs-lookup"><span data-stu-id="c54da-117">The intended model is that `x:Members` exists as a member of a type that specifies an `x:Class`.</span></span> <span data-ttu-id="c54da-118">Tento mechanismus pro přidružení typy a členy nebo pro vytvoření definice dynamického člena však není podporován na úrovni rozhraní .NET Framework XAML Services.</span><span class="sxs-lookup"><span data-stu-id="c54da-118">However, the mechanism for associating types and members or for producing dynamic member definitions is not supported at the .NET Framework XAML Services level.</span></span> <span data-ttu-id="c54da-119">To je zleva jednotlivé rozhraní, které mají modelů aplikace, které podporují definice člena z XAML.</span><span class="sxs-lookup"><span data-stu-id="c54da-119">This is left to individual frameworks that have application models that support member definitions from XAML.</span></span> <span data-ttu-id="c54da-120">Obvykle MSBUILD sestavení akce, které kompilace kódu XAML a buď ji integrovat s nástrojem kódu nebo produktu čistě z XAML sestavení jsou potřeba k podpoře této funkce.</span><span class="sxs-lookup"><span data-stu-id="c54da-120">Typically, MSBUILD build actions that markup-compile the XAML and either integrate it with code-behind or produce pure from-XAML assemblies are needed to support that feature.</span></span>  
  
## <a name="xproperty-for-windows-workflow-foundation"></a><span data-ttu-id="c54da-121">x: Property pro Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="c54da-121">x:Property for Windows Workflow Foundation</span></span>  
 <span data-ttu-id="c54da-122">Pro Windows Workflow Foundation `x:Property` definuje členy vlastní aktivita tvoří zcela v jazyce XAML, nebo XAML – definované dynamické členy pro Návrhář aktivity s kódem v pozadí.</span><span class="sxs-lookup"><span data-stu-id="c54da-122">For Windows Workflow Foundation, `x:Property` defines the members of a custom activity composed entirely in XAML, or XAML –defined dynamic members for an activity designer with code-behind.</span></span> <span data-ttu-id="c54da-123">`x:Class`musí být zadaná také v kořenovém elementu provozních XAML.</span><span class="sxs-lookup"><span data-stu-id="c54da-123">`x:Class` must also be specified on the root element of the XAML production.</span></span> <span data-ttu-id="c54da-124">To není požadavek na úrovni rozhraní .NET Framework XAML Services, ale při načtení provozní XAML akcemi MSBUILD sestavení, které podporují vlastní aktivity a Windows Workflow Foundation XAML obecně se změní na požadavek.</span><span class="sxs-lookup"><span data-stu-id="c54da-124">This is not a requirement at the .NET Framework XAML Services level, but becomes a requirement when the XAML production is loaded by the MSBUILD build actions that support custom activities and Windows Workflow Foundation XAML in general.</span></span> <span data-ttu-id="c54da-125">Windows Workflow Foundation nepoužívá jako jeho určená hodnota pro název typu čistý XAML `x:Property` `Type` atribut a místo toho používá názvů, který není dokumentováno sem.</span><span class="sxs-lookup"><span data-stu-id="c54da-125">Windows Workflow Foundation does not use the pure XAML type name as its intended value for the `x:Property` `Type` attribute, and instead uses a convention that is not documented here.</span></span> <span data-ttu-id="c54da-126">Další informace najdete v tématu [dynamické vytvoření aktivity](http://msdn.microsoft.com/library/dd807392.aspx).</span><span class="sxs-lookup"><span data-stu-id="c54da-126">For more information, see [Dynamic Activity Creation](http://msdn.microsoft.com/library/dd807392.aspx).</span></span>
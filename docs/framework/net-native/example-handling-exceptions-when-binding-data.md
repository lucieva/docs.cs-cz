---
title: "Příklad: Zpracování výjimek, pokud vazba dat"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bd63ed96-9853-46dc-ade5-7bd1b0f39110
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 18f2d06d3a6974b913af663a38a6155b38422232
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="example-handling-exceptions-when-binding-data"></a><span data-ttu-id="3e3c2-102">Příklad: Zpracování výjimek, pokud vazba dat</span><span class="sxs-lookup"><span data-stu-id="3e3c2-102">Example: Handling Exceptions When Binding Data</span></span>
> [!NOTE]
>  <span data-ttu-id="3e3c2-103">Toto téma se týká .NET nativní Developer Preview, což je předběžná verze softwaru.</span><span class="sxs-lookup"><span data-stu-id="3e3c2-103">This topic refers to the .NET Native Developer Preview, which is pre-release software.</span></span> <span data-ttu-id="3e3c2-104">Preview z si můžete stáhnout [webu Microsoft Connect](http://go.microsoft.com/fwlink/?LinkId=394611) (vyžaduje registraci).</span><span class="sxs-lookup"><span data-stu-id="3e3c2-104">You can download the preview from the [Microsoft Connect website](http://go.microsoft.com/fwlink/?LinkId=394611) (requires registration).</span></span>  
  
 <span data-ttu-id="3e3c2-105">Následující příklad ukazuje, jak vyřešit [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) výjimka, která se vyvolá, když aplikace, kompilovat s [!INCLUDE[net_native](../../../includes/net-native-md.md)] řetězu nástroj pokusí vázat data.</span><span class="sxs-lookup"><span data-stu-id="3e3c2-105">The following example shows how to resolve a [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) exception that is thrown when an app compiled with the [!INCLUDE[net_native](../../../includes/net-native-md.md)] tool chain tries to bind data.</span></span> <span data-ttu-id="3e3c2-106">Tady je informace o výjimce:</span><span class="sxs-lookup"><span data-stu-id="3e3c2-106">Here’s the exception information:</span></span>  
  
```  
This operation cannot be carried out as metadata for the following type was removed for performance reasons:   
App.ViewModels.MainPageVM  
```  
  
 <span data-ttu-id="3e3c2-107">Tady je zásobníku přidružené volání:</span><span class="sxs-lookup"><span data-stu-id="3e3c2-107">Here's the associated call stack:</span></span>  
  
```  
Reflection::Execution::ReflectionDomainSetupImplementation.CreateNonInvokabilityException+0x238  
Reflection::Core::ReflectionDomain.CreateNonInvokabilityException+0x2e  
Reflection::Core::Execution::ExecutionEnvironment.+0x316  
System::Reflection::Runtime::PropertyInfos::RuntimePropertyInfo.GetValue+0x1cb  
System::Reflection::PropertyInfo.GetValue+0x22  
System::Runtime::InteropServices::WindowsRuntime::CustomPropertyImpl.GetValue+0x42  
App!$66_Interop::McgNative.Func_IInspectable_IInspectable+0x158  
App!$66_Interop::McgNative::__vtable_Windows_UI_Xaml_Data__ICustomProperty.GetValue__STUB+0x46  
Windows_UI_Xaml!DirectUI::PropertyProviderPropertyAccess::GetValue+0x3f   
Windows_UI_Xaml!DirectUI::PropertyAccessPathStep::GetValue+0x31   
Windows_UI_Xaml!DirectUI::PropertyPathListener::ConnectPathStep+0x113  
```  
  
## <a name="what-was-the-app-doing"></a><span data-ttu-id="3e3c2-108">Co dělal aplikace?</span><span class="sxs-lookup"><span data-stu-id="3e3c2-108">What was the app doing?</span></span>  
 <span data-ttu-id="3e3c2-109">Na bázi zásobníku, rámců z [Windows.UI.Xaml](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.aspx) obor názvů znamenat, že byla spuštěna modul vykreslování XAML.</span><span class="sxs-lookup"><span data-stu-id="3e3c2-109">At the base of the stack, frames from the [Windows.UI.Xaml](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.aspx) namespace indicate that the XAML rendering engine was running.</span></span>   <span data-ttu-id="3e3c2-110">Použití <xref:System.Reflection.PropertyInfo.GetValue%2A?displayProperty=nameWithType> metoda označuje vyhledávání na základě reflexe hodnoty vlastnosti na typ, jejichž metadata byla odebrána.</span><span class="sxs-lookup"><span data-stu-id="3e3c2-110">The use of the <xref:System.Reflection.PropertyInfo.GetValue%2A?displayProperty=nameWithType> method indicates a reflection-based lookup of a property’s value on the type whose metadata was removed.</span></span>  
  
 <span data-ttu-id="3e3c2-111">Prvním krokem při poskytování direktivu metadata by přidat `serialize` metadata pro typ tak, aby jeho vlastnosti jsou všechny dostupné:</span><span class="sxs-lookup"><span data-stu-id="3e3c2-111">The first step in providing a metadata directive would be to add `serialize` metadata for the type so that its properties are all accessible:</span></span>  
  
```xml  
<Type Name="App.ViewModels.MainPageVM" Serialize="Required Public" />  
```  
  
## <a name="is-this-an-isolated-case"></a><span data-ttu-id="3e3c2-112">Je to izolované případ?</span><span class="sxs-lookup"><span data-stu-id="3e3c2-112">Is this an isolated case?</span></span>  
 <span data-ttu-id="3e3c2-113">V tomto scénáři, pokud má datová vazba neúplné metadata pro jednu `ViewModel`, může se příliš ostatní uživatelé.</span><span class="sxs-lookup"><span data-stu-id="3e3c2-113">In this scenario, if data binding has incomplete metadata for one `ViewModel`, it may for others, too.</span></span>  <span data-ttu-id="3e3c2-114">Pokud jsou strukturovaná kód tak, aby aplikace zobrazit modely jsou v `App.ViewModels` obor názvů, můžete použít obecnější direktivy modulu runtime:</span><span class="sxs-lookup"><span data-stu-id="3e3c2-114">If the code is structured in a way that the app’s view models are all in the `App.ViewModels` namespace, you could use a more general runtime directive:</span></span>  
  
```xml  
<Namespace Name="App.ViewModels " Serialize="Required Public" />  
```  
  
## <a name="could-the-code-be-rewritten-to-not-use-reflection"></a><span data-ttu-id="3e3c2-115">By mohla být přepsána kód nechcete použít reflexe?</span><span class="sxs-lookup"><span data-stu-id="3e3c2-115">Could the code be rewritten to not use reflection?</span></span>  
 <span data-ttu-id="3e3c2-116">Datová vazba je velmi náročná na výkon reflexe, a proto Změna kódu, aby se zabránilo reflexe není vhodná.</span><span class="sxs-lookup"><span data-stu-id="3e3c2-116">Because data binding is reflection-intensive, changing the code to avoid reflection isn’t feasible.</span></span>  
  
 <span data-ttu-id="3e3c2-117">Existují však způsobů určení `ViewModel` na stránku XAML tak, aby nástroj řetězu můžete přidružit vlastnost vazby pomocí správného typu v doba kompilace a zachovat metadata bez použití direktivy modulu runtime.</span><span class="sxs-lookup"><span data-stu-id="3e3c2-117">However, there are ways to specify the `ViewModel` to the XAML page so that the tool chain can associate property bindings with the correct type at compile time and keep the metadata without using a runtime directive.</span></span>  <span data-ttu-id="3e3c2-118">Například je možné aplikovat [Windows.UI.Xaml.Data.BindableAttribute](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.data.bindableattribute.aspx) atribut na vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="3e3c2-118">For example, you could apply the [Windows.UI.Xaml.Data.BindableAttribute](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.data.bindableattribute.aspx) attribute on properties.</span></span> <span data-ttu-id="3e3c2-119">To způsobí, že kompilátor jazyka XAML generovat informace o požadované vyhledávání a zabraňuje nutnosti direktivy modulu runtime v souboru Default.rd.xml.</span><span class="sxs-lookup"><span data-stu-id="3e3c2-119">This causes the XAML compiler to generate the required lookup information and avoids requiring a runtime directive in the Default.rd.xml file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e3c2-120">Viz také</span><span class="sxs-lookup"><span data-stu-id="3e3c2-120">See Also</span></span>  
 [<span data-ttu-id="3e3c2-121">Začínáme</span><span class="sxs-lookup"><span data-stu-id="3e3c2-121">Getting Started</span></span>](../../../docs/framework/net-native/getting-started-with-net-native.md)  
 [<span data-ttu-id="3e3c2-122">Příklad: Řešení potíží s dynamické programování</span><span class="sxs-lookup"><span data-stu-id="3e3c2-122">Example: Troubleshooting Dynamic Programming</span></span>](../../../docs/framework/net-native/example-troubleshooting-dynamic-programming.md)
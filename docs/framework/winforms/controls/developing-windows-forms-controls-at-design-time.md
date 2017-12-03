---
title: "Vývoj ovládacích prvků Windows Forms v době návrhu"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms controls [Windows Forms]
- Windows Forms controls, creating
- controls [Windows Forms]
- controls [Windows Forms], creating
- user controls [Windows Forms]
- custom controls [Windows Forms]
ms.assetid: e5a8e088-7ec8-4fd9-bcb3-9078fd134829
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a4f9680bb64339f2f232793beb9c47a36c07aa4a
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/22/2017
---
# <a name="developing-windows-forms-controls-at-design-time"></a><span data-ttu-id="6d650-102">Vývoj ovládacích prvků Windows Forms v době návrhu</span><span class="sxs-lookup"><span data-stu-id="6d650-102">Developing Windows Forms Controls at Design Time</span></span>
<span data-ttu-id="6d650-103">Pro ovládací prvek autory rozhraní .NET Framework poskytuje širokou řadu vytváření technologie ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="6d650-103">For control authors, the .NET Framework provides a wealth of control authoring technology.</span></span> <span data-ttu-id="6d650-104">Autoři je už omezený na navrhování složené ovládací prvky, které fungují jako kolekce dříve existující ovládacích prvků.</span><span class="sxs-lookup"><span data-stu-id="6d650-104">Authors are no longer limited to designing composite controls that act as a collection of preexisting controls.</span></span> <span data-ttu-id="6d650-105">Prostřednictvím dědičnosti můžete vytvořit své vlastní ovládací prvky z dříve existující složené ovládací prvky nebo dříve existující ovládací prvky Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="6d650-105">Through inheritance, you can create your own controls from preexisting composite controls or preexisting Windows Forms controls.</span></span> <span data-ttu-id="6d650-106">Můžete taky navrhnout vlastní ovládací prvky, které implementují vlastní Malování.</span><span class="sxs-lookup"><span data-stu-id="6d650-106">You can also design your own controls that implement custom painting.</span></span> <span data-ttu-id="6d650-107">Tyto možnosti Povolit značnou flexibilitu při návrhu a funkčnost visual rozhraní.</span><span class="sxs-lookup"><span data-stu-id="6d650-107">These options enable a great deal of flexibility to the design and functionality of the visual interface.</span></span> <span data-ttu-id="6d650-108">Abyste mohli využívat tyto funkce, musí být obeznámeni s koncepty programování na základě objektů.</span><span class="sxs-lookup"><span data-stu-id="6d650-108">To take advantage of these features, you should be familiar with object-based programming concepts.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6d650-109">Není nutné mít důkladné znalosti týkající se dědičnosti, ale může být užitečné k odkazování na [základní informace o dědičnosti (Visual Basic)](~/docs/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span><span class="sxs-lookup"><span data-stu-id="6d650-109">It is not necessary to have a thorough understanding of inheritance, but you may find it useful to refer to [Inheritance basics (Visual Basic)](~/docs/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span></span>  
  
 <span data-ttu-id="6d650-110">Pokud chcete vytvořit vlastní ovládací prvky pro použití na webové formuláře naleznete v části [vývoj vlastních serverových ovládacích prvků ASP.NET](http://msdn.microsoft.com/library/fbe26c16-cff4-4089-b3dd-877411f0c0ef).</span><span class="sxs-lookup"><span data-stu-id="6d650-110">If you want to create custom controls to use on Web Forms, see [Developing Custom ASP.NET Server Controls](http://msdn.microsoft.com/library/fbe26c16-cff4-4089-b3dd-877411f0c0ef).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6d650-111">V tomto oddílu</span><span class="sxs-lookup"><span data-stu-id="6d650-111">In This Section</span></span>  
 [<span data-ttu-id="6d650-112">Návod: Vytvoření složeného ovládacího prvku pomocí Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6d650-112">Walkthrough: Authoring a Composite Control with Visual Basic</span></span>](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md)  
 <span data-ttu-id="6d650-113">Ukazuje, jak vytvořit jednoduché složeného ovládacího prvku v jazyce Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="6d650-113">Shows how to create a simple composite control in Visual Basic.</span></span>  
  
 [<span data-ttu-id="6d650-114">Návod: Vytvoření složeného ovládacího prvku pomocí Visual C#</span><span class="sxs-lookup"><span data-stu-id="6d650-114">Walkthrough: Authoring a Composite Control with Visual C#</span></span>](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-csharp.md)  
 <span data-ttu-id="6d650-115">Ukazuje, jak vytvořit jednoduché složeného ovládacího prvku v jazyce C#.</span><span class="sxs-lookup"><span data-stu-id="6d650-115">Shows how to create a simple composite control in C#.</span></span>  
  
 [<span data-ttu-id="6d650-116">Návod: Dědění z ovládacího prvku Windows Forms pomocí Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6d650-116">Walkthrough: Inheriting from a Windows Forms Control with Visual Basic</span></span>](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)  
 <span data-ttu-id="6d650-117">Ukazuje postup vytvoření jednoduchého ovládacího prvku Windows Forms s použitím dědičnosti v jazyce Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="6d650-117">Shows how to create a simple Windows Forms control using inheritance in Visual Basic.</span></span>  
  
 [<span data-ttu-id="6d650-118">Návod: Dědění z ovládacího prvku Windows Forms pomocí Visual C#</span><span class="sxs-lookup"><span data-stu-id="6d650-118">Walkthrough: Inheriting from a Windows Forms Control with Visual C#</span></span>](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)  
 <span data-ttu-id="6d650-119">Ukazuje postup vytvoření jednoduchého ovládacího prvku Windows Forms s použitím dědičnosti v jazyce C#.</span><span class="sxs-lookup"><span data-stu-id="6d650-119">Shows how to create a simple Windows Forms control using inheritance in C#.</span></span>  
  
 [<span data-ttu-id="6d650-120">Návod: Provádění obecných úloh pomocí inteligentních značek v systému Windows Forms – ovládací prvky</span><span class="sxs-lookup"><span data-stu-id="6d650-120">Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/performing-common-tasks-using-smart-tags-on-wf-controls.md)  
 <span data-ttu-id="6d650-121">Ukazuje, jak používat funkci inteligentních značek v ovládacích prvcích Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="6d650-121">Shows how to use the smart tag feature on Windows Forms controls.</span></span>  
  
 [<span data-ttu-id="6d650-122">Návod: Serializace kolekcí standardních typů s DesignerSerializationVisibilityAttribute</span><span class="sxs-lookup"><span data-stu-id="6d650-122">Walkthrough: Serializing Collections of Standard Types with the DesignerSerializationVisibilityAttribute</span></span>](../../../../docs/framework/winforms/controls/serializing-collections-designerserializationvisibilityattribute.md)  
 <span data-ttu-id="6d650-123">Ukazuje, jak používat <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content?displayProperty=nameWithType> atribut k serializaci kolekce.</span><span class="sxs-lookup"><span data-stu-id="6d650-123">Shows how to use the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content?displayProperty=nameWithType> attribute to serialize a collection.</span></span>  
  
 [<span data-ttu-id="6d650-124">Návod: Ladění vlastních Windows Forms – ovládací prvky v době návrhu</span><span class="sxs-lookup"><span data-stu-id="6d650-124">Walkthrough: Debugging Custom Windows Forms Controls at Design Time</span></span>](../../../../docs/framework/winforms/controls/walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)  
 <span data-ttu-id="6d650-125">Ukazuje, jak k ladění návrhu chování ovládacího prvku Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="6d650-125">Shows how to debug the design-time behavior of a Windows Forms control.</span></span>  
  
 [<span data-ttu-id="6d650-126">Návod: Vytvoření ovládacího prvku Windows Forms, který využívá funkce sady Visual Studio návrhu</span><span class="sxs-lookup"><span data-stu-id="6d650-126">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)  
 <span data-ttu-id="6d650-127">Ukazuje, jak úzce integruje složeného ovládacího prvku do prostředí návrhu.</span><span class="sxs-lookup"><span data-stu-id="6d650-127">Shows how to tightly integrate a composite control into the design environment.</span></span>  
  
 [<span data-ttu-id="6d650-128">Postupy: vytváření ovládacích prvků pro Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6d650-128">How to: Author Controls for Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)  
 <span data-ttu-id="6d650-129">Poskytuje přehled aspektů pro implementaci ovládacího prvku Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="6d650-129">Provides an overview of considerations for implementing a Windows Forms control.</span></span>  
  
 [<span data-ttu-id="6d650-130">Postupy: vytváření složených ovládacích prvků</span><span class="sxs-lookup"><span data-stu-id="6d650-130">How to: Author Composite Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-author-composite-controls.md)  
 <span data-ttu-id="6d650-131">Ukazuje, jak vytvořit ovládací prvek dědění ze složeného ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="6d650-131">Shows how to create a control by inheriting from a composite control.</span></span>  
  
 [<span data-ttu-id="6d650-132">Postupy: dědění ze třídy UserControl</span><span class="sxs-lookup"><span data-stu-id="6d650-132">How to: Inherit from the UserControl Class</span></span>](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)  
 <span data-ttu-id="6d650-133">Obsahuje přehled postupu pro vytvoření složeného ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="6d650-133">Provides an overview of the procedure for creating a composite control.</span></span>  
  
 [<span data-ttu-id="6d650-134">Postupy: dědění ze stávajícího systému Windows Forms – ovládací prvky</span><span class="sxs-lookup"><span data-stu-id="6d650-134">How to: Inherit from Existing Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-inherit-from-existing-windows-forms-controls.md)  
 <span data-ttu-id="6d650-135">Ukazuje, jak vytvořit dědění z ovládacího prvku rozšířené <xref:System.Windows.Forms.Button> třídu ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="6d650-135">Shows how to create an extended control by inheriting from the <xref:System.Windows.Forms.Button> control class.</span></span>  
  
 [<span data-ttu-id="6d650-136">Postupy: dědění ze třídy Control</span><span class="sxs-lookup"><span data-stu-id="6d650-136">How to: Inherit from the Control Class</span></span>](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-control-class.md)  
 <span data-ttu-id="6d650-137">Poskytuje přehled vytvoření ovládacího prvku rozšířené.</span><span class="sxs-lookup"><span data-stu-id="6d650-137">Provides an overview of creating an extended control.</span></span>  
  
 [<span data-ttu-id="6d650-138">Postupy: zarovnání ovládacího prvku k okrajům formuláře během návrhu</span><span class="sxs-lookup"><span data-stu-id="6d650-138">How to: Align a Control to the Edges of Forms at Design Time</span></span>](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)  
 <span data-ttu-id="6d650-139">Ukazuje, jak používat <xref:System.Windows.Forms.Control.Dock%2A> vlastnost zarovnání ovládacího prvku hrany zabírá formuláře.</span><span class="sxs-lookup"><span data-stu-id="6d650-139">Shows how to use the <xref:System.Windows.Forms.Control.Dock%2A> property to align your control to the edge of the form it occupies.</span></span>  
  
 [<span data-ttu-id="6d650-140">Postupy: zobrazení ovládacího prvku v výběr položek sady nástrojů – dialogové okno</span><span class="sxs-lookup"><span data-stu-id="6d650-140">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>](../../../../docs/framework/winforms/controls/how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)  
 <span data-ttu-id="6d650-141">Ukazuje postup instalace vlastního ovládacího prvku tak, aby se zobrazuje v **přizpůsobení sady nástrojů** dialogové okno.</span><span class="sxs-lookup"><span data-stu-id="6d650-141">Shows the procedure for installing your control so that it appears in the **Customize Toolbox** dialog box.</span></span>  
  
 [<span data-ttu-id="6d650-142">Postupy: poskytování rastrového obrázku panelu nástrojů pro ovládací prvek</span><span class="sxs-lookup"><span data-stu-id="6d650-142">How to: Provide a Toolbox Bitmap for a Control</span></span>](../../../../docs/framework/winforms/controls/how-to-provide-a-toolbox-bitmap-for-a-control.md)  
 <span data-ttu-id="6d650-143">Ukazuje, jak používat <xref:System.Drawing.ToolboxBitmapAttribute> zobrazíte ikonu vedle vašeho vlastního ovládacího prvku v **sada nástrojů**.</span><span class="sxs-lookup"><span data-stu-id="6d650-143">Shows how to use the <xref:System.Drawing.ToolboxBitmapAttribute> to display an icon next to your custom control in the **Toolbox**.</span></span>  
  
 [<span data-ttu-id="6d650-144">Postupy: testování běhového chování UserControl</span><span class="sxs-lookup"><span data-stu-id="6d650-144">How to: Test the Run-Time Behavior of a UserControl</span></span>](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)  
 <span data-ttu-id="6d650-145">Ukazuje, jak používat **UserControl Test kontejneru** k testování chování složeného ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="6d650-145">Shows how to use the **UserControl Test Container** to test the behavior of a composite control.</span></span>  
  
 [<span data-ttu-id="6d650-146">Chyby při návrhu v Návrháři formulářů Windows</span><span class="sxs-lookup"><span data-stu-id="6d650-146">Design-Time Errors in the Windows Forms Designer</span></span>](../../../../docs/framework/winforms/controls/design-time-errors-in-the-windows-forms-designer.md)  
 <span data-ttu-id="6d650-147">Vysvětluje význam a použití seznamu chyb návrhu, které se zobrazí v sadě Microsoft Visual Studio po Návrhář formulářů Windows nepodaří načíst.</span><span class="sxs-lookup"><span data-stu-id="6d650-147">Explains the meaning and use of the Design-Time Error List that appears in Microsoft Visual Studio when the Windows Forms designer fails to load.</span></span>  
  
 [<span data-ttu-id="6d650-148">Řešení potíží s komponenty vytváření a řízení</span><span class="sxs-lookup"><span data-stu-id="6d650-148">Troubleshooting Control and Component Authoring</span></span>](../../../../docs/framework/winforms/controls/troubleshooting-control-and-component-authoring.md)  
 <span data-ttu-id="6d650-149">Ukazuje, jak diagnostikovat a opravit běžné problémy, které může dojít, když vytváříte vlastní komponenta nebo ovládací prvek.</span><span class="sxs-lookup"><span data-stu-id="6d650-149">Shows how to diagnose and fix common issues that can occur when you author a custom component or control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="6d650-150">Odkaz</span><span class="sxs-lookup"><span data-stu-id="6d650-150">Reference</span></span>  
 <xref:System.Windows.Forms.Control?displayProperty=nameWithType>  
 <span data-ttu-id="6d650-151">Tato třída popisuje a obsahuje odkazy na všechny její členy.</span><span class="sxs-lookup"><span data-stu-id="6d650-151">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>  
 <span data-ttu-id="6d650-152">Tato třída popisuje a obsahuje odkazy na všechny její členy.</span><span class="sxs-lookup"><span data-stu-id="6d650-152">Describes this class and has links to all of its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="6d650-153">Související oddíly</span><span class="sxs-lookup"><span data-stu-id="6d650-153">Related Sections</span></span>  
 [<span data-ttu-id="6d650-154">Vývoj vlastních Windows Forms – ovládací prvky s rozhraním .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6d650-154">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 <span data-ttu-id="6d650-155">Popisuje, jak vytvořit vlastní ovládací prvky s rozhraním .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6d650-155">Discusses how to create your own custom controls with the .NET Framework.</span></span>  
  
 [<span data-ttu-id="6d650-156">Jazyková nezávislost a jazykově nezávislé komponenty</span><span class="sxs-lookup"><span data-stu-id="6d650-156">Language Independence and Language-Independent Components</span></span>](../../../../docs/standard/language-independence-and-language-independent-components.md)  
 <span data-ttu-id="6d650-157">Představuje modul common language runtime, který je určený k zjednodušení vytváření a používání komponent.</span><span class="sxs-lookup"><span data-stu-id="6d650-157">Introduces the common language runtime, which is designed to simplify the creation and use of components.</span></span> <span data-ttu-id="6d650-158">Důležitým aspektem toto zjednodušení je rozšířenou interoperabilitu mezi součástmi, které jsou napsané v různých programovacích jazyků.</span><span class="sxs-lookup"><span data-stu-id="6d650-158">An important aspect of this simplification is enhanced interoperability between components written using different programming languages.</span></span> <span data-ttu-id="6d650-159">Specifikace CLS (Common Language) umožňuje vytvořit nástroje a součásti, které pracují s více programovacích jazyků.</span><span class="sxs-lookup"><span data-stu-id="6d650-159">The Common Language Specification (CLS) makes it possible to create tools and components that work with multiple programming languages.</span></span>  
  
 [<span data-ttu-id="6d650-160">Návod: Automatické vyplnění nástrojů vlastními komponentami</span><span class="sxs-lookup"><span data-stu-id="6d650-160">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)  
 <span data-ttu-id="6d650-161">Popisuje, jak povolit komponenta nebo ovládací prvek, který se má zobrazit v **přizpůsobení sady nástrojů** dialogové okno.</span><span class="sxs-lookup"><span data-stu-id="6d650-161">Describes how to enable your component or control to be displayed in the **Customize Toolbox** dialog box.</span></span>
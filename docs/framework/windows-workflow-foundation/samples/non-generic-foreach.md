---
title: "Neobecné ForEach"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 576cd07a-d58d-4536-b514-77bad60bff38
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 234e5a7ef9591c1e943484402bc235b62ad7fb87
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="non-generic-foreach"></a><span data-ttu-id="58659-102">Neobecné ForEach</span><span class="sxs-lookup"><span data-stu-id="58659-102">Non-Generic ForEach</span></span>
[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]<span data-ttu-id="58659-103">se dodává v jeho nástrojů sadu aktivity toku řízení, včetně <xref:System.Activities.Statements.ForEach%601>, což umožňuje iterace v rámci <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable` kolekce.</span><span class="sxs-lookup"><span data-stu-id="58659-103"> ships in its toolbox a set of Control Flow activities, including <xref:System.Activities.Statements.ForEach%601>, which allows iterating through <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable` collections.</span></span>  
  
 <span data-ttu-id="58659-104"><xref:System.Activities.Statements.ForEach%601>vyžaduje jeho <xref:System.Activities.Statements.ForEach%601.Values%2A> vlastnost, která má být typu <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable`.</span><span class="sxs-lookup"><span data-stu-id="58659-104"><xref:System.Activities.Statements.ForEach%601> requires its <xref:System.Activities.Statements.ForEach%601.Values%2A> property to be of type <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable`.</span></span> <span data-ttu-id="58659-105">To vylučuje uživatelé z iterování přes datové struktury, které implementují <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable` rozhraní (například <xref:System.Collections.ArrayList>).</span><span class="sxs-lookup"><span data-stu-id="58659-105">This precludes users from iterating over data structures that implement <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable` interface (for example, <xref:System.Collections.ArrayList>).</span></span> <span data-ttu-id="58659-106">Verze neobecnou <xref:System.Activities.Statements.ForEach%601> překonává tento požadavek za cenu složitější běhu k zajištění kompatibility typů hodnot v kolekci.</span><span class="sxs-lookup"><span data-stu-id="58659-106">The non-generic version of <xref:System.Activities.Statements.ForEach%601> overcomes this requirement, at the expense of more run-time complexity for ensuring the compatibility of the types of the values in the collection.</span></span>  
  
 <span data-ttu-id="58659-107">Tento příklad ukazuje, jak implementovat není obecný <xref:System.Activities.Statements.ForEach%601> aktivita a její designer.</span><span class="sxs-lookup"><span data-stu-id="58659-107">This sample shows how to implement a non-generic <xref:System.Activities.Statements.ForEach%601> activity and its designer.</span></span> <span data-ttu-id="58659-108">Tato aktivita lze použít k iteraci v rámci <xref:System.Collections.ArrayList>.</span><span class="sxs-lookup"><span data-stu-id="58659-108">This activity can be used to iterate through <xref:System.Collections.ArrayList>.</span></span>  
  
## <a name="foreach-activity"></a><span data-ttu-id="58659-109">ForEach aktivity</span><span class="sxs-lookup"><span data-stu-id="58659-109">ForEach Activity</span></span>  
 <span data-ttu-id="58659-110">C# / VB. `foreach` příkaz zobrazí prvky kolekce, provádění příkazu embedded pro každý prvek kolekce.</span><span class="sxs-lookup"><span data-stu-id="58659-110">The C#/VB `foreach` statement enumerates the elements of a collection, executing an embedded statement for each element of the collection.</span></span> <span data-ttu-id="58659-111">[!INCLUDE[wf1](../../../../includes/wf1-md.md)] Ekvivalentní činnosti `foreach` jsou <xref:System.Activities.Statements.ForEach%601> a <xref:System.Activities.Statements.ParallelForEach%601>.</span><span class="sxs-lookup"><span data-stu-id="58659-111">The [!INCLUDE[wf1](../../../../includes/wf1-md.md)] equivalent activities of `foreach` are <xref:System.Activities.Statements.ForEach%601> and <xref:System.Activities.Statements.ParallelForEach%601>.</span></span> <span data-ttu-id="58659-112"><xref:System.Activities.Statements.ForEach%601> Aktivity obsahuje seznam hodnoty a text.</span><span class="sxs-lookup"><span data-stu-id="58659-112">The <xref:System.Activities.Statements.ForEach%601> activity contains a list of values and a body.</span></span> <span data-ttu-id="58659-113">V době běhu je vstupní seznamu a text je provést pro každou hodnotu v seznamu.</span><span class="sxs-lookup"><span data-stu-id="58659-113">At runtime, the list is iterated and the body is executed for each value in the list.</span></span>  
  
 <span data-ttu-id="58659-114">Pro většině případů obecné verze aktivity musí být upřednostňované řešení, protože pokrývá většinu scénářů, ve kterých se použije a poskytuje typ kontroly v době kompilace.</span><span class="sxs-lookup"><span data-stu-id="58659-114">For most cases, the generic version of the activity should be the preferred solution, because it covers most of the scenarios in which it would be used, and provides type checking at compile time.</span></span> <span data-ttu-id="58659-115">Verze neobecnou lze použít pro iterace v rámci typy, které implementují neobecnou <xref:System.Collections.IEnumerable> rozhraní.</span><span class="sxs-lookup"><span data-stu-id="58659-115">The non-generic version can be used for iterating through types that implement the non-generic <xref:System.Collections.IEnumerable> interface.</span></span>  
  
## <a name="class-definition"></a><span data-ttu-id="58659-116">Definice třídy</span><span class="sxs-lookup"><span data-stu-id="58659-116">Class Definition</span></span>  
 <span data-ttu-id="58659-117">Následující příklad kódu ukazuje definici není obecný `ForEach` aktivity.</span><span class="sxs-lookup"><span data-stu-id="58659-117">The following code example shows the definition of a non-generic `ForEach` activity.</span></span>  
  
```  
[ContentProperty("Body")]  
public class ForEach : NativeActivity  
{  
    [RequiredArgument]  
    [DefaultValue(null)]  
    InArgument<IEnumerable> Values { get; set; }  
  
    [DefaultValue(null)]  
    [DependsOn("Values")]  
    ActivityAction<object> Body { get; set; }   
}  
```  
  
 <span data-ttu-id="58659-118">Text (volitelné)</span><span class="sxs-lookup"><span data-stu-id="58659-118">Body (optional)</span></span>  
 <span data-ttu-id="58659-119"><xref:System.Activities.ActivityAction> Typu <xref:System.Object>, který je spouštěna každý prvek v kolekci.</span><span class="sxs-lookup"><span data-stu-id="58659-119">The <xref:System.Activities.ActivityAction> of type <xref:System.Object>, which is executed for each element in the collection.</span></span> <span data-ttu-id="58659-120">Každý jednotlivý prvek je předána do textu prostřednictvím jeho `Argument` vlastnost.</span><span class="sxs-lookup"><span data-stu-id="58659-120">Each individual element is passed into the Body through its `Argument` property.</span></span>  
  
 <span data-ttu-id="58659-121">Hodnoty (volitelné)</span><span class="sxs-lookup"><span data-stu-id="58659-121">Values (optional)</span></span>  
 <span data-ttu-id="58659-122">Kolekce elementů, které jsou vstupní přes.</span><span class="sxs-lookup"><span data-stu-id="58659-122">The collection of elements that are iterated over.</span></span> <span data-ttu-id="58659-123">Zajistíte, že všechny elementy kolekce typů kompatibilní se provádí za běhu.</span><span class="sxs-lookup"><span data-stu-id="58659-123">Ensuring that all elements of the collection are of compatible types is done at run-time.</span></span>  
  
## <a name="example-of-using-foreach"></a><span data-ttu-id="58659-124">Příklad použití příkazu ForEach</span><span class="sxs-lookup"><span data-stu-id="58659-124">Example of Using ForEach</span></span>  
 <span data-ttu-id="58659-125">Následující kód ukazuje, jak pomocí příkazu ForEach aktivity v aplikaci.</span><span class="sxs-lookup"><span data-stu-id="58659-125">The following code demonstrates how to use the ForEach activity in an application.</span></span>  
  
```  
string[] names = { "bill", "steve", "ray" };  
  
DelegateInArgument<object> iterationVariable = new DelegateInArgument<object>() { Name = "iterationVariable" };  
  
Activity sampleUsage =  
    new ForEach  
    {  
       Values = new InArgument<IEnumerable>(c=> names),  
       Body = new ActivityAction<object>   
       {                          
           Argument = iterationVariable,  
           Handler = new WriteLine  
           {  
               Text = new InArgument<string>(env => string.Format("Hello {0}",                                                               iterationVariable.Get(env)))  
           }  
       }  
   };  
```  
  
|<span data-ttu-id="58659-126">Podmínka</span><span class="sxs-lookup"><span data-stu-id="58659-126">Condition</span></span>|<span data-ttu-id="58659-127">Zpráva</span><span class="sxs-lookup"><span data-stu-id="58659-127">Message</span></span>|<span data-ttu-id="58659-128">Závažnost</span><span class="sxs-lookup"><span data-stu-id="58659-128">Severity</span></span>|<span data-ttu-id="58659-129">Typ výjimky</span><span class="sxs-lookup"><span data-stu-id="58659-129">Exception Type</span></span>|  
|---------------|-------------|--------------|--------------------|  
|<span data-ttu-id="58659-130">Je hodnoty`null`</span><span class="sxs-lookup"><span data-stu-id="58659-130">Values is `null`</span></span>|<span data-ttu-id="58659-131">Nebyla zadána hodnota pro argument požadované aktivity 'Hodnoty'.</span><span class="sxs-lookup"><span data-stu-id="58659-131">Value for a required activity argument 'Values' was not supplied.</span></span>|<span data-ttu-id="58659-132">Chyba</span><span class="sxs-lookup"><span data-stu-id="58659-132">Error</span></span>|<xref:System.InvalidOperationException>|  
  
## <a name="foreach-designer"></a><span data-ttu-id="58659-133">Návrhář ForEach</span><span class="sxs-lookup"><span data-stu-id="58659-133">ForEach Designer</span></span>  
 <span data-ttu-id="58659-134">Návrhář aktivity pro vzorovou se podobá vzhledu s návrháře zadaná pro integrované <xref:System.Activities.Statements.ForEach%601> aktivity.</span><span class="sxs-lookup"><span data-stu-id="58659-134">The activity designer for the sample is similar in appearance to the designer provided for the built-in <xref:System.Activities.Statements.ForEach%601> activity.</span></span> <span data-ttu-id="58659-135">Návrhář se zobrazí v panelu nástrojů v **ukázky**, **aktivity obecného bez** kategorie.</span><span class="sxs-lookup"><span data-stu-id="58659-135">The designer appears in the toolbox in the **Samples**, **Non-Generic Activities** category.</span></span> <span data-ttu-id="58659-136">Návrhář jmenuje **ForEachWithBodyFactory** v sadě nástrojů, protože zpřístupní aktivity <xref:System.Activities.Presentation.IActivityTemplateFactory> v sadě nástrojů, která vytvoří aktivita s správně nakonfigurované <xref:System.Activities.ActivityAction>.</span><span class="sxs-lookup"><span data-stu-id="58659-136">The designer is named **ForEachWithBodyFactory** in the toolbox, because the activity exposes an <xref:System.Activities.Presentation.IActivityTemplateFactory> in the toolbox, which creates the activity with a properly configured <xref:System.Activities.ActivityAction>.</span></span>  
  
```  
public sealed class ForEachWithBodyFactory : IActivityTemplateFactory  
{  
    public Activity Create(DependencyObject target)  
    {  
        return new Microsoft.Samples.Activities.Statements.ForEach()  
        {  
            Body = new ActivityAction<object>()  
            {  
                Argument = new DelegateInArgument<object>()  
                {  
                    Name = "item"  
                }  
            }  
        };  
    }  
}  
```  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="58659-137">Chcete tuto ukázku spustit</span><span class="sxs-lookup"><span data-stu-id="58659-137">To run this sample</span></span>  
  
1.  <span data-ttu-id="58659-138">Nastavte projekt zvoleného jako projekt spuštění řešení:</span><span class="sxs-lookup"><span data-stu-id="58659-138">Set the project of your choice as the start-up project of the solution:</span></span>  
  
    1.  <span data-ttu-id="58659-139">**CodeTestClient** ukazuje, jak pomocí aktivity pomocí kódu.</span><span class="sxs-lookup"><span data-stu-id="58659-139">**CodeTestClient** shows how to use the activity using code.</span></span>  
  
    2.  <span data-ttu-id="58659-140">**DesignerTestClient** ukazuje, jak pomocí aktivity v návrháři.</span><span class="sxs-lookup"><span data-stu-id="58659-140">**DesignerTestClient** shows how to use the activity within the designer.</span></span>  
  
2.  <span data-ttu-id="58659-141">Sestavte a spusťte projekt.</span><span class="sxs-lookup"><span data-stu-id="58659-141">Build and run the project.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="58659-142">Ukázky může být již nainstalována na váš počítač.</span><span class="sxs-lookup"><span data-stu-id="58659-142">The samples may already be installed on your machine.</span></span> <span data-ttu-id="58659-143">Před pokračováním zkontrolovat na následující adresář (výchozí).</span><span class="sxs-lookup"><span data-stu-id="58659-143">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="58659-144">Pokud tento adresář neexistuje, přejděte na [Windows Communication Foundation (WCF) a ukázky Windows Workflow Foundation (WF) pro rozhraní .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) ke stažení všechny [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] a [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ukázky.</span><span class="sxs-lookup"><span data-stu-id="58659-144">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="58659-145">Tato ukázka se nachází v následujícím adresáři.</span><span class="sxs-lookup"><span data-stu-id="58659-145">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\NonGenericForEach`
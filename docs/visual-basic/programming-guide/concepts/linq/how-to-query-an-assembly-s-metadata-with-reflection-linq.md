---
title: "Postupy: dotazování sestavení & č. 39; s Metadata s reflexí (LINQ) (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 53caa336-ab83-4181-b0f6-5c87c5f9e4ee
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 718f8d78ac71c8d6d28f762e756eb2a0219fce19
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-query-an-assembly39s-metadata-with-reflection-linq-visual-basic"></a><span data-ttu-id="90dcf-102">Postupy: dotazování sestavení & č. 39; s Metadata s reflexí (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="90dcf-102">How to: Query An Assembly&#39;s Metadata with Reflection (LINQ) (Visual Basic)</span></span>
<span data-ttu-id="90dcf-103">Následující příklad ukazuje, jak lze použít LINQ s reflexí načíst konkrétní metadata o metodách, které splňují zadané kritérium.</span><span class="sxs-lookup"><span data-stu-id="90dcf-103">The following example shows how LINQ can be used with reflection to retrieve specific metadata about methods that match a specified search criterion.</span></span> <span data-ttu-id="90dcf-104">V takovém případě bude dotaz vrátí názvy ze všech metod sestavení, které vrací výčtové typy jako je například pole.</span><span class="sxs-lookup"><span data-stu-id="90dcf-104">In this case, the query will find the names of all the methods in the assembly that return enumerable types such as arrays.</span></span>  
  
## <a name="example"></a><span data-ttu-id="90dcf-105">Příklad</span><span class="sxs-lookup"><span data-stu-id="90dcf-105">Example</span></span>  
  
```vb  
Imports System.Reflection  
Imports System.IO  
Imports System.Linq  
Module Module1  
  
    Sub Main()  
        Dim asmbly As Assembly =   
            Assembly.Load("System.Core, Version=3.5.0.0, Culture=neutral, PublicKeyToken= b77a5c561934e089")  
  
        Dim pubTypesQuery = From type In asmbly.GetTypes()   
                            Where type.IsPublic   
                            From method In type.GetMethods()   
                            Where method.ReturnType.IsArray = True   
                            Let name = method.ToString()   
                            Let typeName = type.ToString()   
                            Group name By typeName Into methodNames = Group  
  
        Console.WriteLine("Getting ready to iterate")  
        For Each item In pubTypesQuery  
            Console.WriteLine(item.methodNames)  
  
            For Each type In item.methodNames  
                Console.WriteLine(" " & type)  
            Next  
        Next  
        Console.ReadKey()  
    End Sub  
  
End Module  
```  
  
 <span data-ttu-id="90dcf-106">V příkladu se používá <xref:System.Reflection.Assembly.GetTypes%2A> metoda vrátí pole typů v zadaném sestavení.</span><span class="sxs-lookup"><span data-stu-id="90dcf-106">The example uses the <xref:System.Reflection.Assembly.GetTypes%2A> method to return an array of types in the specified assembly.</span></span> <span data-ttu-id="90dcf-107">[Klauzule Where](../../../../visual-basic/language-reference/queries/where-clause.md) filtr tak, aby se vrátí jenom veřejné typy.</span><span class="sxs-lookup"><span data-stu-id="90dcf-107">The [Where Clause](../../../../visual-basic/language-reference/queries/where-clause.md) filter is applied so that only public types are returned.</span></span> <span data-ttu-id="90dcf-108">Pro každý typ veřejné poddotazu je generována pomocí <xref:System.Reflection.MethodInfo> pole, která je vrácena z <xref:System.Type.GetMethods%2A> volání.</span><span class="sxs-lookup"><span data-stu-id="90dcf-108">For each public type, a subquery is generated by using the <xref:System.Reflection.MethodInfo> array that is returned from the <xref:System.Type.GetMethods%2A> call.</span></span> <span data-ttu-id="90dcf-109">Tyto výsledky se filtrují vrátit pouze těch metod, jejichž návratový typ je nebo pole s jiným typem, který implementuje <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="90dcf-109">These results are filtered to return only those methods whose return type is an array or else a type that implements <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="90dcf-110">Nakonec jsou tyto výsledky seskupené podle pomocí názvu typu jako klíč.</span><span class="sxs-lookup"><span data-stu-id="90dcf-110">Finally, these results are grouped by using the type name as a key.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="90dcf-111">Probíhá kompilace kódu</span><span class="sxs-lookup"><span data-stu-id="90dcf-111">Compiling the Code</span></span>  
 <span data-ttu-id="90dcf-112">Vytvoření projektu, jehož cílem rozhraní .NET Framework verze 3.5 nebo vyšší s odkazem na System.Core.dll a `Imports` příkaz pro obor názvů System.Linq.</span><span class="sxs-lookup"><span data-stu-id="90dcf-112">Create a project that targets the .NET Framework version 3.5 or higher with a reference to System.Core.dll and a `Imports` statement for the System.Linq namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90dcf-113">Viz také</span><span class="sxs-lookup"><span data-stu-id="90dcf-113">See Also</span></span>  
 [<span data-ttu-id="90dcf-114">LINQ na objekty (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="90dcf-114">LINQ to Objects (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)
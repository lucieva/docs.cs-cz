---
title: "Postupy: vytváření sjednocení C-C++ pomocí atributů (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 85f35e56-26e0-4d31-9f3a-89bd4005e71a
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 450fb922079ca6737b8db7754f25435b9c3b884b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-cc-union-by-using-attributes-c"></a><span data-ttu-id="04f23-102">Postupy: vytváření sjednocení C/C++ pomocí atributů (C#)</span><span class="sxs-lookup"><span data-stu-id="04f23-102">How to: Create a C/C++ Union by Using Attributes (C#)</span></span>
<span data-ttu-id="04f23-103">Pomocí atributů můžete přizpůsobit, jak jsou rozloženy struktury v paměti.</span><span class="sxs-lookup"><span data-stu-id="04f23-103">By using attributes you can customize how structs are laid out in memory.</span></span> <span data-ttu-id="04f23-104">Například můžete vytvořit, která se označuje jako sjednocení v jazyce C/C++ pomocí `StructLayout(LayoutKind.Explicit)` a `FieldOffset` atributy.</span><span class="sxs-lookup"><span data-stu-id="04f23-104">For example, you can create what is known as a union in C/C++ by using the `StructLayout(LayoutKind.Explicit)` and `FieldOffset` attributes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04f23-105">Příklad</span><span class="sxs-lookup"><span data-stu-id="04f23-105">Example</span></span>  
 <span data-ttu-id="04f23-106">V tomto segmentu kódu, všechna pole z `TestUnion` spustit ve stejném umístění v paměti.</span><span class="sxs-lookup"><span data-stu-id="04f23-106">In this code segment, all of the fields of `TestUnion` start at the same location in memory.</span></span>  
  
```csharp  
// Add a using directive for System.Runtime.InteropServices.  
  
       [System.Runtime.InteropServices.StructLayout(LayoutKind.Explicit)]  
       struct TestUnion  
       {  
           [System.Runtime.InteropServices.FieldOffset(0)]  
           public int i;  
  
           [System.Runtime.InteropServices.FieldOffset(0)]  
           public double d;  
  
           [System.Runtime.InteropServices.FieldOffset(0)]  
           public char c;  
  
           [System.Runtime.InteropServices.FieldOffset(0)]  
           public byte b;  
       }  
```  
  
## <a name="example"></a><span data-ttu-id="04f23-107">Příklad</span><span class="sxs-lookup"><span data-stu-id="04f23-107">Example</span></span>  
 <span data-ttu-id="04f23-108">Zde je další příklad kde počáteční pole v různých explicitně nastavit umístění.</span><span class="sxs-lookup"><span data-stu-id="04f23-108">The following is another example where fields start at different explicitly set locations.</span></span>  
  
```csharp  
// Add a using directive for System.Runtime.InteropServices.  
  
       [System.Runtime.InteropServices.StructLayout(LayoutKind.Explicit)]  
       struct TestExplicit  
       {  
           [System.Runtime.InteropServices.FieldOffset(0)]  
           public long lg;  
  
           [System.Runtime.InteropServices.FieldOffset(0)]  
           public int i1;  
  
           [System.Runtime.InteropServices.FieldOffset(4)]  
           public int i2;  
  
           [System.Runtime.InteropServices.FieldOffset(8)]  
           public double d;  
  
           [System.Runtime.InteropServices.FieldOffset(12)]  
           public char c;  
  
           [System.Runtime.InteropServices.FieldOffset(14)]  
           public byte b;  
       }  
```  
  
 <span data-ttu-id="04f23-109">Pole dva celé číslo `i1` a `i2`, sdílet stejné umístění paměti jako `lg`.</span><span class="sxs-lookup"><span data-stu-id="04f23-109">The two integer fields, `i1` and `i2`, share the same memory locations as `lg`.</span></span> <span data-ttu-id="04f23-110">Tento druh kontrolu nad struktura rozložení je užitečné při použití vyvolání platformy.</span><span class="sxs-lookup"><span data-stu-id="04f23-110">This sort of control over struct layout is useful when using platform invocation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04f23-111">Viz také</span><span class="sxs-lookup"><span data-stu-id="04f23-111">See Also</span></span>  
 <xref:System.Reflection>  
 <xref:System.Attribute>  
 [<span data-ttu-id="04f23-112">Průvodce programováním v C#</span><span class="sxs-lookup"><span data-stu-id="04f23-112">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="04f23-113">Atributy</span><span class="sxs-lookup"><span data-stu-id="04f23-113">Attributes</span></span>](https://msdn.microsoft.com/library/5x6cd29c)  
 [<span data-ttu-id="04f23-114">Reflexe (C#)</span><span class="sxs-lookup"><span data-stu-id="04f23-114">Reflection (C#)</span></span>](../../../../csharp/programming-guide/concepts/reflection.md)  
 [<span data-ttu-id="04f23-115">Atributy (C#)</span><span class="sxs-lookup"><span data-stu-id="04f23-115">Attributes (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/index.md)  
 [<span data-ttu-id="04f23-116">Vytváření vlastních atributů (C#)</span><span class="sxs-lookup"><span data-stu-id="04f23-116">Creating Custom Attributes (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/creating-custom-attributes.md)  
 [<span data-ttu-id="04f23-117">Přístup k atributům pomocí reflexe (C#)</span><span class="sxs-lookup"><span data-stu-id="04f23-117">Accessing Attributes by Using Reflection (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)
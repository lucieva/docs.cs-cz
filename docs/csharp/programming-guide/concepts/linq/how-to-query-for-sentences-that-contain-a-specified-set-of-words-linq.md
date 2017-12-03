---
title: "Postupy: dotazu na věty obsahující zadanou množinu slov (LINQ) (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 0724b429-4b87-4d26-a7b1-409358f3fc20
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: befc93a21388a87fdfd2416349b1310e82378f18
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq-c"></a><span data-ttu-id="0c06c-102">Postupy: dotazu na věty obsahující zadanou množinu slov (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="0c06c-102">How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (C#)</span></span>
<span data-ttu-id="0c06c-103">Tento příklad ukazuje, jak najít věty do textového souboru, které obsahují odpovídá pro každou zadanou množinu slov.</span><span class="sxs-lookup"><span data-stu-id="0c06c-103">This example shows how to find sentences in a text file that contain matches for each of a specified set of words.</span></span> <span data-ttu-id="0c06c-104">I když pole hledaných termínů je pevně zakódovaná v tomto příkladu, se může také naplnit dynamicky za běhu.</span><span class="sxs-lookup"><span data-stu-id="0c06c-104">Although the array of search terms is hard-coded in this example, it could also be populated dynamically at runtime.</span></span> <span data-ttu-id="0c06c-105">V tomto příkladu dotaz vrátí věty obsahující slova "Upřednostňovala", "data" a "integrované".</span><span class="sxs-lookup"><span data-stu-id="0c06c-105">In this example, the query returns the sentences that contain the words "Historically," "data," and "integrated."</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c06c-106">Příklad</span><span class="sxs-lookup"><span data-stu-id="0c06c-106">Example</span></span>  
  
```csharp  
class FindSentences  
{  
    static void Main()  
    {  
        string text = @"Historically, the world of data and the world of objects " +  
        @"have not been well integrated. Programmers work in C# or Visual Basic " +  
        @"and also in SQL or XQuery. On the one side are concepts such as classes, " +  
        @"objects, fields, inheritance, and .NET Framework APIs. On the other side " +  
        @"are tables, columns, rows, nodes, and separate languages for dealing with " +  
        @"them. Data types often require translation between the two worlds; there are " +  
        @"different standard functions. Because the object world has no notion of query, a " +  
        @"query can only be represented as a string without compile-time type checking or " +  
        @"IntelliSense support in the IDE. Transferring data from SQL tables or XML trees to " +  
        @"objects in memory is often tedious and error-prone.";  
  
        // Split the text block into an array of sentences.  
        string[] sentences = text.Split(new char[] { '.', '?', '!' });  
  
        // Define the search terms. This list could also be dynamically populated at runtime.  
        string[] wordsToMatch = { "Historically", "data", "integrated" };  
  
        // Find sentences that contain all the terms in the wordsToMatch array.  
        // Note that the number of terms to match is not specified at compile time.  
        var sentenceQuery = from sentence in sentences  
                            let w = sentence.Split(new char[] { '.', '?', '!', ' ', ';', ':', ',' },  
                                                    StringSplitOptions.RemoveEmptyEntries)  
                            where w.Distinct().Intersect(wordsToMatch).Count() == wordsToMatch.Count()  
                            select sentence;  
  
        // Execute the query. Note that you can explicitly type  
        // the iteration variable here even though sentenceQuery  
        // was implicitly typed.   
        foreach (string str in sentenceQuery)  
        {  
            Console.WriteLine(str);  
        }  
  
        // Keep the console window open in debug mode.  
        Console.WriteLine("Press any key to exit");  
        Console.ReadKey();  
    }  
}  
/* Output:  
Historically, the world of data and the world of objects have not been well integrated  
*/  
```  
  
 <span data-ttu-id="0c06c-107">Dotaz funguje tak, že nejprve rozdělení text do věty a pak do pole řetězců, které mají jednotlivých slov rozdělení věty.</span><span class="sxs-lookup"><span data-stu-id="0c06c-107">The query works by first splitting the text into sentences, and then splitting the sentences into an array of strings that hold each word.</span></span> <span data-ttu-id="0c06c-108">Pro každou z těchto polí <xref:System.Linq.Enumerable.Distinct%2A> metoda odebere všechna duplicitní slova, a potom se provede dotaz <xref:System.Linq.Enumerable.Intersect%2A> operace na pole aplikace word a `wordsToMatch` pole.</span><span class="sxs-lookup"><span data-stu-id="0c06c-108">For each of these arrays, the <xref:System.Linq.Enumerable.Distinct%2A> method removes all duplicate words, and then the query performs an <xref:System.Linq.Enumerable.Intersect%2A> operation on the word array and the `wordsToMatch` array.</span></span> <span data-ttu-id="0c06c-109">Pokud počet průniku je stejný jako počet `wordsToMatch` pole, všechna slova nebyly nalezeny v slova a je vrácen původní větu.</span><span class="sxs-lookup"><span data-stu-id="0c06c-109">If the count of the intersection is the same as the count of the `wordsToMatch` array, all words were found in the words and the original sentence is returned.</span></span>  
  
 <span data-ttu-id="0c06c-110">Ve volání <xref:System.String.Split%2A>, interpunkčních znamének se používají jako oddělovače, aby bylo možné je odebrat z řetězce.</span><span class="sxs-lookup"><span data-stu-id="0c06c-110">In the call to <xref:System.String.Split%2A>, the punctuation marks are used as separators in order to remove them from the string.</span></span> <span data-ttu-id="0c06c-111">Pokud není to uděláte, například můžete mít řetězec "Upřednostňovala", který by odpovídat "V minulosti" v `wordsToMatch` pole.</span><span class="sxs-lookup"><span data-stu-id="0c06c-111">If you did not do this, for example you could have a string "Historically," that would not match "Historically" in the `wordsToMatch` array.</span></span> <span data-ttu-id="0c06c-112">Budete muset použít další oddělovačů, v závislosti na typech interpunkce v textu zdroj nalézt.</span><span class="sxs-lookup"><span data-stu-id="0c06c-112">You may have to use additional separators, depending on the types of punctuation found in the source text.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0c06c-113">Probíhá kompilace kódu</span><span class="sxs-lookup"><span data-stu-id="0c06c-113">Compiling the Code</span></span>  
 <span data-ttu-id="0c06c-114">Vytvoření projektu, jehož cílem rozhraní .NET Framework verze 3.5 nebo vyšší, s odkazem na System.Core.dll a `using` direktivy pro obory názvů System.Linq a System.IO.</span><span class="sxs-lookup"><span data-stu-id="0c06c-114">Create a project that targets the .NET Framework  version 3.5 or higher, with a reference to System.Core.dll and `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c06c-115">Viz také</span><span class="sxs-lookup"><span data-stu-id="0c06c-115">See Also</span></span>  
 [<span data-ttu-id="0c06c-116">LINQ a řetězce (C#)</span><span class="sxs-lookup"><span data-stu-id="0c06c-116">LINQ and Strings (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-and-strings.md)
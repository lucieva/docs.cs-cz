---
title: "Postupy: Čtení z textového souboru (Průvodce programováním v C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: StreamReader.ReadToEnd
helpviewer_keywords:
- text files, writing to
- reading text files
- reading data, text files
- text files, reading
ms.assetid: 92246c5b-e819-4eea-9370-1a9460e12de3
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d2af6102ac6793b4612a6fbc41f8c50189cc24d5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-read-from-a-text-file-c-programming-guide"></a><span data-ttu-id="54591-102">Postupy: Čtení z textového souboru (Průvodce programováním v C#)</span><span class="sxs-lookup"><span data-stu-id="54591-102">How to: Read From a Text File (C# Programming Guide)</span></span>
<span data-ttu-id="54591-103">Tento příklad načte obsah textového souboru s použitím statické metody <xref:System.IO.File.ReadAllText%2A> a <xref:System.IO.File.ReadAllLines%2A> z <xref:System.IO.File?displayProperty=nameWithType> třídy.</span><span class="sxs-lookup"><span data-stu-id="54591-103">This example reads the contents of a text file by using the static methods <xref:System.IO.File.ReadAllText%2A> and <xref:System.IO.File.ReadAllLines%2A> from the <xref:System.IO.File?displayProperty=nameWithType> class.</span></span>  
  
 <span data-ttu-id="54591-104">Pro příklad, který používá <xref:System.IO.StreamReader>, najdete v části [postupy: čtení textového souboru řádcích současně](../../../csharp/programming-guide/file-system/how-to-read-a-text-file-one-line-at-a-time.md).</span><span class="sxs-lookup"><span data-stu-id="54591-104">For an example that uses <xref:System.IO.StreamReader>, see [How to: Read a Text File One Line at a Time](../../../csharp/programming-guide/file-system/how-to-read-a-text-file-one-line-at-a-time.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="54591-105">Soubory, které se používají v tomto příkladu jsou vytvořené v tomto tématu [postupy: zápis do textového souboru](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md).</span><span class="sxs-lookup"><span data-stu-id="54591-105">The files that are used in this example are created in the topic [How to: Write to a Text File](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="54591-106">Příklad</span><span class="sxs-lookup"><span data-stu-id="54591-106">Example</span></span>  
 [!code-csharp[csFilesandFolders#4](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-read-from-a-text-file_1.cs)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="54591-107">Probíhá kompilace kódu</span><span class="sxs-lookup"><span data-stu-id="54591-107">Compiling the Code</span></span>  
 <span data-ttu-id="54591-108">Zkopírujte kód a vložte jej do konzolovou aplikaci C#.</span><span class="sxs-lookup"><span data-stu-id="54591-108">Copy the code and paste it into a C# console application.</span></span>  
  
 <span data-ttu-id="54591-109">Pokud nepoužíváte textové soubory z [postupy: zápis do textového souboru](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md), nahraďte argument `ReadAllText` a `ReadAllLines` s odpovídající název a cesta k souboru ve vašem počítači.</span><span class="sxs-lookup"><span data-stu-id="54591-109">If you are not using the text files from [How to: Write to a Text File](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md), replace the argument to `ReadAllText` and `ReadAllLines` with the appropriate path and file name on your computer.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="54591-110">Robustní programování</span><span class="sxs-lookup"><span data-stu-id="54591-110">Robust Programming</span></span>  
 <span data-ttu-id="54591-111">Následující podmínky mohou způsobit výjimku:</span><span class="sxs-lookup"><span data-stu-id="54591-111">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="54591-112">Soubor neexistuje nebo neexistuje v zadaném umístění.</span><span class="sxs-lookup"><span data-stu-id="54591-112">The file doesn't exist or doesn't exist at the specified location.</span></span> <span data-ttu-id="54591-113">Zkontrolujte cestu a správnost názvu souboru.</span><span class="sxs-lookup"><span data-stu-id="54591-113">Check the path and the spelling of the file name.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="54591-114">Zabezpečení rozhraní .NET Framework</span><span class="sxs-lookup"><span data-stu-id="54591-114">.NET Framework Security</span></span>  
 <span data-ttu-id="54591-115">Nespoléhejte na název souboru k určení obsahu souboru.</span><span class="sxs-lookup"><span data-stu-id="54591-115">Do not rely on the name of a file to determine the contents of the file.</span></span> <span data-ttu-id="54591-116">Například soubor `myFile.cs` nemusí být zdrojový soubor C#.</span><span class="sxs-lookup"><span data-stu-id="54591-116">For example, the file `myFile.cs` might not be a C# source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54591-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="54591-117">See Also</span></span>  
 <xref:System.IO?displayProperty=nameWithType>  
 [<span data-ttu-id="54591-118">Průvodce programováním v C#</span><span class="sxs-lookup"><span data-stu-id="54591-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="54591-119">Systém souborů a registr (C# Průvodce programováním)</span><span class="sxs-lookup"><span data-stu-id="54591-119">File System and the Registry (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/index.md)
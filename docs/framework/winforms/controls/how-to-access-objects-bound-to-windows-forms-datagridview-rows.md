---
title: "Postupy: Přístup k objektům připojeným k řádkům Windows Forms DataGridView"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- object binding [Windows Forms], accessing bound objects
- data grids [Windows Forms], accessing bound objects
- DataGridView control [Windows Forms], accessing objects bound to rows
ms.assetid: 0e05748f-4403-4eb8-8b2f-b098108181b5
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 910730f67024fbe0d292b4a329a36fb3ea8254b5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-access-objects-bound-to-windows-forms-datagridview-rows"></a><span data-ttu-id="10325-102">Postupy: Přístup k objektům připojeným k řádkům Windows Forms DataGridView</span><span class="sxs-lookup"><span data-stu-id="10325-102">How to: Access Objects Bound to Windows Forms DataGridView Rows</span></span>
<span data-ttu-id="10325-103">Někdy je užitečné zobrazit tabulku informací uložených v kolekci objektů firmy.</span><span class="sxs-lookup"><span data-stu-id="10325-103">Sometimes it is useful to display a table of information stored in a collection of business objects.</span></span> <span data-ttu-id="10325-104">Po vytvoření vazby <xref:System.Windows.Forms.DataGridView> řízení takové shromažďování každé veřejné vlastnosti se zobrazí v vlastní sloupce, pokud vlastnost nebyl označen jiný procházet s <xref:System.ComponentModel.BrowsableAttribute>.</span><span class="sxs-lookup"><span data-stu-id="10325-104">When you bind a <xref:System.Windows.Forms.DataGridView> control to such a collection, each public property is displayed in its own column unless the property has been marked non-browsable with a <xref:System.ComponentModel.BrowsableAttribute>.</span></span> <span data-ttu-id="10325-105">Například kolekce `Customer` objekty by mít sloupce jako **název** a **adresu**.</span><span class="sxs-lookup"><span data-stu-id="10325-105">For example, a collection of `Customer` objects would have columns such as **Name** and **Address**.</span></span>  
  
 <span data-ttu-id="10325-106">Pokud tyto objekty obsahují další informace a kód, který chcete získat přístup, mohou být využity prostřednictvím řádek objekty.</span><span class="sxs-lookup"><span data-stu-id="10325-106">If these objects contain additional information and code that you want to access, you can reach it through row objects.</span></span> <span data-ttu-id="10325-107">Uživatelé v následujícím příkladu kódu, můžete vybrat více řádků a klikněte na tlačítko pro odesílání pro všechny zákazníky odpovídající faktury.</span><span class="sxs-lookup"><span data-stu-id="10325-107">In the following code example, users can select multiple rows and click a button to send an invoice to each of the corresponding customers.</span></span>  
  
### <a name="to-access-row-bound-objects"></a><span data-ttu-id="10325-108">Pro přístup k objektům vázané na řádek</span><span class="sxs-lookup"><span data-stu-id="10325-108">To access row-bound objects</span></span>  
  
-   <span data-ttu-id="10325-109">Použití <xref:System.Windows.Forms.DataGridViewRow.DataBoundItem%2A?displayProperty=nameWithType> vlastnost.</span><span class="sxs-lookup"><span data-stu-id="10325-109">Use the <xref:System.Windows.Forms.DataGridViewRow.DataBoundItem%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewObjectBinding#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewObjectBinding/CS/datagridviewobjectbinding.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewObjectBinding#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewObjectBinding/VB/datagridviewobjectbinding.vb#10)]  
  
## <a name="example"></a><span data-ttu-id="10325-110">Příklad</span><span class="sxs-lookup"><span data-stu-id="10325-110">Example</span></span>  
 <span data-ttu-id="10325-111">Úplný příklad kódu zahrnuje jednoduchou `Customer` implementaci a vazby <xref:System.Windows.Forms.DataGridView> k <xref:System.Collections.ArrayList> obsahuje několik `Customer` objekty.</span><span class="sxs-lookup"><span data-stu-id="10325-111">The complete code example includes a simple `Customer` implementation and binds the <xref:System.Windows.Forms.DataGridView> to an <xref:System.Collections.ArrayList> containing a few `Customer` objects.</span></span> <span data-ttu-id="10325-112"><xref:System.Windows.Forms.Control.Click> Obslužnou rutinu události <xref:System.Windows.Forms.Button?displayProperty=nameWithType> potřebuje přístup `Customer` objekty prostřednictvím řádky, protože není přístupný mimo kolekci zákazníka <xref:System.Windows.Forms.Form.Load?displayProperty=nameWithType> obslužné rutiny události.</span><span class="sxs-lookup"><span data-stu-id="10325-112">The <xref:System.Windows.Forms.Control.Click> event handler of the <xref:System.Windows.Forms.Button?displayProperty=nameWithType> must access the `Customer` objects through the rows, because the customer collection is not accessible outside the <xref:System.Windows.Forms.Form.Load?displayProperty=nameWithType> event handler.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridViewObjectBinding#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewObjectBinding/CS/datagridviewobjectbinding.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewObjectBinding#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewObjectBinding/VB/datagridviewobjectbinding.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="10325-113">Probíhá kompilace kódu</span><span class="sxs-lookup"><span data-stu-id="10325-113">Compiling the Code</span></span>  
 <span data-ttu-id="10325-114">Tento příklad vyžaduje:</span><span class="sxs-lookup"><span data-stu-id="10325-114">This example requires:</span></span>  
  
-   <span data-ttu-id="10325-115">Odkazy na systém a System.Windows.Forms sestavení.</span><span class="sxs-lookup"><span data-stu-id="10325-115">References to the System and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="10325-116">Informace o sestavení z příkazového řádku pro tento příklad [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] nebo [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], najdete v části [sestavení z příkazového řádku](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) nebo [vytváření pomocí příkazového řádku csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="10325-116">For information about building this example from the command line for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="10325-117">V tomto příkladu můžete také vytvořit [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] zadáním nebo vložením kódu do nového projektu.</span><span class="sxs-lookup"><span data-stu-id="10325-117">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="10325-118">Viz také [postupy: zkompilování a spuštění dokončení Windows Forms kód příklad pomocí sady Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="10325-118">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10325-119">Viz také</span><span class="sxs-lookup"><span data-stu-id="10325-119">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewRow>  
 <xref:System.Windows.Forms.DataGridViewRow.DataBoundItem%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="10325-120">Zobrazení dat v ovládacím prvku Windows Forms DataGridView</span><span class="sxs-lookup"><span data-stu-id="10325-120">Displaying Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="10325-121">Postupy: připojení objektů k ovládacích prvků Windows Forms DataGridView</span><span class="sxs-lookup"><span data-stu-id="10325-121">How to: Bind Objects to Windows Forms DataGridView Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-objects-to-windows-forms-datagridview-controls.md)
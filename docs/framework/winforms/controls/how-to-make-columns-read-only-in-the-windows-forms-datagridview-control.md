---
title: "Postupy: Přepnutí sloupců do režimu jen pro čtení v ovládacím prvku Windows Forms DataGridView"
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
- data grids [Windows Forms], read-only columns
- DataGridView control [Windows Forms], read-only columns
ms.assetid: 2bb73ebb-1a55-4362-9fda-e50574c087d5
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f3fb80b5baeafff53781cb1ff430ad05dd93f2ad
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-make-columns-read-only-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="89633-102">Postupy: Přepnutí sloupců do režimu jen pro čtení v ovládacím prvku Windows Forms DataGridView</span><span class="sxs-lookup"><span data-stu-id="89633-102">How to: Make Columns Read-Only in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="89633-103">Všechna data je určená pro úpravy.</span><span class="sxs-lookup"><span data-stu-id="89633-103">Not all data is meant for editing.</span></span> <span data-ttu-id="89633-104">V <xref:System.Windows.Forms.DataGridView> řídit, sloupci <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> vlastnost hodnota určuje, zda mohou uživatelé upravovat buňky v tomto sloupci.</span><span class="sxs-lookup"><span data-stu-id="89633-104">In the <xref:System.Windows.Forms.DataGridView> control, the column <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> property value determines whether users can edit cells in that column.</span></span> <span data-ttu-id="89633-105">Informace o tom, jak byl ovládací prvek zcela jen pro čtení najdete v tématu [postupy: zabránění přidávání řádků a odstranění v ovládacím prvku Windows Forms DataGridView](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md).</span><span class="sxs-lookup"><span data-stu-id="89633-105">For information about how to make the control entirely read-only, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md).</span></span>  
  
 <span data-ttu-id="89633-106">Není poskytována podpora pro tuto úlohu v sadě Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="89633-106">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="89633-107">Viz také [postup: Zkontrolujte sloupce jen pro čtení v Windows Forms DataGridView – ovládací prvek pomocí návrháře](http://msdn.microsoft.com/library/xd4k3c7e\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="89633-107">Also see [How to: Make Columns Read-Only in the Windows Forms DataGridView Control Using the Designer](http://msdn.microsoft.com/library/xd4k3c7e\(v=vs.110\)).</span></span>  
  
### <a name="to-make-a-column-read-only-programmatically"></a><span data-ttu-id="89633-108">Chcete-li sloupec jen pro čtení prostřednictvím kódu programu</span><span class="sxs-lookup"><span data-stu-id="89633-108">To make a column read-only programmatically</span></span>  
  
-   <span data-ttu-id="89633-109">Nastavte <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType> vlastnost `true`.</span><span class="sxs-lookup"><span data-stu-id="89633-109">Set the <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType> property to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#064](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#064)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#064](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#064)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="89633-110">Probíhá kompilace kódu</span><span class="sxs-lookup"><span data-stu-id="89633-110">Compiling the Code</span></span>  
 <span data-ttu-id="89633-111">Tento příklad vyžaduje:</span><span class="sxs-lookup"><span data-stu-id="89633-111">This example requires:</span></span>  
  
-   <span data-ttu-id="89633-112">A <xref:System.Windows.Forms.DataGridView> ovládací prvek s názvem `dataGridView1` s sloupec s názvem `CompanyName`.</span><span class="sxs-lookup"><span data-stu-id="89633-112">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` with a column named `CompanyName`.</span></span>  
  
-   <span data-ttu-id="89633-113">Odkazuje na <xref:System?displayProperty=nameWithType> a <xref:System.Windows.Forms?displayProperty=nameWithType> sestavení.</span><span class="sxs-lookup"><span data-stu-id="89633-113">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89633-114">Viz také</span><span class="sxs-lookup"><span data-stu-id="89633-114">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.Columns%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="89633-115">Základní funkce sloupce, řádku a buňky v ovládacím prvku Windows Forms DataGridView</span><span class="sxs-lookup"><span data-stu-id="89633-115">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)  
 [<span data-ttu-id="89633-116">Postupy: zabránění řádek přidání a odstranění ve Windows Forms DataGridView – ovládací prvek</span><span class="sxs-lookup"><span data-stu-id="89633-116">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md)
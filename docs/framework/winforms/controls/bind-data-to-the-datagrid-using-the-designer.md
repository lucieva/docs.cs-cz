---
title: "Postupy: Vytvoření vazby dat k ovládacímu prvku Windows Forms DataGridView pomocí Návrháře"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms controls, binding to a data source
- data sources [Windows Forms], binding to Windows Forms controls
- DataGridView control [Windows Forms], data binding
ms.assetid: f4f46009-cec2-441b-8668-6b5af057558b
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2a203aa20865a4180b4eb9a7b192fc3c9b73a2f7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="444ca-102">Postupy: Vytvoření vazby dat k ovládacímu prvku Windows Forms DataGridView pomocí Návrháře</span><span class="sxs-lookup"><span data-stu-id="444ca-102">How to: Bind Data to the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="444ca-103">Můžete použít návrháře pro připojení <xref:System.Windows.Forms.DataGridView> ovládacího prvku do zdroje dat několik různé typy, včetně databází, obchodní objekty nebo webové služby.</span><span class="sxs-lookup"><span data-stu-id="444ca-103">You can use the designer to connect a <xref:System.Windows.Forms.DataGridView> control to data sources of several different varieties, including databases, business objects, or Web services.</span></span> <span data-ttu-id="444ca-104">Při vytvoření vazby ovládacího prvku ke zdroji dat pomocí návrháře, je ovládací prvek vázán automaticky k <xref:System.Windows.Forms.BindingSource> komponenty, která představuje příslušný zdroj dat.</span><span class="sxs-lookup"><span data-stu-id="444ca-104">When you bind the control to a data source using the designer, the control is automatically bound to a <xref:System.Windows.Forms.BindingSource> component that represents the data source.</span></span> <span data-ttu-id="444ca-105">Kromě toho sloupce jsou automaticky generovány v ovládacím prvku tak, aby odpovídaly zadaný zdroj dat informace o schématu.</span><span class="sxs-lookup"><span data-stu-id="444ca-105">Additionally, columns are automatically generated in the control to match the schema information provided by the data source.</span></span>  
  
 <span data-ttu-id="444ca-106">Po vygenerování sloupců, můžete upravit, aby vyhovovala vašim potřebám.</span><span class="sxs-lookup"><span data-stu-id="444ca-106">After columns have been generated, you can modify them to meet your needs.</span></span> <span data-ttu-id="444ca-107">Například můžete odebrat nebo skrýt sloupce vás zajímá není v zobrazení, můžete pořadí sloupců nebo můžete upravit typy sloupců.</span><span class="sxs-lookup"><span data-stu-id="444ca-107">For example, you can remove or hide columns you are not interested in displaying, you can rearrange the columns, or you can modify the column types.</span></span> <span data-ttu-id="444ca-108">Další informace o úpravách sloupců najdete v tématech uvedených v části Viz také.</span><span class="sxs-lookup"><span data-stu-id="444ca-108">For more information about modifying columns, see the topics listed in the See Also section.</span></span>  
  
 <span data-ttu-id="444ca-109">Můžete také navázat více <xref:System.Windows.Forms.DataGridView> ovládací prvky pro tabulky v relaci k vytvoření relací a podrobností.</span><span class="sxs-lookup"><span data-stu-id="444ca-109">You can also bind multiple <xref:System.Windows.Forms.DataGridView> controls to related tables to create master/detail relationships.</span></span> <span data-ttu-id="444ca-110">V této konfiguraci jeden ovládací prvek zobrazí nadřazenou tabulkou a další ovládací prvek pouze řádky z podřízené tabulky, které se vztahují k aktuální řádek v nadřazené tabulce.</span><span class="sxs-lookup"><span data-stu-id="444ca-110">In this configuration, one control displays a parent table and another control displays only those rows from a child table that are related to the current row in the parent table.</span></span> <span data-ttu-id="444ca-111">Další informace najdete v tématu [postupy: zobrazení souvisejících dat ve formulářové aplikaci Windows](http://msdn.microsoft.com/library/60b1f1ec-6257-42ab-83f0-06d54ed364fd).</span><span class="sxs-lookup"><span data-stu-id="444ca-111">For more information, see [How to: Display Related Data in a Windows Forms Application](http://msdn.microsoft.com/library/60b1f1ec-6257-42ab-83f0-06d54ed364fd).</span></span>  
  
 <span data-ttu-id="444ca-112">Následující postup vyžaduje **aplikace Windows** projekt pomocí formuláře, který obsahuje <xref:System.Windows.Forms.DataGridView> ovládací prvek nebo dvou ovládacích prvků pro relaci a podrobností.</span><span class="sxs-lookup"><span data-stu-id="444ca-112">The following procedure requires a **Windows Application** project with a form that contains a <xref:System.Windows.Forms.DataGridView> control or two controls for a master/detail relationship.</span></span> <span data-ttu-id="444ca-113">Informace o spuštění tohoto projektu najdete v tématu [postupy: vytvoření projektu aplikace Windows](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) a [postupy: Přidání ovládacích prvků do formulářů Windows](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="444ca-113">For information about starting such a project, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="444ca-114">Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici.</span><span class="sxs-lookup"><span data-stu-id="444ca-114">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="444ca-115">Chcete-li změnit nastavení, zvolte **nastavení importu a exportu** na **nástroje** nabídky.</span><span class="sxs-lookup"><span data-stu-id="444ca-115">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="444ca-116">Další informace najdete v tématu [přizpůsobení nastavení pro vývoj v sadě Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="444ca-116">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-bind-the-control-to-a-data-source"></a><span data-ttu-id="444ca-117">K vytvoření vazby ovládacího prvku ke zdroji dat</span><span class="sxs-lookup"><span data-stu-id="444ca-117">To bind the control to a data source</span></span>  
  
1.  <span data-ttu-id="444ca-118">Klikněte na inteligentní značky glyfy (![inteligentní značky glyfy](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) v pravém horním rohu <xref:System.Windows.Forms.DataGridView> ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="444ca-118">Click the smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
2.  <span data-ttu-id="444ca-119">Klikněte na šipku rozevíracího seznamu pro **zvolit zdroj dat** možnost.</span><span class="sxs-lookup"><span data-stu-id="444ca-119">Click the drop-down arrow for the **Choose Data Source** option.</span></span>  
  
3.  <span data-ttu-id="444ca-120">Pokud váš projekt již nemá zdroj dat, klikněte na tlačítko **přidat zdroj dat projektu** a postupujte podle kroků uvedených v průvodci.</span><span class="sxs-lookup"><span data-stu-id="444ca-120">If your project does not already have a data source, click **Add Project Data Source** and follow the steps indicated by the wizard.</span></span>  
  
     <span data-ttu-id="444ca-121">Další informace najdete v tématu [Průvodce konfigurací zdroje dat](http://msdn.microsoft.com/library/c4df7de5-5da0-4064-940c-761dd6d9e28f).</span><span class="sxs-lookup"><span data-stu-id="444ca-121">For more information, see [Data Source Configuration Wizard](http://msdn.microsoft.com/library/c4df7de5-5da0-4064-940c-761dd6d9e28f).</span></span> <span data-ttu-id="444ca-122">Váš nový zdroj dat se objeví v **zvolit zdroj dat** okno rozevíracího seznamu.</span><span class="sxs-lookup"><span data-stu-id="444ca-122">Your new data source will appear in the **Choose Data Source** drop-down window.</span></span> <span data-ttu-id="444ca-123">Pokud váš nový zdroj dat obsahuje pouze jednoho člena, jako je například jeden databázové tabulky, vytvoří automaticky vazbu ovládacího prvku tohoto člena.</span><span class="sxs-lookup"><span data-stu-id="444ca-123">If your new data source contains only one member, such as a single database table, the control will automatically bind to that member.</span></span> <span data-ttu-id="444ca-124">V opačném případě pokračujte k dalšímu kroku.</span><span class="sxs-lookup"><span data-stu-id="444ca-124">Otherwise, continue to the next step.</span></span>  
  
4.  <span data-ttu-id="444ca-125">Rozbalte **jiných zdrojů dat** a **zdroje dat projektu** uzly, pokud nejsou rozbalená a potom vyberte zdroj dat pro vazbu ovládacího prvku do.</span><span class="sxs-lookup"><span data-stu-id="444ca-125">Expand the **Other Data Sources** and **Project Data Sources** nodes if they are not already expanded, and then select the data source to bind the control to.</span></span>  
  
5.  <span data-ttu-id="444ca-126">Pokud zdroj dat obsahuje více než jednoho člena, jako třeba když jste vytvořili <xref:System.Data.DataSet?displayProperty=nameWithType> obsahující více tabulek, rozbalení zdroje dat a pak vyberte konkrétní člena pro vazbu.</span><span class="sxs-lookup"><span data-stu-id="444ca-126">If your data source contains more than one member, such as if you have created a <xref:System.Data.DataSet?displayProperty=nameWithType> that contains multiple tables, expand the data source, and then select the specific member to bind to.</span></span>  
  
6.  <span data-ttu-id="444ca-127">K vytvoření vztahu seznam podrobnosti v **zvolit zdroj dat** rozevíracího okna pro druhý <xref:System.Windows.Forms.DataGridView> řídit, rozbalte <xref:System.Windows.Forms.BindingSource> vytvoří pro nadřazenou tabulku a pak vybrat související podřízenou tabulku ze seznamu Zobrazit.</span><span class="sxs-lookup"><span data-stu-id="444ca-127">To create a master/detail relationship, in the **Choose Data Source** drop-down window for a second <xref:System.Windows.Forms.DataGridView> control, expand the <xref:System.Windows.Forms.BindingSource> created for the parent table, and then select the related child table from the list shown.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="444ca-128">Pokud váš projekt již má zdroj dat, můžete také použít **zdroje dat** okno Vytvoření dat formuláře.</span><span class="sxs-lookup"><span data-stu-id="444ca-128">If your project already has a data source, you can also use the **Data Sources** window to create a data form.</span></span> <span data-ttu-id="444ca-129">Další informace najdete v tématu [okno zdroje dat](http://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992).</span><span class="sxs-lookup"><span data-stu-id="444ca-129">For more information, see [Data Sources Window](http://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="444ca-130">Viz také</span><span class="sxs-lookup"><span data-stu-id="444ca-130">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.Windows.Forms.DataGridView.DataMember%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="444ca-131">Postupy: připojování k datům v databázi</span><span class="sxs-lookup"><span data-stu-id="444ca-131">How to: Connect to Data in a Database</span></span>](http://msdn.microsoft.com/library/6c56e54e-8834-4297-85aa-cc1a443ba556)  
 [<span data-ttu-id="444ca-132">Postupy: přidávání a odebírání sloupců v systému Windows Forms DataGridView – ovládací prvek pomocí návrháře</span><span class="sxs-lookup"><span data-stu-id="444ca-132">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md)  
 [<span data-ttu-id="444ca-133">Postupy: Změna pořadí sloupců v prvku Windows Forms DataGridView pomocí návrháře</span><span class="sxs-lookup"><span data-stu-id="444ca-133">How to: Change the Order of Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/change-the-order-of-columns-in-the-datagrid-using-the-designer.md)  
 [<span data-ttu-id="444ca-134">Postupy: Změna typu sloupce Windows Forms DataGridView pomocí návrháře</span><span class="sxs-lookup"><span data-stu-id="444ca-134">How to: Change the Type of a Windows Forms DataGridView Column Using the Designer</span></span>](../../../../docs/framework/winforms/controls/change-the-type-of-a-wf-datagridview-column-using-the-designer.md)  
 [<span data-ttu-id="444ca-135">Postupy: zablokování sloupců v systému Windows Forms DataGridView – ovládací prvek pomocí návrháře</span><span class="sxs-lookup"><span data-stu-id="444ca-135">How to: Freeze Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/freeze-columns-in-the-datagrid-using-the-designer.md)  
 [<span data-ttu-id="444ca-136">Postupy: skrytí sloupců v systému Windows Forms DataGridView – ovládací prvek pomocí návrháře</span><span class="sxs-lookup"><span data-stu-id="444ca-136">How to: Hide Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/hide-columns-in-the-datagrid-using-the-designer.md)  
 [<span data-ttu-id="444ca-137">Postupy: přepnutí sloupců jen pro čtení v systému Windows Forms DataGridView – ovládací prvek pomocí návrháře</span><span class="sxs-lookup"><span data-stu-id="444ca-137">How to: Make Columns Read-Only in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/make-columns-read-only-in-the-datagrid-using-the-designer.md)  
 [<span data-ttu-id="444ca-138">Postupy: vytvoření projektu aplikace Windows</span><span class="sxs-lookup"><span data-stu-id="444ca-138">How to: Create a Windows Application Project</span></span>](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [<span data-ttu-id="444ca-139">Postupy: Přidání ovládacích prvků do formulářů Windows</span><span class="sxs-lookup"><span data-stu-id="444ca-139">How to: Add Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)  
 [<span data-ttu-id="444ca-140">Okno zdroje dat</span><span class="sxs-lookup"><span data-stu-id="444ca-140">Data Sources Window</span></span>](http://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992)  
 [<span data-ttu-id="444ca-141">Postupy: zobrazení souvisejících dat v systému Windows Forms aplikace</span><span class="sxs-lookup"><span data-stu-id="444ca-141">How to: Display Related Data in a Windows Forms Application</span></span>](http://msdn.microsoft.com/library/60b1f1ec-6257-42ab-83f0-06d54ed364fd)
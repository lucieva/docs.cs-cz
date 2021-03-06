---
title: TreeView – přehled ovládacího prvku (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- TreeView
helpviewer_keywords:
- TreeView control [Windows Forms], about TreeView control
ms.assetid: 0ece823a-9508-478a-bbdb-7d7c3bae51d5
ms.openlocfilehash: cc3fb394a2c55b7095a8111e7018b754985ab0e1
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/06/2018
ms.locfileid: "48839032"
---
# <a name="treeview-control-overview-windows-forms"></a>TreeView – přehled ovládacího prvku (Windows Forms)

Pomocí Windows Forms <xref:System.Windows.Forms.TreeView> ovládacího prvku, lze zobrazit hierarchii uzlů na uživatele, jako je způsob, jak soubory a složky se zobrazí v levém podokně funkci Windows Explorer operačního systému Windows. Každý uzel ve stromovém zobrazení může obsahovat další uzly, volá *podřízené uzly*. Můžete zobrazit nadřazené uzly, nebo uzly, které obsahují podřízené uzly, jako rozbalené nebo sbalené. Zobrazení stromu s zaškrtávací políčka vedle uzlů můžete zobrazit také tak, že nastavíte stromové zobrazení <xref:System.Windows.Forms.TreeView.CheckBoxes%2A> vlastnost `true`. Můžete programově poté zaškrtněte nebo zrušte uzly nastavením uzlu <xref:System.Windows.Forms.TreeNode.Checked%2A> vlastnost `true` nebo `false`.

## <a name="key-properties"></a>Vlastnosti klíče

Klíčové vlastnosti <xref:System.Windows.Forms.TreeView> řízení, představují <xref:System.Windows.Forms.TreeView.Nodes%2A> a <xref:System.Windows.Forms.TreeView.SelectedNode%2A>. <xref:System.Windows.Forms.TreeView.Nodes%2A> Vlastnost obsahuje seznam uzly nejvyšší úrovně ve stromovém zobrazení. <xref:System.Windows.Forms.TreeView.SelectedNode%2A> Vlastnost nastavuje aktuálně vybraný uzel. Můžete zobrazit ikony vedle uzlů. Ovládací prvek používá Image z <xref:System.Windows.Forms.ImageList> s názvem ve stromovém zobrazení <xref:System.Windows.Forms.TreeView.ImageList%2A> vlastnost. <xref:System.Windows.Forms.TreeView.ImageIndex%2A> Vlastnost nastaví na výchozí obrázku pro uzly ve stromovém zobrazení. Další informace o zobrazení obrázků najdete v tématu [postupy: Nastavení ikon pro ovládací prvek Windows Forms TreeView](../../../../docs/framework/winforms/controls/how-to-set-icons-for-the-windows-forms-treeview-control.md). Pokud používáte Visual Studio 2005, budete mít přístup k rozsáhlé knihovně standardní bitové kopie, které můžete použít s <xref:System.Windows.Forms.TreeView> ovládacího prvku.

## <a name="see-also"></a>Viz také

- <xref:System.Windows.Forms.TreeView>
- [Ovládací prvek TreeView](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)
- [Postupy: Nastavení ikon pro ovládací prvek Windows Forms TreeView](../../../../docs/framework/winforms/controls/how-to-set-icons-for-the-windows-forms-treeview-control.md)
- [Postupy: Přidání a odebrání uzlů s ovládacím prvkem Windows Forms TreeView](../../../../docs/framework/winforms/controls/how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)
- [Postupy: Iterace všemi uzly ovládacího prvku Windows Forms TreeView](../../../../docs/framework/winforms/controls/how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [Postupy: Určení uzlu TreeView označeného kliknutím](../../../../docs/framework/winforms/controls/how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [Postupy: Přidání vlastních informací do ovládacího prvku TreeView nebo ListView (Windows Forms)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)
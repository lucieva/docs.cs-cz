---
title: 'Návod: Serializace kolekcí standardních typů s DesignerSerializationVisibilityAttribute'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- serialization [Windows Forms], collections
- standard types [Windows Forms], collections
- collections [Windows Forms], serializing
- collections [Windows Forms], standard types
ms.assetid: 020c9df4-fdc5-4dae-815a-963ecae5668c
ms.openlocfilehash: 54859b3065e8e9bb9680d8b6bf7946b393f73b9f
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/05/2018
ms.locfileid: "43788078"
---
# <a name="walkthrough-serializing-collections-of-standard-types-with-the-designerserializationvisibilityattribute"></a>Návod: Serializace kolekcí standardních typů s DesignerSerializationVisibilityAttribute
Vlastní ovládací prvky se někdy vystavit kolekci jako vlastnost. Tento návod ukazuje, jak používat <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> třídy řídit, jak je kolekce serializovat v době návrhu. Použití <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> hodnota k vaší kolekci vlastností zajišťuje, že vlastnost bude serializována.  
  
 V tomto tématu jako jeden seznam zkopírovat kód, naleznete v tématu [postupy: serializace kolekcí ze standardních typů s DesignerSerializationVisibilityAttribute](https://msdn.microsoft.com/library/7829fcdd-8205-405f-8231-a1282a9835c9).  
  
> [!NOTE]
>  Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici. Chcete-li změnit nastavení, zvolte **nastavení importu a exportu** na **nástroje** nabídky. Další informace najdete v tématu [přizpůsobení integrovaného vývojového prostředí sady Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
## <a name="prerequisites"></a>Požadavky  
 K dokončení tohoto návodu budete potřebovat:  
  
-   Dostatečná oprávnění k vytvoření a spuštění projektů aplikace Windows Forms v počítači nainstalovanou aplikaci Visual Studio.  
  
## <a name="creating-a-control-that-has-a-serializable-collection"></a>Vytvoření ovládacího prvku, který je serializovatelný kolekce  
 Prvním krokem je vytvoření ovládacího prvku, který má kolekci serializovat jako vlastnost. Můžete upravit obsah této kolekce pomocí **Editor kolekce**, která je přístupná z **vlastnosti** okna.  
  
#### <a name="to-create-a-control-with-a-serializable-collection"></a>Vytvoření ovládacího prvku s serializovatelný kolekcí  
  
1.  Vytvořit projekt Knihovna ovládacích prvků Windows s názvem `SerializationDemoControlLib`. Další informace najdete v tématu [šablonu ovládacího prvku knihovny Windows](https://msdn.microsoft.com/library/722f4e2d-1310-4ed5-8f33-593337ab66b4).  
  
2.  Přejmenovat `UserControl1` k `SerializationDemoControl`. Další informace najdete v tématu [postupy: přejmenování identifikátorů](https://msdn.microsoft.com/library/2430f732-2b70-4516-8cf6-a7bb71cc9724).  
  
3.  V **vlastnosti** okno, nastavte hodnotu <xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType> vlastnost `10`.  
  
4.  Místo <xref:System.Windows.Forms.TextBox> v ovládacím prvku `SerializationDemoControl`.  
  
5.  Vyberte <xref:System.Windows.Forms.TextBox> ovládacího prvku. V **vlastnosti** okno, nastavte následující vlastnosti.  
  
    |Vlastnost|Změňte na|  
    |--------------|---------------|  
    |**Multiline**|`true`|  
    |**Ukotvení**|<xref:System.Windows.Forms.DockStyle.Fill>|  
    |**Posuvníky**|<xref:System.Windows.Forms.ScrollBars.Vertical>|  
    |**ReadOnly**|`true`|  
  
6.  V **Editor kódu**, deklarace pole pole řetězce s názvem `stringsValue` v `SerializationDemoControl`.  
  
     [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#4)]
     [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#4)]
     [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#4)]  
  
7.  Definovat `Strings` vlastnost `SerializationDemoControl`.  
  
> [!NOTE]
>  <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> Hodnota se používá k povolení serializace kolekce.  
  
 [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#5)]
 [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#5)]
 [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#5)]  
  
1.  Stisknutím klávesy F5 sestavte projekt a spusťte váš ovládací prvek **UserControl – kontejner testů**.  
  
2.  Najít `Strings` vlastnost <xref:System.Windows.Forms.PropertyGrid> z **UserControl – kontejner testů**. Klikněte na tlačítko `Strings` vlastnost, klepněte na tlačítko se třemi tečkami (![VisualStudioEllipsesButton snímek obrazovky](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) tlačítko Otevřít **Editor kolekce řetězců**.  
  
3.  Zadejte několik řetězců v **Editor kolekce řetězců**. Oddělte je stisknutím klávesy ENTER na konci každého řetězce. Klikněte na tlačítko **OK** po dokončení zadávání řetězců.  
  
> [!NOTE]
>  Zobrazí řetězce jste zadali v <xref:System.Windows.Forms.TextBox> z `SerializationDemoControl`.  
  
## <a name="serializing-a-collection-property"></a>Serializace vlastnost kolekce  
 K otestování chování serializace ovládacího prvku, umístěte ho na formuláři a změnit obsah kolekce s **Editor kolekce**. Zobrazí se stav serializovaná shromažďování zobrazením zvláštní soubor návrháře, do kterého **Návrháře formulářů Windows** emituje kód.  
  
#### <a name="to-serialize-a-collection"></a>K serializaci kolekce  
  
1.  Přidáte do řešení projekt aplikace Windows. Pojmenujte projekt `SerializationDemoControlTest`.  
  
2.  V **nástrojů**, najít na kartě s názvem **SerializationDemoControlLib komponenty**. Na této kartě můžete najít `SerializationDemoControl`. Další informace najdete v tématu [návod: Automatické vyplnění sady nástrojů pomocí vlastních komponent](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md).  
  
3.  Místo `SerializationDemoControl` na formuláři.  
  
4.  Najít `Strings` vlastnost **vlastnosti** okna. Klikněte na tlačítko `Strings` vlastnost, klepněte na tlačítko se třemi tečkami (![VisualStudioEllipsesButton snímek obrazovky](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) tlačítko Otevřít **Editor kolekce řetězců**.  
  
5.  Zadejte několik řetězců v **Editor kolekce řetězců**. Oddělte je stisknutím klávesy ENTER na konci každého řetězce. Klikněte na tlačítko **OK** po dokončení zadávání řetězců.  
  
> [!NOTE]
>  Zobrazí řetězce jste zadali v <xref:System.Windows.Forms.TextBox> z `SerializationDemoControl`.  
  
1.  V **Průzkumníka řešení**, klikněte na tlačítko **zobrazit všechny soubory** tlačítko.  
  
2.  Otevřít **Form1** uzlu. Rat je soubor s názvem **Form1.Designer.cs** nebo **Form1.Designer.vb**. Jedná se o soubor, do kterého **Návrháře formulářů Windows** emituje kód představující stav návrhu a jeho podřízených ovládacích prvků formuláře. Tento soubor otevřít v **Editor kódu**.  
  
3.  Otevřete oblast volá **kód generovaný návrhářem formulářů Windows** a vyhledejte část s názvem **serializationDemoControl1**. Pod tento popisek je kód představující serializovaný stav ovládacího prvku. Řetězce, které jste zadali v kroku 5 jsou zobrazeny v přiřazení k `Strings` vlastnost. Následující příklady kódu v C# a Visual Basic, zobrazit kód podobný co se zobrazí pokud jste zadali řetězce "red", "oranžové" a "žlutý".  
  
    ```csharp  
    this.serializationDemoControl1.Strings = new string[] {  
            "red",  
            "orange",  
            "yellow"};  
    ```  
    
    ```vb  
    Me.serializationDemoControl1.Strings = New String() {"red", "orange", "yellow"}  
    ```
  
4.  V **Editor kódu**, změňte hodnotu <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> na `Strings` vlastnost <xref:System.ComponentModel.DesignerSerializationVisibility.Hidden>.  
  
    ```csharp  
    [DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)]  
    ```  
    ```vb  
    <DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)> _  
    ```  
  
5. Znovu sestavte řešení a zopakujte kroky 3 a 4.  
  
> [!NOTE]
>  V takovém případě **Návrháře formulářů Windows** vysílá žádné přiřazení `Strings` vlastnost.  
  
## <a name="next-steps"></a>Další kroky  
 Když víte, jak serializace kolekcí standardních typů, vezměte v úvahu integrace vlastních ovládacích prvků hlouběji do návrhové prostředí. Následující témata popisují, jak vylepšit návrhu integrace vlastních ovládacích prvků:  
  
-   [Architektura návrhu](https://msdn.microsoft.com/library/4881917b-628f-4689-b872-472e4f8a4e3a)  
  
-   [Atributy v ovládacích prvcích Windows Forms](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)  
  
-   [Přehled serializace návrháře](https://msdn.microsoft.com/library/c342635a-aa5f-4281-915b-b013738af15a)  
  
-   [Návod: Vytvoření ovládacího prvku Windows Forms, který využívá funkce sady Visual Studio pro dobu návrhu](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)  
  
## <a name="see-also"></a>Viz také  
 <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute>  
 [Přehled serializace návrháře](https://msdn.microsoft.com/library/c342635a-aa5f-4281-915b-b013738af15a)  
 [Postupy: serializace kolekcí standardních typů s DesignerSerializationVisibilityAttribute](https://msdn.microsoft.com/library/7829fcdd-8205-405f-8231-a1282a9835c9)  
 [Návod: Automatické vyplnění sady nástrojů vlastními komponentami](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)

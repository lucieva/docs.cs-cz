---
title: Vytváření vlastních součástí naslouchajících protokolům (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- custom log listeners
- My.Application.Log object, custom log listeners
ms.assetid: 0e019115-4b25-4820-afb1-af8c6e391698
ms.openlocfilehash: 6139a1fef2b2c37bc2c8a6167febd060d8d01fb1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/04/2018
ms.locfileid: "33591648"
---
# <a name="walkthrough-creating-custom-log-listeners-visual-basic"></a>Návod: Vytváření vlastních součástí naslouchajících protokolům (Visual Basic)
Tento návod ukazuje, jak vytvořit vlastní protokol naslouchací proces a nakonfigurovat ji tak, aby naslouchala na výstupu `My.Application.Log` objektu.  
  
## <a name="getting-started"></a>Začínáme  
 Naslouchací procesy pro protokoly musí dědit z <xref:System.Diagnostics.TraceListener> třídy.  
  
#### <a name="to-create-the-listener"></a>Chcete-li vytvořit naslouchací proces  
  
-   V aplikaci, vytvořte třídu s názvem `SimpleListener` který dědí z <xref:System.Diagnostics.TraceListener>.  
  
     [!code-vb[VbVbalrMyApplicationLog#16](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/walkthrough-creating-custom-log-listeners_1.vb)]  
  
     <xref:System.Diagnostics.TraceListener.Write%2A> a <xref:System.Diagnostics.TraceListener.WriteLine%2A> volání metody, které vyžadují základní třídy, `MsgBox` pro zobrazení jejich vstupu.  
  
     <xref:System.Security.Permissions.HostProtectionAttribute> Je použit atribut <xref:System.Diagnostics.TraceListener.Write%2A> a <xref:System.Diagnostics.TraceListener.WriteLine%2A> metody tak, aby odpovídaly metody třídy base jejich atributy. <xref:System.Security.Permissions.HostProtectionAttribute> Atribut umožňuje hostiteli, který spouští kód, určit, zda kód zpřístupňuje hostitelskou ochranu synchronizace.  
  
    > [!NOTE]
    >  <xref:System.Security.Permissions.HostProtectionAttribute> Atribut je platná pouze v nespravovaných aplikacích, které jsou hostiteli modul common language runtime a které implementují ochrany hostitele, jako je SQL Server.  
  
 Zajistit, aby `My.Application.Log` používá vaše naslouchací proces protokolu důrazně by měl název sestavení, které obsahuje váš naslouchací proces protokolu.  
  
 Následující postup poskytuje několika jednoduchých kroků pro vytvoření silně pojmenované naslouchací proces protokolu sestavení. Další informace najdete v tématu [vytvoření a použití sestavení](../../../../framework/app-domains/create-and-use-strong-named-assemblies.md).  
  
#### <a name="to-strongly-name-the-log-listener-assembly"></a>Důrazně název naslouchacího procesu protokolu sestavení  
  
1.  Máte projekt vybraný v **Průzkumníku řešení**. Na **projektu** nabídce zvolte **vlastnosti**.   
  
2.  Klikněte **podpisování** kartě.  
  
3.  Vyberte **podepsání sestavení** pole.  
  
4.  Vyberte  **\<nový >** z **vyberte soubor klíče se silným názvem** rozevíracího seznamu.  
  
     **Vytvořit klíč se silným názvem** otevře se dialogové okno.  
  
5.  Zadejte název souboru klíče v **název souboru klíče** pole.  
  
6.  Zadejte heslo do **zadejte heslo** a **potvrzení hesla** polí.  
  
7.  Click **OK**.  
  
8.  Znovu sestavte aplikaci.  
  
## <a name="adding-the-listener"></a>Přidání naslouchací proces  
 Nyní, když sestavení silným názvem, budete muset určit silný název naslouchacího procesu tak, aby `My.Application.Log` používá vaše naslouchací proces protokolu.  
  
 Formát silně pojmenovaného typu je následující.  
  
 \<Název typu >, \<název sestavení >, \<číslo verze >, \<culture >, \<silné jméno >  
  
#### <a name="to-determine-the-strong-name-of-the-listener"></a>Chcete-li určit silný název naslouchacího procesu  
  
-   Následující kód ukazuje, jak určit název silně pojmenovaného typu pro `SimpleListener`.  
  
     [!code-vb[VbVbalrMyApplicationLog#17](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/walkthrough-creating-custom-log-listeners_2.vb)]  
  
     Silný název typu závisí na projektu.  
  
 Se silným názvem, můžete přidat naslouchacího procesu `My.Application.Log` naslouchání protokolu kolekce.  
  
#### <a name="to-add-the-listener-to-myapplicationlog"></a>Chcete-li přidat naslouchací proces pro My.Application.Log  
  
1.  Klikněte pravým tlačítkem na app.config v **Průzkumníku řešení** a zvolte **otevřete**.  
  
     -nebo-  
  
     Pokud je soubor app.config:  
  
    1.  Na **projektu** nabídce zvolte **přidat novou položku**.  
  
    2.  Z **přidat novou položku** dialogovém okně vyberte **konfigurační soubor aplikace**.  
  
    3.  Klikněte na tlačítko **přidat**.  
  
2.  Vyhledejte `<listeners>` v části `<source>` část s `name` atributu "DefaultSource", umístěný ve `<sources>` části. `<sources>` Je umístěna v `<system.diagnostics>` oddílem se v nejvyšší úrovně `<configuration>` části.  
  
3.  Přidejte tento element na `<listeners>` části:  
  
    ```xml  
    <add name="SimpleLog" />  
    ```  
  
4.  Vyhledejte `<sharedListeners>` v části `<system.diagnostics>` oddílem se v nejvyšší úrovně `<configuration>` části.  
  
5.  Přidejte tento element do `<sharedListeners>` části:  
  
    ```xml  
    <add name="SimpleLog" type="SimpleLogStrongName" />  
    ```  
  
     Změňte hodnotu `SimpleLogStrongName` jako silný název naslouchacího procesu.  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>  
 [Práce s protokoly aplikací](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)  
 [Postupy: Protokolování výjimek](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)  
 [Postupy: Zápis zpráv protokolu](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md)  
 [Návod: Změna místa, kam objekt My.Application.Log zapisuje informace](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)

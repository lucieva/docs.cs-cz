---
title: "Postupy: Otevření souboru přetaženého na ovládací prvek RichTextBox"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drag-and-drop [WPF], RichTextBox
- RichTextBox [WPF], drag-and-drop
- drag-and-drop [WPF], open a dropped file
ms.assetid: 6bb8bb54-f576-41db-a9a7-24102ddeb490
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f65ecaf9c6ef34176967e1ebf9134ceee195036b
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-open-a-file-that-is-dropped-on-a-richtextbox-control"></a><span data-ttu-id="dff84-102">Postupy: Otevření souboru přetaženého na ovládací prvek RichTextBox</span><span class="sxs-lookup"><span data-stu-id="dff84-102">How to: Open a File That is Dropped on a RichTextBox Control</span></span>
<span data-ttu-id="dff84-103">V [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>, a <xref:System.Windows.Documents.FlowDocument> všechny ovládací prvky mít integrovanou funkci přetažení myší.</span><span class="sxs-lookup"><span data-stu-id="dff84-103">In [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], the <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>, and <xref:System.Windows.Documents.FlowDocument> controls all have built-in drag-and-drop functionality.</span></span> <span data-ttu-id="dff84-104">Integrovanou funkci umožňuje přetažení myší textu v rámci a mezi ovládacími prvky.</span><span class="sxs-lookup"><span data-stu-id="dff84-104">The built-in functionality enables drag-and-drop of text within and between the controls.</span></span> <span data-ttu-id="dff84-105">Však není povolit otevřením souboru umístěním souboru na ovládací prvek.</span><span class="sxs-lookup"><span data-stu-id="dff84-105">However, it does not enable opening a file by dropping the file on the control.</span></span> <span data-ttu-id="dff84-106">Tyto ovládací prvky přetažení myší události také označit jako zpracování.</span><span class="sxs-lookup"><span data-stu-id="dff84-106">These controls also mark the drag-and-drop events as handled.</span></span> <span data-ttu-id="dff84-107">Ve výchozím nastavení, v důsledku toho nelze přidat svoje vlastní obslužné rutiny událostí nakonfigurovánu otevřete vynechaných soubory.</span><span class="sxs-lookup"><span data-stu-id="dff84-107">As a result, by default, you cannot add your own event handlers to provide functionality to open dropped files.</span></span>  
  
 <span data-ttu-id="dff84-108">Přidat další zpracování pro přetažení myší události v těchto ovládacích prvků, použijte <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> metoda pro přidání obslužné rutiny události pro události přetažení myší.</span><span class="sxs-lookup"><span data-stu-id="dff84-108">To add additional handling for drag-and-drop events in these controls, use the <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> method to add your event handlers for the drag-and-drop events.</span></span> <span data-ttu-id="dff84-109">Nastavte `handledEventsToo` parametr `true` má být volána pro směrované události, která již byla označena jako zpracované jiný element na trase událostí zadaná obslužná rutina.</span><span class="sxs-lookup"><span data-stu-id="dff84-109">Set the `handledEventsToo` parameter to `true` to have the specified handler be invoked for a routed event that has already been marked as handled by another element along the event route.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="dff84-110">Můžete nahradit integrované funkce přetažení myší <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>, a <xref:System.Windows.Documents.FlowDocument> zpracování verze preview událostí přetahování myší a označením události náhledu jako zpracování.</span><span class="sxs-lookup"><span data-stu-id="dff84-110">You can replace the built-in drag-and-drop functionality of <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>, and <xref:System.Windows.Documents.FlowDocument> by handling the preview versions of the drag-and-drop events and marking the preview events as handled.</span></span> <span data-ttu-id="dff84-111">Však tato akce zakáže integrovanou funkci přetažení myší a nedoporučuje se používat.</span><span class="sxs-lookup"><span data-stu-id="dff84-111">However, this will disable the built-in drag-and-drop functionality, and is not recommended.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dff84-112">Příklad</span><span class="sxs-lookup"><span data-stu-id="dff84-112">Example</span></span>  
 <span data-ttu-id="dff84-113">Následující příklad ukazuje, jak přidat obslužné rutiny pro <xref:System.Windows.DragDrop.DragOver> a <xref:System.Windows.DragDrop.Drop> události <xref:System.Windows.Controls.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="dff84-113">The following example demonstrates how to add handlers for the <xref:System.Windows.DragDrop.DragOver> and <xref:System.Windows.DragDrop.Drop> events on a <xref:System.Windows.Controls.RichTextBox>.</span></span> <span data-ttu-id="dff84-114">Tento příklad používá <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> metoda a nastaví `handledEventsToo` parametru `true` tak, aby obslužné rutiny události bude volána i když <xref:System.Windows.Controls.RichTextBox> označí tyto události, jako zpracování.</span><span class="sxs-lookup"><span data-stu-id="dff84-114">This example uses the <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> method and sets the `handledEventsToo` parameter to `true` so that the events handlers will be invoked even though the <xref:System.Windows.Controls.RichTextBox> marks these events as handled.</span></span> <span data-ttu-id="dff84-115">Kód obslužné rutiny událostí přidá funkce otevřete textový soubor, který je umístěný na <xref:System.Windows.Controls.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="dff84-115">The code in the event handlers adds functionality to open a text file that is dropped on the <xref:System.Windows.Controls.RichTextBox>.</span></span>  
  
 <span data-ttu-id="dff84-116">K testování v tomto příkladu, přetáhněte z Průzkumníka Windows na textový soubor nebo soubor formátu RTF formátovaným textem <xref:System.Windows.Controls.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="dff84-116">To test this example, drag a text file or a rich text format (RTF) file from Windows Explorer to the <xref:System.Windows.Controls.RichTextBox>.</span></span> <span data-ttu-id="dff84-117">Soubor se otevřou v <xref:System.Windows.Controls.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="dff84-117">The file will be opened in the <xref:System.Windows.Controls.RichTextBox>.</span></span> <span data-ttu-id="dff84-118">Pokud stisknutím klávesy SHIFT před vyřazování souboru, soubor se otevře jako prostý text.</span><span class="sxs-lookup"><span data-stu-id="dff84-118">If you press the SHIFT key before the dropping the file, the file will be opened as plain text.</span></span>  
  
 [!code-xaml[DragDropSnippets#RtbXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml#rtbxaml)]  
  
 [!code-csharp[DragDropSnippets#RtbHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml.cs#rtbhandlers)]
 [!code-vb[DragDropSnippets#RtbHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/dragdropsnippets/vb/mainwindow.xaml.vb#rtbhandlers)]
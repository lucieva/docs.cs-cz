---
title: "Návod: Vytvoření aplikace systému Windows s usnadněnou obsluhou"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- accessibility [Windows Forms], Windows applications
- Windows applications [Windows Forms], accessibility
- applications [Windows Forms], accessibility
ms.assetid: 654c7f2f-1586-480b-9f12-9d9b8f5cc32b
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d5b52f9f06e2a4adf401367e337be81684f661e1
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/22/2017
---
# <a name="walkthrough-creating-an-accessible-windows-based-application"></a><span data-ttu-id="80aa4-102">Návod: Vytvoření aplikace systému Windows s usnadněnou obsluhou</span><span class="sxs-lookup"><span data-stu-id="80aa4-102">Walkthrough: Creating an Accessible Windows-based Application</span></span>
<span data-ttu-id="80aa4-103">Vytváření přístupné aplikací má zásadní obchodní dopad.</span><span class="sxs-lookup"><span data-stu-id="80aa4-103">Creating an accessible application has important business implications.</span></span> <span data-ttu-id="80aa4-104">Mnoho vlády mají požadavky na usnadnění nákup softwaru.</span><span class="sxs-lookup"><span data-stu-id="80aa4-104">Many governments have accessibility regulations for software purchase.</span></span> <span data-ttu-id="80aa4-105">Logo Certified for Windows obsahuje požadavky na usnadnění přístupu.</span><span class="sxs-lookup"><span data-stu-id="80aa4-105">The Certified for Windows logo includes accessibility requirements.</span></span> <span data-ttu-id="80aa4-106">Usnadnění softwaru se vztahuje odhadované 30 milionů obyvatele samostatně, USA, kolika z nich potenciální zákazníky.</span><span class="sxs-lookup"><span data-stu-id="80aa4-106">An estimated 30 million residents of the U.S. alone, many of them potential customers, are affected by the accessibility of software.</span></span>  
  
 <span data-ttu-id="80aa4-107">Tento názorný postup vyřeší pět požadavky na usnadnění přístupu pro logo Certified for Windows.</span><span class="sxs-lookup"><span data-stu-id="80aa4-107">This walkthrough will address the five accessibility requirements for the Certified for Windows logo.</span></span> <span data-ttu-id="80aa4-108">Dostupné aplikace se podle těchto požadavků:</span><span class="sxs-lookup"><span data-stu-id="80aa4-108">According to these requirements, an accessible application will:</span></span>  
  
-   <span data-ttu-id="80aa4-109">Podporovat velikost ovládacích panelů, barvy, písma a zadejte nastavení.</span><span class="sxs-lookup"><span data-stu-id="80aa4-109">Support Control Panel size, color, font, and input settings.</span></span> <span data-ttu-id="80aa4-110">Panel nabídek, záhlaví, ohraničení a stavového řádku změní všechny velikost sami když uživatel změní nastavení ovládacího panelu.</span><span class="sxs-lookup"><span data-stu-id="80aa4-110">The menu bar, title bar, borders, and status bar will all resize themselves when the user changes the control panel settings.</span></span> <span data-ttu-id="80aa4-111">V této aplikaci se nevyžadují žádné další změny ovládací prvky nebo kódu.</span><span class="sxs-lookup"><span data-stu-id="80aa4-111">No additional changes to the controls or code are required in this application.</span></span>  
  
-   <span data-ttu-id="80aa4-112">Podpora režimu vysokého kontrastu.</span><span class="sxs-lookup"><span data-stu-id="80aa4-112">Support High Contrast mode.</span></span>  
  
-   <span data-ttu-id="80aa4-113">Zadejte zdokumentovaných klávesnice přístup ke všem funkcím.</span><span class="sxs-lookup"><span data-stu-id="80aa4-113">Provide documented keyboard access to all features.</span></span>  
  
-   <span data-ttu-id="80aa4-114">Vystavení umístění fokus klávesnice vizuálně a programově.</span><span class="sxs-lookup"><span data-stu-id="80aa4-114">Expose location of the keyboard focus visually and programmatically.</span></span>  
  
-   <span data-ttu-id="80aa4-115">Vyhněte se předávání důležitých informací zvukovou samostatně.</span><span class="sxs-lookup"><span data-stu-id="80aa4-115">Avoid conveying important information by sound alone.</span></span>  
  
 <span data-ttu-id="80aa4-116">Další informace najdete v tématu [prostředky pro navrhování přístupné aplikace](/visualstudio/ide/reference/resources-for-designing-accessible-applications).</span><span class="sxs-lookup"><span data-stu-id="80aa4-116">For more information, see [Resources for Designing Accessible Applications](/visualstudio/ide/reference/resources-for-designing-accessible-applications).</span></span>  
  
 <span data-ttu-id="80aa4-117">Informace na podporu různých rozložení klávesnice najdete v tématu [osvědčené postupy pro vývoj aplikací připravených](../../../../docs/standard/globalization-localization/best-practices-for-developing-world-ready-apps.md).</span><span class="sxs-lookup"><span data-stu-id="80aa4-117">For information on supporting varying keyboard layouts, see [Best Practices for Developing World-Ready Applications](../../../../docs/standard/globalization-localization/best-practices-for-developing-world-ready-apps.md).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="80aa4-118">Vytvoření projektu</span><span class="sxs-lookup"><span data-stu-id="80aa4-118">Creating the Project</span></span>  
 <span data-ttu-id="80aa4-119">Tento návod vytvoří uživatelské rozhraní pro aplikaci, která přebírá pizza objednávky.</span><span class="sxs-lookup"><span data-stu-id="80aa4-119">This walkthrough creates the user interface for an application that takes pizza orders.</span></span> <span data-ttu-id="80aa4-120">Skládá se z <xref:System.Windows.Forms.TextBox> pro název zákazníka, <xref:System.Windows.Forms.RadioButton> skupina a vyberte velikost pizza <xref:System.Windows.Forms.CheckedListBox> pro výběr toppings, dvou ovládacích prvků tlačítko s názvem bez přípony pořadí a zrušit a nabídky pomocí příkazu pro ukončení.</span><span class="sxs-lookup"><span data-stu-id="80aa4-120">It consists of a <xref:System.Windows.Forms.TextBox> for the customer's name, a <xref:System.Windows.Forms.RadioButton> group to select the pizza size, a <xref:System.Windows.Forms.CheckedListBox> for selecting the toppings, two Button controls labeled Order and Cancel, and a Menu with an Exit command.</span></span>  
  
 <span data-ttu-id="80aa4-121">Uživatel zadá název zákazníka, velikost pizza a toppings potřeby.</span><span class="sxs-lookup"><span data-stu-id="80aa4-121">The user enters the customer's name, the size of the pizza, and the toppings desired.</span></span> <span data-ttu-id="80aa4-122">Když uživatel klikne na tlačítko pořadí, souhrn pořadí a jeho náklady jsou zobrazeny v okně se zprávou a ovládací prvky jsou nezaškrtnuté a připravené pro další pořadí.</span><span class="sxs-lookup"><span data-stu-id="80aa4-122">When the user clicks the Order button, a summary of the order and its cost are displayed in a message box and the controls are cleared and ready for the next order.</span></span> <span data-ttu-id="80aa4-123">Když uživatel klikne na tlačítko Storno, ovládací prvky jsou nezaškrtnuté a připravené pro další pořadí.</span><span class="sxs-lookup"><span data-stu-id="80aa4-123">When the user clicks the Cancel button, the controls are cleared and ready for the next order.</span></span> <span data-ttu-id="80aa4-124">Když uživatel klikne na položku nabídky ukončení, program se ukončí.</span><span class="sxs-lookup"><span data-stu-id="80aa4-124">When the user clicks the Exit menu item, the program closes.</span></span>  
  
 <span data-ttu-id="80aa4-125">Zvýraznění tohoto návodu není kód pro maloobchodní pořadí systému, ale usnadnění uživatelského rozhraní.</span><span class="sxs-lookup"><span data-stu-id="80aa4-125">The emphasis of this walkthrough is not the code for a retail order system, but the accessibility of the user interface.</span></span> <span data-ttu-id="80aa4-126">Průvodce ukazuje, že funkce pro usnadnění přístupu několik často používané ovládací prvky, včetně tlačítka, přepínače, textových polí a popisky.</span><span class="sxs-lookup"><span data-stu-id="80aa4-126">The walkthrough demonstrates the accessibility features of several frequently used controls, including buttons, radio buttons, text boxes, and labels.</span></span>  
  
#### <a name="to-begin-making-the-application"></a><span data-ttu-id="80aa4-127">Chcete-li začít vytvářet aplikace</span><span class="sxs-lookup"><span data-stu-id="80aa4-127">To begin making the application</span></span>  
  
-   <span data-ttu-id="80aa4-128">Vytvoření nové aplikace Windows v [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] nebo [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="80aa4-128">Create a new Windows Application in [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)].</span></span> <span data-ttu-id="80aa4-129">Název projektu **PizzaOrder**.</span><span class="sxs-lookup"><span data-stu-id="80aa4-129">Name the project **PizzaOrder**.</span></span> <span data-ttu-id="80aa4-130">(Podrobnosti najdete v tématu [vytváření nových řešení a projekty](/visualstudio/ide/creating-solutions-and-projects).)</span><span class="sxs-lookup"><span data-stu-id="80aa4-130">(For details see [Creating New Solutions and Projects](/visualstudio/ide/creating-solutions-and-projects).)</span></span>  
  
## <a name="adding-the-controls-to-the-form"></a><span data-ttu-id="80aa4-131">Přidání ovládacích prvků formuláře</span><span class="sxs-lookup"><span data-stu-id="80aa4-131">Adding the Controls to the Form</span></span>  
 <span data-ttu-id="80aa4-132">Při přidávání ovládacích prvků na formuláři, mějte na paměti následující pokyny, aby se aplikace dostupné:</span><span class="sxs-lookup"><span data-stu-id="80aa4-132">When adding the controls to a form, keep in mind the following guidelines to make an accessible application:</span></span>  
  
-   <span data-ttu-id="80aa4-133">Nastavte <xref:System.Windows.Forms.Control.AccessibleDescription%2A> a <xref:System.Windows.Forms.Control.AccessibleName%2A> vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="80aa4-133">Set the <xref:System.Windows.Forms.Control.AccessibleDescription%2A> and <xref:System.Windows.Forms.Control.AccessibleName%2A> properties.</span></span> <span data-ttu-id="80aa4-134">V tomto příkladu výchozí nastavení <xref:System.Windows.Forms.Control.AccessibleRole%2A> je dostačující.</span><span class="sxs-lookup"><span data-stu-id="80aa4-134">In this example, the Default setting for the <xref:System.Windows.Forms.Control.AccessibleRole%2A> is sufficient.</span></span> <span data-ttu-id="80aa4-135">Další informace o vlastnostech usnadnění přístupu najdete v tématu [poskytuje informace o usnadnění pro ovládací prvky na formuláři Windows](../../../../docs/framework/winforms/controls/providing-accessibility-information-for-controls-on-a-windows-form.md).</span><span class="sxs-lookup"><span data-stu-id="80aa4-135">For more information on the accessibility properties, see [Providing Accessibility Information for Controls on a Windows Form](../../../../docs/framework/winforms/controls/providing-accessibility-information-for-controls-on-a-windows-form.md).</span></span>  
  
-   <span data-ttu-id="80aa4-136">Nastavení velikosti písma 10 bodů nebo větší.</span><span class="sxs-lookup"><span data-stu-id="80aa4-136">Set the font size to 10 points or larger.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="80aa4-137">Pokud nastavíte velikost písma formuláře na 10, při spuštění, bude mít všechny ovládací prvky, později přidané do formuláře velikost písma 10.</span><span class="sxs-lookup"><span data-stu-id="80aa4-137">If you set the font size of the form to 10 when you start, then all controls subsequently added to the form will have a font size of 10.</span></span>  
  
-   <span data-ttu-id="80aa4-138">Ujistěte se, že libovolný ovládací prvek popisek, který popisuje ovládacím prvku TextBox okamžitě předchází TextBox – ovládací prvek v pořadí.</span><span class="sxs-lookup"><span data-stu-id="80aa4-138">Make sure any Label control that describes a TextBox control immediately precedes the TextBox control in the tab order.</span></span>  
  
-   <span data-ttu-id="80aa4-139">Přidat přístupový klíč, pomocí znaku "&" na <xref:System.Windows.Forms.Control.Text%2A> vlastnosti libovolného ovládacího prvku, uživatel může chtít přejděte do.</span><span class="sxs-lookup"><span data-stu-id="80aa4-139">Add an access key, using the "&" character, to the <xref:System.Windows.Forms.Control.Text%2A> property of any control the user may want to navigate to.</span></span>  
  
-   <span data-ttu-id="80aa4-140">Přidat přístupový klíč, pomocí znaku "&", položky <xref:System.Windows.Forms.Control.Text%2A> vlastnost štítek, který předchází ovládacího prvku, který uživatel může chtít přejděte do.</span><span class="sxs-lookup"><span data-stu-id="80aa4-140">Add an access key, using the "&" character, to the <xref:System.Windows.Forms.Control.Text%2A> property of the label that precedes a control that the user may want to navigate to.</span></span> <span data-ttu-id="80aa4-141">Nastavit zobrazí popisky <xref:System.Windows.Forms.Label.UseMnemonic%2A> vlastnost `true`, tak, aby fokus je nastavena na další ovládací prvek v pořadí, když uživatel stiskne přístupový klíč.</span><span class="sxs-lookup"><span data-stu-id="80aa4-141">Set the labels' <xref:System.Windows.Forms.Label.UseMnemonic%2A> property to `true`, so that the focus is set to the next control in the tab order when the user presses the access key.</span></span>  
  
-   <span data-ttu-id="80aa4-142">Přidejte přístupové klíče pro všechny položky nabídky.</span><span class="sxs-lookup"><span data-stu-id="80aa4-142">Add access keys to all menu items.</span></span>  
  
#### <a name="to-make-your-windows-application-accessible"></a><span data-ttu-id="80aa4-143">Pro zpřístupnění aplikací pro Windows</span><span class="sxs-lookup"><span data-stu-id="80aa4-143">To make your Windows Application accessible</span></span>  
  
-   <span data-ttu-id="80aa4-144">Přidání ovládacích prvků formuláře a nastavte vlastnosti, jak je popsáno níže.</span><span class="sxs-lookup"><span data-stu-id="80aa4-144">Add the controls to the form and set the properties as described below.</span></span> <span data-ttu-id="80aa4-145">Zobrazí se obrázek na konci v tabulce pro model, jak k uspořádání ovládacích prvků na formuláři.</span><span class="sxs-lookup"><span data-stu-id="80aa4-145">See the picture at the end of the table for a model of how to arrange the controls on the form.</span></span>  
  
    |<span data-ttu-id="80aa4-146">Objekt</span><span class="sxs-lookup"><span data-stu-id="80aa4-146">Object</span></span>|<span data-ttu-id="80aa4-147">Vlastnost</span><span class="sxs-lookup"><span data-stu-id="80aa4-147">Property</span></span>|<span data-ttu-id="80aa4-148">Hodnota</span><span class="sxs-lookup"><span data-stu-id="80aa4-148">Value</span></span>|  
    |------------|--------------|-----------|  
    |<span data-ttu-id="80aa4-149">Form1</span><span class="sxs-lookup"><span data-stu-id="80aa4-149">Form1</span></span>|<span data-ttu-id="80aa4-150">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="80aa4-150">AccessibleDescription</span></span>|<span data-ttu-id="80aa4-151">Pořadí formuláře</span><span class="sxs-lookup"><span data-stu-id="80aa4-151">Order form</span></span>|  
    ||<span data-ttu-id="80aa4-152">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="80aa4-152">AccessibleName</span></span>|<span data-ttu-id="80aa4-153">Pořadí formuláře</span><span class="sxs-lookup"><span data-stu-id="80aa4-153">Order form</span></span>|  
    ||<span data-ttu-id="80aa4-154">Velikost písma</span><span class="sxs-lookup"><span data-stu-id="80aa4-154">Font Size</span></span>|<span data-ttu-id="80aa4-155">10</span><span class="sxs-lookup"><span data-stu-id="80aa4-155">10</span></span>|  
    ||<span data-ttu-id="80aa4-156">Text</span><span class="sxs-lookup"><span data-stu-id="80aa4-156">Text</span></span>|<span data-ttu-id="80aa4-157">Formulář pro objednání pizzy</span><span class="sxs-lookup"><span data-stu-id="80aa4-157">Pizza Order Form</span></span>|  
    |<span data-ttu-id="80aa4-158">PictureBox</span><span class="sxs-lookup"><span data-stu-id="80aa4-158">PictureBox</span></span>|<span data-ttu-id="80aa4-159">Název</span><span class="sxs-lookup"><span data-stu-id="80aa4-159">Name</span></span>|<span data-ttu-id="80aa4-160">Logo</span><span class="sxs-lookup"><span data-stu-id="80aa4-160">logo</span></span>|  
    ||<span data-ttu-id="80aa4-161">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="80aa4-161">AccessibleDescription</span></span>|<span data-ttu-id="80aa4-162">Řez pizza</span><span class="sxs-lookup"><span data-stu-id="80aa4-162">A slice of pizza</span></span>|  
    ||<span data-ttu-id="80aa4-163">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="80aa4-163">AccessibleName</span></span>|<span data-ttu-id="80aa4-164">Logo společnosti</span><span class="sxs-lookup"><span data-stu-id="80aa4-164">Company logo</span></span>|  
    ||<span data-ttu-id="80aa4-165">Image</span><span class="sxs-lookup"><span data-stu-id="80aa4-165">Image</span></span>|<span data-ttu-id="80aa4-166">Všechny ikony nebo rastrového obrázku</span><span class="sxs-lookup"><span data-stu-id="80aa4-166">Any icon or bitmap</span></span>|  
    |<span data-ttu-id="80aa4-167">Popisek</span><span class="sxs-lookup"><span data-stu-id="80aa4-167">Label</span></span>|<span data-ttu-id="80aa4-168">Název</span><span class="sxs-lookup"><span data-stu-id="80aa4-168">Name</span></span>|<span data-ttu-id="80aa4-169">companyLabel</span><span class="sxs-lookup"><span data-stu-id="80aa4-169">companyLabel</span></span>|  
    ||<span data-ttu-id="80aa4-170">Text</span><span class="sxs-lookup"><span data-stu-id="80aa4-170">Text</span></span>|<span data-ttu-id="80aa4-171">Dobrý Pizza</span><span class="sxs-lookup"><span data-stu-id="80aa4-171">Good Pizza</span></span>|  
    ||<span data-ttu-id="80aa4-172">Pořadové číslo prvku</span><span class="sxs-lookup"><span data-stu-id="80aa4-172">TabIndex</span></span>|<span data-ttu-id="80aa4-173">1</span><span class="sxs-lookup"><span data-stu-id="80aa4-173">1</span></span>|  
    ||<span data-ttu-id="80aa4-174">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="80aa4-174">AccessibleDescription</span></span>|<span data-ttu-id="80aa4-175">Název společnosti</span><span class="sxs-lookup"><span data-stu-id="80aa4-175">Company name</span></span>|  
    ||<span data-ttu-id="80aa4-176">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="80aa4-176">AccessibleName</span></span>|<span data-ttu-id="80aa4-177">Název společnosti</span><span class="sxs-lookup"><span data-stu-id="80aa4-177">Company name</span></span>|  
    ||<span data-ttu-id="80aa4-178">Barva pozadí</span><span class="sxs-lookup"><span data-stu-id="80aa4-178">Backcolor</span></span>|<span data-ttu-id="80aa4-179">modrá</span><span class="sxs-lookup"><span data-stu-id="80aa4-179">Blue</span></span>|  
    ||<span data-ttu-id="80aa4-180">ForeColor</span><span class="sxs-lookup"><span data-stu-id="80aa4-180">Forecolor</span></span>|<span data-ttu-id="80aa4-181">žlutý</span><span class="sxs-lookup"><span data-stu-id="80aa4-181">Yellow</span></span>|  
    ||<span data-ttu-id="80aa4-182">Velikost písma</span><span class="sxs-lookup"><span data-stu-id="80aa4-182">Font size</span></span>|<span data-ttu-id="80aa4-183">18</span><span class="sxs-lookup"><span data-stu-id="80aa4-183">18</span></span>|  
    |<span data-ttu-id="80aa4-184">Popisek</span><span class="sxs-lookup"><span data-stu-id="80aa4-184">Label</span></span>|<span data-ttu-id="80aa4-185">Název</span><span class="sxs-lookup"><span data-stu-id="80aa4-185">Name</span></span>|<span data-ttu-id="80aa4-186">customerLabel</span><span class="sxs-lookup"><span data-stu-id="80aa4-186">customerLabel</span></span>|  
    ||<span data-ttu-id="80aa4-187">Text</span><span class="sxs-lookup"><span data-stu-id="80aa4-187">Text</span></span>|<span data-ttu-id="80aa4-188">& název</span><span class="sxs-lookup"><span data-stu-id="80aa4-188">&Name</span></span>|  
    ||<span data-ttu-id="80aa4-189">Pořadové číslo prvku</span><span class="sxs-lookup"><span data-stu-id="80aa4-189">TabIndex</span></span>|<span data-ttu-id="80aa4-190">2</span><span class="sxs-lookup"><span data-stu-id="80aa4-190">2</span></span>|  
    ||<span data-ttu-id="80aa4-191">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="80aa4-191">AccessibleDescription</span></span>|<span data-ttu-id="80aa4-192">Popisek názvu zákazníka</span><span class="sxs-lookup"><span data-stu-id="80aa4-192">Customer name label</span></span>|  
    ||<span data-ttu-id="80aa4-193">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="80aa4-193">AccessibleName</span></span>|<span data-ttu-id="80aa4-194">Popisek názvu zákazníka</span><span class="sxs-lookup"><span data-stu-id="80aa4-194">Customer name label</span></span>|  
    ||<span data-ttu-id="80aa4-195">Usemnemonic –</span><span class="sxs-lookup"><span data-stu-id="80aa4-195">UseMnemonic</span></span>|<span data-ttu-id="80aa4-196">Hodnota TRUE</span><span class="sxs-lookup"><span data-stu-id="80aa4-196">True</span></span>|  
    |<span data-ttu-id="80aa4-197">TextBox</span><span class="sxs-lookup"><span data-stu-id="80aa4-197">TextBox</span></span>|<span data-ttu-id="80aa4-198">Název</span><span class="sxs-lookup"><span data-stu-id="80aa4-198">Name</span></span>|<span data-ttu-id="80aa4-199">JménoZákazníka</span><span class="sxs-lookup"><span data-stu-id="80aa4-199">customerName</span></span>|  
    ||<span data-ttu-id="80aa4-200">Text</span><span class="sxs-lookup"><span data-stu-id="80aa4-200">Text</span></span>|<span data-ttu-id="80aa4-201">(žádný)</span><span class="sxs-lookup"><span data-stu-id="80aa4-201">(none)</span></span>|  
    ||<span data-ttu-id="80aa4-202">Pořadové číslo prvku</span><span class="sxs-lookup"><span data-stu-id="80aa4-202">TabIndex</span></span>|<span data-ttu-id="80aa4-203">3</span><span class="sxs-lookup"><span data-stu-id="80aa4-203">3</span></span>|  
    ||<span data-ttu-id="80aa4-204">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="80aa4-204">AccessibleDescription</span></span>|<span data-ttu-id="80aa4-205">Jméno zákazníka</span><span class="sxs-lookup"><span data-stu-id="80aa4-205">Customer name</span></span>|  
    ||<span data-ttu-id="80aa4-206">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="80aa4-206">AccessibleName</span></span>|<span data-ttu-id="80aa4-207">Jméno zákazníka</span><span class="sxs-lookup"><span data-stu-id="80aa4-207">Customer name</span></span>|  
    |<span data-ttu-id="80aa4-208">GroupBox</span><span class="sxs-lookup"><span data-stu-id="80aa4-208">GroupBox</span></span>|<span data-ttu-id="80aa4-209">Název</span><span class="sxs-lookup"><span data-stu-id="80aa4-209">Name</span></span>|<span data-ttu-id="80aa4-210">sizeOptions</span><span class="sxs-lookup"><span data-stu-id="80aa4-210">sizeOptions</span></span>|  
    ||<span data-ttu-id="80aa4-211">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="80aa4-211">AccessibleDescription</span></span>|<span data-ttu-id="80aa4-212">Možnosti velikosti pizza</span><span class="sxs-lookup"><span data-stu-id="80aa4-212">Pizza size options</span></span>|  
    ||<span data-ttu-id="80aa4-213">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="80aa4-213">AccessibleName</span></span>|<span data-ttu-id="80aa4-214">Možnosti velikosti pizza</span><span class="sxs-lookup"><span data-stu-id="80aa4-214">Pizza size options</span></span>|  
    ||<span data-ttu-id="80aa4-215">Text</span><span class="sxs-lookup"><span data-stu-id="80aa4-215">Text</span></span>|<span data-ttu-id="80aa4-216">Velikost pizza</span><span class="sxs-lookup"><span data-stu-id="80aa4-216">Pizza size</span></span>|  
    ||<span data-ttu-id="80aa4-217">Pořadové číslo prvku</span><span class="sxs-lookup"><span data-stu-id="80aa4-217">TabIndex</span></span>|<span data-ttu-id="80aa4-218">4</span><span class="sxs-lookup"><span data-stu-id="80aa4-218">4</span></span>|  
    |<span data-ttu-id="80aa4-219">RadioButton</span><span class="sxs-lookup"><span data-stu-id="80aa4-219">RadioButton</span></span>|<span data-ttu-id="80aa4-220">Název</span><span class="sxs-lookup"><span data-stu-id="80aa4-220">Name</span></span>|<span data-ttu-id="80aa4-221">smallPizza</span><span class="sxs-lookup"><span data-stu-id="80aa4-221">smallPizza</span></span>|  
    ||<span data-ttu-id="80aa4-222">Text</span><span class="sxs-lookup"><span data-stu-id="80aa4-222">Text</span></span>|<span data-ttu-id="80aa4-223">& malé $6.00</span><span class="sxs-lookup"><span data-stu-id="80aa4-223">&Small $6.00</span></span>|  
    ||<span data-ttu-id="80aa4-224">Zaškrtnutí</span><span class="sxs-lookup"><span data-stu-id="80aa4-224">Checked</span></span>|<span data-ttu-id="80aa4-225">Hodnota TRUE</span><span class="sxs-lookup"><span data-stu-id="80aa4-225">True</span></span>|  
    ||<span data-ttu-id="80aa4-226">Pořadové číslo prvku</span><span class="sxs-lookup"><span data-stu-id="80aa4-226">TabIndex</span></span>|<span data-ttu-id="80aa4-227">0</span><span class="sxs-lookup"><span data-stu-id="80aa4-227">0</span></span>|  
    ||<span data-ttu-id="80aa4-228">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="80aa4-228">AccessibleDescription</span></span>|<span data-ttu-id="80aa4-229">Malé pizza</span><span class="sxs-lookup"><span data-stu-id="80aa4-229">Small pizza</span></span>|  
    ||<span data-ttu-id="80aa4-230">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="80aa4-230">AccessibleName</span></span>|<span data-ttu-id="80aa4-231">Malé pizza</span><span class="sxs-lookup"><span data-stu-id="80aa4-231">Small pizza</span></span>|  
    |<span data-ttu-id="80aa4-232">RadioButton</span><span class="sxs-lookup"><span data-stu-id="80aa4-232">RadioButton</span></span>|<span data-ttu-id="80aa4-233">Název</span><span class="sxs-lookup"><span data-stu-id="80aa4-233">Name</span></span>|<span data-ttu-id="80aa4-234">largePizza</span><span class="sxs-lookup"><span data-stu-id="80aa4-234">largePizza</span></span>|  
    ||<span data-ttu-id="80aa4-235">Text</span><span class="sxs-lookup"><span data-stu-id="80aa4-235">Text</span></span>|<span data-ttu-id="80aa4-236">& velké 10,00 USD</span><span class="sxs-lookup"><span data-stu-id="80aa4-236">&Large $10.00</span></span>|  
    ||<span data-ttu-id="80aa4-237">Pořadové číslo prvku</span><span class="sxs-lookup"><span data-stu-id="80aa4-237">TabIndex</span></span>|<span data-ttu-id="80aa4-238">1</span><span class="sxs-lookup"><span data-stu-id="80aa4-238">1</span></span>|  
    ||<span data-ttu-id="80aa4-239">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="80aa4-239">AccessibleDescription</span></span>|<span data-ttu-id="80aa4-240">Velké pizza</span><span class="sxs-lookup"><span data-stu-id="80aa4-240">Large pizza</span></span>|  
    ||<span data-ttu-id="80aa4-241">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="80aa4-241">AccessibleName</span></span>|<span data-ttu-id="80aa4-242">Velké pizza</span><span class="sxs-lookup"><span data-stu-id="80aa4-242">Large pizza</span></span>|  
    |<span data-ttu-id="80aa4-243">Popisek</span><span class="sxs-lookup"><span data-stu-id="80aa4-243">Label</span></span>|<span data-ttu-id="80aa4-244">Název</span><span class="sxs-lookup"><span data-stu-id="80aa4-244">Name</span></span>|<span data-ttu-id="80aa4-245">toppingsLabel</span><span class="sxs-lookup"><span data-stu-id="80aa4-245">toppingsLabel</span></span>|  
    ||<span data-ttu-id="80aa4-246">Text</span><span class="sxs-lookup"><span data-stu-id="80aa4-246">Text</span></span>|<span data-ttu-id="80aa4-247">& toppings ($0,75 každý)</span><span class="sxs-lookup"><span data-stu-id="80aa4-247">&Toppings ($0.75 each)</span></span>|  
    ||<span data-ttu-id="80aa4-248">Pořadové číslo prvku</span><span class="sxs-lookup"><span data-stu-id="80aa4-248">TabIndex</span></span>|<span data-ttu-id="80aa4-249">5</span><span class="sxs-lookup"><span data-stu-id="80aa4-249">5</span></span>|  
    ||<span data-ttu-id="80aa4-250">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="80aa4-250">AccessibleDescription</span></span>|<span data-ttu-id="80aa4-251">Popisek toppings</span><span class="sxs-lookup"><span data-stu-id="80aa4-251">Toppings label</span></span>|  
    ||<span data-ttu-id="80aa4-252">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="80aa4-252">AccessibleName</span></span>|<span data-ttu-id="80aa4-253">Popisek toppings</span><span class="sxs-lookup"><span data-stu-id="80aa4-253">Toppings label</span></span>|  
    ||<span data-ttu-id="80aa4-254">Usemnemonic –</span><span class="sxs-lookup"><span data-stu-id="80aa4-254">UseMnemonic</span></span>|<span data-ttu-id="80aa4-255">Hodnota TRUE</span><span class="sxs-lookup"><span data-stu-id="80aa4-255">True</span></span>|  
    |<span data-ttu-id="80aa4-256">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="80aa4-256">CheckedListBox</span></span>|<span data-ttu-id="80aa4-257">Název</span><span class="sxs-lookup"><span data-stu-id="80aa4-257">Name</span></span>|<span data-ttu-id="80aa4-258">toppings</span><span class="sxs-lookup"><span data-stu-id="80aa4-258">toppings</span></span>|  
    ||<span data-ttu-id="80aa4-259">Pořadové číslo prvku</span><span class="sxs-lookup"><span data-stu-id="80aa4-259">TabIndex</span></span>|<span data-ttu-id="80aa4-260">6</span><span class="sxs-lookup"><span data-stu-id="80aa4-260">6</span></span>|  
    ||<span data-ttu-id="80aa4-261">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="80aa4-261">AccessibleDescription</span></span>|<span data-ttu-id="80aa4-262">K dispozici toppings</span><span class="sxs-lookup"><span data-stu-id="80aa4-262">Available toppings</span></span>|  
    ||<span data-ttu-id="80aa4-263">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="80aa4-263">AccessibleName</span></span>|<span data-ttu-id="80aa4-264">K dispozici toppings</span><span class="sxs-lookup"><span data-stu-id="80aa4-264">Available toppings</span></span>|  
    ||<span data-ttu-id="80aa4-265">Položky</span><span class="sxs-lookup"><span data-stu-id="80aa4-265">Items</span></span>|<span data-ttu-id="80aa4-266">Pepperoni salám, hub</span><span class="sxs-lookup"><span data-stu-id="80aa4-266">Pepperoni, Sausage, Mushrooms</span></span>|  
    |<span data-ttu-id="80aa4-267">Tlačítko</span><span class="sxs-lookup"><span data-stu-id="80aa4-267">Button</span></span>|<span data-ttu-id="80aa4-268">Název</span><span class="sxs-lookup"><span data-stu-id="80aa4-268">Name</span></span>|<span data-ttu-id="80aa4-269">pořadí</span><span class="sxs-lookup"><span data-stu-id="80aa4-269">order</span></span>|  
    ||<span data-ttu-id="80aa4-270">Text</span><span class="sxs-lookup"><span data-stu-id="80aa4-270">Text</span></span>|<span data-ttu-id="80aa4-271">& pořadí</span><span class="sxs-lookup"><span data-stu-id="80aa4-271">&Order</span></span>|  
    ||<span data-ttu-id="80aa4-272">Pořadové číslo prvku</span><span class="sxs-lookup"><span data-stu-id="80aa4-272">TabIndex</span></span>|<span data-ttu-id="80aa4-273">7</span><span class="sxs-lookup"><span data-stu-id="80aa4-273">7</span></span>|  
    ||<span data-ttu-id="80aa4-274">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="80aa4-274">AccessibleDescription</span></span>|<span data-ttu-id="80aa4-275">Celkový počet pořadí</span><span class="sxs-lookup"><span data-stu-id="80aa4-275">Total the order</span></span>|  
    ||<span data-ttu-id="80aa4-276">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="80aa4-276">AccessibleName</span></span>|<span data-ttu-id="80aa4-277">Celkové pořadí</span><span class="sxs-lookup"><span data-stu-id="80aa4-277">Total order</span></span>|  
    |<span data-ttu-id="80aa4-278">Tlačítko</span><span class="sxs-lookup"><span data-stu-id="80aa4-278">Button</span></span>|<span data-ttu-id="80aa4-279">Název</span><span class="sxs-lookup"><span data-stu-id="80aa4-279">Name</span></span>|<span data-ttu-id="80aa4-280">Zrušit</span><span class="sxs-lookup"><span data-stu-id="80aa4-280">cancel</span></span>|  
    ||<span data-ttu-id="80aa4-281">Text</span><span class="sxs-lookup"><span data-stu-id="80aa4-281">Text</span></span>|<span data-ttu-id="80aa4-282">& Zrušit</span><span class="sxs-lookup"><span data-stu-id="80aa4-282">&Cancel</span></span>|  
    ||<span data-ttu-id="80aa4-283">Pořadové číslo prvku</span><span class="sxs-lookup"><span data-stu-id="80aa4-283">TabIndex</span></span>|<span data-ttu-id="80aa4-284">8</span><span class="sxs-lookup"><span data-stu-id="80aa4-284">8</span></span>|  
    ||<span data-ttu-id="80aa4-285">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="80aa4-285">AccessibleDescription</span></span>|<span data-ttu-id="80aa4-286">Zrušit pořadí</span><span class="sxs-lookup"><span data-stu-id="80aa4-286">Cancel the order</span></span>|  
    ||<span data-ttu-id="80aa4-287">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="80aa4-287">AccessibleName</span></span>|<span data-ttu-id="80aa4-288">Zrušit pořadí</span><span class="sxs-lookup"><span data-stu-id="80aa4-288">Cancel order</span></span>|  
    |<span data-ttu-id="80aa4-289">MainMenu</span><span class="sxs-lookup"><span data-stu-id="80aa4-289">MainMenu</span></span>|<span data-ttu-id="80aa4-290">Název</span><span class="sxs-lookup"><span data-stu-id="80aa4-290">Name</span></span>|<span data-ttu-id="80aa4-291">theMainMenu</span><span class="sxs-lookup"><span data-stu-id="80aa4-291">theMainMenu</span></span>|  
    |<span data-ttu-id="80aa4-292">Položka nabídky</span><span class="sxs-lookup"><span data-stu-id="80aa4-292">MenuItem</span></span>|<span data-ttu-id="80aa4-293">Název</span><span class="sxs-lookup"><span data-stu-id="80aa4-293">Name</span></span>|<span data-ttu-id="80aa4-294">fileCommands</span><span class="sxs-lookup"><span data-stu-id="80aa4-294">fileCommands</span></span>|  
    ||<span data-ttu-id="80aa4-295">Text</span><span class="sxs-lookup"><span data-stu-id="80aa4-295">Text</span></span>|<span data-ttu-id="80aa4-296">& souboru</span><span class="sxs-lookup"><span data-stu-id="80aa4-296">&File</span></span>|  
    |<span data-ttu-id="80aa4-297">Položka nabídky</span><span class="sxs-lookup"><span data-stu-id="80aa4-297">MenuItem</span></span>|<span data-ttu-id="80aa4-298">Název</span><span class="sxs-lookup"><span data-stu-id="80aa4-298">Name</span></span>|<span data-ttu-id="80aa4-299">exitApp</span><span class="sxs-lookup"><span data-stu-id="80aa4-299">exitApp</span></span>|  
    ||<span data-ttu-id="80aa4-300">Text</span><span class="sxs-lookup"><span data-stu-id="80aa4-300">Text</span></span>|<span data-ttu-id="80aa4-301">& Konec</span><span class="sxs-lookup"><span data-stu-id="80aa4-301">E&xit</span></span>|  
  
     <span data-ttu-id="80aa4-302">![Formulář pro objednání pizzy](../../../../docs/framework/winforms/advanced/media/vbpizzaorderform.gif "vbPizzaOrderForm")</span><span class="sxs-lookup"><span data-stu-id="80aa4-302">![Pizza Order Form](../../../../docs/framework/winforms/advanced/media/vbpizzaorderform.gif "vbPizzaOrderForm")</span></span>  
<span data-ttu-id="80aa4-303">Formulář bude vypadat přibližně takto:</span><span class="sxs-lookup"><span data-stu-id="80aa4-303">Your form will look something like the following:</span></span>  
  
## <a name="supporting-high-contrast-mode"></a><span data-ttu-id="80aa4-304">Podpora režimu vysokého kontrastu</span><span class="sxs-lookup"><span data-stu-id="80aa4-304">Supporting High Contrast Mode</span></span>  
 <span data-ttu-id="80aa4-305">V režimu Vysoký kontrast je nastavení systému Windows, který zlepšuje čitelnosti pomocí kontrastní barvy a velikosti písma, které jsou užitečné pro uživatele se zrakovým postižením.</span><span class="sxs-lookup"><span data-stu-id="80aa4-305">High Contrast mode is a Windows system setting that improves readability by using contrasting colors and font sizes that are beneficial for visually impaired users.</span></span> <span data-ttu-id="80aa4-306"><xref:System.Windows.Forms.SystemInformation.HighContrast%2A> Vlastnost je poskytována k určení, zda je nastaven režimu vysokého kontrastu.</span><span class="sxs-lookup"><span data-stu-id="80aa4-306">The <xref:System.Windows.Forms.SystemInformation.HighContrast%2A> property is provided to determine whether the High Contrast mode is set.</span></span>  
  
 <span data-ttu-id="80aa4-307">Pokud je SystemInformation.HighContrast `true`, by měla aplikace:</span><span class="sxs-lookup"><span data-stu-id="80aa4-307">If SystemInformation.HighContrast is `true`, the application should:</span></span>  
  
-   <span data-ttu-id="80aa4-308">Zobrazit všechny prvky uživatelského rozhraní pomocí barevného schématu systému</span><span class="sxs-lookup"><span data-stu-id="80aa4-308">Display all user interface elements using the system color scheme</span></span>  
  
-   <span data-ttu-id="80aa4-309">Oznamují vizuální upozornění nebo zvukových veškeré informace, které se bude předávat přes barvu.</span><span class="sxs-lookup"><span data-stu-id="80aa4-309">Convey by visual cues or sound any information that is conveyed through color.</span></span> <span data-ttu-id="80aa4-310">Například pokud konkrétní seznam položek se zvýrazní pomocí red písmo, můžete také přidat tučné písmo, tak, aby uživatel má jiný color upozornění, že jsou vyznačené položky.</span><span class="sxs-lookup"><span data-stu-id="80aa4-310">For example, if particular list items are highlighted by using a red font, you could also add bold to the font, so that the user has a non-color cue that the items are highlighted.</span></span>  
  
-   <span data-ttu-id="80aa4-311">Vynechat všechny bitové kopie nebo vzory za text</span><span class="sxs-lookup"><span data-stu-id="80aa4-311">Omit any images or patterns behind text</span></span>  
  
 <span data-ttu-id="80aa4-312">Aplikace by se mělo zjistit nastavením <xref:System.Windows.Forms.SystemInformation.HighContrast%2A> když aplikaci spustí a reagovat na systémové události <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged>.</span><span class="sxs-lookup"><span data-stu-id="80aa4-312">The application should check the setting of <xref:System.Windows.Forms.SystemInformation.HighContrast%2A> when the application starts and respond to the system event <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged>.</span></span> <span data-ttu-id="80aa4-313"><xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> Událost se vyvolá, vždy, když hodnota <xref:System.Windows.Forms.SystemInformation.HighContrast%2A> změny.</span><span class="sxs-lookup"><span data-stu-id="80aa4-313">The <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> event is raised whenever the value of <xref:System.Windows.Forms.SystemInformation.HighContrast%2A> changes.</span></span>  
  
 <span data-ttu-id="80aa4-314">V naší aplikaci, je jediným prvkem, který nepoužívá nastavení systému pro barvu `lblCompanyName`.</span><span class="sxs-lookup"><span data-stu-id="80aa4-314">In our application, the only element that is not using the system settings for color is `lblCompanyName`.</span></span> <span data-ttu-id="80aa4-315"><xref:System.Drawing.SystemColors> Třída se používá k změňte nastavení barvu popisku na barvy vybraných uživatelem systému.</span><span class="sxs-lookup"><span data-stu-id="80aa4-315">The <xref:System.Drawing.SystemColors> class is used to change the color settings of the label to the user-selected system colors.</span></span>  
  
#### <a name="to-enable-high-contrast-mode-in-an-effective-way"></a><span data-ttu-id="80aa4-316">Chcete-li povolit režimu vysokého kontrastu účinným způsobem</span><span class="sxs-lookup"><span data-stu-id="80aa4-316">To enable High Contrast mode in an effective way</span></span>  
  
1.  <span data-ttu-id="80aa4-317">Vytvořte metodu a nastavit barvy popisku pro barev systému.</span><span class="sxs-lookup"><span data-stu-id="80aa4-317">Create a method to set the colors of the label to the system colors.</span></span>  
  
    ```  
    ' Visual Basic  
    Private Sub SetColorScheme()  
       If SystemInformation.HighContrast Then  
          companyLabel.BackColor = SystemColors.Window  
          companyLabel.ForeColor = SystemColors.WindowText  
       Else  
          companyLabel.BackColor = Color.Blue  
          companyLabel.ForeColor = Color.Yellow  
       End If  
    End Sub  
  
    // C#  
    private void SetColorScheme()  
    {  
       if (SystemInformation.HighContrast)  
       {  
          companyLabel.BackColor = SystemColors.Window;  
          companyLabel.ForeColor = SystemColors.WindowText;  
       }  
       else  
       {  
          companyLabel.BackColor = Color.Blue;  
          companyLabel.ForeColor = Color.Yellow;  
       }  
    }  
    ```  
  
2.  <span data-ttu-id="80aa4-318">Volání `SetColorScheme` postup v konstruktoru formuláře (`Public Sub New()` v jazyce Visual Basic a `public class Form1` v jazyce Visual C#).</span><span class="sxs-lookup"><span data-stu-id="80aa4-318">Call the `SetColorScheme` procedure in the form constructor (`Public Sub New()` in Visual Basic and `public class Form1` in Visual C#).</span></span> <span data-ttu-id="80aa4-319">Pro přístup k konstruktoru v jazyce Visual Basic, budete muset rozbalte oblast s názvem bez přípony **Windows Form Designer generovaného kódu**.</span><span class="sxs-lookup"><span data-stu-id="80aa4-319">To access the constructor in Visual Basic, you will need to expand the region labeled **Windows Form Designer generated code**.</span></span>  
  
    ```  
    ' Visual Basic   
    Public Sub New()  
       MyBase.New()  
       InitializeComponent()  
       SetColorScheme()  
    End Sub  
  
    // C#  
    public Form1()  
    {  
       InitializeComponent();  
       SetColorScheme();  
    }  
    ```  
  
3.  <span data-ttu-id="80aa4-320">Vytvořit procedury události s odpovídajícím podpisem, aby odpovídal na <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> událostí.</span><span class="sxs-lookup"><span data-stu-id="80aa4-320">Create an event procedure, with the appropriate signature, to respond to the <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> event.</span></span>  
  
    ```  
    ' Visual Basic  
    Protected Sub UserPreferenceChanged(ByVal sender As Object, _  
    ByVal e As Microsoft.Win32.UserPreferenceChangedEventArgs)  
       SetColorScheme()  
    End Sub  
  
    // C#  
    public void UserPreferenceChanged(object sender,   
    Microsoft.Win32.UserPreferenceChangedEventArgs e)  
    {  
       SetColorScheme();  
    }  
    ```  
  
4.  <span data-ttu-id="80aa4-321">Přidejte do konstruktoru formuláře kód po volání `InitializeComponents`, spojit události postup systémové události.</span><span class="sxs-lookup"><span data-stu-id="80aa4-321">Add code to the form constructor, after the call to `InitializeComponents`, to hook up the event procedure to the system event.</span></span> <span data-ttu-id="80aa4-322">Tato metoda volá `SetColorScheme` postupu.</span><span class="sxs-lookup"><span data-stu-id="80aa4-322">This method calls the `SetColorScheme` procedure.</span></span>  
  
    ```  
    ' Visual Basic  
    Public Sub New()  
       MyBase.New()  
       InitializeComponent()  
       SetColorScheme()  
       AddHandler Microsoft.Win32.SystemEvents.UserPreferenceChanged, _  
          AddressOf Me.UserPreferenceChanged  
    End Sub  
  
    // C#  
    public Form1()  
    {  
       InitializeComponent();  
       SetColorScheme();  
       Microsoft.Win32.SystemEvents.UserPreferenceChanged   
          += new Microsoft.Win32.UserPreferenceChangedEventHandler(  
          this.UserPreferenceChanged);  
    }  
    ```  
  
5.  <span data-ttu-id="80aa4-323">Přidejte kód pro formulář <xref:System.Windows.Forms.Control.Dispose%2A> metody před volání <xref:System.Windows.Forms.Control.Dispose%2A> metoda základní třídy, chcete-li uvolnit událostí po ukončení aplikace.</span><span class="sxs-lookup"><span data-stu-id="80aa4-323">Add code to the form <xref:System.Windows.Forms.Control.Dispose%2A> method, before the call to the <xref:System.Windows.Forms.Control.Dispose%2A> method of the base class, to release the event when the application closes.</span></span> <span data-ttu-id="80aa4-324">Abyste měli přístup <xref:System.Windows.Forms.Control.Dispose%2A> metody v jazyce Visual Basic, budete muset rozbalte oblast s názvem bez přípony Windows Form Designer vygenerovat kód.</span><span class="sxs-lookup"><span data-stu-id="80aa4-324">To access the <xref:System.Windows.Forms.Control.Dispose%2A> method in Visual Basic, you will need to expand the region labeled Windows Form Designer generated code.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="80aa4-325">Spustí kód událostí systému vlákno odděleně od hlavní aplikace.</span><span class="sxs-lookup"><span data-stu-id="80aa4-325">The system event code runs a thread separate from the main application.</span></span> <span data-ttu-id="80aa4-326">Pokud není verze události, kód, který spojit události se spustí i po ukončení programu.</span><span class="sxs-lookup"><span data-stu-id="80aa4-326">If you do not release the event, the code that you hook up to the event will run even after the program is closed.</span></span>  
  
    ```  
    ' Visual Basic  
    Protected Overloads Overrides Sub Dispose(ByVal disposing As Boolean)  
       If disposing Then  
          If Not (components Is Nothing) Then  
             components.Dispose()  
          End If  
       End If  
       RemoveHandler Microsoft.Win32.SystemEvents.UserPreferenceChanged, _  
          AddressOf Me.UserPreferenceChanged  
       MyBase.Dispose(disposing)  
    End Sub  
  
    // C#  
    protected override void Dispose( bool disposing )  
    {  
       if( disposing )  
       {  
          if (components != null)   
          {  
             components.Dispose();  
          }  
       }  
       Microsoft.Win32.SystemEvents.UserPreferenceChanged   
          -= new Microsoft.Win32.UserPreferenceChangedEventHandler(  
          this.UserPreferenceChanged);  
       base.Dispose( disposing );  
    }  
    ```  
  
6.  <span data-ttu-id="80aa4-327">Stisknutím klávesy F5 spusťte aplikaci.</span><span class="sxs-lookup"><span data-stu-id="80aa4-327">Press F5 to run the application.</span></span>  
  
## <a name="conveying-important-information-by-means-other-than-sound"></a><span data-ttu-id="80aa4-328">Předávání důležitých informací jiným způsobem než zvuk</span><span class="sxs-lookup"><span data-stu-id="80aa4-328">Conveying Important Information by Means Other Than Sound</span></span>  
 <span data-ttu-id="80aa4-329">V této aplikaci žádné informace předávají zvukovou samostatně.</span><span class="sxs-lookup"><span data-stu-id="80aa4-329">In this application, no information is conveyed by sound alone.</span></span> <span data-ttu-id="80aa4-330">Pokud používáte zvuku ve vaší aplikaci, musí jiným způsobem a zadejte informace.</span><span class="sxs-lookup"><span data-stu-id="80aa4-330">If you use sound in your application, then you should supply the information by some other means as well.</span></span>  
  
#### <a name="to-supply-information-by-some-other-means-than-sound"></a><span data-ttu-id="80aa4-331">K poskytování informací jiným způsobem než zvuk</span><span class="sxs-lookup"><span data-stu-id="80aa4-331">To supply information by some other means than sound</span></span>  
  
1.  <span data-ttu-id="80aa4-332">Zkontrolujte záhlaví s použitím funkce rozhraní API systému Windows FlashWindow, flash.</span><span class="sxs-lookup"><span data-stu-id="80aa4-332">Make the title bar flash by using the Windows API function FlashWindow.</span></span> <span data-ttu-id="80aa4-333">Příklad toho, jak volat funkce rozhraní API systému Windows, naleznete v části [návod: volání rozhraní API systému Windows](~/docs/visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md).</span><span class="sxs-lookup"><span data-stu-id="80aa4-333">For an example of how to call Windows API functions, see [Walkthrough: Calling Windows APIs](~/docs/visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="80aa4-334">Uživatel může mít povoleno, službu Popis zvuku Windows, která způsobí také okno na flash po přehrání zvuku systému prostřednictvím předdefinované mluvčího počítače.</span><span class="sxs-lookup"><span data-stu-id="80aa4-334">The user may have the Windows SoundSentry service enabled, which will also cause the window to flash when the system sounds are played through the computer's built-in speaker.</span></span>  
  
2.  <span data-ttu-id="80aa4-335">Důležité informace zobrazí v nemodálním okně, tak, aby uživatel může odpovědět na ni.</span><span class="sxs-lookup"><span data-stu-id="80aa4-335">Display the important information in a non-modal window so that the user may respond to it.</span></span>  
  
3.  <span data-ttu-id="80aa4-336">Zobrazte okno se zprávou, který získá fokus klávesnice.</span><span class="sxs-lookup"><span data-stu-id="80aa4-336">Display a message box that acquires the keyboard focus.</span></span> <span data-ttu-id="80aa4-337">Tato metoda Vyhněte se při uživatel může být psaní.</span><span class="sxs-lookup"><span data-stu-id="80aa4-337">Avoid this method when the user may be typing.</span></span>  
  
4.  <span data-ttu-id="80aa4-338">Zobrazí indikátor stavu v oznamovací oblasti stav na hlavním panelu.</span><span class="sxs-lookup"><span data-stu-id="80aa4-338">Display a status indicator in the status notification area of the taskbar.</span></span> <span data-ttu-id="80aa4-339">Podrobnosti najdete v tématu [přidání ikon aplikací do TaskBar se součástí Windows Forms NotifyIcon](../../../../docs/framework/winforms/controls/app-icons-to-the-taskbar-with-wf-notifyicon.md).</span><span class="sxs-lookup"><span data-stu-id="80aa4-339">For details, see [Adding Application Icons to the TaskBar with the Windows Forms NotifyIcon Component](../../../../docs/framework/winforms/controls/app-icons-to-the-taskbar-with-wf-notifyicon.md).</span></span>  
  
## <a name="testing-the-application"></a><span data-ttu-id="80aa4-340">Testování aplikace</span><span class="sxs-lookup"><span data-stu-id="80aa4-340">Testing the Application</span></span>  
 <span data-ttu-id="80aa4-341">Před nasazením aplikace, měli byste otestovat funkce usnadnění, které jste implementovali.</span><span class="sxs-lookup"><span data-stu-id="80aa4-341">Before deploying the application, you should test the accessibility features that you have implemented.</span></span>  
  
#### <a name="to-test-accessibility-features"></a><span data-ttu-id="80aa4-342">Testování funkce pro usnadnění přístupu</span><span class="sxs-lookup"><span data-stu-id="80aa4-342">To test accessibility features</span></span>  
  
1.  <span data-ttu-id="80aa4-343">Test přístupu k klávesnice, myš odpojte a Navigovat v uživatelském rozhraní pro každou funkci pouze pomocí klávesnice.</span><span class="sxs-lookup"><span data-stu-id="80aa4-343">To test keyboard access, unplug the mouse and navigate the user interface for each feature using only the keyboard.</span></span> <span data-ttu-id="80aa4-344">Zajistěte, aby všechny úlohy mohou být provedeny pomocí klávesnice jenom.</span><span class="sxs-lookup"><span data-stu-id="80aa4-344">Ensure that all tasks may be performed using the keyboard only.</span></span>  
  
2.  <span data-ttu-id="80aa4-345">K otestování podpory vysoký kontrast, zvolte ikonu Možnosti usnadnění v Ovládacích panelech.</span><span class="sxs-lookup"><span data-stu-id="80aa4-345">To test support of High Contrast, choose the Accessibility Options icon in Control Panel.</span></span> <span data-ttu-id="80aa4-346">Klikněte na kartu zobrazení a zaškrtněte políčko použití vysokého kontrastu.</span><span class="sxs-lookup"><span data-stu-id="80aa4-346">Click the Display tab and select the Use High Contrast check box.</span></span> <span data-ttu-id="80aa4-347">Procházejte všechny prvky uživatelského rozhraní pro zajištění, že barev a písem změny se projeví.</span><span class="sxs-lookup"><span data-stu-id="80aa4-347">Navigate through all user interface elements to ensure that the color and font changes are reflected.</span></span> <span data-ttu-id="80aa4-348">Ujistěte se také, vynechání bitové kopie nebo vzory vykreslovat za text.</span><span class="sxs-lookup"><span data-stu-id="80aa4-348">Also, ensure that images or patterns drawn behind text are omitted.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="80aa4-349">Systém Windows NT 4 nemá ikonu Možnosti usnadnění v Ovládacích panelech.</span><span class="sxs-lookup"><span data-stu-id="80aa4-349">Windows NT 4 does not have an Accessibility Options icon in Control Panel.</span></span> <span data-ttu-id="80aa4-350">Tento postup pro změnu nastavení SystemInformation.HighContrast proto nefunguje v systému Windows NT 4.</span><span class="sxs-lookup"><span data-stu-id="80aa4-350">Thus, this procedure for changing the SystemInformation.HighContrast setting does not work in Windows NT 4.</span></span>  
  
3.  <span data-ttu-id="80aa4-351">Další nástroje jsou snadno dostupné pro testování usnadnění aplikace.</span><span class="sxs-lookup"><span data-stu-id="80aa4-351">Other tools are readily available for testing the accessibility of an application.</span></span>  
  
4.  <span data-ttu-id="80aa4-352">Chcete-li otestovat vystavení fokus klávesnice, spusťte Lupa.</span><span class="sxs-lookup"><span data-stu-id="80aa4-352">To test exposing the keyboard focus, run Magnifier.</span></span> <span data-ttu-id="80aa4-353">(Otevřete ho kliknutím na **spustit** nabídky, přejděte na příkaz **programy**, přejděte na příkaz **Příslušenství**, přejděte na **usnadnění**a pak klikněte na tlačítko  **Lupa**).</span><span class="sxs-lookup"><span data-stu-id="80aa4-353">(To open it, click the **Start** menu, point to **Programs**, point to **Accessories**, point to **Accessibility**, and then click **Magnifier**).</span></span> <span data-ttu-id="80aa4-354">Navigovat v uživatelském rozhraní, pomocí procházení tabulátorem klávesnice a myši.</span><span class="sxs-lookup"><span data-stu-id="80aa4-354">Navigate the user interface using both keyboard tabbing and the mouse.</span></span> <span data-ttu-id="80aa4-355">Ujistěte se, že je správně sledovat všechny navigační **Lupa**.</span><span class="sxs-lookup"><span data-stu-id="80aa4-355">Ensure that all navigation is tracked properly in **Magnifier**.</span></span>  
  
5.  <span data-ttu-id="80aa4-356">K testování zpřístupňuje prvky obrazovky, spusťte kontroly a použít k dosažení každý prvek myši a klávesy TAB.</span><span class="sxs-lookup"><span data-stu-id="80aa4-356">To test exposing screen elements, run Inspect, and use both the mouse and the TAB key to reach each element.</span></span> <span data-ttu-id="80aa4-357">Zajistěte, aby byl informace uvedené v polích pro název, stav, Role, umístění a hodnota okna kontroly srozumitelné pro uživatele pro každý objekt v uživatelském rozhraní.</span><span class="sxs-lookup"><span data-stu-id="80aa4-357">Ensure that the information presented in the Name, State, Role, Location, and Value fields of the Inspect window is meaningful to the user for each object in the UI.</span></span>
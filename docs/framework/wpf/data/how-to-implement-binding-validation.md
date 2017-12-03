---
title: "Postupy: Implementace ověření připojení"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- validation of binding [WPF]
- data binding [WPF], validation of binding
- binding [WPF], validation of
ms.assetid: eb98b33d-9866-49ae-b981-bc5ff20d607a
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ec860cc9cc58febd98d8642c98a50ec296592d02
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-binding-validation"></a><span data-ttu-id="cfb9e-102">Postupy: Implementace ověření připojení</span><span class="sxs-lookup"><span data-stu-id="cfb9e-102">How to: Implement Binding Validation</span></span>
<span data-ttu-id="cfb9e-103">Tento příklad ukazuje, jak používat <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> a aktivační události styl visual svůj názor informovat uživatele, pokud je zadaná neplatná hodnota, podle vlastního ověřovacího pravidla.</span><span class="sxs-lookup"><span data-stu-id="cfb9e-103">This example shows how to use an <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> and a style trigger to provide visual feedback to inform the user when an invalid value is entered, based on a custom validation rule.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cfb9e-104">Příklad</span><span class="sxs-lookup"><span data-stu-id="cfb9e-104">Example</span></span>  
 <span data-ttu-id="cfb9e-105">Obsah textu <xref:System.Windows.Controls.TextBox> v následujícím příkladu je vázána `Age` vlastnost (typ int) s názvem zdrojového objektu vazby `ods`.</span><span class="sxs-lookup"><span data-stu-id="cfb9e-105">The text content of the <xref:System.Windows.Controls.TextBox> in the following example is bound to the `Age` property (of type int) of a binding source object named `ods`.</span></span> <span data-ttu-id="cfb9e-106">Vazba je nastavit tak, aby použijte ověřovací pravidlo s názvem `AgeRangeRule` tak, aby pokud uživatel zadá jiné než číselné znaky nebo hodnotu, která je menší než 21 nebo větší než 130, textovém poli se zobrazí červený vykřičník a popis tlačítka s chybovou zprávou kde n uživatel přesune ukazatel myši nad textové pole.</span><span class="sxs-lookup"><span data-stu-id="cfb9e-106">The binding is set up to use a validation rule named `AgeRangeRule` so that if the user enters non-numeric characters or a value that is smaller than 21 or greater than 130, a red exclamation mark appears next to the text box and a tool tip with the error message appears when the user moves the mouse over the text box.</span></span>  
  
 [!code-xaml[BindValidation#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="cfb9e-107">Následující příklad ukazuje implementaci `AgeRangeRule`, který dědí z <xref:System.Windows.Controls.ValidationRule> a přepíše <xref:System.Windows.Controls.ValidationRule.Validate%2A> metoda.</span><span class="sxs-lookup"><span data-stu-id="cfb9e-107">The following example shows the implementation of `AgeRangeRule`, which inherits from <xref:System.Windows.Controls.ValidationRule> and overrides the <xref:System.Windows.Controls.ValidationRule.Validate%2A> method.</span></span> <span data-ttu-id="cfb9e-108">Int32.Parse() metoda je volána na hodnotu a ujistěte se, zda neobsahuje žádné neplatné znaky.</span><span class="sxs-lookup"><span data-stu-id="cfb9e-108">The Int32.Parse() method is called on the value to make sure that it does not contain any invalid characters.</span></span> <span data-ttu-id="cfb9e-109"><xref:System.Windows.Controls.ValidationRule.Validate%2A> Metoda vrátí <xref:System.Windows.Controls.ValidationResult> určující, pokud hodnota je platná založené na tom, jestli je výjimka zachycena při analýze a jestli je hodnota stáří mimo dolní a horní meze.</span><span class="sxs-lookup"><span data-stu-id="cfb9e-109">The <xref:System.Windows.Controls.ValidationRule.Validate%2A> method returns a <xref:System.Windows.Controls.ValidationResult> that indicates if the value is valid based on whether an exception is caught during the parsing and whether the age value is outside of the lower and upper bounds.</span></span>  
  
 [!code-csharp[BindValidation#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/AgeRangeRule.cs#3)]  
  
 <span data-ttu-id="cfb9e-110">Následující příklad ukazuje vlastní <xref:System.Windows.Controls.ControlTemplate> `validationTemplate` vytvářející červený vykřičník a upozorní uživatele k chybě ověření.</span><span class="sxs-lookup"><span data-stu-id="cfb9e-110">The following example shows the custom <xref:System.Windows.Controls.ControlTemplate> `validationTemplate` that creates a red exclamation mark to notify the user of a validation error.</span></span> <span data-ttu-id="cfb9e-111">Ovládací prvek šablon se používají k znovu definovat vzhledu ovládacího prvku.</span><span class="sxs-lookup"><span data-stu-id="cfb9e-111">Control templates are used to redefine the appearance of a control.</span></span>  
  
 [!code-xaml[BindValidation#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#4)]  
  
 <span data-ttu-id="cfb9e-112">Jak je znázorněno v následujícím příkladu <xref:System.Windows.Controls.ToolTip> , zobrazí se chybová zpráva vytvořena pomocí styl s názvem `textBoxInError`.</span><span class="sxs-lookup"><span data-stu-id="cfb9e-112">As shown in the following example, the <xref:System.Windows.Controls.ToolTip> that shows the error message is created using the style named `textBoxInError`.</span></span> <span data-ttu-id="cfb9e-113">Pokud hodnota <xref:System.Windows.Controls.Validation.HasError%2A> je `true`, aktivační událost nastaví popisek přesunutí aktuálního <xref:System.Windows.Controls.TextBox> do své první chyby ověření.</span><span class="sxs-lookup"><span data-stu-id="cfb9e-113">If the value of <xref:System.Windows.Controls.Validation.HasError%2A> is `true`, the trigger sets the tool tip of the current <xref:System.Windows.Controls.TextBox> to its first validation error.</span></span> <span data-ttu-id="cfb9e-114"><xref:System.Windows.Data.Binding.RelativeSource%2A> Je nastaven na <xref:System.Windows.Data.RelativeSourceMode.Self>odkazující na aktuálního elementu.</span><span class="sxs-lookup"><span data-stu-id="cfb9e-114">The <xref:System.Windows.Data.Binding.RelativeSource%2A> is set to <xref:System.Windows.Data.RelativeSourceMode.Self>, referring to the current element.</span></span>  
  
 [!code-xaml[BindValidation#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#5)]  
  
 <span data-ttu-id="cfb9e-115">Úplný příklad najdete v tématu [vazby Ukázka ověřování](http://go.microsoft.com/fwlink/?LinkID=159972).</span><span class="sxs-lookup"><span data-stu-id="cfb9e-115">For the complete example, see [Binding Validation Sample](http://go.microsoft.com/fwlink/?LinkID=159972).</span></span>  
  
 <span data-ttu-id="cfb9e-116">Všimněte si, že pokud nezadáte vlastní <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> výchozí šablony chyba se zobrazí k poskytnutí zpětné vazby visual pro uživatele, když dojde k chybě ověření.</span><span class="sxs-lookup"><span data-stu-id="cfb9e-116">Note that if you do not provide a custom <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> the default error template appears to provide visual feedback to the user when there is a validation error.</span></span> <span data-ttu-id="cfb9e-117">V části "Ověření dat" v [přehled vazby dat](../../../../docs/framework/wpf/data/data-binding-overview.md) Další informace.</span><span class="sxs-lookup"><span data-stu-id="cfb9e-117">See "Data Validation" in [Data Binding Overview](../../../../docs/framework/wpf/data/data-binding-overview.md) for more information.</span></span> <span data-ttu-id="cfb9e-118">Navíc [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] poskytuje integrované ověřovací pravidlo, které zachytí výjimky, které jsou vyvolány během aktualizace zdrojová vlastnost vazby.</span><span class="sxs-lookup"><span data-stu-id="cfb9e-118">Also, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] provides a built-in validation rule that catches exceptions that are thrown during the update of the binding source property.</span></span> <span data-ttu-id="cfb9e-119">Další informace naleznete v tématu <xref:System.Windows.Controls.ExceptionValidationRule>.</span><span class="sxs-lookup"><span data-stu-id="cfb9e-119">For more information, see <xref:System.Windows.Controls.ExceptionValidationRule>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfb9e-120">Viz také</span><span class="sxs-lookup"><span data-stu-id="cfb9e-120">See Also</span></span>  
 [<span data-ttu-id="cfb9e-121">Přehled vazba dat</span><span class="sxs-lookup"><span data-stu-id="cfb9e-121">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="cfb9e-122">Postupy: témata</span><span class="sxs-lookup"><span data-stu-id="cfb9e-122">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
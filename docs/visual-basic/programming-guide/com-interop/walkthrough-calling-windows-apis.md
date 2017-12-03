---
title: "Návod: Volání rozhraní API systému Windows (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- DLLs, calling
- Windows API, walkthroughs
- platform invoke, walkthroughs
- API calls [Visual Basic], walkthroughs [Visual Basic]
- Windows API, calling
- walkthroughs [Visual Basic], API calls
- DllImport attribute, calling Windows API
- Declare statement [Visual Basic], declaring DLL functions
ms.assetid: 9280ca96-7a93-47a3-8d01-6d01be0657cb
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d494ad0f8bd4eb0dac57de214064fd2d208011ff
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-calling-windows-apis-visual-basic"></a><span data-ttu-id="be007-102">Návod: Volání rozhraní API systému Windows (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="be007-102">Walkthrough: Calling Windows APIs (Visual Basic)</span></span>
<span data-ttu-id="be007-103">Rozhraní API systému Windows jsou dynamické knihovny (DLL), které jsou součástí operačního systému Windows.</span><span class="sxs-lookup"><span data-stu-id="be007-103">Windows APIs are dynamic-link libraries (DLLs) that are part of the Windows operating system.</span></span> <span data-ttu-id="be007-104">Můžete použít je k provádění úloh, když je k zápisu ekvivalentní postupy.</span><span class="sxs-lookup"><span data-stu-id="be007-104">You use them to perform tasks when it is difficult to write equivalent procedures of your own.</span></span> <span data-ttu-id="be007-105">Například systém Windows nabízí funkce s názvem `FlashWindowEx` , umožňuje provádět alternativní mezi světlým a tmavým odstínech záhlaví pro aplikaci.</span><span class="sxs-lookup"><span data-stu-id="be007-105">For example, Windows provides a function named `FlashWindowEx` that lets you make the title bar for an application alternate between light and dark shades.</span></span>  
  
 <span data-ttu-id="be007-106">Výhodou použití rozhraní API systému Windows ve vašem kódu je v okamžiku vývoje si mohou uložit, protože obsahují desítek užitečné funkce, které jsou již zapsány a čekání, který se má použít.</span><span class="sxs-lookup"><span data-stu-id="be007-106">The advantage of using Windows APIs in your code is that they can save development time because they contain dozens of useful functions that are already written and waiting to be used.</span></span> <span data-ttu-id="be007-107">Nevýhodou je, že rozhraní API systému Windows může být složité fungovat s a nepřijímá, když dojde k potížím.</span><span class="sxs-lookup"><span data-stu-id="be007-107">The disadvantage is that Windows APIs can be difficult to work with and unforgiving when things go wrong.</span></span>  
  
 <span data-ttu-id="be007-108">Rozhraní API systému Windows představují zvláštní kategorii interoperability.</span><span class="sxs-lookup"><span data-stu-id="be007-108">Windows APIs represent a special category of interoperability.</span></span> <span data-ttu-id="be007-109">Rozhraní API systému Windows nepoužívejte spravovaného kódu, nemají předdefinované knihovny typů a použít datové typy, které se liší od těch, které používá pomocí sady Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="be007-109">Windows APIs do not use managed code, do not have built-in type libraries, and use data types that are different than those used with Visual Studio.</span></span> <span data-ttu-id="be007-110">Z důvodu těchto rozdílů a protože rozhraní API systému Windows nejsou objekty modelu COM, interoperabilita s rozhraní API systému Windows a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] se provádí pomocí platformy vyvolání, nebo PInvoke.</span><span class="sxs-lookup"><span data-stu-id="be007-110">Because of these differences, and because Windows APIs are not COM objects, interoperability with Windows APIs and the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] is performed using platform invoke, or PInvoke.</span></span> <span data-ttu-id="be007-111">Vyvolání platformy je služba, což umožňuje spravovat kódu volání nespravovaných funkcí, které jsou implementované v knihovnách DLL.</span><span class="sxs-lookup"><span data-stu-id="be007-111">Platform invoke is a service that enables managed code to call unmanaged functions implemented in DLLs.</span></span> <span data-ttu-id="be007-112">Další informace najdete v tématu [využívání nespravovaných funkcí DLL](../../../framework/interop/consuming-unmanaged-dll-functions.md).</span><span class="sxs-lookup"><span data-stu-id="be007-112">For more information, see [Consuming Unmanaged DLL Functions](../../../framework/interop/consuming-unmanaged-dll-functions.md).</span></span> <span data-ttu-id="be007-113">Můžete použít PInvoke v [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] pomocí `Declare` příkaz nebo použití `DllImport` atribut procedury.</span><span class="sxs-lookup"><span data-stu-id="be007-113">You can use PInvoke in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] by using either the `Declare` statement or applying the `DllImport` attribute to an empty procedure.</span></span>  
  
 <span data-ttu-id="be007-114">Volání rozhraní API systému Windows byly důležitou součástí [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] programování v minulosti, ale jsou zřídka nezbytné s Visual Basic .NET.</span><span class="sxs-lookup"><span data-stu-id="be007-114">Windows API calls were an important part of [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] programming in the past, but are seldom necessary with Visual Basic .NET.</span></span> <span data-ttu-id="be007-115">Pokud je to možné, používejte spravovaného kódu z [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] k provádění úloh, namísto volání rozhraní API systému Windows.</span><span class="sxs-lookup"><span data-stu-id="be007-115">Whenever possible, you should use managed code from the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] to perform tasks, instead of Windows API calls.</span></span> <span data-ttu-id="be007-116">Tento názorný postup obsahuje informace pro tyto situace, ve které pomocí rozhraní API systému Windows je potřeba.</span><span class="sxs-lookup"><span data-stu-id="be007-116">This walkthrough provides information for those situations in which using Windows APIs is necessary.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="api-calls-using-declare"></a><span data-ttu-id="be007-117">Volání rozhraní API pomocí deklarace</span><span class="sxs-lookup"><span data-stu-id="be007-117">API Calls Using Declare</span></span>  
 <span data-ttu-id="be007-118">Nejběžnější způsob k volání rozhraní API systému Windows je pomocí `Declare` příkaz.</span><span class="sxs-lookup"><span data-stu-id="be007-118">The most common way to call Windows APIs is by using the `Declare` statement.</span></span>  
  
#### <a name="to-declare-a-dll-procedure"></a><span data-ttu-id="be007-119">Deklarace procedury knihovny DLL</span><span class="sxs-lookup"><span data-stu-id="be007-119">To declare a DLL procedure</span></span>  
  
1.  <span data-ttu-id="be007-120">Určení názvu funkce, kterou chcete volat, a navíc jeho argumenty, typy argumentů a vrátí hodnotu, jakož i název a umístění knihovny DLL, která ji obsahuje.</span><span class="sxs-lookup"><span data-stu-id="be007-120">Determine the name of the function you want to call, plus its arguments, argument types, and return value, as well as the name and location of the DLL that contains it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="be007-121">Úplné informace o rozhraní API systému Windows najdete v dokumentaci k Win32 SDK v rozhraní API systému Windows SDK platformy.</span><span class="sxs-lookup"><span data-stu-id="be007-121">For complete information about the Windows APIs, see the Win32 SDK documentation in the Platform SDK Windows API.</span></span> <span data-ttu-id="be007-122">Další informace o konstanty, které používají rozhraní API systému Windows zkontrolujte soubory hlaviček, jako je například odkazující na součástí sady SDK pro platformu Windows.</span><span class="sxs-lookup"><span data-stu-id="be007-122">For more information about the constants that Windows APIs use, examine the header files such as Windows.h included with the Platform SDK.</span></span>  
  
2.  <span data-ttu-id="be007-123">Otevřete nový projekt aplikace Windows tak, že kliknete na **nový** na **soubor** nabídce a potom kliknutím na **projektu**.</span><span class="sxs-lookup"><span data-stu-id="be007-123">Open a new Windows Application project by clicking **New** on the **File** menu, and then clicking **Project**.</span></span> <span data-ttu-id="be007-124">**Nový projekt** zobrazí se dialogové okno.</span><span class="sxs-lookup"><span data-stu-id="be007-124">The **New Project** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="be007-125">Vyberte **aplikace Windows** ze seznamu [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] šablony projektu.</span><span class="sxs-lookup"><span data-stu-id="be007-125">Select **Windows Application** from the list of [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] project templates.</span></span> <span data-ttu-id="be007-126">Zobrazí se nový projekt.</span><span class="sxs-lookup"><span data-stu-id="be007-126">The new project is displayed.</span></span>  
  
4.  <span data-ttu-id="be007-127">Přidejte následující `Declare` funkce buď ke třídě nebo modul, ve které chcete použít knihovnu DLL:</span><span class="sxs-lookup"><span data-stu-id="be007-127">Add the following `Declare` function either to the class or module in which you want to use the DLL:</span></span>  
  
     [!code-vb[VbVbalrInterop#9](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_1.vb)]  
  
### <a name="parts-of-the-declare-statement"></a><span data-ttu-id="be007-128">Součástí Declare – příkaz</span><span class="sxs-lookup"><span data-stu-id="be007-128">Parts of the Declare Statement</span></span>  
 <span data-ttu-id="be007-129">`Declare` Příkaz obsahuje následující prvky.</span><span class="sxs-lookup"><span data-stu-id="be007-129">The `Declare` statement includes the following elements.</span></span>  
  
#### <a name="auto-modifier"></a><span data-ttu-id="be007-130">Automatické modifikátor</span><span class="sxs-lookup"><span data-stu-id="be007-130">Auto modifier</span></span>  
 <span data-ttu-id="be007-131">`Auto` Modifikátor dá pokyn modulu runtime převést řetězec na základě názvu metoda podle běžnými pravidly language runtime (nebo název aliasu-li zadána).</span><span class="sxs-lookup"><span data-stu-id="be007-131">The `Auto` modifier instructs the runtime to convert the string based on the method name according to common language runtime rules (or alias name if specified).</span></span>  
  
#### <a name="lib-and-alias-keywords"></a><span data-ttu-id="be007-132">LIB a Alias klíčová slova</span><span class="sxs-lookup"><span data-stu-id="be007-132">Lib and Alias keywords</span></span>  
 <span data-ttu-id="be007-133">Tento název `Function` – klíčové slovo je název vašeho programu se používá pro přístup k importované funkce.</span><span class="sxs-lookup"><span data-stu-id="be007-133">The name following the `Function` keyword is the name your program uses to access the imported function.</span></span> <span data-ttu-id="be007-134">Může být stejný jako název skutečné při volání funkce, nebo můžete použít všechny název procedury platný a poté společnosti využívají `Alias` – klíčové slovo zadat skutečné název funkce volání.</span><span class="sxs-lookup"><span data-stu-id="be007-134">It can be the same as the real name of the function you are calling, or you can use any valid procedure name and then employ the `Alias` keyword to specify the real name of the function you are calling.</span></span>  
  
 <span data-ttu-id="be007-135">Zadejte `Lib` – klíčové slovo, za nímž následuje název a umístění knihovny DLL, která obsahuje funkce, které jsou volání.</span><span class="sxs-lookup"><span data-stu-id="be007-135">Specify the `Lib` keyword, followed by the name and location of the DLL that contains the function you are calling.</span></span> <span data-ttu-id="be007-136">Není nutné zadat cestu pro soubory uložené v adresáři systému Windows.</span><span class="sxs-lookup"><span data-stu-id="be007-136">You do not need to specify the path for files located in the Windows system directories.</span></span>  
  
 <span data-ttu-id="be007-137">Použití `Alias` – klíčové slovo, pokud není platný název funkce volání [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] název procedury, nebo koliduje s názvem jiných položek v aplikaci.</span><span class="sxs-lookup"><span data-stu-id="be007-137">Use the `Alias` keyword if the name of the function you are calling is not a valid [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] procedure name, or conflicts with the name of other items in your application.</span></span> <span data-ttu-id="be007-138">`Alias`označuje true název funkce volána.</span><span class="sxs-lookup"><span data-stu-id="be007-138">`Alias` indicates the true name of the function being called.</span></span>  
  
#### <a name="argument-and-data-type-declarations"></a><span data-ttu-id="be007-139">Argument a deklarace typu dat</span><span class="sxs-lookup"><span data-stu-id="be007-139">Argument and Data Type Declarations</span></span>  
 <span data-ttu-id="be007-140">Deklarujte argumenty a jejich datové typy.</span><span class="sxs-lookup"><span data-stu-id="be007-140">Declare the arguments and their data types.</span></span> <span data-ttu-id="be007-141">Tuto část může být náročné, protože typy dat, které používá Windows nemusí odpovídat Visual Studio datové typy.</span><span class="sxs-lookup"><span data-stu-id="be007-141">This part can be challenging because the data types that Windows uses do not correspond to Visual Studio data types.</span></span> [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="be007-142">nemá mnoho činností, které pro vás převodem argumenty na kompatibilní datové typy, procesu označovaného jako *zařazování*.</span><span class="sxs-lookup"><span data-stu-id="be007-142"> does a lot of the work for you by converting arguments to compatible data types, a process called *marshaling*.</span></span> <span data-ttu-id="be007-143">Můžete explicitně řídit, jak jsou argumenty zařazené pomocí <xref:System.Runtime.InteropServices.MarshalAsAttribute> definovaný v atributu <xref:System.Runtime.InteropServices> oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="be007-143">You can explicitly control how arguments are marshaled by using the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute defined in the <xref:System.Runtime.InteropServices> namespace.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="be007-144">Předchozí verze [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] povolené deklarovat parametry `As Any`, tj. Tato data o všech datech typu může.</span><span class="sxs-lookup"><span data-stu-id="be007-144">Previous versions of [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] allowed you to declare parameters `As Any`, meaning that data of any data type could be used.</span></span> [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="be007-145">vyžaduje, aby používal konkrétní datový typ pro všechny `Declare` příkazy.</span><span class="sxs-lookup"><span data-stu-id="be007-145"> requires that you use a specific data type for all `Declare` statements.</span></span>  
  
#### <a name="windows-api-constants"></a><span data-ttu-id="be007-146">Konstanty rozhraním API systému Windows</span><span class="sxs-lookup"><span data-stu-id="be007-146">Windows API Constants</span></span>  
 <span data-ttu-id="be007-147">Některé argumenty jsou kombinace konstanty.</span><span class="sxs-lookup"><span data-stu-id="be007-147">Some arguments are combinations of constants.</span></span> <span data-ttu-id="be007-148">Například `MessageBox` rozhraní API, které jsou uvedené v tomto návodu přijímá argument celé číslo názvem `Typ` která řídí, jak se zobrazí okno se zprávou.</span><span class="sxs-lookup"><span data-stu-id="be007-148">For example, the `MessageBox` API shown in this walkthrough accepts an integer argument called `Typ` that controls how the message box is displayed.</span></span> <span data-ttu-id="be007-149">Číselná hodnota tyto konstanty můžete určit tak, že prověří `#define` příkazy v souboru WINUSER.</span><span class="sxs-lookup"><span data-stu-id="be007-149">You can determine the numeric value of these constants by examining the `#define` statements in the file WinUser.h.</span></span> <span data-ttu-id="be007-150">Číselné hodnoty jsou obecně uvedené v šestnáctkové číslo, proto je vhodné k použití kalkulačky a přidejte je převést na decimal.</span><span class="sxs-lookup"><span data-stu-id="be007-150">The numeric values are generally shown in hexadecimal, so you may want to use a calculator to add them and convert to decimal.</span></span> <span data-ttu-id="be007-151">Například, pokud chcete kombinovat konstanty pro styl vykřičníku `MB_ICONEXCLAMATION` 0x00000030 a Ano/žádné styl `MB_YESNO` 0x00000004, můžete přidat čísla a získání výsledku 0x00000034 nebo 52 decimal.</span><span class="sxs-lookup"><span data-stu-id="be007-151">For example, if you want to combine the constants for the exclamation style `MB_ICONEXCLAMATION` 0x00000030 and the Yes/No style `MB_YESNO` 0x00000004, you can add the numbers and get a result of 0x00000034, or 52 decimal.</span></span> <span data-ttu-id="be007-152">I když používáte decimal výsledek přímo, je lepší deklarovat tyto hodnoty jako konstanty ve vaší aplikaci a zkombinovat pomocí `Or` operátor.</span><span class="sxs-lookup"><span data-stu-id="be007-152">Although you can use the decimal result directly, it is better to declare these values as constants in your application and combine them using the `Or` operator.</span></span>  
  
###### <a name="to-declare-constants-for-windows-api-calls"></a><span data-ttu-id="be007-153">Chcete-li deklarovat konstanty pro volání rozhraní API systému Windows</span><span class="sxs-lookup"><span data-stu-id="be007-153">To declare constants for Windows API calls</span></span>  
  
1.  <span data-ttu-id="be007-154">V dokumentaci pro funkce systému Windows, ke kterému se připojujete.</span><span class="sxs-lookup"><span data-stu-id="be007-154">Consult the documentation for the Windows function you are calling.</span></span> <span data-ttu-id="be007-155">Určuje název, který používá konstanty a název souboru h obsahující číselné hodnoty pro tyto konstanty.</span><span class="sxs-lookup"><span data-stu-id="be007-155">Determine the name of the constants it uses and the name of the .h file that contains the numeric values for these constants.</span></span>  
  
2.  <span data-ttu-id="be007-156">Pomocí textového editoru, například Poznámkový blok, chcete-li zobrazit obsah souboru hlavičky () a najděte hodnoty přidružené k konstanty, kterou používáte.</span><span class="sxs-lookup"><span data-stu-id="be007-156">Use a text editor, such as Notepad, to view the contents of the header (.h) file, and find the values associated with the constants you are using.</span></span> <span data-ttu-id="be007-157">Například `MessageBox` API používá rozhraní konstanta `MB_ICONQUESTION` zobrazíte otazník do pole zpráva.</span><span class="sxs-lookup"><span data-stu-id="be007-157">For example, the `MessageBox` API uses the constant `MB_ICONQUESTION` to show a question mark in the message box.</span></span> <span data-ttu-id="be007-158">Definice `MB_ICONQUESTION` je ve winuser a zobrazí se následujícím způsobem:</span><span class="sxs-lookup"><span data-stu-id="be007-158">The definition for `MB_ICONQUESTION` is in WinUser.h and appears as follows:</span></span>  
  
     `#define MB_ICONQUESTION             0x00000020L`  
  
3.  <span data-ttu-id="be007-159">Přidat ekvivalentní `Const` příkazy ke třídě nebo modul pro zpřístupnění těchto konstanty pro vaše aplikace.</span><span class="sxs-lookup"><span data-stu-id="be007-159">Add equivalent `Const` statements to your class or module to make these constants available to your application.</span></span> <span data-ttu-id="be007-160">Příklad:</span><span class="sxs-lookup"><span data-stu-id="be007-160">For example:</span></span>  
  
     [!code-vb[VbVbalrInterop#11](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_2.vb)]  
  
###### <a name="to-call-the-dll-procedure"></a><span data-ttu-id="be007-161">Voláním procedury knihovny DLL</span><span class="sxs-lookup"><span data-stu-id="be007-161">To call the DLL procedure</span></span>  
  
1.  <span data-ttu-id="be007-162">Přidání tlačítka s názvem `Button1` na spuštění tvoří pro svůj projekt a potom dvojím kliknutím zobrazit jeho kód.</span><span class="sxs-lookup"><span data-stu-id="be007-162">Add a button named `Button1` to the startup form for your project, and then double-click it to view its code.</span></span> <span data-ttu-id="be007-163">Obslužné rutiny události pro tlačítko se zobrazí.</span><span class="sxs-lookup"><span data-stu-id="be007-163">The event handler for the button is displayed.</span></span>  
  
2.  <span data-ttu-id="be007-164">Přidejte kód, který `Click` obslužné rutiny události pro tlačítko jste přidali, zavolejte proceduru a zadejte odpovídající argumenty:</span><span class="sxs-lookup"><span data-stu-id="be007-164">Add code to the `Click` event handler for the button you added, to call the procedure and provide the appropriate arguments:</span></span>  
  
     [!code-vb[VbVbalrInterop#12](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_3.vb)]  
  
3.  <span data-ttu-id="be007-165">Stisknutím klávesy F5 spusťte projekt.</span><span class="sxs-lookup"><span data-stu-id="be007-165">Run the project by pressing F5.</span></span> <span data-ttu-id="be007-166">Do pole zpráva se zobrazí s oběma **Ano** a **ne** tlačítka odpovědi.</span><span class="sxs-lookup"><span data-stu-id="be007-166">The message box is displayed with both **Yes** and **No** response buttons.</span></span> <span data-ttu-id="be007-167">Klikněte na některý.</span><span class="sxs-lookup"><span data-stu-id="be007-167">Click either one.</span></span>  
  
#### <a name="data-marshaling"></a><span data-ttu-id="be007-168">Dat – zařazování</span><span class="sxs-lookup"><span data-stu-id="be007-168">Data Marshaling</span></span>  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="be007-169">automaticky můžete použít datové typy parametry a návratové hodnoty pro volání rozhraní API systému Windows, ale převede `MarshalAs` atribut k explicitnímu zadání nespravované datové typy, které očekává rozhraní API.</span><span class="sxs-lookup"><span data-stu-id="be007-169"> automatically converts the data types of parameters and return values for Windows API calls, but you can use the `MarshalAs` attribute to explicitly specify unmanaged data types that an API expects.</span></span> <span data-ttu-id="be007-170">Další informace o zařazování spolupráce najdete v tématu [zařazování zprostředkovatel komunikace s objekty](../../../framework/interop/interop-marshaling.md).</span><span class="sxs-lookup"><span data-stu-id="be007-170">For more information about interop marshaling, see [Interop Marshaling](../../../framework/interop/interop-marshaling.md).</span></span>  
  
###### <a name="to-use-declare-and-marshalas-in-an-api-call"></a><span data-ttu-id="be007-171">Použití Declare a MarshalAs volání rozhraní API</span><span class="sxs-lookup"><span data-stu-id="be007-171">To use Declare and MarshalAs in an API call</span></span>  
  
1.  <span data-ttu-id="be007-172">Určení názvu funkce chcete volat plus její argumenty datových typů a vrátit hodnotu.</span><span class="sxs-lookup"><span data-stu-id="be007-172">Determine the name of the function you want to call, plus its arguments, data types, and return value.</span></span>  
  
2.  <span data-ttu-id="be007-173">Zjednodušení přístupu k `MarshalAs` atribut, přidejte `Imports` příkaz do horní části kód pro třídu nebo modul, jako v následujícím příkladu:</span><span class="sxs-lookup"><span data-stu-id="be007-173">To simplify access to the `MarshalAs` attribute, add an `Imports` statement to the top of the code for the class or module, as in the following example:</span></span>  
  
     [!code-vb[VbVbalrInterop#13](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_4.vb)]  
  
3.  <span data-ttu-id="be007-174">Přidejte prototyp funkce pro importované funkce ke třídě nebo modul a použít `MarshalAs` atribut parametry nebo vrací hodnotu.</span><span class="sxs-lookup"><span data-stu-id="be007-174">Add a function prototype for the imported function to the class or module you are using, and apply the `MarshalAs` attribute to the parameters or return value.</span></span> <span data-ttu-id="be007-175">V následujícím příkladu volání rozhraní API, která očekává typ `void*` je zařazené jako `AsAny`:</span><span class="sxs-lookup"><span data-stu-id="be007-175">In the following example, an API call that expects the type `void*` is marshaled as `AsAny`:</span></span>  
  
     [!code-vb[VbVbalrInterop#14](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_5.vb)]  
  
## <a name="api-calls-using-dllimport"></a><span data-ttu-id="be007-176">Volání rozhraní API pomocí příkazů DllImport</span><span class="sxs-lookup"><span data-stu-id="be007-176">API Calls Using DllImport</span></span>  
 <span data-ttu-id="be007-177">`DllImport` Atribut poskytuje druhý způsob, jak volat funkce v knihovnách DLL bez knihovny typů.</span><span class="sxs-lookup"><span data-stu-id="be007-177">The `DllImport` attribute provides a second way to call functions in DLLs without type libraries.</span></span> <span data-ttu-id="be007-178">`DllImport`zhruba odpovídá pomocí `Declare` příkaz ale nabízí větší kontrolu nad jak se označují jako funkce.</span><span class="sxs-lookup"><span data-stu-id="be007-178">`DllImport` is roughly equivalent to using a `Declare` statement but provides more control over how functions are called.</span></span>  
  
 <span data-ttu-id="be007-179">Můžete použít `DllImport` s rozhraním API systému Windows pro většinu volá tak dlouho, dokud volání odkazuje na sdílenou (někdy nazývané *statické*) metoda.</span><span class="sxs-lookup"><span data-stu-id="be007-179">You can use `DllImport` with most Windows API calls as long as the call refers to a shared (sometimes called *static*) method.</span></span> <span data-ttu-id="be007-180">Metody, které vyžadují instance třídy nelze použít.</span><span class="sxs-lookup"><span data-stu-id="be007-180">You cannot use methods that require an instance of a class.</span></span> <span data-ttu-id="be007-181">Na rozdíl od `Declare` příkazy, `DllImport` volání nelze použít `MarshalAs` atribut.</span><span class="sxs-lookup"><span data-stu-id="be007-181">Unlike `Declare` statements, `DllImport` calls cannot use the `MarshalAs` attribute.</span></span>  
  
#### <a name="to-call-a-windows-api-using-the-dllimport-attribute"></a><span data-ttu-id="be007-182">K volání rozhraní API systému Windows pomocí DllImport – atribut</span><span class="sxs-lookup"><span data-stu-id="be007-182">To call a Windows API using the DllImport attribute</span></span>  
  
1.  <span data-ttu-id="be007-183">Otevřete nový projekt aplikace Windows tak, že kliknete na **nový** na **soubor** nabídce a potom kliknutím na **projektu**.</span><span class="sxs-lookup"><span data-stu-id="be007-183">Open a new Windows Application project by clicking **New** on the **File** menu, and then clicking **Project**.</span></span> <span data-ttu-id="be007-184">**Nový projekt** zobrazí se dialogové okno.</span><span class="sxs-lookup"><span data-stu-id="be007-184">The **New Project** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="be007-185">Vyberte **aplikace Windows** ze seznamu [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] šablony projektu.</span><span class="sxs-lookup"><span data-stu-id="be007-185">Select **Windows Application** from the list of [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] project templates.</span></span> <span data-ttu-id="be007-186">Zobrazí se nový projekt.</span><span class="sxs-lookup"><span data-stu-id="be007-186">The new project is displayed.</span></span>  
  
3.  <span data-ttu-id="be007-187">Přidání tlačítka s názvem `Button2` na formulář spuštění.</span><span class="sxs-lookup"><span data-stu-id="be007-187">Add a button named `Button2` to the startup form.</span></span>  
  
4.  <span data-ttu-id="be007-188">Klikněte dvakrát na `Button2` k otevření zobrazení kódu pro daný formulář.</span><span class="sxs-lookup"><span data-stu-id="be007-188">Double-click `Button2` to open the code view for the form.</span></span>  
  
5.  <span data-ttu-id="be007-189">Zjednodušení přístupu k `DllImport`, přidejte `Imports` příkaz do horní části kód pro formulář třída při spuštění:</span><span class="sxs-lookup"><span data-stu-id="be007-189">To simplify access to `DllImport`, add an `Imports` statement to the top of the code for the startup form class:</span></span>  
  
     [!code-vb[VbVbalrInterop#13](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_4.vb)]  
  
6.  <span data-ttu-id="be007-190">Deklarovat prázdný funkce předchozí `End Class` příkaz pro formulář a název funkce `MoveFile`.</span><span class="sxs-lookup"><span data-stu-id="be007-190">Declare an empty function preceding the `End Class` statement for the form, and name the function `MoveFile`.</span></span>  
  
7.  <span data-ttu-id="be007-191">Použít `Public` a `Shared` modifikátory deklarace funkce a nastavení parametrů `MoveFile` podle argumenty funkce rozhraní API systému Windows, která používá:</span><span class="sxs-lookup"><span data-stu-id="be007-191">Apply the `Public` and `Shared` modifiers to the function declaration and set parameters for `MoveFile` based on the arguments the Windows API function uses:</span></span>  
  
     [!code-vb[VbVbalrInterop#16](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_6.vb)]  
  
     <span data-ttu-id="be007-192">Funkce může mít libovolný název platný postupu; `DllImport` atribut určuje název v knihovně DLL.</span><span class="sxs-lookup"><span data-stu-id="be007-192">Your function can have any valid procedure name; the `DllImport` attribute specifies the name in the DLL.</span></span> <span data-ttu-id="be007-193">Také obstará interoperabilita zařazování pro parametry a návratové hodnoty, abyste si mohli vybrat Visual Studio datové typy, které jsou podobné data typy používá rozhraní API.</span><span class="sxs-lookup"><span data-stu-id="be007-193">It also handles interoperability marshaling for the parameters and return values, so you can choose Visual Studio data types that are similar to the data types the API uses.</span></span>  
  
8.  <span data-ttu-id="be007-194">Použít `DllImport` atribut funkci prázdný.</span><span class="sxs-lookup"><span data-stu-id="be007-194">Apply the `DllImport` attribute to the empty function.</span></span> <span data-ttu-id="be007-195">První parametr je název a umístění knihovny DLL obsahující danou funkci, ke kterému se připojujete.</span><span class="sxs-lookup"><span data-stu-id="be007-195">The first parameter is the name and location of the DLL containing the function you are calling.</span></span> <span data-ttu-id="be007-196">Není nutné zadat cestu pro soubory uložené v adresáři systému Windows.</span><span class="sxs-lookup"><span data-stu-id="be007-196">You do not need to specify the path for files located in the Windows system directories.</span></span> <span data-ttu-id="be007-197">Druhý parametr je pojmenovaný argument, který určuje název funkce v rozhraní API systému Windows.</span><span class="sxs-lookup"><span data-stu-id="be007-197">The second parameter is a named argument that specifies the name of the function in the Windows API.</span></span> <span data-ttu-id="be007-198">V tomto příkladu `DllImport` atribut vynutí volání `MoveFile` k přeposlání do `MoveFileW` v KERNEL32. KNIHOVNY DLL.</span><span class="sxs-lookup"><span data-stu-id="be007-198">In this example, the `DllImport` attribute forces calls to `MoveFile` to be forwarded to `MoveFileW` in KERNEL32.DLL.</span></span> <span data-ttu-id="be007-199">`MoveFileW` Metoda zkopíruje do souboru z cesty `src` k cestě `dst`.</span><span class="sxs-lookup"><span data-stu-id="be007-199">The `MoveFileW` method copies a file from the path `src` to the path `dst`.</span></span>  
  
     [!code-vb[VbVbalrInterop#17](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_7.vb)]  
  
9. <span data-ttu-id="be007-200">Přidejte kód, který `Button2_Click` obslužné rutiny události pro volání funkce:</span><span class="sxs-lookup"><span data-stu-id="be007-200">Add code to the `Button2_Click` event handler to call the function:</span></span>  
  
     [!code-vb[VbVbalrInterop#18](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_8.vb)]  
  
10. <span data-ttu-id="be007-201">Vytvořte soubor s názvem Test.txt a umístěte jej do adresáře C:\Tmp na vašem pevném disku.</span><span class="sxs-lookup"><span data-stu-id="be007-201">Create a file named Test.txt and place it in the C:\Tmp directory on your hard drive.</span></span> <span data-ttu-id="be007-202">Vytvoření adresáře Tmp v případě potřeby.</span><span class="sxs-lookup"><span data-stu-id="be007-202">Create the Tmp directory if necessary.</span></span>  
  
11. <span data-ttu-id="be007-203">Stisknutím klávesy F5 a spusťte aplikaci.</span><span class="sxs-lookup"><span data-stu-id="be007-203">Press F5 to start the application.</span></span> <span data-ttu-id="be007-204">Zobrazí se hlavní formulář.</span><span class="sxs-lookup"><span data-stu-id="be007-204">The main form appears.</span></span>  
  
12. <span data-ttu-id="be007-205">Klikněte na tlačítko **Button2**.</span><span class="sxs-lookup"><span data-stu-id="be007-205">Click **Button2**.</span></span> <span data-ttu-id="be007-206">Pokud soubor můžete přesunout, zobrazí se zpráva "soubor byl úspěšně přesunut.".</span><span class="sxs-lookup"><span data-stu-id="be007-206">The message "The file was moved successfully" is displayed if the file can be moved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be007-207">Viz také</span><span class="sxs-lookup"><span data-stu-id="be007-207">See Also</span></span>  
 <xref:System.Runtime.InteropServices.DllImportAttribute>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="be007-208">Declare – příkaz</span><span class="sxs-lookup"><span data-stu-id="be007-208">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [<span data-ttu-id="be007-209">Automaticky</span><span class="sxs-lookup"><span data-stu-id="be007-209">Auto</span></span>](../../../visual-basic/language-reference/modifiers/auto.md)  
 [<span data-ttu-id="be007-210">Alias</span><span class="sxs-lookup"><span data-stu-id="be007-210">Alias</span></span>](../../../visual-basic/language-reference/statements/alias-clause.md)  
 [<span data-ttu-id="be007-211">Zprostředkovatel komunikace s objekty COM</span><span class="sxs-lookup"><span data-stu-id="be007-211">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)  
 [<span data-ttu-id="be007-212">Vytváření prototypů ve spravovaném kódu</span><span class="sxs-lookup"><span data-stu-id="be007-212">Creating Prototypes in Managed Code</span></span>](../../../framework/interop/creating-prototypes-in-managed-code.md)  
 [<span data-ttu-id="be007-213">Zařazování delegáta jako metody zpětného volání</span><span class="sxs-lookup"><span data-stu-id="be007-213">Marshaling a Delegate as a Callback Method</span></span>](../../../framework/interop/marshaling-a-delegate-as-a-callback-method.md)
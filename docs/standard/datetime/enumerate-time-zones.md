---
title: "Postupy: vytvoření výčtu časových pásem přítomných na počítači"
ms.custom: 
ms.date: 04/10/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], enumerating
- enumerating time zones [.NET Framework]
ms.assetid: bb7a42ab-6bd9-4c5c-b734-5546d51f8669
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f77afc8a0f2e6c110f4dc037c12ecc8b06908e60
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-enumerate-time-zones-present-on-a-computer"></a><span data-ttu-id="159e8-102">Postupy: vytvoření výčtu časových pásem přítomných na počítači</span><span class="sxs-lookup"><span data-stu-id="159e8-102">How to: Enumerate time zones present on a computer</span></span>

<span data-ttu-id="159e8-103">Úspěšně spolupracuje s určeným časovým pásmem vyžaduje, aby informace o tomto časové pásmo k dispozici v systému.</span><span class="sxs-lookup"><span data-stu-id="159e8-103">Successfully working with a designated time zone requires that information about that time zone be available to the system.</span></span> <span data-ttu-id="159e8-104">Operační systémy Windows XP a Windows Vista uložit tyto informace v registru.</span><span class="sxs-lookup"><span data-stu-id="159e8-104">The Windows XP and Windows Vista operating systems store this information in the registry.</span></span> <span data-ttu-id="159e8-105">Ale sice velká celkový počet časových pásem, které existují v celém světě, registr obsahuje informace o pouze podmnožinu z nich.</span><span class="sxs-lookup"><span data-stu-id="159e8-105">However, although the total number of time zones that exist throughout the world is large, the registry contains information about only a subset of them.</span></span> <span data-ttu-id="159e8-106">Kromě toho je registr je dynamické struktura, jejichž obsah se mohou změnit záměrné i náhodných.</span><span class="sxs-lookup"><span data-stu-id="159e8-106">In addition, the registry itself is a dynamic structure whose contents are subject to both deliberate and accidental change.</span></span> <span data-ttu-id="159e8-107">V důsledku toho aplikace nelze vždy předpokládat, že konkrétní časové pásmo je definovaný a k dispozici v systému.</span><span class="sxs-lookup"><span data-stu-id="159e8-107">As a result, an application cannot always assume that a particular time zone is defined and available on a system.</span></span> <span data-ttu-id="159e8-108">Prvním krokem pro mnoho aplikací, které používají aplikace informace o časovém pásmu je určit, zda jsou k dispozici v místním systému požadované časová pásma nebo uživateli přidělit seznam časových pásem ze které chcete vybrat.</span><span class="sxs-lookup"><span data-stu-id="159e8-108">The first step for many applications that use time zone information applications is to determine whether required time zones are available on the local system, or to give the user a list of time zones from which to select.</span></span> <span data-ttu-id="159e8-109">To vyžaduje, aby aplikace výčet časových pásem definovaných v lokálním systému.</span><span class="sxs-lookup"><span data-stu-id="159e8-109">This requires that an application enumerate the time zones defined on a local system.</span></span>

> [!NOTE]
> <span data-ttu-id="159e8-110">Pokud aplikace spoléhá na přítomnost konkrétní časové pásmo, které nemusí být definován v lokálním systému, aplikace můžete zajistit jeho přítomnosti serializaci a deserializaci informace o časovém pásmu.</span><span class="sxs-lookup"><span data-stu-id="159e8-110">If an application relies on the presence of a particular time zone that may not be defined on a local system, the application can ensure its presence by serializing and deserializing information about the time zone.</span></span> <span data-ttu-id="159e8-111">Časové pásmo poté lze přidat do ovládacího prvku seznam tak, aby uživatel aplikace můžete ji vybrat.</span><span class="sxs-lookup"><span data-stu-id="159e8-111">The time zone can then be added to a list control so that the application user can select it.</span></span> <span data-ttu-id="159e8-112">Podrobnosti najdete v tématu [postupy: ukládání časových pásem do vloženého prostředku](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) a [postupy: obnovení časových pásem ze vloženého prostředku](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md).</span><span class="sxs-lookup"><span data-stu-id="159e8-112">For details, see [How to: Save Time Zones to an Embedded Resource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) and [How to: Restore time zones from an embedded resource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md).</span></span>

### <a name="to-enumerate-the-time-zones-present-on-the-local-system"></a><span data-ttu-id="159e8-113">Výčet časových pásem přítomných v lokálním systému</span><span class="sxs-lookup"><span data-stu-id="159e8-113">To enumerate the time zones present on the local system</span></span>

1. <span data-ttu-id="159e8-114">Volání <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType> metoda.</span><span class="sxs-lookup"><span data-stu-id="159e8-114">Call the <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="159e8-115">Metoda vrátí obecnou <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> kolekce <xref:System.TimeZoneInfo> objekty.</span><span class="sxs-lookup"><span data-stu-id="159e8-115">The method returns a generic <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> collection of <xref:System.TimeZoneInfo> objects.</span></span> <span data-ttu-id="159e8-116">Položky v kolekci jsou seřazeny podle jejich <xref:System.TimeZoneInfo.DisplayName%2A> vlastnost.</span><span class="sxs-lookup"><span data-stu-id="159e8-116">The entries in the collection are sorted by their <xref:System.TimeZoneInfo.DisplayName%2A> property.</span></span> <span data-ttu-id="159e8-117">Příklad:</span><span class="sxs-lookup"><span data-stu-id="159e8-117">For example:</span></span>

   [!code-csharp[System.TimeZone2.Concepts#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#1)]
   [!code-vb[System.TimeZone2.Concepts#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#1)]

2. <span data-ttu-id="159e8-118">Zobrazení výčtu jednotlivých <xref:System.TimeZoneInfo> objektů v kolekcích pomocí `foreach` smyčky (v jazyku C#) nebo `For Each`...`Next`</span><span class="sxs-lookup"><span data-stu-id="159e8-118">Enumerate the individual <xref:System.TimeZoneInfo> objects in the collection by using a `foreach` loop (in C#) or a `For Each`…`Next`</span></span> <span data-ttu-id="159e8-119">smyčky (v jazyce Visual Basic) a proveďte všechny nezbytné zpracování pro každý objekt.</span><span class="sxs-lookup"><span data-stu-id="159e8-119">loop (in Visual Basic), and perform any necessary processing on each object.</span></span> <span data-ttu-id="159e8-120">Například následující kód vytvoří výčet <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> kolekce <xref:System.TimeZoneInfo> objektů vrácených v kroku 1 a vypíše zobrazovaný název každého časového pásma v konzole.</span><span class="sxs-lookup"><span data-stu-id="159e8-120">For example, the following code enumerates the <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> collection of <xref:System.TimeZoneInfo> objects returned in step 1 and lists the display name of each time zone on the console.</span></span>

   [!code-csharp[System.TimeZone2.Concepts#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#12)]
   [!code-vb[System.TimeZone2.Concepts#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#12)]

### <a name="to-present-the-user-with-a-list-of-time-zones-present-on-the-local-system"></a><span data-ttu-id="159e8-121">Možnost prezentovat seznam časových pásem v místním systému</span><span class="sxs-lookup"><span data-stu-id="159e8-121">To present the user with a list of time zones present on the local system</span></span>

1. <span data-ttu-id="159e8-122">Volání <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType> metoda.</span><span class="sxs-lookup"><span data-stu-id="159e8-122">Call the <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="159e8-123">Metoda vrátí obecnou <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> kolekce <xref:System.TimeZoneInfo> objekty.</span><span class="sxs-lookup"><span data-stu-id="159e8-123">The method returns a generic <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> collection of <xref:System.TimeZoneInfo> objects.</span></span>

2. <span data-ttu-id="159e8-124">Přiřadit kolekci vrácenou v kroku 1 `DataSource` vlastností ovládacího prvku Windows forms nebo v technologii ASP.NET ovládací prvek seznamu.</span><span class="sxs-lookup"><span data-stu-id="159e8-124">Assign the collection returned in step 1 to the `DataSource` property of a Windows forms or ASP.NET list control.</span></span>

3. <span data-ttu-id="159e8-125">Načtení <xref:System.TimeZoneInfo> objekt, který uživatel vybral.</span><span class="sxs-lookup"><span data-stu-id="159e8-125">Retrieve the <xref:System.TimeZoneInfo> object that the user has selected.</span></span>

<span data-ttu-id="159e8-126">Příklad uvádí ukázku pro aplikaci systému Windows.</span><span class="sxs-lookup"><span data-stu-id="159e8-126">The example provides an illustration for a Windows application.</span></span>

## <a name="example"></a><span data-ttu-id="159e8-127">Příklad</span><span class="sxs-lookup"><span data-stu-id="159e8-127">Example</span></span>

<span data-ttu-id="159e8-128">V příkladu se spustí aplikace systému Windows, která zobrazuje časových pásem definovaných v systému v seznamu.</span><span class="sxs-lookup"><span data-stu-id="159e8-128">The example starts a Windows application that displays the time zones defined on a system in a list box.</span></span> <span data-ttu-id="159e8-129">V příkladu se pak zobrazí dialogové okno, které obsahuje hodnotu <xref:System.TimeZoneInfo.DisplayName%2A> vlastnost objektu časové pásmo vybraný uživatelem.</span><span class="sxs-lookup"><span data-stu-id="159e8-129">The example then displays a dialog box that contains the value of the <xref:System.TimeZoneInfo.DisplayName%2A> property of the time zone object selected by the user.</span></span>

[!code-csharp[System.TimeZone2.Concepts#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#2)]
[!code-vb[System.TimeZone2.Concepts#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#2)]

<span data-ttu-id="159e8-130">Nejvíce seznamu ovládacích prvků (, jako <xref:System.Windows.Forms.ListBox?displayProperty=nameWithType> nebo <xref:System.Web.UI.WebControls.BulletedList?displayProperty=nameWithType> ovládací prvek) umožňují přiřadit kolekci objektové proměnné, jejich `DataSource` vlastnost, pokud implementuje tuto kolekci <xref:System.Collections.IEnumerable> rozhraní.</span><span class="sxs-lookup"><span data-stu-id="159e8-130">Most list controls (such as the <xref:System.Windows.Forms.ListBox?displayProperty=nameWithType> or <xref:System.Web.UI.WebControls.BulletedList?displayProperty=nameWithType> control) allow you to assign a collection of object variables to their `DataSource` property as long as that collection implements the <xref:System.Collections.IEnumerable> interface.</span></span> <span data-ttu-id="159e8-131">(Obecná <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> třída tomu.) K zobrazení jednotlivých objektů v kolekci, ovládací prvek volá tento objekt `ToString` metoda extrahování řetězec, který se používá k reprezentaci objektu.</span><span class="sxs-lookup"><span data-stu-id="159e8-131">(The generic <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> class does this.) To display an individual object in the collection, the control calls that object's `ToString` method to extract the string that is used to represent the object.</span></span> <span data-ttu-id="159e8-132">U <xref:System.TimeZoneInfo> objekty, `ToString` metoda vrátí <xref:System.TimeZoneInfo> zobrazovaný název objektu (hodnota jeho <xref:System.TimeZoneInfo.DisplayName%2A> vlastnost).</span><span class="sxs-lookup"><span data-stu-id="159e8-132">In the case of <xref:System.TimeZoneInfo> objects, the `ToString` method returns the <xref:System.TimeZoneInfo> object's display name (the value of its <xref:System.TimeZoneInfo.DisplayName%2A> property).</span></span>

> [!NOTE]
> <span data-ttu-id="159e8-133">Protože ovládací prvky seznamu volání objektu `ToString` metodu, můžete přiřadit kolekci <xref:System.TimeZoneInfo> objekty do ovládacího prvku, mají ovládacího prvku zobrazení nějaký výstižný název pro každý objekt a načíst <xref:System.TimeZoneInfo> objekt, který uživatel vybral.</span><span class="sxs-lookup"><span data-stu-id="159e8-133">Because list controls call an object's `ToString` method, you can assign a collection of <xref:System.TimeZoneInfo> objects to the control, have the control display a meaningful name for each object, and retrieve the <xref:System.TimeZoneInfo> object that the user has selected.</span></span> <span data-ttu-id="159e8-134">Tím se eliminuje potřeba extrahovat řetězec pro každý objekt v kolekci, přiřadit řetězec do kolekce, která je pak přiřazen k ovládacímu prvku `DataSource` vlastnost načíst řetězec uživatel vybral a pak použijte tento řetězec k extrakci objektu Popisuje, že IT oddělení.</span><span class="sxs-lookup"><span data-stu-id="159e8-134">This eliminates the need to extract a string for each object in the collection, assign the string to a collection that is in turn assigned to the control's `DataSource` property, retrieve the string the user has selected, and then use this string to extract the object that it describes.</span></span> 

## <a name="compiling-the-code"></a><span data-ttu-id="159e8-135">Probíhá kompilace kódu</span><span class="sxs-lookup"><span data-stu-id="159e8-135">Compiling the code</span></span>

<span data-ttu-id="159e8-136">Tento příklad vyžaduje:</span><span class="sxs-lookup"><span data-stu-id="159e8-136">This example requires:</span></span>

* <span data-ttu-id="159e8-137">Aby byl přidán odkaz na System.Core.dll do projektu.</span><span class="sxs-lookup"><span data-stu-id="159e8-137">That a reference to System.Core.dll be added to the project.</span></span>

* <span data-ttu-id="159e8-138">Aby byly importované následujících oborů názvů:</span><span class="sxs-lookup"><span data-stu-id="159e8-138">That the following namespaces be imported:</span></span>

  <span data-ttu-id="159e8-139"><xref:System>(v kódu jazyka C#)</span><span class="sxs-lookup"><span data-stu-id="159e8-139"><xref:System> (in C# code)</span></span>

  <xref:System.Collections.ObjectModel>

## <a name="see-also"></a><span data-ttu-id="159e8-140">Viz také</span><span class="sxs-lookup"><span data-stu-id="159e8-140">See also</span></span>

<span data-ttu-id="159e8-141">[Data, časy a časová pásma](../../../docs/standard/datetime/index.md)
[postupy: ukládání časových pásem do vloženého prostředku](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)
[postupy: obnovení časových pásem ze vloženého prostředku](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)</span><span class="sxs-lookup"><span data-stu-id="159e8-141">[Dates, times, and time zones](../../../docs/standard/datetime/index.md)
[How to: Save time zones to an embedded resource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)
[How to: Restore time zones from an embedded resource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)</span></span>
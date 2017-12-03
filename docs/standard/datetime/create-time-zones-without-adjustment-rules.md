---
title: "Postupy: vytváření časových pásem bez pravidel úpravy"
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
- time zones [.NET Framework], adjustment rule
- time zones [.NET Framework], creating
- adjustment rule [.NET Framework]
ms.assetid: a6af8647-7893-4f29-95a9-d94c65a6e8dd
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 181d61de62ec9560b46732ad304b4934d4f55fa2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-create-time-zones-without-adjustment-rules"></a><span data-ttu-id="6a126-102">Postupy: vytváření časových pásem bez pravidel úpravy</span><span class="sxs-lookup"><span data-stu-id="6a126-102">How to: Create time zones without adjustment rules</span></span>

<span data-ttu-id="6a126-103">Informace o přesné časovém pásmu, který je požadován pro aplikace nemusí být na určitém systému k dispozici pro několik důvodů:</span><span class="sxs-lookup"><span data-stu-id="6a126-103">The precise time zone information that is required by an application may not be present on a particular system for several reasons:</span></span>

* <span data-ttu-id="6a126-104">Časové pásmo nikdy byla definována v registru místního systému.</span><span class="sxs-lookup"><span data-stu-id="6a126-104">The time zone has never been defined in the local system's registry.</span></span>

* <span data-ttu-id="6a126-105">Data o časovém pásmu byl změněn nebo odstraněn z registru.</span><span class="sxs-lookup"><span data-stu-id="6a126-105">Data about the time zone has been modified or removed from the registry.</span></span>

* <span data-ttu-id="6a126-106">Časové pásmo existuje, ale nemá přesné informace o úpravách časové pásmo pro určité historické období.</span><span class="sxs-lookup"><span data-stu-id="6a126-106">The time zone exists but does not have accurate information about time zone adjustments for a particular historic period.</span></span>

<span data-ttu-id="6a126-107">V těchto případech můžete volat <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> metoda definovat časové pásmo požadované aplikací.</span><span class="sxs-lookup"><span data-stu-id="6a126-107">In these cases, you can call the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method to define the time zone required by your application.</span></span> <span data-ttu-id="6a126-108">Přetížení této metody můžete vytvořit časové pásmo s nebo bez pravidel úpravy.</span><span class="sxs-lookup"><span data-stu-id="6a126-108">You can use the overloads of this method to create a time zone with or without adjustment rules.</span></span> <span data-ttu-id="6a126-109">Pokud se časové pásmo podporuje letní čas, můžete definovat úpravy s pravidly buď pevné nebo plovoucí úpravy.</span><span class="sxs-lookup"><span data-stu-id="6a126-109">If the time zone supports daylight saving time, you can define adjustments with either fixed or floating adjustment rules.</span></span> <span data-ttu-id="6a126-110">(Pro definice těchto podmínkách, najdete v části "Časové pásmo terminologií" v [Přehled časových pásem](../../../docs/standard/datetime/time-zone-overview.md).)</span><span class="sxs-lookup"><span data-stu-id="6a126-110">(For definitions of these terms, see the "Time Zone Terminology" section in [Time zone overview](../../../docs/standard/datetime/time-zone-overview.md).)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6a126-111">Vlastní časová pásma vytvořená voláním <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> metoda nejsou přidány do registru.</span><span class="sxs-lookup"><span data-stu-id="6a126-111">Custom time zones created by calling the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method are not added to the registry.</span></span> <span data-ttu-id="6a126-112">Místo toho jsou dostupné pouze prostřednictvím odkazu na objekt vrácený <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> volání metody.</span><span class="sxs-lookup"><span data-stu-id="6a126-112">Instead, they can be accessed only through the object reference returned by the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method call.</span></span>

<span data-ttu-id="6a126-113">Toto téma ukazuje, jak vytvořit časové pásmo bez pravidel úpravy.</span><span class="sxs-lookup"><span data-stu-id="6a126-113">This topic shows how to create a time zone without adjustment rules.</span></span> <span data-ttu-id="6a126-114">Vytvoření časové pásmo, které podporuje pravidla úpravy letního času naleznete v tématu [postupy: vytváření časových pásem s pravidly úpravy](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md).</span><span class="sxs-lookup"><span data-stu-id="6a126-114">To create a time zone that supports daylight saving time adjustment rules, see [How to: Create time zones with adjustment rules](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md).</span></span>

### <a name="to-create-a-time-zone-without-adjustment-rules"></a><span data-ttu-id="6a126-115">Chcete-li vytvořit časové pásmo bez pravidel úpravy</span><span class="sxs-lookup"><span data-stu-id="6a126-115">To create a time zone without adjustment rules</span></span>

1. <span data-ttu-id="6a126-116">Definujte časové pásmo zobrazovaný název.</span><span class="sxs-lookup"><span data-stu-id="6a126-116">Define the time zone's display name.</span></span>

   <span data-ttu-id="6a126-117">Zobrazovaný název následuje poměrně standardní formát, ve kterém posun časového pásma z koordinovaný světový čas (UTC) uzavřený v závorkách a následuje řetězec, který identifikuje časové pásmo, jeden nebo více měst v časovém pásmu, nebo v jednom nebo více cou oložky nebo oblasti v časovém pásmu.</span><span class="sxs-lookup"><span data-stu-id="6a126-117">The display name follows a fairly standard format in which the time zone's offset from Coordinated Universal Time (UTC) is enclosed in parentheses and is followed by a string that identifies the time zone, one or more of the cities in the time zone, or one or more of the countries or regions in the time zone.</span></span>

2. <span data-ttu-id="6a126-118">Definuje název časové pásmo (běžný čas).</span><span class="sxs-lookup"><span data-stu-id="6a126-118">Define the name of the time zone's standard time.</span></span> <span data-ttu-id="6a126-119">Obvykle se tento řetězec se používá jako identifikátor časového pásma.</span><span class="sxs-lookup"><span data-stu-id="6a126-119">Typically, this string is also used as the time zone's identifier.</span></span>

3. <span data-ttu-id="6a126-120">Pokud chcete použít jiný identifikátor než standardní název časového pásma, definujte identifikátor časového pásma.</span><span class="sxs-lookup"><span data-stu-id="6a126-120">If you want to use a different identifier than the time zone's standard name, define the time zone identifier.</span></span>

4. <span data-ttu-id="6a126-121">Vytváření instancí <xref:System.TimeSpan> objekt, který definuje posun časového pásma od času UTC.</span><span class="sxs-lookup"><span data-stu-id="6a126-121">Instantiate a <xref:System.TimeSpan> object that defines the time zone's offset from UTC.</span></span> <span data-ttu-id="6a126-122">Časová pásma s časy, které jsou novější než čas UTC mít kladný posun.</span><span class="sxs-lookup"><span data-stu-id="6a126-122">Time zones with times that are later than UTC have a positive offset.</span></span> <span data-ttu-id="6a126-123">Časová pásma s časy, které jsou starší než čas UTC mít záporný posun.</span><span class="sxs-lookup"><span data-stu-id="6a126-123">Time zones with times that are earlier than UTC have a negative offset.</span></span>

5. <span data-ttu-id="6a126-124">Volání <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%29?displayProperty=nameWithType> metoda pro vytvoření instance nového časového pásma.</span><span class="sxs-lookup"><span data-stu-id="6a126-124">Call the <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%29?displayProperty=nameWithType> method to instantiate the new time zone.</span></span>

## <a name="example"></a><span data-ttu-id="6a126-125">Příklad</span><span class="sxs-lookup"><span data-stu-id="6a126-125">Example</span></span>

<span data-ttu-id="6a126-126">V následujícím příkladu definuje vlastní časové pásmo pro Mawson, Antarctica, který nemá žádná pravidla úprav.</span><span class="sxs-lookup"><span data-stu-id="6a126-126">The following example defines a custom time zone for Mawson, Antarctica, which has no adjustment rules.</span></span>

[!code-csharp[System.TimeZone2.CreateTimeZone#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#1)]
[!code-vb[System.TimeZone2.CreateTimeZone#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#1)]

<span data-ttu-id="6a126-127">Řetězec přiřazený k <xref:System.TimeZoneInfo.DisplayName%2A> vlastnost následuje standardní formát, ve kterém je posun časového pásma od času UTC Následuje stručný popis časové pásmo.</span><span class="sxs-lookup"><span data-stu-id="6a126-127">The string assigned to the <xref:System.TimeZoneInfo.DisplayName%2A> property follows a standard format in which the time zone's offset from UTC is followed by a friendly description of the time zone.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="6a126-128">Probíhá kompilace kódu</span><span class="sxs-lookup"><span data-stu-id="6a126-128">Compiling the code</span></span>

<span data-ttu-id="6a126-129">Tento příklad vyžaduje:</span><span class="sxs-lookup"><span data-stu-id="6a126-129">This example requires:</span></span>

* <span data-ttu-id="6a126-130">Aby byl přidán odkaz na System.Core.dll do projektu.</span><span class="sxs-lookup"><span data-stu-id="6a126-130">That a reference to System.Core.dll be added to the project.</span></span>

* <span data-ttu-id="6a126-131">Aby byly importované následujících oborů názvů:</span><span class="sxs-lookup"><span data-stu-id="6a126-131">That the following namespaces be imported:</span></span>

  [!code-csharp[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#6)]
  [!code-vb[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#6)]

## <a name="see-also"></a><span data-ttu-id="6a126-132">Viz také</span><span class="sxs-lookup"><span data-stu-id="6a126-132">See also</span></span>

<span data-ttu-id="6a126-133">[Data, časy a časová pásma](../../../docs/standard/datetime/index.md)
[Přehled časových pásem](../../../docs/standard/datetime/time-zone-overview.md)
[postupy: vytváření časových pásem s pravidly úpravy](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)</span><span class="sxs-lookup"><span data-stu-id="6a126-133">[Dates, times, and time zones](../../../docs/standard/datetime/index.md)
[Time zone overview](../../../docs/standard/datetime/time-zone-overview.md)
[How to: Create time zones with adjustment rules](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)</span></span>
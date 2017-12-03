---
title: "Postupy: Zadejte, kteří členové jsou testovány konflikty souběžnosti"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: d2cda293-1e2f-4878-af0e-5aaf0d092120
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 6c13c5d6578f27155b87744ed8730f5fae2e1e25
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-which-members-are-tested-for-concurrency-conflicts"></a><span data-ttu-id="3b864-102">Postupy: Zadejte, kteří členové jsou testovány konflikty souběžnosti</span><span class="sxs-lookup"><span data-stu-id="3b864-102">How to: Specify Which Members are Tested for Concurrency Conflicts</span></span>
<span data-ttu-id="3b864-103">Používání jedné do tří výčty [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> vlastnost na <xref:System.Data.Linq.Mapping.ColumnAttribute> kontroluje atribut k určení členy, které mají být zahrnuty v aktualizaci pro zjišťování konfliktů optimistickou metodu souběžného.</span><span class="sxs-lookup"><span data-stu-id="3b864-103">Apply one of three enums to the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property on a <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to specify which members are to be included in update checks for the detection of optimistic concurrency conflicts.</span></span>  
  
 <span data-ttu-id="3b864-104"><xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> Vlastnost (mapovat v době návrhu) se používá spolu s funkcí concurrency Runtime v [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3b864-104">The <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property (mapped at design time) is used together with run-time concurrency features in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="3b864-105">Další informace najdete v tématu [optimistickou metodu souběžného: Přehled](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span><span class="sxs-lookup"><span data-stu-id="3b864-105">For more information, see [Optimistic Concurrency: Overview](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3b864-106">Původní hodnoty členů jsou porovnávány s aktuálním stavem databáze, tak dlouho, dokud žádné je označena jako `IsVersion=true`.</span><span class="sxs-lookup"><span data-stu-id="3b864-106">Original member values are compared with the current database state as long as no member is designated as `IsVersion=true`.</span></span> <span data-ttu-id="3b864-107">Další informace naleznete v tématu <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span><span class="sxs-lookup"><span data-stu-id="3b864-107">For more information, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span></span>  
  
 <span data-ttu-id="3b864-108">Příklady kódu najdete v tématu <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span><span class="sxs-lookup"><span data-stu-id="3b864-108">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span></span>  
  
### <a name="to-always-use-this-member-for-detecting-conflicts"></a><span data-ttu-id="3b864-109">Vždy nutné použít tento člen pro zjišťování konfliktů</span><span class="sxs-lookup"><span data-stu-id="3b864-109">To always use this member for detecting conflicts</span></span>  
  
1.  <span data-ttu-id="3b864-110">Přidat <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> vlastnost, která má <xref:System.Data.Linq.Mapping.ColumnAttribute> atribut.</span><span class="sxs-lookup"><span data-stu-id="3b864-110">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="3b864-111">Nastavte <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> hodnotu vlastnosti na `Always`.</span><span class="sxs-lookup"><span data-stu-id="3b864-111">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property value to `Always`.</span></span>  
  
### <a name="to-never-use-this-member-for-detecting-conflicts"></a><span data-ttu-id="3b864-112">Nikdy používat tento člen pro zjišťování konfliktů</span><span class="sxs-lookup"><span data-stu-id="3b864-112">To never use this member for detecting conflicts</span></span>  
  
1.  <span data-ttu-id="3b864-113">Přidat <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> vlastnost, která má <xref:System.Data.Linq.Mapping.ColumnAttribute> atribut.</span><span class="sxs-lookup"><span data-stu-id="3b864-113">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="3b864-114">Nastavte <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> hodnotu vlastnosti na `Never`.</span><span class="sxs-lookup"><span data-stu-id="3b864-114">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property value to `Never`.</span></span>  
  
### <a name="to-use-this-member-for-detecting-conflicts-only-when-the-application-has-changed-the-value-of-the-member"></a><span data-ttu-id="3b864-115">Chcete-li použít tento člen pro zjišťování konfliktů, pouze v případě, že aplikace byla změněna hodnota člena</span><span class="sxs-lookup"><span data-stu-id="3b864-115">To use this member for detecting conflicts only when the application has changed the value of the member</span></span>  
  
1.  <span data-ttu-id="3b864-116">Přidat <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> vlastnost, která má <xref:System.Data.Linq.Mapping.ColumnAttribute> atribut.</span><span class="sxs-lookup"><span data-stu-id="3b864-116">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="3b864-117">Nastavte <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> hodnotu vlastnosti na `WhenChanged`.</span><span class="sxs-lookup"><span data-stu-id="3b864-117">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> property value to `WhenChanged`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3b864-118">Příklad</span><span class="sxs-lookup"><span data-stu-id="3b864-118">Example</span></span>  
 <span data-ttu-id="3b864-119">Následující příklad určuje, že `HomePage` objekty by měl být vůbec neotestovali během kontroly aktualizací.</span><span class="sxs-lookup"><span data-stu-id="3b864-119">The following example specifies that `HomePage` objects should never be tested during update checks.</span></span> <span data-ttu-id="3b864-120">Další informace naleznete v tématu <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span><span class="sxs-lookup"><span data-stu-id="3b864-120">For more information, see <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span></span>  
  
 [!code-csharp[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.mapping.updatecheck/cs/northwind.cs#1)]
 [!code-vb[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.mapping.updatecheck/vb/northwind.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="3b864-121">Viz také</span><span class="sxs-lookup"><span data-stu-id="3b864-121">See Also</span></span>  
 [<span data-ttu-id="3b864-122">Postupy: Správa je v konfliktu změn</span><span class="sxs-lookup"><span data-stu-id="3b864-122">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)  
 [<span data-ttu-id="3b864-123">Vytvoření a odeslání změn dat</span><span class="sxs-lookup"><span data-stu-id="3b864-123">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
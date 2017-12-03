---
title: "Technologie LINQ to XML přehled programování (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 2dfa9b6f-5890-461d-b81c-316853c7f320
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4306be3540577bf921eff71dbd9dd822707b33dd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="linq-to-xml-programming-overview-c"></a><span data-ttu-id="9798e-102">Technologie LINQ to XML přehled programování (C#)</span><span class="sxs-lookup"><span data-stu-id="9798e-102">LINQ to XML Programming Overview (C#)</span></span>
<span data-ttu-id="9798e-103">Tato témata poskytují informace o základní přehled o [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] třídy a také podrobné informace o tři nejdůležitější tříd.</span><span class="sxs-lookup"><span data-stu-id="9798e-103">These topics provide high-level overview information about the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] classes, as well as detailed information about three of the most important classes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9798e-104">V tomto oddílu</span><span class="sxs-lookup"><span data-stu-id="9798e-104">In This Section</span></span>  
  
|<span data-ttu-id="9798e-105">Téma</span><span class="sxs-lookup"><span data-stu-id="9798e-105">Topic</span></span>|<span data-ttu-id="9798e-106">Popis</span><span class="sxs-lookup"><span data-stu-id="9798e-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="9798e-107">Funkční vs. Procedurální programování (technologie LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="9798e-107">Functional vs. Procedural Programming (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/functional-vs-procedural-programming-linq-to-xml.md)|<span data-ttu-id="9798e-108">Poskytuje nejvyšší úrovni zobrazení dvě Princip přístupy k zápisu LINQ do XML aplikace.</span><span class="sxs-lookup"><span data-stu-id="9798e-108">Provides a high level view of the two principle approaches to writing LINQ to XML applications.</span></span>|  
|[<span data-ttu-id="9798e-109">Technologie LINQ to XML přehled třídy (C#)</span><span class="sxs-lookup"><span data-stu-id="9798e-109">LINQ to XML Classes Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-classes-overview.md)|<span data-ttu-id="9798e-110">Obsahuje přehled [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] třídy.</span><span class="sxs-lookup"><span data-stu-id="9798e-110">Provides an overview of the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] classes.</span></span>|  
|[<span data-ttu-id="9798e-111">Přehled třídy XElement (C#)</span><span class="sxs-lookup"><span data-stu-id="9798e-111">XElement Class Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/xelement-class-overview.md)|<span data-ttu-id="9798e-112">Zavádí <xref:System.Xml.Linq.XElement> třídy, která reprezentuje elementy XML.</span><span class="sxs-lookup"><span data-stu-id="9798e-112">Introduces the <xref:System.Xml.Linq.XElement> class, which represents XML elements.</span></span> <span data-ttu-id="9798e-113"><xref:System.Xml.Linq.XElement>je jednou ze základní třídy v [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] třídy hierarchie.</span><span class="sxs-lookup"><span data-stu-id="9798e-113"><xref:System.Xml.Linq.XElement> is one of the fundamental classes in the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] class hierarchy.</span></span>|  
|[<span data-ttu-id="9798e-114">Přehled třídy XAttribute (C#)</span><span class="sxs-lookup"><span data-stu-id="9798e-114">XAttribute Class Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/xattribute-class-overview.md)|<span data-ttu-id="9798e-115">Zavádí <xref:System.Xml.Linq.XAttribute> třídy, která představuje atributy XML.</span><span class="sxs-lookup"><span data-stu-id="9798e-115">Introduces the <xref:System.Xml.Linq.XAttribute> class, which represents XML attributes.</span></span>|  
|[<span data-ttu-id="9798e-116">Přehled třídy XDocument (C#)</span><span class="sxs-lookup"><span data-stu-id="9798e-116">XDocument Class Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/xdocument-class-overview.md)|<span data-ttu-id="9798e-117">Zavádí <xref:System.Xml.Linq.XDocument> třídy, která představuje dokumentů XML.</span><span class="sxs-lookup"><span data-stu-id="9798e-117">Introduces the <xref:System.Xml.Linq.XDocument> class, which represents XML documents.</span></span>|  
|[<span data-ttu-id="9798e-118">Postupy: sestavení technologie LINQ to XML Příklady (C#)</span><span class="sxs-lookup"><span data-stu-id="9798e-118">How to: Build LINQ to XML Examples (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-build-linq-to-xml-examples.md)|<span data-ttu-id="9798e-119">Obsahuje `Using` direktivy, které jsou nutné k vytvoření LINQ to XML příklady.</span><span class="sxs-lookup"><span data-stu-id="9798e-119">Contains the `Using` directives that are required to build the LINQ to XML examples.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9798e-120">Viz také</span><span class="sxs-lookup"><span data-stu-id="9798e-120">See Also</span></span>  
 [<span data-ttu-id="9798e-121">Průvodce programováním (technologie LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="9798e-121">Programming Guide (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
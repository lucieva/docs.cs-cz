---
title: "Vytváření stromů XML (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: bccc3e0a-c08c-468e-9d30-e075670fdace
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 23b19593774b5a010b453e3fe755e21386afd015
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="creating-xml-trees-c"></a><span data-ttu-id="5c7f0-102">Vytváření stromů XML (C#)</span><span class="sxs-lookup"><span data-stu-id="5c7f0-102">Creating XML Trees (C#)</span></span>
<span data-ttu-id="5c7f0-103">Jeden z nejčastějších úloh XML je vytváření strom XML.</span><span class="sxs-lookup"><span data-stu-id="5c7f0-103">One of the most common XML tasks is constructing an XML tree.</span></span> <span data-ttu-id="5c7f0-104">Tato část popisuje několik způsobů, jak je vytvořte.</span><span class="sxs-lookup"><span data-stu-id="5c7f0-104">This section describes several ways to create them.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5c7f0-105">V tomto oddílu</span><span class="sxs-lookup"><span data-stu-id="5c7f0-105">In This Section</span></span>  
  
|<span data-ttu-id="5c7f0-106">Téma</span><span class="sxs-lookup"><span data-stu-id="5c7f0-106">Topic</span></span>|<span data-ttu-id="5c7f0-107">Popis</span><span class="sxs-lookup"><span data-stu-id="5c7f0-107">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="5c7f0-108">Funkční konstrukce (technologie LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="5c7f0-108">Functional Construction (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/functional-construction-linq-to-xml.md)|<span data-ttu-id="5c7f0-109">Poskytuje přehled funkční konstrukce v [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5c7f0-109">Provides an overview of functional construction in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span> <span data-ttu-id="5c7f0-110">Funkční konstrukce umožňuje vytvořit nebo její část stromu XML v jediném příkazu.</span><span class="sxs-lookup"><span data-stu-id="5c7f0-110">Functional construction enables you to create all or part of your XML tree in a single statement.</span></span> <span data-ttu-id="5c7f0-111">Toto téma také ukazuje, jak pro vložení dotazy při sestavování ve stromu XML.</span><span class="sxs-lookup"><span data-stu-id="5c7f0-111">This topic also shows how to embed queries when constructing an XML tree.</span></span>|  
|[<span data-ttu-id="5c7f0-112">Vytváření stromů XML v jazyce C# (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="5c7f0-112">Creating XML Trees in C# (LINQ to XML)</span></span>](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees-linq-to-xml-2.md)|<span data-ttu-id="5c7f0-113">Ukazuje, jak vytvořit stromové struktury v jazyku C#.</span><span class="sxs-lookup"><span data-stu-id="5c7f0-113">Shows how to create trees in C#.</span></span>|  
|[<span data-ttu-id="5c7f0-114">Klonování vs. Připojení (C#)</span><span class="sxs-lookup"><span data-stu-id="5c7f0-114">Cloning vs. Attaching (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/cloning-vs-attaching.md)|<span data-ttu-id="5c7f0-115">Ukazuje rozdíl mezi přidání uzlů z existující stromu XML (uzly jsou klonovat a potom přidat) a přidání uzlů žádný nadřazený (jsou jednoduše připojené).</span><span class="sxs-lookup"><span data-stu-id="5c7f0-115">Demonstrates the difference between adding nodes from an existing XML tree (nodes are cloned and then added) and adding nodes with no parent (they are simply attached).</span></span>|  
|[<span data-ttu-id="5c7f0-116">Analýza kódu XML (C#)</span><span class="sxs-lookup"><span data-stu-id="5c7f0-116">Parsing XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/parsing-xml.md)|<span data-ttu-id="5c7f0-117">Ukazuje, jak analyzovat soubor XML z různých zdrojů.</span><span class="sxs-lookup"><span data-stu-id="5c7f0-117">Shows how to parse XML from a variety of sources.</span></span> [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="5c7f0-118">tvoří vrstvu nad <xref:System.Xml.XmlReader>, který se používá k analyzovat kód XML.</span><span class="sxs-lookup"><span data-stu-id="5c7f0-118"> is layered on top of <xref:System.Xml.XmlReader>, which is used to parse the XML.</span></span>|  
|[<span data-ttu-id="5c7f0-119">Postupy: naplnění strom XML s XmlWriter (technologie LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="5c7f0-119">How to: Populate an XML Tree with an XmlWriter (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-populate-an-xml-tree-with-an-xmlwriter-linq-to-xml.md)|<span data-ttu-id="5c7f0-120">Ukazuje, jak k naplnění strom XML pomocí <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="5c7f0-120">Shows how to populate an XML tree by using an <xref:System.Xml.XmlWriter>.</span></span>|  
|[<span data-ttu-id="5c7f0-121">Postupy: ověření pomocí XSD (technologie LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="5c7f0-121">How to: Validate Using XSD (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-validate-using-xsd-linq-to-xml.md)|<span data-ttu-id="5c7f0-122">Ukazuje, jak ověřit strom XML pomocí XSD.</span><span class="sxs-lookup"><span data-stu-id="5c7f0-122">Shows how to validate an XML tree using XSD.</span></span>|  
|[<span data-ttu-id="5c7f0-123">Platný obsah XElement a XDocument objektů</span><span class="sxs-lookup"><span data-stu-id="5c7f0-123">Valid Content of XElement and XDocument Objects</span></span>](../../../../csharp/programming-guide/concepts/linq/valid-content-of-xelement-and-xdocument-objects3.md)|<span data-ttu-id="5c7f0-124">Popisuje platné argumenty, které lze předat konstruktorů a metod, které slouží k přidání obsahu do elementů a dokumenty.</span><span class="sxs-lookup"><span data-stu-id="5c7f0-124">Describes the valid arguments that can be passed to the constructors and methods that are used to add content to elements and documents.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5c7f0-125">Viz také</span><span class="sxs-lookup"><span data-stu-id="5c7f0-125">See Also</span></span>  
 [<span data-ttu-id="5c7f0-126">Průvodce programováním (technologie LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="5c7f0-126">Programming Guide (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
---
title: "Typové datové sady"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 033d2548-cf24-4c05-8179-67d8b009c048
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: e3d5edc4f469b59ff787e500ad447fe0076c332c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="typed-datasets"></a><span data-ttu-id="a67ff-102">Typové datové sady</span><span class="sxs-lookup"><span data-stu-id="a67ff-102">Typed DataSets</span></span>
<span data-ttu-id="a67ff-103">Společně s pozdní vázané přístup k hodnotám prostřednictvím slabě typovaná proměnné <xref:System.Data.DataSet> poskytuje přístup k datům prostřednictvím silného typu jedná.</span><span class="sxs-lookup"><span data-stu-id="a67ff-103">Along with late bound access to values through weakly typed variables, the <xref:System.Data.DataSet> provides access to data through a strongly typed metaphor.</span></span> <span data-ttu-id="a67ff-104">Tabulky a sloupce, které jsou součástí **datovou sadu** lze přistupovat pomocí uživatelsky přívětivých názvů a silného typu proměnné.</span><span class="sxs-lookup"><span data-stu-id="a67ff-104">Tables and columns that are part of the **DataSet** can be accessed using user-friendly names and strongly typed variables.</span></span>  
  
 <span data-ttu-id="a67ff-105">Představuje zadaný **datovou sadu** je třída, která je odvozena z **datovou sadu**.</span><span class="sxs-lookup"><span data-stu-id="a67ff-105">A typed **DataSet** is a class that derives from a **DataSet**.</span></span> <span data-ttu-id="a67ff-106">Jako takový dědí všechny metody, události a vlastnosti **datovou sadu**.</span><span class="sxs-lookup"><span data-stu-id="a67ff-106">As such, it inherits all the methods, events, and properties of a **DataSet**.</span></span> <span data-ttu-id="a67ff-107">Kromě toho typové **datovou sadu** poskytuje silného typu metody, události a vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="a67ff-107">Additionally, a typed **DataSet** provides strongly typed methods, events, and properties.</span></span> <span data-ttu-id="a67ff-108">To znamená, že dostanete tabulky a sloupce, podle názvu, namísto použití metody založené na kolekcích.</span><span class="sxs-lookup"><span data-stu-id="a67ff-108">This means you can access tables and columns by name, instead of using collection-based methods.</span></span> <span data-ttu-id="a67ff-109">Kromě zajištění dostatečného lepší čitelnost kódu, představuje zadaný **datovou sadu** také umožňuje kód sady Visual Studio .NET editor při psaní automaticky dokončit řádky.</span><span class="sxs-lookup"><span data-stu-id="a67ff-109">Aside from the improved readability of the code, a typed **DataSet** also allows the Visual Studio .NET code editor to automatically complete lines as you type.</span></span>  
  
 <span data-ttu-id="a67ff-110">Kromě toho silného **datovou sadu** poskytuje přístup k hodnotám jako správného typu v době kompilace.</span><span class="sxs-lookup"><span data-stu-id="a67ff-110">Additionally, the strongly typed **DataSet** provides access to values as the correct type at compile time.</span></span> <span data-ttu-id="a67ff-111">S silného typu **datovou sadu**, chyby neshoda typu jsou zachyceny, pokud kód je kompilovat spíše než v dobu běhu.</span><span class="sxs-lookup"><span data-stu-id="a67ff-111">With a strongly typed **DataSet**, type mismatch errors are caught when the code is compiled rather than at run time.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a67ff-112">V tomto oddílu</span><span class="sxs-lookup"><span data-stu-id="a67ff-112">In This Section</span></span>  
 [<span data-ttu-id="a67ff-113">Generování silného typu datové sady</span><span class="sxs-lookup"><span data-stu-id="a67ff-113">Generating Strongly Typed DataSets</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-strongly-typed-datasets.md)  
 <span data-ttu-id="a67ff-114">Popisuje postup vytvoření a používání silného typu **datovou sadu**.</span><span class="sxs-lookup"><span data-stu-id="a67ff-114">Describes how to create and use a strongly typed **DataSet**.</span></span>  
  
 [<span data-ttu-id="a67ff-115">Zadávání poznámek k typové datové sady</span><span class="sxs-lookup"><span data-stu-id="a67ff-115">Annotating Typed DataSets</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/annotating-typed-datasets.md)  
 <span data-ttu-id="a67ff-116">Popisuje postup přidání poznámek ke schématu jazyka (XSD) definice schématu XML sloužící ke generování silného typu **datovou sadu**, umožnit **datovou sadu** popisné názvy elementů beze změny základní schéma.</span><span class="sxs-lookup"><span data-stu-id="a67ff-116">Describes how to annotate the XML Schema definition language (XSD) schema used to generate a strongly typed **DataSet**, to give **DataSet** elements friendly names without altering the underlying schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a67ff-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="a67ff-117">See Also</span></span>  
 [<span data-ttu-id="a67ff-118">Datové sady, DataTables a DataView</span><span class="sxs-lookup"><span data-stu-id="a67ff-118">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="a67ff-119">ADO.NET spravované zprostředkovatelé a středisku pro vývojáře datové sady</span><span class="sxs-lookup"><span data-stu-id="a67ff-119">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
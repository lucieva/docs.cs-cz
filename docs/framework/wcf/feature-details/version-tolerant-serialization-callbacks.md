---
title: "Zpětná volání serializace tolerantní k verzím"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- OnDeserializedAttribute [WCF]
- OnDeserializingAttribute [WCF]
- OnSerializingAttribute [WCF]
- serialization [WCF], setting default values
- OnSerializedAttribute [WCF]
ms.assetid: aa4a3a6f-05ec-4efd-bdbf-2181e13e6468
caps.latest.revision: "17"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7c00cadd4b0e643e35f7f56a28760e261c423699
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="version-tolerant-serialization-callbacks"></a><span data-ttu-id="96fb3-102">Zpětná volání serializace tolerantní k verzím</span><span class="sxs-lookup"><span data-stu-id="96fb3-102">Version-Tolerant Serialization Callbacks</span></span>
<span data-ttu-id="96fb3-103">Programovací model kontraktu dat plně podporuje metody zpětného volání serializace tolerantní k verzi, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> a <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> třídy podpory.</span><span class="sxs-lookup"><span data-stu-id="96fb3-103">The data contract programming model fully supports the version-tolerant serialization callback methods that the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> and <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> classes support.</span></span>  
  
## <a name="version-tolerant-attributes"></a><span data-ttu-id="96fb3-104">Verze proti chybám atributy</span><span class="sxs-lookup"><span data-stu-id="96fb3-104">Version-Tolerant Attributes</span></span>  
 <span data-ttu-id="96fb3-105">Existují čtyři atributy zpětného volání.</span><span class="sxs-lookup"><span data-stu-id="96fb3-105">There are four callback attributes.</span></span> <span data-ttu-id="96fb3-106">Každý atribut je použít pro metodu, která volá modul serializaci nebo deserializaci v různé časy.</span><span class="sxs-lookup"><span data-stu-id="96fb3-106">Each attribute can be applied to a method that the serialization/deserialization engine calls at various times.</span></span> <span data-ttu-id="96fb3-107">Následující tabulka vysvětluje, kdy použít každý atribut.</span><span class="sxs-lookup"><span data-stu-id="96fb3-107">The table below explains when to use each attribute.</span></span>  
  
|<span data-ttu-id="96fb3-108">Atribut</span><span class="sxs-lookup"><span data-stu-id="96fb3-108">Attribute</span></span>|<span data-ttu-id="96fb3-109">Pokud odpovídající metoda je volána</span><span class="sxs-lookup"><span data-stu-id="96fb3-109">When the corresponding method is called</span></span>|  
|---------------|---------------------------------------------|  
|<xref:System.Runtime.Serialization.OnSerializingAttribute>|<span data-ttu-id="96fb3-110">Volá se před serializace typu.</span><span class="sxs-lookup"><span data-stu-id="96fb3-110">Called before serializing the type.</span></span>|  
|<xref:System.Runtime.Serialization.OnSerializedAttribute>|<span data-ttu-id="96fb3-111">Volá se po serializace typu.</span><span class="sxs-lookup"><span data-stu-id="96fb3-111">Called after serializing the type.</span></span>|  
|<xref:System.Runtime.Serialization.OnDeserializingAttribute>|<span data-ttu-id="96fb3-112">Volá se před deserializaci typu.</span><span class="sxs-lookup"><span data-stu-id="96fb3-112">Called before deserializing the type.</span></span>|  
|<xref:System.Runtime.Serialization.OnDeserializedAttribute>|<span data-ttu-id="96fb3-113">Volá se po deserializaci typu.</span><span class="sxs-lookup"><span data-stu-id="96fb3-113">Called after deserializing the type.</span></span>|  
  
 <span data-ttu-id="96fb3-114">Metody musí přijmout <xref:System.Runtime.Serialization.StreamingContext> parametr.</span><span class="sxs-lookup"><span data-stu-id="96fb3-114">The methods must accept a <xref:System.Runtime.Serialization.StreamingContext> parameter.</span></span>  
  
 <span data-ttu-id="96fb3-115">Tyto metody jsou primárně určený pro použití se službou Správa verzí nebo inicializace.</span><span class="sxs-lookup"><span data-stu-id="96fb3-115">These methods are primarily intended for use with versioning or initialization.</span></span> <span data-ttu-id="96fb3-116">Během deserializace se nazývají žádné konstruktory.</span><span class="sxs-lookup"><span data-stu-id="96fb3-116">During deserialization, no constructors are called.</span></span> <span data-ttu-id="96fb3-117">Proto datové členy není možné správně inicializovat (pro určený výchozí hodnoty) Pokud data pro tyto členy chybí v příchozím datovém proudu, například pokud data pocházejí z předchozí verze typ, který chybí některé datové členy.</span><span class="sxs-lookup"><span data-stu-id="96fb3-117">Therefore, data members may not be correctly initialized (to intended default values) if the data for these members is missing in the incoming stream, for example, if the data comes from a previous version of a type that is missing some data members.</span></span> <span data-ttu-id="96fb3-118">Chcete-li vyřešit tento problém, použijte metoda zpětného volání, které jsou označené jako <xref:System.Runtime.Serialization.OnDeserializingAttribute>, jak je znázorněno v následujícím příkladu.</span><span class="sxs-lookup"><span data-stu-id="96fb3-118">To correct this, use the callback method marked with the <xref:System.Runtime.Serialization.OnDeserializingAttribute>, as shown in the following example.</span></span>  
  
 <span data-ttu-id="96fb3-119">Můžete označit pouze jednu metodu podle typu k jednotlivým atributům předchozí zpětného volání.</span><span class="sxs-lookup"><span data-stu-id="96fb3-119">You can mark only one method per type with each of the preceding callback attributes.</span></span>  
  
### <a name="example"></a><span data-ttu-id="96fb3-120">Příklad</span><span class="sxs-lookup"><span data-stu-id="96fb3-120">Example</span></span>  
 [!code-csharp[C_DataContract#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontract/cs/source.cs#9)]
 [!code-vb[C_DataContract#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontract/vb/source.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="96fb3-121">Viz také</span><span class="sxs-lookup"><span data-stu-id="96fb3-121">See Also</span></span>  
 <xref:System.Runtime.Serialization.OnSerializingAttribute>  
 <xref:System.Runtime.Serialization.OnSerializedAttribute>  
 <xref:System.Runtime.Serialization.OnDeserializingAttribute>  
 <xref:System.Runtime.Serialization.OnDeserializedAttribute>  
 <xref:System.Runtime.Serialization.StreamingContext>  
 [<span data-ttu-id="96fb3-122">Verze serializace</span><span class="sxs-lookup"><span data-stu-id="96fb3-122">Version Tolerant Serialization</span></span>](../../../../docs/standard/serialization/version-tolerant-serialization.md)
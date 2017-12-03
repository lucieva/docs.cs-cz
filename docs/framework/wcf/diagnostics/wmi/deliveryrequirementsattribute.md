---
title: DeliveryRequirementsAttribute
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 40c5435c-a325-4cf8-9dd0-d6e24b4a56a3
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 40bdc27337daae02795137fc3ac67575787018c1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="deliveryrequirementsattribute"></a><span data-ttu-id="a8cda-102">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="a8cda-102">DeliveryRequirementsAttribute</span></span>
<span data-ttu-id="a8cda-103">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="a8cda-103">DeliveryRequirementsAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8cda-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="a8cda-104">Syntax</span></span>  
  
```  
class DeliveryRequirementsAttribute : Behavior  
{  
  string QueuedDeliveryRequirements;  
  boolean RequireOrderedDelivery;  
  string TargetContract;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="a8cda-105">Metody</span><span class="sxs-lookup"><span data-stu-id="a8cda-105">Methods</span></span>  
 <span data-ttu-id="a8cda-106">Třída Atribut DeliveryRequirementsAttribute nedefinuje žádné metody.</span><span class="sxs-lookup"><span data-stu-id="a8cda-106">The DeliveryRequirementsAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="a8cda-107">Vlastnosti</span><span class="sxs-lookup"><span data-stu-id="a8cda-107">Properties</span></span>  
 <span data-ttu-id="a8cda-108">Atribut DeliveryRequirementsAttribute třída má následující vlastnosti:</span><span class="sxs-lookup"><span data-stu-id="a8cda-108">The DeliveryRequirementsAttribute class has the following properties:</span></span>  
  
### <a name="queueddeliveryrequirements"></a><span data-ttu-id="a8cda-109">Atribut QueuedDeliveryRequirements</span><span class="sxs-lookup"><span data-stu-id="a8cda-109">QueuedDeliveryRequirements</span></span>  
 <span data-ttu-id="a8cda-110">Datový typ: řetězec</span><span class="sxs-lookup"><span data-stu-id="a8cda-110">Data type: string</span></span>  
  
 <span data-ttu-id="a8cda-111">Přístup k typu: jen pro čtení</span><span class="sxs-lookup"><span data-stu-id="a8cda-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a8cda-112">Určuje, zda vazby pro službu podporuje kontrakty.</span><span class="sxs-lookup"><span data-stu-id="a8cda-112">Specifies whether the binding for a service supports contracts.</span></span>  
  
### <a name="requireordereddelivery"></a><span data-ttu-id="a8cda-113">RequireOrderedDelivery</span><span class="sxs-lookup"><span data-stu-id="a8cda-113">RequireOrderedDelivery</span></span>  
 <span data-ttu-id="a8cda-114">Datový typ: logická hodnota</span><span class="sxs-lookup"><span data-stu-id="a8cda-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="a8cda-115">Přístup k typu: jen pro čtení</span><span class="sxs-lookup"><span data-stu-id="a8cda-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a8cda-116">Určuje, zda vazby podporuje seřazené zprávy.</span><span class="sxs-lookup"><span data-stu-id="a8cda-116">Specifies whether the binding supports ordered messages.</span></span>  
  
### <a name="targetcontract"></a><span data-ttu-id="a8cda-117">TargetContract</span><span class="sxs-lookup"><span data-stu-id="a8cda-117">TargetContract</span></span>  
 <span data-ttu-id="a8cda-118">Datový typ: řetězec</span><span class="sxs-lookup"><span data-stu-id="a8cda-118">Data type: string</span></span>  
  
 <span data-ttu-id="a8cda-119">Přístup k typu: jen pro čtení</span><span class="sxs-lookup"><span data-stu-id="a8cda-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a8cda-120">Kontrakt, na který se vztahuje.</span><span class="sxs-lookup"><span data-stu-id="a8cda-120">The contract to which it applies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8cda-121">Požadavky</span><span class="sxs-lookup"><span data-stu-id="a8cda-121">Requirements</span></span>  
  
|<span data-ttu-id="a8cda-122">MOF</span><span class="sxs-lookup"><span data-stu-id="a8cda-122">MOF</span></span>|<span data-ttu-id="a8cda-123">Deklarované v Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="a8cda-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="a8cda-124">Obor názvů</span><span class="sxs-lookup"><span data-stu-id="a8cda-124">Namespace</span></span>|<span data-ttu-id="a8cda-125">Definované v root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a8cda-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a8cda-126">Viz také</span><span class="sxs-lookup"><span data-stu-id="a8cda-126">See Also</span></span>  
 <xref:System.ServiceModel.DeliveryRequirementsAttribute>
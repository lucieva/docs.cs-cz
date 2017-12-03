---
title: IEnumRAWINPUTDEVIC:Clone
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Clone method [WPF]
ms.assetid: 2a6a1900-aa55-45fa-9382-241d569a2dc4
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 35f3c00f3a0efd41c425ba29f8465a73e78d624c
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/22/2017
---
# <a name="ienumrawinputdevicclone"></a><span data-ttu-id="45183-102">IEnumRAWINPUTDEVIC:Clone</span><span class="sxs-lookup"><span data-stu-id="45183-102">IEnumRAWINPUTDEVIC:Clone</span></span>
<span data-ttu-id="45183-103">Vytvoří další nezpracované vstupní zařízení enumerátor stejného stavu jako aktuální enumerátor Iterujte přes stejný seznam.</span><span class="sxs-lookup"><span data-stu-id="45183-103">Creates another raw input device enumerator with the same state as the current enumerator to iterate over the same list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45183-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="45183-104">Syntax</span></span>  
  
```  
HRESULT Clone( [out] IEnumRAWINPUTDEVICE **ppenum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="45183-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="45183-105">Parameters</span></span>  
 `ppenum`  
  
 <span data-ttu-id="45183-106">[out] Adresa výstup proměnné, která přijímá [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) ukazatel rozhraní.</span><span class="sxs-lookup"><span data-stu-id="45183-106">[out] Address of output variable that receives the [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) interface pointer.</span></span> <span data-ttu-id="45183-107">Pokud je metoda úspěšné, hodnotu tento výstup proměnné není definován.</span><span class="sxs-lookup"><span data-stu-id="45183-107">If the method is unsuccessful, the value of this output variable is undefined.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="45183-108">Hodnota vlastnosti / návratová hodnota</span><span class="sxs-lookup"><span data-stu-id="45183-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="45183-109">HRESULT: Tato metoda podporuje standardní návratové hodnoty E_INVALIDARG E_OUTOFMEMORY a E_UNEXPECTED.</span><span class="sxs-lookup"><span data-stu-id="45183-109">HRESULT: This method supports the standard return values E_INVALIDARG, E_OUTOFMEMORY, and E_UNEXPECTED.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="45183-110">Poznámky</span><span class="sxs-lookup"><span data-stu-id="45183-110">Remarks</span></span>  
 <span data-ttu-id="45183-111">Tato metoda umožňuje zaznamenat bod v pořadí výčtu cílem vrátit do tohoto bodu později.</span><span class="sxs-lookup"><span data-stu-id="45183-111">This method makes it possible to record a point in the enumeration sequence in order to return to that point at a later time.</span></span> <span data-ttu-id="45183-112">Volající musí uvolnit tento nový enumerátor odděleně od první enumerátor.</span><span class="sxs-lookup"><span data-stu-id="45183-112">The caller must release this new enumerator separately from the first enumerator.</span></span>
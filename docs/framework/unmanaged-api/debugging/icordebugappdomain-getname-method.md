---
title: "ICorDebugAppDomain::GetName – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAppDomain.GetName
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAppDomain::GetName
helpviewer_keywords:
- ICorDebugAppDomain::GetName method [.NET Framework debugging]
- GetName method, ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: 02c596d7-00b0-4e2c-856b-5425158fcefd
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 590bfb5d7d8cac8e322bddfe6258ad9bf377dad6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugappdomaingetname-method"></a><span data-ttu-id="46377-102">ICorDebugAppDomain::GetName – metoda</span><span class="sxs-lookup"><span data-stu-id="46377-102">ICorDebugAppDomain::GetName Method</span></span>
<span data-ttu-id="46377-103">Získá název domény aplikace.</span><span class="sxs-lookup"><span data-stu-id="46377-103">Gets the name of the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46377-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="46377-104">Syntax</span></span>  
  
```  
HRESULT GetName (  
    [in]  ULONG32           cchName,  
    [out] ULONG32           *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
         WCHAR              szName[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="46377-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="46377-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="46377-106">[v] Velikost `szName` pole.</span><span class="sxs-lookup"><span data-stu-id="46377-106">[in] The size of the `szName` array.</span></span> <span data-ttu-id="46377-107">Tuto hodnotu nastavte na nulu, tato metoda uvést do režimu dotazu.</span><span class="sxs-lookup"><span data-stu-id="46377-107">Set this value to zero to put this method in query mode.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="46377-108">[out] Ukazatel na velikost název nebo počet znaků, které jsou ve skutečnosti, vrátí se v `szName`.</span><span class="sxs-lookup"><span data-stu-id="46377-108">[out] A pointer to the size of the name or the number of characters actually returned in `szName`.</span></span> <span data-ttu-id="46377-109">V režimu dotazu, tato hodnota umožňuje volající vědět, jak velké vyrovnávací paměti k přidělení pro název.</span><span class="sxs-lookup"><span data-stu-id="46377-109">In query mode, this value lets the caller know how large a buffer to allocate for the name.</span></span>  
  
 `szName`  
 <span data-ttu-id="46377-110">[out] Pole, které ukládá název domény aplikace.</span><span class="sxs-lookup"><span data-stu-id="46377-110">[out] An array that stores the name of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="46377-111">Poznámky</span><span class="sxs-lookup"><span data-stu-id="46377-111">Remarks</span></span>  
 <span data-ttu-id="46377-112">Ladicí program volá `GetName` metoda jednou se získat velikost vyrovnávací paměti potřebné pro název.</span><span class="sxs-lookup"><span data-stu-id="46377-112">A debugger calls the `GetName` method once to get the size of a buffer needed for the name.</span></span> <span data-ttu-id="46377-113">Ladicí program přiděluje vyrovnávací paměť a pak zavolá metodu podruhé k vyplnění vyrovnávací paměti.</span><span class="sxs-lookup"><span data-stu-id="46377-113">The debugger allocates the buffer, and then calls the method a second time to fill the buffer.</span></span> <span data-ttu-id="46377-114">První volání se získat velikost názvu, se označuje jako *režim dotazu*.</span><span class="sxs-lookup"><span data-stu-id="46377-114">The first call, to get the size of the name, is referred to as *query mode*.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46377-115">Požadavky</span><span class="sxs-lookup"><span data-stu-id="46377-115">Requirements</span></span>  
 <span data-ttu-id="46377-116">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46377-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46377-117">**Záhlaví:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="46377-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="46377-118">**Knihovna:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="46377-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="46377-119">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46377-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
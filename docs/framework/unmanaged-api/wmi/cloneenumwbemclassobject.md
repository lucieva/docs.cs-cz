---
title: "Funkce CloneEnumWbemClassObject (referenční dokumentace nespravovaného rozhraní API)"
description: "Funkce CloneEnumWbemClassObject vytvoří kopii logické enumerátor."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: CloneEnumWbemClassObject
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: CloneEnumWbemClassObject
helpviewer_keywords: CloneEnumWbemClassObject function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7a4103a0103a334a0e5eace32d8fcf1b365917b8
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/15/2017
---
# <a name="cloneenumwbemclassobject-function"></a><span data-ttu-id="1dff4-103">CloneEnumWbemClassObject – funkce</span><span class="sxs-lookup"><span data-stu-id="1dff4-103">CloneEnumWbemClassObject function</span></span>
<span data-ttu-id="1dff4-104">Vytvoří kopii logické enumerátor zachovat své aktuální pozici ve výčtu.</span><span class="sxs-lookup"><span data-stu-id="1dff4-104">Makes a logical copy of an enumerator, retaining its current position in an enumeration.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="1dff4-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="1dff4-105">Syntax</span></span>  
  
```  
HRESULT CloneEnumWbemClassObject (
   [out] IEnumWbemClassObject**  ppEnum, 
   [in] DWORD                    authLevel,
   [in] DWORD                    impLevel,
   [in] IEnumWbemClassObject*    pCurrentEnumWbemClassObject, 
   [in] BSTR                     strUser,
   [in] BSTR                     strPassword,
   [in BSTR]                     strAuthority 
); 
```  

## <a name="parameters"></a><span data-ttu-id="1dff4-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="1dff4-106">Parameters</span></span>

`ppEnum`  
<span data-ttu-id="1dff4-107">[out] Obdrží ukazatel na novou [IEnumWbemClassObject](https://msdn.microsoft.com/library/aa390857(v=vs.85).aspx).</span><span class="sxs-lookup"><span data-stu-id="1dff4-107">[out] Receives a pointer to a new [IEnumWbemClassObject](https://msdn.microsoft.com/library/aa390857(v=vs.85).aspx).</span></span>

`authLevel`  
<span data-ttu-id="1dff4-108">[v] Úroveň ověřování.</span><span class="sxs-lookup"><span data-stu-id="1dff4-108">[in] The authorization level.</span></span>

<span data-ttu-id="1dff4-109">`impLevel`[v] Úroveň zosobnění.</span><span class="sxs-lookup"><span data-stu-id="1dff4-109">`impLevel` [in] The impersonation level.</span></span>

`pCurrentEnumWbemClassObject`  
<span data-ttu-id="1dff4-110">[out] Ukazatel [IEnumWbemClassObject](https://msdn.microsoft.com/library/aa390857(v=vs.85).aspx) instance ke klonování.</span><span class="sxs-lookup"><span data-stu-id="1dff4-110">[out] A pointer to the [IEnumWbemClassObject](https://msdn.microsoft.com/library/aa390857(v=vs.85).aspx) instance to be cloned.</span></span>

`strUser`   
<span data-ttu-id="1dff4-111">[v] Uživatelské jméno.</span><span class="sxs-lookup"><span data-stu-id="1dff4-111">[in] The user name.</span></span> <span data-ttu-id="1dff4-112">Najdete v článku [ConnectServerWmi](connectserverwmi.md) funkce pro další informace.</span><span class="sxs-lookup"><span data-stu-id="1dff4-112">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`   
<span data-ttu-id="1dff4-113">[v] Heslo.</span><span class="sxs-lookup"><span data-stu-id="1dff4-113">[in] The password.</span></span> <span data-ttu-id="1dff4-114">Najdete v článku [ConnectServerWmi](connectserverwmi.md) funkce pro další informace.</span><span class="sxs-lookup"><span data-stu-id="1dff4-114">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`   
<span data-ttu-id="1dff4-115">[v] Název domény uživatele.</span><span class="sxs-lookup"><span data-stu-id="1dff4-115">[in] The domain name of the user.</span></span> <span data-ttu-id="1dff4-116">Najdete v článku [ConnectServerWmi](connectserverwmi.md) funkce pro další informace.</span><span class="sxs-lookup"><span data-stu-id="1dff4-116">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="1dff4-117">Návratová hodnota</span><span class="sxs-lookup"><span data-stu-id="1dff4-117">Return value</span></span>

<span data-ttu-id="1dff4-118">Následující hodnoty, vrátí tato funkce jsou definovány v *WbemCli.h* soubor hlaviček, případně je možné definovat je jako konstanty ve vašem kódu:</span><span class="sxs-lookup"><span data-stu-id="1dff4-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="1dff4-119">Konstanta</span><span class="sxs-lookup"><span data-stu-id="1dff4-119">Constant</span></span>  |<span data-ttu-id="1dff4-120">Hodnota</span><span class="sxs-lookup"><span data-stu-id="1dff4-120">Value</span></span>  |<span data-ttu-id="1dff4-121">Popis</span><span class="sxs-lookup"><span data-stu-id="1dff4-121">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="1dff4-122">0x80041001</span><span class="sxs-lookup"><span data-stu-id="1dff4-122">0x80041001</span></span> | <span data-ttu-id="1dff4-123">Došlo k obecné chybě.</span><span class="sxs-lookup"><span data-stu-id="1dff4-123">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="1dff4-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="1dff4-124">0x80041008</span></span> | <span data-ttu-id="1dff4-125">Parametr je neplatný.</span><span class="sxs-lookup"><span data-stu-id="1dff4-125">A parameter is invalid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="1dff4-126">0x80041006</span><span class="sxs-lookup"><span data-stu-id="1dff4-126">0x80041006</span></span> | <span data-ttu-id="1dff4-127">Je k dispozici není dostatek paměti dokončit operaci.</span><span class="sxs-lookup"><span data-stu-id="1dff4-127">Not enough memory is available complete the operation.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="1dff4-128">0x80041015</span><span class="sxs-lookup"><span data-stu-id="1dff4-128">0x80041015</span></span> | <span data-ttu-id="1dff4-129">Propojení vzdáleného volání procedur (RPC) mezi aktuálním procesem a rozhraní WMI se nezdařilo.</span><span class="sxs-lookup"><span data-stu-id="1dff4-129">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="1dff4-130">0</span><span class="sxs-lookup"><span data-stu-id="1dff4-130">0</span></span> | <span data-ttu-id="1dff4-131">Volání funkce byla úspěšná.</span><span class="sxs-lookup"><span data-stu-id="1dff4-131">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="1dff4-132">Poznámky</span><span class="sxs-lookup"><span data-stu-id="1dff4-132">Remarks</span></span>

<span data-ttu-id="1dff4-133">Tato funkce zabalí volání [IEnumWbemClassObject::Clone](https://msdn.microsoft.com/library/aa390859(v=vs.85).aspx) metoda.</span><span class="sxs-lookup"><span data-stu-id="1dff4-133">This function wraps a call to the [IEnumWbemClassObject::Clone](https://msdn.microsoft.com/library/aa390859(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="1dff4-134">Tato metoda umožňuje pouze kopie "co možná nejlepší".</span><span class="sxs-lookup"><span data-stu-id="1dff4-134">This method makes only a "best effort" copy.</span></span> <span data-ttu-id="1dff4-135">Z důvodu dynamické povaha mnoho objektů CIM je možné, že nový enumerátor neprovede výčet stejnou sadu objektů jako enumerátoru zdroje.</span><span class="sxs-lookup"><span data-stu-id="1dff4-135">Due to the dynamic nature of many CIM objects, it is possible that the new enumerator does not enumerate the same set of objects as the source enumerator.</span></span>  

<span data-ttu-id="1dff4-136">Pokud volání funkce selže, můžete získat další informace o chybě při volání [GetErrorInfo –](geterrorinfo.md) funkce.</span><span class="sxs-lookup"><span data-stu-id="1dff4-136">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="example"></a><span data-ttu-id="1dff4-137">Příklad</span><span class="sxs-lookup"><span data-stu-id="1dff4-137">Example</span></span>

<span data-ttu-id="1dff4-138">Příklad, naleznete v části [IEnumWbemClassObject::Clone](https://msdn.microsoft.com/library/aa390859(v=vs.85).aspx) metoda.</span><span class="sxs-lookup"><span data-stu-id="1dff4-138">For an example, see the [IEnumWbemClassObject::Clone](https://msdn.microsoft.com/library/aa390859(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="1dff4-139">Požadavky</span><span class="sxs-lookup"><span data-stu-id="1dff4-139">Requirements</span></span>  
 <span data-ttu-id="1dff4-140">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1dff4-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1dff4-141">**Záhlaví:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="1dff4-141">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="1dff4-142">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1dff4-142">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1dff4-143">Viz také</span><span class="sxs-lookup"><span data-stu-id="1dff4-143">See also</span></span>  
[<span data-ttu-id="1dff4-144">Rozhraní WMI a čítače výkonu (referenční dokumentace nespravovaného rozhraní API)</span><span class="sxs-lookup"><span data-stu-id="1dff4-144">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
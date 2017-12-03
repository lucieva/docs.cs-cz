---
title: "Funkce CreateClassEnumWmi (referenční dokumentace nespravovaného rozhraní API)"
description: "Funkce CreateClassEnumWmi vrací enumerátor pro všechny třídy, které splňují zadaná kritéria."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: CreateClassEnumWmi
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: CreateClassEnumWmi
helpviewer_keywords: CreateClassEnumWmi function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bfbfee6f8e98d04a591c58560e6d50044e716a1f
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/15/2017
---
# <a name="createclassenumwmi-function"></a><span data-ttu-id="9e8aa-103">CreateClassEnumWmi – funkce</span><span class="sxs-lookup"><span data-stu-id="9e8aa-103">CreateClassEnumWmi function</span></span>
<span data-ttu-id="9e8aa-104">Vrátí enumerátor pro všechny třídy, které splňují kritéria zadaná výběru.</span><span class="sxs-lookup"><span data-stu-id="9e8aa-104">Returns an enumerator for all classes that satisfy the specified selection criteria.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="9e8aa-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="9e8aa-105">Syntax</span></span>  
  
```  
HRESULT CreateClassEnumWmi (
   [in] BSTR                    strSuperclass,
   [in] long                    lFlags,
   [in] IWbemContext*           pCtx,
   [out] IEnumWbemClassObject** ppEnum,
   [in] DWORD                   authLevel,
   [in] DWORD                   impLevel,
   [in] IWbemServices*          pCurrentNamespace,
   [in] BSTR                    strUser,
   [in] BSTR                    strPassword,
   [in] BSTR                    strAuthority
); 
```  

## <a name="parameters"></a><span data-ttu-id="9e8aa-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="9e8aa-106">Parameters</span></span>

`strSuperclass`    
<span data-ttu-id="9e8aa-107">[v] Není-li `null` nebo prázdná, určuje název nadřazené třídy; enumerátor vrátí pouze podtřídy této třídy.</span><span class="sxs-lookup"><span data-stu-id="9e8aa-107">[in] If not `null` or blank, specifies the name of a parent class; the enumerator returns only subclasses of this class.</span></span> <span data-ttu-id="9e8aa-108">Pokud je `null` nebo je prázdný a `lFlags` je WBEM_FLAG_SHALLOW, vrátí pouze nejvyšší úrovně třídy (třídy s žádné nadřazené třídy).</span><span class="sxs-lookup"><span data-stu-id="9e8aa-108">If it is `null` or blank and `lFlags` is WBEM_FLAG_SHALLOW, returns only top-level classes (classes with no parent class).</span></span> <span data-ttu-id="9e8aa-109">Pokud je `null` nebo je prázdný a `lFlags` je `WBEM_FLAG_DEEP`, vrátí všechny třídy v oboru názvů.</span><span class="sxs-lookup"><span data-stu-id="9e8aa-109">If it is `null` or blank and `lFlags` is `WBEM_FLAG_DEEP`, returns all classes in the namespace.</span></span>

`lFlags`   
<span data-ttu-id="9e8aa-110">[v] Kombinace příznaky, které ovlivňují chování této funkce.</span><span class="sxs-lookup"><span data-stu-id="9e8aa-110">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="9e8aa-111">Následující hodnoty jsou definovány v *WbemCli.h* soubor hlaviček, případně je možné definovat je jako konstanty ve vašem kódu:</span><span class="sxs-lookup"><span data-stu-id="9e8aa-111">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span> 

|<span data-ttu-id="9e8aa-112">Konstanta</span><span class="sxs-lookup"><span data-stu-id="9e8aa-112">Constant</span></span>  |<span data-ttu-id="9e8aa-113">Hodnota</span><span class="sxs-lookup"><span data-stu-id="9e8aa-113">Value</span></span>  |<span data-ttu-id="9e8aa-114">Popis</span><span class="sxs-lookup"><span data-stu-id="9e8aa-114">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="9e8aa-115">0x20000</span><span class="sxs-lookup"><span data-stu-id="9e8aa-115">0x20000</span></span> | <span data-ttu-id="9e8aa-116">Pokud sadu, funkce načte doplněné kvalifikátory uložené v lokalizovaných obor názvů národního prostředí aktuálního připojení.</span><span class="sxs-lookup"><span data-stu-id="9e8aa-116">If set, the function retrieves the amended qualifiers stored in the localized namespace of the current connection's locale.</span></span> <br/> <span data-ttu-id="9e8aa-117">Pokud není sada, funkce načte pouze kvalifikátory uložené v oboru názvů okamžitou.</span><span class="sxs-lookup"><span data-stu-id="9e8aa-117">If not set, the function retrieves only the qualifiers stored in the immediate namespace.</span></span> |
| `WBEM_FLAG_DEEP` | <span data-ttu-id="9e8aa-118">0</span><span class="sxs-lookup"><span data-stu-id="9e8aa-118">0</span></span> | <span data-ttu-id="9e8aa-119">Výčet obsahuje všechny podtřídy v hierarchii, ale není pro tuto třídu.</span><span class="sxs-lookup"><span data-stu-id="9e8aa-119">The enumeration includes all subclasses in the hierarchy, but not this class.</span></span> |
| `WBEM_FLAG_SHALLOW` | <span data-ttu-id="9e8aa-120">1</span><span class="sxs-lookup"><span data-stu-id="9e8aa-120">1</span></span> | <span data-ttu-id="9e8aa-121">Výčet obsahuje pouze čistý instance této třídy a vyloučí všechny instance podtříd zadat vlastnosti nebyl nalezen v této třídě.</span><span class="sxs-lookup"><span data-stu-id="9e8aa-121">The enumeration includes only pure instances of this class and excludes all instances of subclasses that supply properties not found in this class.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="9e8aa-122">0x10</span><span class="sxs-lookup"><span data-stu-id="9e8aa-122">0x10</span></span> | <span data-ttu-id="9e8aa-123">Příznak způsobí, že polosynchronní volání.</span><span class="sxs-lookup"><span data-stu-id="9e8aa-123">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="9e8aa-124">0x20</span><span class="sxs-lookup"><span data-stu-id="9e8aa-124">0x20</span></span> | <span data-ttu-id="9e8aa-125">Vrátí enumerátor dopředné.</span><span class="sxs-lookup"><span data-stu-id="9e8aa-125">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="9e8aa-126">Obvykle dopředných enumerátory je rychlejší a využívají méně paměti než konvenční výčty, ale nepovoluje volání [klon](clone.md).</span><span class="sxs-lookup"><span data-stu-id="9e8aa-126">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |
| `WBEM_FLAG_BIDIRECTIONAL` | <span data-ttu-id="9e8aa-127">0</span><span class="sxs-lookup"><span data-stu-id="9e8aa-127">0</span></span> | <span data-ttu-id="9e8aa-128">Rozhraní WMI zachová ukazatelé na objekty v enumration, dokud jejich vydání.</span><span class="sxs-lookup"><span data-stu-id="9e8aa-128">WMI retains pointers to objects in the enumration until they are released.</span></span> | 

<span data-ttu-id="9e8aa-129">Doporučené příznaky jsou `WBEM_FLAG_RETURN_IMMEDIATELY` a `WBEM_FLAG_FORWARD_ONLY` pro nejlepší výkon.</span><span class="sxs-lookup"><span data-stu-id="9e8aa-129">The recommended flags are `WBEM_FLAG_RETURN_IMMEDIATELY` and `WBEM_FLAG_FORWARD_ONLY` for best performance.</span></span>

`pCtx`  
<span data-ttu-id="9e8aa-130">[v] Obvykle je tato hodnota `null`.</span><span class="sxs-lookup"><span data-stu-id="9e8aa-130">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="9e8aa-131">Jinak je ukazatel na [IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) instanci, která mohou být využívána zprostředkovatele, který poskytuje požadované třídy.</span><span class="sxs-lookup"><span data-stu-id="9e8aa-131">Otherwise, it is a pointer to an [IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) instance that can be used by the provider that is providing the requested classes.</span></span> 

`ppEnum`  
<span data-ttu-id="9e8aa-132">[out] Obdrží má ukazatel na enumerátor.</span><span class="sxs-lookup"><span data-stu-id="9e8aa-132">[out] Receives the pointer to the enumerator.</span></span>

`authLevel`  
<span data-ttu-id="9e8aa-133">[v] Úroveň ověřování.</span><span class="sxs-lookup"><span data-stu-id="9e8aa-133">[in] The authorization level.</span></span>

<span data-ttu-id="9e8aa-134">`impLevel`[v] Úroveň zosobnění.</span><span class="sxs-lookup"><span data-stu-id="9e8aa-134">`impLevel` [in] The impersonation level.</span></span>

`pCurrentNamespace`   
<span data-ttu-id="9e8aa-135">[v] Ukazatel na [Služby IWbem](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) objekt, který představuje aktuální obor názvů.</span><span class="sxs-lookup"><span data-stu-id="9e8aa-135">[in] A pointer to an [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) object that represents the current namespace.</span></span>

`strUser`   
<span data-ttu-id="9e8aa-136">[v] Uživatelské jméno.</span><span class="sxs-lookup"><span data-stu-id="9e8aa-136">[in] The user name.</span></span> <span data-ttu-id="9e8aa-137">Najdete v článku [ConnectServerWmi](connectserverwmi.md) funkce pro další informace.</span><span class="sxs-lookup"><span data-stu-id="9e8aa-137">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`   
<span data-ttu-id="9e8aa-138">[v] Heslo.</span><span class="sxs-lookup"><span data-stu-id="9e8aa-138">[in] The password.</span></span> <span data-ttu-id="9e8aa-139">Najdete v článku [ConnectServerWmi](connectserverwmi.md) funkce pro další informace.</span><span class="sxs-lookup"><span data-stu-id="9e8aa-139">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`   
<span data-ttu-id="9e8aa-140">[v] Název domény uživatele.</span><span class="sxs-lookup"><span data-stu-id="9e8aa-140">[in] The domain name of the user.</span></span> <span data-ttu-id="9e8aa-141">Najdete v článku [ConnectServerWmi](connectserverwmi.md) funkce pro další informace.</span><span class="sxs-lookup"><span data-stu-id="9e8aa-141">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="9e8aa-142">Návratová hodnota</span><span class="sxs-lookup"><span data-stu-id="9e8aa-142">Return value</span></span>

<span data-ttu-id="9e8aa-143">Následující hodnoty, vrátí tato funkce jsou definovány v *WbemCli.h* soubor hlaviček, případně je možné definovat je jako konstanty ve vašem kódu:</span><span class="sxs-lookup"><span data-stu-id="9e8aa-143">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="9e8aa-144">Konstanta</span><span class="sxs-lookup"><span data-stu-id="9e8aa-144">Constant</span></span>  |<span data-ttu-id="9e8aa-145">Hodnota</span><span class="sxs-lookup"><span data-stu-id="9e8aa-145">Value</span></span>  |<span data-ttu-id="9e8aa-146">Popis</span><span class="sxs-lookup"><span data-stu-id="9e8aa-146">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="9e8aa-147">0x80041003</span><span class="sxs-lookup"><span data-stu-id="9e8aa-147">0x80041003</span></span> | <span data-ttu-id="9e8aa-148">Uživatel nemá oprávnění k zobrazení jeden nebo více tříd, které můžou vrátit funkce.</span><span class="sxs-lookup"><span data-stu-id="9e8aa-148">The user does not have permission to view one or more of the classes that the function can return.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="9e8aa-149">0x80041001</span><span class="sxs-lookup"><span data-stu-id="9e8aa-149">0x80041001</span></span> | <span data-ttu-id="9e8aa-150">Došlo k neurčené chybě.</span><span class="sxs-lookup"><span data-stu-id="9e8aa-150">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="9e8aa-151">0x80041010</span><span class="sxs-lookup"><span data-stu-id="9e8aa-151">0x80041010</span></span> | <span data-ttu-id="9e8aa-152">`strSuperClass`neexistuje.</span><span class="sxs-lookup"><span data-stu-id="9e8aa-152">`strSuperClass` does not exist.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="9e8aa-153">0x80041008</span><span class="sxs-lookup"><span data-stu-id="9e8aa-153">0x80041008</span></span> | <span data-ttu-id="9e8aa-154">Parametr není platný.</span><span class="sxs-lookup"><span data-stu-id="9e8aa-154">A parameter is not valid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="9e8aa-155">0x80041006</span><span class="sxs-lookup"><span data-stu-id="9e8aa-155">0x80041006</span></span> | <span data-ttu-id="9e8aa-156">Je k dispozici k dokončení operace není dostatek paměti.</span><span class="sxs-lookup"><span data-stu-id="9e8aa-156">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="9e8aa-157">0x80041033</span><span class="sxs-lookup"><span data-stu-id="9e8aa-157">0x80041033</span></span> | <span data-ttu-id="9e8aa-158">Služba WMI byla pravděpodobně zastavena a restartování.</span><span class="sxs-lookup"><span data-stu-id="9e8aa-158">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="9e8aa-159">Volání [ConnectServerWmi](connectserverwmi.md) znovu.</span><span class="sxs-lookup"><span data-stu-id="9e8aa-159">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="9e8aa-160">0x80041015</span><span class="sxs-lookup"><span data-stu-id="9e8aa-160">0x80041015</span></span> | <span data-ttu-id="9e8aa-161">Propojení vzdáleného volání procedur (RPC) mezi aktuálním procesem a rozhraní WMI se nezdařilo.</span><span class="sxs-lookup"><span data-stu-id="9e8aa-161">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="9e8aa-162">0</span><span class="sxs-lookup"><span data-stu-id="9e8aa-162">0</span></span> | <span data-ttu-id="9e8aa-163">Volání funkce byla úspěšná.</span><span class="sxs-lookup"><span data-stu-id="9e8aa-163">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="9e8aa-164">Poznámky</span><span class="sxs-lookup"><span data-stu-id="9e8aa-164">Remarks</span></span>

<span data-ttu-id="9e8aa-165">Tato funkce zabalí volání [IWbemServices::CreateClassEnum](https://msdn.microsoft.com/library/aa392095(v=vs.85).aspx) metoda.</span><span class="sxs-lookup"><span data-stu-id="9e8aa-165">This function wraps a call to the [IWbemServices::CreateClassEnum](https://msdn.microsoft.com/library/aa392095(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="9e8aa-166">Pokud volání funkce selže, můžete získat další informace o chybě při volání [GetErrorInfo –](geterrorinfo.md) funkce.</span><span class="sxs-lookup"><span data-stu-id="9e8aa-166">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="9e8aa-167">Požadavky</span><span class="sxs-lookup"><span data-stu-id="9e8aa-167">Requirements</span></span>  
 <span data-ttu-id="9e8aa-168">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e8aa-168">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e8aa-169">**Záhlaví:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="9e8aa-169">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="9e8aa-170">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9e8aa-170">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e8aa-171">Viz také</span><span class="sxs-lookup"><span data-stu-id="9e8aa-171">See also</span></span>  
[<span data-ttu-id="9e8aa-172">Rozhraní WMI a čítače výkonu (referenční dokumentace nespravovaného rozhraní API)</span><span class="sxs-lookup"><span data-stu-id="9e8aa-172">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
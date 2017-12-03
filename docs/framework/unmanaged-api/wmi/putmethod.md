---
title: "Funkce PutMethod (referenční dokumentace nespravovaného rozhraní API)"
description: "Funkce PutMethod vytvoří metodu."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: PutMethod
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: PutMethod
helpviewer_keywords: PutMethod function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 64e43165b34b74540931b308100c9ca942946bcf
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/15/2017
---
# <a name="putmethod-function"></a><span data-ttu-id="ea140-103">PutMethod – funkce</span><span class="sxs-lookup"><span data-stu-id="ea140-103">PutMethod function</span></span>
<span data-ttu-id="ea140-104">Vytvoří metodu.</span><span class="sxs-lookup"><span data-stu-id="ea140-104">Creates a method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="ea140-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="ea140-105">Syntax</span></span>  
  
```  
HRESULT PutMethod (
   [in] int                vFunc, 
   [in] IWbemClassObject*  ptr, 
   [in] LPCWSTR            wszName,
   [in] LONG               lFlags,
   [in] IWbemClassObject*  pInSignature,
   [in] IWbemClassObject*  pOutSignature
); 
```  

## <a name="parameters"></a><span data-ttu-id="ea140-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="ea140-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="ea140-107">[v] Tento parametr se nepoužívá.</span><span class="sxs-lookup"><span data-stu-id="ea140-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="ea140-108">[v] Ukazatel na [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span><span class="sxs-lookup"><span data-stu-id="ea140-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszName`  
<span data-ttu-id="ea140-109">[v] Název metody pro vytvoření.</span><span class="sxs-lookup"><span data-stu-id="ea140-109">[in] The name of the method to create.</span></span> 

`lFlags`  
<span data-ttu-id="ea140-110">[v] Vyhrazena.</span><span class="sxs-lookup"><span data-stu-id="ea140-110">[in] Reserved.</span></span> <span data-ttu-id="ea140-111">Tento parametr musí být 0.</span><span class="sxs-lookup"><span data-stu-id="ea140-111">This parameter must be 0.</span></span>

`pSignatureIn`  
<span data-ttu-id="ea140-112">[v] Ukazatel na kopii [__Parameters systémové třídy](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx) obsahující `in` parametry pro metodu.</span><span class="sxs-lookup"><span data-stu-id="ea140-112">[in] A pointer to a copy of the [__Parameters system class](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx) that contains the `in` parameters for the method.</span></span> <span data-ttu-id="ea140-113">Tento parametr je ignorována, pokud nastavena na `null`.</span><span class="sxs-lookup"><span data-stu-id="ea140-113">This parameter is ignored if set to `null`.</span></span>  

`pSignatureOut`  
<span data-ttu-id="ea140-114">[v]  Ukazatel na kopii [__Parameters systémové třídy](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx) obsahující `out` parametry pro metodu.</span><span class="sxs-lookup"><span data-stu-id="ea140-114">[in]  A pointer to a copy of the [__Parameters system class](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx) that contains the `out` parameters for the method.</span></span> <span data-ttu-id="ea140-115">Tento parametr je ignorována, pokud nastavena na `null`.</span><span class="sxs-lookup"><span data-stu-id="ea140-115">This parameter is ignored if set to `null`.</span></span>
 

## <a name="return-value"></a><span data-ttu-id="ea140-116">Návratová hodnota</span><span class="sxs-lookup"><span data-stu-id="ea140-116">Return value</span></span>

<span data-ttu-id="ea140-117">Následující hodnoty, vrátí tato funkce jsou definovány v *WbemCli.h* soubor hlaviček, případně je možné definovat je jako konstanty ve vašem kódu:</span><span class="sxs-lookup"><span data-stu-id="ea140-117">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="ea140-118">Konstanta</span><span class="sxs-lookup"><span data-stu-id="ea140-118">Constant</span></span>  |<span data-ttu-id="ea140-119">Hodnota</span><span class="sxs-lookup"><span data-stu-id="ea140-119">Value</span></span>  |<span data-ttu-id="ea140-120">Popis</span><span class="sxs-lookup"><span data-stu-id="ea140-120">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="ea140-121">0x80041008</span><span class="sxs-lookup"><span data-stu-id="ea140-121">0x80041008</span></span> | <span data-ttu-id="ea140-122">Jeden nebo více parametrů nejsou platné.</span><span class="sxs-lookup"><span data-stu-id="ea140-122">One or more parameters are not valid.</span></span> |
| `WBEM_E_INVALID_DUPLICATE_PARAMETER` | <span data-ttu-id="ea140-123">0x80041043</span><span class="sxs-lookup"><span data-stu-id="ea140-123">0x80041043</span></span> | <span data-ttu-id="ea140-124">`[in, out]` Parametru metody, které jsou zadané v obou *pInSignature* a *pOutSignature* objekty mají různé kvalifikátory.</span><span class="sxs-lookup"><span data-stu-id="ea140-124">The `[in, out]` method parameter specified in both the *pInSignature* and *pOutSignature* objects have different qualifiers.</span></span>
| `WBEM_E_MISSING_PARAMETER_ID` | <span data-ttu-id="ea140-125">0x80041036</span><span class="sxs-lookup"><span data-stu-id="ea140-125">0x80041036</span></span> | <span data-ttu-id="ea140-126">Chybí parametr metody specifikaci **ID** kvalifikátor.</span><span class="sxs-lookup"><span data-stu-id="ea140-126">A method parameter is missing the specification of the **ID** qualifier.</span></span> |
| `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS` | <span data-ttu-id="ea140-127">0x80041038</span><span class="sxs-lookup"><span data-stu-id="ea140-127">0x80041038</span></span> | <span data-ttu-id="ea140-128">ID řady, která je přiřazena k parametrům metody není po sobě jdoucích nebo se nespustí na 0.</span><span class="sxs-lookup"><span data-stu-id="ea140-128">The ID series that is assigned to the method parameters is not consecutive or does not start at 0.</span></span> |
| `WBEM_E_PARAMETER_ID_ON_RETVAL` | <span data-ttu-id="ea140-129">0x80041039</span><span class="sxs-lookup"><span data-stu-id="ea140-129">0x80041039</span></span> | <span data-ttu-id="ea140-130">Návratovou hodnotu pro metodu má **ID** kvalifikátor.</span><span class="sxs-lookup"><span data-stu-id="ea140-130">The return value for a method has an **ID** qualifier.</span></span> |
| `WBEM_E_PROPAGATED_METHOD` | <span data-ttu-id="ea140-131">0x80041034</span><span class="sxs-lookup"><span data-stu-id="ea140-131">0x80041034</span></span> | <span data-ttu-id="ea140-132">Došlo k pokusu o opakované použití existujícího názvu metody od nadřazené třídy a podpisů se neshoduje.</span><span class="sxs-lookup"><span data-stu-id="ea140-132">An attempt was made to reuse an existing method name from a parent class, and the signatures did not match.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="ea140-133">0</span><span class="sxs-lookup"><span data-stu-id="ea140-133">0</span></span> | <span data-ttu-id="ea140-134">Volání funkce byla úspěšná.</span><span class="sxs-lookup"><span data-stu-id="ea140-134">The function call was successful.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="ea140-135">Poznámky</span><span class="sxs-lookup"><span data-stu-id="ea140-135">Remarks</span></span>

<span data-ttu-id="ea140-136">Tato funkce zabalí volání [IWbemClassObject::PutMethod](https://msdn.microsoft.com/library/aa391456(v=vs.85).aspx) metoda.</span><span class="sxs-lookup"><span data-stu-id="ea140-136">This function wraps a call to the [IWbemClassObject::PutMethod](https://msdn.microsoft.com/library/aa391456(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="ea140-137">Toto volání metody je podporována pouze v případě `ptr` je definice třídy CIM.</span><span class="sxs-lookup"><span data-stu-id="ea140-137">This method call is only supported if `ptr` is a CIM class definition.</span></span> <span data-ttu-id="ea140-138">Manipulace s metoda není k dispozici z [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx?f=255&MSPPError=-2147217396) ukazatele, které odkazují na modelu CIM instancí.</span><span class="sxs-lookup"><span data-stu-id="ea140-138">Method manipulation is not available from [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx?f=255&MSPPError=-2147217396) pointers that point to CIM instances.</span></span>

<span data-ttu-id="ea140-139">Uživatele nelze vytvořit metody s názvy, které začínat ani končit znakem podtržítka.</span><span class="sxs-lookup"><span data-stu-id="ea140-139">Users cannot create methods with names that begin or end with an underscore.</span></span> <span data-ttu-id="ea140-140">Toto je vyhrazená pro systém třídy a vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="ea140-140">This is reserved for system classes and properties.</span></span>

<span data-ttu-id="ea140-141">Pro metodu `in` a `out` parametry jsou popsané v jako vlastnosti [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx?f=255&MSPPError=-2147217396) objekty.</span><span class="sxs-lookup"><span data-stu-id="ea140-141">For a method, the `in` and `out` parameters are described as properties in [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx?f=255&MSPPError=-2147217396) objects.</span></span>

<span data-ttu-id="ea140-142">`[in/out]` Parametr lze definovat přidáním stejnou vlastnost na oba objekty, na kterou odkazuje `pInSignature` a `pOutSignature` parametry.</span><span class="sxs-lookup"><span data-stu-id="ea140-142">An `[in/out]` parameter can be defined by adding the same property to both objects pointed to by the `pInSignature` and `pOutSignature` parameters.</span></span> <span data-ttu-id="ea140-143">V takovém případě vlastnosti sdílet stejný **ID** kvalifikátor hodnotu.</span><span class="sxs-lookup"><span data-stu-id="ea140-143">In this case, the properties share the same **ID** qualifier value.</span></span>

<span data-ttu-id="ea140-144">Každou vlastnost v [__Parameters](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx) třídy objektu jiné než `ReturnValue` musí mít **ID** kvalifikátor, počítáno od nuly číselnou hodnotu, která identifikuje pořadí, ve kterém se zobrazí parametry.</span><span class="sxs-lookup"><span data-stu-id="ea140-144">Each property in a [__Parameters](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx) class object other than `ReturnValue` must have an **ID** qualifier, a zero-based numeric value that identifies the order in which the parameters appear.</span></span> <span data-ttu-id="ea140-145">Žádné dva parametry může mít stejný **ID** hodnota a ne **ID** hodnoty mohou být přeskočeny.</span><span class="sxs-lookup"><span data-stu-id="ea140-145">No two parameters can have the same **ID** value, and no **ID** value can be skipped.</span></span> <span data-ttu-id="ea140-146">Pokud dojde k buď podmínky, `PutMethod` funkce vrátí `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`.</span><span class="sxs-lookup"><span data-stu-id="ea140-146">If either condition occurs, the `PutMethod` function returns `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`.</span></span>

## <a name="example"></a><span data-ttu-id="ea140-147">Příklad</span><span class="sxs-lookup"><span data-stu-id="ea140-147">Example</span></span>

<span data-ttu-id="ea140-148">Příklad, naleznete v části [IWbemClassObject::PutMethod](https://msdn.microsoft.com/library/aa391456(v=vs.85).aspx) metoda.</span><span class="sxs-lookup"><span data-stu-id="ea140-148">For an example, see the [IWbemClassObject::PutMethod](https://msdn.microsoft.com/library/aa391456(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="ea140-149">Požadavky</span><span class="sxs-lookup"><span data-stu-id="ea140-149">Requirements</span></span>  
 <span data-ttu-id="ea140-150">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea140-150">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea140-151">**Záhlaví:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="ea140-151">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="ea140-152">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ea140-152">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea140-153">Viz také</span><span class="sxs-lookup"><span data-stu-id="ea140-153">See also</span></span>  
[<span data-ttu-id="ea140-154">Rozhraní WMI a čítače výkonu (referenční dokumentace nespravovaného rozhraní API)</span><span class="sxs-lookup"><span data-stu-id="ea140-154">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
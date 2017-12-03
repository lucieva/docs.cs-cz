---
title: "_CorDllMain – funkce"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: _CorDllMain
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: _CorDllMain
helpviewer_keywords: _CorDllMain function [.NET Framework hosting]
ms.assetid: bc7b51cf-39d3-48ec-a5cb-2f179fbefff8
topic_type: apiref
caps.latest.revision: "23"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d2e4188f8b95141118e4bbb2df2a702ff04c2adf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="cordllmain-function"></a><span data-ttu-id="38d5d-102">_CorDllMain – funkce</span><span class="sxs-lookup"><span data-stu-id="38d5d-102">_CorDllMain Function</span></span>
<span data-ttu-id="38d5d-103">Inicializuje modul CLR (CLR), vyhledá spravované vstupní bod v záhlaví modulu CLR sestavení knihoven DLL a zahájí spuštění.</span><span class="sxs-lookup"><span data-stu-id="38d5d-103">Initializes the common language runtime (CLR), locates the managed entry point in the DLL assembly's CLR header, and begins execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38d5d-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="38d5d-104">Syntax</span></span>  
  
```  
BOOL STDMETHODCALLTYPE _CorDllMain (  
   [in] HINSTANCE hInst,  
   [in] DWORD     dwReason,  
   [in] LPVOID    lpReserved  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="38d5d-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="38d5d-105">Parameters</span></span>  
 `hInst`  
 <span data-ttu-id="38d5d-106">[v] Instance popisovače načíst modul.</span><span class="sxs-lookup"><span data-stu-id="38d5d-106">[in] The instance handle of the loaded module.</span></span>  
  
 `dwReason`  
 <span data-ttu-id="38d5d-107">[v] Označuje, proč je volána funkce vstupního bodu knihovny DLL.</span><span class="sxs-lookup"><span data-stu-id="38d5d-107">[in]Indicates why the DLL entry-point function is being called.</span></span> <span data-ttu-id="38d5d-108">Tento parametr může být jedna z následujících hodnot: DLL_PROCESS_ATTACH DLL_THREAD_ATTACH, DLL_THREAD_ATTACH nebo DLL_PROCESS_DETACH.</span><span class="sxs-lookup"><span data-stu-id="38d5d-108">This parameter can be one of the following values: DLL_PROCESS_ATTACH, DLL_THREAD_ATTACH, DLL_THREAD_ATTACH, or DLL_PROCESS_DETACH.</span></span> <span data-ttu-id="38d5d-109">Popis těchto hodnot najdete v tématu `DllMain` dokumentace v sadě SDK pro platformu.</span><span class="sxs-lookup"><span data-stu-id="38d5d-109">For descriptions of these values, see the `DllMain` documentation in the Platform SDK.</span></span>  
  
 `lpReserved`  
 <span data-ttu-id="38d5d-110">[v] Nepoužívá se.</span><span class="sxs-lookup"><span data-stu-id="38d5d-110">[in] Unused.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="38d5d-111">Návratová hodnota</span><span class="sxs-lookup"><span data-stu-id="38d5d-111">Return Value</span></span>  
 <span data-ttu-id="38d5d-112">Tato metoda vrátí hodnotu `true` úspěch a `false` Pokud dojde k chybě.</span><span class="sxs-lookup"><span data-stu-id="38d5d-112">This method returns `true` for success and `false` if an error occurs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="38d5d-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="38d5d-113">Remarks</span></span>  
 <span data-ttu-id="38d5d-114">Tato funkce je volána zavaděčem operačního systému pro knihovnu DLL sestavení.</span><span class="sxs-lookup"><span data-stu-id="38d5d-114">This function is called by the operating system loader for DLL assemblies.</span></span> <span data-ttu-id="38d5d-115">Pro spustitelný soubor sestavení zavaděč volá [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) funkce místo.</span><span class="sxs-lookup"><span data-stu-id="38d5d-115">For executable assemblies, the loader calls the [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) function instead.</span></span>  
  
 <span data-ttu-id="38d5d-116">Zavaděč operačního systému volá tuto metodu, bez ohledu na to, vstupní bod uvedený v souboru DLL.</span><span class="sxs-lookup"><span data-stu-id="38d5d-116">The operating system loader calls this method regardless of the entry point specified in the DLL file.</span></span>  
  
 <span data-ttu-id="38d5d-117">V systému Windows 98, Windows ME, systém Windows NT a Windows 2000 `_CorDllMain` je volána funkce nepřímo prostřednictvím fixupin zavaděč operačního systému.</span><span class="sxs-lookup"><span data-stu-id="38d5d-117">In Windows 98, Windows ME, Windows NT, and Windows 2000, the `_CorDllMain` function is called indirectly through a fixupin the operating system loader.</span></span> <span data-ttu-id="38d5d-118">Ve všech ostatních verzí systému Windows je volána přímo zavaděčem operačního systému.</span><span class="sxs-lookup"><span data-stu-id="38d5d-118">In all other versions of Windows, it is called directly by the operating system loader.</span></span>  
  
 <span data-ttu-id="38d5d-119">Další informace najdete v části poznámky v [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) tématu.</span><span class="sxs-lookup"><span data-stu-id="38d5d-119">For additional information, see the Remarks section in the [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) topic.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38d5d-120">Požadavky</span><span class="sxs-lookup"><span data-stu-id="38d5d-120">Requirements</span></span>  
 <span data-ttu-id="38d5d-121">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38d5d-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38d5d-122">**Záhlaví:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="38d5d-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="38d5d-123">**Knihovna:** zahrnuty jako prostředek v MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="38d5d-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="38d5d-124">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38d5d-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38d5d-125">Viz také</span><span class="sxs-lookup"><span data-stu-id="38d5d-125">See Also</span></span>  
 [<span data-ttu-id="38d5d-126">Globální statické funkce metadat</span><span class="sxs-lookup"><span data-stu-id="38d5d-126">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
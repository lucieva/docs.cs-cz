---
title: "AssemblyBindInfo – struktura"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: AssemblyBindInfo
api_location: mscoree.dll
api_type: COM
f1_keywords: AssemblyBindInfo
helpviewer_keywords: AssemblyBindInfo structure [.NET Framework hosting]
ms.assetid: 6fc01e98-c2e7-49de-ab9f-95937cc89017
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4f23c8269c7dd7f85ad0f848c1dee2ed0bf903c0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="assemblybindinfo-structure"></a><span data-ttu-id="6ad0a-102">AssemblyBindInfo – struktura</span><span class="sxs-lookup"><span data-stu-id="6ad0a-102">AssemblyBindInfo Structure</span></span>
<span data-ttu-id="6ad0a-103">Poskytuje podrobné informace o odkazované sestavení.</span><span class="sxs-lookup"><span data-stu-id="6ad0a-103">Provides detailed information about the referenced assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ad0a-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="6ad0a-104">Syntax</span></span>  
  
```  
typedef struct _AssemblyBindInfo {  
    DWORD       dwAppDomainId;  
    LPCWSTR     lpReferencedIdentity;  
    LPCWSTR     lpPostPolicyIdentity;  
    DWORD       ePolicyLevel;  
} AssemblyBindInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="6ad0a-105">Členové</span><span class="sxs-lookup"><span data-stu-id="6ad0a-105">Members</span></span>  
  
|<span data-ttu-id="6ad0a-106">Člen</span><span class="sxs-lookup"><span data-stu-id="6ad0a-106">Member</span></span>|<span data-ttu-id="6ad0a-107">Popis</span><span class="sxs-lookup"><span data-stu-id="6ad0a-107">Description</span></span>|  
|------------|-----------------|  
|`dwAppDomainId`|<span data-ttu-id="6ad0a-108">Jedinečný identifikátor `IStream` vrácený volání [ihostassemblystore::provideassembly –](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md), ze které odkazované sestavení se jej načíst.</span><span class="sxs-lookup"><span data-stu-id="6ad0a-108">A unique identifier for the `IStream` returned by a call to [IHostAssemblyStore::ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md), from which the referenced assembly is to be loaded.</span></span>|  
|`lpReferencedIdentity`|<span data-ttu-id="6ad0a-109">Jedinečný identifikátor pro odkazované sestavení.</span><span class="sxs-lookup"><span data-stu-id="6ad0a-109">A unique identifier for the referenced assembly.</span></span>|  
|`lpPostPolicyIdentity`|<span data-ttu-id="6ad0a-110">Identifikátor pro odkazované sestavení po použití hodnoty zásad žádné vazby.</span><span class="sxs-lookup"><span data-stu-id="6ad0a-110">The identifier for the referenced assembly after the application of any binding policy values.</span></span>|  
|`ePolicyLevel`|<span data-ttu-id="6ad0a-111">Jeden z [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) hodnoty, které označují, které zásady správy verzí, pokud existuje, bude použito k odkazované sestavení.</span><span class="sxs-lookup"><span data-stu-id="6ad0a-111">One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values that indicate which versioning policies, if any, should be applied to the referenced assembly.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6ad0a-112">Poznámky</span><span class="sxs-lookup"><span data-stu-id="6ad0a-112">Remarks</span></span>  
 <span data-ttu-id="6ad0a-113">Hostitel poskytuje jedinečný identifikátor `dwAppDomainId` do common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="6ad0a-113">The host supplies the unique identifier `dwAppDomainId` to the common language runtime (CLR).</span></span> <span data-ttu-id="6ad0a-114">Po volání `IHostAssemblyStore::ProvideAssembly` vrací, běhové prostředí používá k určení identifikátor zda obsah `IStream` namapované.</span><span class="sxs-lookup"><span data-stu-id="6ad0a-114">After a call to `IHostAssemblyStore::ProvideAssembly` returns, the runtime uses the identifier to determine whether the contents of the `IStream` have been mapped.</span></span> <span data-ttu-id="6ad0a-115">Pokud ano, načte modul runtime existující kopie místo přemapování datového proudu.</span><span class="sxs-lookup"><span data-stu-id="6ad0a-115">If so, the runtime loads the existing copy rather than remapping the stream.</span></span> <span data-ttu-id="6ad0a-116">Modul runtime tento identifikátor také používá jako klíč vyhledávání pro datové proudy vrácená z volání [ihostassemblystore::providemodule –](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md).</span><span class="sxs-lookup"><span data-stu-id="6ad0a-116">The runtime also uses this identifier as a lookup key for streams returned from calls to [IHostAssemblyStore::ProvideModule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md).</span></span> <span data-ttu-id="6ad0a-117">Identifikátor proto musí být jedinečný pro modul požadavky a požadavky sestavení.</span><span class="sxs-lookup"><span data-stu-id="6ad0a-117">Therefore, the identifier must be unique for module requests and for assembly requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ad0a-118">Požadavky</span><span class="sxs-lookup"><span data-stu-id="6ad0a-118">Requirements</span></span>  
 <span data-ttu-id="6ad0a-119">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ad0a-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ad0a-120">**Záhlaví:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="6ad0a-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="6ad0a-121">**Knihovna:** zahrnuty jako prostředek v MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6ad0a-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6ad0a-122">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ad0a-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ad0a-123">Viz také</span><span class="sxs-lookup"><span data-stu-id="6ad0a-123">See Also</span></span>  
 [<span data-ttu-id="6ad0a-124">Struktury pro hostování</span><span class="sxs-lookup"><span data-stu-id="6ad0a-124">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
 [<span data-ttu-id="6ad0a-125">Iclrassemblyidentitymanager – rozhraní</span><span class="sxs-lookup"><span data-stu-id="6ad0a-125">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="6ad0a-126">Iclrassemblyreferencelist – rozhraní</span><span class="sxs-lookup"><span data-stu-id="6ad0a-126">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="6ad0a-127">Ihostassemblymanager – rozhraní</span><span class="sxs-lookup"><span data-stu-id="6ad0a-127">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [<span data-ttu-id="6ad0a-128">Ihostassemblystore – rozhraní</span><span class="sxs-lookup"><span data-stu-id="6ad0a-128">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)  
 [<span data-ttu-id="6ad0a-129">Modulebindinfo – struktura</span><span class="sxs-lookup"><span data-stu-id="6ad0a-129">ModuleBindInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md)
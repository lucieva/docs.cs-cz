---
title: "&lt;Vymazat&gt; Element pro schemeSettings (nastavení Uri)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 65098332-ce61-4542-ab8d-e7dc0257d31f
caps.latest.revision: "7"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: a2a4841635b5d6bcaa49d024dd92241573473036
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="ltcleargt-element-for-schemesettings-uri-settings"></a><span data-ttu-id="10a1a-102">&lt;Vymazat&gt; Element pro schemeSettings (nastavení Uri)</span><span class="sxs-lookup"><span data-stu-id="10a1a-102">&lt;clear&gt; Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="10a1a-103">Vymaže všechna existující nastavení schéma.</span><span class="sxs-lookup"><span data-stu-id="10a1a-103">Clears all existing scheme settings.</span></span>  
  
 <span data-ttu-id="10a1a-104">\<Konfigurace ></span><span class="sxs-lookup"><span data-stu-id="10a1a-104">\<configuration></span></span>  
<span data-ttu-id="10a1a-105">\<identifikátor URI ></span><span class="sxs-lookup"><span data-stu-id="10a1a-105">\<uri></span></span>  
<span data-ttu-id="10a1a-106">\<schemeSettings ></span><span class="sxs-lookup"><span data-stu-id="10a1a-106">\<schemeSettings></span></span>  
<span data-ttu-id="10a1a-107">\<Clear ></span><span class="sxs-lookup"><span data-stu-id="10a1a-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10a1a-108">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="10a1a-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="10a1a-109">Atributy a elementy</span><span class="sxs-lookup"><span data-stu-id="10a1a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="10a1a-110">Následující části popisují atributy, podřízené prvky a nadřazené prvky.</span><span class="sxs-lookup"><span data-stu-id="10a1a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="10a1a-111">Atributy</span><span class="sxs-lookup"><span data-stu-id="10a1a-111">Attributes</span></span>  
 <span data-ttu-id="10a1a-112">Žádné</span><span class="sxs-lookup"><span data-stu-id="10a1a-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="10a1a-113">Podřízené elementy</span><span class="sxs-lookup"><span data-stu-id="10a1a-113">Child Elements</span></span>  
 <span data-ttu-id="10a1a-114">Žádné</span><span class="sxs-lookup"><span data-stu-id="10a1a-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="10a1a-115">Nadřazené elementy</span><span class="sxs-lookup"><span data-stu-id="10a1a-115">Parent Elements</span></span>  
  
|<span data-ttu-id="10a1a-116">Prvek</span><span class="sxs-lookup"><span data-stu-id="10a1a-116">Element</span></span>|<span data-ttu-id="10a1a-117">Popis</span><span class="sxs-lookup"><span data-stu-id="10a1a-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="10a1a-118">\<schemeSettings > – Element (nastavení Uri)</span><span class="sxs-lookup"><span data-stu-id="10a1a-118">\<schemeSettings> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="10a1a-119">Určuje, jak <xref:System.Uri> bude analyzovat pro konkrétní schémat.</span><span class="sxs-lookup"><span data-stu-id="10a1a-119">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="10a1a-120">Poznámky</span><span class="sxs-lookup"><span data-stu-id="10a1a-120">Remarks</span></span>  
 <span data-ttu-id="10a1a-121">Ve výchozím nastavení <xref:System.Uri?displayProperty=nameWithType> třída zrušení – řídicí sekvence procent kódovaný cesta oddělovače před provedením cesta komprese.</span><span class="sxs-lookup"><span data-stu-id="10a1a-121">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="10a1a-122">Tato možnost byla implementovaná jako vhodný mechanismus zabezpečení před útoky takto:</span><span class="sxs-lookup"><span data-stu-id="10a1a-122">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="10a1a-123">Pokud tento identifikátor URI předána dolů moduly není zpracování procent kódování znaků správně, to může způsobit vykonáván serveru následující příkaz:</span><span class="sxs-lookup"><span data-stu-id="10a1a-123">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="10a1a-124">Z tohoto důvodu <xref:System.Uri?displayProperty=nameWithType> třídy první oddělovače zrušení – řídicí sekvence cestu a poté použije cesta komprese.</span><span class="sxs-lookup"><span data-stu-id="10a1a-124">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="10a1a-125">Výsledek předáním škodlivý adresu URL výše na <xref:System.Uri?displayProperty=nameWithType> třídy konstruktor má za následek následující identifikátor URI:</span><span class="sxs-lookup"><span data-stu-id="10a1a-125">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="10a1a-126">Toto výchozí chování můžete upravit tak, aby není zrušení řídicí procenta kódovaného cesta oddělovače pomocí možnosti konfigurace schemeSettings pro konkrétní schéma.</span><span class="sxs-lookup"><span data-stu-id="10a1a-126">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="10a1a-127">Konfigurační soubory</span><span class="sxs-lookup"><span data-stu-id="10a1a-127">Configuration Files</span></span>  
 <span data-ttu-id="10a1a-128">Tento element lze použít v konfiguračním souboru aplikace nebo v konfiguračním souboru počítače (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="10a1a-128">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="10a1a-129">Příklad</span><span class="sxs-lookup"><span data-stu-id="10a1a-129">Example</span></span>  
 <span data-ttu-id="10a1a-130">Následující příklad ukazuje konfigurace používané <xref:System.Uri> třídu, která vymaže všechna nastavení schéma a pak přidává podporu pro není uvozovací znaky oddělovače kódováním procent cestu pro schéma protokolu http.</span><span class="sxs-lookup"><span data-stu-id="10a1a-130">The following example shows a configuration used by the <xref:System.Uri> class that clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <clear/>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="10a1a-131">Viz také</span><span class="sxs-lookup"><span data-stu-id="10a1a-131">See Also</span></span>  
 <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>  
 <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>  
 <xref:System.GenericUriParserOptions?displayProperty=nameWithType>  
 <xref:System.Uri?displayProperty=nameWithType>  
 [<span data-ttu-id="10a1a-132">Schéma nastavení sítě</span><span class="sxs-lookup"><span data-stu-id="10a1a-132">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
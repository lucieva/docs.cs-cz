---
title: "&lt;cryptoclass –&gt; – Element"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/cryptoClasses/cryptoClass
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoClass
helpviewer_keywords:
- cryptoClass element
- <cryptoClass> element
ms.assetid: 03db52ef-010e-44ea-b6fd-b9c900ecad50
caps.latest.revision: "14"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 448e2c83f6897fd876bb79dfb781bcf4ddd2252b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="ltcryptoclassgt-element"></a><span data-ttu-id="258f8-102">&lt;cryptoclass –&gt; – Element</span><span class="sxs-lookup"><span data-stu-id="258f8-102">&lt;cryptoClass&gt; Element</span></span>
<span data-ttu-id="258f8-103">Obsahuje třídy šifrování, která má mapování na popisného názvu do [ \<nameEntry >](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) element.</span><span class="sxs-lookup"><span data-stu-id="258f8-103">Contains a cryptography class that has a mapping to a friendly name in the [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) element.</span></span>  
  
 <span data-ttu-id="258f8-104">\<Konfigurace ></span><span class="sxs-lookup"><span data-stu-id="258f8-104">\<configuration></span></span>  
<span data-ttu-id="258f8-105">\<mscorlib ></span><span class="sxs-lookup"><span data-stu-id="258f8-105">\<mscorlib></span></span>  
<span data-ttu-id="258f8-106">\<cryptographySettings – ></span><span class="sxs-lookup"><span data-stu-id="258f8-106">\<cryptographySettings></span></span>  
<span data-ttu-id="258f8-107">\<cryptoNameMapping ></span><span class="sxs-lookup"><span data-stu-id="258f8-107">\<cryptoNameMapping></span></span>  
<span data-ttu-id="258f8-108">\<cryptoClasses – ></span><span class="sxs-lookup"><span data-stu-id="258f8-108">\<cryptoClasses></span></span>  
<span data-ttu-id="258f8-109">\<cryptoclass – ></span><span class="sxs-lookup"><span data-stu-id="258f8-109">\<cryptoClass></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="258f8-110">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="258f8-110">Syntax</span></span>  
  
```xml  
<cryptoClass customClassName="fully qualified type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="258f8-111">Atributy a elementy</span><span class="sxs-lookup"><span data-stu-id="258f8-111">Attributes and Elements</span></span>  
 <span data-ttu-id="258f8-112">Následující části popisují atributy, podřízené prvky a nadřazené prvky.</span><span class="sxs-lookup"><span data-stu-id="258f8-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="258f8-113">Atributy</span><span class="sxs-lookup"><span data-stu-id="258f8-113">Attributes</span></span>  
  
|<span data-ttu-id="258f8-114">Atribut</span><span class="sxs-lookup"><span data-stu-id="258f8-114">Attribute</span></span>|<span data-ttu-id="258f8-115">Popis</span><span class="sxs-lookup"><span data-stu-id="258f8-115">Description</span></span>|  
|---------------|-----------------|  
|`customClassName`|<span data-ttu-id="258f8-116">Požadovaný atribut.</span><span class="sxs-lookup"><span data-stu-id="258f8-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="258f8-117">Obsahuje informace o třídě šifrování.</span><span class="sxs-lookup"><span data-stu-id="258f8-117">Contains the information for the cryptography class.</span></span> <span data-ttu-id="258f8-118">Pomocí tohoto atributu zadejte krátký název pro vlastní třídy.</span><span class="sxs-lookup"><span data-stu-id="258f8-118">Use this attribute to provide a short name for your class.</span></span> <span data-ttu-id="258f8-119">Zadejte řetězec, který splňuje požadavky uvedené v [určení plně kvalifikované názvy typů](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="258f8-119">You must specify a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="258f8-120">Podřízené elementy</span><span class="sxs-lookup"><span data-stu-id="258f8-120">Child Elements</span></span>  
 <span data-ttu-id="258f8-121">Žádné</span><span class="sxs-lookup"><span data-stu-id="258f8-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="258f8-122">Nadřazené elementy</span><span class="sxs-lookup"><span data-stu-id="258f8-122">Parent Elements</span></span>  
  
|<span data-ttu-id="258f8-123">Prvek</span><span class="sxs-lookup"><span data-stu-id="258f8-123">Element</span></span>|<span data-ttu-id="258f8-124">Popis</span><span class="sxs-lookup"><span data-stu-id="258f8-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="258f8-125">Kořenový prvek v každém konfiguračním souboru, který je používán modulem Common Language Runtime (CLR) a aplikacemi rozhraní .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="258f8-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptoClasses`|<span data-ttu-id="258f8-126">Obsahuje seznam tříd šifrování, které mají mapování na popisného názvu do [ \<nameEntry >](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) element.</span><span class="sxs-lookup"><span data-stu-id="258f8-126">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) element.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="258f8-127">Obsahuje nastavení šifrování.</span><span class="sxs-lookup"><span data-stu-id="258f8-127">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="258f8-128">Obsahuje mapování třídy popisné názvy.</span><span class="sxs-lookup"><span data-stu-id="258f8-128">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="258f8-129">Obsahuje [ \<cryptographySettings – >](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md) element.</span><span class="sxs-lookup"><span data-stu-id="258f8-129">Contains the [\<cryptographySettings>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md) element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="258f8-130">Příklad</span><span class="sxs-lookup"><span data-stu-id="258f8-130">Example</span></span>  
 <span data-ttu-id="258f8-131">Následující příklad ukazuje, jak používat  **\<cryptoclass – >** element tak, aby odkazovaly kryptografické třídy a ke konfiguraci modulu runtime.</span><span class="sxs-lookup"><span data-stu-id="258f8-131">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="258f8-132">Řetězec "RSA" můžete poté předat do <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> metoda a použít <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> metoda vrátí `MyCryptoRSAClass` objektu.</span><span class="sxs-lookup"><span data-stu-id="258f8-132">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCryptoRSA="MyCryptoRSAClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="RSA" class="MyCryptoRSA"/>  
            <nameEntry name="System.Security.Cryptography.AsymmetricAlgorithm"  
                       class="MyCryptoRSA"/>  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="258f8-133">Viz také</span><span class="sxs-lookup"><span data-stu-id="258f8-133">See Also</span></span>  
 [<span data-ttu-id="258f8-134">Schéma konfiguračního souboru</span><span class="sxs-lookup"><span data-stu-id="258f8-134">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="258f8-135">Schéma nastavení šifrování</span><span class="sxs-lookup"><span data-stu-id="258f8-135">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 [<span data-ttu-id="258f8-136">Kryptografické služby</span><span class="sxs-lookup"><span data-stu-id="258f8-136">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)  
 [<span data-ttu-id="258f8-137">Konfigurace šifrovacích tříd</span><span class="sxs-lookup"><span data-stu-id="258f8-137">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
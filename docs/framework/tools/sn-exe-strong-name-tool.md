---
title: "Sn.exe (nástroj pro silný název)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- public keys, signing files
- Strong Name tool
- Sn.exe
- assemblies [.NET Framework], signing
- signing files
- strong-named assemblies, signing files
- key pairs for signing files
ms.assetid: c1d2b532-1b8e-4c7a-8ac5-53b801135ec6
caps.latest.revision: "44"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e303246737d52f76d893074973804710b2dc9b71
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="snexe-strong-name-tool"></a><span data-ttu-id="c8738-102">Sn.exe (nástroj pro silný název)</span><span class="sxs-lookup"><span data-stu-id="c8738-102">Sn.exe (Strong Name Tool)</span></span>
<span data-ttu-id="c8738-103">Nástroj silného názvu (Sn.exe) pomáhá přihlašovací sestavení s [silné názvy](../../../docs/framework/app-domains/strong-named-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="c8738-103">The Strong Name tool (Sn.exe) helps sign assemblies with [strong names](../../../docs/framework/app-domains/strong-named-assemblies.md).</span></span> <span data-ttu-id="c8738-104">Nástroj Sn.exe poskytuje možnosti pro správu klíčů, generování podpisů a ověřování podpisů.</span><span class="sxs-lookup"><span data-stu-id="c8738-104">Sn.exe provides options for key management, signature generation, and signature verification.</span></span>  
  
 <span data-ttu-id="c8738-105">Další informace o silné názvy a sestavení se silným názvem naleznete v tématu [sestavení se silným názvem](../../../docs/framework/app-domains/strong-named-assemblies.md) a [postupy: podepsání sestavení se silným názvem](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="c8738-105">For more information on strong naming and strong-named assemblies, see [Strong-Named Assemblies](../../../docs/framework/app-domains/strong-named-assemblies.md) and [How to: Sign an Assembly with a Strong Name](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span></span>  
  
 <span data-ttu-id="c8738-106">Nástroj Strong Name je automaticky nainstalován se sadou Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c8738-106">The Strong Name tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="c8738-107">Spusťte nástroj pomocí příkazového řádku vývojáře (nebo příkazový řádek sady Visual Studio v systému Windows 7).</span><span class="sxs-lookup"><span data-stu-id="c8738-107">To start the tool, use the Developer Command Prompt (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="c8738-108">Další informace najdete v tématu [příkazového řádku](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="c8738-108">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c8738-109">Na 64bitových počítačích spusťte 32bitovou verzi Sn.exe pomocí příkazového řádku Visual Studio a 64bitová verze pomocí příkazového řádku Visual Studia x64 Win64.</span><span class="sxs-lookup"><span data-stu-id="c8738-109">On 64-bit computers, run the 32-bit version of Sn.exe by using the Visual Studio Command Prompt and the 64-bit version by using the Visual Studio x64 Win64 Command Prompt.</span></span>  
  
 <span data-ttu-id="c8738-110">V příkazovém řádku zadejte následující:</span><span class="sxs-lookup"><span data-stu-id="c8738-110">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8738-111">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="c8738-111">Syntax</span></span>  
  
```  
sn [-quiet][option [parameter(s)]]  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c8738-112">Parametry</span><span class="sxs-lookup"><span data-stu-id="c8738-112">Parameters</span></span>  
  
|<span data-ttu-id="c8738-113">Možnost</span><span class="sxs-lookup"><span data-stu-id="c8738-113">Option</span></span>|<span data-ttu-id="c8738-114">Popis</span><span class="sxs-lookup"><span data-stu-id="c8738-114">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="c8738-115">**-a** *identityKeyPairFile* *signaturePublicKeyFile*</span><span class="sxs-lookup"><span data-stu-id="c8738-115">**-a** *identityKeyPairFile* *signaturePublicKeyFile*</span></span>|<span data-ttu-id="c8738-116">Generuje <xref:System.Reflection.AssemblySignatureKeyAttribute> data migrovat do klíč podpisu klíč identity ze souboru.</span><span class="sxs-lookup"><span data-stu-id="c8738-116">Generates <xref:System.Reflection.AssemblySignatureKeyAttribute> data to migrate the identity key to the signature key from a file.</span></span>|  
|<span data-ttu-id="c8738-117">**-ac** *identityPublicKeyFile* *identityKeyPairContainer* *signaturePublicKeyFile*</span><span class="sxs-lookup"><span data-stu-id="c8738-117">**-ac** *identityPublicKeyFile* *identityKeyPairContainer* *signaturePublicKeyFile*</span></span>|<span data-ttu-id="c8738-118">Generuje <xref:System.Reflection.AssemblySignatureKeyAttribute> data migrovat do klíč podpisu klíč identity z kontejneru klíčů.</span><span class="sxs-lookup"><span data-stu-id="c8738-118">Generates <xref:System.Reflection.AssemblySignatureKeyAttribute> data to migrate the identity key to the signature key from a key container.</span></span>|  
|<span data-ttu-id="c8738-119">**-c** [*csp*]</span><span class="sxs-lookup"><span data-stu-id="c8738-119">**-c** [*csp*]</span></span>|<span data-ttu-id="c8738-120">Nastaví výchozího zprostředkovatele kryptografických služeb (CSP) pro použití k podepisování se silným názvem.</span><span class="sxs-lookup"><span data-stu-id="c8738-120">Sets the default cryptographic service provider (CSP) to use for strong name signing.</span></span> <span data-ttu-id="c8738-121">Toto nastavení platí pro celý počítač.</span><span class="sxs-lookup"><span data-stu-id="c8738-121">This setting applies to the entire computer.</span></span> <span data-ttu-id="c8738-122">Pokud název CSP nezadáte, nástroj Sn.exe vymaže aktuální nastavení.</span><span class="sxs-lookup"><span data-stu-id="c8738-122">If you do not specify a CSP name, Sn.exe clears the current setting.</span></span>|  
|<span data-ttu-id="c8738-123">**-d** *kontejneru*</span><span class="sxs-lookup"><span data-stu-id="c8738-123">**-d** *container*</span></span>|<span data-ttu-id="c8738-124">Odstraní zadaný kontejner klíče z CSP silného názvu.</span><span class="sxs-lookup"><span data-stu-id="c8738-124">Deletes the specified key container from the strong name CSP.</span></span>|  
|<span data-ttu-id="c8738-125">**-D***assembly1 assembly2* </span><span class="sxs-lookup"><span data-stu-id="c8738-125">**-D**  *assembly1 assembly2*</span></span>|<span data-ttu-id="c8738-126">Ověří, zda se dvě sestavení liší pouze v podpisu.</span><span class="sxs-lookup"><span data-stu-id="c8738-126">Verifies that two assemblies differ only by signature.</span></span> <span data-ttu-id="c8738-127">Toto se často používá jako kontrola poté, co bylo sestavení znovu podepsáno jiným párem klíčů.</span><span class="sxs-lookup"><span data-stu-id="c8738-127">This is often used as a check after an assembly has been re-signed with a different key pair.</span></span>|  
|<span data-ttu-id="c8738-128">**-e***Výstupní_soubor sestavení* </span><span class="sxs-lookup"><span data-stu-id="c8738-128">**-e**  *assembly outfile*</span></span>|<span data-ttu-id="c8738-129">Extrahuje veřejného klíče z *sestavení* a uloží jej do *Výstupní_soubor.*</span><span class="sxs-lookup"><span data-stu-id="c8738-129">Extracts the public key from *assembly* and stores it in *outfile.*</span></span>|  
|<span data-ttu-id="c8738-130">**-h**</span><span class="sxs-lookup"><span data-stu-id="c8738-130">**-h**</span></span>|<span data-ttu-id="c8738-131">Zobrazí syntaxi příkazu a možnosti nástroje.</span><span class="sxs-lookup"><span data-stu-id="c8738-131">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="c8738-132">**-i** *Vstupní_soubor kontejneru*</span><span class="sxs-lookup"><span data-stu-id="c8738-132">**-i** *infile container*</span></span>|<span data-ttu-id="c8738-133">Nainstaluje pár klíčů z *Vstupní_soubor* v zadaném kontejneru klíčů.</span><span class="sxs-lookup"><span data-stu-id="c8738-133">Installs the key pair from *infile* in the specified key container.</span></span> <span data-ttu-id="c8738-134">Kontejner klíčů je umístěn v CSP silného názvu.</span><span class="sxs-lookup"><span data-stu-id="c8738-134">The key container resides in the strong name CSP.</span></span>|  
|<span data-ttu-id="c8738-135">**-k** [*velikost klíče*] *Výstupní_soubor*</span><span class="sxs-lookup"><span data-stu-id="c8738-135">**-k** [*keysize*] *outfile*</span></span>|<span data-ttu-id="c8738-136">Generuje nový <xref:System.Security.Cryptography.RSACryptoServiceProvider> klíče zadané velikosti a zapíše ho do zadaného souboru.</span><span class="sxs-lookup"><span data-stu-id="c8738-136">Generates a new <xref:System.Security.Cryptography.RSACryptoServiceProvider> key of the specified size and writes it to the specified file.</span></span>  <span data-ttu-id="c8738-137">Do souboru je zapsán veřejný i soukromý klíč.</span><span class="sxs-lookup"><span data-stu-id="c8738-137">Both a public and private key are written to the file.</span></span><br /><br /> <span data-ttu-id="c8738-138">Nezadáte-li velikost klíče, je dle výchozího nastavení vygenerován 1024bitový klíč, pokud máte nainstalovaný vylepšený zprostředkovatel kryptografických služeb Microsoft. V opačném případě je vygenerován 512bitový klíč.</span><span class="sxs-lookup"><span data-stu-id="c8738-138">If you do not specify a key size, a 1,024-bit key is generated by default if you have the Microsoft enhanced cryptographic provider installed; otherwise, a 512-bit key is generated.</span></span><br /><br /> <span data-ttu-id="c8738-139">*Velikost klíče* parametr podporuje délky klíčů z 384 bitů na 16 384 bitů v přírůstcích po 8 bitů, pokud máte Microsoft rozšířené zprostředkovatelem kryptografických služeb nainstalován.</span><span class="sxs-lookup"><span data-stu-id="c8738-139">The *keysize* parameter supports key lengths from 384 bits to 16,384 bits in increments of 8 bits if you have the Microsoft enhanced cryptographic provider installed.</span></span>  <span data-ttu-id="c8738-140">Je-li nainstalován základní zprostředkovatel kryptografických služeb Microsoft, podporuje délky klíčů od 384 do 512 bitů v krocích po 8 bitech.</span><span class="sxs-lookup"><span data-stu-id="c8738-140">It supports key lengths from 384 bits to 512 bits in increments of 8 bits if you have the Microsoft base cryptographic provider installed.</span></span>|  
|<span data-ttu-id="c8738-141">**-m** [**y** *&#124;* **n**]</span><span class="sxs-lookup"><span data-stu-id="c8738-141">**-m** [**y** *&#124;* **n**]</span></span>|<span data-ttu-id="c8738-142">Určí, zda jsou kontejnery klíčů specifické pro počítač nebo pro uživatele.</span><span class="sxs-lookup"><span data-stu-id="c8738-142">Specifies whether key containers are computer-specific, or user-specific.</span></span> <span data-ttu-id="c8738-143">Pokud zadáte *y*, kontejnery klíčů jsou specifické pro počítač.</span><span class="sxs-lookup"><span data-stu-id="c8738-143">If you specify *y*, key containers are computer-specific.</span></span> <span data-ttu-id="c8738-144">Pokud zadáte  *n* , kontejnery klíčů jsou specifické pro uživatele.</span><span class="sxs-lookup"><span data-stu-id="c8738-144">If you specify *n*, key containers are user-specific.</span></span><br /><br /> <span data-ttu-id="c8738-145">Není-li zadána žádná z hodnot y nebo n, zobrazí tato možnost aktuální nastavení.</span><span class="sxs-lookup"><span data-stu-id="c8738-145">If neither y nor n is specified, this option displays the current setting.</span></span>|  
|<span data-ttu-id="c8738-146">**-o***Vstupní_soubor* [*Výstupní_soubor*]  </span><span class="sxs-lookup"><span data-stu-id="c8738-146">**-o**  *infile* [*outfile*]</span></span>|<span data-ttu-id="c8738-147">Extrahuje veřejného klíče z *Vstupní_soubor* a ukládá je v souboru CSV.</span><span class="sxs-lookup"><span data-stu-id="c8738-147">Extracts the public key from the *infile* and stores it in a .csv file.</span></span> <span data-ttu-id="c8738-148">Každý bajt veřejného klíče je oddělen čárkou.</span><span class="sxs-lookup"><span data-stu-id="c8738-148">A comma separates each byte of the public key.</span></span> <span data-ttu-id="c8738-149">Tento formát je užitečný pro pevné zakódování odkazů na klíče jako inicializovaných polí ve zdrojovém kódu.</span><span class="sxs-lookup"><span data-stu-id="c8738-149">This format is useful for hard-coding references to keys as initialized arrays in source code.</span></span> <span data-ttu-id="c8738-150">Pokud nezadáte *Výstupní_soubor*, tato možnost umístí výstup do schránky.</span><span class="sxs-lookup"><span data-stu-id="c8738-150">If you do not specify an *outfile*, this option places the output on the Clipboard.</span></span> <span data-ttu-id="c8738-151">**Poznámka:** tato možnost není ověřte, zda vstup je veřejný klíč.</span><span class="sxs-lookup"><span data-stu-id="c8738-151">**Note:**  This option does not verify that the input is only a public key.</span></span> <span data-ttu-id="c8738-152">Pokud `infile` obsahuje pár klíčů s privátním klíčem, je také extrahován privátní klíč.</span><span class="sxs-lookup"><span data-stu-id="c8738-152">If the `infile` contains a key pair with a private key, the private key is also extracted.</span></span>|  
|<span data-ttu-id="c8738-153">**-p** *Vstupní_soubor Výstupní_soubor* [*Algoritmus_hash*]</span><span class="sxs-lookup"><span data-stu-id="c8738-153">**-p** *infile outfile* [*hashalg*]</span></span>|<span data-ttu-id="c8738-154">Extrahuje veřejný klíč z tohoto páru klíčů v *Vstupní_soubor* a uloží jej do *Výstupní_soubor*, volitelně pomocí algoritmu RSA určeného *Algoritmus_hash*.</span><span class="sxs-lookup"><span data-stu-id="c8738-154">Extracts the public key from the key pair in *infile* and stores it in *outfile*, optionally using the RSA algorithm specified by *hashalg*.</span></span> <span data-ttu-id="c8738-155">Tento veřejný klíč může být použit zpoždění podepsání sestavení pomocí **/delaysign+** a **/keyfile** možnosti [Linker sestavení (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md).</span><span class="sxs-lookup"><span data-stu-id="c8738-155">This public key can be used to delay-sign an assembly using the **/delaysign+** and **/keyfile** options of the [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md).</span></span> <span data-ttu-id="c8738-156">Pokud je sestavení podepsáno opožděně, je v době kompilace nastaven pouze veřejný klíč a v souboru je vyhrazen prostor pro pozdější přidání podpisu, až bude znám soukromý klíč.</span><span class="sxs-lookup"><span data-stu-id="c8738-156">When an assembly is delay-signed, only the public key is set at compile time and space is reserved in the file for the signature to be added later, when the private key is known.</span></span>|  
|<span data-ttu-id="c8738-157">**-pc***kontejneru* *Výstupní_soubor* [*Algoritmus_hash*]  </span><span class="sxs-lookup"><span data-stu-id="c8738-157">**-pc**  *container* *outfile* [*hashalg*]</span></span>|<span data-ttu-id="c8738-158">Extrahuje veřejný klíč z tohoto páru klíčů v *kontejneru* a uloží jej do *Výstupní_soubor*.</span><span class="sxs-lookup"><span data-stu-id="c8738-158">Extracts the public key from the key pair in *container* and stores it in *outfile*.</span></span> <span data-ttu-id="c8738-159">Pokud použijete *Algoritmus_hash* možnost, algoritmus RSA slouží k extrakci veřejný klíč.</span><span class="sxs-lookup"><span data-stu-id="c8738-159">If you use the *hashalg* option, the RSA algorithm is used to extract the public key.</span></span>|  
|<span data-ttu-id="c8738-160">**-Pb** [**y** *&#124;* **n**]</span><span class="sxs-lookup"><span data-stu-id="c8738-160">**-Pb** [**y** *&#124;* **n**]</span></span>|<span data-ttu-id="c8738-161">Určí, zda bude vynucena zásada potlačení silných názvů.</span><span class="sxs-lookup"><span data-stu-id="c8738-161">Specifies whether the strong-name bypass policy is enforced.</span></span> <span data-ttu-id="c8738-162">Pokud zadáte *y*, silné názvy pro plné důvěryhodnosti sestavení uděláte, neověřuje při načítání do plné důvěryhodnosti <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="c8738-162">If you specify *y*, strong names for full-trust assemblies are not validated when loaded into a full-trust <xref:System.AppDomain>.</span></span> <span data-ttu-id="c8738-163">Pokud zadáte  *n* , silné názvy se ověří správnost, ale ne pro konkrétní silný název.</span><span class="sxs-lookup"><span data-stu-id="c8738-163">If you specify *n*, strong names are validated for correctness, but not for a specific strong name.</span></span> <span data-ttu-id="c8738-164"><xref:System.Security.Permissions.StrongNameIdentityPermission> Nemá žádný vliv na sestavení plné důvěryhodnosti.</span><span class="sxs-lookup"><span data-stu-id="c8738-164">The <xref:System.Security.Permissions.StrongNameIdentityPermission> has no effect on full-trust assemblies.</span></span> <span data-ttu-id="c8738-165">Je zapotřebí provést vlastní kontrolu shody silných názvů.</span><span class="sxs-lookup"><span data-stu-id="c8738-165">You must perform your own check for a strong name match.</span></span><br /><br /> <span data-ttu-id="c8738-166">Pokud ani `y` ani `n` není zadaný, tato možnost zobrazí aktuální nastavení.</span><span class="sxs-lookup"><span data-stu-id="c8738-166">If neither `y` nor `n` is specified, this option displays the current setting.</span></span> <span data-ttu-id="c8738-167">Výchozí hodnota je `y`.</span><span class="sxs-lookup"><span data-stu-id="c8738-167">The default is `y`.</span></span> <span data-ttu-id="c8738-168">**Poznámka:** na 64bitových počítačích, musí v 32bitová verze a 64bitová verze instance Sn.exe nastavte tento parametr.</span><span class="sxs-lookup"><span data-stu-id="c8738-168">**Note:**  On 64-bit computers, you must set this parameter in both the 32-bit and the 64-bit instances of Sn.exe.</span></span>|  
|<span data-ttu-id="c8738-169">**-q**[**uiet**]</span><span class="sxs-lookup"><span data-stu-id="c8738-169">**-q**[**uiet**]</span></span>|<span data-ttu-id="c8738-170">Určuje použití tichého režimu; potlačí zobrazování zpráv o úspěchu.</span><span class="sxs-lookup"><span data-stu-id="c8738-170">Specifies quiet mode; suppresses the display of success messages.</span></span>|  
|<span data-ttu-id="c8738-171">**-R**[****] *sestavení* *Vstupní_soubor*</span><span class="sxs-lookup"><span data-stu-id="c8738-171">**-R**[**a**] *assembly* *infile*</span></span>|<span data-ttu-id="c8738-172">Znovu podepíše dříve podepsané nebo zpoždění podepsané sestavení s páru klíčů v *Vstupní_soubor*.</span><span class="sxs-lookup"><span data-stu-id="c8738-172">Re-signs a previously signed or delay-signed assembly with the key pair in *infile*.</span></span><br /><br /> <span data-ttu-id="c8738-173">Pokud **-Ra** se používá, hodnoty hash přepočítávány pro všechny soubory v sestavení.</span><span class="sxs-lookup"><span data-stu-id="c8738-173">If **-Ra** is used, hashes are recomputed for all files in the assembly.</span></span>|  
|<span data-ttu-id="c8738-174">**-Rc**[****] *kontejneru sestavení*</span><span class="sxs-lookup"><span data-stu-id="c8738-174">**-Rc**[**a**] *assembly container*</span></span>|<span data-ttu-id="c8738-175">Znovu podepíše dříve podepsané nebo zpoždění podepsané sestavení s páru klíčů v *kontejneru*.</span><span class="sxs-lookup"><span data-stu-id="c8738-175">Re-signs a previously signed or delay-signed assembly with the key pair in *container*.</span></span><br /><br /> <span data-ttu-id="c8738-176">Pokud **- Rca** se používá, hodnoty hash přepočítávány pro všechny soubory v sestavení.</span><span class="sxs-lookup"><span data-stu-id="c8738-176">If **-Rca** is used, hashes are recomputed for all files in the assembly.</span></span>|  
|<span data-ttu-id="c8738-177">**-Rh** *sestavení*</span><span class="sxs-lookup"><span data-stu-id="c8738-177">**-Rh** *assembly*</span></span>|<span data-ttu-id="c8738-178">Přepočítá hodnoty hash pro všechny soubory v sestavení.</span><span class="sxs-lookup"><span data-stu-id="c8738-178">Recomputes hashes for all files in the assembly.</span></span>|  
|<span data-ttu-id="c8738-179">**-t**[**p**] *Vstupní_soubor*</span><span class="sxs-lookup"><span data-stu-id="c8738-179">**-t**[**p**] *infile*</span></span>|<span data-ttu-id="c8738-180">Zobrazí token pro veřejný klíč uložené v *Vstupní_soubor*.</span><span class="sxs-lookup"><span data-stu-id="c8738-180">Displays the token for the public key stored in *infile*.</span></span> <span data-ttu-id="c8738-181">Obsah *Vstupní_soubor* musí být veřejný klíč dříve generované ze souboru pár klíčů pomocí **-p**.</span><span class="sxs-lookup"><span data-stu-id="c8738-181">The contents of *infile* must be a public key previously generated from a key pair file using **-p**.</span></span>  <span data-ttu-id="c8738-182">Nepoužívejte **-t [p]** možnost extrahuje daný token přímo ze souboru pár klíčů.</span><span class="sxs-lookup"><span data-stu-id="c8738-182">Do not use the **-t[p]** option to extract the token directly from a key pair file.</span></span><br /><br /> <span data-ttu-id="c8738-183">Nástroj Sn.exe počítá token z veřejného klíče pomocí funkce hash.</span><span class="sxs-lookup"><span data-stu-id="c8738-183">Sn.exe computes the token by using a hash function from the public key.</span></span> <span data-ttu-id="c8738-184">Z důvodu šetření místem ukládá modul CLR tokeny veřejných klíčů do manifestů jako součást odkazů na jiné sestavení ve chvíli, kdy je do sestavení se silným názvem zaznamenána závislost.</span><span class="sxs-lookup"><span data-stu-id="c8738-184">To save space, the common language runtime stores public key tokens in the manifest as part of a reference to another assembly when it records a dependency to an assembly that has a strong name.</span></span> <span data-ttu-id="c8738-185">**- Tp** možnost zobrazí veřejný klíč kromě token.</span><span class="sxs-lookup"><span data-stu-id="c8738-185">The **-tp** option displays the public key in addition to the token.</span></span> <span data-ttu-id="c8738-186">Pokud <xref:System.Reflection.AssemblySignatureKeyAttribute> byl použit atribut sestavení, je token pro klíč identity a se zobrazí název algoritmu hash a klíč identity.</span><span class="sxs-lookup"><span data-stu-id="c8738-186">If the <xref:System.Reflection.AssemblySignatureKeyAttribute> attribute has been applied to the assembly, the token is for the identity key, and the name of the hash algorithm and the identity key is displayed.</span></span><br /><br /> <span data-ttu-id="c8738-187">Tato možnost neověřuje popis sestavení a neměla by být použita pro rozhodování o důvěryhodnosti.</span><span class="sxs-lookup"><span data-stu-id="c8738-187">Note that this option does not verify the assembly signature and should not be used to make trust decisions.</span></span>  <span data-ttu-id="c8738-188">Tato možnost zobrazuje pouze nezpracovaná data tokenu veřejného klíče.</span><span class="sxs-lookup"><span data-stu-id="c8738-188">This option only displays the raw public key token data.</span></span>|  
|<span data-ttu-id="c8738-189">**-T**[**p**] *sestavení*</span><span class="sxs-lookup"><span data-stu-id="c8738-189">**-T**[**p**] *assembly*</span></span>|<span data-ttu-id="c8738-190">Zobrazí token veřejného klíče pro *sestavení.*</span><span class="sxs-lookup"><span data-stu-id="c8738-190">Displays the public key token for *assembly.*</span></span> <span data-ttu-id="c8738-191">*Sestavení* musí být název souboru, který obsahuje manifest sestavení.</span><span class="sxs-lookup"><span data-stu-id="c8738-191">The *assembly* must be the name of a file that contains an assembly manifest.</span></span><br /><br /> <span data-ttu-id="c8738-192">Nástroj Sn.exe počítá token z veřejného klíče pomocí funkce hash.</span><span class="sxs-lookup"><span data-stu-id="c8738-192">Sn.exe computes the token by using a hash function from the public key.</span></span> <span data-ttu-id="c8738-193">Z důvodu šetření místem ukládá modul runtime tokeny veřejných klíčů do manifestů jako součást odkazů na jiné sestavení ve chvíli, kdy je do sestavení se silným názvem zaznamenána závislost.</span><span class="sxs-lookup"><span data-stu-id="c8738-193">To save space, the runtime stores public key tokens in the manifest as part of a reference to another assembly when it records a dependency to an assembly that has a strong name.</span></span> <span data-ttu-id="c8738-194">**- Tp** možnost zobrazí veřejný klíč kromě token.</span><span class="sxs-lookup"><span data-stu-id="c8738-194">The **-Tp** option displays the public key in addition to the token.</span></span> <span data-ttu-id="c8738-195">Pokud <xref:System.Reflection.AssemblySignatureKeyAttribute> byl použit atribut sestavení, je token pro klíč identity a se zobrazí název algoritmu hash a klíč identity.</span><span class="sxs-lookup"><span data-stu-id="c8738-195">If the <xref:System.Reflection.AssemblySignatureKeyAttribute> attribute has been applied to the assembly, the token is for the identity key, and the name of the hash algorithm and the identity key is displayed.</span></span><br /><br /> <span data-ttu-id="c8738-196">Tato možnost neověřuje popis sestavení a neměla by být použita pro rozhodování o důvěryhodnosti.</span><span class="sxs-lookup"><span data-stu-id="c8738-196">Note that this option does not verify the assembly signature and should not be used to make trust decisions.</span></span>  <span data-ttu-id="c8738-197">Tato možnost zobrazuje pouze nezpracovaná data tokenu veřejného klíče.</span><span class="sxs-lookup"><span data-stu-id="c8738-197">This option only displays the raw public key token data.</span></span>|  
|<span data-ttu-id="c8738-198">`-TS` `assembly` `infile`</span><span class="sxs-lookup"><span data-stu-id="c8738-198">`-TS` `assembly` `infile`</span></span>|<span data-ttu-id="c8738-199">Test přihlásí podepsaný držitelem nebo částečně podepsané `assembly` s páru klíčů v `infile`.</span><span class="sxs-lookup"><span data-stu-id="c8738-199">Test-signs the signed or partially signed `assembly` with the key pair in `infile`.</span></span>|  
|-`TSc``assembly``container`|<span data-ttu-id="c8738-200">Test přihlásí podepsaný držitelem nebo částečně podepsané `assembly` s páru klíčů v kontejneru klíčů `container`.</span><span class="sxs-lookup"><span data-stu-id="c8738-200">Test-signs the signed or partially signed `assembly` with the key pair in the key container `container`.</span></span>|  
|<span data-ttu-id="c8738-201">**-v** *sestavení*</span><span class="sxs-lookup"><span data-stu-id="c8738-201">**-v** *assembly*</span></span>|<span data-ttu-id="c8738-202">Ověřuje silného názvu v *sestavení*, kde *sestavení* je název souboru, který obsahuje manifest sestavení.</span><span class="sxs-lookup"><span data-stu-id="c8738-202">Verifies the strong name in *assembly*, where *assembly* is the name of a file that contains an assembly manifest.</span></span>|  
|<span data-ttu-id="c8738-203">**-vf***sestavení* </span><span class="sxs-lookup"><span data-stu-id="c8738-203">**-vf**  *assembly*</span></span>|<span data-ttu-id="c8738-204">Ověřuje silného názvu v *sestavení.*</span><span class="sxs-lookup"><span data-stu-id="c8738-204">Verifies the strong name in *assembly.*</span></span> <span data-ttu-id="c8738-205">Na rozdíl od **- v** možnost, **-vf** vynutí ověření, i když je zakázán, pomocí **- Vr** možnost.</span><span class="sxs-lookup"><span data-stu-id="c8738-205">Unlike the **-v** option, **-vf** forces verification even if it is disabled using the **-Vr** option.</span></span>|  
|<span data-ttu-id="c8738-206">**-Vk***regfile.reg* *sestavení* [*userlist*] [*Vstupní_soubor*]  </span><span class="sxs-lookup"><span data-stu-id="c8738-206">**-Vk**  *regfile.reg* *assembly* [*userlist*] [*infile*]</span></span>|<span data-ttu-id="c8738-207">Vytvoří soubor registračních položek (.reg), které lze použít k registraci zadaného sestavení pro vynechání ověření.</span><span class="sxs-lookup"><span data-stu-id="c8738-207">Creates a registration entries (.reg) file you can use to register the specified assembly for verification skipping.</span></span> <span data-ttu-id="c8738-208">Pravidla pro názvy sestavení, která se vztahují k **- Vr** možnost použít **– Vk** také.</span><span class="sxs-lookup"><span data-stu-id="c8738-208">The rules for assembly naming that apply to the **-Vr** option apply to **–Vk** as well.</span></span> <span data-ttu-id="c8738-209">Informace o *userlist* a *Vstupní_soubor* najdete v části Možnosti, **– Vr** možnost.</span><span class="sxs-lookup"><span data-stu-id="c8738-209">For information about the *userlist* and *infile* options, see the **–Vr** option.</span></span>|  
|<span data-ttu-id="c8738-210">**-Vl**</span><span class="sxs-lookup"><span data-stu-id="c8738-210">**-Vl**</span></span>|<span data-ttu-id="c8738-211">Vypíše aktuální nastavení pro ověřování silných názvů v tomto počítači.</span><span class="sxs-lookup"><span data-stu-id="c8738-211">Lists current settings for strong-name verification on this computer.</span></span>|  
|<span data-ttu-id="c8738-212">**-Vr***sestavení* [*userlist*] [*Vstupní_soubor*]  </span><span class="sxs-lookup"><span data-stu-id="c8738-212">**-Vr**  *assembly* [*userlist*] [*infile*]</span></span>|<span data-ttu-id="c8738-213">Zaregistruje *sestavení* pro přeskočení ověření.</span><span class="sxs-lookup"><span data-stu-id="c8738-213">Registers *assembly* for verification skipping.</span></span> <span data-ttu-id="c8738-214">Volitelně lze také zadat čárkou oddělený seznam uživatelských jmen, pro která by vynechání ověřování mělo platit.</span><span class="sxs-lookup"><span data-stu-id="c8738-214">Optionally, you can specify a comma-separated list of user names the skip verification should apply to.</span></span> <span data-ttu-id="c8738-215">Pokud zadáte *Vstupní_soubor*, zůstanou ověření povoleno, ale veřejný klíč v *Vstupní_soubor* se používá v operacích ověření.</span><span class="sxs-lookup"><span data-stu-id="c8738-215">If you specify *infile*, verification remains enabled, but the public key in *infile* is used in verification operations.</span></span> <span data-ttu-id="c8738-216">Můžete zadat *sestavení* ve tvaru  *\*, strongname* pro registraci všechny sestavení se silným názvem zadaný.</span><span class="sxs-lookup"><span data-stu-id="c8738-216">You can specify *assembly* in the form *\*, strongname* to register all assemblies with the specified strong name.</span></span> <span data-ttu-id="c8738-217">Pro *strongname*, zadejte řetězec šestnáctkových číslic představující tokenizovaná formu veřejný klíč.</span><span class="sxs-lookup"><span data-stu-id="c8738-217">For *strongname*, specify the string of hexadecimal digits representing the tokenized form of the public key.</span></span> <span data-ttu-id="c8738-218">Najdete v článku **-t** a **-T** možnosti zobrazíte token veřejného klíče.</span><span class="sxs-lookup"><span data-stu-id="c8738-218">See the **-t** and **-T** options to display the public key token.</span></span> <span data-ttu-id="c8738-219">**Upozornění:** pomocí této možnosti pouze během vývoje.</span><span class="sxs-lookup"><span data-stu-id="c8738-219">**Caution:**  Use this option only during development.</span></span> <span data-ttu-id="c8738-220">Přidání sestavení na seznam pro přeskočení ověření vytvoří ohrožení zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="c8738-220">Adding an assembly to the skip verification list creates a security vulnerability.</span></span> <span data-ttu-id="c8738-221">Škodlivé sestavení by mohlo použít plně zadaný název sestavení (název sestavení, verze, jazyková verze a token veřejného klíče), které je přidáno do seznamu pro přeskočení ověření, k falšování identity.</span><span class="sxs-lookup"><span data-stu-id="c8738-221">A malicious assembly could use the fully specified assembly name (assembly name, version, culture, and public key token) of the assembly added to the skip verification list to fake its identity.</span></span> <span data-ttu-id="c8738-222">To by také umožnilo škodlivému sestavení přeskočit ověření.</span><span class="sxs-lookup"><span data-stu-id="c8738-222">This would allow the malicious assembly to also skip verification.</span></span>|  
|||  
|<span data-ttu-id="c8738-223">**-Vu***sestavení* </span><span class="sxs-lookup"><span data-stu-id="c8738-223">**-Vu**  *assembly*</span></span>|<span data-ttu-id="c8738-224">Zruší registraci *sestavení* pro přeskočení ověření.</span><span class="sxs-lookup"><span data-stu-id="c8738-224">Unregisters *assembly* for verification skipping.</span></span> <span data-ttu-id="c8738-225">Stejná pravidla pro sestavení názvy, které platí pro **- Vr** týkají **- Vu**.</span><span class="sxs-lookup"><span data-stu-id="c8738-225">The same rules for assembly naming that apply to **-Vr** apply to **-Vu**.</span></span>|  
|<span data-ttu-id="c8738-226">**-Vx**</span><span class="sxs-lookup"><span data-stu-id="c8738-226">**-Vx**</span></span>|<span data-ttu-id="c8738-227">Odstraní všechny záznamy o vynechání ověřování.</span><span class="sxs-lookup"><span data-stu-id="c8738-227">Removes all verification-skipping entries.</span></span>|  
|<span data-ttu-id="c8738-228">**-?**</span><span class="sxs-lookup"><span data-stu-id="c8738-228">**-?**</span></span>|<span data-ttu-id="c8738-229">Zobrazí syntaxi příkazu a možnosti nástroje.</span><span class="sxs-lookup"><span data-stu-id="c8738-229">Displays command syntax and options for the tool.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="c8738-230">Všechny možnosti nástroje Sn.exe rozlišují velká a malá písmena a musí být pro rozpoznání nástrojem zapsána přesně dle tabulky.</span><span class="sxs-lookup"><span data-stu-id="c8738-230">All Sn.exe options are case-sensitive and must be typed exactly as shown to be recognized by the tool.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c8738-231">Poznámky</span><span class="sxs-lookup"><span data-stu-id="c8738-231">Remarks</span></span>  
 <span data-ttu-id="c8738-232">**-R** a **– Rc** možnosti jsou užitečné s sestavení, která byla podepsána zpoždění.</span><span class="sxs-lookup"><span data-stu-id="c8738-232">The **-R** and **–Rc** options are useful with assemblies that have been delay-signed.</span></span> <span data-ttu-id="c8738-233">V tomto scénáři byl při kompilování nastaven pouze veřejný klíč a podepsání bylo provedeno později, až při znalosti soukromého klíče.</span><span class="sxs-lookup"><span data-stu-id="c8738-233">In this scenario, only the public key has been set at compile time and signing is performed later, when the private key is known.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c8738-234">Pro parametry (například –**Vr)** , zápis k chráněným prostředkům, například registr, SN.exe spustit jako správce.</span><span class="sxs-lookup"><span data-stu-id="c8738-234">For parameters (for example, –**Vr)** that write to protected resources such as the registry, run SN.exe as an administrator.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="c8738-235">Příklady</span><span class="sxs-lookup"><span data-stu-id="c8738-235">Examples</span></span>  
 <span data-ttu-id="c8738-236">Následující příkaz vytvoří dvojici klíčů nové, náhodné a uloží jej do `keyPair.snk`.</span><span class="sxs-lookup"><span data-stu-id="c8738-236">The following command creates a new, random key pair and stores it in `keyPair.snk`.</span></span>  
  
```  
sn -k keyPair.snk  
```  
  
 <span data-ttu-id="c8738-237">Následující příkaz uloží klíč v `keyPair.snk` v kontejneru `MyContainer` v silné název CSP.</span><span class="sxs-lookup"><span data-stu-id="c8738-237">The following command stores the key in `keyPair.snk` in the container `MyContainer` in the strong name CSP.</span></span>  
  
```  
sn -i keyPair.snk MyContainer  
```  
  
 <span data-ttu-id="c8738-238">Následující příkaz extrahuje veřejný klíč z `keyPair.snk` a uloží jej do `publicKey.snk`.</span><span class="sxs-lookup"><span data-stu-id="c8738-238">The following command extracts the public key from `keyPair.snk` and stores it in `publicKey.snk`.</span></span>  
  
```  
sn -p keyPair.snk publicKey.snk  
```  
  
 <span data-ttu-id="c8738-239">Následující příkaz zobrazí veřejný klíč a token veřejného klíče obsažené v `publicKey.snk`.</span><span class="sxs-lookup"><span data-stu-id="c8738-239">The following command displays the public key and the token for the public key contained in `publicKey.snk`.</span></span>  
  
```  
sn -tp publicKey.snk  
```  
  
 <span data-ttu-id="c8738-240">Následující příkaz ověřuje sestavení `MyAsm.dll`.</span><span class="sxs-lookup"><span data-stu-id="c8738-240">The following command verifies the assembly `MyAsm.dll`.</span></span>  
  
```  
sn -v MyAsm.dll  
```  
  
 <span data-ttu-id="c8738-241">Následující příkaz odstraní `MyContainer` z výchozího zprostředkovatele kryptografických služeb.</span><span class="sxs-lookup"><span data-stu-id="c8738-241">The following command deletes `MyContainer` from the default CSP.</span></span>  
  
```  
sn -d MyContainer  
```  
  
## <a name="see-also"></a><span data-ttu-id="c8738-242">Viz také</span><span class="sxs-lookup"><span data-stu-id="c8738-242">See Also</span></span>  
 [<span data-ttu-id="c8738-243">Nástroje</span><span class="sxs-lookup"><span data-stu-id="c8738-243">Tools</span></span>](../../../docs/framework/tools/index.md)  
 [<span data-ttu-id="c8738-244">Al.exe (Linker sestavení)</span><span class="sxs-lookup"><span data-stu-id="c8738-244">Al.exe (Assembly Linker)</span></span>](../../../docs/framework/tools/al-exe-assembly-linker.md)  
 [<span data-ttu-id="c8738-245">Sestavení se silným názvem</span><span class="sxs-lookup"><span data-stu-id="c8738-245">Strong-Named Assemblies</span></span>](../../../docs/framework/app-domains/strong-named-assemblies.md)  
 [<span data-ttu-id="c8738-246">Příkazové řádky</span><span class="sxs-lookup"><span data-stu-id="c8738-246">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
---
title: "Postupy: Konfigurace bezregistrační aktivace komponent využívajících rozhraní .NET Framework"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- components [.NET Framework], manifest
- application manifests [.NET Framework]
- manifests [.NET Framework]
- registration-free COM interop, configuring .NET-based components
- activation, registration-free
ms.assetid: 32f8b7c6-3f73-455d-8e13-9846895bd43b
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d373d6abc82e482a3b1df873295573f0e34eeda2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-configure-net-framework-based-com-components-for-registration-free-activation"></a><span data-ttu-id="2c703-102">Postupy: Konfigurace bezregistrační aktivace komponent využívajících rozhraní .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2c703-102">How to: Configure .NET Framework-Based COM Components for Registration-Free Activation</span></span>
<span data-ttu-id="2c703-103">Bezregistrační aktivace komponent využívajících rozhraní .NET Framework je pouze mírně složitěji, než je pro komponenty modelu COM.</span><span class="sxs-lookup"><span data-stu-id="2c703-103">Registration-free activation for .NET Framework-based components is only slightly more complicated than it is for COM components.</span></span> <span data-ttu-id="2c703-104">Instalace vyžaduje dva manifesty:</span><span class="sxs-lookup"><span data-stu-id="2c703-104">The setup requires two manifests:</span></span>  
  
-   <span data-ttu-id="2c703-105">Aplikace modelu COM musí mít manifest aplikace Win32 stylu k identifikaci spravované součásti.</span><span class="sxs-lookup"><span data-stu-id="2c703-105">COM applications must have a Win32-style application manifest to identify the managed component.</span></span>  
  
-   <span data-ttu-id="2c703-106">Součásti rozhraní .NET framework pro musí mít manifest součásti pro informace o aktivaci za běhu.</span><span class="sxs-lookup"><span data-stu-id="2c703-106">.NET Framework-based components must have a component manifest for activation information needed at run time.</span></span>  
  
 <span data-ttu-id="2c703-107">Toto téma popisuje, jak přidružit manifest aplikace aplikace. manifest součásti přidružit součást; a vložení do sestavení manifest součásti.</span><span class="sxs-lookup"><span data-stu-id="2c703-107">This topic describes how to associate an application manifest with an application; associate a component manifest with a component; and embed a component manifest in an assembly.</span></span>  
  
### <a name="to-create-an-application-manifest"></a><span data-ttu-id="2c703-108">Chcete-li vytvořit manifest aplikace</span><span class="sxs-lookup"><span data-stu-id="2c703-108">To create an application manifest</span></span>  
  
1.  <span data-ttu-id="2c703-109">Pomocí editoru XML, vytvořit (nebo upravit) manifest aplikace, které jsou ve vlastnictví aplikací modelu COM, která je spolupráce s jedním nebo více spravovaných součásti.</span><span class="sxs-lookup"><span data-stu-id="2c703-109">Using an XML editor, create (or modify) the application manifest owned by the COM application that is interoperating with one or more managed components.</span></span>  
  
2.  <span data-ttu-id="2c703-110">Na začátek souboru vložte následující standardní hlavičku:</span><span class="sxs-lookup"><span data-stu-id="2c703-110">Insert the following standard header at the beginning of the file:</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
    ```  
  
     <span data-ttu-id="2c703-111">Informace o manifestu elementy a jejich atributy najdete v tématu [manifesty aplikací](https://msdn.microsoft.com/library/windows/desktop/aa374191.aspx).</span><span class="sxs-lookup"><span data-stu-id="2c703-111">For information about manifest elements and their attributes, see [Application Manifests](https://msdn.microsoft.com/library/windows/desktop/aa374191.aspx).</span></span>  
  
3.  <span data-ttu-id="2c703-112">Identifikujte vlastník manifestu.</span><span class="sxs-lookup"><span data-stu-id="2c703-112">Identify the owner of the manifest.</span></span> <span data-ttu-id="2c703-113">V následujícím příkladu `myComApp` verze 1 vlastní soubor manifestu.</span><span class="sxs-lookup"><span data-stu-id="2c703-113">In the following example, `myComApp` version 1 owns the manifest file.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
      <assemblyIdentity type="win32"   
                        name="myOrganization.myDivision.myComApp"   
                        version="1.0.0.0"   
                        processorArchitecture="msil"   
      />  
    ```  
  
4.  <span data-ttu-id="2c703-114">Identifikujte závislá sestavení.</span><span class="sxs-lookup"><span data-stu-id="2c703-114">Identify dependent assemblies.</span></span> <span data-ttu-id="2c703-115">V následujícím příkladu `myComApp` závisí na `myManagedComp`.</span><span class="sxs-lookup"><span data-stu-id="2c703-115">In the following example, `myComApp` depends on `myManagedComp`.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
      <assemblyIdentity type="win32"   
                        name="myOrganization.myDivision.myComApp"   
                        version="1.0.0.0"   
                        processorArchitecture="x86"   
                        publicKeyToken="8275b28176rcbbef"  
      />  
      <dependency>  
        <dependentAssembly>  
          <assemblyIdentity type="win32"   
                        name="myOrganization.myDivision.myManagedComp"   
                        version="6.0.0.0"   
                        processorArchitecture="X86"   
                        publicKeyToken="8275b28176rcbbef"  
          />  
        </dependentAssembly>  
      </dependency>  
    </assembly>  
    ```  
  
5.  <span data-ttu-id="2c703-116">Uložte a název souboru manifestu.</span><span class="sxs-lookup"><span data-stu-id="2c703-116">Save and name the manifest file.</span></span> <span data-ttu-id="2c703-117">Název manifest aplikace je název spustitelného souboru sestavení a příponu manifest.</span><span class="sxs-lookup"><span data-stu-id="2c703-117">The name of an application manifest is the name of the assembly executable followed by the .manifest extension.</span></span> <span data-ttu-id="2c703-118">Například je název souboru manifestu aplikace pro myComApp.exe myComApp.exe.manifest.</span><span class="sxs-lookup"><span data-stu-id="2c703-118">For example, the application manifest file name for myComApp.exe is myComApp.exe.manifest.</span></span>  
  
 <span data-ttu-id="2c703-119">Manifest aplikace můžete nainstalovat do stejného adresáře jako aplikaci COM.</span><span class="sxs-lookup"><span data-stu-id="2c703-119">You can install an application manifest in the same directory as the COM application.</span></span> <span data-ttu-id="2c703-120">Alternativně můžete ho přidat jako prostředek do souboru .exe aplikace.</span><span class="sxs-lookup"><span data-stu-id="2c703-120">Alternatively, you can add it as a resource to the application's .exe file.</span></span> <span data-ttu-id="2c703-121">Další informace najdete další informace najdete v tématu [o souběžně sdílená sestavení](https://msdn.microsoft.com/library/windows/desktop/ff951640.aspx).</span><span class="sxs-lookup"><span data-stu-id="2c703-121">For additional information, For more information, see [About Side-by-Side Assemblies](https://msdn.microsoft.com/library/windows/desktop/ff951640.aspx).</span></span>  
  
#### <a name="to-create-a-component-manifest"></a><span data-ttu-id="2c703-122">Chcete-li vytvořit manifest součásti</span><span class="sxs-lookup"><span data-stu-id="2c703-122">To create a component manifest</span></span>  
  
1.  <span data-ttu-id="2c703-123">Pomocí editoru XML, vytvoření manifestu součástí popsat spravované sestavení.</span><span class="sxs-lookup"><span data-stu-id="2c703-123">Using an XML editor, create a component manifest to describe the managed assembly.</span></span>  
  
2.  <span data-ttu-id="2c703-124">Na začátek souboru vložte následující standardní hlavičku:</span><span class="sxs-lookup"><span data-stu-id="2c703-124">Insert the following standard header at the beginning of the file:</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
    ```  
  
3.  <span data-ttu-id="2c703-125">Určete vlastníka souboru.</span><span class="sxs-lookup"><span data-stu-id="2c703-125">Identify the owner of the file.</span></span> <span data-ttu-id="2c703-126">`<assemblyIdentity>` Element `<dependentAssembly>` element v souboru manifestu aplikace musí odpovídat názvu v manifestu součásti.</span><span class="sxs-lookup"><span data-stu-id="2c703-126">The `<assemblyIdentity>` element of the `<dependentAssembly>` element in application manifest file must match the one in the component manifest.</span></span> <span data-ttu-id="2c703-127">V následujícím příkladu `myManagedComp` verze 1.2.3.4 vlastní soubor manifestu.</span><span class="sxs-lookup"><span data-stu-id="2c703-127">In the following example, `myManagedComp` version 1.2.3.4 owns the manifest file.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
           <assemblyIdentity  
                        name="myOrganization.myDivision.myManagedComp"  
                        version="1.2.3.4"  
                        publicKeyToken="8275b28176rcbbef"  
                        processorArchitecture="msil"  
           />  
    ```  
  
4.  <span data-ttu-id="2c703-128">Identifikujte každá třída v sestavení.</span><span class="sxs-lookup"><span data-stu-id="2c703-128">Identify each class in the assembly.</span></span> <span data-ttu-id="2c703-129">Použití `<clrClass>` element k jednoznačné identifikaci každé třídě spravované sestavení.</span><span class="sxs-lookup"><span data-stu-id="2c703-129">Use the `<clrClass>` element to uniquely identify each class in the managed assembly.</span></span> <span data-ttu-id="2c703-130">Element, který je dílčí prvek z `<assembly>` elementu, má atributy popsané v následující tabulce.</span><span class="sxs-lookup"><span data-stu-id="2c703-130">The element, which is a subelement of the `<assembly>` element, has the attributes described in the following table.</span></span>  
  
    |<span data-ttu-id="2c703-131">Atribut</span><span class="sxs-lookup"><span data-stu-id="2c703-131">Attribute</span></span>|<span data-ttu-id="2c703-132">Popis</span><span class="sxs-lookup"><span data-stu-id="2c703-132">Description</span></span>|<span data-ttu-id="2c703-133">Požadováno</span><span class="sxs-lookup"><span data-stu-id="2c703-133">Required</span></span>|  
    |---------------|-----------------|--------------|  
    |`clsid`|<span data-ttu-id="2c703-134">Identifikátor, který určuje třídu, která chcete aktivovat.</span><span class="sxs-lookup"><span data-stu-id="2c703-134">The identifier that specifies the class to be activated.</span></span>|<span data-ttu-id="2c703-135">Ano</span><span class="sxs-lookup"><span data-stu-id="2c703-135">Yes</span></span>|  
    |`description`|<span data-ttu-id="2c703-136">Řetězec, který informuje uživatele o komponentu.</span><span class="sxs-lookup"><span data-stu-id="2c703-136">A string that informs the user about the component.</span></span> <span data-ttu-id="2c703-137">Výchozí je prázdný řetězec.</span><span class="sxs-lookup"><span data-stu-id="2c703-137">An empty string is the default.</span></span>|<span data-ttu-id="2c703-138">Ne</span><span class="sxs-lookup"><span data-stu-id="2c703-138">No</span></span>|  
    |`name`|<span data-ttu-id="2c703-139">Řetězec, který představuje spravované třídy.</span><span class="sxs-lookup"><span data-stu-id="2c703-139">A string that represents the managed class.</span></span>|<span data-ttu-id="2c703-140">Ano</span><span class="sxs-lookup"><span data-stu-id="2c703-140">Yes</span></span>|  
    |`progid`|<span data-ttu-id="2c703-141">Identifikátor, který má být použit pro aktivaci pozdní vazbu.</span><span class="sxs-lookup"><span data-stu-id="2c703-141">The identifier to be used for late-bound activation.</span></span>|<span data-ttu-id="2c703-142">Ne</span><span class="sxs-lookup"><span data-stu-id="2c703-142">No</span></span>|  
    |`threadingModel`|<span data-ttu-id="2c703-143">Model COM vláken.</span><span class="sxs-lookup"><span data-stu-id="2c703-143">The COM threading model.</span></span> <span data-ttu-id="2c703-144">"I" je výchozí hodnota.</span><span class="sxs-lookup"><span data-stu-id="2c703-144">"Both" is the default value.</span></span>|<span data-ttu-id="2c703-145">Ne</span><span class="sxs-lookup"><span data-stu-id="2c703-145">No</span></span>|  
    |`runtimeVersion`|<span data-ttu-id="2c703-146">Určuje společné jazykové verzi modulu runtime (CLR) používat.</span><span class="sxs-lookup"><span data-stu-id="2c703-146">Specifies the common language runtime (CLR) version to use.</span></span> <span data-ttu-id="2c703-147">Pokud nezadáte tento atribut a dosud není načtený modulu CLR, součást je načtena s nainstalovanou CLR před CLR verze 4.</span><span class="sxs-lookup"><span data-stu-id="2c703-147">If you do not specify this attribute, and the CLR is not already loaded, the component is loaded with the latest installed CLR prior to CLR version 4.</span></span> <span data-ttu-id="2c703-148">Pokud zadáte v1.0.3705, v1.1.4322 nebo v2.0.50727, verze automaticky posunete na nejnovější nainstalované verze CLR před CLR verze 4 (obvykle v2.0.50727).</span><span class="sxs-lookup"><span data-stu-id="2c703-148">If you specify v1.0.3705, v1.1.4322, or v2.0.50727, the version automatically rolls forward to the latest installed CLR version prior to CLR version 4 (usually v2.0.50727).</span></span> <span data-ttu-id="2c703-149">Pokud už je načtený jinou verzi modulu CLR a zadaná verze mohou být načteny vedle sebe v procesu, je zadaná verze načten. načíst CLR, jinak se používá.</span><span class="sxs-lookup"><span data-stu-id="2c703-149">If another version of the CLR is already loaded and the specified version can be loaded side-by-side in-process, the specified version is loaded; otherwise, the loaded CLR is used.</span></span> <span data-ttu-id="2c703-150">To může způsobit selhání načtení.</span><span class="sxs-lookup"><span data-stu-id="2c703-150">This might cause a load failure.</span></span>|<span data-ttu-id="2c703-151">Ne</span><span class="sxs-lookup"><span data-stu-id="2c703-151">No</span></span>|  
    |`tlbid`|<span data-ttu-id="2c703-152">Identifikátor knihovny typů, který obsahuje informace o typu o třídě.</span><span class="sxs-lookup"><span data-stu-id="2c703-152">The identifier of the type library that contains type information about the class.</span></span>|<span data-ttu-id="2c703-153">Ne</span><span class="sxs-lookup"><span data-stu-id="2c703-153">No</span></span>|  
  
     <span data-ttu-id="2c703-154">Všechny značky atribut rozlišují velká a malá písmena.</span><span class="sxs-lookup"><span data-stu-id="2c703-154">All attribute tags are case-sensitive.</span></span> <span data-ttu-id="2c703-155">Můžete získat CLSID, ProgID, dělení na vlákna modely a verze modulu runtime zobrazením knihovně exportovaný typ pro toto sestavení s ObjectViewer OLE/COM (Oleview.exe).</span><span class="sxs-lookup"><span data-stu-id="2c703-155">You can obtain CLSIDs, ProgIDs, threading models, and the runtime version by viewing the exported type library for the assembly with the OLE/COM ObjectViewer (Oleview.exe).</span></span>  
  
     <span data-ttu-id="2c703-156">Následující součást manifest identifikuje dvě třídy `testClass1` a `testClass2`.</span><span class="sxs-lookup"><span data-stu-id="2c703-156">The following component manifest identifies two classes, `testClass1` and `testClass2`.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
           <assemblyIdentity  
                        name="myOrganization.myDivision.myManagedComp"  
                        version="1.2.3.4" />  
                        publicKeyToken="8275b28176rcbbef"  
           />  
           <clrClass  
                        clsid="{65722BE6-3449-4628-ABD3-74B6864F9739}"  
                        progid="myManagedComp.testClass1"  
                        threadingModel="Both"  
                        name="myManagedComp.testClass1"  
                        runtimeVersion="v1.0.3705">  
           </clrClass>  
           <clrClass  
                        clsid="{367221D6-3559-3328-ABD3-45B6825F9732}"  
                        progid="myManagedComp.testClass2"  
                        threadingModel="Both"  
                        name="myManagedComp.testClass2"  
                        runtimeVersion="v1.0.3705">  
           </clrClass>  
           <file name="MyManagedComp.dll">  
           </file>  
    </assembly>  
    ```  
  
5.  <span data-ttu-id="2c703-157">Uložte a název souboru manifestu.</span><span class="sxs-lookup"><span data-stu-id="2c703-157">Save and name the manifest file.</span></span> <span data-ttu-id="2c703-158">Název manifestu součástí je název a příponu manifest sestavení knihovny.</span><span class="sxs-lookup"><span data-stu-id="2c703-158">The name of a component manifest is the name of the assembly library followed by the .manifest extension.</span></span> <span data-ttu-id="2c703-159">Například myManagedComp.dll je myManagedComp.manifest.</span><span class="sxs-lookup"><span data-stu-id="2c703-159">For example, the myManagedComp.dll is myManagedComp.manifest.</span></span>  
  
 <span data-ttu-id="2c703-160">Manifest součásti musíte vložit jako prostředek v sestavení.</span><span class="sxs-lookup"><span data-stu-id="2c703-160">You must embed the component manifest as a resource in the assembly.</span></span>  
  
#### <a name="to-embed-a-component-manifest-in-a-managed-assembly"></a><span data-ttu-id="2c703-161">Manifest součásti vložit do spravované sestavení.</span><span class="sxs-lookup"><span data-stu-id="2c703-161">To embed a component manifest in a managed assembly</span></span>  
  
1.  <span data-ttu-id="2c703-162">Vytvořte prostředek skript, který obsahuje následující příkaz:</span><span class="sxs-lookup"><span data-stu-id="2c703-162">Create a resource script that contains the following statement:</span></span>  
  
     `RT_MANIFEST 1 myManagedComp.manifest`  
  
     <span data-ttu-id="2c703-163">V tomto prohlášení `myManagedComp.manifest` je název manifestu součástí jeho vkládání.</span><span class="sxs-lookup"><span data-stu-id="2c703-163">In this statement, `myManagedComp.manifest` is the name of the component manifest being embedded.</span></span> <span data-ttu-id="2c703-164">V tomto příkladu je název souboru skriptu `myresource.rc`.</span><span class="sxs-lookup"><span data-stu-id="2c703-164">For this example, the script file name is `myresource.rc`.</span></span>  
  
2.  <span data-ttu-id="2c703-165">Zkompilujte skriptu pomocí kompilátor prostředků systému Microsoft Windows (Rc.exe).</span><span class="sxs-lookup"><span data-stu-id="2c703-165">Compile the script using the Microsoft Windows Resource Compiler (Rc.exe).</span></span> <span data-ttu-id="2c703-166">V příkazovém řádku zadejte následující příkaz:</span><span class="sxs-lookup"><span data-stu-id="2c703-166">At the command prompt, type the following command:</span></span>  
  
     `rc myresource.rc`  
  
     <span data-ttu-id="2c703-167">Vytvoří RC.exe `myresource.res` souboru prostředků.</span><span class="sxs-lookup"><span data-stu-id="2c703-167">Rc.exe produces the `myresource.res` resource file.</span></span>  
  
3.  <span data-ttu-id="2c703-168">Kompilace sestavení zdrojový soubor znovu a určete soubor prostředků pomocí **/win32res** možnost:</span><span class="sxs-lookup"><span data-stu-id="2c703-168">Compile the assembly's source file again and specify the resource file by using the **/win32res** option:</span></span>  
  
    ```  
    /win32res:myresource.res  
    ```  
  
     <span data-ttu-id="2c703-169">Znovu `myresource.res` je název souboru prostředků obsahující vložený prostředek.</span><span class="sxs-lookup"><span data-stu-id="2c703-169">Again, `myresource.res` is the name of the resource file containing embedded resource.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c703-170">Viz také</span><span class="sxs-lookup"><span data-stu-id="2c703-170">See Also</span></span>  
 [<span data-ttu-id="2c703-171">Zprostředkovatel komunikace s objekty COM bez registrace</span><span class="sxs-lookup"><span data-stu-id="2c703-171">Registration-Free COM Interop</span></span>](../../../docs/framework/interop/registration-free-com-interop.md)  
 [<span data-ttu-id="2c703-172">Požadavky pro zprostředkovatel komunikace s objekty COM bez registrace</span><span class="sxs-lookup"><span data-stu-id="2c703-172">Requirements for Registration-Free COM Interop</span></span>](http://msdn.microsoft.com/en-us/0c43bc57-eecf-4e6c-8114-490141cce4da)  
 [<span data-ttu-id="2c703-173">Konfigurace komponenty modelu COM bez registrace aktivace</span><span class="sxs-lookup"><span data-stu-id="2c703-173">Configuring COM Components for Registration-Free Activation</span></span>](http://msdn.microsoft.com/en-us/bfe9b02f-d964-4784-960e-a1f94692fbfe)  
 [<span data-ttu-id="2c703-174">Bezregistrační aktivace. Na základě NET komponenty: Návod</span><span class="sxs-lookup"><span data-stu-id="2c703-174">Registration-Free Activation of .NET-Based Components: A Walkthrough</span></span>](http://go.microsoft.com/fwlink/?LinkId=158812)
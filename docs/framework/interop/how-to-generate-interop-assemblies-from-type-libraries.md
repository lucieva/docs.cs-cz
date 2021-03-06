---
title: 'Postupy: Generování sestavení vzájemné spolupráce z knihoven typů'
ms.date: 03/30/2017
helpviewer_keywords:
- importing type library
- interop assemblies, generating
- Type Library Importer
- type libraries
- COM interop, importing type library
ms.assetid: 4afd40c3-68f2-41c5-8ec1-4951bc148b9c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 62d9213e58aaabd0b4001d5c6a7fd6fd375eba2e
ms.sourcegitcommit: 59b51cd7c95c75be85bd6ef715e9ef8c85720bac
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/06/2018
ms.locfileid: "37874855"
---
# <a name="how-to-generate-interop-assemblies-from-type-libraries"></a>Postupy: Generování sestavení vzájemné spolupráce z knihoven typů
[Importér knihovny typů (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md) je nástroj příkazového řádku, který převádí třídy typu coclass a rozhraní, které jsou obsaženy v knihovně typů modelu COM na metadata. Tento nástroj automaticky vytvoří definiční sestavení a oboru názvů pro informace o typu. Po metadata třídy jsou k dispozici, spravovaných klientů můžete vytvořit instance daného typu modelu COM a volat jeho metody, stejně jako by šlo instanci .NET. Tlbimp.exe najednou převede celé knihovny typů na metadata a nemůže generovat informace o typu pro podmnožinu typů definovaných v knihovně typů.  
  
### <a name="to-generate-an-interop-assembly-from-a-type-library"></a>Ke generování sestavení vzájemné spolupráce z knihovny typů  
  
1.  Použijte následující příkaz:  
  
     **Tlbimp** \< *soubor knihovny typů*>  
  
     Přidávání **/out:** definiční sestavení s upravený název, jako je například LOANLib.dll vytváří přepínač. Změna názvu sestavení vzájemné spolupráce pomáhá odlišil od původní knihovnu DLL modelu COM a zabránit problémům, které mohou nastat z s duplicitními názvy.  
  
## <a name="example"></a>Příklad  
 Následující příkaz vytvoří sestavení Loanlib.dll v `Loanlib` oboru názvů.  
  
```  
tlbimp Loanlib.tlb  
```  
  
 Následující příkaz vygeneruje sestavení vzájemné spolupráce s upravený název (LOANLib.dll).  
  
```  
tlbimp LoanLib.tlb /out: LOANLib.dll  
```  
  
## <a name="see-also"></a>Viz také  
 [Import knihovny typů ve formě sestavení](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md)  
 [Vystavení komponent COM pro rozhraní .NET Framework](../../../docs/framework/interop/exposing-com-components.md)

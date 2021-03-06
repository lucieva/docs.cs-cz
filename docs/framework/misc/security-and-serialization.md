---
title: Zabezpečení a serializace
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- code security, serialization
- serialization, security
- secure coding, serialization
- security [.NET Framework], serialization
ms.assetid: b921bc94-bd3a-4c91-9ede-2c8d4f78ea9a
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a30e80b1b4a412405787c0c14ad58995a2d7fffc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/04/2018
ms.locfileid: "33394245"
---
# <a name="security-and-serialization"></a>Zabezpečení a serializace
Protože serializace můžete povolit jiný kód, zobrazit nebo upravit data instance objektů, které by jinak nedostupná, speciální oprávnění jsou nutná kódu provádění serializace: <xref:System.Security.Permissions.SecurityPermission> s <xref:System.Security.Permissions.SecurityPermissionFlag.SerializationFormatter> příznak. Podle výchozích zásad Toto oprávnění nemá přístup k Internetu stáhnout nebo intranetu kód; Toto oprávnění je uděleno pouze kód v místním počítači.  
  
 Za normálních okolností se serializují všechna pole instance objektu, což znamená, že data jsou reprezentována v serializovaných datech pro instanci. Je možné pro kód, který dokáže interpretovat formát, který se zjistit, co jsou hodnoty dat, nezávisle na přístupnosti člena. Podobně deserializace extrahuje data ze serializované reprezentace a nastaví stav objektu přímo, znovu bez ohledu na pravidla přístupu.  
  
 Libovolný objekt, který může obsahovat data citlivým z hlediska zabezpečení by měl být neserializovatelný, pokud je to možné. Pokud musí být serializovatelný, zkuste provést konkrétní pole, které obsahují citlivá data neserializovatelné. Pokud tuto změnu nelze provést, mějte na paměti, že tato data budou vystavena kód, který má oprávnění k serializaci a ujistěte se, že žádný škodlivý kód můžete získat toto oprávnění.  
  
 <xref:System.Runtime.Serialization.ISerializable> Rozhraní je určena pro použití pouze infrastrukturou serializace. Ale pokud nechráněné, je potenciálně uvolnit citlivé informace. Pokud jste zadali vlastní serializace implementací **ISerializable**, ujistěte se, postupujte podle následujících opatření:  
  
-   <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> Metoda by měla být explicitně zabezpečena požadavkem **SecurityPermission** s **SerializationFormatter** oprávnění zadaný nebo nástrojem a ověřte, zda žádná velká a malá písmena informace o vydání pomocí výstupu metody. Příklad:  
  
    ```vb  
    Public Overrides<SecurityPermissionAttribute(SecurityAction.Demand, SerializationFormatter := True)>  _  
    Sub GetObjectData(info As SerializationInfo, context As StreamingContext)  
    End Sub  
    ```  
  
    ```csharp  
    [SecurityPermissionAttribute(SecurityAction.Demand,SerializationFormatter   
    =true)]  
    public override void GetObjectData(SerializationInfo info,   
    StreamingContext context)  
    {  
    }  
    ```  
  
-   Zvláštní konstruktor pro serializaci by také provést důkladné ověřování vstupu a musí být chráněný nebo privátní zajistit ochranu proti zneužití škodlivý kód. Měla vynutit, stejné kontroly zabezpečení a oprávnění potřebná k získání instance této třídy jiným způsobem, jako je například explicitně vytvořením třídy nebo nepřímo přes určitého druhu objektu pro vytváření.  
  
## <a name="see-also"></a>Viz také  
 [Pokyny pro zabezpečené kódování](../../../docs/standard/security/secure-coding-guidelines.md)

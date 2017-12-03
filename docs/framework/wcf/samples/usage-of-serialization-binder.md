---
title: "Použití vazače serializace"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ab46c087-200c-45bf-9c95-5a6cda6e8b98
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 77f5c2914051c4310102a57b7181333bab6811b6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="usage-of-serialization-binder"></a><span data-ttu-id="2dbd7-102">Použití vazače serializace</span><span class="sxs-lookup"><span data-stu-id="2dbd7-102">Usage of Serialization Binder</span></span>
<span data-ttu-id="2dbd7-103">Tento příklad ukazuje způsob použití <xref:System.Runtime.Serialization.SerializationBinder> změna verze obecného typu, pokud je serializováno.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-103">This sample shows how to use the <xref:System.Runtime.Serialization.SerializationBinder> to change the version of a generic type when it is serialized.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="2dbd7-104">Demonstruje</span><span class="sxs-lookup"><span data-stu-id="2dbd7-104">Demonstrates</span></span>  
 <span data-ttu-id="2dbd7-105"><xref:System.Runtime.Serialization.SerializationBinder>, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter></span><span class="sxs-lookup"><span data-stu-id="2dbd7-105"><xref:System.Runtime.Serialization.SerializationBinder>, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter></span></span>  
  
## <a name="discussion"></a><span data-ttu-id="2dbd7-106">Diskusní</span><span class="sxs-lookup"><span data-stu-id="2dbd7-106">Discussion</span></span>  
 <span data-ttu-id="2dbd7-107">Tento příklad ukazuje, jak dvě entity, které jsou cílené na různých verzích [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] může komunikovat pomocí binární formátovacího modulu a vazače serializace.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-107">This sample shows how two entities that are targeting different versions of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] can communicate using the binary formatter and the serialization binder.</span></span>  
  
 <span data-ttu-id="2dbd7-108">Vývoj této ukázky bylo provedeno pomocí .NET Remoting.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-108">The development of this sample has been done using .NET Remoting.</span></span> <span data-ttu-id="2dbd7-109">Ukázkový soubor obsahuje cílení na serverový [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)], který implementuje kontrakt s obecné typy a dvou různých klientů, jeden cílení na [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)] a jiné cílení [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2dbd7-109">The sample consists of a server targeting [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)], which implements a contract with generic types, and two different clients, one targeting [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)] and another targeting [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)].</span></span>  
  
 <span data-ttu-id="2dbd7-110">Připojí serveru <xref:System.Runtime.Serialization.SerializationBinder> na binární formátování, které bude moci změnit verzi typy odpovídajícím způsobem v serializaci, tak i klientů může deserializovat tyto typy správně.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-110">The server attaches a <xref:System.Runtime.Serialization.SerializationBinder> to the binary formatter to be able to change the version of the types accordingly on serialization, so both clients can deserialize those types properly.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="2dbd7-111">Pokud chcete nastavit, sestavit a spustit ukázku</span><span class="sxs-lookup"><span data-stu-id="2dbd7-111">To set up, build and run the sample</span></span>  
  
1.  <span data-ttu-id="2dbd7-112">Spuštění klienta, klikněte pravým tlačítkem na řešení, SBGenericsVTS (6 projektů) a potom vyberte **vlastnosti**.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-112">To execute the client, right-click the solution, SBGenericsVTS (6 projects) and then select **Properties**.</span></span>  
  
2.  <span data-ttu-id="2dbd7-113">V **společných vlastností**, vyberte **spouštěný projekt**, pak vyberte **více projektů po spuštění**.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-113">In **Common Properties**, select **Startup Project**, then select **Multiple Startup Projects**.</span></span>  
  
3.  <span data-ttu-id="2dbd7-114">Vyberte **Server** první, pak **Client20** a potom **Client40**.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-114">Select **Server** first, then **Client20** and then **Client40**.</span></span> <span data-ttu-id="2dbd7-115">Vyberte **spustit** akce do těchto tří projektů a ponechejte zbývající nastavena na **žádné**.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-115">Select the **Start** action to these three projects and leave the rest set to **None**.</span></span>  
  
4.  <span data-ttu-id="2dbd7-116">Klikněte na tlačítko **OK** a potom stiskněte klávesu F5 a spusťte vzorku.</span><span class="sxs-lookup"><span data-stu-id="2dbd7-116">Click **OK** and then press F5 to run the sample.</span></span>
---
title: Oboru Convoy transakce
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 37141708-a29f-4b6a-81fe-f8a11f825061
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 085c52d94db5af12a022fa353a80d69534bfe219
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/28/2017
---
# <a name="transaction-convoy-scope"></a><span data-ttu-id="b7398-102">Oboru Convoy transakce</span><span class="sxs-lookup"><span data-stu-id="b7398-102">Transaction Convoy Scope</span></span>
<span data-ttu-id="b7398-103">Tento příklad ukazuje, jak vytvořit paralelní Convoy zasílání zpráv vzor aktivity ve spojení s <xref:System.ServiceModel.Activities.TransactedReceiveScope> pro modelování protokol, kde několik operací, může dojít v libovolném pořadí všechny ve stejné transakci.</span><span class="sxs-lookup"><span data-stu-id="b7398-103">This sample demonstrates how to create a Parallel Convoy messaging activity pattern in conjunction with a <xref:System.ServiceModel.Activities.TransactedReceiveScope> to model a protocol where a number of operations can happen in any order all under the same transaction.</span></span> <span data-ttu-id="b7398-104">Tento příklad také ukazuje, jak <xref:System.ServiceModel.Activities.TransactedReceiveScope> automaticky vytvoří novou transakci, pokud jeden není předávány na server, tak klient neprovede použití jakékoli transakce.</span><span class="sxs-lookup"><span data-stu-id="b7398-104">This sample also demonstrates how a <xref:System.ServiceModel.Activities.TransactedReceiveScope> automatically creates a new transaction when one is not flowed to the server, so the client does not make use of any transactions.</span></span>  
  
 <span data-ttu-id="b7398-105">Ukázkový soubor obsahuje dva projekty pracovního postupu, které představují klientem a serverem.</span><span class="sxs-lookup"><span data-stu-id="b7398-105">The sample consists of two workflow projects that represent the client and server.</span></span> <span data-ttu-id="b7398-106">Projektu klienta se spustí pracovní postup, který začíná odesláním zprávy k navázání připojení serveru pracovního postupu, která inicializuje korelaci a spustí transakční obor pro zbytek aktivity zasílání zpráv.</span><span class="sxs-lookup"><span data-stu-id="b7398-106">The client project runs a workflow that begins by sending a message to bootstrap the server workflow, which initializes a correlation and starts a transactional scope for the remainder of the messaging activities.</span></span> <span data-ttu-id="b7398-107">Klient <xref:System.Activities.Statements.Sequence> aktivity obsahuje počáteční <xref:System.ServiceModel.Activities.Send> a <xref:System.ServiceModel.Activities.ReceiveReply> pár a potom <xref:System.Activities.Statements.Parallel> aktivitu tři větve.</span><span class="sxs-lookup"><span data-stu-id="b7398-107">The client <xref:System.Activities.Statements.Sequence> activity contains an initial <xref:System.ServiceModel.Activities.Send> and <xref:System.ServiceModel.Activities.ReceiveReply> pair and then a <xref:System.Activities.Statements.Parallel> activity with three branches.</span></span> <span data-ttu-id="b7398-108">U každé větve odešle zprávu jednosměrný k serveru.</span><span class="sxs-lookup"><span data-stu-id="b7398-108">Each branch sends a one-way message to the server.</span></span> <span data-ttu-id="b7398-109"><xref:System.Activities.Statements.Parallel.CompletionCondition%2A> Vlastnost <xref:System.Activities.Statements.Parallel> aktivity je nastavený na `false` tak, aby všechny tři větve dokončit.</span><span class="sxs-lookup"><span data-stu-id="b7398-109">The <xref:System.Activities.Statements.Parallel.CompletionCondition%2A> property of the <xref:System.Activities.Statements.Parallel> activity is set to `false` so that all three branches complete.</span></span>  
  
 <span data-ttu-id="b7398-110">Pracovní postup serveru je podobná klienta pracovního postupu, s výjimkou zasílání zpráv aktivity jsou orientované směrem komunikace na straně serveru a jsou obsaženy v rámci <xref:System.ServiceModel.Activities.TransactedReceiveScope> aktivity tak, aby všechny pracovat done provede ve stejné transakci.</span><span class="sxs-lookup"><span data-stu-id="b7398-110">The server workflow is similar to the client workflow except the messaging activities are oriented towards the server side of the communication and they are contained within a <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity so that all work done executes under the same transaction.</span></span> <span data-ttu-id="b7398-111">První zpráva odeslaná na server, transakce se vytvoří a přišla vedlejším rozsahu <xref:System.ServiceModel.Activities.TransactedReceiveScope> body, aby všechny aktivity v rámci tohoto rozsahu přístup transakce.</span><span class="sxs-lookup"><span data-stu-id="b7398-111">When the first message is received on the server, a transaction is created and is made ambient for the scope of the <xref:System.ServiceModel.Activities.TransactedReceiveScope> body so that any activity within this scope can access the transaction.</span></span> <span data-ttu-id="b7398-112">Potom všechny obdrží provést paralelně.</span><span class="sxs-lookup"><span data-stu-id="b7398-112">After this, all receives execute in parallel.</span></span> <span data-ttu-id="b7398-113">Všechny obdrží musí provést pouze jednou, jak je popsáno podmínka dokončení na paralelní aktivity.</span><span class="sxs-lookup"><span data-stu-id="b7398-113">All receives must execute exactly once as described by the completion condition on the parallel activity.</span></span> <span data-ttu-id="b7398-114">Bod implicitní trvalost existuje na konci <xref:System.ServiceModel.Activities.TransactedReceiveScope> textu a operace trvalost je také provést v rámci stejné transakci.</span><span class="sxs-lookup"><span data-stu-id="b7398-114">An implicit persistence point exists at the end of the <xref:System.ServiceModel.Activities.TransactedReceiveScope> body and the persistence operation is also executed under the same transaction.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="b7398-115">Pro fungování této ukázky</span><span class="sxs-lookup"><span data-stu-id="b7398-115">To use this sample</span></span>  
  
1.  <span data-ttu-id="b7398-116">Pomocí [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], otevřete soubor řešení ParallelConvoySample.sln.</span><span class="sxs-lookup"><span data-stu-id="b7398-116">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the ParallelConvoySample.sln solution file.</span></span>  
  
2.  <span data-ttu-id="b7398-117">Sestavte řešení, stiskněte CTRL + SHIFT + B.</span><span class="sxs-lookup"><span data-stu-id="b7398-117">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="b7398-118">Zajistěte, aby že oba projekty jsou nastaveny na spustit.</span><span class="sxs-lookup"><span data-stu-id="b7398-118">Ensure both projects are set to start.</span></span>  
  
    1.  <span data-ttu-id="b7398-119">V **Průzkumníku řešení**, klikněte pravým tlačítkem na řešení a vyberte **nastavit projekty po spuštění**.</span><span class="sxs-lookup"><span data-stu-id="b7398-119">In **Solution Explorer**, right-click the solution and select **Set Startup Projects**.</span></span>  
  
    2.  <span data-ttu-id="b7398-120">Vyberte **více projektů po spuštění** a zkontrolujte akci pro oba projekty je nastavená na **spustit**.</span><span class="sxs-lookup"><span data-stu-id="b7398-120">Select **Multiple Startup Projects** and ensure the action for both projects is set to **Start**.</span></span>  
  
4.  <span data-ttu-id="b7398-121">Chcete-li spustit řešení, stiskněte CTRL + F5.</span><span class="sxs-lookup"><span data-stu-id="b7398-121">To run the solution, press CTRL+F5.</span></span>  
  
     <span data-ttu-id="b7398-122">Server výtisků `Server is running`, což naznačuje server je připraven.</span><span class="sxs-lookup"><span data-stu-id="b7398-122">The server prints `Server is running`, which indicates the server is ready.</span></span>  
  
     <span data-ttu-id="b7398-123">Stisknutím libovolné klávesy v okně konzoly klienta ke spuštění ukázky.</span><span class="sxs-lookup"><span data-stu-id="b7398-123">Press any key in the client console window to start the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b7398-124">Ukázky může být již nainstalována na váš počítač.</span><span class="sxs-lookup"><span data-stu-id="b7398-124">The samples may already be installed on your machine.</span></span> <span data-ttu-id="b7398-125">Před pokračováním zkontrolovat na následující adresář (výchozí).</span><span class="sxs-lookup"><span data-stu-id="b7398-125">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="b7398-126">Pokud tento adresář neexistuje, přejděte na [Windows Communication Foundation (WCF) a ukázky Windows Workflow Foundation (WF) pro rozhraní .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) ke stažení všechny [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] a [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ukázky.</span><span class="sxs-lookup"><span data-stu-id="b7398-126">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b7398-127">Tato ukázka se nachází v následujícím adresáři.</span><span class="sxs-lookup"><span data-stu-id="b7398-127">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Transactions\TransactedConvoyScope`
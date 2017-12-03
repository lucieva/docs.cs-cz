---
title: "Implementace explicitní transakce pomocí CommittableTransaction"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 29efe5e5-897b-46c2-a35f-e599a273acc8
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cc6f039ffbdeaef70e3bc4eb71aa5046105f4ee9
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/02/2017
---
# <a name="implementing-an-explicit-transaction-using-committabletransaction"></a><span data-ttu-id="7565e-102">Implementace explicitní transakce pomocí CommittableTransaction</span><span class="sxs-lookup"><span data-stu-id="7565e-102">Implementing an Explicit Transaction using CommittableTransaction</span></span>
<span data-ttu-id="7565e-103"><xref:System.Transactions.CommittableTransaction> Třída poskytuje explicitní způsob pro použití transakcí, na rozdíl od použití aplikacemi <xref:System.Transactions.TransactionScope> třídy implicitně.</span><span class="sxs-lookup"><span data-stu-id="7565e-103">The <xref:System.Transactions.CommittableTransaction> class provides an explicit way for applications to use a transaction, as opposed to using the <xref:System.Transactions.TransactionScope> class implicitly.</span></span> <span data-ttu-id="7565e-104">Je užitečné pro aplikace, které chcete použít stejnou transakci napříč několika volání funkce nebo více vláken volání.</span><span class="sxs-lookup"><span data-stu-id="7565e-104">It is useful for applications that want to use the same transaction across multiple function calls or multiple thread calls.</span></span> <span data-ttu-id="7565e-105">Na rozdíl od <xref:System.Transactions.TransactionScope> třídy pro zápis do aplikace potřebuje konkrétně volat <xref:System.Transactions.CommittableTransaction.Commit%2A> a <xref:System.Transactions.Transaction.Rollback%2A> metody za účelem potvrzení nebo přerušení transakce.</span><span class="sxs-lookup"><span data-stu-id="7565e-105">Unlike the <xref:System.Transactions.TransactionScope> class, the application writer needs to specifically call the <xref:System.Transactions.CommittableTransaction.Commit%2A> and <xref:System.Transactions.Transaction.Rollback%2A> methods in order to commit or abort the transaction.</span></span>  
  
## <a name="overview-of-the-committabletransaction-class"></a><span data-ttu-id="7565e-106">Přehled třídy CommittableTransaction</span><span class="sxs-lookup"><span data-stu-id="7565e-106">Overview of the CommittableTransaction class</span></span>  
 <span data-ttu-id="7565e-107"><xref:System.Transactions.CommittableTransaction> Třída odvozena z <xref:System.Transactions.Transaction> třídy, proto poskytuje všechny funkce ten.</span><span class="sxs-lookup"><span data-stu-id="7565e-107">The <xref:System.Transactions.CommittableTransaction> class derives from the <xref:System.Transactions.Transaction> class, therefore providing all the functionality of the latter.</span></span> <span data-ttu-id="7565e-108">Je obzvláště užitečná <xref:System.Transactions.Transaction.Rollback%2A> metodu na <xref:System.Transactions.Transaction> třídu, která lze také použít k vrácení zpět <xref:System.Transactions.CommittableTransaction> objektu.</span><span class="sxs-lookup"><span data-stu-id="7565e-108">Specifically useful is the <xref:System.Transactions.Transaction.Rollback%2A> method on the <xref:System.Transactions.Transaction> class that can also be used to rollback a <xref:System.Transactions.CommittableTransaction> object.</span></span>  
  
 <span data-ttu-id="7565e-109"><xref:System.Transactions.Transaction> Třída je podobně jako <xref:System.Transactions.CommittableTransaction> třídy, ale nenabízí `Commit` metody.</span><span class="sxs-lookup"><span data-stu-id="7565e-109">The  <xref:System.Transactions.Transaction> class is similar to the <xref:System.Transactions.CommittableTransaction> class but does not offer a `Commit` method.</span></span> <span data-ttu-id="7565e-110">To umožňuje předat objekt transakce (nebo klony jeho) do jiné metody (potenciálně na jiných vláknech) při stále řízení při transakce se potvrzeny.</span><span class="sxs-lookup"><span data-stu-id="7565e-110">This enables you to pass the transaction object (or clones of it) to other methods (potentially on other threads) while still controlling when the transaction is committed.</span></span> <span data-ttu-id="7565e-111">Je volána kód je možné zařazení a hlasovat pro transakce, ale pouze tvůrce <xref:System.Transactions.CommittableTransaction> objektu má možnost potvrzení transakce.</span><span class="sxs-lookup"><span data-stu-id="7565e-111">The called code is able to enlist and vote on the transaction, but only the creator of the <xref:System.Transactions.CommittableTransaction> object has the ability to commit the transaction.</span></span>  
  
 <span data-ttu-id="7565e-112">Všimněte si těchto hodnot při práci s <xref:System.Transactions.CommittableTransaction> třídy</span><span class="sxs-lookup"><span data-stu-id="7565e-112">You should note the followings when working with the <xref:System.Transactions.CommittableTransaction> class,</span></span>  
  
-   <span data-ttu-id="7565e-113">Vytváření <xref:System.Transactions.CommittableTransaction> transakce nenastaví okolí transakce.</span><span class="sxs-lookup"><span data-stu-id="7565e-113">Creating a <xref:System.Transactions.CommittableTransaction> transaction does not set the ambient transaction.</span></span> <span data-ttu-id="7565e-114">Je třeba konkrétně nastavena a okolí transakce, ujistěte se, že správci prostředků pracovat v kontextu vpravo transakce v případě potřeby obnovit.</span><span class="sxs-lookup"><span data-stu-id="7565e-114">You need to specifically set and reset the ambient transaction, to ensure that resource managers operate under the right transaction context when appropriate.</span></span> <span data-ttu-id="7565e-115">Způsob, jak nastavit aktuální okolí transakce je nastavením statické <xref:System.Transactions.Transaction.Current%2A> vlastnost na globální <xref:System.Transactions.Transaction> objektu.</span><span class="sxs-lookup"><span data-stu-id="7565e-115">The way to set the current ambient transaction is by setting the static <xref:System.Transactions.Transaction.Current%2A> property on the global <xref:System.Transactions.Transaction> object.</span></span>  
  
-   <span data-ttu-id="7565e-116">Objekt <xref:System.Transactions.CommittableTransaction> objektu nelze znovu použít.</span><span class="sxs-lookup"><span data-stu-id="7565e-116">A <xref:System.Transactions.CommittableTransaction> object cannot be reused.</span></span> <span data-ttu-id="7565e-117">Jednou <xref:System.Transactions.CommittableTransaction> objektu byla potvrzena nebo vrácena zpět, nelze jej použít znovu v transakci.</span><span class="sxs-lookup"><span data-stu-id="7565e-117">Once a <xref:System.Transactions.CommittableTransaction> object has been committed or rolled back, it cannot be used again in a transaction.</span></span> <span data-ttu-id="7565e-118">To znamená nelze jej nastavit jako aktuální kontext okolí transakce.</span><span class="sxs-lookup"><span data-stu-id="7565e-118">That is, it cannot be set as the current ambient transaction context.</span></span>  
  
## <a name="creating-a-committabletransaction"></a><span data-ttu-id="7565e-119">Vytváření CommittableTransaction</span><span class="sxs-lookup"><span data-stu-id="7565e-119">Creating a CommittableTransaction</span></span>  
 <span data-ttu-id="7565e-120">Následující příklad vytvoří nový <xref:System.Transactions.CommittableTransaction> a potvrdí ji.</span><span class="sxs-lookup"><span data-stu-id="7565e-120">The following sample creates a new <xref:System.Transactions.CommittableTransaction> and commits it.</span></span>  
  
 [!code-csharp[Tx_CommittableTx#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/tx_committabletx/cs/committabletxwithsql.cs#1)]
 [!code-vb[Tx_CommittableTx#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/tx_committabletx/vb/committabletxwithsql.vb#1)]  
  
 <span data-ttu-id="7565e-121">Vytváření instance <xref:System.Transactions.CommittableTransaction> automaticky nenastaví kontext okolí transakce.</span><span class="sxs-lookup"><span data-stu-id="7565e-121">Creating an instance of <xref:System.Transactions.CommittableTransaction> does not automatically set the ambient transaction context.</span></span> <span data-ttu-id="7565e-122">Proto všechny operace na správce prostředků není součástí této transakce.</span><span class="sxs-lookup"><span data-stu-id="7565e-122">Therefore, any operation on a resource manager is not part of that transaction.</span></span> <span data-ttu-id="7565e-123">Statické <xref:System.Transactions.Transaction.Current%2A> vlastnost na globální <xref:System.Transactions.Transaction> objektu se používá k nastavení nebo načtení okolí transakce a aplikace musíte ručně nastavit k zajištění správci prostředků mohou být součástí transakce.</span><span class="sxs-lookup"><span data-stu-id="7565e-123">The static <xref:System.Transactions.Transaction.Current%2A> property on the global <xref:System.Transactions.Transaction> object is used to set or retrieve the ambient transaction and the application must manually set it to ensure that resource managers can participate in the transaction.</span></span> <span data-ttu-id="7565e-124">Je také vhodné k uložení původní okolí transakce a jeho obnovení po dokončení práce <xref:System.Transactions.CommittableTransaction> objektu.</span><span class="sxs-lookup"><span data-stu-id="7565e-124">It is also a good practice to save the old ambient transaction and restore it when you finish using the <xref:System.Transactions.CommittableTransaction> object.</span></span>  
  
 <span data-ttu-id="7565e-125">Potvrzení transakce, je třeba explicitně volat <xref:System.Transactions.CommittableTransaction.Commit%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="7565e-125">To commit the transaction, you need to explicitly call the <xref:System.Transactions.CommittableTransaction.Commit%2A> method.</span></span> <span data-ttu-id="7565e-126">Pro vrácení zpět transakcí, měli byste zavolat <xref:System.Transactions.Transaction.Rollback%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="7565e-126">For rolling back a transaction, you should call the <xref:System.Transactions.Transaction.Rollback%2A> method.</span></span> <span data-ttu-id="7565e-127">Je důležité si všimněte si, že až <xref:System.Transactions.CommittableTransaction> byl potvrzené nebo vrátit zpět všechny prostředky zahrnuté v tom, že transakce jsou stále uzamčena.</span><span class="sxs-lookup"><span data-stu-id="7565e-127">It is important to note that until a <xref:System.Transactions.CommittableTransaction> has been committed or rolled back, all the resources involved in that transaction are still locked.</span></span>  
  
 <span data-ttu-id="7565e-128">Objekt <xref:System.Transactions.CommittableTransaction> objekt lze použít v rámci volání funkce a vlákna.</span><span class="sxs-lookup"><span data-stu-id="7565e-128">A <xref:System.Transactions.CommittableTransaction> object can be used across function calls and threads.</span></span> <span data-ttu-id="7565e-129">Je však až do vývojář aplikace ke zpracování výjimek a konkrétně volání <xref:System.Transactions.Transaction.Rollback%28System.Exception%29> metodu v případě selhání.</span><span class="sxs-lookup"><span data-stu-id="7565e-129">However, it is up to the application developer to handle exceptions and specifically call the <xref:System.Transactions.Transaction.Rollback%28System.Exception%29> method in case of failures.</span></span>  
  
## <a name="asynchronous-commit"></a><span data-ttu-id="7565e-130">Asynchronní zápis</span><span class="sxs-lookup"><span data-stu-id="7565e-130">Asynchronous Commit</span></span>  
 <span data-ttu-id="7565e-131"><xref:System.Transactions.CommittableTransaction> Třída rovněž poskytuje mechanismus pro potvrzení transakce asynchronně.</span><span class="sxs-lookup"><span data-stu-id="7565e-131">The <xref:System.Transactions.CommittableTransaction> class also provides a mechanism for committing a transaction asynchronously.</span></span> <span data-ttu-id="7565e-132">Zápis transakce může trvat značné množství času, jak ji může zahrnovat více přístup k databázi a latence možný sítě.</span><span class="sxs-lookup"><span data-stu-id="7565e-132">A transaction commit can take substantial time, as it might involve multiple database access and possible network latency.</span></span> <span data-ttu-id="7565e-133">Pokud chcete, aby se zabránilo zablokování v vysoce výkonných aplikací, můžete pomocí asynchronní zápis dokončete transakční pracovní co nejdříve a spustit operaci potvrzení jako pozadí úlohu.</span><span class="sxs-lookup"><span data-stu-id="7565e-133">When you want to avoid deadlocks in high throughput applications, you can use asynchronous commit to finish the transactional work as soon as possible, and run the commit operation as a background task.</span></span> <span data-ttu-id="7565e-134"><xref:System.Transactions.CommittableTransaction.BeginCommit%2A> a <xref:System.Transactions.CommittableTransaction.EndCommit%2A> metody <xref:System.Transactions.CommittableTransaction> třída umožňuje provést.</span><span class="sxs-lookup"><span data-stu-id="7565e-134">The <xref:System.Transactions.CommittableTransaction.BeginCommit%2A> and <xref:System.Transactions.CommittableTransaction.EndCommit%2A> methods of the <xref:System.Transactions.CommittableTransaction> class allow you to do so.</span></span>  
  
 <span data-ttu-id="7565e-135">Můžete volat <xref:System.Transactions.CommittableTransaction.BeginCommit%2A> odesláním holdup potvrzení na vlákno z fondu podprocesů.</span><span class="sxs-lookup"><span data-stu-id="7565e-135">You can call <xref:System.Transactions.CommittableTransaction.BeginCommit%2A> to dispatch the commit holdup to a thread from the thread pool.</span></span> <span data-ttu-id="7565e-136">Můžete také volat <xref:System.Transactions.CommittableTransaction.EndCommit%2A> k určení, pokud transakce ve skutečnosti byla.</span><span class="sxs-lookup"><span data-stu-id="7565e-136">You can also call <xref:System.Transactions.CommittableTransaction.EndCommit%2A> to determine if the transaction has actually been committed.</span></span> <span data-ttu-id="7565e-137">Je-li transakce se nepodařilo zapsat z jakéhokoli důvodu <xref:System.Transactions.CommittableTransaction.EndCommit%2A> vyvolá výjimka transakce.</span><span class="sxs-lookup"><span data-stu-id="7565e-137">If the transaction failed to commit for whatever reason, <xref:System.Transactions.CommittableTransaction.EndCommit%2A> raises a transaction exception.</span></span> <span data-ttu-id="7565e-138">Pokud není v čase ještě potvrzené transakce <xref:System.Transactions.CommittableTransaction.EndCommit%2A> je volána, volajícího bude blokován, dokud nebude transakce potvrzena nebo zrušena.</span><span class="sxs-lookup"><span data-stu-id="7565e-138">If the transaction is not yet committed by the time <xref:System.Transactions.CommittableTransaction.EndCommit%2A> is called, the caller is blocked until the transaction is committed or aborted.</span></span>  
  
 <span data-ttu-id="7565e-139">Nejjednodušší způsob, jak provést asynchronní zápis je poskytnutím metoda zpětného volání, která se má volat po dokončení potvrzení.</span><span class="sxs-lookup"><span data-stu-id="7565e-139">The easiest way to do an asynchronous commit is by providing a callback method, to be called when committing is finished.</span></span> <span data-ttu-id="7565e-140">Je však třeba volat <xref:System.Transactions.CommittableTransaction.EndCommit%2A> metodu na původní <xref:System.Transactions.CommittableTransaction> objekt použitý k vyvolání volání.</span><span class="sxs-lookup"><span data-stu-id="7565e-140">However, you must call the <xref:System.Transactions.CommittableTransaction.EndCommit%2A> method on the original <xref:System.Transactions.CommittableTransaction> object used to invoke the call.</span></span> <span data-ttu-id="7565e-141">Chcete-li získat tento objekt, můžete přetypování dolů *IAsyncResult* parametru metody zpětného volání, vzhledem k tomu, <xref:System.Transactions.CommittableTransaction> třída implementuje <xref:System.IAsyncResult> třídy.</span><span class="sxs-lookup"><span data-stu-id="7565e-141">To obtain that object, you can downcast the *IAsyncResult* parameter of the callback method, since the <xref:System.Transactions.CommittableTransaction> class implements <xref:System.IAsyncResult> class.</span></span>  
  
 <span data-ttu-id="7565e-142">Následující příklad ukazuje, jak lze provést asynchronní zápis.</span><span class="sxs-lookup"><span data-stu-id="7565e-142">The following example shows how an asynchronous commit can be done.</span></span>  
  
```csharp  
public void DoTransactionalWork()  
{  
     Transaction oldAmbient = Transaction.Current;  
     CommittableTransaction committableTransaction = new CommittableTransaction();  
     Transaction.Current = committableTransaction;  
  
     try  
     {  
          /* Perform transactional work here */  
          // No errors - commit transaction asynchronously  
          committableTransaction.BeginCommit(OnCommitted,null);  
     }  
     finally  
     {  
          //Restore the ambient transaction   
          Transaction.Current = oldAmbient;  
     }  
}  
void OnCommitted(IAsyncResult asyncResult)  
{  
     CommittableTransaction committableTransaction;  
     committableTransaction = asyncResult as CommittableTransaction;     
     Debug.Assert(committableTransaction != null);  
     try  
     {  
          using(committableTransaction)  
          {  
               committableTransaction.EndCommit(asyncResult);  
          }  
     }  
     catch(TransactionException e)  
     {  
          //Handle the failure to commit  
     }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="7565e-143">Viz také</span><span class="sxs-lookup"><span data-stu-id="7565e-143">See Also</span></span>  
 [<span data-ttu-id="7565e-144">Implementace implicitní transakci pomocí oboru transakce</span><span class="sxs-lookup"><span data-stu-id="7565e-144">Implementing an Implicit Transaction using Transaction Scope</span></span>](../../../../docs/framework/data/transactions/implementing-an-implicit-transaction-using-transaction-scope.md)  
 [<span data-ttu-id="7565e-145">Zpracování transakcí</span><span class="sxs-lookup"><span data-stu-id="7565e-145">Transaction Processing</span></span>](../../../../docs/framework/data/transactions/index.md)
---
title: Tok transakcí do služeb pracovních postupů a mimo ně
ms.date: 03/30/2017
ms.assetid: 03ced70e-b540-4dd9-86c8-87f7bd61f609
ms.openlocfilehash: f53bfa3c745a0d487a8daf23f399c1420e36c8ec
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/02/2018
ms.locfileid: "48036049"
---
# <a name="flowing-transactions-into-and-out-of-workflow-services"></a>Tok transakcí do služeb pracovních postupů a mimo ně
Služby pracovních postupů a klienti mohou účastnit transakce.  Operace služeb se stanou součástí okolí transakce, umístěte <xref:System.ServiceModel.Activities.Receive> aktivitu v rámci <xref:System.ServiceModel.Activities.TransactedReceiveScope> aktivity. Všechna volání prováděných <xref:System.ServiceModel.Activities.Send> nebo <xref:System.ServiceModel.Activities.SendReply> aktivitu v rámci <xref:System.ServiceModel.Activities.TransactedReceiveScope> bude také možné v rámci ambientní transakce. Klientská aplikace pracovního postupu můžete vytvořit pomocí okolí transakce <xref:System.Activities.Statements.TransactionScope> aktivity a volání operací služby pomocí okolí transakce. Toto téma vás provede procesem vytvoření služby pracovních postupů a pracovních postupů klienta, který se podílet na transakcích.  
  
> [!WARNING]
>  Pokud instance služby pracovního postupu je načten v rámci transakce a obsahuje pracovní postup <xref:System.Activities.Statements.Persist> aktivity, instance pracovního postupu se zablokuje, dokud nebude transakce vyprší časový limit.  
  
> [!IMPORTANT]
>  Vždy, když použijete <xref:System.ServiceModel.Activities.TransactedReceiveScope> doporučujeme umístit všechny přijme v pracovním postupu v rámci <xref:System.ServiceModel.Activities.TransactedReceiveScope> aktivity.  
  
> [!IMPORTANT]
>  Při použití <xref:System.ServiceModel.Activities.TransactedReceiveScope> a doručování zpráv v nesprávném pořadí, pracovní postup přeruší se při pokusu doručit první zprávu mimo pořadí. Můžete třeba Ujistěte se, že váš pracovní postup je vždy na konzistentního koncový bod při pracovního postupu nečinné po dlouhou dobu. To vám umožní restartovat pracovní postup z předchozího bodu trvalosti by měl pracovní postup přeruší.  
  
### <a name="create-a-shared-library"></a>Vytvořte sdílenou knihovnu  
  
1.  Vytvoření nové prázdné řešení sady Visual Studio.  
  
2.  Přidat nový projekt knihovny tříd s názvem `Common`. Přidejte odkazy na následující sestavení:  
  
    -   System.Activities.dll  
  
    -   System.ServiceModel.dll  
  
    -   System.ServiceModel.Activities.dll  
  
    -   System.Transactions.dll  
  
3.  Přidejte novou třídu s názvem `PrintTransactionInfo` k `Common` projektu. Tato třída je odvozena z <xref:System.Activities.NativeActivity> a přetížení <xref:System.Activities.NativeActivity.Execute%2A> metody.  
  
    ```  
    using System;  
    using System;  
    using System.Activities;  
    using System.Transactions;  
  
    namespace Common  
    {  
        public class PrintTransactionInfo : NativeActivity  
        {  
            protected override void Execute(NativeActivityContext context)  
            {  
                RuntimeTransactionHandle rth = context.Properties.Find(typeof(RuntimeTransactionHandle).FullName) as RuntimeTransactionHandle;  
  
                if (rth == null)  
                {  
                    Console.WriteLine("There is no ambient RuntimeTransactionHandle");  
                }  
  
                Transaction t = rth.GetCurrentTransaction(context);  
  
                if (t == null)  
                {  
                    Console.WriteLine("There is no ambient transaction");  
                }  
                else  
                {  
                    Console.WriteLine("Transaction: {0} is {1}", t.TransactionInformation.DistributedIdentifier, t.TransactionInformation.Status);  
                }  
            }  
        }  
  
    }  
    ```  
  
     Toto je nativní aktivitu, která zobrazí informace o okolí transakce a používá se v pracovních postupech služby a klient používat v tomto tématu. Sestavte řešení, které chcete zpřístupnit tuto aktivitu v **běžné** část **nástrojů**.  
  
### <a name="implement-the-workflow-service"></a>Implementace služby pracovního postupu  
  
1.  Přidejte novou službu pracovního postupu WCF volá `WorkflowService` k `Common` projektu. Klikněte na tlačítko vpravo `Common` projekt, vyberte **přidat**, **novou položku...** Vyberte **pracovního postupu** pod **nainstalované šablony** a vyberte **služby pracovního postupu WCF**.  
  
     ![Přidání služby pracovního postupu](../../../../docs/framework/wcf/feature-details/media/addwfservice.JPG "AddWFService")  
  
2.  Odstranit výchozí `ReceiveRequest` a `SendResponse` aktivity.  
  
3.  Přetáhnout myší <xref:System.Activities.Statements.WriteLine> aktivitu `Sequential Service` aktivity. Nastavte vlastnost text na `"Workflow Service starting ..."` jak je znázorněno v následujícím příkladu.  
  
     ![Přidání aktivity WriteLine](../../../../docs/framework/wcf/feature-details/media/addwriteline.JPG "AddWriteLine")  
  
4.  Přetáhnout myší <xref:System.ServiceModel.Activities.TransactedReceiveScope> po <xref:System.Activities.Statements.WriteLine> aktivity. <xref:System.ServiceModel.Activities.TransactedReceiveScope> Aktivit najdete v **zasílání zpráv** část **nástrojů**. <xref:System.ServiceModel.Activities.TransactedReceiveScope> Aktivity se skládá ze dvou částí **žádosti** a **tělo**. **Žádosti** oddíl obsahuje <xref:System.ServiceModel.Activities.Receive> aktivity. **Tělo** oddíl obsahuje aktivity ke spuštění v rámci transakce po byla přijata zpráva.  
  
     ![Přidání aktivity TransactedReceiveScope](../../../../docs/framework/wcf/feature-details/media/trs.JPG "TRS")  
  
5.  Vyberte <xref:System.ServiceModel.Activities.TransactedReceiveScope> aktivity a kliknutím **proměnné** tlačítko. Přidejte následující proměnné.  
  
     ![Přidávání proměnných do TransactedReceiveScope](../../../../docs/framework/wcf/feature-details/media/trsvariables.JPG "TRSVariables")  
  
    > [!NOTE]
    >  Můžete odstranit datovou proměnnou, která je k dispozici ve výchozím nastavení. Můžete také použít existující proměnnou popisovač.  
  
6.  Přetáhnout myší <xref:System.ServiceModel.Activities.Receive> aktivitu v rámci **žádosti** část <xref:System.ServiceModel.Activities.TransactedReceiveScope> aktivity. Nastavte následující vlastnosti:  
  
    |Vlastnost|Hodnota|  
    |--------------|-----------|  
    |CanCreateInstance|True (zaškrtávací políčko)|  
    |OperationName|StartSample|  
    |Názvy ServiceContractName|ITransactionSample|  
  
     Pracovní postup by měl vypadat nějak takto:  
  
     ![Přidání aktivity Receive](../../../../docs/framework/wcf/feature-details/media/serviceaddreceive.JPG "ServiceAddReceive")  
  
7.  Klikněte na tlačítko **definovat...**  propojit <xref:System.ServiceModel.Activities.Receive> aktivity a proveďte následující nastavení:  
  
     ![Nastavení zpráv pro aktivitu Receive](../../../../docs/framework/wcf/feature-details/media/receivemessagesettings.JPG "ReceiveMessageSettings")  
  
8.  Přetáhnout myší <xref:System.Activities.Statements.Sequence> aktivity do těla oddílu <xref:System.ServiceModel.Activities.TransactedReceiveScope>. V rámci <xref:System.Activities.Statements.Sequence> aktivity přetáhnout myší dvě <xref:System.Activities.Statements.WriteLine> aktivity a nastavte <xref:System.Activities.Statements.WriteLine.Text%2A> vlastnosti, jak je znázorněno v následující tabulce.  
  
    |Aktivita|Hodnota|  
    |--------------|-----------|  
    |1. WriteLine|"Service: Zobrazit dokončené"|  
    |2. WriteLine|"Service: přijatá =" + requestMessage|  
  
     Pracovní postup by teď měl vypadat takto:  
  
     ![Přidání aktivity WriteLine](../../../../docs/framework/wcf/feature-details/media/afteraddingwritelines.JPG "AfterAddingWriteLines")  
  
9. Přetáhnout myší `PrintTransactionInfo` aktivitu po druhé <xref:System.Activities.Statements.WriteLine> aktivity v **tělo** v <xref:System.ServiceModel.Activities.TransactedReceiveScope> aktivity.  
  
     ![Po přidání PrintTransactionInfo](../../../../docs/framework/wcf/feature-details/media/afteraddingprinttransactioninfo.JPG "AfterAddingPrintTransactionInfo")  
  
10. Přetáhnout myší <xref:System.Activities.Statements.Assign> aktivity po `PrintTransactionInfo` aktivity a nastavte jeho vlastnosti podle následující tabulky.  
  
    |Vlastnost|Hodnota|  
    |--------------|-----------|  
    |Chcete-li|replyMessage|  
    |Hodnota|"Service: odesílání odpovědi."|  
  
11. Přetáhnout myší <xref:System.Activities.Statements.WriteLine> aktivity po <xref:System.Activities.Statements.Assign> aktivity a nastavte jeho <xref:System.Activities.Statements.WriteLine.Text%2A> vlastnost "Service: začít odpověď."  
  
     Pracovní postup by teď měl vypadat takto:  
  
     ![Po přidání přiřadit a WriteLine](../../../../docs/framework/wcf/feature-details/media/afteraddingsbrwriteline.JPG "AfterAddingSBRWriteLine")  
  
12. Klikněte pravým tlačítkem myši <xref:System.ServiceModel.Activities.Receive> aktivitu a vyberte **vytvořit odeslání odpovědi SendReply** a vložte za poslední <xref:System.Activities.Statements.WriteLine> aktivity. Klikněte na tlačítko **definovat...**  propojit `SendReplyToReceive` aktivity a proveďte následující nastavení.  
  
     ![Odpovědět nastavení zpráv](../../../../docs/framework/wcf/feature-details/media/replymessagesettings.JPG "ReplyMessageSettings")  
  
13. Přetáhnout myší <xref:System.Activities.Statements.WriteLine> aktivity po `SendReplyToReceive` aktivity a nastavte má <xref:System.Activities.Statements.WriteLine.Text%2A> vlastnost "Service: byla odeslána odpověď."  
  
14. Přetáhnout myší <xref:System.Activities.Statements.WriteLine> aktivity v dolní části pracovního postupu a nastavte jeho <xref:System.Activities.Statements.WriteLine.Text%2A> vlastnost "Service: ukončení pracovního postupu, stisknutím klávesy ENTER ukončete."  
  
     Pracovní postup dokončený služby by měl vypadat nějak takto:  
  
     ![Dokončení pracovního postupu služby](../../../../docs/framework/wcf/feature-details/media/servicecomplete.jpg "ServiceComplete")  
  
### <a name="implement-the-workflow-client"></a>Implementace klienta pracovního postupu  
  
1.  Přidat novou aplikaci pracovního postupu WCF, s názvem `WorkflowClient` k `Common` projektu. Klikněte na tlačítko vpravo `Common` projekt, vyberte **přidat**, **novou položku...** Vyberte **pracovního postupu** pod **nainstalované šablony** a vyberte **aktivity**.  
  
     ![Přidání projektu aktivity](../../../../docs/framework/wcf/feature-details/media/addactivity.JPG "AddActivity")  
  
2.  Přetáhnout myší <xref:System.Activities.Statements.Sequence> aktivity na návrhovou plochu.  
  
3.  V rámci <xref:System.Activities.Statements.Sequence> přetáhnout aktivity <xref:System.Activities.Statements.WriteLine> aktivity a nastavte jeho <xref:System.Activities.Statements.WriteLine.Text%2A> vlastnost `"Client: Workflow starting"`. Pracovní postup by teď měl vypadat takto:  
  
     ![Přidání aktivity WriteLine](../../../../docs/framework/wcf/feature-details/media/clientaddwriteline.JPG "ClientAddWriteLine")  
  
4.  Přetáhnout myší <xref:System.Activities.Statements.TransactionScope> aktivity po <xref:System.Activities.Statements.WriteLine> aktivity.  Vyberte <xref:System.Activities.Statements.TransactionScope> aktivity, klikněte na tlačítko proměnné a přidejte následující proměnné.  
  
     ![Přidejte proměnné do objektu TransactionScope](../../../../docs/framework/wcf/feature-details/media/tsvariables.JPG "TSVariables")  
  
5.  Přetáhnout myší <xref:System.Activities.Statements.Sequence> aktivity do textu <xref:System.Activities.Statements.TransactionScope> aktivity.  
  
6.  Přetáhnout myší `PrintTransactionInfo` aktivitu v rámci <xref:System.Activities.Statements.Sequence>  
  
7.  Přetáhnout myší <xref:System.Activities.Statements.WriteLine> aktivity po `PrintTransactionInfo` aktivity a nastavte jeho <xref:System.Activities.Statements.WriteLine.Text%2A> vlastnost "Klienta: začátek odeslat". Pracovní postup by teď měl vypadat takto:  
  
     ![Přidání aktivity](../../../../docs/framework/wcf/feature-details/media/clientaddcbswriteline.JPG "ClientAddCBSWriteLine")  
  
8.  Přetáhnout myší <xref:System.ServiceModel.Activities.Send> aktivity po <xref:System.Activities.Statements.Assign> aktivity a nastavte následující vlastnosti:  
  
    |Vlastnost|Hodnota|  
    |--------------|-----------|  
    |EndpointConfigurationName|workflowServiceEndpoint|  
    |OperationName|StartSample|  
    |Názvy ServiceContractName|ITransactionSample|  
  
     Pracovní postup by teď měl vypadat takto:  
  
     ![Nastavení vlastnosti aktivity Send](../../../../docs/framework/wcf/feature-details/media/clientsendsettings.JPG "ClientSendSettings")  
  
9. Klikněte na tlačítko **definovat...**  odkaz a proveďte následující nastavení:  
  
     ![Odeslání zprávy nastavení aktivity](../../../../docs/framework/wcf/feature-details/media/sendmessagesettings.JPG "SendMessageSettings")  
  
10. Klikněte pravým tlačítkem myši <xref:System.ServiceModel.Activities.Send> aktivitu a vyberte **vytvořit ReceiveReply**. <xref:System.ServiceModel.Activities.ReceiveReply> Aktivity se automaticky umístí po <xref:System.ServiceModel.Activities.Send> aktivity.  
  
11. Klikněte na tlačítko... definovat odkaz na aktivitu ReceiveReplyForSend a proveďte následující nastavení:  
  
     ![Nastavení zpráv ReceiveForSend](../../../../docs/framework/wcf/feature-details/media/clientreplymessagesettings.JPG "ClientReplyMessageSettings")  
  
12. Přetáhnout myší <xref:System.Activities.Statements.WriteLine> aktivity mezi <xref:System.ServiceModel.Activities.Send> a <xref:System.ServiceModel.Activities.ReceiveReply> aktivity a nastavte jeho <xref:System.Activities.Statements.WriteLine.Text%2A> vlastnost "klienta: odeslat kompletní."  
  
13. Přetáhnout myší <xref:System.Activities.Statements.WriteLine> aktivity po <xref:System.ServiceModel.Activities.ReceiveReply> aktivity a nastavte jeho <xref:System.Activities.Statements.WriteLine.Text%2A> vlastnost "na straně klienta: přijatá odpověď =" + replyMessage  
  
14. Přetáhnout myší `PrintTransactionInfo` aktivity po <xref:System.Activities.Statements.WriteLine> aktivity.  
  
15. Přetáhnout myší <xref:System.Activities.Statements.WriteLine> aktivity na konci pracovního postupu a nastavte jeho <xref:System.Activities.Statements.WriteLine.Text%2A> vlastnost "Klienta pracovní postup ukončen." Pracovní postup dokončený klienta by mělo vypadat jako na následujícím diagramu.  
  
     ![Dokončené klienta workfliow](../../../../docs/framework/wcf/feature-details/media/clientcompleteworkflow.jpg "ClientCompleteWorkflow")  
  
16. Sestavte řešení.  
  
### <a name="create-the-service-application"></a>Vytvoření aplikace služby  
  
1.  Přidat nový projekt konzolové aplikace s názvem `Service` do řešení. Přidejte odkazy na následující sestavení:  
  
    1.  System.Activities.dll  
  
    2.  System.ServiceModel.dll  
  
    3.  System.ServiceModel.Activities.dll  
  
2.  Otevřete vygenerovaný soubor Program.cs a následující kód:  
  
    ```  
    static void Main()  
          {  
              Console.WriteLine("Building the server.");  
              using (WorkflowServiceHost host = new WorkflowServiceHost(new DeclarativeServiceWorkflow(), new Uri("net.tcp://localhost:8000/TransactedReceiveService/Declarative")))  
              {                
                  //Start the server  
                  host.Open();  
                  Console.WriteLine("Service started.");  
  
                  Console.WriteLine();  
                  Console.ReadLine();  
                  //Shutdown  
                  host.Close();  
              };         
          }  
    ```  
  
3.  Následující soubor app.config přidejte do projektu.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <!-- Copyright © Microsoft Corporation.  All rights reserved. -->  
    <configuration>  
        <system.serviceModel>  
            <bindings>  
                <netTcpBinding>  
                    <binding transactionFlow="true" />  
                </netTcpBinding>  
            </bindings>  
        </system.serviceModel>  
    </configuration>  
    ```  
  
### <a name="create-the-client-application"></a>Vytvoření klientské aplikace  
  
1.  Přidat nový projekt konzolové aplikace s názvem `Client` do řešení. Přidejte odkaz na System.Activities.dll.  
  
2.  Otevřete soubor program.cs a přidejte následující kód.  
  
    ```  
    class Program  
        {  
  
            private static AutoResetEvent syncEvent = new AutoResetEvent(false);  
  
            static void Main(string[] args)  
            {  
                //Build client  
                Console.WriteLine("Building the client.");  
                WorkflowApplication client = new WorkflowApplication(new DeclarativeClientWorkflow());  
                client.Completed = Program.Completed;  
                client.Aborted = Program.Aborted;  
                client.OnUnhandledException = Program.OnUnhandledException;  
  
                //Wait for service to start  
                Console.WriteLine("Press ENTER once service is started.");  
                Console.ReadLine();  
  
                //Start the client              
                Console.WriteLine("Starting the client.");  
                client.Run();  
                syncEvent.WaitOne();  
  
                //Sample complete  
                Console.WriteLine();  
                Console.WriteLine("Client complete. Press ENTER to exit.");  
                Console.ReadLine();  
            }  
  
            private static void Completed(WorkflowApplicationCompletedEventArgs e)  
            {  
                Program.syncEvent.Set();  
            }  
  
            private static void Aborted(WorkflowApplicationAbortedEventArgs e)  
            {  
                Console.WriteLine("Client Aborted: {0}", e.Reason);  
                Program.syncEvent.Set();  
            }  
  
            private static UnhandledExceptionAction OnUnhandledException(WorkflowApplicationUnhandledExceptionEventArgs e)  
            {  
                Console.WriteLine("Client had an unhandled exception: {0}", e.UnhandledException);  
                return UnhandledExceptionAction.Cancel;  
            }  
        }  
    ```  
  
## <a name="see-also"></a>Viz také  

- [Služby pracovních postupů](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
- [Přehled transakcí ve Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/transactions-overview.md)
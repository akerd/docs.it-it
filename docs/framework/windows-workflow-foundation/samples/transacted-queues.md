---
title: Code transazionali
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b1b011dd-5e0b-482c-9bb0-9d8727038f14
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 11d1d0d3481fb575abd01894db631e24c50b6d56
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="transacted-queues"></a>Code transazionali
In questo esempio viene illustrato come integrare code e transazioni in [!INCLUDE[wf](../../../../includes/wf-md.md)] per creare servizi affidabili e scalabili. Oggetto <!--zz <xref:System.Activities.TransactionScope>--> `System.Activities.TransactionScope` viene utilizzato nel flusso di lavoro client per inviare messaggi a una coda in una transazione tramite la <xref:System.ServiceModel.NetMsmqBinding>. Un oggetto <xref:System.ServiceModel.Activities.TransactedReceiveScope> viene usato nel server per ricevere messaggi dalla coda e aggiornare lo stato del flusso di lavoro nella stessa transazione.  
  
## <a name="demonstrates"></a>Dimostrazione  
 <xref:System.Activities.Statements.TransactionScope>, <xref:System.ServiceModel.Activities.TransactedReceiveScope>, <xref:System.ServiceModel.NetMsmqBinding>, <xref:System.ServiceModel.Activities.Receive> e correlazione basata sul contenuto.  
  
## <a name="discussion"></a>Discussione  
 Per illustrare le funzionalità analizzate in questo esempio, viene creato un servizio flusso di lavoro `RewardsPoints` che tiene traccia dei punti guadagnati e usati per un account specificato. Il client usa l'oggetto <xref:System.Activities.WorkflowInvoker> per simulare l'invio di varie richieste alla coda. Per inviare un messaggio alla coda in una transazione, l'attività <xref:System.ServiceModel.Activities.Send> può essere posizionata all'interno della proprietà <xref:System.Activities.Statements.TransactionScope.Body%2A> di un oggetto <xref:System.Activities.Statements.TransactionScope>. In questo esempio, viene eseguito prima il client, quindi il server, per illustrare come i messaggi in coda possono decuplicare le applicazioni client e quelle server.  
  
 Una volta completato il client, il servizio viene configurato e ospitato. Appena viene visualizzato, avvia l'elaborazione dei messaggi già posizionati nella coda. Ogni messaggio viene ricevuto ed elaborato nella stessa transazione server. In questo esempio, il primo messaggio ricevuto è una richiesta `CreateAccount` che crea l'istanza e inizializza la correlazione del contenuto in base al nome dell'account passato come parte del messaggio di richiesta. Per modellare un tipo di servizio prevedibile nel mondo reale, le due seguenti attività <xref:System.ServiceModel.Activities.TransactedReceiveScope> che elaborano i messaggi `AddPoints` e `UsePoints` sono posizionate nei rami paralleli all'interno di un ciclo `while`, in modo che possano elaborare ripetutamente questi messaggi in qualsiasi ordine.  
  
 <xref:System.Activities.Statements.TransactionScope> e <xref:System.ServiceModel.Activities.TransactedReceiveScope> dispongono ognuno di un punto di persistenza implicito alla fine dei relativi ambiti, pertanto l'uso di queste attività in [!INCLUDE[wf1](../../../../includes/wf1-md.md)] in combinazione con le code è un modo affidabile per spostare il flusso di lavoro da uno stato coerente al successivo, assicurando che i messaggi non vengano mai persi.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1.  Installare e configurare MSMQ. Vedere [installazione Accodamento](http://go.microsoft.com/fwlink/?LinkId=178526) per informazioni dettagliate.  
  
2.  Assicurarsi che MSDTC sia in funzione eseguendo il comando seguente su una riga di comando `net start msdtc`  
  
3.  Compilare il progetto e aprire il file eseguibile oppure aprire il progetto in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] e selezionare un'opzione di avvio dal menu Debug. Innanzitutto viene creata la coda, quindi viene eseguito il client e vengono inviati messaggi alla coda, infine viene avviato il servizio e vengono elaborati i messaggi. Per uscire dal programma, premere INVIO.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Transactions\TransactedQueues`

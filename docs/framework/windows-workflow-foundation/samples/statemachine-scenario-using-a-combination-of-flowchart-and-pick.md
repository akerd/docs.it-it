---
title: "Scenario StateMachine utilizzando una combinazione attività FlowChart e Pick"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 88d81395-f7a3-41d8-8439-20a425c538a6
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 46aa2f9a4ed152bfc861bb02ed2d8c6429694764
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="statemachine-scenario-using-a-combination-of-flowchart-and-pick"></a>Scenario StateMachine utilizzando una combinazione attività FlowChart e Pick
In questo esempio, viene illustrato come implementare uno scenario StopWatch semplice usando una combinazione di attività <xref:System.Activities.Statements.Flowchart> e <xref:System.Activities.Statements.Pick>. Vengono usate attività Receive e Send all'interno dell'attività Pick per rimanere in ascolto di eventi Stopwatch.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, visitare la pagina di download per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)]. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\StateMachineWithPick`  
  
## <a name="sample-details"></a>Dettagli dell'esempio  
 Nella tabella seguente vengono elencati i progetti contenuti in questo esempio.  
  
|Nome progetto|Descrizione|  
|-|-|  
|StopWatchService|Questo progetto contiene l'implementazione di una macchina a stati per l'esempio del cronometro usando una combinazione di attività <xref:System.Activities.Statements.Flowchart> e <xref:System.Activities.Statements.Pick>.<br /><br /> L'attività <xref:System.Activities.Statements.Pick> dispone di 3 istruzioni <xref:System.Activities.Statements.PickBranch> all'interno della proprietà <xref:System.Activities.Statements.Pick.Branches%2A> che rimane in ascolto di eventi `GetStart`, `GetStop` e `GetOff`. In base all'evento in ingresso, si attivano i trigger per uno dei rami e viene attivato l'oggetto <xref:System.Activities.Statements.PickBranch.Action%2A> corrispondente. Nella proprietà <xref:System.Activities.Statements.PickBranch.Action%2A> è presente un'istruzione <xref:System.Activities.Statements.Switch%601> che valuta se la transizione è valida e, tal caso, la proprietà `currentState` viene aggiornata allo stato di transizione e inviata al client.<br /><br /> L'attività <xref:System.Activities.Statements.FlowDecision> alla fine di <xref:System.Activities.Statements.Flowchart> valuta la proprietà `currentState` per determinare se lo stato è finale. In caso affermativo, il flusso di lavoro viene terminato. In caso contrario il controllo esegue il loopback all'inizio dell'attività <xref:System.Activities.Statements.Pick> dove il flusso di lavoro attende più eventi Stopwatch.|  
|StopWatchClient|Si tratta di una semplice applicazione console del flusso di lavoro sequenziale che invia vari eventi Stopwatch con semplici combinazioni di attività Send o Receive.|  
  
#### <a name="to-use-this-sample"></a>Per usare questo esempio  
  
1.  Tramite [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire il file della soluzione StateMachineWithPick.sln.  
  
2.  Per compilare la soluzione, premere CTRL+MAIUSC+B.  
  
3.  Avviare StopWatchService.exe da [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] come amministratore facendo clic il file .exe e selezionando **Esegui come amministratore**.  
  
    1.  Passare alla cartella StateMachineWithPick\CS\StopWatchService\bin\Debug.  
  
    2.  Fare clic sul file StopWatchService.exe e selezionare **Esegui come amministratore**.  
  
4.  Avviare l'applicazione client StopWatchClient dall'interno di [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
    1.  In **Esplora**, selezionare il **StopWatchClient** del progetto e fare doppio clic su **imposta come progetto di avvio**.  
  
    2.  Per eseguire la soluzione, premere CTRL+F5.  
  
5.  Tornare alla finestra della console di StopWatchService.exe per visualizzare le transizioni di stato.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\StateMachineWithPick`
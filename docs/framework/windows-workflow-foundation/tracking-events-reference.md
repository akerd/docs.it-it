---
title: "Riferimento agli eventi di rilevamento | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c1c1ee87-f80a-449b-acd0-50d81eef116e
caps.latest.revision: 23
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 23
---
# Riferimento agli eventi di rilevamento
Durante l'esecuzione, un flusso di lavoro di [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] genera eventi di rilevamento durante le varie fasi della durata.L'host può sottoscrivere questi eventi e mantenersi aggiornato sullo stato di avanzamento del flusso di lavoro per tutta la durata.Gli eventi di rilevamento generati vengono descritti in questa sezione.  
  
## Riferimento dell'evento  
  
|ID evento|Livello dell'evento|Messaggio dell'evento|Parole chiave|  
|---------------|-------------------------|---------------------------|-------------------|  
|[100 \- WorkflowInstanceRecord](../../../docs/framework/windows-workflow-foundation//100-workflowinstancerecord.md)|Informazioni|TrackRecord\= WorkflowInstanceRecord, InstanceID \= %1, RecordNumber \= %2, EventTime \= %3, ActivityDefinitionId \= %4, State \= %5, Annotations \= %6, ProfileName \= %7|EndToEndMonitoring, Risoluzione dei problemi, HealthMonitoring, WFTracking|  
|[101 \- WorkflowInstanceUnhandledExceptionRecord](../../../docs/framework/windows-workflow-foundation//101-workflowinstanceunhandledexceptionrecord.md)|Error|TrackRecord \= WorkflowInstanceUnhandledExceptionRecord, InstanceID \= %1, RecordNumber \= %2, EventTime \= %3, ActivityDefinitionId \= %4, SourceName \= %5, SourceId \= %6, SourceInstanceId \= %7, SourceTypeName\=%8, Exception\=%9, Annotations\= %10, ProfileName \= %11|EndToEndMonitoring, Risoluzione dei problemi, HealthMonitoring, WFTracking|  
|[102 \- WorkflowInstanceAbortedRecord](../../../docs/framework/windows-workflow-foundation//102-workflowinstanceabortedrecord.md)|Avviso|TrackRecord \= WorkflowInstanceAbortedRecord, InstanceID \= %1, RecordNumber \= %2, EventTime \= %3, ActivityDefinitionId \= %4, Reason \= %5, Annotations \= %6, ProfileName \= %7|EndToEndMonitoring, Risoluzione dei problemi, HealthMonitoring, WFTracking|  
|[103 \- ActivityStateRecord](../../../docs/framework/windows-workflow-foundation//103-activitystaterecord.md)|Informazioni|TrackRecord \= ActivityStateRecord, InstanceID \= %1, RecordNumber\=%2, EventTime\=%3, State \= %4, Name\=%5, ActivityId\=%6, ActivityInstanceId\=%7, ActivityTypeName\=%8, Arguments\=%9, Variables\=%10, Annotations\=%11, ProfileName \= %12|EndToEndMonitoring, Risoluzione dei problemi, HealthMonitoring, WFTracking|  
|[104 \- ActivityScheduledRecord](../../../docs/framework/windows-workflow-foundation//104-activityscheduledrecord.md)|Informazioni|TrackRecord \= ActivityScheduledRecord, InstanceID \= %1, RecordNumber \= %2, EventTime \= %3, Name \= %4, ActivityId \= %5, ActivityInstanceId \= %6, ActivityTypeName \= %7, ChildActivityName \= %8, ChildActivityId \= %9, ChildActivityInstanceId \= %10, ChildActivityTypeName \=%11, Annotations\=%12, ProfileName \= %13|EndToEndMonitoring, Risoluzione dei problemi, HealthMonitoring, WFTracking|  
|[105 \- FaultPropagationRecord](../../../docs/framework/windows-workflow-foundation//105-faultpropagationrecord.md)|Avviso|TrackRecord \= FaultPropagationRecord, InstanceID\=%1, RecordNumber\=%2, EventTime\=%3, FaultSourceActivityName\=%4, FaultSourceActivityId\=%5, FaultSourceActivityInstanceId\=%6, FaultSourceActivityTypeName\=%7, FaultHandlerActivityName\=%8, FaultHandlerActivityId \= %9, FaultHandlerActivityInstanceId \=%10, FaultHandlerActivityTypeName\=%11, Fault\=%12, IsFaultSource\=%13, Annotations\=%14, ProfileName \= %15|EndToEndMonitoring, Risoluzione dei problemi, HealthMonitoring, WFTracking|  
|[106 \- CancelRequestRecord](../../../docs/framework/windows-workflow-foundation//106-cancelrequestrecord.md)|Informazioni|TrackRecord \= CancelRequestedRecord, InstanceID\=%1, RecordNumber\=%2, EventTime\=%3, Name\=%4, ActivityId\=%5, ActivityInstanceId\=%6, ActivityTypeName \= %7, ChildActivityName \= %8, ChildActivityId \= %9, ChildActivityInstanceId \= %10, ChildActivityTypeName \=%11, Annotations\=%12, ProfileName \= %13|EndToEndMonitoring, Risoluzione dei problemi, HealthMonitoring, WFTracking|  
|[107 \-\- BookmarkResumptionRecord](../../../docs/framework/windows-workflow-foundation//107-bookmarkresumptionrecord.md)|Informazioni|TrackRecord \= BookmarkResumptionRecord, InstanceID\=%1, RecordNumber\=%2,EventTime\=%3, Name\=%4, SubInstanceID\=%5, OwnerActivityName\=%6, OwnerActivityId \=%7, OwnerActivityInstanceId\=%8, OwnerActivityTypeName\=%9, Annotations\=%10, ProfileName \= %11|EndToEndMonitoring, Risoluzione dei problemi, HealthMonitoring, WFTracking|  
|[108 \- CustomTrackingRecordInfo](../../../docs/framework/windows-workflow-foundation//108-customtrackingrecordinfo.md)|Informazioni|TrackRecord \= CustomTrackingRecord, InstanceID \= %1, RecordNumber\=%2, EventTime\=%3, Name\=%4, ActivityName\=%5, ActivityId\=%6, ActivityInstanceId\=%7, ActivityTypeName\=%8, Data\=%9, Annotations\=%10, ProfileName \= %11|UserEvents, EndToEndMonitoring, Risoluzione dei problemi, HealthMonitoring, WFTracking|  
|[110 \- CustomTrackingRecordWarning](../../../docs/framework/windows-workflow-foundation//110-customtrackingrecordwarning.md)|Avviso|TrackRecord \= CustomTrackingRecord, InstanceID \= %1, RecordNumber\=%2, EventTime\=%3, Name\=%4, ActivityName\=%5, ActivityId\=%6, ActivityInstanceId\=%7, ActivityTypeName\=%8, Data\=%9, Annotations\=%10, ProfileName \= %11|UserEvents, EndToEndMonitoring, Risoluzione dei problemi, HealthMonitoring, WFTracking|  
|[111 \- CustomTrackingRecordError](../../../docs/framework/windows-workflow-foundation//111-customtrackingrecorderror.md)|Error|TrackRecord \= CustomTrackingRecord, InstanceID \= %1, RecordNumber\=%2, EventTime\=%3, Name\=%4, ActivityName\=%5, ActivityId\=%6, ActivityInstanceId\=%7, ActivityTypeName\=%8, Data\=%9, Annotations\=%10, ProfileName \= %11|UserEvents, EndToEndMonitoring, Risoluzione dei problemi, HealthMonitoring, WFTracking|  
|[112 \- WorkflowInstanceSuspendedRecord](../../../docs/framework/windows-workflow-foundation//112-workflowinstancesuspendedrecord.md)|Informazioni|TrackRecord \= WorkflowInstanceSuspendedRecord, InstanceID \= %1, RecordNumber \= %2, EventTime \= %3, ActivityDefinitionId \= %4, Reason \= %5, Annotations \= %6, ProfileName \= %7|EndToEndMonitoring, Risoluzione dei problemi, HealthMonitoring, WFTracking|  
|[113 \- WorkflowInstanceTerminatedRecord](../../../docs/framework/windows-workflow-foundation//113-workflowinstanceterminatedrecord.md)|Error|TrackRecord \= WorkflowInstanceTerminatedRecord, InstanceID \= %1, RecordNumber \= %2, EventTime \= %3, ActivityDefinitionId \= %4, Reason \= %5, Annotations \= %6, ProfileName \= %7|EndToEndMonitoring, Risoluzione dei problemi, HealthMonitoring, WFTracking|  
|[114 \- WorkflowInstanceRecordWithId](../../../docs/framework/windows-workflow-foundation//114-workflowinstancerecordwithid.md)|Informazioni|TrackRecord\= WorkflowInstanceRecord, InstanceID \= %1, RecordNumber \= %2, EventTime \= %3, ActivityDefinitionId \= %4, State \= %5, Annotations \= %6, ProfileName \= %7, WorkflowDefinitionIdentity \= %8|HealthMonitoring, WFTracking|  
|[115 \- WorkflowInstanceAbortedRecordWithId](../../../docs/framework/windows-workflow-foundation//115-workflowinstanceabortedrecordwithid.md)|Avviso|TrackRecord \= WorkflowInstanceAbortedRecord, InstanceID \= %1, RecordNumber \= %2, EventTime \= %3, ActivityDefinitionId \= %4, Reason \= %5, Annotations \= %6, ProfileName \= %7, WorkflowDefinitionIdentity \= %8|HealthMonitoring, WFTracking|  
|[116 \- WorkflowInstanceSuspendedRecordWithId](../../../docs/framework/windows-workflow-foundation//116-workflowinstancesuspendedrecordwithid.md)|Informazioni|TrackRecord \= WorkflowInstanceSuspendedRecord, InstanceID \= %1, RecordNumber \= %2, EventTime \= %3, ActivityDefinitionId \= %4, Reason \= %5, Annotations \= %6, ProfileName \= %7, WorkflowDefinitionIdentity \= %8|HealthMonitoring, WFTracking|  
|[117 \- WorkflowInstanceTerminatedRecordWithId](../../../docs/framework/windows-workflow-foundation//117-workflowinstanceterminatedrecordwithid.md)|Error|TrackRecord \= WorkflowInstanceTerminatedRecord, InstanceID \= %1, RecordNumber \= %2, EventTime \= %3, ActivityDefinitionId \= %4, Reason \= %5, Annotations \= %6, ProfileName \= %7, WorkflowDefinitionIdentity \= %8|HealthMonitoring, WFTracking|  
|[118 \- WorkflowInstanceUnhandledExceptionRecordWithId](../../../docs/framework/windows-workflow-foundation//118-workflowinstanceunhandledexceptionrecordwithid.md)|Error|TrackRecord \= WorkflowInstanceUnhandledExceptionRecord, InstanceID \= %1, RecordNumber \= %2, EventTime \= %3, ActivityDefinitionId \= %4, SourceName \= %5, SourceId \= %6, SourceInstanceId \= %7, SourceTypeName\=%8, Exception\=%9, Annotations\= %10, ProfileName \= %11, WorkflowDefinitionIdentity \= %12|HealthMonitoring, WFTrackingHealthMonitoring, WFTracking|  
|[119 \- WorkflowInstanceUpdatedRecord](../../../docs/framework/windows-workflow-foundation//119-workflowinstanceupdatedrecord.md)|Informazioni|TrackRecord\= WorkflowInstanceUpdatedRecord, InstanceID \= %1, RecordNumber \= %2, EventTime \= %3, ActivityDefinitionId \= %4, State \= %5, OriginalDefinitionIdentity \= %6, UpdatedDefinitionIdentity \= %7, Annotations \= %8, ProfileName \= %9|HealthMonitoring, WFTracking|  
|[225 \- TraceCorrelationKeys](../../../docs/framework/windows-workflow-foundation//225-tracecorrelationkeys.md)|Informazioni|Chiave di correlazione '%1' calcolata utilizzando i valori '%2' nell'ambito padre '%3'.|Risoluzione dei problemi di WFServices|  
|[440 \- StartSignpostEvent1](../../../docs/framework/windows-workflow-foundation//440-startsignpostevent.md)|Informazioni|Limite dell'attività.|Risoluzione dei problemi di WFServices|  
|[441\- StopSignpostEvent1](../../../docs/framework/windows-workflow-foundation//441-stopsignpostevent.md)|Informazioni|Limite dell'attività.|Risoluzione dei problemi di WFServices|  
|[1001 \- WorkflowApplicationCompleted](../../../docs/framework/windows-workflow-foundation//1001-workflowapplicationcompleted.md)|Informazioni|WorkflowInstance con ID: '%1' completato nello stato Closed.|WFRuntime|  
|[1002 \- WorkflowApplicationTerminated](../../../docs/framework/windows-workflow-foundation//1002-workflowapplicationterminated.md)|Informazioni|WorkflowApplication con ID: '%1' terminata.È stata completata nello stato Faulted con un'eccezione.|WFRuntime|  
|[1003 \- WorkflowInstanceCanceled](../../../docs/framework/windows-workflow-foundation//1003-workflowinstancecanceled.md)|Informazioni|WorkflowInstance con ID: '%1' completata nello stato Canceled.|WFRuntime|  
|[1004 \- WorkflowInstanceAborted](../../../docs/framework/windows-workflow-foundation//1004-workflowinstanceaborted.md)|Informazioni|WorkflowInstance con ID: '%1' interrotta con un'eccezione.|WFRuntime|  
|[1005 \- WorkflowApplicationIdled](../../../docs/framework/windows-workflow-foundation//1005-workflowapplicationidled.md)|Informazioni|WorkflowApplication con ID: '%1' inattiva.|WFRuntime|  
|[1006 \- WorkflowApplicationUnhandledException](../../../docs/framework/windows-workflow-foundation//1006-workflowapplicationunhandledexception.md)|Error|WorkflowInstance con ID: '%1' ha riscontrato un'eccezione non gestita. Eccezione originata dall'attività '%2', DisplayName: '%3'. Verrà effettuata l'azione seguente: %4.|WFRuntime|  
|[1007 \- WorkflowApplicationPersisted](../../../docs/framework/windows-workflow-foundation//1007-workflowapplicationpersisted.md)|Informazioni|WorkflowApplication con ID: '%1' persistente.|WFRuntime|  
|[1008 \- WorkflowApplicationUnloaded](../../../docs/framework/windows-workflow-foundation//1008-workflowapplicationunloaded.md)|Informazioni|WorkflowInstance con ID: '%1' scaricata.|WFRuntime|  
|[1009 \- ActivityScheduled](../../../docs/framework/windows-workflow-foundation//1009-activityscheduled.md)|Informazioni|L'attività padre '%1', DisplayName: '%2', InstanceId: '%3' ha pianificato l'attività figlio '%4'', DisplayName: '%5', InstanceId: '%6'.|WFRuntime|  
|[1010 \- ActivityCompleted](../../../docs/framework/windows-workflow-foundation//1010-activitycompleted.md)|Informazioni|L'attività padre '%1', DisplayName: '%2', InstanceId: '%3' ha pianificato l'attività figlio '%4'', DisplayName: '%5', InstanceId: '%6'.|WFRuntime|  
|[1011 \- ScheduleExecuteActivityWorkItem](../../../docs/framework/windows-workflow-foundation//1011-scheduleexecuteactivityworkitem.md)|Verbose|ExecuteActivityWorkItem pianificato per l'attività '%1, DisplayName: '%2', InstanceId: '%3'.|WFRuntime|  
|[1012 \- StartExecuteActivityWorkItem](../../../docs/framework/windows-workflow-foundation//1012-startexecuteactivityworkitem.md)|Verbose|Avvio dell'esecuzione di ExecuteActivityWorkItem per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.|WFRuntime|  
|[1013 \- CompleteExecuteActivityWorkItem](../../../docs/framework/windows-workflow-foundation//1013-completeexecuteactivityworkitem.md)|Verbose|ExecuteActivityWorkItem completato per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.|WFRuntime|  
|[1014 \- ScheduleCompletionWorkItem](../../../docs/framework/windows-workflow-foundation//1014-schedulecompletionworkitem.md)|Verbose|CompletionWorkItem pianificato per l'attività padre '%1', DisplayName: '%2', InstanceId: '%3'. Attività '%4', DisplayName: '%5', InstanceId: '%6' completata.|WFRuntime|  
|[1015 \- StartCompletionWorkItem](../../../docs/framework/windows-workflow-foundation//1015-startcompletionworkitem.md)|Verbose|Avvio dell'esecuzione di CompletionWorkItem per l'attività padre '%1', DisplayName: '%2', InstanceId: '%3'.Attività '%4', DisplayName: '%5', InstanceId: '%6' completata.|WFRuntime|  
|[1016 \- CompleteCompletionWorkItem](../../../docs/framework/windows-workflow-foundation//1016-completecompletionworkitem.md)|Verbose|CompletionWorkItem completato per l'attività padre '%1', DisplayName: '%2', InstanceId: '%3'.Attività '%4', DisplayName: '%5', InstanceId: '%6' completata.|WFRuntime|  
|[1017 \- ScheduleCancelActivityWorkItem](../../../docs/framework/windows-workflow-foundation//1017-schedulecancelactivityworkitem.md)|Verbose|CancelActivityWorkItem pianificato per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.|WFRuntime|  
|[1018 \- StartCancelActivityWorkItem](../../../docs/framework/windows-workflow-foundation//1018-startcancelactivityworkitem.md)|Verbose|Avvio dell'esecuzione di CancelActivityWorkItem per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.|WFRuntime|  
|[1019 \- CompleteCancelActivityWorkItem](../../../docs/framework/windows-workflow-foundation//1019-completecancelactivityworkitem.md)|Verbose|CancelActivityWorkItem completato per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.|WFRuntime|  
|[1020 \- CreateBookmark](../../../docs/framework/windows-workflow-foundation//1020-createbookmark.md)|Verbose|Bookmark creato per l'attività '%1', DisplayName: '%2', InstanceId: '%3'. BookmarkName: %4, BookmarkScope: %5.|WFRuntime|  
|[1021 \- ScheduleBookmarkWorkItem](../../../docs/framework/windows-workflow-foundation//1021-schedulebookmarkworkitem.md)|Verbose|BookmarkWorkItem pianificato per l'attività '%1', DisplayName: '%2', InstanceId: '%3'. BookmarkName: %4, BookmarkScope: %5.|WFRuntime|  
|[1022 \- StartBookmarkWorkItem](../../../docs/framework/windows-workflow-foundation//1022-startbookmarkworkitem.md)|Verbose|Avvio dell'esecuzione di BookmarkWorkItem per l'attività '%1', DisplayName: '%2', InstanceId: '%3'. BookmarkName: %4, BookmarkScope: %5.|WFRuntime|  
|[1023 \- CompleteBookmarkWorkItem](../../../docs/framework/windows-workflow-foundation//1023-completebookmarkworkitem.md)|Verbose|BookmarkWorkItem completato per l'attività '%1', DisplayName: '%2', InstanceId: '%3'. BookmarkName: %4, BookmarkScope: %5.BookmarkName: %4, BookmarkScope: %5.|WFRuntime|  
|[1024 \- CreateBookmarkScope](../../../docs/framework/windows-workflow-foundation//1024-createbookmarkscope.md)|Verbose|BookmarkScope creato: %1.|WFRuntime|  
|[1025 \- BookmarkScopeInitialized](../../../docs/framework/windows-workflow-foundation//1025-bookmarkscopeinitialized.md)|Verbose|BookmarkScope con TemporaryId: '%1' è stato inizializzato con ID: '%2'.|WFRuntime|  
|[1026 \- ScheduleTransactionContextWorkItem](../../../docs/framework/windows-workflow-foundation//1026-scheduletransactioncontextworkitem.md)|Verbose|TransactionContextWorkItem pianificato per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.|WFRuntime|  
|[1027 \- StartTransactionContextWorkItem](../../../docs/framework/windows-workflow-foundation//1027-starttransactioncontextworkitem.md)|Verbose|Avvio dell'esecuzione di TransactionContextWorkItem per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.|WFRuntime|  
|[1028 \- CompleteTransactionContextWorkItem](../../../docs/framework/windows-workflow-foundation//1028-completetransactioncontextworkitem.md)|Verbose|TransactionContextWorkItem completato per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.|WFRuntime|  
|[1029 \- ScheduleFaultWorkItem](../../../docs/framework/windows-workflow-foundation//1029-schedulefaultworkitem.md)|Verbose|FaultWorkItem pianificato per l'attività '%1', DisplayName: '%2', InstanceId: '%3'. Eccezione propagata dall'attività '%4', DisplayName: '%5', InstanceId: '%6'.|WFRuntime|  
|[1030 \- StartFaultWorkItem](../../../docs/framework/windows-workflow-foundation//1030-startfaultworkitem.md)|Verbose|Avvio dell'esecuzione di FaultWorkItem per l'attività '%1', DisplayName: '%2', InstanceId: '%3'. Eccezione propagata dall'attività '%4', DisplayName: '%5', InstanceId: '%6'.|WFRuntime|  
|[1031 \- CompleteFaultWorkItem](../../../docs/framework/windows-workflow-foundation//1031-completefaultworkitem.md)|Verbose|FaultWorkItem completato per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.Eccezione propagata dall'attività '%4', DisplayName: '%5', InstanceId: '%6'.|WFRuntime|  
|[1032 \- ScheduleRuntimeWorkItem](../../../docs/framework/windows-workflow-foundation//1032-scheduleruntimeworkitem.md)|Verbose|Elemento di lavoro del runtime pianificato per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.|WFRuntime|  
|[1033 \- StartRuntimeWorkItem](../../../docs/framework/windows-workflow-foundation//1033-startruntimeworkitem.md)|Verbose|Avvio dell'esecuzione di un elemento di lavoro del runtime per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.|WFRuntime|  
|[1034 \- CompleteRuntimeWorkItem](../../../docs/framework/windows-workflow-foundation//1034-completeruntimeworkitem.md)|Verbose|Elemento di lavoro del runtime completato per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.|WFRuntime|  
|[1035 \- RuntimeTransactionSet](../../../docs/framework/windows-workflow-foundation//1035-runtimetransactionset.md)|Verbose|Transazione di runtime impostata dall'attività '%1', DisplayName: '%2', InstanceId: '%3'. Esecuzione isolata all'attività '%4', DisplayName: '%5', InstanceId: '%6'.|WFRuntime|  
|[1036 \- RuntimeTransactionCompletionRequested](../../../docs/framework/windows-workflow-foundation//1036-runtimetransactioncompletionrequested.md)|Verbose|L'attività '%1', DisplayName: '%2', InstanceId: '%3' ha pianificato il completamento della transazione di runtime.|WFRuntime|  
|[1037 \- RuntimeTransactionComplete](../../../docs/framework/windows-workflow-foundation//1037-runtimetransactioncomplete.md)|Verbose|Transazione del runtime completata con lo stato '%1'.|WFRuntime|  
|[1038 \- EnterNoPersistBlock](../../../docs/framework/windows-workflow-foundation//1038-enternopersistblock.md)|Verbose|Accesso a un blocco di non persistenza.|WFRuntime|  
|[1039 \- ExitNoPersistBlock](../../../docs/framework/windows-workflow-foundation//1039-exitnopersistblock.md)|Verbose|Uscita da un blocco di non persistenza.|WFRuntime|  
|[1040 \- InArgumentBound](../../../docs/framework/windows-workflow-foundation//1040-inargumentbound.md)|Verbose|Argomento In '%1' nell'attività '%2', DisplayName: '%3', InstanceId: '%4' è stato associato al valore: %5.|WFActivities|  
|[1041 \- WorkflowApplicationPersistableIdle](../../../docs/framework/windows-workflow-foundation//1041-workflowapplicationpersistableidle.md)|Informazioni|WorkflowApplication con ID: '%1' è inattiva e persistente. Verrà effettuata l'azione seguente: %2.|WFRuntime|  
|[1101 \- WorkflowActivityStart](../../../docs/framework/windows-workflow-foundation//1101-workflowactivitystart.md)|Informazioni|Attività end\-to\-end di WorkflowInstance con ID: '%1'|WFRuntime|  
|[1102 \- WorkflowActivityStop](../../../docs/framework/windows-workflow-foundation//1102-workflowactivitystop.md)|Informazioni|Attività end\-to\-end di WorkflowInstance con ID: '%1'|WFRuntime|  
|[1103 \- WorkflowActivitySuspend](../../../docs/framework/windows-workflow-foundation//1103-workflowactivitysuspend.md)|Informazioni|Attività end\-to\-end di WorkflowInstance con ID: '%1'|WFRuntime|  
|[1104 \- WorkflowActivityResume](../../../docs/framework/windows-workflow-foundation//1104-workflowactivityresume.md)|Informazioni|Attività end\-to\-end di WorkflowInstance con ID: '%1'|WFRuntime|  
|[1124 \- InvokeMethodIsStatic](../../../docs/framework/windows-workflow-foundation//1124-invokemethodisstatic.md)|Informazioni|InvokeMethod '%1': il metodo è statico.|WFRuntime|  
|[1125 \- InvokeMethodIsNotStatic](../../../docs/framework/windows-workflow-foundation//1125-invokemethodisnotstatic.md)|Informazioni|InvokeMethod '%1': il metodo non è statico.|WFRuntime|  
|[1126 \- InvokedMethodThrewException](../../../docs/framework/windows-workflow-foundation//1126-invokedmethodthrewexception.md)|Informazioni|È stata generata un'eccezione nel metodo chiamato dall'attività '%1'.%2|WFRuntime|  
|[1131 \- InvokeMethodUseAsyncPattern](../../../docs/framework/windows-workflow-foundation//1131-invokemethoduseasyncpattern.md)|Informazioni|InvokeMethod '%1': il metodo utilizza un modello asincrono di '%2' e '%3'.|WFRuntime|  
|[1132 \- InvokeMethodDoesNotUseAsyncPattern](../../../docs/framework/windows-workflow-foundation//1132-invokemethoddoesnotuseasyncpattern.md)|Informazioni|InvokeMethod '%1': il metodo non utilizza un modello asincrono.|WFRuntime|  
|[1140 \- FlowchartStart](../../../docs/framework/windows-workflow-foundation//1140-flowchartstart.md)|Informazioni|Diagramma di flusso '%1': è stato pianificato l'avvio.|WFActivities|  
|[1141 \- FlowchartEmpty](../../../docs/framework/windows-workflow-foundation//1141-flowchartempty.md)|Avviso|Diagramma di flusso '%1': eseguito senza nodi. È stata generata un'eccezione nel metodo chiamato dall'attività '%1'.%2|WFActivities|  
|[1143 \- FlowchartNextNull](../../../docs/framework/windows-workflow-foundation//1143-flowchartnextnull.md)|Informazioni|Diagramma di flusso '%1'\/FlowStep: il nodo successivo è Null.L'esecuzione del diagramma di flusso terminerà.|WFActivities|  
|[1146 \- FlowchartSwitchCase](../../../docs/framework/windows-workflow-foundation//1146-flowchartswitchcase.md)|Informazioni|Diagramma di flusso '%1'\/FlowSwitch: è stato selezionato il case '%2'.|WFActivities|  
|[1147 \- FlowchartSwitchDefault](../../../docs/framework/windows-workflow-foundation//1147-flowchartswitchdefault.md)|Informazioni|Diagramma di flusso '%1'\/FlowSwitch: è stato selezionato il case predefinito.|WFActivities|  
|[1148 \- FlowchartSwitchCaseNotFound](../../../docs/framework/windows-workflow-foundation//1148-flowchartswitchcasenotfound.md)|Informazioni|Diagramma di flusso '%1'\/FlowSwitch: impossibile trovare un'attività Case o un case predefinito corrispondente al risultato dell'espressione.L'esecuzione del diagramma di flusso terminerà.|WFActivities|  
|[1150 \- CompensationState](../../../docs/framework/windows-workflow-foundation//1150-compensationstate.md)|Informazioni|CompensableActivity '%1' è nello stato '%2'.|WFActivities|  
|[1223 \- SwitchCaseNotFound](../../../docs/framework/windows-workflow-foundation//1223-switchcasenotfound.md)|Informazioni|L'attività Switch '%1' non è in grado di trovare un'attività Case corrispondente al risultato dell'espressione.|WFActivities|  
|[1449 \- WfMessageReceived](../../../docs/framework/windows-workflow-foundation//1449-wfmessagereceived.md)|Informazioni|Messaggio ricevuto dal flusso di lavoro|WFServices|  
|[1450 \- WfMessageSent](../../../docs/framework/windows-workflow-foundation//1450-wfmessagesent.md)|Informazioni|Messaggio inviato dal flusso di lavoro|WFServices|  
|[2021 \- ExecuteWorkItemStart](../../../docs/framework/windows-workflow-foundation//2021-executeworkitemstart.md)|Verbose|Avvio esecuzione elemento di lavoro|WFRuntime|  
|[2022 \- ExecuteWorkItemStop](../../../docs/framework/windows-workflow-foundation//2022-executeworkitemstop.md)|Verbose|Arresto esecuzione elemento di lavoro|WFRuntime|  
|[2023 \- SendMessageChannelCacheMiss](../../../docs/framework/windows-workflow-foundation//2023-sendmessagechannelcachemiss.md)|Verbose|SendMessageChannelCache mancante|WFRuntime|  
|[2024 \- InternalCacheMetadataStart](../../../docs/framework/windows-workflow-foundation//2024-internalcachemetadatastart.md)|Verbose|InternalCacheMetadata avviato nell'attività '%1'.|WFRuntime|  
|[2025 \- InternalCacheMetadataStop](../../../docs/framework/windows-workflow-foundation//2025-internalcachemetadatastop.md)|Verbose|InternalCacheMetadata arrestato nell'attività '%1'.|WFRuntime|  
|[2026 \- CompileVbExpressionStart](../../../docs/framework/windows-workflow-foundation//2026-compilevbexpressionstart.md)|Verbose|Compilazione espressione VB '%1'|WFRuntime|  
|[2027 \- CacheRootMetadataStart](../../../docs/framework/windows-workflow-foundation//2027-cacherootmetadatastart.md)|Verbose|CacheRootMetadata avviato nell'attività '%1'|WFRuntime|  
|[2028 \- CacheRootMetadataStop](../../../docs/framework/windows-workflow-foundation//2028-cacherootmetadatastop.md)|Verbose|CacheRootMetadata arrestato nell'attività '%1'.|WFRuntime|  
|[2029 \- CompileVbExpressionStop](../../../docs/framework/windows-workflow-foundation//2029-compilevbexpressionstop.md)|Verbose|Compilazione espressione VB terminata.|WFRuntime|  
|[2576 \- TryCatchExceptionFromTry](../../../docs/framework/windows-workflow-foundation//2576-trycatchexceptionfromtry.md)|Informazioni|L'attività TryCatch '%1' ha intercettato un'eccezione di tipo '%2'.|WFActivities|  
|[2577 \- TryCatchExceptionDuringCancelation](../../../docs/framework/windows-workflow-foundation//2577-trycatchexceptionduringcancelation.md)|Avviso|Un'attività figlio dell'attività TryCatch '%1' ha generato un'eccezione durante l'annullamento.|WFActivities|  
|[2578 \- TryCatchExceptionFromCatchOrFinally](../../../docs/framework/windows-workflow-foundation//2578-trycatchexceptionfromcatchorfinally.md)|Avviso|Un'attività Catch o Finally associata all'attività TryCatch '%1' ha generato un'eccezione.|WFActivities|  
|[3501 \- InferredContractDescription](../../../docs/framework/windows-workflow-foundation//3501-inferredcontractdescription.md)|Informazioni|ContractDescription con Name\='%1' e Namespace\='%2' dedotta da WorkflowService.|WFServices|  
|[3502 \- InferredOperationDescription](../../../docs/framework/windows-workflow-foundation//3502-inferredoperationdescription.md)|Informazioni|OperationDescription con Name\='%1' nel contratto '%2' dedotta da WorkflowService. IsOneWay\=%3.IsOneWay\=%3.|WFServices|  
|[3503 \- DuplicateCorrelationQuery](../../../docs/framework/windows-workflow-foundation//3503-duplicatecorrelationquery.md)|Avviso|CorrelationQuery duplicata trovata con Where\='%1'.La query duplicata non verrà utilizzata per il calcolo della correlazione.|WFServices|  
|[3507 \- ServiceEndpointAdded](../../../docs/framework/windows-workflow-foundation//3507-serviceendpointadded.md)|Informazioni|È stato aggiunto un endpoint del servizio per l'indirizzo '%1', binding '%2' e contratto '%3'.|WFServices|  
|[3508 \- TrackingProfileNotFound](../../../docs/framework/windows-workflow-foundation//3508-trackingprofilenotfound.md)|Verbose|Impossibile trovare TrackingProfile '%1' per ActivityDefinitionId '%2'.TrackingProfile non presente nel file di configurazione oppure ActivityDefinitionId non corrisponde.|WFServices|  
|[3550 \- BufferOutOfOrderMessageNoInstance](../../../docs/framework/windows-workflow-foundation//3550-bufferoutofordermessagenoinstance.md)|Informazioni|Impossibile eseguire l'operazione '%1'.Verrà effettuato un altro tentativo quando l'istanza del servizio è pronta a elaborare questa operazione.|WFServices|  
|[3551 \- BufferOutOfOrderMessageNoBookmark](../../../docs/framework/windows-workflow-foundation//3551-bufferoutofordermessagenobookmark.md)|Informazioni|Impossibile eseguire l'operazione '%2' nell'istanza del servizio '%1'.Verrà effettuato un altro tentativo quando l'istanza del servizio è pronta a elaborare questa operazione.|WFServices|  
|[3552 \- MaxPendingMessagesPerChannelExceeded](../../../docs/framework/windows-workflow-foundation//3552-maxpendingmessagesperchannelexceeded.md)|Avviso|È stato raggiunto il limite '%1' per la velocità 'MaxPendingMessagesPerChannel'.Per aumentare questo limite, modificare la proprietà MaxPendingMessagesPerChannel in BufferedReceiveServiceBehavior.|Quota WFServices|  
|[3557 \- TransactedReceiveScopeEndCommitFailed](../../../docs/framework/windows-workflow-foundation//3557-transactedreceivescopeendcommitfailed.md)|Informazioni|La chiamata a EndCommit in CommittableTransaction con ID \= '%1' ha generato TransactionException con il messaggio seguente: '%2'.|WFServices|  
|[4201 \- EndSqlCommandExecute](../../../docs/framework/windows-workflow-foundation//4201-endsqlcommandexecute.md)|Verbose|Fine esecuzione comando SQL: %1|WFInstanceStore|  
|[4202 \- StartSqlCommandExecute](../../../docs/framework/windows-workflow-foundation//4202-startsqlcommandexecute.md)|Verbose|Avvio esecuzione comando SQL: %1|WFInstanceStore|  
|[4203 \- RenewLockSystemError](../../../docs/framework/windows-workflow-foundation//4203-renewlocksystemerror.md)|Error|Impossibile estendere la scadenza del blocco. Scadenza già passata o proprietario del blocco eliminato.Interruzione di SqlWorkflowInstanceStore in corso.|WFInstanceStore|  
|[4205 \- FoundProcessingError](../../../docs/framework/windows-workflow-foundation//4205-foundprocessingerror.md)|Error|Comando non riuscito: %1|WFInstanceStore|  
|[4206 \- UnlockInstanceException](../../../docs/framework/windows-workflow-foundation//4206-unlockinstanceexception.md)|Error|Eccezione riscontrata %1 durante il tentativo di sbloccare l'istanza.|WFInstanceStore|  
|[4207 \- MaximumRetriesExceededForSqlCommand](../../../docs/framework/windows-workflow-foundation//4207-maximumretriesexceededforsqlcommand.md)|Informazioni|Interruzione dei tentativi di eseguire un comando SQL. Numero massimo di tentativi raggiunto.|Quota WFInstanceStore|  
|[4208 \- RetryingSqlCommandDueToSqlError](../../../docs/framework/windows-workflow-foundation//4208-retryingsqlcommandduetosqlerror.md)|Informazioni|Nuovo tentativo di esecuzione di un comando SQL in seguito all'errore SQL numero %1.|WFInstanceStore|  
|[4209 \- TimeoutOpeningSqlConnection](../../../docs/framework/windows-workflow-foundation//4209-timeoutopeningsqlconnection.md)|Error|Timeout durante il tentativo di aprire una connessione SQL.Operazione non completata entro il timeout assegnato di %1.È possibile che la durata consentita per l'operazione fosse una porzione di un timeout più lungo.|WFInstanceStore|  
|[4210 \- SqlExceptionCaught](../../../docs/framework/windows-workflow-foundation//4210-sqlexceptioncaught.md)|Avviso|Rilevata eccezione SQL numero %1 messaggio %2.|WFInstanceStore|  
|[4211 \- QueuingSqlRetry](../../../docs/framework/windows-workflow-foundation//4211-queuingsqlretry.md)|Avviso|Accodamento tentativo SQL con ritardo di %1 millisecondi.|WFInstanceStore|  
|[4212 \- LockRetryTimeout](../../../docs/framework/windows-workflow-foundation//4212-lockretrytimeout.md)|Avviso|Timeout durante il tentativo di acquisire il blocco di istanza. Operazione non completata entro il timeout assegnato di %1.È possibile che la durata consentita per l'operazione fosse una porzione di un timeout più lungo.|WFInstanceStore|  
|[4213 \- RunnableInstancesDetectionError](../../../docs/framework/windows-workflow-foundation//4213-runnableinstancesdetectionerror.md)|Error|Rilevamento delle istanze eseguibili non riuscito a causa dell'eccezione seguente|WFInstanceStore|  
|[4214 \- InstanceLocksRecoveryError](../../../docs/framework/windows-workflow-foundation//4214-instancelocksrecoveryerror.md)|Error|Recupero dei blocchi di istanza non riuscito a causa dell'eccezione seguente|WFInstanceStore|  
|[39456 \- TrackingRecordDropped](../../../docs/framework/windows-workflow-foundation//39456-trackingrecorddropped.md)|Avviso|La dimensione del record di rilevamento %1 supera il valore massimo consentito dalla sessione ETW per il provider %2|WFTracking|  
|[39457 \- TrackingRecordRaised](../../../docs/framework/windows-workflow-foundation//39457-trackingrecordraised.md)|Informazioni|Record di rilevamento %1 aumentato a %2.|WFRuntime|  
|[39458 \- TrackingRecordTruncated](../../../docs/framework/windows-workflow-foundation//39458-trackingrecordtruncated.md)|Avviso|Record di rilevamento %1 troncato scritto nella sessione ETW con il provider %2.Variabili\/annotazioni\/dati utente rimossi|WFTracking|  
|[39459 \- TrackingDataExtracted](../../../docs/framework/windows-workflow-foundation//39459-trackingdataextracted.md)|Verbose|Rilevamento dati %1 estratti nell'attività %2.|WFRuntime|  
|[39460 \- TrackingValueNotSerializable](../../../docs/framework/windows-workflow-foundation//39460-trackingvaluenotserializable.md)|Avviso|La variabile\/argomento estratto '%1' non è serializzabile.|WFTracking|  
|[57398 \- MaxInstancesExceeded](../../../docs/framework/windows-workflow-foundation//57398-maxinstancesexceeded.md)|Avviso|Il sistema ha raggiunto il limite impostato per la velocità 'MaxConcurrentInstances'.Il limite per la velocità è stato impostato su %1.Il valore di velocità può essere cambiato modificando l'attributo 'maxConcurrentInstances' nell'elemento serviceThrottle o modificando la proprietà 'MaxConcurrentInstances' nel comportamento ServiceThrottlingBehavior.|WFServices|
---
title: Threading gestito e non gestito in Windows
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], unmanaged
- threading [.NET Framework], managed
- managed threading
ms.assetid: 4fb6452f-c071-420d-9e71-da16dee7a1eb
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3c55caaff3fd96b2791e75a392a9522abfceb22e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="managed-and-unmanaged-threading-in-windows"></a>Threading gestito e non gestito in Windows
La gestione di tutti i thread viene eseguita tramite la classe <xref:System.Threading.Thread> , inclusi i thread creati da Common Language Runtime e quelli creati all'esterno dell'ambiente di esecuzione che accedono all'ambiente gestito per eseguire il codice. L'ambiente di esecuzione monitora tutti i thread nei relativi processi che abbiano eseguito codice nell'ambiente di esecuzione gestito. Non tiene traccia di altri thread. I thread possono accedere all'ambiente di esecuzione gestito tramite l'interoperabilità COM (perché il runtime espone gli oggetti gestiti come oggetti COM all'ambiente non gestito), la funzione [DllGetClassObject](https://msdn.microsoft.com/en-us/library/ms680760.aspx) COM e la funzionalità platform invoke.  
  
 Quando un thread non gestito accede al runtime tramite, ad esempio, un oggetto COM Callable Wrapper, il sistema verifica l'archivio locale dei thread del thread in questione per trovare un oggetto <xref:System.Threading.Thread> gestito interno. Se ne viene trovato uno, all'ambiente di esecuzione è già nota la presenza di questo thread. Se non ne vengono trovati, tuttavia, il runtime compila un nuovo oggetto <xref:System.Threading.Thread> e lo installa nell'archivio locale dei thread del thread in questione.  
  
 Nel threading gestito, <xref:System.Threading.Thread.GetHashCode%2A?displayProperty=nameWithType> rappresenta l'identificazione del thread gestito stabile. Per la durata del thread, questo non entrerà in conflitto con il valore di altri thread, indipendentemente dal dominio dell'applicazione da cui si è ottenuto il valore.  
  
> [!NOTE]
>  L'oggetto **ThreadId** di un sistema operativo non ha una relazione fissa con un thread gestito, perché un host non gestito può controllare la relazione tra thread gestiti e non gestiti. Nello specifico, un host sofisticato può usare l'API Fiber per pianificare molti thread gestiti sullo stesso thread del sistema operativo o spostare un thread gestito tra thread diversi del sistema operativo.  
  
## <a name="mapping-from-win32-threading-to-managed-threading"></a>Mapping dal threading di Win32 al threading gestito  
 Nella tabella seguente viene mostrata la corrispondenza degli elementi del threading di Win32 con gli elementi equivalenti dell'ambiente di esecuzione. Si noti che questa corrispondenza non rappresenta funzionalità identiche. Ad esempio, **TerminateThread** non esegue clausole **finally** o libera risorse e non può essere evitato. Tuttavia, <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> esegue tutto il codice di ripristino dello stato precedente, recupera tutte le risorse e può essere negato tramite <xref:System.Threading.Thread.ResetAbort%2A>. Assicurarsi di leggere attentamente la documentazione prima di fare ipotesi sulle funzionalità.  
  
|Win32|Common Language Runtime|  
|--------------|------------------------------------|  
|**CreateThread**|Combinazione di **Thread** e <xref:System.Threading.ThreadStart>|  
|**TerminateThread**|<xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>|  
|**SuspendThread**|<xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType>|  
|**ResumeThread**|<xref:System.Threading.Thread.Resume%2A?displayProperty=nameWithType>|  
|**Sleep**|<xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType>|  
|**WaitForSingleObject** sull'handle del thread|<xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType>|  
|**ExitThread**|Nessun equivalente|  
|**GetCurrentThread**|<xref:System.Threading.Thread.CurrentThread%2A?displayProperty=nameWithType>|  
|**SetThreadPriority**|<xref:System.Threading.Thread.Priority%2A?displayProperty=nameWithType>|  
|Nessun equivalente|<xref:System.Threading.Thread.Name%2A?displayProperty=nameWithType>|  
|Nessun equivalente|<xref:System.Threading.Thread.IsBackground%2A?displayProperty=nameWithType>|  
|Simile a **CoInitializeEx** (OLE32.DLL)|<xref:System.Threading.Thread.ApartmentState%2A?displayProperty=nameWithType>|  
  
## <a name="managed-threads-and-com-apartments"></a>Thread gestiti e apartment COM  
 Un thread gestito può essere contrassegnato per indicare che ospita un apartment [a thread singolo](http://msdn.microsoft.com/library/windows/desktop/ms680112.aspx) o [a thread multipli](http://msdn.microsoft.com/library/windows/desktop/ms693421.aspx). (Per altre informazioni sull'architettura di threading COM, vedere [Processi, thread e apartment](http://msdn.microsoft.com/library/windows/desktop/ms693344.aspx).) I metodi <xref:System.Threading.Thread.GetApartmentState%2A>, <xref:System.Threading.Thread.SetApartmentState%2A> e <xref:System.Threading.Thread.TrySetApartmentState%2A> della classe <xref:System.Threading.Thread> restituiscono e assegnano lo stato dell'apartment di un thread. Se lo stato non è stato impostato, <xref:System.Threading.Thread.GetApartmentState%2A> restituisce <xref:System.Threading.ApartmentState.Unknown?displayProperty=nameWithType>.  
  
 La proprietà può essere impostata solo quando il thread si trova il <xref:System.Threading.ThreadState.Unstarted?displayProperty=nameWithType> stato; può essere impostata solo una volta per un thread.  
  
 Se lo stato dell'apartment non è impostato prima dell'avvio del thread, il thread viene inizializzato come un apartment a thread multipli. Il thread finalizzatore e tutti i thread controllati da <xref:System.Threading.ThreadPool> sono apartment a thread multipli.  
  
> [!IMPORTANT]
>  Per il codice di avvio dell'applicazione, l'unico modo per controllare lo stato dell'apartment consiste nell'applicare <xref:System.MTAThreadAttribute> o <xref:System.STAThreadAttribute> alla routine del punto di ingresso. In .NET Framework 1.0 e 1.1 la proprietà <xref:System.Threading.Thread.ApartmentState%2A> può essere impostata come la prima riga di codice. In .NET Framework 2.0 questo non è consentito.  
  
 Gli oggetti gestiti esposti a COM si comportano come se avessero aggregato il gestore del marshalling a thread libero. In altre parole, possono essere chiamati da qualsiasi apartment COM con modello a thread libero. Gli unici oggetti gestiti che non esibiscono questo comportamento a thread libero sono gli oggetti che derivano da <xref:System.EnterpriseServices.ServicedComponent> o <xref:System.Runtime.InteropServices.StandardOleMarshalObject>.  
  
 Nell'ambiente gestito non è disponibile il supporto per <xref:System.Runtime.Remoting.Contexts.SynchronizationAttribute> a meno che non si usino i contesti e le istanze gestite associate al contesto. Se si utilizza Enterprise Services, quindi l'oggetto deve derivare da <xref:System.EnterpriseServices.ServicedComponent> (che è a sua volta deriva da <xref:System.ContextBoundObject>).  
  
 Quando il codice gestito effettua una chiamata agli oggetti COM, segue sempre le regole COM. In altre parole, la chiamata viene eseguita tramite proxy di apartment COM e wrapper del contesto COM+ 1.0 come indicato da OLE32.  
  
## <a name="blocking-issues"></a>Problemi di blocco  
 Se un thread effettua una chiamata non gestita all'interno del sistema operativo che ha bloccato il thread nel codice non gestito, l'ambiente di esecuzione non ne assumerà il controllo per <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> o <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>. In caso di <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>, il runtime contrassegna il thread per **Abort** e assume il controllo al rientro nel codice gestito. È preferibile usare il blocco gestito anziché quello non gestito. <xref:System.Threading.WaitHandle.WaitOne%2A?displayProperty=nameWithType>,<xref:System.Threading.WaitHandle.WaitAny%2A?displayProperty=nameWithType>, <xref:System.Threading.WaitHandle.WaitAll%2A?displayProperty=nameWithType>, <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType>, <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType>, <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType>, <xref:System.GC.WaitForPendingFinalizers%2A?displayProperty=nameWithType>e così via rispondono tutti a <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> e <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>. Inoltre, se il thread è incluso in un apartment a thread singolo, tutte queste operazioni di blocco gestite eseguiranno correttamente il pumping dei messaggi nell'apartment fintanto che il thread è bloccato.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Threading.Thread.ApartmentState%2A?displayProperty=nameWithType>  
 <xref:System.Threading.ThreadState>  
 <xref:System.EnterpriseServices.ServicedComponent>  
 <xref:System.Threading.Thread>  
 <xref:System.Threading.Monitor>

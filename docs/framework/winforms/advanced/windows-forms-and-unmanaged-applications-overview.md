---
title: Cenni preliminari su Windows Form e applicazioni non gestite
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- COM [Windows Forms]
- Windows Forms, unmanaged
- COM interop
- ActiveX controls [Windows Forms], about ActiveX controls
- Windows Forms, interop
ms.assetid: 0a26d99d-8135-4895-8760-c9a2b5f67f14
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ae36d1897b452767fae5f48bd6501c18f9405801
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="windows-forms-and-unmanaged-applications-overview"></a>Cenni preliminari su Windows Form e applicazioni non gestite
Le applicazioni e i controlli Windows Form possono interagire con le applicazioni non gestite, con alcune raccomandazioni. Nelle sezioni che seguono vengono descritti configurazioni e scenari supportati e non supportati dalle applicazioni e dai controlli Windows Form.  
  
## <a name="windows-forms-controls-and-activex-applications"></a>Controlli Windows Form e applicazioni ActiveX  
 Fatta eccezione per Microsoft Internet Explorer e MFC (Microsoft Foundation Classes), i controlli Windows Form non sono supportati in applicazioni progettate per ospitare controlli ActiveX. Le altre applicazioni e gli strumenti per lo sviluppo in grado di ospitare controlli ActiveX, come i Test Container ActiveX di versioni di Visual Studio precedenti a Visual Studio .NET 2003, non sono host supportati per i controlli Windows Form.  
  
 Queste limitazioni si applicano anche all'uso dei controlli Windows Form tramite l'interoperabilità COM (Component Object Model). L'uso di un controllo Windows Form tramite COM Callable Wrapper (CCW) è supportato solo in Internet Explorer. Per altre informazioni sull'interoperabilità COM, vedere  
  
 [COM Interop](../../../visual-basic/programming-guide/com-interop/index.md).  
  
 Nella tabella riportata di seguito è illustrato il supporto per l'hosting ActiveX per i controlli Windows Form.  
  
|Versione di Windows Form|Supporto|  
|---------------------------|-------------|  
|.NET Framework versione 1.0|Internet Explorer 5.01 e versioni successive|  
|.NET Framework 1.1 e versioni successive|Internet Explorer 5.01 e versioni successive<br /><br /> MFC (Microsoft Foundation Classes) 7.0 e versioni successive|  
  
## <a name="hosting-windows-forms-components-as-activex-controls"></a>Hosting dei componenti Windows Form come controlli ActiveX  
 In .NET Framework 1.1, il supporto è stato esteso per includere MFC 7.0 e versioni successive. Questo supporto include tutti i contenitori completamente compatibili con il contenitore di controlli ActiveX di MFC 7.0 e versioni successive.  
  
 La registrazione dei controlli Windows Form come controlli ActiveX non è tuttavia supportata, analogamente alla chiamata al metodo `com.ms.win32.Ole32.CoCreateInstance` per i controlli Windows Form. È supportata solo l'attivazione gestita dei controlli Windows Form. Dopo aver creato un controllo Windows Form, è possibile inserirlo in un'applicazione MFC come se fosse un controllo ActiveX.  
  
 Per usare i controlli Windows Form nell'applicazione non gestita, inserire il CLR usando le API per l'hosting del CLR non gestito oppure usare le funzioni di interoperabilità C++. Si consiglia di usare le funzioni di interoperabilità C++.  
  
## <a name="windows-forms-in-com-client-applications"></a>Windows Form in applicazioni client COM  
 Quando si apre un Windows Form da un'applicazione client COM, come un'applicazione Visual Basic 6.0 o un'applicazione MFC, il form può presentare comportamenti imprevisti. Ad esempio, quando si preme il tasto TAB, lo stato di attivazione non passa da un controllo a un altro. Se si preme il tasto INVIO quando un pulsante di comando è nello stato di attivazione, l'evento <xref:System.Windows.Forms.Control.Click> del pulsante non viene generato. Può verificarsi un comportamento imprevisto anche per le pressioni dei tasti o l'attività del mouse.  
  
 Questo comportamento si verifica in quanto l'applicazione non gestita non implementa il supporto del ciclo di messaggi richiesto per il funzionamento corretto di Windows Form. Il ciclo di messaggi fornito dall'applicazione client COM è fondamentalmente diverso dal ciclo di messaggi di Windows Form.  
  
 Il ciclo di messaggi di un'applicazione è un ciclo interno di programma che recupera i messaggi dalla coda di messaggi di un thread, li converte e li invia all'applicazione per la gestione. Il ciclo di messaggi di Windows Form non dispone della stessa architettura dei cicli di messaggi fornita dalle applicazioni precedenti, come le applicazioni Visual Basic 6.0 e le applicazioni MFC. I messaggi inseriti nel ciclo dei messaggi possono essere gestiti in modo diverso da quanto previsto nel Windows Form. Di conseguenza, può prodursi un comportamento imprevisto. Alcune combinazioni di tasti potrebbero non funzionare, così come alcune operazioni eseguite con il mouse, oppure alcuni eventi potrebbero non essere generati in modo appropriato.  
  
## <a name="resolving-interoperability-issues"></a>Risoluzione di problemi di interoperabilità  
 È possibile risolvere i problemi di interoperabilità visualizzando il form in un ciclo di messaggi [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], creato usando il metodo <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType>.  
  
 Perché un Windows Form funzioni correttamente da un'applicazione client COM, è necessario eseguirlo in un ciclo di messaggi Windows Form. Per eseguire questa operazione, adottare uno degli approcci seguenti:  
  
-   Usare il metodo <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> per visualizzare il Windows Form. Per altre informazioni, vedere [How to: Support COM Interop by Displaying a Windows Form with the ShowDialog Method](../../../../docs/framework/winforms/advanced/com-interop-by-displaying-a-windows-form-shadow.md).  
  
-   Visualizzare ogni Windows Form in un nuovo thread. Per altre informazioni, vedere [Procedura: supportare l'interoperabilità COM mediante la visualizzazione di ogni Windows Form nel relativo thread](../../../../docs/framework/winforms/advanced/how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Windows Form e applicazioni non gestite](../../../../docs/framework/winforms/advanced/windows-forms-and-unmanaged-applications.md)  
 [Interoperabilità COM](../../../visual-basic/programming-guide/com-interop/index.md)  
 [Interoperabilità COM nelle applicazioni .NET Framework](~/docs/visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)  
 [Esempi di interoperabilità COM](http://msdn.microsoft.com/en-us/09c38567-6380-4d70-848a-e896a4ca05f4)  
 [Aximp.exe (utilità di importazione di controlli ActiveX di Windows Form)](../../../../docs/framework/tools/aximp-exe-windows-forms-activex-control-importer.md)  
 [Esposizione di componenti .NET Framework a COM](../../../../docs/framework/interop/exposing-dotnet-components-to-com.md)  
 [Preparazione di un assembly per COM](../../../../docs/framework/interop/packaging-an-assembly-for-com.md)  
 [Registrazione di assembly presso COM](../../../../docs/framework/interop/registering-assemblies-with-com.md)  
 [Procedura: Supportare l'interoperabilità COM visualizzando un Windows Form con il metodo ShowDialog](../../../../docs/framework/winforms/advanced/com-interop-by-displaying-a-windows-form-shadow.md)  
 [Procedura: supportare l'interoperabilità COM mediante la visualizzazione di ogni Windows Form nel relativo thread](../../../../docs/framework/winforms/advanced/how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md)

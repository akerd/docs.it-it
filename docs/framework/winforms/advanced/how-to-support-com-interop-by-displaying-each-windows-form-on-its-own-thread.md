---
title: "Procedura: supportare l'interoperabilità COM mediante la visualizzazione di ogni Windows Form nel relativo thread"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: vb
helpviewer_keywords:
- COM interop [Windows Forms], Windows Forms
- COM [Windows Forms]
- Windows Forms, unmanaged
- ActiveX controls [Windows Forms], COM interop
- Windows Forms, interop
ms.assetid: a9e04765-d2de-4389-a494-a9a6d07aa6ee
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8c772f547dc87af6618b92603ed1e709efc511b5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread"></a>Procedura: supportare l'interoperabilità COM mediante la visualizzazione di ogni Windows Form nel relativo thread
Per risolvere i problemi di interoperabilità COM, visualizzare il form in un ciclo di messaggi di [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], che è possibile creare usando il metodo <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType>.  
  
 Perché un Windows Form funzioni correttamente da un'applicazione client COM, è necessario eseguire il form in un ciclo di messaggi Windows Form. Per eseguire questa operazione, adottare uno degli approcci seguenti:  
  
-   Usare il metodo <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> per visualizzare il Windows Form. Per altre informazioni, vedere [How to: Support COM Interop by Displaying a Windows Form with the ShowDialog Method](../../../../docs/framework/winforms/advanced/com-interop-by-displaying-a-windows-form-shadow.md).  
  
-   Visualizzare ogni Windows Form in un thread separato.  
  
 In [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]è disponibile un supporto completo per questa funzionalità.  
  
 Vedere anche [Procedura dettagliata: supporto dell'interoperabilità COM mediante la visualizzazione di ogni Windows Form nel relativo thread](http://msdn.microsoft.com/library/ms233639\(v=vs.110\)).  
  
## <a name="example"></a>Esempio  
 L'esempio di codice seguente illustra come visualizzare il form in un thread separato e chiamare il metodo <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType> per avviare un message pump Windows Form su tale thread. Per adottare questo approccio, è necessario effettuare il marshalling di tutte le chiamate al form dall'applicazione non gestita usando il metodo <xref:System.Windows.Forms.Control.Invoke%2A> .  
  
 Questo approccio richiede che ogni istanza di un form venga eseguita nel rispettivo thread usando il proprio ciclo di messaggi. Non è possibile eseguire più di un ciclo di messaggi per ogni thread. Quindi non è possibile modificare il ciclo di messaggi dell'applicazione client. Tuttavia, è possibile modificare il componente [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] per avviare un nuovo thread che usa il proprio ciclo di messaggi.  
  
 [!code-vb[System.Windows.Forms.ComInterop#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ComInterop/VB/COMForm.vb#1)]  
  
 [!code-vb[System.Windows.Forms.ComInterop#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ComInterop/VB/FormManager.vb#10)]  
  
 [!code-vb[System.Windows.Forms.ComInterop#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ComInterop/VB/Form1.vb#100)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
  
-   Compilare i tipi `COMForm`, `Form1`e `FormManager` in un assembly denominato `COMWinform.dll`. Registrare l'assembly per l'interoperabilità COM usando uno dei metodi descritti in [Packaging an Assembly for COM](../../../../docs/framework/interop/packaging-an-assembly-for-com.md). Ora è possibile usare l'assembly e il file libreria dei tipi (tlb) corrispondente nelle applicazioni non gestite. Ad esempio, è possibile usare la libreria dei tipi come riferimento in un progetto eseguibile di Visual Basic 6.0.  
  
## <a name="see-also"></a>Vedere anche  
 [Esposizione di componenti .NET Framework a COM](../../../../docs/framework/interop/exposing-dotnet-components-to-com.md)  
 [Preparazione di un assembly per COM](../../../../docs/framework/interop/packaging-an-assembly-for-com.md)  
 [Registrazione di assembly presso COM](../../../../docs/framework/interop/registering-assemblies-with-com.md)  
 [Procedura: Supportare l'interoperabilità COM visualizzando un Windows Form con il metodo ShowDialog](../../../../docs/framework/winforms/advanced/com-interop-by-displaying-a-windows-form-shadow.md)  
 [Panoramica su Windows Form e applicazioni non gestite](../../../../docs/framework/winforms/advanced/windows-forms-and-unmanaged-applications-overview.md)

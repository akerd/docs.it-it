---
title: Compilazione di applicazioni console in .NET Framework
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- .NET Framework, building console applications
- application development [.NET Framework], console
- console applications
ms.assetid: c21fb997-9f0e-40a5-8741-f73bba376bd8
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4e0bc3f14a3d21776506f0a269a1a8c9f970cac0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="building-console-applications-in-the-net-framework"></a>Compilazione di applicazioni console in .NET Framework
La classe <xref:System.Console?displayProperty=nameWithType> può essere utilizzata dalle applicazioni in .NET Framework per la lettura e scrittura di caratteri nella console. I dati provenienti dalla console vengono letti dal flusso di input standard, mentre i dati inviati alla console vengono scritti nel flusso di output standard e i dati di errori inviati alla console vengono scritti nel flusso di output standard degli errori. I flussi vengono associati automaticamente alla console in fase di avvio dell'applicazione e vengono presentati rispettivamente come proprietà <xref:System.Console.In%2A>, <xref:System.Console.Out%2A> ed <xref:System.Console.Error%2A>.  
  
 Il valore della proprietà <xref:System.Console.In%2A?displayProperty=nameWithType> è un oggetto <xref:System.IO.TextReader?displayProperty=nameWithType>, mentre i valori delle proprietà <xref:System.Console.Out%2A?displayProperty=nameWithType> e <xref:System.Console.Error%2A?displayProperty=nameWithType> sono oggetti <xref:System.IO.TextWriter?displayProperty=nameWithType>. È possibile associare queste proprietà ai flussi che non rappresentano la console, rendendo possibile l'indirizzamento del flusso a una posizione diversa per l'input e l'output. È possibile ad esempio reindirizzare l'output in un file impostando la proprietà <xref:System.Console.Out%2A?displayProperty=nameWithType> su <xref:System.IO.StreamWriter?displayProperty=nameWithType>, che incapsula un <xref:System.IO.FileStream?displayProperty=nameWithType> tramite il metodo <xref:System.Console.SetOut%2A?displayProperty=nameWithType>. Le proprietà <xref:System.Console.In%2A?displayProperty=nameWithType> e <xref:System.Console.Out%2A?displayProperty=nameWithType> non devono fare necessariamente riferimento allo stesso flusso.  
  
> [!NOTE]
>  Per altre informazioni sulla creazione di applicazioni console, inclusi esempi in C#, Visual Basic e C++, vedere la documentazione per la classe <xref:System.Console>.  
  
 Se la console non esiste, come in un'applicazione Windows, l'output scritto nel flusso di output standard non sarà visibile, in quanto non è disponibile alcuna console in cui scrivere le informazioni. La scrittura di informazioni in una console inaccessibile non genera un'eccezione.  
  
 In alternativa, per abilitare la console per la lettura e la scrittura all'interno di un'applicazione basata su Windows sviluppata con Visual Studio, aprire la finestra di dialogo **Proprietà** del progetto, fare clic sulla scheda **Applicazione** e impostare **Tipo applicazione** su **Applicazione console**.  
  
 Le applicazioni console non dispongono di un message pump avviato per impostazione predefinita. È pertanto possibile che le chiamate ai timer Win32 Microsoft non riescano.  
  
 La classe **System.Console** include metodi che consentono di leggere singoli caratteri o intere righe dalla console. Altri metodi consentono di convertire dati e formattare stringhe, quindi di scrivere le stringhe formattate nella console. Per altre informazioni sulla formattazione delle stringhe, vedere [Formatting Types](../../docs/standard/base-types/formatting-types.md) (Formattazione dei tipi).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Console?displayProperty=nameWithType>  
 [Formattazione di tipi](../../docs/standard/base-types/formatting-types.md)

---
title: 'Procedura: enumerare un sottoinsieme di code di stampa'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- enumerating [WPF], subset of print queues
- print queues [WPF], enumerating subset of
ms.assetid: cc4a1b5b-d46f-4c5e-bc26-22c226e4bee0
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 393d1692526551b1eb9aa16f48d3c78c3cd6692f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-enumerate-a-subset-of-print-queues"></a>Procedura: enumerare un sottoinsieme di code di stampa
Una situazione comune riscontrata da professionisti IT (IT) la gestione di un set a livello aziendale di stampanti consiste nel generare un elenco delle stampanti con determinate caratteristiche. Questa funzionalità viene fornita per il <xref:System.Printing.PrintServer.GetPrintQueues%2A> metodo di un <xref:System.Printing.PrintServer> oggetto e <xref:System.Printing.EnumeratedPrintQueueTypes> enumerazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, il codice inizia creando una matrice di flag che specificano le caratteristiche delle code di stampa che si desidera elencare. In questo esempio, si sta cercando le code di stampa vengono installate localmente nel server di stampa e condivise. Il <xref:System.Printing.EnumeratedPrintQueueTypes> enumerazione offre molte altre possibilità.  
  
 Il codice crea quindi un <xref:System.Printing.LocalPrintServer> dell'oggetto, una classe derivata da <xref:System.Printing.PrintServer>. Server di stampa locale è il computer in cui è in esecuzione l'applicazione.  
  
 L'ultimo passaggio significativo consiste nel passare la matrice di <xref:System.Printing.PrintServer.GetPrintQueues%2A> metodo.  
  
 Infine, i risultati vengono presentati all'utente.  
  
 [!code-cpp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/cpp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CPP/Program.cpp#listsubsetofprintqueues)]
 [!code-csharp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CSharp/Program.cs#listsubsetofprintqueues)]
 [!code-vb[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/visualbasic/program.vb#listsubsetofprintqueues)]  
  
 È possibile estendere questo esempio con il `foreach` ciclo che scorre ogni coda di stampa ulteriormente screening. Ad esempio, è possibile escludere le stampanti che non supportano la stampa fronte retro con la chiamata di ciclo ogni coda di stampa <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> metodo e il valore restituito di test per la presenza di stampa fronte retro.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Printing.PrintServer.GetPrintQueues%2A>  
 <xref:System.Printing.PrintServer>  
 <xref:System.Printing.LocalPrintServer>  
 <xref:System.Printing.EnumeratedPrintQueueTypes>  
 <xref:System.Printing.PrintQueue>  
 <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>  
 [Documenti in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [Panoramica della stampa](../../../../docs/framework/wpf/advanced/printing-overview.md)  
 [Microsoft XPS Document Writer](http://go.microsoft.com/fwlink/?LinkId=147319)

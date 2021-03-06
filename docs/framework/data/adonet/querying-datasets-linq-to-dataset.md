---
title: Esecuzione di query su dataset (LINQ to DataSet)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bb68d2e4-623d-4d60-85e3-965254f6fee7
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 4f1b1a70025dc81bdf99c636b65c23d373e73a80
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="querying-datasets-linq-to-dataset"></a>Esecuzione di query su dataset (LINQ to DataSet)
È possibile iniziare a eseguire query su un oggetto <xref:System.Data.DataSet> dopo averlo popolato con i dati. La formulazione di query con [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] è simile all'utilizzo di [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] su altre origini dati con supporto [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]. Tenere tuttavia presente che quando si utilizza [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] esegue una query su un <xref:System.Data.DataSet> si esegue una query di un'enumerazione dell'oggetto <xref:System.Data.DataRow> oggetti, anziché un'enumerazione di un tipo personalizzato. Ciò significa che è possibile utilizzare uno dei membri del <xref:System.Data.DataRow> classe il [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] query. e creare query dettagliate e complesse.  
  
 Come con altre implementazioni di [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)], è possibile creare [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] query in due formati diversi: espressione sintassi delle query e sintassi di query basate su metodo. Per ulteriori informazioni su questi due formati, vedere [Introduzione a LINQ](http://msdn.microsoft.com/en-us/6cc9af04-950a-4cc3-83d4-2aeb4abe4de9). È possibile utilizzare la sintassi delle espressioni di query o la sintassi delle query basate su metodo per eseguire query su singole tabelle di <xref:System.Data.DataSet>, più tabelle di <xref:System.Data.DataSet> o tabelle di <xref:System.Data.DataSet> tipizzati.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Query su singola tabella](../../../../docs/framework/data/adonet/single-table-queries-linq-to-dataset.md)  
 Viene descritto come eseguire query su una singola tabella.  
  
 [Query tra tabelle](../../../../docs/framework/data/adonet/cross-table-queries-linq-to-dataset.md)  
 Viene descritto come eseguire query tra tabelle.  
  
 [Esecuzione di query su dataset tipizzati](../../../../docs/framework/data/adonet/querying-typed-datasets.md)  
 Viene descritto come eseguire una query su oggetti <xref:System.Data.DataSet> tipizzati.  
  
## <a name="see-also"></a>Vedere anche  
 [LINQ to DataSet esempi](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [Caricamento di dati in un set di dati](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)

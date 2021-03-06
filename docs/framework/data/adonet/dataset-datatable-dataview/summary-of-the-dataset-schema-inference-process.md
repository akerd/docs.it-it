---
title: Riepilogo del processo di inferenza dello schema dataset
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fd0891c8-d068-4e30-a76f-7c375f078bf7
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 15469e917129db7668df17f22fb71b166993d4fc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="summary-of-the-dataset-schema-inference-process"></a>Riepilogo del processo di inferenza dello schema dataset
Il processo di inferenza determina innanzitutto, sulla base del documento XML, quali elementi verranno inferiti come tabelle. Sulla base delle rimanenti informazioni XML, il processo di inferenza consente quindi di determinare le colonne per tali tabelle. Nel caso di tabelle annidate, gli oggetti <xref:System.Data.DataRelation> e <xref:System.Data.ForeignKeyConstraint> vengono generati dal processo di inferenza.  
  
 Di seguito viene riportato un breve riepilogo delle regole di inferenza:  
  
-   Gli elementi a cui sono associati attributi vengono inferiti come tabelle.  
  
-   Gli elementi a cui sono associati elementi figlio vengono inferiti come tabelle.  
  
-   Gli elementi ripetuti vengono inferiti come tabella singola.  
  
-   Se all'elemento del documento, o radice, non sono associati attributi ed elementi figlio da inferire come colonne, tale elemento viene inferito come un tipo <xref:System.Data.DataSet>. In caso contrario, l'elemento del documento viene inferito come tabella.  
  
-   Gli attributi vengono inferiti come colonne.  
  
-   Gli elementi a cui non sono associati attributi o elementi figlio e che non si ripetono vengono inferiti come colonne.  
  
-   Per gli elementi che vengono inferiti come tabelle annidate all'interno di altri elementi inferiti come tabelle, nidificate **DataRelation** viene creato tra due tabelle. Una nuova colonna di chiave primaria denominata **TableName_Id** viene aggiunta a entrambe le tabelle e utilizzato per il **DataRelation**. Oggetto **ForeignKeyConstraint** viene creato tra due tabelle utilizzando il **TableName_Id** colonna.  
  
-   Per gli elementi che vengono inferiti come tabelle e contenenti testo ma non gli elementi figlio, una nuova colonna denominata **TableName_Text** viene creato per il testo di ognuno degli elementi. Se un elemento viene inferito come tabella e dispone di testo, ma a tale elemento sono associati anche elementi figlio, il testo verrà ignorato.  
  
## <a name="see-also"></a>Vedere anche  
 [Inferenza della struttura relazionale di DataSet da XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [Caricamento di un DataSet da XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [Il caricamento delle informazioni dello Schema di DataSet da XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [Uso di XML in un set di dati](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [Oggetti DataSet, DataTable e DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)

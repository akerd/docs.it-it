---
title: Oggetti DbProviderFactory
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2a8e2640-3a49-42a1-a3a9-b43026907ae1
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0e8c6310b8ce164a60541dae030ce603bccd372e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="dbproviderfactories"></a>Oggetti DbProviderFactory
Lo spazio dei nomi <xref:System.Data.Common> fornisce classi per la creazione di istanze di <xref:System.Data.Common.DbProviderFactory> per l'uso di origini dati specifiche. Quando si crea un'istanza di <xref:System.Data.Common.DbProviderFactory> e si passano le informazioni sul provider di dati, `DbProviderFactory` è in grado di determinare l'oggetto connessione corretto, fortemente tipizzato, da restituire in base alle informazioni fornite.  
  
 A partire dalla versione 4 di .NET Framework, i provider di dati come <xref:System.Data.Odbc>, <xref:System.Data.OleDb>, <xref:System.Data.SqlClient> e <xref:System.Data.OracleClient>, a differenza dei provider personalizzati, non vengono più elencati nel file machine.config.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Cenni preliminari sul modello di factory](../../../../docs/framework/data/adonet/factory-model-overview.md)  
 Viene fornita una panoramica del modello di progettazione e dell'interfaccia di programmazione di factory.  
  
 [Recupero di un oggetto DbProviderFactory](../../../../docs/framework/data/adonet/obtaining-a-dbproviderfactory.md)  
 Viene illustrato come elencare i provider di dati installati e creare un oggetto <xref:System.Data.Common.DbConnection> da `DbProviderFactory`.  
  
 [DbConnection, DbCommand e DbException](../../../../docs/framework/data/adonet/dbconnection-dbcommand-and-dbexception.md)  
 Viene illustrato come creare oggetti <xref:System.Data.Common.DbCommand> e <xref:System.Data.Common.DbDataReader> nonché come gestire gli errori di dati tramite <xref:System.Data.Common.DbException>.  
  
 [Modifica di dati con un DbDataAdapter](../../../../docs/framework/data/adonet/modifying-data-with-a-dbdataadapter.md)  
 Viene illustrato come usare <xref:System.Data.Common.DbCommandBuilder> con <xref:System.Data.Common.DbDataAdapter> per recuperare e modificare dati.  
  
## <a name="see-also"></a>Vedere anche  
 [Recupero e modifica di dati in ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)

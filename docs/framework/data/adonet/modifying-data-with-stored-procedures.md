---
title: Modifica di dati con stored procedure
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 7d8e9a46-1af6-4a02-bf61-969d77ae07e0
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 1f8f0c37e5ac84d878f1d443d2bcc1e8ded099a6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="modifying-data-with-stored-procedures"></a>Modifica di dati con stored procedure
Le stored procedure possono accettare dati come parametri di input e possono restituire dati come parametri di output, set di risultati o valori restituiti. Nell'esempio seguente vengono illustrati l'invio e la ricezione di parametri di input, parametri di output e valori restituiti in ADO.NET. Viene inserito un nuovo record in una tabella in cui la colonna della chiave primaria è una colonna Identity di un database SQL Server.  
  
> [!NOTE]
>  Se si usano stored procedure SQL Server per modificare o eliminare dati tramite <xref:System.Data.SqlClient.SqlDataAdapter>, assicurarsi di non usare SET NOCOUNT ON nella definizione della stored procedure. Con tale comando il totale restituito delle righe interessate è pari a zero e tale situazione viene interpretata da `DataAdapter` come un conflitto di concorrenza. In questo caso verrà generata un'eccezione <xref:System.Data.DBConcurrencyException>.  
  
## <a name="example"></a>Esempio  
 L'esempio utilizza la stored procedure seguente per inserire una nuova categoria nella **Northwind** **categorie** tabella. La stored procedure accetta il valore di **CategoryName** funzione colonna come un parametro di input e l'utilizzo di SCOPE_IDENTITY () per recuperare il nuovo valore del campo di identità, **CategoryID**e come restituirlo in un parametro di output. Utilizza l'istruzione RETURN di @@ROWCOUNT funzione per restituire il numero di righe inserite.  
  
```  
CREATE PROCEDURE dbo.InsertCategory  
  @CategoryName nvarchar(15),  
  @Identity int OUT  
AS  
INSERT INTO Categories (CategoryName) VALUES(@CategoryName)  
SET @Identity = SCOPE_IDENTITY()  
RETURN @@ROWCOUNT  
```  
  
 Nell'esempio di codice seguente viene usata la stored procedure `InsertCategory` sopra indicata come origine per <xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A> di <xref:System.Data.SqlClient.SqlDataAdapter>. Il parametro di output `@Identity` e il valore restituito verranno riflessi in <xref:System.Data.DataSet> dopo l'inserimento del record nel database quando viene chiamato il metodo `Update` di <xref:System.Data.SqlClient.SqlDataAdapter>. Nel codice viene inoltre recuperato il valore restituito:  
  
> [!NOTE]
>  Quando si utilizza il <xref:System.Data.OleDb.OleDbDataAdapter>, è necessario specificare i parametri con un <xref:System.Data.ParameterDirection> di **ReturnValue** prima degli altri parametri.  
  
 [!code-csharp[DataWorks SqlClient.SprocIdentityReturn#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.SprocIdentityReturn/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.SprocIdentityReturn#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.SprocIdentityReturn/VB/source.vb#1)]  
  
## <a name="see-also"></a>Vedere anche  
 [Recupero e modifica di dati in ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [DataAdapter e DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [Esegue un comando](../../../../docs/framework/data/adonet/executing-a-command.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)

---
title: MULTISET (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eb90a377-e47a-43a5-b308-e993b6d611e6
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: e72605225d214ccd2283aaae3f0c2071ceb92d91
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="multiset-entity-sql"></a>MULTISET (Entity SQL)
Crea un'istanza di un multiset da un elenco di valori. Tutti i valori nel costruttore MULTISET devono essere di un tipo `T`compatibile. Non sono consentiti costruttori multiset vuoti.  
  
## <a name="syntax"></a>Sintassi  
  
```  
MULTISET ( expression [{, expression }] )  
or  
{ expression [{, expression }] }  
```  
  
## <a name="arguments"></a>Argomenti  
 `expression`  
 Qualsiasi elenco valido di valori.  
  
## <a name="return-value"></a>Valore restituito  
 Una raccolta di tipo MULTISET\<T >.  
  
## <a name="remarks"></a>Note  
 In[!INCLUDE[esql](../../../../../../includes/esql-md.md)] sono disponibili tre tipi di costruttori, ovvero costruttori di riga, costruttori di oggetti e costruttori di raccolte o multiset. Per ulteriori informazioni, vedere [la costruzione di tipi](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).  
  
 Il costruttore multiset crea un'istanza di un multiset da un elenco di valori. Tutti i valori nel costruttore devono essere di un tipo compatibile.  
  
 L'espressione seguente consente ad esempio di creare un multiset di valori interi.  
  
 `MULTISET(1, 2, 3)`  
  
 `{1, 2, 3}`  
  
> [!NOTE]
>  I valori letterali di multiset annidati sono supportati solo quando un multiset di wrapping contiene un solo elemento multiset, ad esempio `{{1, 2, 3}}`. Quando il multiset di wrapping contiene più elementi multiset, ad esempio `{{1, 2}, {3, 4}}`, non sono supportati valori letterali di multiset annidati.  
  
## <a name="example"></a>Esempio  
 Nella query Entity SQL seguente viene usato l'operatore MULTISET per creare un'istanza di un multiset da un elenco di valori. La query è basata sul modello Sales di AdventureWorks. Per compilare ed eseguire questa query, effettuare le operazioni seguenti:  
  
1.  Seguire la procedura indicata in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#MULTISET](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#multiset)]  
  
## <a name="see-also"></a>Vedere anche  
 [Costruzione di tipi](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md)  
 [Riferimento a Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)

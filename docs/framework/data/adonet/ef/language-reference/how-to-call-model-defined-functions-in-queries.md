---
title: 'Procedura: chiamare funzioni definite dal modello in query'
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
ms.assetid: 6c804e4d-f348-4afd-9f63-d3f0f24bc6a9
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 179c00def6b5a810806d536a8728cbbc544b1084
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-call-model-defined-functions-in-queries"></a>Procedura: chiamare funzioni definite dal modello in query
In questo argomento viene descritto come chiamare funzioni definite nel modello concettuale dall'interno di query [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)].  
  
 La procedura descritta di seguito fornisce una struttura di alto livello per la chiamata di una funzione definita dal modello dall'interno di una query [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)]. Nell'esempio che segue vengono forniti dettagli aggiuntivi sui passaggi della procedura. In questa procedura si presuppone che sia stata definita una funzione nel modello concettuale. Per ulteriori informazioni, vedere [procedura: definire le funzioni personalizzate nel modello concettuale](http://msdn.microsoft.com/en-us/0dad7b8b-58f6-4271-b238-f34810d68e5f).  
  
### <a name="to-call-a-function-defined-in-the-conceptual-model"></a>Per chiamare una funzione definita nel modello concettuale  
  
1.  Aggiungere un metodo CLR (Common Language Runtime) all'applicazione che esegue il mapping alla funzione definita nel modello concettuale. Per eseguire il mapping del metodo, è necessario applicare un oggetto <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> al metodo. Si noti che i parametri <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> e <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> dell'attributo sono rispettivamente il nome dello spazio dei nomi del modello concettuale e il nome della funzione nel modello concettuale. La risoluzione del nome della funzione per LINQ rileva la distinzione tra maiuscole e minuscole.  
  
2.  Chiamare la funzione in una query [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)].  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene mostrato come chiamare una funzione definita nel modello concettuale dall'interno di una query [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)]. Nell'esempio viene usato il modello School. Per informazioni sul modello School, vedere [la creazione di Database di esempio School](http://msdn.microsoft.com/en-us/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0) e [la generazione di File con estensione edmx dell'istituto di istruzione](http://msdn.microsoft.com/en-us/c48b3907-a8be-4fe6-884c-e95af1852758).  
  
 La funzione del modello concettuale seguente restituisce il numero di anni di servizio di un docente. Per informazioni sull'aggiunta di funzione a un modello concettuale, vedere [procedura: definire le funzioni personalizzate nel modello concettuale](http://msdn.microsoft.com/en-us/0dad7b8b-58f6-4271-b238-f34810d68e5f).)  
  
 [!code-xml[DP ConceptualModelFunctions#1](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp conceptualmodelfunctions/xml/school.edmx#1)]
  
## <a name="example"></a>Esempio  
 Successivamente aggiungere il metodo seguente all'applicazione e usare un oggetto <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> per eseguirne il mapping alla funzione del modello concettuale:  
  
 [!code-csharp[DP ConceptualModelFunctions#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp conceptualmodelfunctions/cs/program.cs#2)]
 [!code-vb[DP ConceptualModelFunctions#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp conceptualmodelfunctions/vb/module1.vb#2)]  
  
## <a name="example"></a>Esempio  
 A questo punto è possibile chiamare la funzione del modello concettuale dall'interno di una query [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)]. Nel codice seguente viene chiamato il metodo per visualizzare tutti i docenti assunti da più di dieci anni:  
  
 [!code-csharp[DP ConceptualModelFunctions#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp conceptualmodelfunctions/cs/program.cs#3)]
 [!code-vb[DP ConceptualModelFunctions#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp conceptualmodelfunctions/vb/module1.vb#3)]  
  
## <a name="see-also"></a>Vedere anche  
 [Cenni preliminari sui file con estensione edmx](http://msdn.microsoft.com/en-us/f4c8e7ce-1db6-417e-9759-15f8b55155d4)  
 [Query in LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)  
 [Chiamata di funzioni in query LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/calling-functions-in-linq-to-entities-queries.md)  
 [Procedura: chiamare funzioni definite dal modello come metodi di oggetti](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-model-defined-functions-as-object-methods.md)

---
title: Matrici tipizzate in modo implicito (Guida per programmatori C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- arrays [C#], implicity-typed
- implicitly-typed arrays [C#]
- C# language, implicitly typed arrays
ms.assetid: e05be95c-6732-403d-ae42-b35f057cbbea
caps.latest.revision: "13"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f6e60ff600a04dab47e8b0ed52dda00441e17f25
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="implicitly-typed-arrays-c-programming-guide"></a>Matrici tipizzate in modo implicito (Guida per programmatori C#)
È possibile creare una matrice tipizzata in modo implicito in cui il tipo dell'istanza della matrice viene derivato tramite inferenza dagli elementi specificati nell'inizializzatore di matrice. Le regole per qualsiasi variabile tipizzata in modo implicito si applicano anche alle matrici tipizzate in modo implicito. Per altre informazioni, vedere [Variabili locali tipizzate in modo implicito](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).  
  
 Le matrici tipizzate in modo implicito vengono in genere usate nelle espressioni di query insieme ai tipi anonimi e agli inizializzatori di oggetto e di raccolta.  
  
 Gli esempi seguenti illustrano come creare una matrice tipizzata in modo implicito:  
  
 [!code-csharp[csProgGuideLINQ#37](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-arrays_1.cs)]  
  
 Nell'esempio precedente si noti che con le matrici tipizzate in modo implicito, non vengono usate parentesi quadre sul lato sinistro dell'istruzione di inizializzazione. Si noti anche che le matrici di matrici vengono inizializzate usando `new []` esattamente come le matrici unidimensionali.  
  
## <a name="implicitly-typed-arrays-in-object-initializers"></a>Matrici tipizzate in modo implicito negli inizializzatori di oggetto  
 Quando si crea un tipo anonimo che contiene una matrice, la matrice deve essere tipizzata in modo implicito nell'inizializzatore di oggetto del tipo. Nell'esempio seguente `contacts` è una matrice tipizzata in modo implicito di tipi anonimi, ognuno dei quali contiene una matrice denominata `PhoneNumbers`. Si noti che la parola chiave `var` non viene usata negli inizializzatori di oggetto.  
  
 [!code-csharp[csProgGuideLINQ#38](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-arrays_2.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Variabili locali tipizzate in modo implicito](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)  
 [Array](../../../csharp/programming-guide/arrays/index.md)  
 [Tipi anonimi](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)  
 [Inizializzatori di oggetto e di raccolta](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)  
 [var](../../../csharp/language-reference/keywords/var.md)  
 [Espressioni di query LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)

---
title: 'Procedura: accedere a un membro mediante un puntatore (Guida per programmatori C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: pointers [C#], member access
ms.assetid: 1e998498-8c85-4a78-8ce2-4d8c20f08342
caps.latest.revision: "16"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 622d9910b09c9197b7f4ccd5e54e2675fbbbbccb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-access-a-member-with-a-pointer-c-programming-guide"></a>Procedura: accedere a un membro mediante un puntatore (Guida per programmatori C#)
Per accedere a un membro di uno struct dichiarato in un contesto non sicuro, è possibile usare l'operatore di accesso ai membri, come illustrato nell'esempio seguente in cui `p` è un puntatore a uno [struct](../../../csharp/language-reference/keywords/struct.md) che contiene un membro `x`.  
  
```  
CoOrds* p = &home;  
p -> x = 25; //member access operator ->  
```  
  
## <a name="example"></a>Esempio  
 In questo esempio uno [struct](../../../csharp/language-reference/keywords/struct.md), `CoOrds`, che contiene le due coordinate `x` e `y` viene dichiarato e ne viene creata un'istanza. Usando l'operatore di accesso ai membri `->` e un puntatore all'istanza di `home`, vengono assegnati i valori a `x` e `y`.  
  
> [!NOTE]
>  Si noti che l'espressione `p->x` è equivalente all'espressione `(*p).x` e che è possibile ottenere lo stesso risultato usando una delle due espressioni.  
  
 [!code-csharp[csProgGuidePointers#9](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-a-member-with-a-pointer_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#10](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-a-member-with-a-pointer_2.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Espressioni puntatore](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [Tipi di puntatori](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [Tipi](../../../csharp/language-reference/keywords/types.md)  
 [unsafe](../../../csharp/language-reference/keywords/unsafe.md)  
 [Istruzione fixed](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)

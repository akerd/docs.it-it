---
title: "Accesso di membro condiviso tramite un'istanza; l'espressione di qualificazione non verrà valutata"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42025
- BC42025
helpviewer_keywords: BC42025
ms.assetid: db3337e5-c349-42bf-86df-d9c1e00952a5
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bcf3c37852e73464eec612e9e1d458ca707342e2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="access-of-shared-member-through-an-instance-qualifying-expression-will-not-be-evaluated"></a>Accesso di membro condiviso tramite un'istanza; l'espressione di qualificazione non verrà valutata
Una variabile di istanza di una classe o struttura viene utilizzata per accedere a un `Shared` variabile, proprietà, routine o evento definito in quella classe o struttura. Questo avviso può verificarsi anche se una variabile di istanza viene utilizzata per accedere a un membro condiviso in modo implicito di una classe o struttura, ad esempio una costante, enumerazione o una classe annidata o struttura.  
  
 Lo scopo di un membro di condivisione consiste nel creare una sola copia di tale membro e renderla disponibile per ogni istanza della classe o struttura in cui viene dichiarato. È coerenza con lo scopo per accedere a un `Shared` membro tramite il nome della relativa classe o struttura, anziché tramite una variabile che contiene una singola istanza di quella classe o struttura.  
  
 L'accesso a un `Shared` membro tramite una variabile di istanza può rendere più difficile da comprendere nascondendo il fatto che il membro è il codice `Shared`. Inoltre, se tale accesso è parte di un'espressione che esegue altre operazioni, ad esempio un `Function` procedure che restituisce un'istanza del membro condiviso, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] ignora l'espressione e tutte le altre azioni che altrimenti verrebbero eseguite.  
  
 Per ulteriori informazioni e un esempio, vedere [Shared](../../../visual-basic/language-reference/modifiers/shared.md).  
  
 Per impostazione predefinita, si tratta di un messaggio di avviso. Per ulteriori informazioni su come nascondere gli avvisi o considerarli come errori, vedere [configurazione degli avvisi in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **ID errore:** BC42025  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Utilizzare il nome della classe o struttura che definisce il `Shared` membro per l'accesso, come illustrato nell'esempio seguente.  
  
```vb  
Public Class testClass  
    Public Shared Sub sayHello()  
        MsgBox("Hello")  
    End Sub  
End Class  
  
Module testModule  
    Public Sub Main()  
        ' Access a shared method through an instance variable.  
        ' This generates a warning.  
        Dim tc As New testClass  
        tc.sayHello()  
  
        ' Access a shared method by using the class name.  
        ' This does not generate a warning.  
        testClass.sayHello()  
    End Sub  
End Module  
```  
  
> [!NOTE]
>  Quando due elementi di programmazione presentano lo stesso nome, prestare attenzione agli effetti dell'ambito. Nell'esempio precedente, se si dichiara un'istanza tramite `Dim testClass as testClass = Nothing`, il compilatore considera una chiamata a `testClass.sayHello()` come si verifica l'accesso al metodo tramite il nome della classe e alcun messaggio di avviso.  
  
## <a name="see-also"></a>Vedere anche  
 [Shared](../../../visual-basic/language-reference/modifiers/shared.md)  
 [Ambito in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)

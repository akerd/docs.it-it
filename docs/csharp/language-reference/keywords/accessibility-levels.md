---
title: "Livelli di accessibilità (Riferimenti per C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- access modifiers [C#], accessibility levels
- accessibility levels
ms.assetid: dc083921-0073-413e-8936-a613e8bb7df4
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 77124554d7a0b38414e154e024aceddbfffcfbd4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="accessibility-levels-c-reference"></a>Livelli di accessibilità (Riferimenti per C#)
Usano i modificatori di accesso [public](../../../csharp/language-reference/keywords/public.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md) o [private](../../../csharp/language-reference/keywords/private.md) per specificare uno dei livelli seguenti di accessibilità dichiarata per i membri.  
  
|Accessibilità dichiarata|Significato|  
|----------------------------|-------------|  
|`public`|L'accesso non è limitato.|  
|`protected`|L'accesso è limitato alla classe o ai tipi derivati dalla classe che li contiene.|  
|`internal`|L'accesso è limitato all'assembly corrente.|  
|`protected internal`|L'accesso è limitato all'assembly corrente o ai tipi derivati dalla classe che li contiene.|  
|`private`|L'accesso è limitato al tipo contenitore.|  
|`private protected`|Accesso è limitato a una classe o i tipi derivati dalla classe di appartenenza all'interno dell'assembly corrente.|  
  
 Solo un modificatore di accesso è consentito per un membro o un tipo, tranne quando si utilizza il `protected internal` o `private protected` combinazioni.  
  
 I modificatori di accesso non sono consentiti negli spazi dei nomi. Gli spazi dei nomi non hanno restrizioni di accesso.  
  
 A seconda del contesto in cui si verifica una dichiarazione di membro, sono consentite solo determinate accessibilità dichiarate. Se non è specificato nessun modificatore di accesso in una dichiarazione di membro, viene usata un'accessibilità predefinita.  
  
 I tipi di primo livello, che non sono annidati in altri tipi, possono avere solo l'accessibilità `internal` o `public`. L'accessibilità predefinita per questi tipi è `internal`.  
  
 I tipi annidati, che sono membri di altri tipi, possono avere accessibilità dichiarate come indicato nella tabella seguente.  
  
|Membri di|Accessibilità predefinita del membro|Accessibilità dichiarate e consentite del membro|  
|----------------|----------------------------------|--------------------------------------------------|  
|`enum`|`public`|Nessuno|  
|`class`|`private`|`public`<br /><br /> `protected`<br /><br /> `internal`<br /><br /> `private`<br /><br /> `protected internal` <br /><br />`private protected`|  
|`interface`|`public`|Nessuno|  
|`struct`|`private`|`public`<br /><br /> `internal`<br /><br /> `private`|  
  
 L'accessibilità di un tipo annidato dipende dal relativo [dominio di accessibilità](../../../csharp/language-reference/keywords/accessibility-domain.md), che è determinato dall'accessibilità dichiarata del membro e dal dominio di accessibilità del tipo contenitore. Tuttavia il dominio di accessibilità di un tipo annidato non può essere superiore a quello del tipo che lo contiene.  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Parole chiave di C#](../../../csharp/language-reference/keywords/index.md)  
 [Modificatori di accesso](../../../csharp/language-reference/keywords/access-modifiers.md)  
 [Dominio di accessibilità](../../../csharp/language-reference/keywords/accessibility-domain.md)  
 [Restrizioni relative all'uso dei livelli di accessibilità](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md)  
 [Modificatori di accesso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [public](../../../csharp/language-reference/keywords/public.md)  
 [private](../../../csharp/language-reference/keywords/private.md)  
 [protected](../../../csharp/language-reference/keywords/protected.md)  
 [internal](../../../csharp/language-reference/keywords/internal.md)

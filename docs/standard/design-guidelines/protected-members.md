---
title: Membri protetti
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- members [.NET Framework], protected
- protected members
- classes [.NET Framework], unsealed
- classes [.NET Framework], protected members
- unsealed classes
- customizing class behavior
ms.assetid: aa0b58ee-3956-494d-ab48-471ae5db8740
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7c3aacd0f08641c01200f0b1791a78413a306590
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="protected-members"></a>Membri protetti
Membri protetti da soli non forniscono alcun estendibilità, ma può rendere più potente di estendibilità tramite la creazione di sottoclassi. Possono essere utilizzati per esporre le opzioni di personalizzazione avanzate senza inutilmente complica l'interfaccia pubblica principale.  
  
 Finestre di progettazione Framework necessario prestare attenzione ai membri protetti perché il nome "protetto" può concedere a un falso senso di sicurezza. Chiunque sia in grado di sottoclasse di una classe non sealed e i membri di accesso protetto e pertanto le stesse difensivo procedure di codifica utilizzati per i membri pubblici applicano ai membri protetti.  
  
 **Provare a ✓** utilizzando membri per la personalizzazione avanzata protetti.  
  
 **✓ SI** trattare i membri protetti nelle classi non sealed come public allo scopo di analisi di sicurezza, documentazione e compatibilità.  
  
 Chiunque può ereditare da una classe e accedere ai membri protetti.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche  
 [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)  
 [Progettazione di estendibilità](../../../docs/standard/design-guidelines/designing-for-extensibility.md)

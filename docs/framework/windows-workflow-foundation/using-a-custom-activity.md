---
title: "Utilizzo di un'attività personalizzata"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8f356419-681a-4175-ae93-878eee970249
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cea0e819c79550b27a71957f6d8c2c9badfef7c0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="using-a-custom-activity"></a>Utilizzo di un'attività personalizzata
Le attività che derivano da <xref:System.Activities.Activity> o le relative sottoclassi possono essere composte in flussi di lavoro più grandi o create direttamente nel codice. In questo argomento viene descritto come usare le attività personalizzate nei flussi di lavoro creati nel codice o nella finestra di progettazione.  
  
> [!NOTE]
>  Attività personalizzate possono essere usate nello stesso progetto in cui sono definiti, purché sia l'attività personalizzata e l'attività che usa vengono compilate (vale a dire caricati da un tipo di istanza generato dal processo di compilazione) se l'attività di riferimento viene caricato in modo dinamico (ad esempio usando ActivityXAMLServices), quindi l'assembly di riferimento deve essere inserito in un progetto diverso o il codice XAML generato da progettazione deve essere modificato manualmente per abilitare questa opzione.  
  
#### <a name="using-a-custom-activity-to-a-workflow-project"></a>Uso di un'attività personalizzata per un progetto di flusso di lavoro  
  
1.  Aggiungere un riferimento dal progetto host al progetto della libreria di attività contenente l'attività personalizzata.  
  
2.  Compilare la soluzione.  
  
3.  Per usare l'attività personalizzata nella finestra di progettazione, individuare l'attività personalizzata nella casella degli strumenti e trascinare l'attività nell'area di progettazione.  
  
4.  Per usare l'attività personalizzata nel codice, aggiungere un'istruzione Using che fa riferimento al progetto di attività personalizzata e passare una nuova istanza dell'attività a <xref:System.Activities.WorkflowInvoker.Invoke%2A>.

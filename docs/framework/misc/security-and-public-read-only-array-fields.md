---
title: Sicurezza e campi di matrice pubblici di sola lettura
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: security [.NET Framework], public read-only array fields
ms.assetid: 3df28dee-2a9f-40ff-9852-bfdbe59c27f3
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ae2e9a7dd9e08344c254b52c7139c6d1dd2776a3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="security-and-public-read-only-array-fields"></a>Sicurezza e campi di matrice pubblici di sola lettura
Non utilizzare mai i campi di matrice pubblici di sola lettura da librerie gestite per definire il comportamento del limite o la sicurezza delle applicazioni, poiché i campi di matrice pubblici di sola lettura possono essere modificati.  
  
## <a name="remarks"></a>Note  
 Alcune classi di .NET framework includono campi pubblici di sola lettura che contengono parametri limiti specifici della piattaforma.  Ad esempio, il <xref:System.IO.Path.InvalidPathChars> campo è una matrice che contiene i caratteri non consentiti in una stringa di percorso del file.  Numero di campi simili è presenti in .NET Framework.  
  
 I valori dei campi pubblici di sola lettura come <xref:System.IO.Path.InvalidPathChars> può essere modificato da codice che condivide il dominio dell'applicazione o il codice.  Utilizzare i campi di matrice pubblici di sola lettura simile al seguente per definire il comportamento del limite delle applicazioni non.  In caso contrario, codice dannoso può modificare le definizioni di limite e utilizzare il codice in modo imprevisto.  
  
 Nella versione 2.0 e versioni successive di .NET Framework, è necessario utilizzare metodi che restituiscono una nuova matrice anziché utilizzare i campi di matrice pubblici.  Ad esempio, anziché utilizzare il <xref:System.IO.Path.InvalidPathChars> campo, è consigliabile utilizzare il <xref:System.IO.Path.GetInvalidPathChars%2A> metodo.  
  
 Si noti che i tipi .NET Framework non utilizzano i campi pubblici per definire i tipi di limite internamente.  .NET Framework utilizza invece campi privati separati.  Modifica dei valori di questi campi pubblici non modifica il comportamento dei tipi di .NET Framework.  
  
## <a name="see-also"></a>Vedere anche  
 [Linee guida per la generazione di codice sicuro](../../../docs/standard/security/secure-coding-guidelines.md)

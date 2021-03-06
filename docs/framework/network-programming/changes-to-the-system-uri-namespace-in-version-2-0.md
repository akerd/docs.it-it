---
title: Modifiche apportate allo spazio dei nomi System.Uri nella versione 2.0
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 35883fe9-2d09-4d8b-80ca-cf23a941e459
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 906abbcbd3ec00e76d8c183f61828fb5135d9154
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="changes-to-the-systemuri-namespace-in-version-20"></a>Modifiche apportate allo spazio dei nomi System.Uri nella versione 2.0
Alla classe <xref:System.Uri?displayProperty=nameWithType> sono state apportate alcune modifiche allo scopo di correggerne il comportamento nonché di aumentarne le possibilità d'utilizzo e il livello di sicurezza.  
  
## <a name="obsolete-and-deprecated-members"></a>Membri obsoleti e deprecati  
 Costruttori:  
  
-   Tutti i costruttori che accettano `dontEscape` come parametro.  
  
 Metodi:  
  
-   <xref:System.Uri.CheckSecurity%2A>  
  
-   <xref:System.Uri.Escape%2A>  
  
-   <xref:System.Uri.Canonicalize%2A>  
  
-   <xref:System.Uri.Parse%2A>  
  
-   <xref:System.Uri.IsReservedCharacter%2A>  
  
-   <xref:System.Uri.IsBadFileSystemCharacter%2A>  
  
-   <xref:System.Uri.IsExcludedCharacter%2A>  
  
-   <xref:System.Uri.EscapeString%2A>  
  
## <a name="changes"></a>Modifiche  
  
-   Nel caso di schemi URI in cui è notoriamente assente una parte relativa a query (file, ftp e altri), il punto interrogativo (?) deve essere sempre preceduto da un carattere di escape e non viene considerato come inizio di una parte <xref:System.Uri.Query%2A>.  
  
-   Per gli URI di file impliciti, nel formato c:\directory\file@name.txt, il cancelletto (#) viene sempre preceduto da un carattere di escape tranne nei casi in cui è esplicitamente richiesta l'assenza totale di caratteri di escape oppure <xref:System.Uri.LocalPath%2A> è `true`.  
  
-   Il supporto per nomi host UNC non è più disponibile. Per la rappresentazione dei nomi host internazionali è ora stata adottata la specifica IDN.  
  
-   <xref:System.Uri.LocalPath%2A> restituisce sempre una stringa senza alcun carattere di escape.  
  
-   <xref:System.Uri.ToString%2A> non rimuove l'eventuale carattere di escape che precede il segno di percentuale (%), il punto interrogativo (?) o il cancelletto (#).  
  
-   <xref:System.Uri.Equals%2A> include ora la parte <xref:System.Uri.Query%2A> nel controllo di uguaglianza.  
  
-   Gli operatori == e != sono sottoposti a override e collegati al metodo <xref:System.Uri.Equals%2A>.  
  
-   <xref:System.Uri.IsLoopback%2A> è ora in grado di generare risultati coerenti.  
  
-   L'URI `file:///path` non viene più convertito in file://path.  
  
-   Il cancelletto (#) viene ora riconosciuto come carattere di terminazione di nome host. In altre parole, http://contoso.com#frammento viene ora convertito in http://contoso.com/#frammento.  
  
-   È stato corretto un bug relativo alla combinazione di un URI di base con un frammento.  
  
-   È stato corretto un bug in <xref:System.Uri.HostNameType%2A>.  
  
-   È stato corretto un bug nell'analisi NNTP.  
  
-   Un URI nel formato HTTP:contoso.com genera ora un'eccezione di analisi.  
  
-   .NET Framework gestisce correttamente le informazioni utente in un URI.  
  
-   La compressione dei percorsi URI è stata corretta in modo da impedire a un URI interrotto di attraversare il file system al di sopra della radice.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Uri?displayProperty=nameWithType>

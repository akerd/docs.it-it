---
title: HTTP
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- protocols, HTTP
- sending data, HTTP
- HttpWebResponse class, sending and receiving data
- HTTP
- receiving data, HTTP
- application protocols, HTTP
- Internet, HTTP
- network resources, HTTP
- HTTP, about HTTP
- HttpWebRequest class, sending and receiving data
ms.assetid: 985fe5d8-eb71-4024-b361-41fbdc1618d8
caps.latest.revision: "10"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 701ff252380ef93dbe3668c8aca73f08a8425d6b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="http"></a>HTTP
.NET Framework offre il supporto completo per il protocollo HTTP, che costituisce la maggior parte di tutto il traffico Internet, con la <xref:System.Net.HttpWebRequest> e <xref:System.Net.HttpWebResponse> classi. Queste classi, derivate da <xref:System.Net.WebRequest> e <xref:System.Net.WebResponse>, vengono restituite per impostazione predefinita ogni volta che il metodo statico <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> rileva un URI che inizia con "http" o "https". Nella maggior parte dei casi, le classi **WebRequest** e **WebResponse** rendono disponibile tutto ciò che serve per eseguire la richiesta. Se tuttavia è necessario accedere alle funzionalità specifiche di HTTP esposte come proprietà, è possibile eseguire il cast di tipo di queste classi su **HttpWebRequest** o **HttpWebResponse**.  
  
 **HttpWebRequest** e **HttpWebResponse** incapsulano una transazione standard di richiesta e risposta HTTP e forniscono l'accesso alle intestazioni HTTP comuni. Queste classi supportano anche la maggior parte delle funzionalità HTTP 1.1, tra cui pipelining, l'invio e ricezione di dati in blocchi, autenticazione, preautenticazione, crittografia, supporto di proxy, convalida del certificato del server e gestione della connessione. Le intestazioni personalizzate e le intestazioni non fornite tramite proprietà possono essere archiviate e sono accessibili tramite la proprietà **Headers**.  
  
 **HttpWebRequest** è la classe predefinita usata da **WebRequest** e non deve essere registrata prima di poter passare un URI al metodo **WebRequest**.  
  
 È possibile configurare l'applicazione in modo che segua automaticamente i reindirizzamenti HTTP impostando la proprietà <xref:System.Net.HttpWebRequest.AllowAutoRedirect%2A> su **true** (impostazione predefinita). L'applicazione reindirizzerà le richieste e la proprietà <xref:System.Net.HttpWebResponse.ResponseUri%2A> di **HttpWebResponse** conterrà la risorsa Web effettiva che ha risposto alla richiesta. Se si imposta **AllowAutoRedirect** su **false**, l'applicazione deve essere in grado di gestire i reindirizzamenti come errori del protocollo HTTP.  
  
 Le applicazioni ricevono gli errori del protocollo HTTP intercettando una <xref:System.Net.WebException> con la proprietà <xref:System.Net.WebException.Status%2A> impostata <xref:System.Net.WebExceptionStatus>. La proprietà <xref:System.Net.WebException.Response%2A> contiene l'oggetto **WebResponse** inviato dal server e indica l'errore HTTP effettivo rilevato.  
  
## <a name="see-also"></a>Vedere anche  
 [Accesso a Internet con un proxy](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)  
 [Uso di protocolli applicativi](../../../docs/framework/network-programming/using-application-protocols.md)  
 [Procedura: Accedere a proprietà specifiche di HTTP](../../../docs/framework/network-programming/how-to-access-http-specific-properties.md)

---
title: '&lt;proxy&gt; elemento (impostazioni di rete)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/proxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#proxy
helpviewer_keywords:
- <proxy> element
- proxy element
ms.assetid: 37a548d8-fade-4ac5-82ec-b49b6c6cb22a
caps.latest.revision: "20"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 7178527f369c698b0ab53aa41cb28dd0126436b3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltproxygt-element-network-settings"></a>&lt;proxy&gt; elemento (impostazioni di rete)
Definisce un server proxy.  
  
 \<configuration>  
\<System.NET >  
\<defaultProxy >  
\<proxy >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<proxy
  autoDetect="true|false|unspecified" 
  bypassonlocal="true|false|unspecified"
  proxyaddress="uriString"
  scriptLocation="uriString"
  usesystemdefault="true|false|unspecified"
/>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|**Attributo**|**Descrizione**|  
|-------------------|---------------------|  
|`autoDetect`|Specifica se il proxy viene rilevato automaticamente. Il valore predefinito è `unspecified`.|  
|`bypassonlocal`|Specifica se il proxy viene ignorato per le risorse locali. Le risorse locali includono il server locale (http://localhost, http://loopback o http://127.0.0.1) e un URI senza punto (http://webserver). Il valore predefinito è `unspecified`.|  
|`proxyaddress`|Specifica l'URI del proxy da utilizzare.|  
|`scriptLocation`|Specifica il percorso dello script di configurazione.|  
|`usesystemdefault`|Specifica se utilizzare le impostazioni proxy di Internet Explorer. Se impostato su `true`, gli attributi successivi sostituiranno le impostazioni proxy di Internet Explorer. Il valore predefinito è `unspecified`.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|**Elemento**|**Descrizione**|  
|-----------------|---------------------|  
|[defaultProxy](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|Configura il server proxy Hypertext Transfer Protocol (HTTP).|  
  
## <a name="text-value"></a>Valore di testo  
  
## <a name="remarks"></a>Note  
 Il `proxy` elemento definisce un server proxy per un'applicazione. Se questo elemento è mancano dal file di configurazione, .NET Framework utilizzerà le impostazioni del proxy in Internet Explorer.  
  
 Il valore per il `proxyaddress` attributo deve essere un formato corretto indicatore URI (Uniform Resource).  
  
 Il `scriptLocation` attributo fa riferimento per il rilevamento automatico proxy script di configurazione. Il <xref:System.Net.WebProxy> classe tenterà di individuare uno script di configurazione (in genere denominato WPAD) quando il **utilizzare script di configurazione automatica** opzione è selezionata in Internet Explorer.  
  
 Utilizzare il `usesystemdefault` attributo per le applicazioni .NET Framework versione 1.1 che esegue la migrazione alla versione 2.0.  
  
 Viene generata un'eccezione se il `proxyaddress` attributo specifica un proxy predefinito non valido. La proprietà <xref:System.Exception.InnerException%2A> nell'eccezione dovrebbe contenere altre informazioni sulla causa principale dell'errore.  
  
## <a name="configuration-files"></a>File di configurazione  
 Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente usa le impostazioni predefinite del proxy di Internet Explorer, specifica l'indirizzo del proxy e ignora il proxy per l'accesso locale.  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        proxyaddress="http://192.168.1.10:3128"  
        bypassonlocal="true"  
      />  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Net.WebProxy?displayProperty=nameWithType>  
 [Schema delle impostazioni di rete](../../../../../docs/framework/configure-apps/file-schema/network/index.md)

---
title: "Novità &#39; s New in Windows Communication Foundation 4.5"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF [WCF], what's new
- Windows Communication Foundation [WCF], what's new
ms.assetid: 7e93fe73-af93-46b5-9f63-32f761ee40cf
caps.latest.revision: "35"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 362578e6e8066c0490e692d0cd9d637b05bb1fa0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="what39s-new-in-windows-communication-foundation-45"></a>Novità &#39; s New in Windows Communication Foundation 4.5
In questo argomento vengono illustrate le nuove funzionalità di [!INCLUDE[indigo1](../../../includes/indigo1-md.md)].  
  
## <a name="wcf-simplification-features"></a>Funzionalità di semplificazione WCF  
 È stato svolto molto lavoro per rendere più semplici lo sviluppo e la gestione delle applicazioni WCF 4.5. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Funzionalità di semplificazione WCF](../../../docs/framework/wcf/wcf-simplification-features.md).  
  
### <a name="task-based-async-support"></a>Supporto asincrono basato su attività  
 Per impostazione predefinita, Aggiungi riferimento al servizio genera metodi di operazioni del servizio asincrono come risultato di attività. Questa operazione viene eseguita per i metodi sincroni e asincroni. Consente di chiamare le operazioni del servizio in modo asincrono utilizzando il nuovo modello di programmazione asincrono basato su attività. Quando si chiama il metodo proxy generato, WCF costruisce un oggetto attività per rappresentare un'operazione asincrona e restituisce l'attività all'utente. L'attività viene completata al completamento dell'operazione.  Quando si implementa un'operazione asincrona è possibile implementarla come operazione asincrona basata su attività. Per ulteriori informazioni, vedere [sincrono e alle operazioni asincrone](../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md).  
  
### <a name="simplified-generated-configuration-files"></a>File di configurazione generati semplificati  
 Quando si aggiunge un riferimento al servizio in Visual Studio o si utilizza lo strumento SvcUtil.exe, viene generato un file di configurazione client. Nelle versioni precedenti di WCF, questi file di configurazione contenevano il valore di ogni proprietà di associazione anche se il relativo valore è quello predefinito. In WCF 4.5 i file di configurazione generati contengono soltanto le proprietà di associazione che sono impostate su un valore non predefinito.  
  
 [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Funzionalità di semplificazione WCF](../../../docs/framework/wcf/wcf-simplification-features.md)  
  
### <a name="contract-first-development"></a>Sviluppo con priorità al contratto ("contract-first")  
 WCF supporta ora lo sviluppo con priorità al contratto ("contract-first"). Lo strumento svcutl.exe dispone di un'opzione /serviceContract che consente di generare contratti di servizio e dati da un documento WSDL.  
  
### <a name="add-service-reference-from-a-portable-subset-project"></a>Aggiungere un riferimento al servizio da un progetto di subset portabili  
 I progetti di subset portabili consentono ai programmatori di assembly .NET di gestire un unico albero di origine e di compilare il sistema supportando allo stesso tempo più piattaforme .NET (desktop, Silverlight, Windows Phone e XBOX). Solo i progetti di subset portabili fanno riferimento a librerie portabili .NET che rappresentano un assembly di .NET framework che può essere usato in qualsiasi piattaforma .NET. L'esperienza dello sviluppatore equivale all'aggiunta di un riferimento al servizio all'interno di qualsiasi altra applicazione client WCF. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Aggiungi riferimento al servizio in un progetto di Subset portabili](../../../docs/framework/wcf/add-service-reference-in-a-portable-subset-project.md).  
  
### <a name="aspnet-compatibility-mode-default-changed"></a>Modifica dell'impostazione predefinita della modalità di compatibilità ASP.NET  
 WCF fornisce la modalità di compatibilità ASP.NET per garantire agli sviluppatori l'accesso completo alle funzionalità nella pipeline HTTP ASP.NET in caso di scrittura di servizi WCF. Per utilizzare questa modalità, è necessario impostare il `aspNetCompatibilityEnabled` attributo su true nel [ \<serviceHostingEnvironment >](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) sezione di Web. config. Inoltre, la proprietà `RequirementsMode` dell'oggetto <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> di qualsiasi servizio in questo appDomain deve essere impostata sul campo <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed> o <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Required>. Per impostazione predefinita <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> è ora impostato su <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed>. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Novità di Windows Communication Foundation](../../../docs/framework/wcf/whats-new.md) e [servizi WCF e ASP.NET](../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).  
  
### <a name="new-transport-default-values"></a>Nuovi valori predefiniti di trasporto  
 Per semplificare la configurazione, sono stati modificati alcuni valori predefiniti della proprietà di trasporto. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Funzionalità di semplificazione WCF](../../../docs/framework/wcf/wcf-simplification-features.md).  
  
### <a name="xmldictionaryreaderquotas"></a>XmlDictionaryReaderQuotas  
 L'oggetto <xref:System.Xml.XmlDictionaryReaderQuotas> contiene i valori di quota configurabili per lettori di dizionari XML che limitano la quantità di memoria utilizzata da un codificatore durante la creazione di un messaggio. Anche se queste quote sono configurabili, i valori predefiniti sono stati modificati per ridurre la possibilità che uno sviluppatore debba impostarle in modo esplicito. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Funzionalità di semplificazione WCF](../../../docs/framework/wcf/wcf-simplification-features.md).  
  
### <a name="wcf-configuration-validation"></a>Convalida della configurazione WCF  
 Il processo di compilazione in Visual Studio include ora la convalida dei file di configurazione WCF per gli attributi definiti all'interno del progetto. Se la convalida non riesce, in Visual Studio viene visualizzato un elenco di errori o avvisi di convalida.  
  
### <a name="xml-editor-tooltips"></a>Descrizioni comandi dell'editor XML  
 Per consentire agli sviluppatori di servizi WCF nuovi ed esistenti di configurare i propri servizi, l'editor XML di Visual Studio offre ora le descrizioni comandi per ogni elemento di configurazione e le relative proprietà che fanno parte del file di configurazione del servizio.  
  
## <a name="streaming-improvements"></a>Miglioramenti del flusso  
 Aggiunta del supporto di un vero flusso asincrono in cui il lato di invio ora non blocca i thread se il lato di ricezione non sta leggendo o è lento nell'eseguire questa operazione, causando quindi l'aumento della scalabilità. Eliminazione della limitazione del buffering dei messaggi quando un client invia un messaggio trasmesso a un servizio WCF ospitato da IIS. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Funzionalità di semplificazione WCF](../../../docs/framework/wcf/wcf-simplification-features.md).  
  
## <a name="simplifying-exposing-an-endpoint-over-https-with-iis"></a>Semplificazione dell'esposizione di un endpoint tramite HTTPS con IIS  
 È stato aggiunto un mapping del protocollo HTTPS per semplificare l'esposizione di un endpoint tramite HTTPS. Per abilitare un endpoint HTTPS, assicurarsi che il sito Web disponga di un'associazione HTTPS e di un certificato SSL configurato e, successivamente, abilitare HTTPS per la directory virtuale che ospita il servizio. Se i metadati sono abilitati per il servizio, verranno esposti anche tramite HTTPS.  
  
## <a name="generating-a-single-wsdl-document"></a>Generazione di un singolo documento WSDL  
 Alcuni stack di elaborazione WSDL di terze parti non sono in grado di elaborare i documenti WSDL con dipendenze da altri documenti tramite un elemento xsd:import.  WCF ora consente di specificare che tutte le informazioni WSDL vengano restituite in un singolo documento. Per richiedere un singolo documento WSDL, aggiungere "? singleWSDL" all'URI quando richiede i metadati dal servizio.  
  
## <a name="websocket-support"></a>Supporto di WebSocket  
 WebSockets è una tecnologia che fornisce la vera comunicazione bidirezionale per le porte 80 e 443 con caratteristiche di prestazioni simili a TCP. Sono state aggiunte due nuove associazioni per supportare la comunicazione tramite un trasporto WebSocket, <xref:System.ServiceModel.NetHttpBinding> e <xref:System.ServiceModel.NetHttpsBinding>. Per ulteriori informazioni, vedere: [associazioni fornite dal sistema](../../../docs/framework/wcf/system-provided-bindings.md).  
  
## <a name="new-transport-default-values"></a>Nuovi valori predefiniti di trasporto  
 Nella tabella seguente vengono descritte le impostazioni che sono state modificate e dove reperire informazioni aggiuntive.  
  
|Proprietà|Attivato|Nuova impostazione predefinita|Per ulteriori informazioni, vedere|  
|--------------|--------|-----------------|------------------------------|  
|channelInitializationTimeout|<xref:System.ServiceModel.NetTcpBinding>|30 secondi|<xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement.ChannelInitializationTimeout%2A>|  
|listenBacklog|<xref:System.ServiceModel.NetTcpBinding>|12 * il numero di processori|<xref:System.ServiceModel.NetTcpBinding.ListenBacklog%2A>|  
|maxPendingAccepts|ConnectionOrientedTransportBindingElement<br /><br /> SMSvcHost.exe|2 * il numero di processori per trasporto<br /><br /> 4 \* numero di processori per SMSvcHost.exe|<xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement.MaxPendingAccepts%2A>[Configurazione il servizio di condivisione delle porte Net.TCP](http://msdn.microsoft.com/en-us/b6dd81fa-68b7-4e1b-868e-88e5901b7ea0)|  
|maxPendingConnections|ConnectionOrientedTransportBindingElement|12 * il numero di processori|<xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement.MaxPendingConnections%2A>|  
|receiveTimeout|SMSvcHost.exe|30 secondi|[Configurare il servizio di condivisione delle porte Net.TCP](http://msdn.microsoft.com/en-us/b6dd81fa-68b7-4e1b-868e-88e5901b7ea0)|  
  
## <a name="xml-editor-tooltips"></a>Descrizioni comandi dell'editor XML  
 Per consentire agli sviluppatori di servizi WCF nuovi ed esistenti di configurare i propri servizi, l'editor XML di Visual Studio offre ora le descrizioni comandi per ogni elemento di configurazione e le relative proprietà che fanno parte del file di configurazione del servizio.  
  
## <a name="configuring-wcf-services-in-code"></a>Configurazione dei servizi WCF nel codice  
 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] consente agli sviluppatori di configurare i servizi utilizzando file di configurazione o codice.  I file di configurazione sono utili quando è necessario configurare un servizio dopo la relativa distribuzione. Quando si utilizzano i file di configurazione, un professionista IT deve solo aggiornare il file di configurazione. Non è necessario eseguire la ricompilazione. I file di configurazione, tuttavia, possono risultare complessi e difficili da gestire. Non è disponibile alcun supporto per il debug dei file di configurazione e, poiché il riferimento agli elementi di configurazione viene fatto in base ai nomi, i file di configurazione della creazione possono risultare difficili e soggetti a errori. [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] consente inoltre di configurare i servizi nel codice. Nelle versioni precedenti di [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] (4.0 e versioni precedenti), la configurazione dei servizi nel codice era semplice negli scenari indipendenti. La classe <xref:System.ServiceModel.ServiceHost> consentiva di configurare endpoint e comportamenti prima di chiamare ServiceHost.Open. Negli scenari ospitati dal Web, tuttavia, non è possibile accedere alla classe <xref:System.ServiceModel.ServiceHost>. Per configurare un servizio ospitato dal Web era necessario creare un oggetto `System.ServiceModel.ServiceHostFactory` che creava l'oggetto <xref:System.ServiceModel.Activation.ServiceHostFactory> ed effettuava qualsiasi configurazione richiesta. A partire da .NET 4.5, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] fornisce un modo più semplice per configurare sia i servizi indipendenti sia quelli ospitati dal Web nel codice. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Configurazione dei servizi WCF nel codice](../../../docs/framework/wcf/configuring-wcf-services-in-code.md).  
  
## <a name="channelfactory-caching"></a>Memorizzazione nella cache di ChannelFactory  
 Le applicazioni client WCF utilizzano la classe <xref:System.ServiceModel.ChannelFactory%601> per creare un canale di comunicazione con un servizio WCF.  La creazione di istanze dell'oggetto <xref:System.ServiceModel.ChannelFactory%601> comporta un sovraccarico perché include le seguenti operazioni:  
  
1.  Costruzione dell'albero <xref:System.ServiceModel.Description.ContractDescription>  
  
2.  Reflection di tutti i tipi CLR obbligatori  
  
3.  Costruzione dello stack dei canali  
  
4.  Eliminazione di risorse  
  
 Per ridurre il sovraccarico, WCF può memorizzare le channel factory nella cache quando si utilizza un proxy client WCF. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Channel Factory e memorizzazione nella cache](../../../docs/framework/wcf/feature-details/channel-factory-and-caching.md).  
  
## <a name="compression-and-the-binary-encoder"></a>Compressione e codificatore binario  
 A partire da WCF 4.5, il codificatore binario WCF aggiunge il supporto per la compressione. Il tipo di compressione è configurato con la proprietà <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement.CompressionFormat%2A>. Sia il client sia il servizio devono configurare la proprietà <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement.CompressionFormat%2A>. La compressione verrà utilizzata per i protocolli HTTP, HTTPS e TCP. Se un client specifica di utilizzare la compressione, ma il servizio non la supporta, viene generata un'eccezione di protocollo che indica una mancata corrispondenza di protocollo. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Scelta di un codificatore di messaggi](../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
  
## <a name="udp"></a>UDP  
 Per un trasporto UDP che consente agli sviluppatori di scrivere servizi che usano "fire and forget" è stato aggiunto il supporto di messaggistica. Un client invia un messaggio a un servizio e non prevede alcuna risposta dal servizio.  
  
## <a name="multiple-authentication-support"></a>Supporto di più autenticazioni  
 Come in IIS, è stato aggiunto il supporto di più modalità di autenticazione in un singolo endpoint WCF quando si utilizza il trasporto HTTP e la relativa sicurezza. IIS consente di abilitare più modalità di autenticazione in una directory virtuale. Questa funzionalità permette a un singolo endpoint WCF di supportare più modalità di autenticazione abilitate per la directory virtuale in cui è ospitato il servizio WCF.  
  
## <a name="idn-support"></a>Supporto IDN  
 È stato aggiunto il supporto di servizi WCF con gli IDN (Internationalized Domain Name). Per ulteriori informazioni vedere [WCF e nomi di dominio internazionali](../../../docs/framework/wcf/feature-details/wcf-and-internationalized-domain-names.md).  
  
## <a name="httpclient"></a>HttpClient  
 È stata aggiunta una nuova classe denominata <xref:System.Net.Http.HttpClient> per semplificare l'utilizzo delle richieste HTTP. Per altre informazioni, vedere [rendere le app social networking e connesso con i servizi HTTP](http://go.microsoft.com/fwlink/?LinkId=231886) e [esempio di Client HTTP](http://code.msdn.microsoft.com/windowsapps/HttpClient-sample-55700664).  
  
## <a name="configuration-intellisense"></a>Configurazione di Intellisense  
 I valori degli attributi nei file di configurazione per gli attributi personalizzati definiti nel progetto supportano ora Intellisense per facilitare l'utilizzo delle configurazioni in modo rapido e preciso.  
  
## <a name="configuration-tooltips"></a>Descrizioni comandi di configurazione  
 Gli elementi e gli attributi di [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] dispongono ora di descrizioni comandi nell'editor XML per individuare più facilmente e accuratamente lo scopo dell'elemento o dell'attributo.  
  
## <a name="paste-data-as-classes"></a>Incollare i dati come classi  
 In un progetto WCF i tipi di dati definiti in XML (ad esempio quelli esposti in un servizio) possono essere incollati direttamente in una tabella codici. Il tipo XML verrà incollato come tipo CLR. Vedere [la generazione di classi di tipo dati da XML](../../../docs/framework/wcf/generating-data-type-classes-from-xml.md) per altri dettagli.  
  
## <a name="webservicehost-and-default-endpoints"></a>WebServiceHost ed endpoint predefiniti  
 In Visual Studio 2010 WebServiceHost ha creato automaticamente un endpoint predefinito, indipendentemente dall'eventuale specificazione esplicita di un endpoint. In Visual Studio 2012 WebServiceHost creerà un endpoint predefinito solo se non vengono aggiunti endpoint in modo esplicito. Se il client prevede l'endpoint predefinito, è possibile aggiungere un endpoint in modo esplicito e puntare il client sull'endpoint. In alternativa, è possibile tornare al comportamento precedente di WCF aggiungendo la seguente impostazione al file di configurazione dell'applicazione  
  
```xml  
<appSettings>  
    <add key="wcf:webservicehost:enableautomaticendpointscompatability" value="true"/>  
  </appSettings>  
```  
  
## <a name="ihttpcookiecontainermanager"></a>IHttpCookieContainerManager  
 Questa interfaccia, esposta da <xref:System.ServiceModel.Channels.IChannelFactory%601>, rende l'utilizzo dei cookie sul lato client molto più semplice. Quando AllowCookies è impostato su true nell'associazione, è possibile accedere ai cookie utilizzando il codice seguente:  
  
```csharp  
IHttpCookieContainerManager cookieManager = factory.GetProperty<IHttpCookieContainerManager>();   
System.Net.CookieContainer container = cookieManager.CookieContainer;  
```  
  
 È quindi possibile recuperare o impostare i cookie da <xref:System.Net.CookieContainer>. Quando AllowCookies è impostato su false, è possibile recuperare i cookie manualmente mediante <xref:System.ServiceModel.OperationContext> e inviarli in altre richieste utilizzando un altro controllo messaggi o <xref:System.ServiceModel.OperationContext>. L'interfaccia IHttpCookieContainerManager consente di autenticare un utente per un servizio e utilizzare il cookie di autenticazione restituito dal servizio per eseguire l'autenticazione per altri servizi.

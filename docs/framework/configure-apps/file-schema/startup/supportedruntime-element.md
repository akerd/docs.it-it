---
title: '&lt;supportedRuntime&gt; elemento'
ms.date: 10/17/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
ms.custom: updateeachrelease
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#supportedRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/supportedRuntime
helpviewer_keywords:
- supportedRuntime element
- <supportedRuntime> element
ms.assetid: 1ae16e23-afbe-4de4-b413-bc457f37b69f
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 5c38dc87d6015f0c814ea319c9353ea757478b85
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltsupportedruntimegt-element"></a>&lt;supportedRuntime&gt; elemento
Specifica le versioni di Common Language Runtime supportate dall'applicazione. È necessario utilizzare questo elemento in tutte le applicazioni compilate con la versione 1.1 o successiva di .NET Framework.  
  
[\<configuration>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  

[\<startup>](../../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)  
  
**\<supportedRuntime>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<supportedRuntime version="runtime version" sku="sku id"/>  
```  
  
## <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|**version**|Attributo facoltativo.<br /><br /> Valore stringa mediante il quale viene specificata la versione di Common Language Runtime (CLR) supportata da questa applicazione. Per i valori validi del `version` attributo, vedere il [valori "runtime version"](#version) sezione. **Nota:** tramite .NET Framework 3.5, il "*versione runtime*" valore assume la forma *principali*. *secondaria*. *Compilare*. A partire da [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], sono necessari solo i numeri delle versioni principale e secondaria (vale a dire, "v4.0" anziché "v4.0.30319"). È consigliabile la stringa più corta.|  
|**SKU**|Attributo facoltativo.<br /><br /> Valore stringa che specifica il codice di riferimento del prodotto (SKU), che a sua volta specifica la versione di .NET Framework supportata dall'applicazione.<br /><br /> A partire da .NET Framework 4.0, l'utilizzo del `sku` consiglia di attributo.  Quando è presente, indica la versione di .NET Framework di destinazione dell'app.<br /><br /> Per i valori validi dell'attributo sku, vedere il [i valori di "sku id"](#sku) sezione.|  
  
## <a name="remarks"></a>Note  
Se il  **\<supportedRuntime >** elemento non è presente nel file di configurazione dell'applicazione, viene utilizzata la versione di CLR impiegata per compilare l'applicazione.  

Il  **\<supportedRuntime >** elemento deve essere utilizzato da tutte le applicazioni compilate con la versione 1.1 o successiva del runtime. Nelle applicazioni compilate per supportare esclusivamente la versione 1.0 del runtime è necessario utilizzare il [ \<requiredRuntime >](../../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md) elemento.  
  
> [!NOTE]
>  Se si utilizza il [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md) funzione per specificare il file di configurazione, è necessario utilizzare il `<requiredRuntime>` elemento per tutte le versioni del runtime. Il `<supportedRuntime>` elemento viene ignorato quando si utilizza [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md).  
  
Per le app che supportano le versioni di runtime da .NET Framework 1.1 a 3.5, quando sono supportate più versioni, il primo elemento deve indicare la versione preferita, mentre l'ultimo elemento quella meno desiderata. Per le applicazioni che supportano il .NET Framework 4.0 o versioni successive, il `version` attributo indica la versione CLR che è comune a di .NET Framework 4 e versioni successive, e `sku` attributo indica una singola versione di .NET Framework che l'app destinazioni.  
  
> [!NOTE]
>  Se l'applicazione usa i percorsi di attivazione legacy, ad esempio il [funzione CorBindToRuntimeEx](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), e si desidera attivare la versione 4 di CLR anziché una versione precedente, tali percorsi oppure se l'applicazione viene compilata con la [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]ma presenta una dipendenza su un assembly in modalità mista compilato con una versione precedente di .NET Framework, non è sufficiente specificare il [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] nell'elenco dei runtime supportati. Inoltre, nel [ \<avvio > elemento](../../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) nel file di configurazione, è necessario impostare il `useLegacyV2RuntimeActivationPolicy` attributo `true`. Tuttavia, se questo attributo viene impostato su `true` tutti i componenti compilati con le versioni precedenti di .NET Framework vengono eseguiti utilizzando [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] invece dei runtime con cui sono stati compilati.  
  
È inoltre consigliabile testare l'applicazione con tutte le versioni di .NET Framework in cui possono essere eseguite.  
  
<a name="version"></a>   
## <a name="runtime-version-values"></a>Valori di "runtime version"  
Il `runtime` attributo specifica la versione di Common Language Runtime (CLR) che è necessaria per una determinata applicazione. Si noti che tutte le versioni di .NET Framework 4. x specificare il `v4.0` CLR. Nella tabella seguente sono elencati i valori validi per il *versione runtime* valore il `version` attributo.  

|Versione di .NET Framework|Attributo `version`|  
|----------------------------|-------------------------|  
|1.0|"v1.0.3705"|  
|1.1|"v1.1.4322"|  
|2.0|"v2.0.50727"|  
|3.0|"v2.0.50727"|  
|3.5|"v2.0.50727"|  
|4.0-4.7.1|"v4.0"|  

  
<a name="sku"></a>   
## <a name="sku-id-values"></a>Valori di "sku id"  
Il `sku` attributo Usa un moniker del framework di destinazione (TFM) per indicare la versione di .NET Framework che l'app ha come destinazione e deve essere eseguito. Nella tabella seguente sono elencati i valori validi che sono supportati dal `sku` attributo, a partire da .NET Framework 4.
  
|Versione di .NET Framework|Attributo `sku`|  
|----------------------------|---------------------|  
|4.0|".NETFramework,Version=v4.0"|  
|4.0, Client Profile|".NETFramework,Version=v4.0,Profile=Client"|  
|4.0, aggiornamento piattaforma 1|.NETFramework,Version=v4.0.1|  
|4.0, Client Profile, aggiornamento 1|.NETFramework, Version=v4.0.1, Profile=Client|  
|4.0, aggiornamento piattaforma 2|.NETFramework,Version=v4.0.2|  
|4.0, Client Profile, aggiornamento 2|.NETFramework, Version=v4.0.2, Profile=Client|  
|4.0, aggiornamento piattaforma 3|.NETFramework,Version=v4.0.3|  
|4.0, Client Profile, aggiornamento 3|.NETFramework,Version=v4.0.3,Profile=Client|  
|4.5|".NETFramework,Version=v4.5"|  
|4.5.1|".NETFramework,Version=v4.5.1"|  
|4.5.2|".NETFramework,Version=v4.5.2"|  
|4.6|".NETFramework,Version=v4.6"|  
|4.6.1|".NETFramework,Version=v4.6.1"|  
|4.6.2|". NETFramework, Version = v4.6.2 "|  
|4.7|". NETFramework, Version = v 4.7 "|
|4.7.1|". NETFramework, Version = 4.7.1"|

## <a name="example"></a>Esempio  
 L'esempio seguente illustra come specificare la versione di runtime in un file di configurazione. Il file di configurazione indica che l'app è destinata la 4.7 di .NET Framework.  
  
```xml  
<configuration>  
   <startup>  
      <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.7" />  
   </startup>  
</configuration>  
```  
  
## <a name="configuration-file"></a>File di configurazione  
 L'elemento può essere utilizzato nel file di configurazione dell'applicazione.  
  
## <a name="see-also"></a>Vedere anche  
 [Schema delle impostazioni di avvio](../../../../../docs/framework/configure-apps/file-schema/startup/index.md)  
 [Schema dei file di configurazione](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [In-Process Side-by-Side Execution](../../../../../docs/framework/deployment/in-process-side-by-side-execution.md) (Esecuzione side-by-side In-Process)

---
title: '&lt;certificate&gt; di &lt;peer&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 48b69142-c957-4305-a042-c9d0c9a55c0e
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e8bf8cb80201f2501fb60df7c9abb5039d688dc5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltcertificategt-of-ltpeergt"></a>&lt;certificate&gt; di &lt;peer&gt;
Specifica un certificato usato da un peer.  
  
 \<System. ServiceModel >  
\<i comportamenti >  
\<serviceBehaviors >  
\<comportamento >  
\<serviceCredentials >  
\<peer >  
\<certificato >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<certificate findValue = "String"   
storeLocation = "CurrentUser/LocalMachine"  
storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`findValue`|Stringa che contiene il valore da cercare nell'archivio certificati X.509. Il tipo contenuto nell'attributo deve soddisfare i requisiti del valore `x509FindType` specificato. Il valore predefinito è una stringa vuota.|  
|`storeLocation`|Specifica il percorso dell'archivio certificati X.509 usato dal client per eseguire la convalida del certificato peer. Di seguito vengono elencati i valori validi:<br /><br /> -LocalMachine: l'archivio certificati assegnato al computer locale.<br />-CurrentUser: l'archivio certificati assegnato all'utente corrente.<br /><br /> L'impostazione predefinita è LocalMachine.|  
|`storeName`|Specifica il nome dell'archivio certificati X.509 da aprire. Di seguito vengono elencati i valori validi:<br /><br /> -AddressBook: Archivio certificati per altri utenti.<br />-AuthRoot: Archivio certificati per autorità di certificazione di terze parti (CA).<br />-CertificateAuthority: Archivio certificati per autorità di certificazione intermedie (CA).<br />-Disallowed: Archivio certificati per certificati revocati.<br />-My: Archivio certificati per certificati personali.<br />-Root: Archivio certificati per autorità di certificazione radice attendibile (CA).<br />-TrustedPeople: Archivio certificati per utenti e risorse direttamente attendibili.<br />-TrustedPublisher: Archivio certificati per autori direttamente attendibili.<br /><br /> L'impostazione predefinita è My.|  
|`X509FindType`|Definisce il tipo di ricerca X.509 da eseguire. Di seguito vengono elencati i valori validi:<br /><br /> -FindByThumbPrint<br />-FindBySubjectName<br />-FindBySubjectDistinguishedName<br />-FindByIssuerName<br />-FindByIssuerDistinguishedName<br />-FindBySerialNumber<br />-FindByTimeValid<br />-FindByTimeNotYetValid<br />-FindByTemplateName<br />-FindByApplicationPolicy<br />-FindByCertificatePolicy<br />-FindByExtension<br />-FindByKeyUsage<br />-FindBySubjectKeyIdentifier<br /><br /> Il tipo contenuto nell'attributo `findValue` deve soddisfare i requisiti del valore `X509FindType` specificato.<br /><br /> L'impostazione predefinita è FindBySubjectDistinguishedName.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<peer >](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|Specifica le credenziali correnti per un nodo peer.|  
  
## <a name="remarks"></a>Note  
 Questa elemento di configurazione contiene un'istanza `X509Certificate2` usata per autenticare elementi adiacenti nella rete di peer.  
  
 Per ulteriori informazioni sulla programmazione peer-to-peer, vedere [rete Peer-to-Peer](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.Certificate%2A>  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateElement>  
 <xref:System.ServiceModel.Security.PeerCredential.Certificate%2A>  
 <xref:System.ServiceModel.Security.PeerCredential>  
 [Utilizzo dei certificati](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [Rete peer-to-Peer](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [Autenticazione dei messaggi del canale peer](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [Autenticazione personalizzata canale peer](http://msdn.microsoft.com/en-us/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [Protezione delle applicazioni del canale Peer](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)  
 [Protezione di servizi e client](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)

---
title: Ricerca dello strumento di chiave privata (FindPrivateKey.exe)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b8846a95-3fcc-4e8c-b9c0-128d975a6307
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f542e0ba3bf35319c270fe9f93d3f355cc45ac95
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="find-private-key-tool-findprivatekeyexe"></a>Ricerca dello strumento di chiave privata (FindPrivateKey.exe)
Questo strumento da riga di comando può essere usato per recuperare una chiave privata da un archivio certificati. Ad esempio, FindPrivateKey.exe può essere usato per cercare il percorso e il nome del file di chiave privata associati a un certificato X.509 specifico nell'archivio certificati.  
  
> [!IMPORTANT]
>  Lo strumento FindPrivateKey viene fornito come esempio WCF. Per altre informazioni sull'ubicazione dell'esempio e su come compilarlo, vedere  
  
## <a name="syntax"></a>Sintassi  
  
```  
FindPrivateKey<storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]  
```  
  
## <a name="remarks"></a>Note  
 Nelle tabelle seguenti vengono descritti gli argomenti e le opzioni che possono essere usati con lo strumento di Ricerca della Chiave Privata (FindPrivateKey.exe).  
  
|Argomento|Descrizione|  
|--------------|-----------------|  
|`storeName`|Nome dell'archivio certificati.|  
|`storeLocation`|Percorso dell'archivio certificati.|  
  
|Opzione|Descrizione|  
|------------|-----------------|  
|`/n <`*subjectName*`>`|Specifica il nome dell’oggetto del certificato.|  
|`/t <`*identificazione personale*`>`|Specifica l'identificazione digitale del certificato. Usare Certmgr.exe per recuperare l'identificazione digitale del certificato.|  
|`/f`|Restituisce soltanto il nome file.|  
|`/d`|Restituisce soltanto la directory.|  
|`/a`|Restituisce il nome file assoluto.|  
  
## <a name="examples"></a>Esempi  
 Il comando seguente consente di recuperare la chiave privata per John Doe.  
  
```  
FindPrivateKey My CurrentUser -n "CN=John Doe"  
```  
  
 Il comando seguente consente di recuperare la chiave privata per il computer locale.  
  
```  
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" –a  
```

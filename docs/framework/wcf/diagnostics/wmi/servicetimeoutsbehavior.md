---
title: ServiceTimeoutsBehavior
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4412525d-a3cc-4eae-b3e8-a50ce766d09d
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a65104a6fe76c22fca308091cc02e9496912129c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="servicetimeoutsbehavior"></a>ServiceTimeoutsBehavior
ServiceTimeoutsBehavior  
  
## <a name="syntax"></a>Sintassi  
  
```  
class ServiceTimeoutsBehavior : Behavior  
{  
  datetime TransactionTimeout;  
};  
```  
  
## <a name="methods"></a>Metodi  
 La classe ServiceTimeoutsBehavior non definisce metodi.  
  
## <a name="properties"></a>Proprietà  
 La classe ServiceTimeoutsBehavior dispone della proprietà seguente:  
  
### <a name="transactiontimeout"></a>TransactionTimeout  
 Tipo di dati: DateTime  
  
 Tipo di accesso: sola lettura  
  
 Periodo entro il quale una transazione deve essere completata.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>

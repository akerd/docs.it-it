---
title: Metodo ICLRDataTarget::Request
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataTarget.Request
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataTarget::Request
helpviewer_keywords:
- ICLRDataTarget::Request method [.NET Framework debugging]
- Request method [.NET Framework debugging]
ms.assetid: 4723bd1c-eddb-4ed2-897a-010024a47e01
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0e0ce905ea21267419e6a68e73f918de8fc364f3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="iclrdatatargetrequest-method"></a>Metodo ICLRDataTarget::Request
Chiamato dai servizi di accesso ai dati di common language runtime (CLR) per richiedere un'operazione, come definito dall'implementazione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT Request (  
    [in] ULONG32            reqCode,  
    [in] ULONG32            inBufferSize,  
    [in, size_is(inBufferSize)]   
        BYTE                *inBuffer,  
    [in] ULONG32            outBufferSize,  
    [out, size_is(outBufferSize)]   
        BYTE                *outBuffer  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `reqCode`  
 [in] Definito dall'utente.  
  
 `inBufferSize`  
 [in] Le dimensioni del buffer di input, viene utilizzato per la richiesta in ingresso.  
  
 `inBuffer`  
 [in] Un buffer che contiene la richiesta.  
  
 `outBufferSize`  
 [in] Le dimensioni del buffer di output, viene utilizzato per la risposta.  
  
 `outBuffer`  
 [out] Un Buffer contenente la risposta.  
  
## <a name="remarks"></a>Note  
 Il `Request` metodo semplifica l'aggiunta di operazioni personalizzate non specificate. Questo metodo, fornisce l'estendibilità senza richiedere una revisione della definizione dell'interfaccia.  
  
 Questo metodo è implementato dal writer dell'applicazione di debug.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** ClrData.idl, Clrdata. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [ICLRDataTarget (interfaccia)](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)

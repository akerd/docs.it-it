---
title: Metodo IMetaDataImport::GetNativeCallConvFromSig
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetNativeCallConvFromSig
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetNativeCallConvFromSig
helpviewer_keywords:
- GetNativeCallConvFromSig method [.NET Framework metadata]
- IMetaDataImport::GetNativeCallConvFromSig method [.NET Framework metadata]
ms.assetid: 50e04026-4d4a-47d9-96c1-f4677d6d938b
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5bcd54d4c0a0a1ac4dcb98e51fc25e5f3a7c7288
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetnativecallconvfromsig-method"></a>Metodo IMetaDataImport::GetNativeCallConvFromSig
Ottiene la convenzione di chiamata nativa per il metodo rappresentato dal puntatore a firma specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetNativeCallConvFromSig (  
   [in]  void const  *pvSig,  
   [in]  ULONG       cbSig,  
   [out] ULONG       *pCallConv  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pvSig`  
 [in] Un puntatore per la firma dei metadati del metodo per restituire la convenzione di chiamata.  
  
 `cbSig`  
 [in] Le dimensioni in byte di `pvSig`.  
  
 `pCallConv`  
 [out] Puntatore alla convenzione di chiamata nativa.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** inclusa come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Runtime.InteropServices.CallingConvention>  
 [IMetaDataImport (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

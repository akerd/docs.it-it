---
title: Metodo ICorDebugCode::GetILToNativeMapping
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCode.GetILToNativeMapping
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode::GetILToNativeMapping
helpviewer_keywords:
- GetILToNativeMapping method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetILToNativeMapping method [.NET Framework debugging]
ms.assetid: a8ecd8c8-9627-4356-9c6f-bd05e24637c0
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 54937e8d5d7a2e345ebcbccadbc592b12e3ee9b6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcodegetiltonativemapping-method"></a>Metodo ICorDebugCode::GetILToNativeMapping
Ottiene una matrice di istanze di "COR_DEBUG_IL_TO_NATIVE_MAP" che rappresentano i mapping da Microsoft intermediate language (MSIL) agli offset nativi.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetILToNativeMapping (  
    [in]  ULONG32    cMap,  
    [out] ULONG32    *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `cMap`  
 [in] Dimensione della matrice `map`.  
  
 `pcMap`  
 [out] Un puntatore al numero effettivo di elementi restituiti nella `map` matrice.  
  
 `map`  
 [out] Matrice di `COR_DEBUG_IL_TO_NATIVE_MAP` strutture, ognuno dei quali rappresenta un mapping da un offset MSIL a un offset nativo.  
  
 Non sussiste alcun ordinamento per la matrice di elementi restituiti.  
  
## <a name="remarks"></a>Note  
 Il `GetILToNativeMapping` metodo restituirà risultati significativi solo se l'istanza "ICorDebugCode" rappresenta il codice nativo che era just-in-time (JIT) compilati dal codice MSIL.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [ICorDebugCode Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md)

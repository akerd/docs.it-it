---
title: Metodo ICorDebugChain::GetActiveFrame
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugChain.GetActiveFrame
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugChain::GetActiveFrame
helpviewer_keywords:
- ICorDebugChain::GetActiveFrame method [.NET Framework debugging]
- GetActiveFrame method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 36887017-670b-4f21-b406-8fab956f84a3
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b5de327c1579d05f6ae4a440fc76a3fb9ee99b13
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugchaingetactiveframe-method"></a>Metodo ICorDebugChain::GetActiveFrame
Ottiene attivo (vale a dire più recente) frame sulla catena.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `ppFrame`  
 [out] Un puntatore all'indirizzo di un oggetto ICorDebugFrame che rappresenta l'attivo (vale a dire più recente) frame sulla catena.  
  
## <a name="remarks"></a>Note  
 Se non è disponibile alcun frame dello stack gestito `ppFrame` è impostato su null.  
  
 Se il frame attivo non è disponibile, la chiamata avrà esito positivo e `ppFrame` sarà null. Non sarà disponibili per le catene avviate da CHAIN_ENTER_UNMANAGED e per alcune catene avviate CHAIN_CLASS_INIT frame attivi. Vedere l'enumerazione CorDebugChainReason.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

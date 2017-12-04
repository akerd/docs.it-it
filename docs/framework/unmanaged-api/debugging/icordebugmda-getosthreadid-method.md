---
title: Metodo ICorDebugMDA::GetOSThreadId
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugMDA.GetOSThreadId
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugMDA::GetOSThreadId
helpviewer_keywords:
- ICorDebugMDA::GetOSThreadId method [.NET Framework debugging]
- GetOSThreadId method [.NET Framework debugging]
ms.assetid: 7ca7c364-ade4-4219-b434-9f6ae2359be6
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6cc53eecadd982d7cea045424de52d8e6f64107b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmdagetosthreadid-method"></a><span data-ttu-id="10f6a-102">Metodo ICorDebugMDA::GetOSThreadId</span><span class="sxs-lookup"><span data-stu-id="10f6a-102">ICorDebugMDA::GetOSThreadId Method</span></span>
<span data-ttu-id="10f6a-103">Ottiene l'identificatore del thread del sistema operativo (sistema operativo) su cui l'assistente al debug gestito (MDA) rappresentato da [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="10f6a-103">Gets the operating system (OS) thread identifier upon which the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10f6a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="10f6a-104">Syntax</span></span>  
  
```  
HRESULT GetOSThreadId (  
    [out] DWORD    *pOsTid  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="10f6a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="10f6a-105">Parameters</span></span>  
 `pOsTid`  
 <span data-ttu-id="10f6a-106">[out] Puntatore all'identificatore del thread del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="10f6a-106">[out] A pointer to the OS thread identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="10f6a-107">Note</span><span class="sxs-lookup"><span data-stu-id="10f6a-107">Remarks</span></span>  
 <span data-ttu-id="10f6a-108">Il thread del sistema operativo viene utilizzato invece di un oggetto ICorDebugThread per consentire situazioni in cui un assistente al debug gestito è generato su un thread nativo o su un thread gestito non ancora entrato nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="10f6a-108">The OS thread is used instead of an ICorDebugThread to allow for situations in which an MDA is fired either on a native thread or on a managed thread that has not yet entered managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10f6a-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="10f6a-109">Requirements</span></span>  
 <span data-ttu-id="10f6a-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10f6a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10f6a-111">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="10f6a-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="10f6a-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="10f6a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="10f6a-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10f6a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10f6a-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="10f6a-114">See Also</span></span>  
 [<span data-ttu-id="10f6a-115">ICorDebugMDA (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="10f6a-115">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)  
 [<span data-ttu-id="10f6a-116">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="10f6a-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
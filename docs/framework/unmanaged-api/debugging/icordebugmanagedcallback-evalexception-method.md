---
title: Metodo ICorDebugManagedCallback::EvalException
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.EvalException
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::EvalException
helpviewer_keywords:
- EvalException method [.NET Framework debugging]
- ICorDebugManagedCallback::EvalException method [.NET Framework debugging]
ms.assetid: d6036345-18a3-45c1-a302-b1c6f2dced9b
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ed64c7b28d60e966e836ac75e6dd7c0848304a38
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmanagedcallbackevalexception-method"></a><span data-ttu-id="75faa-102">Metodo ICorDebugManagedCallback::EvalException</span><span class="sxs-lookup"><span data-stu-id="75faa-102">ICorDebugManagedCallback::EvalException Method</span></span>
<span data-ttu-id="75faa-103">Notifica al debugger che una versione di valutazione è terminato con un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="75faa-103">Notifies the debugger that an evaluation has terminated with an unhandled exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75faa-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="75faa-104">Syntax</span></span>  
  
```  
HRESULT EvalException (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] ICorDebugEval      *pEval  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="75faa-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="75faa-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="75faa-106">[in] Un puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione in cui la valutazione è terminata.</span><span class="sxs-lookup"><span data-stu-id="75faa-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the evaluation terminated.</span></span>  
  
 `pThread`  
 <span data-ttu-id="75faa-107">[in] Un puntatore a un oggetto ICorDebugThread che rappresenta il thread in cui è terminata la valutazione.</span><span class="sxs-lookup"><span data-stu-id="75faa-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the evaluation terminated.</span></span>  
  
 `pEval`  
 <span data-ttu-id="75faa-108">[in] Un puntatore a un oggetto ICorDebugEval che rappresenta il codice che ha eseguito la valutazione.</span><span class="sxs-lookup"><span data-stu-id="75faa-108">[in] A pointer to an ICorDebugEval object that represents the code that performed the evaluation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75faa-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="75faa-109">Requirements</span></span>  
 <span data-ttu-id="75faa-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="75faa-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75faa-111">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="75faa-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="75faa-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="75faa-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="75faa-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75faa-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75faa-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75faa-114">See Also</span></span>  
 [<span data-ttu-id="75faa-115">ICorDebugManagedCallback (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="75faa-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
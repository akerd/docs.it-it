---
title: Metodo ICorProfilerModuleEnum::Skip
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerModuleEnum.Skip Method
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerModuleEnum::Skip
helpviewer_keywords:
- Skip method, ICorProfilerModuleEnum interface [.NET Framework profiling]
- ICorProfilerModuleEnum::Skip method [.NET Framework profiling]
ms.assetid: 8dc29c6a-e2ba-41d8-a1e0-0fdd21421e0b
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7331c5221de1dc1bfdbbce77f8c40f4fbc95aea2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilermoduleenumskip-method"></a><span data-ttu-id="48192-102">Metodo ICorProfilerModuleEnum::Skip</span><span class="sxs-lookup"><span data-stu-id="48192-102">ICorProfilerModuleEnum::Skip Method</span></span>
<span data-ttu-id="48192-103">Sposta in avanti il cursore dell'enumeratore dalla posizione corrente, in modo che venga ignorato il numero specificato di elementi.</span><span class="sxs-lookup"><span data-stu-id="48192-103">Advances the enumerator's cursor from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48192-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="48192-104">Syntax</span></span>  
  
```  
HRESULT Skip([in] ULONG celt);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="48192-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="48192-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="48192-106">[in] Il numero di elementi da ignorare.</span><span class="sxs-lookup"><span data-stu-id="48192-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="48192-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="48192-107">Return Value</span></span>  
 <span data-ttu-id="48192-108">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="48192-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="48192-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="48192-109">HRESULT</span></span>|<span data-ttu-id="48192-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="48192-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="48192-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="48192-111">S_OK</span></span>|<span data-ttu-id="48192-112">`celt`gli elementi sono stati ignorati.</span><span class="sxs-lookup"><span data-stu-id="48192-112">`celt` elements were skipped.</span></span>|  
|<span data-ttu-id="48192-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="48192-113">S_FALSE</span></span>|<span data-ttu-id="48192-114">Meno di `celt` elementi ignorati, a indicare che non sono presenti più elementi.</span><span class="sxs-lookup"><span data-stu-id="48192-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="48192-115">Note</span><span class="sxs-lookup"><span data-stu-id="48192-115">Remarks</span></span>  
 <span data-ttu-id="48192-116">La nuova posizione del cursore dell'enumeratore, questo viene (posizione corrente) + `celt`.</span><span class="sxs-lookup"><span data-stu-id="48192-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48192-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="48192-117">Requirements</span></span>  
 <span data-ttu-id="48192-118">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48192-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48192-119">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="48192-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="48192-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="48192-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="48192-121">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48192-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48192-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="48192-122">See Also</span></span>  
 [<span data-ttu-id="48192-123">ICorProfilerModuleEnum (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="48192-123">ICorProfilerModuleEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)  
 [<span data-ttu-id="48192-124">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="48192-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
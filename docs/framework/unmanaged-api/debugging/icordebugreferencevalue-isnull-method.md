---
title: Metodo ICorDebugReferenceValue::IsNull
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugReferenceValue.IsNull
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugReferenceValue::IsNull
helpviewer_keywords:
- IsNull method, ICorDebugReferenceValue interface [.NET Framework debugging]
- ICorDebugReferenceValue::IsNull method [.NET Framework debugging]
ms.assetid: 99e8c8d7-a1c0-47c8-9dbd-03e0b2bcb4d5
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f8a7892900149380c979f0bee1a4229407af8c9c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugreferencevalueisnull-method"></a><span data-ttu-id="885cc-102">Metodo ICorDebugReferenceValue::IsNull</span><span class="sxs-lookup"><span data-stu-id="885cc-102">ICorDebugReferenceValue::IsNull Method</span></span>
<span data-ttu-id="885cc-103">Ottiene un valore che indica se l'interfaccia ICorDebugReferenceValue è un valore null, nel qual caso il `ICorDebugReferenceValue` non punta a un oggetto.</span><span class="sxs-lookup"><span data-stu-id="885cc-103">Gets a value that indicates whether this ICorDebugReferenceValue is a null value, in which case the `ICorDebugReferenceValue` does not point to an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="885cc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="885cc-104">Syntax</span></span>  
  
```  
HRESULT IsNull (  
    [out] BOOL   *pbNull  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="885cc-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="885cc-105">Parameters</span></span>  
 `pbNull`  
 <span data-ttu-id="885cc-106">[out] Un puntatore a un valore booleano che è `true` se `ICorDebugReferenceValue` oggetto è null; in caso contrario, `pbNull` è `false`.</span><span class="sxs-lookup"><span data-stu-id="885cc-106">[out] A pointer to a Boolean value that is `true` if this `ICorDebugReferenceValue` object is null; otherwise, `pbNull` is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="885cc-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="885cc-107">Requirements</span></span>  
 <span data-ttu-id="885cc-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="885cc-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="885cc-109">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="885cc-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="885cc-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="885cc-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="885cc-111">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="885cc-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
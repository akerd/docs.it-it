---
title: Metodo IHostMemoryManager::AcquiredVirtualAddressSpace
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMemoryManager.AcquiredVirtualAddressSpace
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMemoryManager::AcquiredVirtualAddressSpace
helpviewer_keywords:
- IHostMemoryManager::AcquiredVirtualAddressSpace method [.NET Framework hosting]
- AcquiredVirtualAddressSpace method [.NET Framework hosting]
ms.assetid: ef2f83c2-127e-4c38-8385-306c03cd2167
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 480dba9257c34af2cd1bc11aba4a07a4fbbe1162
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ihostmemorymanageracquiredvirtualaddressspace-method"></a><span data-ttu-id="ee066-102">Metodo IHostMemoryManager::AcquiredVirtualAddressSpace</span><span class="sxs-lookup"><span data-stu-id="ee066-102">IHostMemoryManager::AcquiredVirtualAddressSpace Method</span></span>
<span data-ttu-id="ee066-103">Notifica all'host che common language runtime (CLR) ha acquisito la memoria specificata dal sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="ee066-103">Notifies the host that the common language runtime (CLR) has acquired the specified memory from the operating system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee066-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ee066-104">Syntax</span></span>  
  
```  
HRESULT AcquiredVirtualAddressSpace(  
    [in] LPVOID  startAddress,  
    [in] SIZE_T  size  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ee066-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ee066-105">Parameters</span></span>  
 `startAddress`  
 <span data-ttu-id="ee066-106">[in] L'indirizzo iniziale della memoria.</span><span class="sxs-lookup"><span data-stu-id="ee066-106">[in] The starting address of the memory.</span></span>  
  
 `size`  
 <span data-ttu-id="ee066-107">[in] Le dimensioni in byte, della memoria.</span><span class="sxs-lookup"><span data-stu-id="ee066-107">[in] The size, in bytes, of the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ee066-108">Note</span><span class="sxs-lookup"><span data-stu-id="ee066-108">Remarks</span></span>  
 <span data-ttu-id="ee066-109">Il `AcquiredVirtualAddressSpace` metodo è un metodo di callback e deve essere implementato dal writer dell'applicazione host.</span><span class="sxs-lookup"><span data-stu-id="ee066-109">The `AcquiredVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="ee066-110">Viene chiamato da CLR.</span><span class="sxs-lookup"><span data-stu-id="ee066-110">It is called by the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee066-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ee066-111">Requirements</span></span>  
 <span data-ttu-id="ee066-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee066-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee066-113">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="ee066-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ee066-114">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ee066-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ee066-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee066-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee066-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ee066-116">See Also</span></span>  
 [<span data-ttu-id="ee066-117">IHostMemoryManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="ee066-117">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
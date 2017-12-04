---
title: Metodo FreeWin32ResBlob
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.FreeWin32ResBlob
api_location: alink.dll
api_type: COM
f1_keywords: FreeWin32ResBlob
helpviewer_keywords: FreeWin32ResBlob method
ms.assetid: d941102b-2679-4c49-b15e-c0fc9c53e11f
topic_type: apiref
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ae7b01fee1460abfae8fc2f8f6c12a5f19d83b6e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="freewin32resblob-method"></a><span data-ttu-id="8a1c5-102">Metodo FreeWin32ResBlob</span><span class="sxs-lookup"><span data-stu-id="8a1c5-102">FreeWin32ResBlob Method</span></span>
<span data-ttu-id="8a1c5-103">Rilascia le risorse associate e il blob di risorse Win32.</span><span class="sxs-lookup"><span data-stu-id="8a1c5-103">Releases the Win32 resource blob and associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a1c5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8a1c5-104">Syntax</span></span>  
  
```  
HRESULT FreeWin32ResBlob(  
    const void** ppResBlob  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8a1c5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8a1c5-105">Parameters</span></span>  
 `ppResBlob`  
 <span data-ttu-id="8a1c5-106">Il blob di risorse da rilasciare.</span><span class="sxs-lookup"><span data-stu-id="8a1c5-106">The resource blob to be released.</span></span> <span data-ttu-id="8a1c5-107">Questo metodo assegna il puntatore del blob a NULL.</span><span class="sxs-lookup"><span data-stu-id="8a1c5-107">This method assigns the blob pointer to NULL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8a1c5-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8a1c5-108">Return Value</span></span>  
 <span data-ttu-id="8a1c5-109">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="8a1c5-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a1c5-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8a1c5-110">Requirements</span></span>  
 <span data-ttu-id="8a1c5-111">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="8a1c5-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a1c5-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8a1c5-112">See Also</span></span>  
 [<span data-ttu-id="8a1c5-113">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="8a1c5-113">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="8a1c5-114">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="8a1c5-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="8a1c5-115">ALink (API)</span><span class="sxs-lookup"><span data-stu-id="8a1c5-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
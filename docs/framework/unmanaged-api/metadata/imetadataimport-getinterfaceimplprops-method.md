---
title: Metodo IMetaDataImport::GetInterfaceImplProps
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetInterfaceImplProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetInterfaceImplProps
helpviewer_keywords:
- IMetaDataImport::GetInterfaceImplProps method [.NET Framework metadata]
- GetInterfaceImpProps method [.NET Framework metadata]
ms.assetid: be3f5985-b1e4-4036-8602-c16e8508d4af
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0843c9823ba40944e6ea075d469f9a76510d8714
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetinterfaceimplprops-method"></a><span data-ttu-id="a567c-102">Metodo IMetaDataImport::GetInterfaceImplProps</span><span class="sxs-lookup"><span data-stu-id="a567c-102">IMetaDataImport::GetInterfaceImplProps Method</span></span>
<span data-ttu-id="a567c-103">Ottiene un puntatore al token di metadati per il <xref:System.Type> che implementa il metodo specificato e per l'interfaccia che dichiara tale metodo.</span><span class="sxs-lookup"><span data-stu-id="a567c-103">Gets a pointer to the metadata tokens for the <xref:System.Type> that implements the specified method, and for the interface that declares that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a567c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a567c-104">Syntax</span></span>  
  
```  
HRESULT GetInterfaceImplProps (  
   [in]  mdInterfaceImpl        iiImpl,  
   [out] mdTypeDef              *pClass,  
   [out] mdToken                *ptkIface  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a567c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a567c-105">Parameters</span></span>  
 `iiImpl`  
 <span data-ttu-id="a567c-106">[in] Che rappresenta il metodo per restituire i token di classe e interfaccia per il token di metadati.</span><span class="sxs-lookup"><span data-stu-id="a567c-106">[in] The metadata token representing the method to return the class and interface tokens for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="a567c-107">[out] Il token di metadati che rappresenta la classe che implementa il metodo.</span><span class="sxs-lookup"><span data-stu-id="a567c-107">[out] The metadata token representing the class that implements the method.</span></span>  
  
 `ptkIface`  
 <span data-ttu-id="a567c-108">[out] Il token di metadati che rappresenta l'interfaccia che definisce il metodo implementato.</span><span class="sxs-lookup"><span data-stu-id="a567c-108">[out] The metadata token representing the interface that defines the implemented method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a567c-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a567c-109">Requirements</span></span>  
 <span data-ttu-id="a567c-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a567c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a567c-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a567c-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a567c-112">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a567c-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a567c-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a567c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a567c-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a567c-114">See Also</span></span>  
 [<span data-ttu-id="a567c-115">IMetaDataImport (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="a567c-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="a567c-116">IMetaDataImport2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="a567c-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
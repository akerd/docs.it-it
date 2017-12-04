---
title: Metodo IMetaDataAssemblyImport::EnumAssemblyRefs
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport.EnumAssemblyRefs
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport::EnumAssemblyRefs
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumAssemblyRefs method [.NET Framework metadata]
- EnumAssemblyRefs method [.NET Framework metadata]
ms.assetid: 8844d0dd-730e-4592-8a7b-c1462d312c70
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 24a289ed42a99cd26c7829d9a5789ac3027026c0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataassemblyimportenumassemblyrefs-method"></a><span data-ttu-id="961a2-102">Metodo IMetaDataAssemblyImport::EnumAssemblyRefs</span><span class="sxs-lookup"><span data-stu-id="961a2-102">IMetaDataAssemblyImport::EnumAssemblyRefs Method</span></span>
<span data-ttu-id="961a2-103">Enumera il `mdAssemblyRef` istanze definite nel manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="961a2-103">Enumerates the `mdAssemblyRef` instances that are defined in the assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="961a2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="961a2-104">Syntax</span></span>  
  
```  
HRESULT EnumAssemblyRefs (  
    [in, out] HCORENUM        *phEnum,   
    [out]     mdAssemblyRef   rAssemblyRefs[],   
    [in]      ULONG           cMax,   
    [out]     ULONG           *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="961a2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="961a2-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="961a2-106">[in, out] Un puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="961a2-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="961a2-107">Deve essere un valore null valore quando il `EnumAssemblyRefs` metodo viene chiamato per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="961a2-107">This must be a null value when the `EnumAssemblyRefs` method is called for the first time.</span></span>  
  
 `rAssemblyRefs`  
 <span data-ttu-id="961a2-108">[out] L'enumerazione di `mdAssemblyRef` i token di metadati.</span><span class="sxs-lookup"><span data-stu-id="961a2-108">[out] The enumeration of `mdAssemblyRef` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="961a2-109">[in] Il numero massimo di token che può essere inserita nel `rAssemblyRefs` matrice.</span><span class="sxs-lookup"><span data-stu-id="961a2-109">[in] The maximum number of tokens that can be placed in the `rAssemblyRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="961a2-110">[out] Numero di token effettivamente inseriti in `rAssemblyRefs`.</span><span class="sxs-lookup"><span data-stu-id="961a2-110">[out] The number of tokens actually placed in `rAssemblyRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="961a2-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="961a2-111">Return Value</span></span>  
  
|<span data-ttu-id="961a2-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="961a2-112">HRESULT</span></span>|<span data-ttu-id="961a2-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="961a2-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="961a2-114">`EnumAssemblyRefs`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="961a2-114">`EnumAssemblyRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="961a2-115">Non sono presenti token da enumerare.</span><span class="sxs-lookup"><span data-stu-id="961a2-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="961a2-116">In questo caso, `pcTokens` è impostato su zero.</span><span class="sxs-lookup"><span data-stu-id="961a2-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="961a2-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="961a2-117">Requirements</span></span>  
 <span data-ttu-id="961a2-118">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="961a2-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="961a2-119">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="961a2-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="961a2-120">**Libreria:** usata come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="961a2-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="961a2-121">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="961a2-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="961a2-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="961a2-122">See Also</span></span>  
 [<span data-ttu-id="961a2-123">IMetaDataAssemblyImport (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="961a2-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
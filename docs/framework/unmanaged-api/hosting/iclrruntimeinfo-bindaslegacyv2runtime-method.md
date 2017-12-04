---
title: Metodo ICLRRuntimeInfo::BindAsLegacyV2Runtime
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo.BindAsLegacyV2Runtime
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo::BindAsLegacyV2Runtime
helpviewer_keywords:
- ICLRRuntimeInfo::BindAsLegacyV2Runtime method [.NET Framework hosting]
- BindAsLegacyV2Runtime method [.NET Framework hosting]
ms.assetid: 65fd55ac-4a24-4479-9384-a2e8013bfb2b
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 229c5483c02357054f3d2821d8e024c78887e839
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimeinfobindaslegacyv2runtime-method"></a><span data-ttu-id="e1014-102">Metodo ICLRRuntimeInfo::BindAsLegacyV2Runtime</span><span class="sxs-lookup"><span data-stu-id="e1014-102">ICLRRuntimeInfo::BindAsLegacyV2Runtime Method</span></span>
<span data-ttu-id="e1014-103">Associa il runtime corrente per tutti i legacy common language runtime (CLR) versione 2 attivazione decisioni relative ai criteri.</span><span class="sxs-lookup"><span data-stu-id="e1014-103">Binds the current runtime for all legacy common language runtime (CLR) version 2 activation policy decisions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1014-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e1014-104">Syntax</span></span>  
  
```  
HRESULT BindAsLegacyV2Runtime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="e1014-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e1014-105">Return Value</span></span>  
 <span data-ttu-id="e1014-106">Questo metodo restituisce gli HRESULT specifici seguenti:</span><span class="sxs-lookup"><span data-stu-id="e1014-106">This method returns the following specific HRESULTs:</span></span>  
  
|<span data-ttu-id="e1014-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e1014-107">HRESULT</span></span>|<span data-ttu-id="e1014-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e1014-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e1014-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="e1014-109">S_OK</span></span>|<span data-ttu-id="e1014-110">L'associazione ha avuto esito positivo o questo runtime già associato come il runtime criteri 2 attivazione della versione CLR legacy.</span><span class="sxs-lookup"><span data-stu-id="e1014-110">Either binding succeeded, or this runtime was already bound as the legacy CLR version 2 activation policy runtime.</span></span>|  
|<span data-ttu-id="e1014-111">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span><span class="sxs-lookup"><span data-stu-id="e1014-111">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span></span>|<span data-ttu-id="e1014-112">Un runtime diverso è già associato ai criteri di attivazione 2 versione CLR legacy.</span><span class="sxs-lookup"><span data-stu-id="e1014-112">A different runtime was already bound to the legacy CLR version 2 activation policy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1014-113">Note</span><span class="sxs-lookup"><span data-stu-id="e1014-113">Remarks</span></span>  
 <span data-ttu-id="e1014-114">Se il runtime corrente è già associato per tutti i precedenti CLR versione 2 attivazione decisioni relative ai criteri (ad esempio, tramite il `useLegacyV2RuntimeActivationPolicy` attributo la [ \<avvio > elemento](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) nel file di configurazione), questo metodo non restituisce un risultato di errore. al contrario, il risultato è S_OK, così come lo sarebbe se il metodo avesse associato correttamente i criteri di attivazione legacy.</span><span class="sxs-lookup"><span data-stu-id="e1014-114">If the current runtime is already bound for all legacy CLR version 2 activation policy decisions (for example, by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) in the configuration file), this method does not return an error result; instead, the result is S_OK, just as it would be if the method had successfully bound legacy activation policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1014-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e1014-115">Requirements</span></span>  
 <span data-ttu-id="e1014-116">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1014-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1014-117">**Intestazione:** Metahost. H</span><span class="sxs-lookup"><span data-stu-id="e1014-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="e1014-118">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e1014-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e1014-119">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1014-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1014-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e1014-120">See Also</span></span>  
 [<span data-ttu-id="e1014-121">ICLRRuntimeInfo (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="e1014-121">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="e1014-122">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="e1014-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="e1014-123">Hosting</span><span class="sxs-lookup"><span data-stu-id="e1014-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 [<span data-ttu-id="e1014-124">\<avvio > elemento</span><span class="sxs-lookup"><span data-stu-id="e1014-124">\<startup> Element</span></span>](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)
---
title: Metodo IHostControl::SetAppDomainManager
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostControl.SetAppDomainManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostControl::SetAppDomainManager
helpviewer_keywords:
- IHostControl::SetAppDomainManager method [.NET Framework hosting]
- SetAppDomainManager method [.NET Framework hosting]
ms.assetid: 6562bbe7-0d67-4c50-a958-3a18cf680375
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 97e853bc74babca5b5400953b63714a13419fcaa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihostcontrolsetappdomainmanager-method"></a><span data-ttu-id="1af92-102">Metodo IHostControl::SetAppDomainManager</span><span class="sxs-lookup"><span data-stu-id="1af92-102">IHostControl::SetAppDomainManager Method</span></span>
<span data-ttu-id="1af92-103">Notifica all'host che è stato creato un dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="1af92-103">Notifies the host that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1af92-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1af92-104">Syntax</span></span>  
  
```  
HRESULT SetAppDomainManager (  
    [in] DWORD     dwAppDomainID,  
    [in] IUnknown* pUnkAppDomainManager  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1af92-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1af92-105">Parameters</span></span>  
 `dwAppDomainID`  
 <span data-ttu-id="1af92-106">[in] L'identificatore numerico dell'oggetto selezionato <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="1af92-106">[in] The numeric identifier of the selected <xref:System.AppDomain>.</span></span>  
  
 `pUnkAppDomainManager`  
 <span data-ttu-id="1af92-107">[in] Un puntatore al <xref:System.AppDomainManager> oggetto che implementa l'host come `IUnknown`.</span><span class="sxs-lookup"><span data-stu-id="1af92-107">[in] A pointer to the <xref:System.AppDomainManager> object that the host implements as `IUnknown`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1af92-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1af92-108">Return Value</span></span>  
  
|<span data-ttu-id="1af92-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1af92-109">HRESULT</span></span>|<span data-ttu-id="1af92-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1af92-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1af92-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="1af92-111">S_OK</span></span>|<span data-ttu-id="1af92-112">`SetAppDomainManager`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="1af92-112">`SetAppDomainManager` returned successfully.</span></span>|  
|<span data-ttu-id="1af92-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1af92-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1af92-114">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="1af92-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1af92-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1af92-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1af92-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="1af92-116">The call timed out.</span></span>|  
|<span data-ttu-id="1af92-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1af92-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1af92-118">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="1af92-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1af92-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1af92-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1af92-120">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="1af92-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1af92-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1af92-121">E_FAIL</span></span>|<span data-ttu-id="1af92-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="1af92-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1af92-123">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="1af92-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1af92-124">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="1af92-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1af92-125">Note</span><span class="sxs-lookup"><span data-stu-id="1af92-125">Remarks</span></span>  
 <span data-ttu-id="1af92-126">Il <xref:System.AppDomainManager> fornisce un meccanismo per l'avvio automatico in codice gestito e per controllare la creazione e configurazione di ciascun host <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="1af92-126">The <xref:System.AppDomainManager> provides the host with a mechanism to bootstrap into managed code and to control the creation and settings of each <xref:System.AppDomain>.</span></span> <span data-ttu-id="1af92-127">Il <xref:System.AppDomainManager> viene caricato in ogni <xref:System.AppDomain> quando che <xref:System.AppDomain> viene creato.</span><span class="sxs-lookup"><span data-stu-id="1af92-127">The <xref:System.AppDomainManager> is loaded into each <xref:System.AppDomain> when that <xref:System.AppDomain> is created.</span></span> <span data-ttu-id="1af92-128">Se sceglie, Common Language Runtime notifica all'host che il dominio applicazione è stato creato impostando il valore della `pUnkAppDomainManager` parametro.</span><span class="sxs-lookup"><span data-stu-id="1af92-128">If it chooses, the CLR notifies the host that the application domain has been created by setting the value of the `pUnkAppDomainManager` parameter.</span></span>  
  
 <span data-ttu-id="1af92-129">Nella sua implementazione del `SetAppDomainManager` (metodo), l'host può impostare il nome dell'assembly e il tipo per la gestione del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="1af92-129">In its implementation of the `SetAppDomainManager` method, the host can set the assembly name and type for the application domain manager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1af92-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1af92-130">Requirements</span></span>  
 <span data-ttu-id="1af92-131">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1af92-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1af92-132">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="1af92-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1af92-133">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1af92-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1af92-134">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1af92-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1af92-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1af92-135">See Also</span></span>  
 <xref:System.AppDomain>  
 <xref:System.AppDomainManager>  
 [<span data-ttu-id="1af92-136">IHostControl (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="1af92-136">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
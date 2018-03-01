---
title: "Метод ICLRRuntimeHost::UnloadAppDomain"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRRuntimeHost.UnloadAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::UnloadAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::UnloadAppDomain method [.NET Framework hosting]
- UnloadAppDomain method [.NET Framework hosting]
ms.assetid: 571912bc-3429-4ff8-8eb2-ea993ffbd901
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 481f701ae4db15b66596c3af89c2e7aff7a28f88
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iclrruntimehostunloadappdomain-method"></a><span data-ttu-id="481c5-102">Метод ICLRRuntimeHost::UnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="481c5-102">ICLRRuntimeHost::UnloadAppDomain Method</span></span>
<span data-ttu-id="481c5-103">Выгружает управляемый <xref:System.AppDomain> , соответствующий указанный числовой идентификатор.</span><span class="sxs-lookup"><span data-stu-id="481c5-103">Unloads the managed <xref:System.AppDomain> that corresponds to the specified numeric identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="481c5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="481c5-104">Syntax</span></span>  
  
```  
HRESULT UnloadAppDomain(  
    [in] DWORD dwAppDomainId  
    [in] BOOL  fWaitUntilDone  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="481c5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="481c5-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="481c5-106">[in] Числовой идентификатор для выгрузки домена приложения.</span><span class="sxs-lookup"><span data-stu-id="481c5-106">[in] The numeric identifier of the application domain to unload.</span></span>  
  
 `fWaitUntilDone`  
 <span data-ttu-id="481c5-107">[in] `true` для указания, что общеязыковой среды выполнения (CLR), необходимо дождаться завершения выполнения текущего потока приложения, прежде чем пытаться выгрузить домен приложения.</span><span class="sxs-lookup"><span data-stu-id="481c5-107">[in] `true` to indicate that the common language runtime( CLR) must wait until it has finished executing the application's current thread before attempting to unload the application domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="481c5-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="481c5-108">Return Value</span></span>  
  
|<span data-ttu-id="481c5-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="481c5-109">HRESULT</span></span>|<span data-ttu-id="481c5-110">Описание</span><span class="sxs-lookup"><span data-stu-id="481c5-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="481c5-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="481c5-111">S_OK</span></span>|<span data-ttu-id="481c5-112">`UnloadAppDomain`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="481c5-112">`UnloadAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="481c5-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="481c5-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="481c5-114">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="481c5-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="481c5-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="481c5-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="481c5-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="481c5-116">The call timed out.</span></span>|  
|<span data-ttu-id="481c5-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="481c5-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="481c5-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="481c5-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="481c5-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="481c5-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="481c5-120">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="481c5-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="481c5-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="481c5-121">E_FAIL</span></span>|<span data-ttu-id="481c5-122">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="481c5-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="481c5-123">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="481c5-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="481c5-124">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="481c5-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="481c5-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="481c5-125">Remarks</span></span>  
 <span data-ttu-id="481c5-126">Можно получить числовой идентификатор домена приложения, в которой выполняется текущий поток путем вызова [GetCurrentAppDomainId](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span><span class="sxs-lookup"><span data-stu-id="481c5-126">You can get the numeric identifier of the application domain in which the current thread is executing by calling [GetCurrentAppDomainId](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span></span> <span data-ttu-id="481c5-127">Этот идентификатор соответствует <xref:System.AppDomain.Id%2A> свойство управляемых <xref:System.AppDomain> типа.</span><span class="sxs-lookup"><span data-stu-id="481c5-127">This identifier corresponds to the <xref:System.AppDomain.Id%2A> property of the managed <xref:System.AppDomain> type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="481c5-128">Требования</span><span class="sxs-lookup"><span data-stu-id="481c5-128">Requirements</span></span>  
 <span data-ttu-id="481c5-129">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="481c5-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="481c5-130">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="481c5-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="481c5-131">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="481c5-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="481c5-132">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="481c5-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="481c5-133">См. также</span><span class="sxs-lookup"><span data-stu-id="481c5-133">See Also</span></span>  
 [<span data-ttu-id="481c5-134">Интерфейс ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="481c5-134">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)

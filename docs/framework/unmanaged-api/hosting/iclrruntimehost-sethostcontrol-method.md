---
title: "Метод ICLRRuntimeHost::SetHostControl"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeHost.SetHostControl
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeHost::SetHostControl
helpviewer_keywords:
- SetHostControl method [.NET Framework hosting]
- ICLRRuntimeHost::SetHostControl method [.NET Framework hosting]
ms.assetid: 6136be87-e631-4756-81ed-74b66581bad4
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9727144e9504a5a3ad7ae2529286440d07633b2a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iclrruntimehostsethostcontrol-method"></a><span data-ttu-id="7d902-102">Метод ICLRRuntimeHost::SetHostControl</span><span class="sxs-lookup"><span data-stu-id="7d902-102">ICLRRuntimeHost::SetHostControl Method</span></span>
<span data-ttu-id="7d902-103">Задает указатель интерфейса, общеязыковой среды выполнения (CLR) можно использовать для получения реализации [IHostControl-интерфейс](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md).</span><span class="sxs-lookup"><span data-stu-id="7d902-103">Sets the interface pointer that the common language runtime (CLR) can use to get the host's implementation of [IHostControl Interface](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d902-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7d902-104">Syntax</span></span>  
  
```  
HRESULT SetHostControl(  
    [in] IHostControl* pHostControl  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7d902-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7d902-105">Parameters</span></span>  
 `pHostControl`  
 <span data-ttu-id="7d902-106">[in] Указатель на интерфейс для реализации [IHostControl-интерфейс](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md).</span><span class="sxs-lookup"><span data-stu-id="7d902-106">[in] An interface pointer to the host's implementation of [IHostControl Interface](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7d902-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7d902-107">Return Value</span></span>  
  
|<span data-ttu-id="7d902-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7d902-108">HRESULT</span></span>|<span data-ttu-id="7d902-109">Описание</span><span class="sxs-lookup"><span data-stu-id="7d902-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7d902-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="7d902-110">S_OK</span></span>|<span data-ttu-id="7d902-111">`SetHostControl`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="7d902-111">`SetHostControl` returned successfully.</span></span>|  
|<span data-ttu-id="7d902-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7d902-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7d902-113">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="7d902-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7d902-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7d902-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7d902-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="7d902-115">The call timed out.</span></span>|  
|<span data-ttu-id="7d902-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7d902-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7d902-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="7d902-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7d902-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7d902-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7d902-119">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="7d902-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7d902-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7d902-120">E_FAIL</span></span>|<span data-ttu-id="7d902-121">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="7d902-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7d902-122">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="7d902-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7d902-123">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7d902-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7d902-124">E_CLR_ALREADY_STARTED</span><span class="sxs-lookup"><span data-stu-id="7d902-124">E_CLR_ALREADY_STARTED</span></span>|<span data-ttu-id="7d902-125">Среда CLR уже инициализирован.</span><span class="sxs-lookup"><span data-stu-id="7d902-125">The CLR has already been initialized.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7d902-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="7d902-126">Remarks</span></span>  
 <span data-ttu-id="7d902-127">Необходимо вызвать `SetHostControl` до инициализации среды CLR, то есть, перед вызовом метода [метод Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) или использовать любой из [интерфейсы метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="7d902-127">You must call `SetHostControl` before the CLR is initialized, that is, before you call [Start Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) or use any of the [Metadata Interfaces](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).</span></span> <span data-ttu-id="7d902-128">Рекомендуется вызывать `SetHostControl` сразу после вызова [corbindtocurrentruntime-функция](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md) или [функция CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md).</span><span class="sxs-lookup"><span data-stu-id="7d902-128">It is recommended that you call `SetHostControl` immediately after calling [CorBindToCurrentRuntime Function](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md) or [CorBindToRuntimeEx Function](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d902-129">Требования</span><span class="sxs-lookup"><span data-stu-id="7d902-129">Requirements</span></span>  
 <span data-ttu-id="7d902-130">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d902-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d902-131">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7d902-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7d902-132">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7d902-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7d902-133">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d902-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d902-134">См. также</span><span class="sxs-lookup"><span data-stu-id="7d902-134">See Also</span></span>  
 [<span data-ttu-id="7d902-135">Интерфейс ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="7d902-135">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 [<span data-ttu-id="7d902-136">Интерфейс IHostControl</span><span class="sxs-lookup"><span data-stu-id="7d902-136">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)

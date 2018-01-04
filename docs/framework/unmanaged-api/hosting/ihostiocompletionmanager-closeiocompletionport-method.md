---
title: "Метод IHostIoCompletionManager::CloseIoCompletionPort"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostIoCompletionManager.CloseIoCompletionPort
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostIoCompletionManager::CloseIoCompletionPort
helpviewer_keywords:
- IHostIoCompletionManager::CloseIoCompletionPort method [.NET Framework hosting]
- CloseIoCompletionPort method [.NET Framework hosting]
ms.assetid: e86ad7be-3758-498a-a972-5522d69dfbb3
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e74803cad610d5550ce8b52ce04295247617d907
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ihostiocompletionmanagercloseiocompletionport-method"></a><span data-ttu-id="f947a-102">Метод IHostIoCompletionManager::CloseIoCompletionPort</span><span class="sxs-lookup"><span data-stu-id="f947a-102">IHostIoCompletionManager::CloseIoCompletionPort Method</span></span>
<span data-ttu-id="f947a-103">Запросы, что узел закрыть порт, который был открыт по предыдущим вызовом [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span><span class="sxs-lookup"><span data-stu-id="f947a-103">Requests that the host close a port that was opened through an earlier call to [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f947a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f947a-104">Syntax</span></span>  
  
```  
HRESULT CloseIoCompletionPort (  
    [in] HANDLE hPort  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f947a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f947a-105">Parameters</span></span>  
 `hPort`  
 <span data-ttu-id="f947a-106">[in] Дескриптор для закрытия порта.</span><span class="sxs-lookup"><span data-stu-id="f947a-106">[in] The handle of the port to close.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f947a-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f947a-107">Return Value</span></span>  
  
|<span data-ttu-id="f947a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f947a-108">HRESULT</span></span>|<span data-ttu-id="f947a-109">Описание</span><span class="sxs-lookup"><span data-stu-id="f947a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f947a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f947a-110">S_OK</span></span>|<span data-ttu-id="f947a-111">`CloseIoCompletionPort`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="f947a-111">`CloseIoCompletionPort` returned successfully.</span></span>|  
|<span data-ttu-id="f947a-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f947a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f947a-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="f947a-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f947a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f947a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f947a-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="f947a-115">The call timed out.</span></span>|  
|<span data-ttu-id="f947a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f947a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f947a-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="f947a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f947a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f947a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f947a-119">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="f947a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f947a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f947a-120">E_FAIL</span></span>|<span data-ttu-id="f947a-121">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="f947a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f947a-122">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="f947a-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f947a-123">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f947a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f947a-124">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="f947a-124">E_INVALIDARG</span></span>|<span data-ttu-id="f947a-125">Передан недопустимый дескриптор порта.</span><span class="sxs-lookup"><span data-stu-id="f947a-125">An invalid port handle was passed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f947a-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="f947a-126">Remarks</span></span>  
 <span data-ttu-id="f947a-127">`hPort`должен быть дескриптор к порту, созданные предыдущими вызовами метода `CreateIoCompletionPort`.</span><span class="sxs-lookup"><span data-stu-id="f947a-127">`hPort` must be a handle to a port that was created by an earlier call to `CreateIoCompletionPort`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f947a-128">Требования</span><span class="sxs-lookup"><span data-stu-id="f947a-128">Requirements</span></span>  
 <span data-ttu-id="f947a-129">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f947a-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f947a-130">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f947a-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f947a-131">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f947a-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f947a-132">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f947a-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f947a-133">См. также</span><span class="sxs-lookup"><span data-stu-id="f947a-133">See Also</span></span>  
 [<span data-ttu-id="f947a-134">Интерфейс ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="f947a-134">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="f947a-135">Интерфейс IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="f947a-135">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)

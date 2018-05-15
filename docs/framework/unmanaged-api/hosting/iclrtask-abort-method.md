---
title: Метод ICLRTask::Abort
ms.date: 03/30/2017
api_name:
- ICLRTask.Abort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::Abort
helpviewer_keywords:
- ICLRTask::Abort method [.NET Framework hosting]
- Abort method, ICLRTask interface [.NET Framework hosting]
ms.assetid: b3594b5f-2e41-4e36-9096-3586276a138c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 46d60ff6ab64d57ca5c7020877758657b61125ad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="iclrtaskabort-method"></a><span data-ttu-id="917bd-102">Метод ICLRTask::Abort</span><span class="sxs-lookup"><span data-stu-id="917bd-102">ICLRTask::Abort Method</span></span>
<span data-ttu-id="917bd-103">Запрашивает прерывание задачи общеязыковой среды выполнения (CLR), текущий [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) представляет экземпляр.</span><span class="sxs-lookup"><span data-stu-id="917bd-103">Requests that the common language runtime (CLR) abort the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="917bd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="917bd-104">Syntax</span></span>  
  
```  
HRESULT Abort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="917bd-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="917bd-105">Return Value</span></span>  
  
|<span data-ttu-id="917bd-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="917bd-106">HRESULT</span></span>|<span data-ttu-id="917bd-107">Описание</span><span class="sxs-lookup"><span data-stu-id="917bd-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="917bd-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="917bd-108">S_OK</span></span>|<span data-ttu-id="917bd-109">`Abort` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="917bd-109">`Abort` returned successfully.</span></span>|  
|<span data-ttu-id="917bd-110">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="917bd-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="917bd-111">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="917bd-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="917bd-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="917bd-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="917bd-113">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="917bd-113">The call timed out.</span></span>|  
|<span data-ttu-id="917bd-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="917bd-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="917bd-115">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="917bd-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="917bd-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="917bd-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="917bd-117">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="917bd-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="917bd-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="917bd-118">E_FAIL</span></span>|<span data-ttu-id="917bd-119">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="917bd-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="917bd-120">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="917bd-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="917bd-121">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="917bd-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="917bd-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="917bd-122">Remarks</span></span>  
 <span data-ttu-id="917bd-123">Среда CLR вызывает <xref:System.Threading.ThreadAbortException> Если узел вызывает метод `Abort`.</span><span class="sxs-lookup"><span data-stu-id="917bd-123">The CLR raises a <xref:System.Threading.ThreadAbortException> when the host calls `Abort`.</span></span> <span data-ttu-id="917bd-124">Возвращается сразу после инициализации сведения об исключении, не ожидая пользовательский код, например методы завершения или механизмы обработки исключений, для выполнения.</span><span class="sxs-lookup"><span data-stu-id="917bd-124">It returns immediately after the exception information is initialized, without waiting for user code, such as finalizers or exception handling mechanisms, to execute.</span></span> <span data-ttu-id="917bd-125">Вызовы `Abort` тем самым быстро вернуться.</span><span class="sxs-lookup"><span data-stu-id="917bd-125">Calls to `Abort` thus return quickly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="917bd-126">Требования</span><span class="sxs-lookup"><span data-stu-id="917bd-126">Requirements</span></span>  
 <span data-ttu-id="917bd-127">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="917bd-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="917bd-128">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="917bd-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="917bd-129">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="917bd-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="917bd-130">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="917bd-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="917bd-131">См. также</span><span class="sxs-lookup"><span data-stu-id="917bd-131">See Also</span></span>  
 [<span data-ttu-id="917bd-132">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="917bd-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="917bd-133">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="917bd-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="917bd-134">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="917bd-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="917bd-135">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="917bd-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

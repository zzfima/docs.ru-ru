---
title: "Метод ICLRTask::NeedsPriorityScheduling"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask.NeedsPriorityScheduling
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask::NeedsPriorityScheduling
helpviewer_keywords:
- ICLRTask::NeedsPriorityScheduling method [.NET Framework hosting]
- NeedsPriorityScheduling method [.NET Framework hosting]
ms.assetid: 9c9db3f3-26bf-4317-88de-5eb926a22a1d
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 46da785535bef3443a1b917a5fb997e8e6ef3fa8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrtaskneedspriorityscheduling-method"></a><span data-ttu-id="fc5ff-102">Метод ICLRTask::NeedsPriorityScheduling</span><span class="sxs-lookup"><span data-stu-id="fc5ff-102">ICLRTask::NeedsPriorityScheduling Method</span></span>
<span data-ttu-id="fc5ff-103">Возвращает значение, указывающее, нужно ли текущую задачу, которая была отключена, помечается как с высоким приоритетом для изменения расписания.</span><span class="sxs-lookup"><span data-stu-id="fc5ff-103">Gets a value that indicates whether the current task, which is being switched out, needs to be marked as a high priority for rescheduling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc5ff-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fc5ff-104">Syntax</span></span>  
  
```  
HRESULT NeedsPriorityScheduling (  
    [out] BOOL *pbNeedsPriorityScheduling  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fc5ff-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fc5ff-105">Parameters</span></span>  
 `pbNeedsPriorityRescheduling`  
 <span data-ttu-id="fc5ff-106">[out] `true`, если узел должен попытаться повторно Запланировать текущий экземпляр задачи, как можно быстрее, в противном случае — `false`.</span><span class="sxs-lookup"><span data-stu-id="fc5ff-106">[out] `true`, if the host should attempt to reschedule the current task instance as soon as possible; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fc5ff-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fc5ff-107">Return Value</span></span>  
  
|<span data-ttu-id="fc5ff-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fc5ff-108">HRESULT</span></span>|<span data-ttu-id="fc5ff-109">Описание</span><span class="sxs-lookup"><span data-stu-id="fc5ff-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fc5ff-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="fc5ff-110">S_OK</span></span>|<span data-ttu-id="fc5ff-111">`NeedsPriorityRescheduling`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="fc5ff-111">`NeedsPriorityRescheduling` returned successfully.</span></span>|  
|<span data-ttu-id="fc5ff-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fc5ff-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fc5ff-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="fc5ff-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fc5ff-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fc5ff-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fc5ff-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="fc5ff-115">The call timed out.</span></span>|  
|<span data-ttu-id="fc5ff-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fc5ff-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fc5ff-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="fc5ff-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fc5ff-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fc5ff-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fc5ff-119">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="fc5ff-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fc5ff-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fc5ff-120">E_FAIL</span></span>|<span data-ttu-id="fc5ff-121">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="fc5ff-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fc5ff-122">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="fc5ff-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fc5ff-123">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="fc5ff-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fc5ff-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="fc5ff-124">Remarks</span></span>  
 <span data-ttu-id="fc5ff-125">В ситуациях, когда задача близко к сборщиком мусора, среда CLR задает значение `pbNeedsPriorityScheduling` для `true`, указывающее, Перепланирование высоким приоритетом.</span><span class="sxs-lookup"><span data-stu-id="fc5ff-125">In situations where the task is close to being collected by the garbage collector, the CLR sets the value of `pbNeedsPriorityScheduling` to `true`, indicating high-priority rescheduling.</span></span> <span data-ttu-id="fc5ff-126">Это позволяет основному задачу в расписание быстро, тем самым сводя к минимуму возможные задержки при сборке мусора, а также разрешают узла и среда выполнения взаимодействовать для сохранения ресурсов памяти.</span><span class="sxs-lookup"><span data-stu-id="fc5ff-126">This allows the host to reschedule the task quickly, thereby minimizing the potential for delays in garbage collection, and enabling the host and the runtime to cooperate in conserving memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc5ff-127">Требования</span><span class="sxs-lookup"><span data-stu-id="fc5ff-127">Requirements</span></span>  
 <span data-ttu-id="fc5ff-128">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc5ff-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc5ff-129">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fc5ff-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fc5ff-130">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fc5ff-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fc5ff-131">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc5ff-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc5ff-132">См. также</span><span class="sxs-lookup"><span data-stu-id="fc5ff-132">See Also</span></span>  
 [<span data-ttu-id="fc5ff-133">ICLRTask-интерфейс</span><span class="sxs-lookup"><span data-stu-id="fc5ff-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="fc5ff-134">ICLRTaskManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="fc5ff-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="fc5ff-135">IHostTask-интерфейс</span><span class="sxs-lookup"><span data-stu-id="fc5ff-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="fc5ff-136">IHostTaskManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="fc5ff-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

---
title: Метод ICLRTask::NeedsPriorityScheduling
ms.date: 03/30/2017
api_name:
- ICLRTask.NeedsPriorityScheduling
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::NeedsPriorityScheduling
helpviewer_keywords:
- ICLRTask::NeedsPriorityScheduling method [.NET Framework hosting]
- NeedsPriorityScheduling method [.NET Framework hosting]
ms.assetid: 9c9db3f3-26bf-4317-88de-5eb926a22a1d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9503e5aeeb1b59c8e62cab20736ea6ab7d5f629f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67758916"
---
# <a name="iclrtaskneedspriorityscheduling-method"></a><span data-ttu-id="f814a-102">Метод ICLRTask::NeedsPriorityScheduling</span><span class="sxs-lookup"><span data-stu-id="f814a-102">ICLRTask::NeedsPriorityScheduling Method</span></span>
<span data-ttu-id="f814a-103">Получает значение, указывающее, должен ли быть помечен как высокий приоритет для перепланирования текущую задачу, которая была отключена.</span><span class="sxs-lookup"><span data-stu-id="f814a-103">Gets a value that indicates whether the current task, which is being switched out, needs to be marked as a high priority for rescheduling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f814a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f814a-104">Syntax</span></span>  
  
```cpp  
HRESULT NeedsPriorityScheduling (  
    [out] BOOL *pbNeedsPriorityScheduling  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f814a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f814a-105">Parameters</span></span>  
 `pbNeedsPriorityRescheduling`  
 <span data-ttu-id="f814a-106">[out] `true`, если узел должен попытаться изменить расписание текущий экземпляр задачи, как можно скорее, в противном случае — `false`.</span><span class="sxs-lookup"><span data-stu-id="f814a-106">[out] `true`, if the host should attempt to reschedule the current task instance as soon as possible; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f814a-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f814a-107">Return Value</span></span>  
  
|<span data-ttu-id="f814a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f814a-108">HRESULT</span></span>|<span data-ttu-id="f814a-109">Описание</span><span class="sxs-lookup"><span data-stu-id="f814a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f814a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f814a-110">S_OK</span></span>|<span data-ttu-id="f814a-111">`NeedsPriorityRescheduling` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="f814a-111">`NeedsPriorityRescheduling` returned successfully.</span></span>|  
|<span data-ttu-id="f814a-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f814a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f814a-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="f814a-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f814a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f814a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f814a-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="f814a-115">The call timed out.</span></span>|  
|<span data-ttu-id="f814a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f814a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f814a-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="f814a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f814a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f814a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f814a-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="f814a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f814a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f814a-120">E_FAIL</span></span>|<span data-ttu-id="f814a-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="f814a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f814a-122">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="f814a-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f814a-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f814a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f814a-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="f814a-124">Remarks</span></span>  
 <span data-ttu-id="f814a-125">В случаях, когда задача слишком близко к сборщиком мусора, среда CLR задает значение `pbNeedsPriorityScheduling` для `true`, указывающее, является повторное высоким приоритетом.</span><span class="sxs-lookup"><span data-stu-id="f814a-125">In situations where the task is close to being collected by the garbage collector, the CLR sets the value of `pbNeedsPriorityScheduling` to `true`, indicating high-priority rescheduling.</span></span> <span data-ttu-id="f814a-126">Это позволяет узлу задачу в расписание, тем самым минимизируя возможные задержки при сборке мусора и включение узла и среды выполнения для совместной деятельности для сохранения ресурсов памяти.</span><span class="sxs-lookup"><span data-stu-id="f814a-126">This allows the host to reschedule the task quickly, thereby minimizing the potential for delays in garbage collection, and enabling the host and the runtime to cooperate in conserving memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f814a-127">Требования</span><span class="sxs-lookup"><span data-stu-id="f814a-127">Requirements</span></span>  
 <span data-ttu-id="f814a-128">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f814a-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f814a-129">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f814a-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f814a-130">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f814a-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f814a-131">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f814a-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f814a-132">См. также</span><span class="sxs-lookup"><span data-stu-id="f814a-132">See also</span></span>

- [<span data-ttu-id="f814a-133">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="f814a-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="f814a-134">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="f814a-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="f814a-135">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="f814a-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="f814a-136">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="f814a-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

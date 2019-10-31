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
ms.openlocfilehash: 91c1ea51969447861ff6d0956c5714baa0054450
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124670"
---
# <a name="iclrtaskneedspriorityscheduling-method"></a><span data-ttu-id="01a63-102">Метод ICLRTask::NeedsPriorityScheduling</span><span class="sxs-lookup"><span data-stu-id="01a63-102">ICLRTask::NeedsPriorityScheduling Method</span></span>
<span data-ttu-id="01a63-103">Возвращает значение, указывающее, нужно ли пометить текущую задачу, для которой выполняется переключение, в качестве высокого приоритета для повторного планирования.</span><span class="sxs-lookup"><span data-stu-id="01a63-103">Gets a value that indicates whether the current task, which is being switched out, needs to be marked as a high priority for rescheduling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01a63-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="01a63-104">Syntax</span></span>  
  
```cpp  
HRESULT NeedsPriorityScheduling (  
    [out] BOOL *pbNeedsPriorityScheduling  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="01a63-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="01a63-105">Parameters</span></span>  
 `pbNeedsPriorityRescheduling`  
 <span data-ttu-id="01a63-106">[out] `true`, если узел должен попытаться повторно запланировать текущий экземпляр задачи как можно скорее. в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="01a63-106">[out] `true`, if the host should attempt to reschedule the current task instance as soon as possible; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="01a63-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="01a63-107">Return Value</span></span>  
  
|<span data-ttu-id="01a63-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="01a63-108">HRESULT</span></span>|<span data-ttu-id="01a63-109">Описание</span><span class="sxs-lookup"><span data-stu-id="01a63-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="01a63-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="01a63-110">S_OK</span></span>|<span data-ttu-id="01a63-111">`NeedsPriorityRescheduling` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="01a63-111">`NeedsPriorityRescheduling` returned successfully.</span></span>|  
|<span data-ttu-id="01a63-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="01a63-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="01a63-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="01a63-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="01a63-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="01a63-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="01a63-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="01a63-115">The call timed out.</span></span>|  
|<span data-ttu-id="01a63-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="01a63-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="01a63-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="01a63-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="01a63-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="01a63-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="01a63-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="01a63-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="01a63-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="01a63-120">E_FAIL</span></span>|<span data-ttu-id="01a63-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="01a63-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="01a63-122">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="01a63-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="01a63-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="01a63-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="01a63-124">Заметки</span><span class="sxs-lookup"><span data-stu-id="01a63-124">Remarks</span></span>  
 <span data-ttu-id="01a63-125">В ситуациях, когда задача находится в близком к сбору сборщиком мусора, среда CLR задает для `pbNeedsPriorityScheduling` значение `true`, означающее перепланирование с высоким приоритетом.</span><span class="sxs-lookup"><span data-stu-id="01a63-125">In situations where the task is close to being collected by the garbage collector, the CLR sets the value of `pbNeedsPriorityScheduling` to `true`, indicating high-priority rescheduling.</span></span> <span data-ttu-id="01a63-126">Это позволяет основному приложению быстро планировать задачу, уменьшая вероятность задержек при сборке мусора и позволяя основному приложению и среде выполнения взаимодействовать для экономии ресурсов памяти.</span><span class="sxs-lookup"><span data-stu-id="01a63-126">This allows the host to reschedule the task quickly, thereby minimizing the potential for delays in garbage collection, and enabling the host and the runtime to cooperate in conserving memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01a63-127">Требования</span><span class="sxs-lookup"><span data-stu-id="01a63-127">Requirements</span></span>  
 <span data-ttu-id="01a63-128">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="01a63-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01a63-129">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="01a63-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="01a63-130">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="01a63-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="01a63-131">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01a63-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01a63-132">См. также</span><span class="sxs-lookup"><span data-stu-id="01a63-132">See also</span></span>

- [<span data-ttu-id="01a63-133">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="01a63-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="01a63-134">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="01a63-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="01a63-135">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="01a63-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="01a63-136">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="01a63-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

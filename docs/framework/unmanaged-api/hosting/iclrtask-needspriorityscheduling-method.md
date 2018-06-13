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
ms.openlocfilehash: 36403abcae4d4e691fe6362e61cf7fa979ec7f5e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435742"
---
# <a name="iclrtaskneedspriorityscheduling-method"></a><span data-ttu-id="dab28-102">Метод ICLRTask::NeedsPriorityScheduling</span><span class="sxs-lookup"><span data-stu-id="dab28-102">ICLRTask::NeedsPriorityScheduling Method</span></span>
<span data-ttu-id="dab28-103">Возвращает значение, указывающее, нужно ли текущую задачу, которая была отключена, помечается как с высоким приоритетом для изменения расписания.</span><span class="sxs-lookup"><span data-stu-id="dab28-103">Gets a value that indicates whether the current task, which is being switched out, needs to be marked as a high priority for rescheduling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dab28-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dab28-104">Syntax</span></span>  
  
```  
HRESULT NeedsPriorityScheduling (  
    [out] BOOL *pbNeedsPriorityScheduling  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dab28-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="dab28-105">Parameters</span></span>  
 `pbNeedsPriorityRescheduling`  
 <span data-ttu-id="dab28-106">[out] `true`, если узел должен попытаться повторно Запланировать текущий экземпляр задачи, как можно быстрее, в противном случае — `false`.</span><span class="sxs-lookup"><span data-stu-id="dab28-106">[out] `true`, if the host should attempt to reschedule the current task instance as soon as possible; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dab28-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="dab28-107">Return Value</span></span>  
  
|<span data-ttu-id="dab28-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dab28-108">HRESULT</span></span>|<span data-ttu-id="dab28-109">Описание</span><span class="sxs-lookup"><span data-stu-id="dab28-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dab28-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="dab28-110">S_OK</span></span>|<span data-ttu-id="dab28-111">`NeedsPriorityRescheduling` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="dab28-111">`NeedsPriorityRescheduling` returned successfully.</span></span>|  
|<span data-ttu-id="dab28-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="dab28-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="dab28-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="dab28-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="dab28-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="dab28-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="dab28-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="dab28-115">The call timed out.</span></span>|  
|<span data-ttu-id="dab28-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="dab28-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="dab28-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="dab28-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="dab28-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="dab28-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="dab28-119">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="dab28-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="dab28-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="dab28-120">E_FAIL</span></span>|<span data-ttu-id="dab28-121">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="dab28-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="dab28-122">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="dab28-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="dab28-123">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="dab28-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dab28-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="dab28-124">Remarks</span></span>  
 <span data-ttu-id="dab28-125">В ситуациях, когда задача близко к сборщиком мусора, среда CLR задает значение `pbNeedsPriorityScheduling` для `true`, указывающее, Перепланирование высоким приоритетом.</span><span class="sxs-lookup"><span data-stu-id="dab28-125">In situations where the task is close to being collected by the garbage collector, the CLR sets the value of `pbNeedsPriorityScheduling` to `true`, indicating high-priority rescheduling.</span></span> <span data-ttu-id="dab28-126">Это позволяет основному задачу в расписание быстро, тем самым сводя к минимуму возможные задержки при сборке мусора, а также разрешают узла и среда выполнения взаимодействовать для сохранения ресурсов памяти.</span><span class="sxs-lookup"><span data-stu-id="dab28-126">This allows the host to reschedule the task quickly, thereby minimizing the potential for delays in garbage collection, and enabling the host and the runtime to cooperate in conserving memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dab28-127">Требования</span><span class="sxs-lookup"><span data-stu-id="dab28-127">Requirements</span></span>  
 <span data-ttu-id="dab28-128">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dab28-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dab28-129">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="dab28-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dab28-130">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dab28-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dab28-131">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dab28-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dab28-132">См. также</span><span class="sxs-lookup"><span data-stu-id="dab28-132">See Also</span></span>  
 [<span data-ttu-id="dab28-133">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="dab28-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="dab28-134">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="dab28-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="dab28-135">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="dab28-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="dab28-136">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="dab28-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

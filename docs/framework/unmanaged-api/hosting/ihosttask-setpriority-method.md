---
title: Метод IHostTask::SetPriority
ms.date: 03/30/2017
api_name:
- IHostTask.SetPriority
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::SetPriority
helpviewer_keywords:
- IHostTask::SetPriority method [.NET Framework hosting]
- SetPriority method [.NET Framework hosting]
ms.assetid: cd8c379b-c7a0-434f-8e23-899bd26be75d
topic_type:
- apiref
ms.openlocfilehash: c64cee9ec9b62d87e0c4ae1aafaff59bb985ec95
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121358"
---
# <a name="ihosttasksetpriority-method"></a><span data-ttu-id="4caab-102">Метод IHostTask::SetPriority</span><span class="sxs-lookup"><span data-stu-id="4caab-102">IHostTask::SetPriority Method</span></span>
<span data-ttu-id="4caab-103">Запрашивает у узла настройку уровня приоритета потока для задачи, представленной текущим экземпляром [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="4caab-103">Requests that the host adjust the thread priority level for the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4caab-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4caab-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPriority (  
    [in] int newPriority  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4caab-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4caab-105">Parameters</span></span>  
 `newPriority`  
 <span data-ttu-id="4caab-106">окне Целое число, представляющее запрошенное значение приоритета потока для задачи, представленной текущим экземпляром `IHostTask`.</span><span class="sxs-lookup"><span data-stu-id="4caab-106">[in] An integer that represents the requested thread priority value for the task represented by the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4caab-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4caab-107">Return Value</span></span>  
  
|<span data-ttu-id="4caab-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4caab-108">HRESULT</span></span>|<span data-ttu-id="4caab-109">Описание</span><span class="sxs-lookup"><span data-stu-id="4caab-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4caab-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="4caab-110">S_OK</span></span>|<span data-ttu-id="4caab-111">`SetPriority` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="4caab-111">`SetPriority` returned successfully.</span></span>|  
|<span data-ttu-id="4caab-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4caab-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4caab-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="4caab-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4caab-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4caab-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4caab-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="4caab-115">The call timed out.</span></span>|  
|<span data-ttu-id="4caab-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4caab-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4caab-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="4caab-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4caab-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4caab-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4caab-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="4caab-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4caab-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4caab-120">E_FAIL</span></span>|<span data-ttu-id="4caab-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="4caab-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4caab-122">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="4caab-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4caab-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4caab-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4caab-124">Заметки</span><span class="sxs-lookup"><span data-stu-id="4caab-124">Remarks</span></span>  
 <span data-ttu-id="4caab-125">Потокам предоставляется время обработки с помощью системы циклического перебора, частично основанной на уровне приоритета потока.</span><span class="sxs-lookup"><span data-stu-id="4caab-125">Threads are granted processing time using a round-robin system that is partly based on a thread's priority level.</span></span> <span data-ttu-id="4caab-126">`SetPriority` позволяет среде CLR установить этот уровень приоритета потока для текущей задачи.</span><span class="sxs-lookup"><span data-stu-id="4caab-126">`SetPriority` allows the CLR to set that thread priority level for the current task.</span></span> <span data-ttu-id="4caab-127">Поддерживаются следующие значения `newPriority`.</span><span class="sxs-lookup"><span data-stu-id="4caab-127">The following `newPriority` values are supported.</span></span>  
  
- <span data-ttu-id="4caab-128">THREAD_PRIORITY_ABOVE_NORMAL</span><span class="sxs-lookup"><span data-stu-id="4caab-128">THREAD_PRIORITY_ABOVE_NORMAL</span></span>  
  
- <span data-ttu-id="4caab-129">THREAD_PRIORITY_BELOW_NORMAL</span><span class="sxs-lookup"><span data-stu-id="4caab-129">THREAD_PRIORITY_BELOW_NORMAL</span></span>  
  
- <span data-ttu-id="4caab-130">THREAD_PRIORITY_HIGHEST</span><span class="sxs-lookup"><span data-stu-id="4caab-130">THREAD_PRIORITY_HIGHEST</span></span>  
  
- <span data-ttu-id="4caab-131">THREAD_PRIORITY_IDLE</span><span class="sxs-lookup"><span data-stu-id="4caab-131">THREAD_PRIORITY_IDLE</span></span>  
  
- <span data-ttu-id="4caab-132">THREAD_PRIORITY_LOWEST</span><span class="sxs-lookup"><span data-stu-id="4caab-132">THREAD_PRIORITY_LOWEST</span></span>  
  
- <span data-ttu-id="4caab-133">THREAD_PRIORITY_NORMAL</span><span class="sxs-lookup"><span data-stu-id="4caab-133">THREAD_PRIORITY_NORMAL</span></span>  
  
- <span data-ttu-id="4caab-134">THREAD_PRIORITY_TIME_CRITICAL</span><span class="sxs-lookup"><span data-stu-id="4caab-134">THREAD_PRIORITY_TIME_CRITICAL</span></span>  
  
 <span data-ttu-id="4caab-135">Среда CLR вызывает `SetPriority`, когда значение <xref:System.Threading.Thread.Priority%2A?displayProperty=nameWithType> изменяется кодом пользователя.</span><span class="sxs-lookup"><span data-stu-id="4caab-135">The CLR calls `SetPriority` when the value of the <xref:System.Threading.Thread.Priority%2A?displayProperty=nameWithType> is modified by user code.</span></span> <span data-ttu-id="4caab-136">Узел может определять собственные алгоритмы для назначения приоритета потоков и может без необходимости пропускать этот запрос.</span><span class="sxs-lookup"><span data-stu-id="4caab-136">A host can define its own algorithms for thread priority assignment, and is free to ignore this request.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4caab-137">`SetPriority` не сообщает, был ли изменен уровень приоритета потока.</span><span class="sxs-lookup"><span data-stu-id="4caab-137">`SetPriority` does not report whether the thread priority level was changed.</span></span> <span data-ttu-id="4caab-138">Вызовите метод [IHostTask:: предшествовал](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md) , чтобы определить значение уровня приоритета потока задачи.</span><span class="sxs-lookup"><span data-stu-id="4caab-138">Call [IHostTask::GetPriority](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md) to determine the value of the task's thread priority level.</span></span>  
  
 <span data-ttu-id="4caab-139">Значения уровня приоритета потока определяются функцией Win32 `SetThreadPriority`.</span><span class="sxs-lookup"><span data-stu-id="4caab-139">Thread priority level values are defined by the Win32 `SetThreadPriority` function.</span></span> <span data-ttu-id="4caab-140">Дополнительные сведения о приоритете потоков см. в документации по платформе Windows.</span><span class="sxs-lookup"><span data-stu-id="4caab-140">For more information about thread priority, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4caab-141">Требования</span><span class="sxs-lookup"><span data-stu-id="4caab-141">Requirements</span></span>  
 <span data-ttu-id="4caab-142">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4caab-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4caab-143">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="4caab-143">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4caab-144">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4caab-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4caab-145">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4caab-145">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4caab-146">См. также</span><span class="sxs-lookup"><span data-stu-id="4caab-146">See also</span></span>

- <xref:System.Threading.Thread>
- [<span data-ttu-id="4caab-147">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="4caab-147">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="4caab-148">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="4caab-148">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="4caab-149">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="4caab-149">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="4caab-150">Метод GetPriority</span><span class="sxs-lookup"><span data-stu-id="4caab-150">GetPriority Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)
- [<span data-ttu-id="4caab-151">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="4caab-151">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

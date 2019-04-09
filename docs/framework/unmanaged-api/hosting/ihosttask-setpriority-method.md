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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c5382341a8c0c6455438af9e8c476348ab2467a6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59189044"
---
# <a name="ihosttasksetpriority-method"></a><span data-ttu-id="c66da-102">Метод IHostTask::SetPriority</span><span class="sxs-lookup"><span data-stu-id="c66da-102">IHostTask::SetPriority Method</span></span>
<span data-ttu-id="c66da-103">Уровень запросов, настройки, узел приоритет потока для задачи, представленный текущим [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="c66da-103">Requests that the host adjust the thread priority level for the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c66da-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c66da-104">Syntax</span></span>  
  
```  
HRESULT SetPriority (  
    [in] int newPriority  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c66da-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c66da-105">Parameters</span></span>  
 `newPriority`  
 <span data-ttu-id="c66da-106">[in] Целое число, представляющее значение приоритета запрошенный поток для задачи, представленный текущим `IHostTask` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="c66da-106">[in] An integer that represents the requested thread priority value for the task represented by the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c66da-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c66da-107">Return Value</span></span>  
  
|<span data-ttu-id="c66da-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c66da-108">HRESULT</span></span>|<span data-ttu-id="c66da-109">Описание</span><span class="sxs-lookup"><span data-stu-id="c66da-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c66da-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c66da-110">S_OK</span></span>|`SetPriority` <span data-ttu-id="c66da-111">успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="c66da-111">returned successfully.</span></span>|  
|<span data-ttu-id="c66da-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c66da-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c66da-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="c66da-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c66da-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c66da-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c66da-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="c66da-115">The call timed out.</span></span>|  
|<span data-ttu-id="c66da-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c66da-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c66da-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="c66da-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c66da-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c66da-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c66da-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="c66da-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c66da-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c66da-120">E_FAIL</span></span>|<span data-ttu-id="c66da-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="c66da-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c66da-122">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="c66da-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c66da-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c66da-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c66da-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="c66da-124">Remarks</span></span>  
 <span data-ttu-id="c66da-125">Потоки время выполнения предоставляется с помощью системы циклический перебор, частично основывается на уровень приоритета потока.</span><span class="sxs-lookup"><span data-stu-id="c66da-125">Threads are granted processing time using a round-robin system that is partly based on a thread's priority level.</span></span> `SetPriority` <span data-ttu-id="c66da-126">позволяет среде CLR задать уровень приоритета потока для текущей задачи.</span><span class="sxs-lookup"><span data-stu-id="c66da-126">allows the CLR to set that thread priority level for the current task.</span></span> <span data-ttu-id="c66da-127">Следующие `newPriority` значения поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="c66da-127">The following `newPriority` values are supported.</span></span>  
  
-   <span data-ttu-id="c66da-128">THREAD_PRIORITY_ABOVE_NORMAL</span><span class="sxs-lookup"><span data-stu-id="c66da-128">THREAD_PRIORITY_ABOVE_NORMAL</span></span>  
  
-   <span data-ttu-id="c66da-129">THREAD_PRIORITY_BELOW_NORMAL</span><span class="sxs-lookup"><span data-stu-id="c66da-129">THREAD_PRIORITY_BELOW_NORMAL</span></span>  
  
-   <span data-ttu-id="c66da-130">THREAD_PRIORITY_HIGHEST</span><span class="sxs-lookup"><span data-stu-id="c66da-130">THREAD_PRIORITY_HIGHEST</span></span>  
  
-   <span data-ttu-id="c66da-131">THREAD_PRIORITY_IDLE</span><span class="sxs-lookup"><span data-stu-id="c66da-131">THREAD_PRIORITY_IDLE</span></span>  
  
-   <span data-ttu-id="c66da-132">НАИНИЗШИЙ</span><span class="sxs-lookup"><span data-stu-id="c66da-132">THREAD_PRIORITY_LOWEST</span></span>  
  
-   <span data-ttu-id="c66da-133">THREAD_PRIORITY_NORMAL</span><span class="sxs-lookup"><span data-stu-id="c66da-133">THREAD_PRIORITY_NORMAL</span></span>  
  
-   <span data-ttu-id="c66da-134">THREAD_PRIORITY_TIME_CRITICAL</span><span class="sxs-lookup"><span data-stu-id="c66da-134">THREAD_PRIORITY_TIME_CRITICAL</span></span>  
  
 <span data-ttu-id="c66da-135">Среда CLR вызывает `SetPriority` при значение <xref:System.Threading.Thread.Priority%2A?displayProperty=nameWithType> изменяется с помощью пользовательского кода.</span><span class="sxs-lookup"><span data-stu-id="c66da-135">The CLR calls `SetPriority` when the value of the <xref:System.Threading.Thread.Priority%2A?displayProperty=nameWithType> is modified by user code.</span></span> <span data-ttu-id="c66da-136">Узел можно определить собственные алгоритмы для назначения приоритета потоков и игнорировать этот запрос.</span><span class="sxs-lookup"><span data-stu-id="c66da-136">A host can define its own algorithms for thread priority assignment, and is free to ignore this request.</span></span>  
  
> [!NOTE]
>  `SetPriority` <span data-ttu-id="c66da-137">не сообщать, был ли изменен уровень приоритета потока.</span><span class="sxs-lookup"><span data-stu-id="c66da-137">does not report whether the thread priority level was changed.</span></span> <span data-ttu-id="c66da-138">Вызовите [IHostTask::GetPriority](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md) для определения значения уровня приоритета потока задачи.</span><span class="sxs-lookup"><span data-stu-id="c66da-138">Call [IHostTask::GetPriority](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md) to determine the value of the task's thread priority level.</span></span>  
  
 <span data-ttu-id="c66da-139">Значения уровня приоритета потока определяются Win32 `SetThreadPriority` функции.</span><span class="sxs-lookup"><span data-stu-id="c66da-139">Thread priority level values are defined by the Win32 `SetThreadPriority` function.</span></span> <span data-ttu-id="c66da-140">Дополнительные сведения о приоритете потока см. в документации платформы Windows.</span><span class="sxs-lookup"><span data-stu-id="c66da-140">For more information about thread priority, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c66da-141">Требования</span><span class="sxs-lookup"><span data-stu-id="c66da-141">Requirements</span></span>  
 <span data-ttu-id="c66da-142">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c66da-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c66da-143">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c66da-143">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c66da-144">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c66da-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="c66da-145">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="c66da-145">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c66da-146">См. также</span><span class="sxs-lookup"><span data-stu-id="c66da-146">See also</span></span>

- <xref:System.Threading.Thread>
- [<span data-ttu-id="c66da-147">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="c66da-147">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="c66da-148">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="c66da-148">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="c66da-149">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="c66da-149">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="c66da-150">Метод GetPriority</span><span class="sxs-lookup"><span data-stu-id="c66da-150">GetPriority Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)
- [<span data-ttu-id="c66da-151">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="c66da-151">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

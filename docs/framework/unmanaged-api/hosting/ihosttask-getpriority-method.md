---
title: Метод IHostTask::GetPriority
ms.date: 03/30/2017
api_name:
- IHostTask.GetPriority
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::GetPriority
helpviewer_keywords:
- GetPriority method [.NET Framework hosting]
- IHostTask::GetPriority method [.NET Framework hosting]
ms.assetid: 4b463cd6-77c1-4f9a-8518-346ad8fc4b70
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 45597f6bb5e050f4afc00bd8f2db8116b29b8d4b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57482227"
---
# <a name="ihosttaskgetpriority-method"></a><span data-ttu-id="dd08c-102">Метод IHostTask::GetPriority</span><span class="sxs-lookup"><span data-stu-id="dd08c-102">IHostTask::GetPriority Method</span></span>
<span data-ttu-id="dd08c-103">Возвращает уровень приоритета потока задачи, представленный текущим [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="dd08c-103">Gets the thread priority level of the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd08c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dd08c-104">Syntax</span></span>  
  
```  
HRESULT GetPriority (  
    [out] int *pPriority  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dd08c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="dd08c-105">Parameters</span></span>  
 `pPriority`  
 <span data-ttu-id="dd08c-106">[out] Указатель на целое число, указывающее уровень приоритета потока задачи, представленный текущим `IHostTask` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="dd08c-106">[out] A pointer to an integer that indicates the thread priority level of the task represented by the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dd08c-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="dd08c-107">Return Value</span></span>  
  
|<span data-ttu-id="dd08c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dd08c-108">HRESULT</span></span>|<span data-ttu-id="dd08c-109">Описание</span><span class="sxs-lookup"><span data-stu-id="dd08c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dd08c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="dd08c-110">S_OK</span></span>|<span data-ttu-id="dd08c-111">`GetPriority` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="dd08c-111">`GetPriority` returned successfully.</span></span>|  
|<span data-ttu-id="dd08c-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="dd08c-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="dd08c-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="dd08c-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="dd08c-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="dd08c-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="dd08c-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="dd08c-115">The call timed out.</span></span>|  
|<span data-ttu-id="dd08c-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="dd08c-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="dd08c-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="dd08c-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="dd08c-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="dd08c-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="dd08c-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="dd08c-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="dd08c-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="dd08c-120">E_FAIL</span></span>|<span data-ttu-id="dd08c-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="dd08c-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="dd08c-122">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="dd08c-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="dd08c-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="dd08c-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dd08c-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="dd08c-124">Remarks</span></span>  
 <span data-ttu-id="dd08c-125">Значения уровня приоритета потока определяются Win32 `SetThreadPriority` функции.</span><span class="sxs-lookup"><span data-stu-id="dd08c-125">Thread priority level values are defined by the Win32 `SetThreadPriority` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd08c-126">Требования</span><span class="sxs-lookup"><span data-stu-id="dd08c-126">Requirements</span></span>  
 <span data-ttu-id="dd08c-127">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd08c-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd08c-128">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="dd08c-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dd08c-129">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dd08c-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dd08c-130">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd08c-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd08c-131">См. также</span><span class="sxs-lookup"><span data-stu-id="dd08c-131">See also</span></span>
- [<span data-ttu-id="dd08c-132">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="dd08c-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="dd08c-133">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="dd08c-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="dd08c-134">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="dd08c-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="dd08c-135">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="dd08c-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

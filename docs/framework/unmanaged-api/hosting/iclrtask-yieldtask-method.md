---
title: Метод ICLRTask::YieldTask
ms.date: 03/30/2017
api_name:
- ICLRTask.YieldTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::YieldTask
helpviewer_keywords:
- ICLRTask::YieldTask method [.NET Framework hosting]
- YieldTask method [.NET Framework hosting]
ms.assetid: b8eb4095-3a8f-4be3-9446-63e9893dce7d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bc8d936ac4fca704e7e3069209d8ff75d46b044d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59113676"
---
# <a name="iclrtaskyieldtask-method"></a><span data-ttu-id="292b4-102">Метод ICLRTask::YieldTask</span><span class="sxs-lookup"><span data-stu-id="292b4-102">ICLRTask::YieldTask Method</span></span>
<span data-ttu-id="292b4-103">Запросы, что общеязыковая среда выполнения (CLR) отложить задачу, текущий [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) представленное экземпляром и сделать доступным для других задач времени процессора.</span><span class="sxs-lookup"><span data-stu-id="292b4-103">Requests that the common language runtime (CLR) put aside the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents, and make the processor time available to other tasks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="292b4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="292b4-104">Syntax</span></span>  
  
```  
HRESULT YieldTask ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="292b4-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="292b4-105">Return Value</span></span>  
  
|<span data-ttu-id="292b4-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="292b4-106">HRESULT</span></span>|<span data-ttu-id="292b4-107">Описание</span><span class="sxs-lookup"><span data-stu-id="292b4-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="292b4-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="292b4-108">S_OK</span></span>|<span data-ttu-id="292b4-109">`YieldTask` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="292b4-109">`YieldTask` returned successfully.</span></span>|  
|<span data-ttu-id="292b4-110">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="292b4-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="292b4-111">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="292b4-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="292b4-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="292b4-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="292b4-113">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="292b4-113">The call timed out.</span></span>|  
|<span data-ttu-id="292b4-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="292b4-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="292b4-115">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="292b4-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="292b4-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="292b4-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="292b4-117">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="292b4-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="292b4-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="292b4-118">E_FAIL</span></span>|<span data-ttu-id="292b4-119">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="292b4-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="292b4-120">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="292b4-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="292b4-121">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="292b4-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="292b4-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="292b4-122">Remarks</span></span>  
 <span data-ttu-id="292b4-123">Узел вызывает `YieldTask` для запроса ресурсов процессора для других задач или процессов.</span><span class="sxs-lookup"><span data-stu-id="292b4-123">A host calls `YieldTask` to request processor resources for other tasks or processes.</span></span> <span data-ttu-id="292b4-124">Этот метод предназначен главным образом, разрешающий коду выполняющейся длительное время освобождать время ЦП.</span><span class="sxs-lookup"><span data-stu-id="292b4-124">This method is primarily intended to allow long-running code to give up CPU time.</span></span> <span data-ttu-id="292b4-125">Среда выполнения пытается перевести задачу, текущий `ICLRTask` представляет экземпляр в состоянии, когда он может дать время обработки, но не гарантирует успеха.</span><span class="sxs-lookup"><span data-stu-id="292b4-125">The runtime attempts to put the task that the current `ICLRTask` instance represents in a state where it can yield processing time, but makes no guarantee of success.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="292b4-126">Требования</span><span class="sxs-lookup"><span data-stu-id="292b4-126">Requirements</span></span>  
 <span data-ttu-id="292b4-127">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="292b4-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="292b4-128">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="292b4-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="292b4-129">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="292b4-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="292b4-130">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="292b4-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="292b4-131">См. также</span><span class="sxs-lookup"><span data-stu-id="292b4-131">See also</span></span>

- [<span data-ttu-id="292b4-132">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="292b4-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="292b4-133">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="292b4-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="292b4-134">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="292b4-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="292b4-135">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="292b4-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

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
ms.openlocfilehash: 44716e0c763fe71fe94c8c0ec247cd37379561ec
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54682895"
---
# <a name="iclrtaskyieldtask-method"></a><span data-ttu-id="a25ce-102">Метод ICLRTask::YieldTask</span><span class="sxs-lookup"><span data-stu-id="a25ce-102">ICLRTask::YieldTask Method</span></span>
<span data-ttu-id="a25ce-103">Запросы, что общеязыковая среда выполнения (CLR) отложить задачу, текущий [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) представленное экземпляром и сделать доступным для других задач времени процессора.</span><span class="sxs-lookup"><span data-stu-id="a25ce-103">Requests that the common language runtime (CLR) put aside the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents, and make the processor time available to other tasks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a25ce-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a25ce-104">Syntax</span></span>  
  
```  
HRESULT YieldTask ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="a25ce-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a25ce-105">Return Value</span></span>  
  
|<span data-ttu-id="a25ce-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a25ce-106">HRESULT</span></span>|<span data-ttu-id="a25ce-107">Описание</span><span class="sxs-lookup"><span data-stu-id="a25ce-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a25ce-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="a25ce-108">S_OK</span></span>|<span data-ttu-id="a25ce-109">`YieldTask` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="a25ce-109">`YieldTask` returned successfully.</span></span>|  
|<span data-ttu-id="a25ce-110">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a25ce-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a25ce-111">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="a25ce-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a25ce-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a25ce-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a25ce-113">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="a25ce-113">The call timed out.</span></span>|  
|<span data-ttu-id="a25ce-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a25ce-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a25ce-115">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="a25ce-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a25ce-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a25ce-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a25ce-117">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="a25ce-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a25ce-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a25ce-118">E_FAIL</span></span>|<span data-ttu-id="a25ce-119">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="a25ce-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a25ce-120">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="a25ce-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a25ce-121">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a25ce-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a25ce-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="a25ce-122">Remarks</span></span>  
 <span data-ttu-id="a25ce-123">Узел вызывает `YieldTask` для запроса ресурсов процессора для других задач или процессов.</span><span class="sxs-lookup"><span data-stu-id="a25ce-123">A host calls `YieldTask` to request processor resources for other tasks or processes.</span></span> <span data-ttu-id="a25ce-124">Этот метод предназначен главным образом, разрешающий коду выполняющейся длительное время освобождать время ЦП.</span><span class="sxs-lookup"><span data-stu-id="a25ce-124">This method is primarily intended to allow long-running code to give up CPU time.</span></span> <span data-ttu-id="a25ce-125">Среда выполнения пытается перевести задачу, текущий `ICLRTask` представляет экземпляр в состоянии, когда он может дать время обработки, но не гарантирует успеха.</span><span class="sxs-lookup"><span data-stu-id="a25ce-125">The runtime attempts to put the task that the current `ICLRTask` instance represents in a state where it can yield processing time, but makes no guarantee of success.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a25ce-126">Требования</span><span class="sxs-lookup"><span data-stu-id="a25ce-126">Requirements</span></span>  
 <span data-ttu-id="a25ce-127">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a25ce-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a25ce-128">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a25ce-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a25ce-129">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a25ce-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a25ce-130">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a25ce-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a25ce-131">См. также</span><span class="sxs-lookup"><span data-stu-id="a25ce-131">See also</span></span>
- [<span data-ttu-id="a25ce-132">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="a25ce-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="a25ce-133">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="a25ce-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="a25ce-134">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="a25ce-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="a25ce-135">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="a25ce-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

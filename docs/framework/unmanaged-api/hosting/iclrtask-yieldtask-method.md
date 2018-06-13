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
ms.openlocfilehash: 821f524cc8ff7f9983f811f539e2badb2306be26
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437707"
---
# <a name="iclrtaskyieldtask-method"></a><span data-ttu-id="053fe-102">Метод ICLRTask::YieldTask</span><span class="sxs-lookup"><span data-stu-id="053fe-102">ICLRTask::YieldTask Method</span></span>
<span data-ttu-id="053fe-103">Запросы, что общеязыковой среды выполнения (CLR) отложить задачу, текущий [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) представляет экземпляр и сделать доступным для других задач процессорного времени.</span><span class="sxs-lookup"><span data-stu-id="053fe-103">Requests that the common language runtime (CLR) put aside the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents, and make the processor time available to other tasks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="053fe-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="053fe-104">Syntax</span></span>  
  
```  
HRESULT YieldTask ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="053fe-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="053fe-105">Return Value</span></span>  
  
|<span data-ttu-id="053fe-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="053fe-106">HRESULT</span></span>|<span data-ttu-id="053fe-107">Описание</span><span class="sxs-lookup"><span data-stu-id="053fe-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="053fe-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="053fe-108">S_OK</span></span>|<span data-ttu-id="053fe-109">`YieldTask` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="053fe-109">`YieldTask` returned successfully.</span></span>|  
|<span data-ttu-id="053fe-110">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="053fe-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="053fe-111">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="053fe-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="053fe-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="053fe-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="053fe-113">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="053fe-113">The call timed out.</span></span>|  
|<span data-ttu-id="053fe-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="053fe-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="053fe-115">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="053fe-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="053fe-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="053fe-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="053fe-117">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="053fe-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="053fe-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="053fe-118">E_FAIL</span></span>|<span data-ttu-id="053fe-119">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="053fe-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="053fe-120">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="053fe-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="053fe-121">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="053fe-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="053fe-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="053fe-122">Remarks</span></span>  
 <span data-ttu-id="053fe-123">Узел вызывает `YieldTask` для запроса ресурсов процессора для других задач или процессов.</span><span class="sxs-lookup"><span data-stu-id="053fe-123">A host calls `YieldTask` to request processor resources for other tasks or processes.</span></span> <span data-ttu-id="053fe-124">Этот метод в основном предназначен для предоставления времени ЦП долго выполняющихся кодом.</span><span class="sxs-lookup"><span data-stu-id="053fe-124">This method is primarily intended to allow long-running code to give up CPU time.</span></span> <span data-ttu-id="053fe-125">Среда выполнения пытается перевести задачу, текущий `ICLRTask` представляет экземпляр в состоянии, где его сможет выделить время обработки, но не гарантирует успешности.</span><span class="sxs-lookup"><span data-stu-id="053fe-125">The runtime attempts to put the task that the current `ICLRTask` instance represents in a state where it can yield processing time, but makes no guarantee of success.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="053fe-126">Требования</span><span class="sxs-lookup"><span data-stu-id="053fe-126">Requirements</span></span>  
 <span data-ttu-id="053fe-127">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="053fe-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="053fe-128">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="053fe-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="053fe-129">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="053fe-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="053fe-130">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="053fe-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="053fe-131">См. также</span><span class="sxs-lookup"><span data-stu-id="053fe-131">See Also</span></span>  
 [<span data-ttu-id="053fe-132">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="053fe-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="053fe-133">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="053fe-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="053fe-134">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="053fe-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="053fe-135">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="053fe-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

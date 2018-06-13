---
title: Метод ICLRTask::ExitTask
ms.date: 03/30/2017
api_name:
- ICLRTask.ExitTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::ExitTask
helpviewer_keywords:
- ExitTask method [.NET Framework hosting]
- ICLRTask::ExitTask method [.NET Framework hosting]
ms.assetid: 746c85a6-4b33-4f72-a2e9-379fdf2e96af
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3391ed2be03c965807a1c6cad89579cea4015693
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434568"
---
# <a name="iclrtaskexittask-method"></a><span data-ttu-id="89668-102">Метод ICLRTask::ExitTask</span><span class="sxs-lookup"><span data-stu-id="89668-102">ICLRTask::ExitTask Method</span></span>
<span data-ttu-id="89668-103">Уведомляет среду (CLR), задача, представленная текущим [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) экземпляра заканчивается и пытается корректно задача завершается.</span><span class="sxs-lookup"><span data-stu-id="89668-103">Notifies the common language runtime (CLR) that the task represented by the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance is ending, and attempts to shut the task down gracefully.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89668-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="89668-104">Syntax</span></span>  
  
```  
HRESULT ExitTask ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="89668-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="89668-105">Return Value</span></span>  
  
|<span data-ttu-id="89668-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="89668-106">HRESULT</span></span>|<span data-ttu-id="89668-107">Описание</span><span class="sxs-lookup"><span data-stu-id="89668-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="89668-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="89668-108">S_OK</span></span>|<span data-ttu-id="89668-109">`ExitTask` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="89668-109">`ExitTask` returned successfully.</span></span>|  
|<span data-ttu-id="89668-110">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="89668-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="89668-111">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="89668-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="89668-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="89668-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="89668-113">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="89668-113">The call timed out.</span></span>|  
|<span data-ttu-id="89668-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="89668-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="89668-115">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="89668-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="89668-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="89668-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="89668-117">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="89668-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="89668-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="89668-118">E_FAIL</span></span>|<span data-ttu-id="89668-119">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="89668-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="89668-120">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="89668-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="89668-121">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="89668-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="89668-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="89668-122">Remarks</span></span>  
 <span data-ttu-id="89668-123">`ExitTask` пытается корректно завершить задачи, аналогично для отсоединения поток из библиотеки неуправляемых типов.</span><span class="sxs-lookup"><span data-stu-id="89668-123">`ExitTask` attempts a clean shutdown of a task, in a manner analogous to detaching a thread from an unmanaged type library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89668-124">Требования</span><span class="sxs-lookup"><span data-stu-id="89668-124">Requirements</span></span>  
 <span data-ttu-id="89668-125">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89668-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89668-126">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="89668-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="89668-127">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="89668-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="89668-128">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89668-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89668-129">См. также</span><span class="sxs-lookup"><span data-stu-id="89668-129">See Also</span></span>  
 [<span data-ttu-id="89668-130">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="89668-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="89668-131">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="89668-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="89668-132">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="89668-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="89668-133">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="89668-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

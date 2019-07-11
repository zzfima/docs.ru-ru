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
ms.openlocfilehash: 81afc2aa738c719456091c3f28f3ca33682776e4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67759007"
---
# <a name="iclrtaskexittask-method"></a><span data-ttu-id="f706a-102">Метод ICLRTask::ExitTask</span><span class="sxs-lookup"><span data-stu-id="f706a-102">ICLRTask::ExitTask Method</span></span>
<span data-ttu-id="f706a-103">Уведомляет среду (CLR), задача, представленная текущим [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) экземпляра завершается и пытается корректно завершить работу задачи.</span><span class="sxs-lookup"><span data-stu-id="f706a-103">Notifies the common language runtime (CLR) that the task represented by the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance is ending, and attempts to shut the task down gracefully.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f706a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f706a-104">Syntax</span></span>  
  
```cpp  
HRESULT ExitTask ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="f706a-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f706a-105">Return Value</span></span>  
  
|<span data-ttu-id="f706a-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f706a-106">HRESULT</span></span>|<span data-ttu-id="f706a-107">Описание</span><span class="sxs-lookup"><span data-stu-id="f706a-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f706a-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="f706a-108">S_OK</span></span>|<span data-ttu-id="f706a-109">`ExitTask` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="f706a-109">`ExitTask` returned successfully.</span></span>|  
|<span data-ttu-id="f706a-110">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f706a-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f706a-111">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="f706a-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f706a-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f706a-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f706a-113">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="f706a-113">The call timed out.</span></span>|  
|<span data-ttu-id="f706a-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f706a-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f706a-115">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="f706a-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f706a-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f706a-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f706a-117">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="f706a-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f706a-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f706a-118">E_FAIL</span></span>|<span data-ttu-id="f706a-119">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="f706a-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f706a-120">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="f706a-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f706a-121">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f706a-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f706a-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="f706a-122">Remarks</span></span>  
 <span data-ttu-id="f706a-123">`ExitTask` пытается задачи, аналогично для отсоединения поток из библиотеки неуправляемого типа.</span><span class="sxs-lookup"><span data-stu-id="f706a-123">`ExitTask` attempts a clean shutdown of a task, in a manner analogous to detaching a thread from an unmanaged type library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f706a-124">Требования</span><span class="sxs-lookup"><span data-stu-id="f706a-124">Requirements</span></span>  
 <span data-ttu-id="f706a-125">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f706a-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f706a-126">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f706a-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f706a-127">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f706a-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f706a-128">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f706a-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f706a-129">См. также</span><span class="sxs-lookup"><span data-stu-id="f706a-129">See also</span></span>

- [<span data-ttu-id="f706a-130">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="f706a-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="f706a-131">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="f706a-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="f706a-132">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="f706a-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="f706a-133">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="f706a-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

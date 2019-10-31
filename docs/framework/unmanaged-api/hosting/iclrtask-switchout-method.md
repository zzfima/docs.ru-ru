---
title: Метод ICLRTask::SwitchOut
ms.date: 03/30/2017
api_name:
- ICLRTask.SwitchOut
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::SwitchOut
helpviewer_keywords:
- ICLRTask::SwitchOut method [.NET Framework hosting]
- SwitchOut method [.NET Framework hosting]
ms.assetid: b6fb168c-b24b-4ecf-a390-2b5ba3317ae6
topic_type:
- apiref
ms.openlocfilehash: f9c2e77013ff9e31a0a2ef3b4ca511b76ae345e1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124600"
---
# <a name="iclrtaskswitchout-method"></a><span data-ttu-id="4a285-102">Метод ICLRTask::SwitchOut</span><span class="sxs-lookup"><span data-stu-id="4a285-102">ICLRTask::SwitchOut Method</span></span>
<span data-ttu-id="4a285-103">Уведомляет среду CLR о том, что задача, представленная текущим экземпляром [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) , больше не находится в рабочем состоянии.</span><span class="sxs-lookup"><span data-stu-id="4a285-103">Notifies the common language runtime (CLR) that the task represented by the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance is no longer in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a285-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4a285-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchOut ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="4a285-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4a285-105">Return Value</span></span>  
  
|<span data-ttu-id="4a285-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4a285-106">HRESULT</span></span>|<span data-ttu-id="4a285-107">Описание</span><span class="sxs-lookup"><span data-stu-id="4a285-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4a285-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="4a285-108">S_OK</span></span>|<span data-ttu-id="4a285-109">`SwitchOut` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="4a285-109">`SwitchOut` returned successfully.</span></span>|  
|<span data-ttu-id="4a285-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4a285-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4a285-111">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="4a285-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4a285-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4a285-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4a285-113">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="4a285-113">The call timed out.</span></span>|  
|<span data-ttu-id="4a285-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4a285-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4a285-115">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="4a285-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4a285-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4a285-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4a285-117">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="4a285-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4a285-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4a285-118">E_FAIL</span></span>|<span data-ttu-id="4a285-119">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="4a285-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4a285-120">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="4a285-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4a285-121">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4a285-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4a285-122">Заметки</span><span class="sxs-lookup"><span data-stu-id="4a285-122">Remarks</span></span>  
 <span data-ttu-id="4a285-123">Узел вызывает `SwitchOut`, чтобы сообщить среде CLR о том, что она временно остановила выполнение задачи, которую представляет текущий экземпляр `ICLRTask`, и перепланирует задачу.</span><span class="sxs-lookup"><span data-stu-id="4a285-123">A host calls `SwitchOut` to inform the CLR that it has temporarily stopped executing the task that the current `ICLRTask` instance represents, and will reschedule the task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a285-124">Требования</span><span class="sxs-lookup"><span data-stu-id="4a285-124">Requirements</span></span>  
 <span data-ttu-id="4a285-125">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a285-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a285-126">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="4a285-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4a285-127">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4a285-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4a285-128">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a285-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a285-129">См. также</span><span class="sxs-lookup"><span data-stu-id="4a285-129">See also</span></span>

- [<span data-ttu-id="4a285-130">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="4a285-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="4a285-131">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="4a285-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="4a285-132">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="4a285-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="4a285-133">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="4a285-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

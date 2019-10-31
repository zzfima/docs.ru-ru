---
title: Метод ICLRTask::SetTaskIdentifier
ms.date: 03/30/2017
api_name:
- ICLRTask.SetTaskIdentifier
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::SetTaskIdentifier
helpviewer_keywords:
- SetTaskIdentifier method [.NET Framework hosting]
- ICLRTask::SetTaskIdentifier method [.NET Framework hosting]
ms.assetid: bdb7f047-1e90-40fc-9e3b-d44a16509073
topic_type:
- apiref
ms.openlocfilehash: cf6d84e483188ea7ed3376ba9b28906a38913fd4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124628"
---
# <a name="iclrtasksettaskidentifier-method"></a><span data-ttu-id="97bf3-102">Метод ICLRTask::SetTaskIdentifier</span><span class="sxs-lookup"><span data-stu-id="97bf3-102">ICLRTask::SetTaskIdentifier Method</span></span>
<span data-ttu-id="97bf3-103">Инструктирует среду CLR, чтобы связать указанное значение идентификатора с задачей, представленной текущим экземпляром [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="97bf3-103">Instructs the common language runtime (CLR) to associate the specified identifier value with the task represented by the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97bf3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="97bf3-104">Syntax</span></span>  
  
```cpp  
HRESULT SetTaskIdentifier (  
    [in] DWORD Asked  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="97bf3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="97bf3-105">Parameters</span></span>  
 `Asked`  
 <span data-ttu-id="97bf3-106">окне Уникальный идентификатор среды CLR, связываемый с задачей, представленной текущим экземпляром `ICLRTask`.</span><span class="sxs-lookup"><span data-stu-id="97bf3-106">[in] The unique identifier for the common language runtime to associate with the task represented by the current `ICLRTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="97bf3-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="97bf3-107">Return Value</span></span>  
  
|<span data-ttu-id="97bf3-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="97bf3-108">HRESULT</span></span>|<span data-ttu-id="97bf3-109">Описание</span><span class="sxs-lookup"><span data-stu-id="97bf3-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="97bf3-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="97bf3-110">S_OK</span></span>|<span data-ttu-id="97bf3-111">`SetTaskIdentifier` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="97bf3-111">`SetTaskIdentifier` returned successfully.</span></span>|  
|<span data-ttu-id="97bf3-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="97bf3-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="97bf3-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="97bf3-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="97bf3-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="97bf3-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="97bf3-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="97bf3-115">The call timed out.</span></span>|  
|<span data-ttu-id="97bf3-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="97bf3-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="97bf3-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="97bf3-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="97bf3-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="97bf3-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="97bf3-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="97bf3-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="97bf3-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="97bf3-120">E_FAIL</span></span>|<span data-ttu-id="97bf3-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="97bf3-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="97bf3-122">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="97bf3-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="97bf3-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="97bf3-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="97bf3-124">Заметки</span><span class="sxs-lookup"><span data-stu-id="97bf3-124">Remarks</span></span>  
 <span data-ttu-id="97bf3-125">Узел может связать идентификатор с задачей, чтобы упростить интеграцию среды CLR и узла в среде отладки.</span><span class="sxs-lookup"><span data-stu-id="97bf3-125">The host can associate an identifier with a task to help integrate the CLR and the host in a debugging environment.</span></span> <span data-ttu-id="97bf3-126">Идентификатор не имеет смысла для CLR.</span><span class="sxs-lookup"><span data-stu-id="97bf3-126">The identifier has no meaning for the CLR.</span></span> <span data-ttu-id="97bf3-127">Среда CLR передает ее в приложение отладчика.</span><span class="sxs-lookup"><span data-stu-id="97bf3-127">The CLR passes it along to a debugger application.</span></span> <span data-ttu-id="97bf3-128">Отладчик может использовать этот идентификатор для связывания стека вызовов CLR с стеком вызовов узла и включения соответствующей информации трассировки при просмотре в пользовательском интерфейсе отладчика.</span><span class="sxs-lookup"><span data-stu-id="97bf3-128">The debugger can use this identifier to associate a CLR call stack with a host call stack, and enable their respective trace information to be unified when viewed in the debugger's user interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97bf3-129">Требования</span><span class="sxs-lookup"><span data-stu-id="97bf3-129">Requirements</span></span>  
 <span data-ttu-id="97bf3-130">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97bf3-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97bf3-131">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="97bf3-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="97bf3-132">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="97bf3-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="97bf3-133">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97bf3-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97bf3-134">См. также</span><span class="sxs-lookup"><span data-stu-id="97bf3-134">See also</span></span>

- [<span data-ttu-id="97bf3-135">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="97bf3-135">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="97bf3-136">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="97bf3-136">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="97bf3-137">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="97bf3-137">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="97bf3-138">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="97bf3-138">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

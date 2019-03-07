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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 58a010def407751a49cbb1de51c59a3df85cfb18
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487777"
---
# <a name="iclrtasksettaskidentifier-method"></a><span data-ttu-id="1c78c-102">Метод ICLRTask::SetTaskIdentifier</span><span class="sxs-lookup"><span data-stu-id="1c78c-102">ICLRTask::SetTaskIdentifier Method</span></span>
<span data-ttu-id="1c78c-103">Указывает, что среда CLR (CLR), чтобы связать указанное значение идентификатора с задачей, представленный текущим [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="1c78c-103">Instructs the common language runtime (CLR) to associate the specified identifier value with the task represented by the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c78c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1c78c-104">Syntax</span></span>  
  
```  
HRESULT SetTaskIdentifier (  
    [in] DWORD Asked  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c78c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1c78c-105">Parameters</span></span>  
 `Asked`  
 <span data-ttu-id="1c78c-106">[in] Уникальный идентификатор для общеязыковой среды выполнения следует связать с задачей, представленный текущим `ICLRTask` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="1c78c-106">[in] The unique identifier for the common language runtime to associate with the task represented by the current `ICLRTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1c78c-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1c78c-107">Return Value</span></span>  
  
|<span data-ttu-id="1c78c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1c78c-108">HRESULT</span></span>|<span data-ttu-id="1c78c-109">Описание</span><span class="sxs-lookup"><span data-stu-id="1c78c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1c78c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="1c78c-110">S_OK</span></span>|<span data-ttu-id="1c78c-111">`SetTaskIdentifier` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="1c78c-111">`SetTaskIdentifier` returned successfully.</span></span>|  
|<span data-ttu-id="1c78c-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1c78c-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1c78c-113">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="1c78c-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1c78c-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1c78c-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1c78c-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="1c78c-115">The call timed out.</span></span>|  
|<span data-ttu-id="1c78c-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1c78c-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1c78c-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="1c78c-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1c78c-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1c78c-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1c78c-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="1c78c-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1c78c-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1c78c-120">E_FAIL</span></span>|<span data-ttu-id="1c78c-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="1c78c-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1c78c-122">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="1c78c-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1c78c-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="1c78c-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1c78c-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="1c78c-124">Remarks</span></span>  
 <span data-ttu-id="1c78c-125">Узел может связать идентификатор с задачей облегчают интеграцию среды CLR и узлом в отладочной среде.</span><span class="sxs-lookup"><span data-stu-id="1c78c-125">The host can associate an identifier with a task to help integrate the CLR and the host in a debugging environment.</span></span> <span data-ttu-id="1c78c-126">Идентификатор не имеет смысла для среды CLR.</span><span class="sxs-lookup"><span data-stu-id="1c78c-126">The identifier has no meaning for the CLR.</span></span> <span data-ttu-id="1c78c-127">Среда CLR передает его вместе с отладчиком.</span><span class="sxs-lookup"><span data-stu-id="1c78c-127">The CLR passes it along to a debugger application.</span></span> <span data-ttu-id="1c78c-128">Отладчик можно использовать этот идентификатор должен быть сопоставлен стек вызова CLR основного приложения и разрешить их соответствующих трассировки отправку информации об единой, при просмотре в пользовательском интерфейсе отладчика.</span><span class="sxs-lookup"><span data-stu-id="1c78c-128">The debugger can use this identifier to associate a CLR call stack with a host call stack, and enable their respective trace information to be unified when viewed in the debugger's user interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c78c-129">Требования</span><span class="sxs-lookup"><span data-stu-id="1c78c-129">Requirements</span></span>  
 <span data-ttu-id="1c78c-130">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c78c-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c78c-131">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1c78c-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1c78c-132">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1c78c-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1c78c-133">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c78c-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c78c-134">См. также</span><span class="sxs-lookup"><span data-stu-id="1c78c-134">See also</span></span>
- [<span data-ttu-id="1c78c-135">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="1c78c-135">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="1c78c-136">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="1c78c-136">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="1c78c-137">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="1c78c-137">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="1c78c-138">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="1c78c-138">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

---
title: Метод IHostTaskManager::Sleep
ms.date: 03/30/2017
api_name:
- IHostTaskManager.Sleep
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::Sleep
helpviewer_keywords:
- IHostTaskManager::Sleep method [.NET Framework hosting]
- Sleep method, IHostTaskManager interface [.NET Framework hosting]
ms.assetid: f67d25f3-9199-4c5f-b1e8-1c819243cfd5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0e25f2e49ab25d2df827fdd59526b13976d21219
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756569"
---
# <a name="ihosttaskmanagersleep-method"></a><span data-ttu-id="e171c-102">Метод IHostTaskManager::Sleep</span><span class="sxs-lookup"><span data-stu-id="e171c-102">IHostTaskManager::Sleep Method</span></span>
<span data-ttu-id="e171c-103">Уведомляет основное приложение, что текущая задача будет в спящий режим.</span><span class="sxs-lookup"><span data-stu-id="e171c-103">Notifies the host that the current task is going to sleep.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e171c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e171c-104">Syntax</span></span>  
  
```cpp  
HRESULT Sleep (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e171c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e171c-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="e171c-106">[in] Интервал времени в миллисекундах, которое приостанавливается поток.</span><span class="sxs-lookup"><span data-stu-id="e171c-106">[in] The time interval, in milliseconds, that the thread will sleep.</span></span>  
  
 `option`  
 <span data-ttu-id="e171c-107">[in] Один из [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) значений перечисления, указывающее, какое действие должен выполнить узел, если это действие блоков.</span><span class="sxs-lookup"><span data-stu-id="e171c-107">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) enumeration values, indicating what action the host should take if this action blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e171c-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e171c-108">Return Value</span></span>  
  
|<span data-ttu-id="e171c-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e171c-109">HRESULT</span></span>|<span data-ttu-id="e171c-110">Описание</span><span class="sxs-lookup"><span data-stu-id="e171c-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e171c-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="e171c-111">S_OK</span></span>|<span data-ttu-id="e171c-112">`Sleep` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="e171c-112">`Sleep` returned successfully.</span></span>|  
|<span data-ttu-id="e171c-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e171c-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e171c-114">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="e171c-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e171c-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e171c-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e171c-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="e171c-116">The call timed out.</span></span>|  
|<span data-ttu-id="e171c-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e171c-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e171c-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="e171c-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e171c-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e171c-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e171c-120">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="e171c-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e171c-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e171c-121">E_FAIL</span></span>|<span data-ttu-id="e171c-122">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="e171c-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e171c-123">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="e171c-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e171c-124">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e171c-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e171c-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="e171c-125">Remarks</span></span>  
 <span data-ttu-id="e171c-126">Среда CLR обычно вызывает `IHostTaskManager::Sleep` при <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> вызова из пользовательского кода.</span><span class="sxs-lookup"><span data-stu-id="e171c-126">The CLR typically calls `IHostTaskManager::Sleep` when <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> is called from user code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e171c-127">Требования</span><span class="sxs-lookup"><span data-stu-id="e171c-127">Requirements</span></span>  
 <span data-ttu-id="e171c-128">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e171c-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e171c-129">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e171c-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e171c-130">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e171c-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e171c-131">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e171c-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e171c-132">См. также</span><span class="sxs-lookup"><span data-stu-id="e171c-132">See also</span></span>

- [<span data-ttu-id="e171c-133">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="e171c-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="e171c-134">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="e171c-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="e171c-135">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="e171c-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="e171c-136">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="e171c-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

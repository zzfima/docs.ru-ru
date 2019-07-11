---
title: Метод ICLRTask::GetMemStats
ms.date: 03/30/2017
api_name:
- ICLRTask.GetMemStats
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::GetMemStats
helpviewer_keywords:
- ICLRTask::GetMemStats method [.NET Framework hosting]
- GetMemStats method [.NET Framework hosting]
ms.assetid: c9e07657-1682-4c30-a336-f8658ff1a125
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ab388459df88e91093459658ced4d4b4eb023460
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67758986"
---
# <a name="iclrtaskgetmemstats-method"></a><span data-ttu-id="0c618-102">Метод ICLRTask::GetMemStats</span><span class="sxs-lookup"><span data-stu-id="0c618-102">ICLRTask::GetMemStats Method</span></span>
<span data-ttu-id="0c618-103">Возвращает сведения об использовании статистического памяти, связанные с задачей, текущий [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) представленное экземпляром.</span><span class="sxs-lookup"><span data-stu-id="0c618-103">Gets statistical memory usage information related to the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c618-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0c618-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMemStats (  
    [out] COR_GC_THREAD_STATS *pMemUsage  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c618-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0c618-105">Parameters</span></span>  
 `pMemUsage`  
 <span data-ttu-id="0c618-106">[out] Указатель на [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) экземпляр, содержащий сведения об использовании памяти задачи, включая число байтов, выделенных.</span><span class="sxs-lookup"><span data-stu-id="0c618-106">[out] A pointer to a [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) instance that contains details about the memory usage of the task, including the number of bytes allocated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0c618-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0c618-107">Return Value</span></span>  
  
|<span data-ttu-id="0c618-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0c618-108">HRESULT</span></span>|<span data-ttu-id="0c618-109">Описание</span><span class="sxs-lookup"><span data-stu-id="0c618-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0c618-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="0c618-110">S_OK</span></span>|<span data-ttu-id="0c618-111">`GetMemStats` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="0c618-111">`GetMemStats` returned successfully.</span></span>|  
|<span data-ttu-id="0c618-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0c618-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0c618-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="0c618-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0c618-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0c618-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0c618-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="0c618-115">The call timed out.</span></span>|  
|<span data-ttu-id="0c618-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0c618-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0c618-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="0c618-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0c618-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0c618-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0c618-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="0c618-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0c618-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0c618-120">E_FAIL</span></span>|<span data-ttu-id="0c618-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="0c618-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0c618-122">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="0c618-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0c618-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0c618-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0c618-124">Требования</span><span class="sxs-lookup"><span data-stu-id="0c618-124">Requirements</span></span>  
 <span data-ttu-id="0c618-125">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c618-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c618-126">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0c618-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0c618-127">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0c618-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0c618-128">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c618-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c618-129">См. также</span><span class="sxs-lookup"><span data-stu-id="0c618-129">See also</span></span>

- [<span data-ttu-id="0c618-130">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="0c618-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="0c618-131">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="0c618-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="0c618-132">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="0c618-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="0c618-133">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="0c618-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

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
ms.openlocfilehash: 668e570c315f5473f222905a061f05ac94afa81a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763572"
---
# <a name="iclrtaskgetmemstats-method"></a><span data-ttu-id="d7748-102">Метод ICLRTask::GetMemStats</span><span class="sxs-lookup"><span data-stu-id="d7748-102">ICLRTask::GetMemStats Method</span></span>
<span data-ttu-id="d7748-103">Возвращает сведения об использовании статистического памяти, связанные с задачей, текущий [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) представленное экземпляром.</span><span class="sxs-lookup"><span data-stu-id="d7748-103">Gets statistical memory usage information related to the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7748-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d7748-104">Syntax</span></span>  
  
```  
HRESULT GetMemStats (  
    [out] COR_GC_THREAD_STATS *pMemUsage  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7748-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d7748-105">Parameters</span></span>  
 `pMemUsage`  
 <span data-ttu-id="d7748-106">[out] Указатель на [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) экземпляр, содержащий сведения об использовании памяти задачи, включая число байтов, выделенных.</span><span class="sxs-lookup"><span data-stu-id="d7748-106">[out] A pointer to a [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) instance that contains details about the memory usage of the task, including the number of bytes allocated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d7748-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d7748-107">Return Value</span></span>  
  
|<span data-ttu-id="d7748-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d7748-108">HRESULT</span></span>|<span data-ttu-id="d7748-109">Описание</span><span class="sxs-lookup"><span data-stu-id="d7748-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d7748-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d7748-110">S_OK</span></span>|<span data-ttu-id="d7748-111">`GetMemStats` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="d7748-111">`GetMemStats` returned successfully.</span></span>|  
|<span data-ttu-id="d7748-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d7748-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d7748-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="d7748-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d7748-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d7748-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d7748-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="d7748-115">The call timed out.</span></span>|  
|<span data-ttu-id="d7748-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d7748-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d7748-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="d7748-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d7748-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d7748-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d7748-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="d7748-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d7748-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d7748-120">E_FAIL</span></span>|<span data-ttu-id="d7748-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="d7748-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d7748-122">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="d7748-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d7748-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d7748-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d7748-124">Требования</span><span class="sxs-lookup"><span data-stu-id="d7748-124">Requirements</span></span>  
 <span data-ttu-id="d7748-125">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7748-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7748-126">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d7748-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d7748-127">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d7748-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d7748-128">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7748-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7748-129">См. также</span><span class="sxs-lookup"><span data-stu-id="d7748-129">See also</span></span>

- [<span data-ttu-id="d7748-130">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="d7748-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="d7748-131">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="d7748-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="d7748-132">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="d7748-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="d7748-133">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="d7748-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59183408"
---
# <a name="iclrtaskgetmemstats-method"></a><span data-ttu-id="4cd41-102">Метод ICLRTask::GetMemStats</span><span class="sxs-lookup"><span data-stu-id="4cd41-102">ICLRTask::GetMemStats Method</span></span>
<span data-ttu-id="4cd41-103">Возвращает сведения об использовании статистического памяти, связанные с задачей, текущий [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) представленное экземпляром.</span><span class="sxs-lookup"><span data-stu-id="4cd41-103">Gets statistical memory usage information related to the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cd41-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4cd41-104">Syntax</span></span>  
  
```  
HRESULT GetMemStats (  
    [out] COR_GC_THREAD_STATS *pMemUsage  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4cd41-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4cd41-105">Parameters</span></span>  
 `pMemUsage`  
 <span data-ttu-id="4cd41-106">[out] Указатель на [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) экземпляр, содержащий сведения об использовании памяти задачи, включая число байтов, выделенных.</span><span class="sxs-lookup"><span data-stu-id="4cd41-106">[out] A pointer to a [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) instance that contains details about the memory usage of the task, including the number of bytes allocated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4cd41-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4cd41-107">Return Value</span></span>  
  
|<span data-ttu-id="4cd41-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4cd41-108">HRESULT</span></span>|<span data-ttu-id="4cd41-109">Описание</span><span class="sxs-lookup"><span data-stu-id="4cd41-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4cd41-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="4cd41-110">S_OK</span></span>|`GetMemStats` <span data-ttu-id="4cd41-111">успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="4cd41-111">returned successfully.</span></span>|  
|<span data-ttu-id="4cd41-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4cd41-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4cd41-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="4cd41-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4cd41-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4cd41-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4cd41-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="4cd41-115">The call timed out.</span></span>|  
|<span data-ttu-id="4cd41-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4cd41-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4cd41-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="4cd41-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4cd41-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4cd41-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4cd41-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="4cd41-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4cd41-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4cd41-120">E_FAIL</span></span>|<span data-ttu-id="4cd41-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="4cd41-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4cd41-122">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="4cd41-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4cd41-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4cd41-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4cd41-124">Требования</span><span class="sxs-lookup"><span data-stu-id="4cd41-124">Requirements</span></span>  
 <span data-ttu-id="4cd41-125">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4cd41-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4cd41-126">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4cd41-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4cd41-127">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4cd41-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="4cd41-128">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="4cd41-128">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4cd41-129">См. также</span><span class="sxs-lookup"><span data-stu-id="4cd41-129">See also</span></span>

- [<span data-ttu-id="4cd41-130">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="4cd41-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="4cd41-131">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="4cd41-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="4cd41-132">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="4cd41-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="4cd41-133">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="4cd41-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

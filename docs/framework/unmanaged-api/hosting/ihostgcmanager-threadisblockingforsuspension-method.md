---
title: Метод IHostGCManager::ThreadIsBlockingForSuspension
ms.date: 03/30/2017
api_name:
- IHostGCManager.ThreadIsBlockingForSuspension
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager::ThreadIsBlockingForSuspension
helpviewer_keywords:
- IHostGCManager::ThreadIsBlockingForSuspension method [.NET Framework hosting]
- ThreadIsBlockingForSuspension method [.NET Framework hosting]
ms.assetid: 2657d45d-26d2-4d0a-8473-32b652e3321d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 740f408b84dad67ee20c2508ae42a9569ed095f1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59179872"
---
# <a name="ihostgcmanagerthreadisblockingforsuspension-method"></a><span data-ttu-id="70ef9-102">Метод IHostGCManager::ThreadIsBlockingForSuspension</span><span class="sxs-lookup"><span data-stu-id="70ef9-102">IHostGCManager::ThreadIsBlockingForSuspension Method</span></span>
<span data-ttu-id="70ef9-103">Уведомляет основное приложение, что поток, из которого был вызван метод собираетесь заблокировать для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="70ef9-103">Notifies the host that the thread from which the method call was made is about to block for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70ef9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="70ef9-104">Syntax</span></span>  
  
```  
HRESULT ThreadIsBlockingForSuspension ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="70ef9-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="70ef9-105">Return Value</span></span>  
  
|<span data-ttu-id="70ef9-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="70ef9-106">HRESULT</span></span>|<span data-ttu-id="70ef9-107">Описание</span><span class="sxs-lookup"><span data-stu-id="70ef9-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="70ef9-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="70ef9-108">S_OK</span></span>|<span data-ttu-id="70ef9-109">`ThreadIsBlockingForSuspension` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="70ef9-109">`ThreadIsBlockingForSuspension` returned successfully.</span></span>|  
|<span data-ttu-id="70ef9-110">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="70ef9-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="70ef9-111">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="70ef9-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="70ef9-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="70ef9-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="70ef9-113">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="70ef9-113">The call timed out.</span></span>|  
|<span data-ttu-id="70ef9-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="70ef9-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="70ef9-115">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="70ef9-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="70ef9-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="70ef9-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="70ef9-117">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="70ef9-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="70ef9-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="70ef9-118">E_FAIL</span></span>|<span data-ttu-id="70ef9-119">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="70ef9-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="70ef9-120">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="70ef9-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="70ef9-121">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="70ef9-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="70ef9-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="70ef9-122">Remarks</span></span>  
 <span data-ttu-id="70ef9-123">Среда CLR обычно вызывает `ThreadIsBlockForSuspension` метод в процессе подготовки для сборки мусора, для предоставления возможности повторного планирования потока для неуправляемых задач на узле.</span><span class="sxs-lookup"><span data-stu-id="70ef9-123">The CLR typically calls the `ThreadIsBlockForSuspension` method in preparation for a garbage collection, to give the host an opportunity to reschedule the thread for unmanaged tasks.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="70ef9-124">Узел можно запланировать повторное выполнение задачи только после вызова `ThreadIsBlockingForSuspension`.</span><span class="sxs-lookup"><span data-stu-id="70ef9-124">The host can reschedule tasks only after a call to `ThreadIsBlockingForSuspension`.</span></span> <span data-ttu-id="70ef9-125">После выполнения вызовов [SuspensionStarting](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionstarting-method.md), основное приложение не должно планировать задачи.</span><span class="sxs-lookup"><span data-stu-id="70ef9-125">After the runtime calls [SuspensionStarting](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionstarting-method.md), the host must not reschedule a task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70ef9-126">Требования</span><span class="sxs-lookup"><span data-stu-id="70ef9-126">Requirements</span></span>  
 <span data-ttu-id="70ef9-127">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="70ef9-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70ef9-128">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="70ef9-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="70ef9-129">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="70ef9-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="70ef9-130">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70ef9-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70ef9-131">См. также</span><span class="sxs-lookup"><span data-stu-id="70ef9-131">See also</span></span>

- [<span data-ttu-id="70ef9-132">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="70ef9-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="70ef9-133">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="70ef9-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="70ef9-134">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="70ef9-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="70ef9-135">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="70ef9-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="70ef9-136">Интерфейс IHostGCManager</span><span class="sxs-lookup"><span data-stu-id="70ef9-136">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)

---
title: Метод IHostTaskManager::BeginThreadAffinity
ms.date: 03/30/2017
api_name:
- IHostTaskManager.BeginThreadAffinity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::BeginThreadAffinity
helpviewer_keywords:
- IHostTaskManager::BeginThreadAffinity method [.NET Framework hosting]
- BeginThreadAffinity method [.NET Framework hosting]
ms.assetid: fea3ab88-ce41-4c5a-847b-bb78cd748da6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 59af484710dc0848d7712017021adc5f3dcb7bce
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749770"
---
# <a name="ihosttaskmanagerbeginthreadaffinity-method"></a><span data-ttu-id="f950d-102">Метод IHostTaskManager::BeginThreadAffinity</span><span class="sxs-lookup"><span data-stu-id="f950d-102">IHostTaskManager::BeginThreadAffinity Method</span></span>
<span data-ttu-id="f950d-103">Уведомляет хост, что управляемый код к периоду, в котором текущей задачи не должен быть перемещена в другой поток операционной системы.</span><span class="sxs-lookup"><span data-stu-id="f950d-103">Notifies the host that managed code is entering a period in which the current task must not be moved to another operating system thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f950d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f950d-104">Syntax</span></span>  
  
```cpp  
HRESULT BeginThreadAffinity ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="f950d-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f950d-105">Return Value</span></span>  
  
|<span data-ttu-id="f950d-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f950d-106">HRESULT</span></span>|<span data-ttu-id="f950d-107">Описание</span><span class="sxs-lookup"><span data-stu-id="f950d-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f950d-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="f950d-108">S_OK</span></span>|<span data-ttu-id="f950d-109">`BeginThreadAffinity` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="f950d-109">`BeginThreadAffinity` returned successfully.</span></span>|  
|<span data-ttu-id="f950d-110">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f950d-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f950d-111">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="f950d-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f950d-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f950d-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f950d-113">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="f950d-113">The call timed out.</span></span>|  
|<span data-ttu-id="f950d-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f950d-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f950d-115">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="f950d-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f950d-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f950d-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f950d-117">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="f950d-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f950d-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f950d-118">E_FAIL</span></span>|<span data-ttu-id="f950d-119">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="f950d-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f950d-120">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="f950d-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f950d-121">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f950d-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f950d-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="f950d-122">Remarks</span></span>  
 <span data-ttu-id="f950d-123">Среда CLR обычно вызывает `IHostTaskManager::BeginThreadAffinity` в контексте вызова <xref:System.Threading.Thread.BeginThreadAffinity%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f950d-123">The CLR typically calls `IHostTaskManager::BeginThreadAffinity` in the context of a call to <xref:System.Threading.Thread.BeginThreadAffinity%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f950d-124">Текущая задача не должно быть Переназначено, пока соответствующий вызов [IHostTaskManager::EndThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md).</span><span class="sxs-lookup"><span data-stu-id="f950d-124">The current task must not be rescheduled until a corresponding call is made to [IHostTaskManager::EndThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md).</span></span> <span data-ttu-id="f950d-125">Задачи могут отключаться, но при их обратно в, они должны быть назначены один поток операционной системы, из которого они были выключены. Вложенные вызовы `BeginThreadAffinity` не оказывают влияния, так как вызов связан с текущей задачей.</span><span class="sxs-lookup"><span data-stu-id="f950d-125">Tasks can be switched out, but when they are switched back in, they must be assigned to the same operating system thread from which they were switched out. Nested calls to `BeginThreadAffinity` have no effect, because the call refers to the current task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f950d-126">Требования</span><span class="sxs-lookup"><span data-stu-id="f950d-126">Requirements</span></span>  
 <span data-ttu-id="f950d-127">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f950d-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f950d-128">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f950d-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f950d-129">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f950d-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f950d-130">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f950d-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f950d-131">См. также</span><span class="sxs-lookup"><span data-stu-id="f950d-131">See also</span></span>

- [<span data-ttu-id="f950d-132">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="f950d-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="f950d-133">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="f950d-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="f950d-134">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="f950d-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="f950d-135">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="f950d-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

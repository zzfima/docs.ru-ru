---
title: Метод IHostSyncManager::CreateCrst
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateCrst
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateCrst
helpviewer_keywords:
- CreateCrst method [.NET Framework hosting]
- IHostSyncManager::CreateCrst method [.NET Framework hosting]
ms.assetid: ac278cc8-2540-4a6c-b5c6-b90c3970b4f4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 88b7b2093ecb2c601e57eca32e25c21e91641281
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753473"
---
# <a name="ihostsyncmanagercreatecrst-method"></a><span data-ttu-id="e4f5a-102">Метод IHostSyncManager::CreateCrst</span><span class="sxs-lookup"><span data-stu-id="e4f5a-102">IHostSyncManager::CreateCrst Method</span></span>
<span data-ttu-id="e4f5a-103">Создает объект критической секции для синхронизации.</span><span class="sxs-lookup"><span data-stu-id="e4f5a-103">Creates a critical section object for synchronization.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4f5a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e4f5a-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateCrst (  
    [out] IHostCrst** ppCrst  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e4f5a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e4f5a-105">Parameters</span></span>  
 `ppCrst`  
 <span data-ttu-id="e4f5a-106">[out] Указатель на адрес [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) экземпляр реализованного узлом, или значение null, если не удалось создать критический раздел.</span><span class="sxs-lookup"><span data-stu-id="e4f5a-106">[out] A pointer to the address of an [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance implemented by the host, or null if the critical section could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e4f5a-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e4f5a-107">Return Value</span></span>  
  
|<span data-ttu-id="e4f5a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e4f5a-108">HRESULT</span></span>|<span data-ttu-id="e4f5a-109">Описание</span><span class="sxs-lookup"><span data-stu-id="e4f5a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e4f5a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="e4f5a-110">S_OK</span></span>|<span data-ttu-id="e4f5a-111">`CreateCrst` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="e4f5a-111">`CreateCrst` returned successfully.</span></span>|  
|<span data-ttu-id="e4f5a-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e4f5a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e4f5a-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="e4f5a-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e4f5a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e4f5a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e4f5a-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="e4f5a-115">The call timed out.</span></span>|  
|<span data-ttu-id="e4f5a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e4f5a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e4f5a-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="e4f5a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e4f5a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e4f5a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e4f5a-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="e4f5a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e4f5a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e4f5a-120">E_FAIL</span></span>|<span data-ttu-id="e4f5a-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="e4f5a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e4f5a-122">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="e4f5a-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e4f5a-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e4f5a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e4f5a-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="e4f5a-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="e4f5a-125">Недостаточно памяти, доступного для создания запрошенной критической секции.</span><span class="sxs-lookup"><span data-stu-id="e4f5a-125">Not enough memory was available to create the requested critical section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e4f5a-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="e4f5a-126">Remarks</span></span>  
 <span data-ttu-id="e4f5a-127">Важные объекты разделов обеспечивать синхронизацию, аналогичны предоставляемым объектом mutex, за исключением того, что критические секции могут использоваться только потоки одного процесса.</span><span class="sxs-lookup"><span data-stu-id="e4f5a-127">Critical section objects provide synchronization similar to that provided by a mutex object, except that critical sections can be used only by the threads of a single process.</span></span> <span data-ttu-id="e4f5a-128">`CreateCrst` зеркально отражает Win32 `InitializeCriticalSection` функции.</span><span class="sxs-lookup"><span data-stu-id="e4f5a-128">`CreateCrst` mirrors the Win32 `InitializeCriticalSection` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4f5a-129">Требования</span><span class="sxs-lookup"><span data-stu-id="e4f5a-129">Requirements</span></span>  
 <span data-ttu-id="e4f5a-130">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4f5a-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4f5a-131">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e4f5a-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e4f5a-132">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e4f5a-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e4f5a-133">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4f5a-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4f5a-134">См. также</span><span class="sxs-lookup"><span data-stu-id="e4f5a-134">See also</span></span>

- [<span data-ttu-id="e4f5a-135">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="e4f5a-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="e4f5a-136">Интерфейс IHostCrst</span><span class="sxs-lookup"><span data-stu-id="e4f5a-136">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="e4f5a-137">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="e4f5a-137">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="e4f5a-138">Интерфейс IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="e4f5a-138">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="e4f5a-139">Мьютексы</span><span class="sxs-lookup"><span data-stu-id="e4f5a-139">Mutexes</span></span>](../../../../docs/standard/threading/mutexes.md)
- [<span data-ttu-id="e4f5a-140">Классы Semaphore и SemaphoreSlim</span><span class="sxs-lookup"><span data-stu-id="e4f5a-140">Semaphore and SemaphoreSlim</span></span>](../../../../docs/standard/threading/semaphore-and-semaphoreslim.md)

---
title: Метод IHostSyncManager::CreateRWLockWriterEvent
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateRWLockWriterEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateRWLockWriterEvent
helpviewer_keywords:
- CreateRWLockWriterEvent method [.NET Framework hosting]
- IHostSyncManager::CreateRWLockWriterEvent method [.NET Framework hosting]
ms.assetid: 70e488c2-cf53-4dc0-ba52-74372d215c41
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 533f7244dc47bc26b59cb9de6289ce011387bf68
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753402"
---
# <a name="ihostsyncmanagercreaterwlockwriterevent-method"></a><span data-ttu-id="d0f86-102">Метод IHostSyncManager::CreateRWLockWriterEvent</span><span class="sxs-lookup"><span data-stu-id="d0f86-102">IHostSyncManager::CreateRWLockWriterEvent Method</span></span>
<span data-ttu-id="d0f86-103">Создает объект события автоматического сброса для реализации блокировку записи.</span><span class="sxs-lookup"><span data-stu-id="d0f86-103">Creates an auto-reset event object for the implementation of a writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0f86-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d0f86-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateRWLockWriterEvent (  
    [in]  SIZE_T cookie,  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d0f86-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d0f86-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="d0f86-106">[in] Файл cookie, который связывается с событием автоматического сброса.</span><span class="sxs-lookup"><span data-stu-id="d0f86-106">[in] A cookie to associate with the auto-reset event.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="d0f86-107">[out] Указатель на адрес [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) экземпляра, или значение null, если не удалось создать объект события.</span><span class="sxs-lookup"><span data-stu-id="d0f86-107">[out] A pointer to the address of an [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d0f86-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d0f86-108">Return Value</span></span>  
  
|<span data-ttu-id="d0f86-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d0f86-109">HRESULT</span></span>|<span data-ttu-id="d0f86-110">Описание</span><span class="sxs-lookup"><span data-stu-id="d0f86-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d0f86-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="d0f86-111">S_OK</span></span>|<span data-ttu-id="d0f86-112">`CreateRWLockWriterEvent` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="d0f86-112">`CreateRWLockWriterEvent` returned successfully.</span></span>|  
|<span data-ttu-id="d0f86-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d0f86-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d0f86-114">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="d0f86-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d0f86-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d0f86-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d0f86-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="d0f86-116">The call timed out.</span></span>|  
|<span data-ttu-id="d0f86-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d0f86-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d0f86-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="d0f86-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d0f86-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d0f86-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d0f86-120">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="d0f86-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d0f86-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d0f86-121">E_FAIL</span></span>|<span data-ttu-id="d0f86-122">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="d0f86-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d0f86-123">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="d0f86-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d0f86-124">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d0f86-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d0f86-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="d0f86-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="d0f86-126">Недостаточно памяти, доступного для создания запрошенного объекта события.</span><span class="sxs-lookup"><span data-stu-id="d0f86-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d0f86-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="d0f86-127">Remarks</span></span>  
 <span data-ttu-id="d0f86-128">Среда CLR вызывает `CreateRWLockWriterEvent` метод, чтобы получить ссылку на `IHostAutoEvent` экземпляр для использования в своей реализации блокировку записи.</span><span class="sxs-lookup"><span data-stu-id="d0f86-128">The CLR calls the `CreateRWLockWriterEvent` method to get a reference to an `IHostAutoEvent` instance to use in its implementation of a writer lock.</span></span> <span data-ttu-id="d0f86-129">Узел может использовать указанный файл cookie для определения задач, ожидающих блокировки, вызвав методы итерации [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="d0f86-129">The host can use the specified cookie to determine which tasks are waiting on the lock by calling the iteration methods of the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0f86-130">Требования</span><span class="sxs-lookup"><span data-stu-id="d0f86-130">Requirements</span></span>  
 <span data-ttu-id="d0f86-131">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d0f86-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0f86-132">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d0f86-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d0f86-133">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d0f86-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d0f86-134">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0f86-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0f86-135">См. также</span><span class="sxs-lookup"><span data-stu-id="d0f86-135">See also</span></span>

- [<span data-ttu-id="d0f86-136">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="d0f86-136">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="d0f86-137">Интерфейс IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="d0f86-137">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="d0f86-138">Интерфейс IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="d0f86-138">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="d0f86-139">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="d0f86-139">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)

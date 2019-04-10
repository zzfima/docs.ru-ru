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
ms.openlocfilehash: e994cf5c68871d6e81d53ac522259bc973c173ea
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59223619"
---
# <a name="ihostsyncmanagercreaterwlockwriterevent-method"></a><span data-ttu-id="32e08-102">Метод IHostSyncManager::CreateRWLockWriterEvent</span><span class="sxs-lookup"><span data-stu-id="32e08-102">IHostSyncManager::CreateRWLockWriterEvent Method</span></span>
<span data-ttu-id="32e08-103">Создает объект события автоматического сброса для реализации блокировку записи.</span><span class="sxs-lookup"><span data-stu-id="32e08-103">Creates an auto-reset event object for the implementation of a writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32e08-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="32e08-104">Syntax</span></span>  
  
```  
HRESULT CreateRWLockWriterEvent (  
    [in]  SIZE_T cookie,  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="32e08-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="32e08-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="32e08-106">[in] Файл cookie, который связывается с событием автоматического сброса.</span><span class="sxs-lookup"><span data-stu-id="32e08-106">[in] A cookie to associate with the auto-reset event.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="32e08-107">[out] Указатель на адрес [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) экземпляра, или значение null, если не удалось создать объект события.</span><span class="sxs-lookup"><span data-stu-id="32e08-107">[out] A pointer to the address of an [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="32e08-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="32e08-108">Return Value</span></span>  
  
|<span data-ttu-id="32e08-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="32e08-109">HRESULT</span></span>|<span data-ttu-id="32e08-110">Описание</span><span class="sxs-lookup"><span data-stu-id="32e08-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="32e08-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="32e08-111">S_OK</span></span>|`CreateRWLockWriterEvent` <span data-ttu-id="32e08-112">успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="32e08-112">returned successfully.</span></span>|  
|<span data-ttu-id="32e08-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="32e08-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="32e08-114">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="32e08-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="32e08-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="32e08-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="32e08-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="32e08-116">The call timed out.</span></span>|  
|<span data-ttu-id="32e08-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="32e08-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="32e08-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="32e08-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="32e08-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="32e08-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="32e08-120">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="32e08-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="32e08-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="32e08-121">E_FAIL</span></span>|<span data-ttu-id="32e08-122">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="32e08-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="32e08-123">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="32e08-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="32e08-124">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="32e08-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="32e08-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="32e08-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="32e08-126">Недостаточно памяти, доступного для создания запрошенного объекта события.</span><span class="sxs-lookup"><span data-stu-id="32e08-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="32e08-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="32e08-127">Remarks</span></span>  
 <span data-ttu-id="32e08-128">Среда CLR вызывает `CreateRWLockWriterEvent` метод, чтобы получить ссылку на `IHostAutoEvent` экземпляр для использования в своей реализации блокировку записи.</span><span class="sxs-lookup"><span data-stu-id="32e08-128">The CLR calls the `CreateRWLockWriterEvent` method to get a reference to an `IHostAutoEvent` instance to use in its implementation of a writer lock.</span></span> <span data-ttu-id="32e08-129">Узел может использовать указанный файл cookie для определения задач, ожидающих блокировки, вызвав методы итерации [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="32e08-129">The host can use the specified cookie to determine which tasks are waiting on the lock by calling the iteration methods of the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32e08-130">Требования</span><span class="sxs-lookup"><span data-stu-id="32e08-130">Requirements</span></span>  
 <span data-ttu-id="32e08-131">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="32e08-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32e08-132">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="32e08-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="32e08-133">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="32e08-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="32e08-134">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="32e08-134">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="32e08-135">См. также</span><span class="sxs-lookup"><span data-stu-id="32e08-135">See also</span></span>

- [<span data-ttu-id="32e08-136">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="32e08-136">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="32e08-137">Интерфейс IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="32e08-137">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="32e08-138">Интерфейс IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="32e08-138">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="32e08-139">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="32e08-139">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)

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
ms.openlocfilehash: 5ff830c136e539fec58d573247a83d1f8239e3bf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443207"
---
# <a name="ihostsyncmanagercreaterwlockwriterevent-method"></a><span data-ttu-id="3ac3c-102">Метод IHostSyncManager::CreateRWLockWriterEvent</span><span class="sxs-lookup"><span data-stu-id="3ac3c-102">IHostSyncManager::CreateRWLockWriterEvent Method</span></span>
<span data-ttu-id="3ac3c-103">Создает объект события автоматического сброса для реализации блокировки модуля записи.</span><span class="sxs-lookup"><span data-stu-id="3ac3c-103">Creates an auto-reset event object for the implementation of a writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ac3c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3ac3c-104">Syntax</span></span>  
  
```  
HRESULT CreateRWLockWriterEvent (  
    [in]  SIZE_T cookie,  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3ac3c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3ac3c-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="3ac3c-106">[in] Файл cookie, связываемый с события автоматического сброса.</span><span class="sxs-lookup"><span data-stu-id="3ac3c-106">[in] A cookie to associate with the auto-reset event.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="3ac3c-107">[out] Указатель на адрес [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) экземпляра, или значение null, если не удалось создать объект события.</span><span class="sxs-lookup"><span data-stu-id="3ac3c-107">[out] A pointer to the address of an [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3ac3c-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3ac3c-108">Return Value</span></span>  
  
|<span data-ttu-id="3ac3c-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3ac3c-109">HRESULT</span></span>|<span data-ttu-id="3ac3c-110">Описание</span><span class="sxs-lookup"><span data-stu-id="3ac3c-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3ac3c-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="3ac3c-111">S_OK</span></span>|<span data-ttu-id="3ac3c-112">`CreateRWLockWriterEvent` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="3ac3c-112">`CreateRWLockWriterEvent` returned successfully.</span></span>|  
|<span data-ttu-id="3ac3c-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3ac3c-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3ac3c-114">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="3ac3c-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3ac3c-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3ac3c-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3ac3c-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="3ac3c-116">The call timed out.</span></span>|  
|<span data-ttu-id="3ac3c-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3ac3c-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3ac3c-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="3ac3c-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3ac3c-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3ac3c-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3ac3c-120">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="3ac3c-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3ac3c-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3ac3c-121">E_FAIL</span></span>|<span data-ttu-id="3ac3c-122">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="3ac3c-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3ac3c-123">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="3ac3c-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3ac3c-124">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3ac3c-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="3ac3c-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="3ac3c-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="3ac3c-126">Не хватает памяти была доступна для создания запрошенного объекта события.</span><span class="sxs-lookup"><span data-stu-id="3ac3c-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3ac3c-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="3ac3c-127">Remarks</span></span>  
 <span data-ttu-id="3ac3c-128">Среда CLR вызывает `CreateRWLockWriterEvent` метод позволяет получить ссылку на `IHostAutoEvent` экземпляр для использования в своей реализации блокировку записи.</span><span class="sxs-lookup"><span data-stu-id="3ac3c-128">The CLR calls the `CreateRWLockWriterEvent` method to get a reference to an `IHostAutoEvent` instance to use in its implementation of a writer lock.</span></span> <span data-ttu-id="3ac3c-129">Узел может использовать указанного файла cookie для определения задач, ожидающих блокировки, вызывая итерационные методы [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) интерфейса.</span><span class="sxs-lookup"><span data-stu-id="3ac3c-129">The host can use the specified cookie to determine which tasks are waiting on the lock by calling the iteration methods of the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ac3c-130">Требования</span><span class="sxs-lookup"><span data-stu-id="3ac3c-130">Requirements</span></span>  
 <span data-ttu-id="3ac3c-131">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ac3c-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ac3c-132">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3ac3c-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3ac3c-133">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3ac3c-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3ac3c-134">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ac3c-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ac3c-135">См. также</span><span class="sxs-lookup"><span data-stu-id="3ac3c-135">See Also</span></span>  
 [<span data-ttu-id="3ac3c-136">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="3ac3c-136">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="3ac3c-137">Интерфейс IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="3ac3c-137">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="3ac3c-138">Интерфейс IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="3ac3c-138">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="3ac3c-139">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="3ac3c-139">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)

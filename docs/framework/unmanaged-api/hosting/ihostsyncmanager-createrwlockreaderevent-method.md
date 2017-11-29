---
title: "Метод IHostSyncManager::CreateRWLockReaderEvent"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSyncManager.CreateRWLockReaderEvent
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSyncManager::CreateRWLockReaderEvent
helpviewer_keywords:
- CreateRWLockReaderEvent method [.NET Framework hosting]
- IHostSyncManager::CreateRWLockReaderEvent method [.NET Framework hosting]
ms.assetid: 68c4ea19-c47c-45c6-b420-d3a2ba1c2d50
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a783f4511e27b5d230a90444e5a91b34327543cf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsyncmanagercreaterwlockreaderevent-method"></a><span data-ttu-id="0748d-102">Метод IHostSyncManager::CreateRWLockReaderEvent</span><span class="sxs-lookup"><span data-stu-id="0748d-102">IHostSyncManager::CreateRWLockReaderEvent Method</span></span>
<span data-ttu-id="0748d-103">Создает объект события ручного сброса для реализации блокировки чтения.</span><span class="sxs-lookup"><span data-stu-id="0748d-103">Creates a manual-reset event object for the implementation of a reader lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0748d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0748d-104">Syntax</span></span>  
  
```  
HRESULT CreateRWLockReaderEvent (  
    [in]  BOOL bInitialState,  
    [in]  SIZE_T cookie,  
    [out] IHostManualEvent **ppEvent  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0748d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0748d-105">Parameters</span></span>  
 `bInitialState`  
 <span data-ttu-id="0748d-106">[in] `true`, если `ppEvent` следует сигнальное; в противном случае — `false`.</span><span class="sxs-lookup"><span data-stu-id="0748d-106">[in] `true`, if `ppEvent` should be signaled; otherwise, `false`.</span></span>  
  
 `cookie`  
 <span data-ttu-id="0748d-107">[in] Файл cookie для связывания с блокировкой чтения.</span><span class="sxs-lookup"><span data-stu-id="0748d-107">[in] A cookie to associate with the reader lock.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="0748d-108">[out] Указатель на адрес [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) экземпляра, или значение null, если не удалось создать объект события.</span><span class="sxs-lookup"><span data-stu-id="0748d-108">[out] A pointer to the address of an [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0748d-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0748d-109">Return Value</span></span>  
  
|<span data-ttu-id="0748d-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0748d-110">HRESULT</span></span>|<span data-ttu-id="0748d-111">Описание</span><span class="sxs-lookup"><span data-stu-id="0748d-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0748d-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="0748d-112">S_OK</span></span>|<span data-ttu-id="0748d-113">`CreateRWLockReaderEvent`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="0748d-113">`CreateRWLockReaderEvent` returned successfully.</span></span>|  
|<span data-ttu-id="0748d-114">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0748d-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0748d-115">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="0748d-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0748d-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0748d-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0748d-117">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="0748d-117">The call timed out.</span></span>|  
|<span data-ttu-id="0748d-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0748d-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0748d-119">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="0748d-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0748d-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0748d-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0748d-121">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="0748d-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0748d-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0748d-122">E_FAIL</span></span>|<span data-ttu-id="0748d-123">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="0748d-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0748d-124">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="0748d-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0748d-125">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0748d-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="0748d-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="0748d-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="0748d-127">Не хватает памяти была доступна для создания запрошенного объекта события.</span><span class="sxs-lookup"><span data-stu-id="0748d-127">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0748d-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="0748d-128">Remarks</span></span>  
 <span data-ttu-id="0748d-129">Среда CLR вызывает `CreateRWLockReaderEvent` для получения ссылки на `IHostManualEvent` экземпляр для использования в своей реализации блокировку чтения.</span><span class="sxs-lookup"><span data-stu-id="0748d-129">The CLR calls `CreateRWLockReaderEvent` to get a reference to an `IHostManualEvent` instance to use in its implementation of a reader lock.</span></span> <span data-ttu-id="0748d-130">Узел может использовать файл cookie для определения задач, ожидающих блокировки чтения с помощью запроса к [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) интерфейса.</span><span class="sxs-lookup"><span data-stu-id="0748d-130">The host can use the cookie to determine which tasks are waiting on the reader lock by querying the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0748d-131">Требования</span><span class="sxs-lookup"><span data-stu-id="0748d-131">Requirements</span></span>  
 <span data-ttu-id="0748d-132">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0748d-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0748d-133">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0748d-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0748d-134">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0748d-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0748d-135">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0748d-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0748d-136">См. также</span><span class="sxs-lookup"><span data-stu-id="0748d-136">See Also</span></span>  
 [<span data-ttu-id="0748d-137">ICLRSyncManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="0748d-137">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="0748d-138">IHostAutoEvent-интерфейс</span><span class="sxs-lookup"><span data-stu-id="0748d-138">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="0748d-139">IHostManualEvent-интерфейс</span><span class="sxs-lookup"><span data-stu-id="0748d-139">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="0748d-140">Ihostsyncmanager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="0748d-140">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)

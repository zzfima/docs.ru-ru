---
title: Метод IHostSyncManager::CreateRWLockReaderEvent
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateRWLockReaderEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateRWLockReaderEvent
helpviewer_keywords:
- CreateRWLockReaderEvent method [.NET Framework hosting]
- IHostSyncManager::CreateRWLockReaderEvent method [.NET Framework hosting]
ms.assetid: 68c4ea19-c47c-45c6-b420-d3a2ba1c2d50
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da5b640093184e10ef9e3b895ce2328969a45ac9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61696344"
---
# <a name="ihostsyncmanagercreaterwlockreaderevent-method"></a><span data-ttu-id="a6e65-102">Метод IHostSyncManager::CreateRWLockReaderEvent</span><span class="sxs-lookup"><span data-stu-id="a6e65-102">IHostSyncManager::CreateRWLockReaderEvent Method</span></span>
<span data-ttu-id="a6e65-103">Создает объект события ручного сброса для реализации блокировки чтения.</span><span class="sxs-lookup"><span data-stu-id="a6e65-103">Creates a manual-reset event object for the implementation of a reader lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6e65-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a6e65-104">Syntax</span></span>  
  
```  
HRESULT CreateRWLockReaderEvent (  
    [in]  BOOL bInitialState,  
    [in]  SIZE_T cookie,  
    [out] IHostManualEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6e65-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a6e65-105">Parameters</span></span>  
 `bInitialState`  
 <span data-ttu-id="a6e65-106">[in] `true`, если `ppEvent` должно быть в сигнальном состоянии; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="a6e65-106">[in] `true`, if `ppEvent` should be signaled; otherwise, `false`.</span></span>  
  
 `cookie`  
 <span data-ttu-id="a6e65-107">[in] Файл cookie, связываемый с блокировкой чтения.</span><span class="sxs-lookup"><span data-stu-id="a6e65-107">[in] A cookie to associate with the reader lock.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="a6e65-108">[out] Указатель на адрес [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) экземпляра, или значение null, если не удалось создать объект события.</span><span class="sxs-lookup"><span data-stu-id="a6e65-108">[out] A pointer to the address of an [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a6e65-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a6e65-109">Return Value</span></span>  
  
|<span data-ttu-id="a6e65-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a6e65-110">HRESULT</span></span>|<span data-ttu-id="a6e65-111">Описание</span><span class="sxs-lookup"><span data-stu-id="a6e65-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a6e65-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="a6e65-112">S_OK</span></span>|<span data-ttu-id="a6e65-113">`CreateRWLockReaderEvent` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="a6e65-113">`CreateRWLockReaderEvent` returned successfully.</span></span>|  
|<span data-ttu-id="a6e65-114">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a6e65-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a6e65-115">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="a6e65-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a6e65-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a6e65-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a6e65-117">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="a6e65-117">The call timed out.</span></span>|  
|<span data-ttu-id="a6e65-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a6e65-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a6e65-119">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="a6e65-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a6e65-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a6e65-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a6e65-121">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="a6e65-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a6e65-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a6e65-122">E_FAIL</span></span>|<span data-ttu-id="a6e65-123">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="a6e65-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a6e65-124">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="a6e65-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a6e65-125">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a6e65-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a6e65-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="a6e65-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="a6e65-127">Недостаточно памяти, доступного для создания запрошенного объекта события.</span><span class="sxs-lookup"><span data-stu-id="a6e65-127">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a6e65-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="a6e65-128">Remarks</span></span>  
 <span data-ttu-id="a6e65-129">Среда CLR вызывает `CreateRWLockReaderEvent` для получения ссылки на `IHostManualEvent` экземпляр для использования в своей реализации блокировку чтения.</span><span class="sxs-lookup"><span data-stu-id="a6e65-129">The CLR calls `CreateRWLockReaderEvent` to get a reference to an `IHostManualEvent` instance to use in its implementation of a reader lock.</span></span> <span data-ttu-id="a6e65-130">Узел может использовать файл cookie для определения задач, ожидающих блокировку чтения, запросив [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="a6e65-130">The host can use the cookie to determine which tasks are waiting on the reader lock by querying the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6e65-131">Требования</span><span class="sxs-lookup"><span data-stu-id="a6e65-131">Requirements</span></span>  
 <span data-ttu-id="a6e65-132">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6e65-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6e65-133">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a6e65-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a6e65-134">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a6e65-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a6e65-135">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6e65-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6e65-136">См. также</span><span class="sxs-lookup"><span data-stu-id="a6e65-136">See also</span></span>

- [<span data-ttu-id="a6e65-137">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="a6e65-137">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="a6e65-138">Интерфейс IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="a6e65-138">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="a6e65-139">Интерфейс IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="a6e65-139">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="a6e65-140">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="a6e65-140">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)

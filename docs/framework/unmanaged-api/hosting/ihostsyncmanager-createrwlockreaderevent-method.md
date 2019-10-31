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
ms.openlocfilehash: 64cf6c80ab1cf4b3ca52c60d6e72b54c438f9f4a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73195838"
---
# <a name="ihostsyncmanagercreaterwlockreaderevent-method"></a><span data-ttu-id="dc7ac-102">Метод IHostSyncManager::CreateRWLockReaderEvent</span><span class="sxs-lookup"><span data-stu-id="dc7ac-102">IHostSyncManager::CreateRWLockReaderEvent Method</span></span>
<span data-ttu-id="dc7ac-103">Создает объект события ручного сброса для реализации блокировки чтения.</span><span class="sxs-lookup"><span data-stu-id="dc7ac-103">Creates a manual-reset event object for the implementation of a reader lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc7ac-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dc7ac-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateRWLockReaderEvent (  
    [in]  BOOL bInitialState,  
    [in]  SIZE_T cookie,  
    [out] IHostManualEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc7ac-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="dc7ac-105">Parameters</span></span>  
 `bInitialState`  
 <span data-ttu-id="dc7ac-106">[in] `true`, если `ppEvent` должны быть сигнальными; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="dc7ac-106">[in] `true`, if `ppEvent` should be signaled; otherwise, `false`.</span></span>  
  
 `cookie`  
 <span data-ttu-id="dc7ac-107">окне Файл cookie, связываемый с блокировкой чтения.</span><span class="sxs-lookup"><span data-stu-id="dc7ac-107">[in] A cookie to associate with the reader lock.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="dc7ac-108">заполняет Указатель на адрес экземпляра [ихостмануалевент](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) или значение null, если не удалось создать объект события.</span><span class="sxs-lookup"><span data-stu-id="dc7ac-108">[out] A pointer to the address of an [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dc7ac-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="dc7ac-109">Return Value</span></span>  
  
|<span data-ttu-id="dc7ac-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dc7ac-110">HRESULT</span></span>|<span data-ttu-id="dc7ac-111">Описание</span><span class="sxs-lookup"><span data-stu-id="dc7ac-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dc7ac-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="dc7ac-112">S_OK</span></span>|<span data-ttu-id="dc7ac-113">`CreateRWLockReaderEvent` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="dc7ac-113">`CreateRWLockReaderEvent` returned successfully.</span></span>|  
|<span data-ttu-id="dc7ac-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="dc7ac-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="dc7ac-115">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="dc7ac-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="dc7ac-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="dc7ac-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="dc7ac-117">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="dc7ac-117">The call timed out.</span></span>|  
|<span data-ttu-id="dc7ac-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="dc7ac-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="dc7ac-119">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="dc7ac-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="dc7ac-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="dc7ac-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="dc7ac-121">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="dc7ac-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="dc7ac-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="dc7ac-122">E_FAIL</span></span>|<span data-ttu-id="dc7ac-123">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="dc7ac-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="dc7ac-124">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="dc7ac-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="dc7ac-125">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="dc7ac-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="dc7ac-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="dc7ac-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="dc7ac-127">Недостаточно свободной памяти для создания запрошенного объекта события.</span><span class="sxs-lookup"><span data-stu-id="dc7ac-127">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dc7ac-128">Заметки</span><span class="sxs-lookup"><span data-stu-id="dc7ac-128">Remarks</span></span>  
 <span data-ttu-id="dc7ac-129">Среда CLR вызывает `CreateRWLockReaderEvent`, чтобы получить ссылку на экземпляр `IHostManualEvent`, используемый в реализации блокировки чтения.</span><span class="sxs-lookup"><span data-stu-id="dc7ac-129">The CLR calls `CreateRWLockReaderEvent` to get a reference to an `IHostManualEvent` instance to use in its implementation of a reader lock.</span></span> <span data-ttu-id="dc7ac-130">Узел может использовать файл cookie для определения задач, ожидающих блокировки чтения, путем запроса к интерфейсу [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="dc7ac-130">The host can use the cookie to determine which tasks are waiting on the reader lock by querying the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc7ac-131">Требования</span><span class="sxs-lookup"><span data-stu-id="dc7ac-131">Requirements</span></span>  
 <span data-ttu-id="dc7ac-132">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc7ac-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc7ac-133">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="dc7ac-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dc7ac-134">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="dc7ac-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dc7ac-135">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc7ac-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc7ac-136">См. также</span><span class="sxs-lookup"><span data-stu-id="dc7ac-136">See also</span></span>

- [<span data-ttu-id="dc7ac-137">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="dc7ac-137">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="dc7ac-138">Интерфейс IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="dc7ac-138">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="dc7ac-139">Интерфейс IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="dc7ac-139">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="dc7ac-140">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="dc7ac-140">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)

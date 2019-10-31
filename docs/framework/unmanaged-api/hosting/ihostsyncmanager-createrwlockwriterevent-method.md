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
ms.openlocfilehash: 13eb23c530a4fe1b491f41cc65cc94dacc9d34f4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192009"
---
# <a name="ihostsyncmanagercreaterwlockwriterevent-method"></a><span data-ttu-id="7e7b5-102">Метод IHostSyncManager::CreateRWLockWriterEvent</span><span class="sxs-lookup"><span data-stu-id="7e7b5-102">IHostSyncManager::CreateRWLockWriterEvent Method</span></span>
<span data-ttu-id="7e7b5-103">Создает объект события автоматического сброса для реализации блокировки модуля записи.</span><span class="sxs-lookup"><span data-stu-id="7e7b5-103">Creates an auto-reset event object for the implementation of a writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e7b5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7e7b5-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateRWLockWriterEvent (  
    [in]  SIZE_T cookie,  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e7b5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7e7b5-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="7e7b5-106">окне Файл cookie, связываемый с событием автоматического сброса.</span><span class="sxs-lookup"><span data-stu-id="7e7b5-106">[in] A cookie to associate with the auto-reset event.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="7e7b5-107">заполняет Указатель на адрес экземпляра [ихостаутоевент](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) или значение null, если не удалось создать объект события.</span><span class="sxs-lookup"><span data-stu-id="7e7b5-107">[out] A pointer to the address of an [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7e7b5-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7e7b5-108">Return Value</span></span>  
  
|<span data-ttu-id="7e7b5-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7e7b5-109">HRESULT</span></span>|<span data-ttu-id="7e7b5-110">Описание</span><span class="sxs-lookup"><span data-stu-id="7e7b5-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7e7b5-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="7e7b5-111">S_OK</span></span>|<span data-ttu-id="7e7b5-112">`CreateRWLockWriterEvent` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="7e7b5-112">`CreateRWLockWriterEvent` returned successfully.</span></span>|  
|<span data-ttu-id="7e7b5-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7e7b5-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7e7b5-114">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="7e7b5-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7e7b5-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7e7b5-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7e7b5-116">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="7e7b5-116">The call timed out.</span></span>|  
|<span data-ttu-id="7e7b5-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7e7b5-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7e7b5-118">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="7e7b5-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7e7b5-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7e7b5-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7e7b5-120">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="7e7b5-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7e7b5-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7e7b5-121">E_FAIL</span></span>|<span data-ttu-id="7e7b5-122">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="7e7b5-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7e7b5-123">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="7e7b5-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7e7b5-124">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7e7b5-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7e7b5-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="7e7b5-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="7e7b5-126">Недостаточно свободной памяти для создания запрошенного объекта события.</span><span class="sxs-lookup"><span data-stu-id="7e7b5-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7e7b5-127">Заметки</span><span class="sxs-lookup"><span data-stu-id="7e7b5-127">Remarks</span></span>  
 <span data-ttu-id="7e7b5-128">Среда CLR вызывает метод `CreateRWLockWriterEvent` для получения ссылки на экземпляр `IHostAutoEvent`, используемый в реализации блокировки записи.</span><span class="sxs-lookup"><span data-stu-id="7e7b5-128">The CLR calls the `CreateRWLockWriterEvent` method to get a reference to an `IHostAutoEvent` instance to use in its implementation of a writer lock.</span></span> <span data-ttu-id="7e7b5-129">Узел может использовать указанный файл cookie, чтобы определить, какие задачи ожидают блокировки, вызвав методы итерации интерфейса [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="7e7b5-129">The host can use the specified cookie to determine which tasks are waiting on the lock by calling the iteration methods of the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e7b5-130">Требования</span><span class="sxs-lookup"><span data-stu-id="7e7b5-130">Requirements</span></span>  
 <span data-ttu-id="7e7b5-131">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e7b5-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e7b5-132">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="7e7b5-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7e7b5-133">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="7e7b5-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7e7b5-134">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e7b5-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e7b5-135">См. также</span><span class="sxs-lookup"><span data-stu-id="7e7b5-135">See also</span></span>

- [<span data-ttu-id="7e7b5-136">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="7e7b5-136">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="7e7b5-137">Интерфейс IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="7e7b5-137">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="7e7b5-138">Интерфейс IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="7e7b5-138">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="7e7b5-139">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="7e7b5-139">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)

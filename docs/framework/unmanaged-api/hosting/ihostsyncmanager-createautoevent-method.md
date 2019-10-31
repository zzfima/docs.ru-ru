---
title: Метод IHostSyncManager::CreateAutoEvent
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateAutoEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateAutoEvent
helpviewer_keywords:
- IHostSyncManager::CreateAutoEvent method [.NET Framework hosting]
- CreateAutoEvent method [.NET Framework hosting]
ms.assetid: 3153643e-cf5c-4b44-8e0e-c2b22cb08208
topic_type:
- apiref
ms.openlocfilehash: b3778e12dd96d4f4653633252e13469601c4879d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139434"
---
# <a name="ihostsyncmanagercreateautoevent-method"></a><span data-ttu-id="f72b4-102">Метод IHostSyncManager::CreateAutoEvent</span><span class="sxs-lookup"><span data-stu-id="f72b4-102">IHostSyncManager::CreateAutoEvent Method</span></span>
<span data-ttu-id="f72b4-103">Создает объект события автоматического сброса.</span><span class="sxs-lookup"><span data-stu-id="f72b4-103">Creates an auto-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f72b4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f72b4-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAutoEvent (  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f72b4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f72b4-105">Parameters</span></span>  
 `ppEvent`  
 <span data-ttu-id="f72b4-106">заполняет Указатель на адрес экземпляра [ихостаутоевент](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) , реализуемого узлом, или значение null, если не удалось создать объект события.</span><span class="sxs-lookup"><span data-stu-id="f72b4-106">[out] A pointer to the address of an [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance implemented by the host, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f72b4-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f72b4-107">Return Value</span></span>  
  
|<span data-ttu-id="f72b4-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f72b4-108">HRESULT</span></span>|<span data-ttu-id="f72b4-109">Описание</span><span class="sxs-lookup"><span data-stu-id="f72b4-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f72b4-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f72b4-110">S_OK</span></span>|<span data-ttu-id="f72b4-111">`CreateAutoEvent` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="f72b4-111">`CreateAutoEvent` returned successfully.</span></span>|  
|<span data-ttu-id="f72b4-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f72b4-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f72b4-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="f72b4-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f72b4-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f72b4-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f72b4-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="f72b4-115">The call timed out.</span></span>|  
|<span data-ttu-id="f72b4-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f72b4-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f72b4-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="f72b4-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f72b4-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f72b4-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f72b4-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="f72b4-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f72b4-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f72b4-120">E_FAIL</span></span>|<span data-ttu-id="f72b4-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="f72b4-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f72b4-122">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="f72b4-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f72b4-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f72b4-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f72b4-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="f72b4-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="f72b4-125">Недостаточно свободной памяти для создания запрошенного объекта события.</span><span class="sxs-lookup"><span data-stu-id="f72b4-125">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f72b4-126">Заметки</span><span class="sxs-lookup"><span data-stu-id="f72b4-126">Remarks</span></span>  
 <span data-ttu-id="f72b4-127">`CreateAutoEvent` создает объект автоматического события, состояние которого автоматически меняется на несигнальное после освобождения ожидающего потока.</span><span class="sxs-lookup"><span data-stu-id="f72b4-127">`CreateAutoEvent` creates an auto-event object whose state is automatically changed to non-signaled after the waiting thread has been released.</span></span> <span data-ttu-id="f72b4-128">Этот метод отражает функцию `CreateEvent` Win32 со значением `false`, указанным для параметра `bManualReset`</span><span class="sxs-lookup"><span data-stu-id="f72b4-128">This method mirrors the Win32 `CreateEvent` function with a value of `false` specified for the `bManualReset` parameter</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f72b4-129">Требования</span><span class="sxs-lookup"><span data-stu-id="f72b4-129">Requirements</span></span>  
 <span data-ttu-id="f72b4-130">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f72b4-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f72b4-131">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f72b4-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f72b4-132">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f72b4-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f72b4-133">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f72b4-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f72b4-134">См. также</span><span class="sxs-lookup"><span data-stu-id="f72b4-134">See also</span></span>

- [<span data-ttu-id="f72b4-135">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="f72b4-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="f72b4-136">Интерфейс IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="f72b4-136">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="f72b4-137">Интерфейс IHostControl</span><span class="sxs-lookup"><span data-stu-id="f72b4-137">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
- [<span data-ttu-id="f72b4-138">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="f72b4-138">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)

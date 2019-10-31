---
title: Метод IHostSyncManager::CreateManualEvent
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateManualEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateManualEvent
helpviewer_keywords:
- CreateManualEvent method [.NET Framework hosting]
- IHostSyncManager::CreateManualEvent method [.NET Framework hosting]
ms.assetid: 68661fbd-09cf-46dc-890b-e694f8a3880a
topic_type:
- apiref
ms.openlocfilehash: 13679b4d40e660dfdd18e6fbafe19226b2ffda37
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73195873"
---
# <a name="ihostsyncmanagercreatemanualevent-method"></a><span data-ttu-id="10e65-102">Метод IHostSyncManager::CreateManualEvent</span><span class="sxs-lookup"><span data-stu-id="10e65-102">IHostSyncManager::CreateManualEvent Method</span></span>
<span data-ttu-id="10e65-103">Создает объект события ручного сброса.</span><span class="sxs-lookup"><span data-stu-id="10e65-103">Creates a manual-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10e65-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="10e65-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateManualEvent (  
    [in]  BOOL bInitialState,  
    [out] IHostManualEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="10e65-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="10e65-105">Parameters</span></span>  
 `bInitialState`  
 <span data-ttu-id="10e65-106">[in] `true`, если объект имеет сигнальное состояние; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="10e65-106">[in] `true`, if the object is signaled; otherwise, `false`.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="10e65-107">заполняет Указатель на адрес экземпляра [ихостмануалевент](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) или значение null, если не удалось создать событие.</span><span class="sxs-lookup"><span data-stu-id="10e65-107">[out] A pointer to the address of an [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance, or null if the event could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="10e65-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="10e65-108">Return Value</span></span>  
  
|<span data-ttu-id="10e65-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="10e65-109">HRESULT</span></span>|<span data-ttu-id="10e65-110">Описание</span><span class="sxs-lookup"><span data-stu-id="10e65-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="10e65-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="10e65-111">S_OK</span></span>|<span data-ttu-id="10e65-112">`CreateManualEvent` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="10e65-112">`CreateManualEvent` returned successfully.</span></span>|  
|<span data-ttu-id="10e65-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="10e65-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="10e65-114">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="10e65-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="10e65-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="10e65-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="10e65-116">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="10e65-116">The call timed out.</span></span>|  
|<span data-ttu-id="10e65-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="10e65-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="10e65-118">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="10e65-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="10e65-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="10e65-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="10e65-120">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="10e65-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="10e65-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="10e65-121">E_FAIL</span></span>|<span data-ttu-id="10e65-122">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="10e65-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="10e65-123">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="10e65-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="10e65-124">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="10e65-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="10e65-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="10e65-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="10e65-126">Недостаточно свободной памяти для создания запрошенного объекта события.</span><span class="sxs-lookup"><span data-stu-id="10e65-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="10e65-127">Заметки</span><span class="sxs-lookup"><span data-stu-id="10e65-127">Remarks</span></span>  
 <span data-ttu-id="10e65-128">`CreateManualEvent` создает `IHostManualEvent`, объект события ручного сброса, требующий вызова метода [ихостмануалевент:: Reset](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md) , чтобы перевести его в несигнальное состояние.</span><span class="sxs-lookup"><span data-stu-id="10e65-128">`CreateManualEvent` creates an `IHostManualEvent`, a manual-reset event object that requires a call to the [IHostManualEvent::Reset](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md) method to set it to a non-signaled state.</span></span> <span data-ttu-id="10e65-129">`CreateManualEvent` отображает функцию `CreateEvent` Win32 со значением `true`, указанным для параметра `bManualReset`.</span><span class="sxs-lookup"><span data-stu-id="10e65-129">`CreateManualEvent` mirrors the Win32 `CreateEvent` function with a value of `true` specified for the `bManualReset` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10e65-130">Требования</span><span class="sxs-lookup"><span data-stu-id="10e65-130">Requirements</span></span>  
 <span data-ttu-id="10e65-131">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10e65-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10e65-132">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="10e65-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="10e65-133">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="10e65-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="10e65-134">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10e65-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10e65-135">См. также</span><span class="sxs-lookup"><span data-stu-id="10e65-135">See also</span></span>

- [<span data-ttu-id="10e65-136">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="10e65-136">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="10e65-137">Интерфейс IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="10e65-137">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="10e65-138">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="10e65-138">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)

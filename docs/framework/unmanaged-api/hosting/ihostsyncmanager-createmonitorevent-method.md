---
title: Метод IHostSyncManager::CreateMonitorEvent
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateMonitorEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateMonitorEvent
helpviewer_keywords:
- CreateMonitorEvent method [.NET Framework hosting]
- IHostSyncManager::CreateMonitorEvent method [.NET Framework hosting]
ms.assetid: 524c7fd3-9b5c-46e7-99ba-555fd2fe33f0
topic_type:
- apiref
ms.openlocfilehash: f7426585045c7ae81377ec9bfca9d397d6f734cb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192019"
---
# <a name="ihostsyncmanagercreatemonitorevent-method"></a><span data-ttu-id="6aa23-102">Метод IHostSyncManager::CreateMonitorEvent</span><span class="sxs-lookup"><span data-stu-id="6aa23-102">IHostSyncManager::CreateMonitorEvent Method</span></span>
<span data-ttu-id="6aa23-103">Создает Отслеживаемый объект события автоматического сброса.</span><span class="sxs-lookup"><span data-stu-id="6aa23-103">Creates a monitored auto-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6aa23-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6aa23-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateMonitorEvent (  
    [in]  SIZE_T cookie,  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6aa23-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6aa23-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="6aa23-106">окне Файл cookie, связываемый с объектом события.</span><span class="sxs-lookup"><span data-stu-id="6aa23-106">[in] A cookie to associate with the event object.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="6aa23-107">заполняет Указатель на адрес экземпляра [ихостаутоевент](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) или значение null, если не удалось создать объект события.</span><span class="sxs-lookup"><span data-stu-id="6aa23-107">[out] A pointer to the address of an [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6aa23-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6aa23-108">Return Value</span></span>  
  
|<span data-ttu-id="6aa23-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6aa23-109">HRESULT</span></span>|<span data-ttu-id="6aa23-110">Описание</span><span class="sxs-lookup"><span data-stu-id="6aa23-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6aa23-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="6aa23-111">S_OK</span></span>|<span data-ttu-id="6aa23-112">`CreateMonitorEvent` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="6aa23-112">`CreateMonitorEvent` returned successfully.</span></span>|  
|<span data-ttu-id="6aa23-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6aa23-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6aa23-114">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="6aa23-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6aa23-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6aa23-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6aa23-116">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="6aa23-116">The call timed out.</span></span>|  
|<span data-ttu-id="6aa23-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6aa23-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6aa23-118">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="6aa23-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6aa23-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6aa23-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6aa23-120">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="6aa23-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6aa23-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6aa23-121">E_FAIL</span></span>|<span data-ttu-id="6aa23-122">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="6aa23-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6aa23-123">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="6aa23-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6aa23-124">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="6aa23-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="6aa23-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="6aa23-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="6aa23-126">Недостаточно свободной памяти для создания запрошенного объекта события.</span><span class="sxs-lookup"><span data-stu-id="6aa23-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6aa23-127">Заметки</span><span class="sxs-lookup"><span data-stu-id="6aa23-127">Remarks</span></span>  
 <span data-ttu-id="6aa23-128">`CreateMonitorEvent` возвращает `IHostAutoEvent`, который среда CLR использует в реализации управляемого типа <xref:System.Threading.Monitor?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6aa23-128">`CreateMonitorEvent` returns an `IHostAutoEvent` that the CLR uses in its implementation of the managed <xref:System.Threading.Monitor?displayProperty=nameWithType> type.</span></span> <span data-ttu-id="6aa23-129">Этот метод отражает функцию `CreateEvent` Win32 со значением `false`, указанным для параметра `bManualReset`.</span><span class="sxs-lookup"><span data-stu-id="6aa23-129">This method mirrors the Win32 `CreateEvent` function, with a value of `false` specified for the `bManualReset` parameter.</span></span>  
  
 <span data-ttu-id="6aa23-130">Узел может использовать файл cookie, чтобы определить, какая задача ожидает монитор, вызвав метод [ICLRSyncManager:: GetMonitorOwner](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getmonitorowner-method.md) .</span><span class="sxs-lookup"><span data-stu-id="6aa23-130">The host can use the cookie to determine which task is waiting on the monitor by calling the [ICLRSyncManager::GetMonitorOwner](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getmonitorowner-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6aa23-131">Требования</span><span class="sxs-lookup"><span data-stu-id="6aa23-131">Requirements</span></span>  
 <span data-ttu-id="6aa23-132">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6aa23-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6aa23-133">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="6aa23-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6aa23-134">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="6aa23-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6aa23-135">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6aa23-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6aa23-136">См. также</span><span class="sxs-lookup"><span data-stu-id="6aa23-136">See also</span></span>

- [<span data-ttu-id="6aa23-137">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="6aa23-137">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="6aa23-138">Интерфейс IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="6aa23-138">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="6aa23-139">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="6aa23-139">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- <xref:System.Threading.Monitor>

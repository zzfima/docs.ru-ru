---
title: "Метод IHostSyncManager::CreateMonitorEvent"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ae12db71f4eae0f7d887fda26e05401f4f23ee5c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsyncmanagercreatemonitorevent-method"></a><span data-ttu-id="37216-102">Метод IHostSyncManager::CreateMonitorEvent</span><span class="sxs-lookup"><span data-stu-id="37216-102">IHostSyncManager::CreateMonitorEvent Method</span></span>
<span data-ttu-id="37216-103">Создает объект, отслеживаемый события автоматического сброса.</span><span class="sxs-lookup"><span data-stu-id="37216-103">Creates a monitored auto-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37216-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="37216-104">Syntax</span></span>  
  
```  
HRESULT CreateMonitorEvent (  
    [in]  SIZE_T cookie,  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="37216-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="37216-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="37216-106">[in] Файл cookie, связываемый с объекта события.</span><span class="sxs-lookup"><span data-stu-id="37216-106">[in] A cookie to associate with the event object.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="37216-107">[out] Указатель на адрес [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) экземпляра, или значение null, если не удалось создать объект события.</span><span class="sxs-lookup"><span data-stu-id="37216-107">[out] A pointer to the address of an [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="37216-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="37216-108">Return Value</span></span>  
  
|<span data-ttu-id="37216-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="37216-109">HRESULT</span></span>|<span data-ttu-id="37216-110">Описание</span><span class="sxs-lookup"><span data-stu-id="37216-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="37216-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="37216-111">S_OK</span></span>|<span data-ttu-id="37216-112">`CreateMonitorEvent`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="37216-112">`CreateMonitorEvent` returned successfully.</span></span>|  
|<span data-ttu-id="37216-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="37216-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="37216-114">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="37216-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="37216-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="37216-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="37216-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="37216-116">The call timed out.</span></span>|  
|<span data-ttu-id="37216-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="37216-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="37216-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="37216-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="37216-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="37216-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="37216-120">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="37216-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="37216-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="37216-121">E_FAIL</span></span>|<span data-ttu-id="37216-122">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="37216-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="37216-123">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="37216-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="37216-124">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="37216-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="37216-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="37216-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="37216-126">Не хватает памяти была доступна для создания запрошенного объекта события.</span><span class="sxs-lookup"><span data-stu-id="37216-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="37216-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="37216-127">Remarks</span></span>  
 <span data-ttu-id="37216-128">`CreateMonitorEvent`Возвращает `IHostAutoEvent` , среда CLR использует в своей реализации управляемый <xref:System.Threading.Monitor?displayProperty=nameWithType> типа.</span><span class="sxs-lookup"><span data-stu-id="37216-128">`CreateMonitorEvent` returns an `IHostAutoEvent` that the CLR uses in its implementation of the managed <xref:System.Threading.Monitor?displayProperty=nameWithType> type.</span></span> <span data-ttu-id="37216-129">Этот метод получает зеркально Win32 `CreateEvent` функции со значением `false` указано `bManualReset` параметра.</span><span class="sxs-lookup"><span data-stu-id="37216-129">This method mirrors the Win32 `CreateEvent` function, with a value of `false` specified for the `bManualReset` parameter.</span></span>  
  
 <span data-ttu-id="37216-130">Узел может использовать куки-файл, чтобы определить, какие задача ожидает монитор, вызвав [ICLRSyncManager::GetMonitorOwner](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getmonitorowner-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="37216-130">The host can use the cookie to determine which task is waiting on the monitor by calling the [ICLRSyncManager::GetMonitorOwner](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getmonitorowner-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37216-131">Требования</span><span class="sxs-lookup"><span data-stu-id="37216-131">Requirements</span></span>  
 <span data-ttu-id="37216-132">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37216-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37216-133">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="37216-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="37216-134">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="37216-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="37216-135">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37216-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37216-136">См. также</span><span class="sxs-lookup"><span data-stu-id="37216-136">See Also</span></span>  
 [<span data-ttu-id="37216-137">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="37216-137">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="37216-138">Интерфейс IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="37216-138">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="37216-139">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="37216-139">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [<span data-ttu-id="37216-140">Мониторы</span><span class="sxs-lookup"><span data-stu-id="37216-140">Monitors</span></span>](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db)

---
title: "Метод IHostSyncManager::CreateManualEvent"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSyncManager.CreateManualEvent
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSyncManager::CreateManualEvent
helpviewer_keywords:
- CreateManualEvent method [.NET Framework hosting]
- IHostSyncManager::CreateManualEvent method [.NET Framework hosting]
ms.assetid: 68661fbd-09cf-46dc-890b-e694f8a3880a
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b7b43a6b26c3788708419d3598e95bba1273dcb9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsyncmanagercreatemanualevent-method"></a><span data-ttu-id="6dfcd-102">Метод IHostSyncManager::CreateManualEvent</span><span class="sxs-lookup"><span data-stu-id="6dfcd-102">IHostSyncManager::CreateManualEvent Method</span></span>
<span data-ttu-id="6dfcd-103">Создает объект события ручного сброса.</span><span class="sxs-lookup"><span data-stu-id="6dfcd-103">Creates a manual-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6dfcd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6dfcd-104">Syntax</span></span>  
  
```  
HRESULT CreateManualEvent (  
    [in]  BOOL bInitialState,  
    [out] IHostManualEvent **ppEvent  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6dfcd-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6dfcd-105">Parameters</span></span>  
 `bInitialState`  
 <span data-ttu-id="6dfcd-106">[in] `true`, если объект находится в сигнальном состоянии; в противном случае — `false`.</span><span class="sxs-lookup"><span data-stu-id="6dfcd-106">[in] `true`, if the object is signaled; otherwise, `false`.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="6dfcd-107">[out] Указатель на адрес [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) экземпляра, или значение null, если не удается создать событие.</span><span class="sxs-lookup"><span data-stu-id="6dfcd-107">[out] A pointer to the address of an [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance, or null if the event could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6dfcd-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6dfcd-108">Return Value</span></span>  
  
|<span data-ttu-id="6dfcd-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6dfcd-109">HRESULT</span></span>|<span data-ttu-id="6dfcd-110">Описание</span><span class="sxs-lookup"><span data-stu-id="6dfcd-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6dfcd-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="6dfcd-111">S_OK</span></span>|<span data-ttu-id="6dfcd-112">`CreateManualEvent`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="6dfcd-112">`CreateManualEvent` returned successfully.</span></span>|  
|<span data-ttu-id="6dfcd-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6dfcd-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6dfcd-114">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="6dfcd-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6dfcd-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6dfcd-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6dfcd-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="6dfcd-116">The call timed out.</span></span>|  
|<span data-ttu-id="6dfcd-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6dfcd-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6dfcd-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="6dfcd-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6dfcd-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6dfcd-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6dfcd-120">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="6dfcd-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6dfcd-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6dfcd-121">E_FAIL</span></span>|<span data-ttu-id="6dfcd-122">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="6dfcd-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6dfcd-123">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="6dfcd-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6dfcd-124">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="6dfcd-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="6dfcd-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="6dfcd-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="6dfcd-126">Не хватает памяти была доступна для создания запрошенного объекта события.</span><span class="sxs-lookup"><span data-stu-id="6dfcd-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6dfcd-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="6dfcd-127">Remarks</span></span>  
 <span data-ttu-id="6dfcd-128">`CreateManualEvent`Создает `IHostManualEvent`, объект события ручного сброса, который требуется вызов [IHostManualEvent::Reset](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md) метод присваивается несигнальное состояние.</span><span class="sxs-lookup"><span data-stu-id="6dfcd-128">`CreateManualEvent` creates an `IHostManualEvent`, a manual-reset event object that requires a call to the [IHostManualEvent::Reset](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md) method to set it to a non-signaled state.</span></span> <span data-ttu-id="6dfcd-129">`CreateManualEvent`зеркально отражает Win32 `CreateEvent` функции со значением `true` указано `bManualReset` параметра.</span><span class="sxs-lookup"><span data-stu-id="6dfcd-129">`CreateManualEvent` mirrors the Win32 `CreateEvent` function with a value of `true` specified for the `bManualReset` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6dfcd-130">Требования</span><span class="sxs-lookup"><span data-stu-id="6dfcd-130">Requirements</span></span>  
 <span data-ttu-id="6dfcd-131">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6dfcd-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6dfcd-132">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6dfcd-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6dfcd-133">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6dfcd-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6dfcd-134">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6dfcd-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dfcd-135">См. также</span><span class="sxs-lookup"><span data-stu-id="6dfcd-135">See Also</span></span>  
 [<span data-ttu-id="6dfcd-136">ICLRSyncManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="6dfcd-136">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="6dfcd-137">IHostManualEvent-интерфейс</span><span class="sxs-lookup"><span data-stu-id="6dfcd-137">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="6dfcd-138">Ihostsyncmanager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="6dfcd-138">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)

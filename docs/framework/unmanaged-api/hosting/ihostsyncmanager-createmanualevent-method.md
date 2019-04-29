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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ada9a3131ea3063239ab7897d0096f0accbd0f94
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697268"
---
# <a name="ihostsyncmanagercreatemanualevent-method"></a><span data-ttu-id="49373-102">Метод IHostSyncManager::CreateManualEvent</span><span class="sxs-lookup"><span data-stu-id="49373-102">IHostSyncManager::CreateManualEvent Method</span></span>
<span data-ttu-id="49373-103">Создает объект события ручного сброса.</span><span class="sxs-lookup"><span data-stu-id="49373-103">Creates a manual-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49373-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="49373-104">Syntax</span></span>  
  
```  
HRESULT CreateManualEvent (  
    [in]  BOOL bInitialState,  
    [out] IHostManualEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="49373-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="49373-105">Parameters</span></span>  
 `bInitialState`  
 <span data-ttu-id="49373-106">[in] `true`, если объект находится в сигнальном состоянии; в противном случае — значение `false`.</span><span class="sxs-lookup"><span data-stu-id="49373-106">[in] `true`, if the object is signaled; otherwise, `false`.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="49373-107">[out] Указатель на адрес [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) экземпляра, или значение null, если не удалось создать событие.</span><span class="sxs-lookup"><span data-stu-id="49373-107">[out] A pointer to the address of an [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance, or null if the event could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="49373-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="49373-108">Return Value</span></span>  
  
|<span data-ttu-id="49373-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="49373-109">HRESULT</span></span>|<span data-ttu-id="49373-110">Описание</span><span class="sxs-lookup"><span data-stu-id="49373-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="49373-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="49373-111">S_OK</span></span>|<span data-ttu-id="49373-112">`CreateManualEvent` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="49373-112">`CreateManualEvent` returned successfully.</span></span>|  
|<span data-ttu-id="49373-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="49373-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="49373-114">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="49373-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="49373-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="49373-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="49373-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="49373-116">The call timed out.</span></span>|  
|<span data-ttu-id="49373-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="49373-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="49373-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="49373-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="49373-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="49373-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="49373-120">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="49373-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="49373-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="49373-121">E_FAIL</span></span>|<span data-ttu-id="49373-122">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="49373-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="49373-123">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="49373-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="49373-124">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="49373-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="49373-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="49373-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="49373-126">Недостаточно памяти, доступного для создания запрошенного объекта события.</span><span class="sxs-lookup"><span data-stu-id="49373-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="49373-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="49373-127">Remarks</span></span>  
 <span data-ttu-id="49373-128">`CreateManualEvent` Создает `IHostManualEvent`, объект события ручного сброса, который требуется вызвать [IHostManualEvent::Reset](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md) метод, чтобы задать его в сигнальное состояние.</span><span class="sxs-lookup"><span data-stu-id="49373-128">`CreateManualEvent` creates an `IHostManualEvent`, a manual-reset event object that requires a call to the [IHostManualEvent::Reset](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md) method to set it to a non-signaled state.</span></span> <span data-ttu-id="49373-129">`CreateManualEvent` зеркально отражает Win32 `CreateEvent` функции со значением `true` указанный для `bManualReset` параметра.</span><span class="sxs-lookup"><span data-stu-id="49373-129">`CreateManualEvent` mirrors the Win32 `CreateEvent` function with a value of `true` specified for the `bManualReset` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49373-130">Требования</span><span class="sxs-lookup"><span data-stu-id="49373-130">Requirements</span></span>  
 <span data-ttu-id="49373-131">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49373-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49373-132">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="49373-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="49373-133">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="49373-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="49373-134">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49373-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49373-135">См. также</span><span class="sxs-lookup"><span data-stu-id="49373-135">See also</span></span>

- [<span data-ttu-id="49373-136">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="49373-136">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="49373-137">Интерфейс IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="49373-137">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="49373-138">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="49373-138">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)

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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b9c91a982a5f3d28b43a301f961601485639bb91
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61696656"
---
# <a name="ihostsyncmanagercreateautoevent-method"></a><span data-ttu-id="8ff6e-102">Метод IHostSyncManager::CreateAutoEvent</span><span class="sxs-lookup"><span data-stu-id="8ff6e-102">IHostSyncManager::CreateAutoEvent Method</span></span>
<span data-ttu-id="8ff6e-103">Создает объект события автоматического сброса.</span><span class="sxs-lookup"><span data-stu-id="8ff6e-103">Creates an auto-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ff6e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8ff6e-104">Syntax</span></span>  
  
```  
HRESULT CreateAutoEvent (  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ff6e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8ff6e-105">Parameters</span></span>  
 `ppEvent`  
 <span data-ttu-id="8ff6e-106">[out] Указатель на адрес [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) экземпляр реализованного узлом, или значение null, если не удалось создать объект события.</span><span class="sxs-lookup"><span data-stu-id="8ff6e-106">[out] A pointer to the address of an [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance implemented by the host, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8ff6e-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8ff6e-107">Return Value</span></span>  
  
|<span data-ttu-id="8ff6e-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8ff6e-108">HRESULT</span></span>|<span data-ttu-id="8ff6e-109">Описание</span><span class="sxs-lookup"><span data-stu-id="8ff6e-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8ff6e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="8ff6e-110">S_OK</span></span>|<span data-ttu-id="8ff6e-111">`CreateAutoEvent` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="8ff6e-111">`CreateAutoEvent` returned successfully.</span></span>|  
|<span data-ttu-id="8ff6e-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8ff6e-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8ff6e-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="8ff6e-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8ff6e-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8ff6e-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8ff6e-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="8ff6e-115">The call timed out.</span></span>|  
|<span data-ttu-id="8ff6e-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8ff6e-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8ff6e-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="8ff6e-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8ff6e-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8ff6e-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8ff6e-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="8ff6e-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8ff6e-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8ff6e-120">E_FAIL</span></span>|<span data-ttu-id="8ff6e-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="8ff6e-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8ff6e-122">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="8ff6e-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8ff6e-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="8ff6e-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8ff6e-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="8ff6e-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="8ff6e-125">Недостаточно памяти, доступного для создания запрошенного объекта события.</span><span class="sxs-lookup"><span data-stu-id="8ff6e-125">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8ff6e-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="8ff6e-126">Remarks</span></span>  
 <span data-ttu-id="8ff6e-127">`CreateAutoEvent` Создает объект автоматического события, состояние которого будет автоматически изменено на несигнальное после выпуска ожидающий поток.</span><span class="sxs-lookup"><span data-stu-id="8ff6e-127">`CreateAutoEvent` creates an auto-event object whose state is automatically changed to non-signaled after the waiting thread has been released.</span></span> <span data-ttu-id="8ff6e-128">Этот метод отражает Win32 `CreateEvent` функции со значением `false` указанный для `bManualReset` параметр</span><span class="sxs-lookup"><span data-stu-id="8ff6e-128">This method mirrors the Win32 `CreateEvent` function with a value of `false` specified for the `bManualReset` parameter</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ff6e-129">Требования</span><span class="sxs-lookup"><span data-stu-id="8ff6e-129">Requirements</span></span>  
 <span data-ttu-id="8ff6e-130">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ff6e-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ff6e-131">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8ff6e-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8ff6e-132">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8ff6e-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8ff6e-133">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ff6e-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ff6e-134">См. также</span><span class="sxs-lookup"><span data-stu-id="8ff6e-134">See also</span></span>

- [<span data-ttu-id="8ff6e-135">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="8ff6e-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="8ff6e-136">Интерфейс IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="8ff6e-136">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="8ff6e-137">Интерфейс IHostControl</span><span class="sxs-lookup"><span data-stu-id="8ff6e-137">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
- [<span data-ttu-id="8ff6e-138">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="8ff6e-138">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)

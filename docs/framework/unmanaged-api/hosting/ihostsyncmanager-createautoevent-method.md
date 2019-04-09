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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59180645"
---
# <a name="ihostsyncmanagercreateautoevent-method"></a><span data-ttu-id="12227-102">Метод IHostSyncManager::CreateAutoEvent</span><span class="sxs-lookup"><span data-stu-id="12227-102">IHostSyncManager::CreateAutoEvent Method</span></span>
<span data-ttu-id="12227-103">Создает объект события автоматического сброса.</span><span class="sxs-lookup"><span data-stu-id="12227-103">Creates an auto-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12227-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="12227-104">Syntax</span></span>  
  
```  
HRESULT CreateAutoEvent (  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="12227-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="12227-105">Parameters</span></span>  
 `ppEvent`  
 <span data-ttu-id="12227-106">[out] Указатель на адрес [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) экземпляр реализованного узлом, или значение null, если не удалось создать объект события.</span><span class="sxs-lookup"><span data-stu-id="12227-106">[out] A pointer to the address of an [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance implemented by the host, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="12227-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="12227-107">Return Value</span></span>  
  
|<span data-ttu-id="12227-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="12227-108">HRESULT</span></span>|<span data-ttu-id="12227-109">Описание</span><span class="sxs-lookup"><span data-stu-id="12227-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="12227-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="12227-110">S_OK</span></span>|`CreateAutoEvent` <span data-ttu-id="12227-111">успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="12227-111">returned successfully.</span></span>|  
|<span data-ttu-id="12227-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="12227-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="12227-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="12227-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="12227-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="12227-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="12227-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="12227-115">The call timed out.</span></span>|  
|<span data-ttu-id="12227-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="12227-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="12227-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="12227-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="12227-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="12227-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="12227-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="12227-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="12227-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="12227-120">E_FAIL</span></span>|<span data-ttu-id="12227-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="12227-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="12227-122">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="12227-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="12227-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="12227-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="12227-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="12227-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="12227-125">Недостаточно памяти, доступного для создания запрошенного объекта события.</span><span class="sxs-lookup"><span data-stu-id="12227-125">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="12227-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="12227-126">Remarks</span></span>  
 `CreateAutoEvent` <span data-ttu-id="12227-127">Создает объект автоматического события, состояние которого будет автоматически изменено на несигнальное после выпуска ожидающий поток.</span><span class="sxs-lookup"><span data-stu-id="12227-127">creates an auto-event object whose state is automatically changed to non-signaled after the waiting thread has been released.</span></span> <span data-ttu-id="12227-128">Этот метод отражает Win32 `CreateEvent` функции со значением `false` указанный для `bManualReset` параметр</span><span class="sxs-lookup"><span data-stu-id="12227-128">This method mirrors the Win32 `CreateEvent` function with a value of `false` specified for the `bManualReset` parameter</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12227-129">Требования</span><span class="sxs-lookup"><span data-stu-id="12227-129">Requirements</span></span>  
 <span data-ttu-id="12227-130">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="12227-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12227-131">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="12227-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="12227-132">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="12227-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="12227-133">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="12227-133">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="12227-134">См. также</span><span class="sxs-lookup"><span data-stu-id="12227-134">See also</span></span>

- [<span data-ttu-id="12227-135">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="12227-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="12227-136">Интерфейс IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="12227-136">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="12227-137">Интерфейс IHostControl</span><span class="sxs-lookup"><span data-stu-id="12227-137">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
- [<span data-ttu-id="12227-138">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="12227-138">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)

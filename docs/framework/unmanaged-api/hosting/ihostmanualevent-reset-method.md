---
title: Метод IHostManualEvent::Reset
ms.date: 03/30/2017
api_name:
- IHostManualEvent.Reset
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent::Reset
helpviewer_keywords:
- Reset method, IHostManualEvent interface [.NET Framework hosting]
- IHostManualEvent::Reset method [.NET Framework hosting]
ms.assetid: 0d101168-b5e3-49ce-90c7-85cf2db83c4c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9b3de70e6bdecba6370174ee825d2dec7c14270e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61935685"
---
# <a name="ihostmanualeventreset-method"></a><span data-ttu-id="6755d-102">Метод IHostManualEvent::Reset</span><span class="sxs-lookup"><span data-stu-id="6755d-102">IHostManualEvent::Reset Method</span></span>
<span data-ttu-id="6755d-103">Сбрасывает текущий [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) экземпляра в сигнальное состояние.</span><span class="sxs-lookup"><span data-stu-id="6755d-103">Resets the current [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance to a non-signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6755d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6755d-104">Syntax</span></span>  
  
```  
HRESULT Reset ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="6755d-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6755d-105">Return Value</span></span>  
  
|<span data-ttu-id="6755d-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6755d-106">HRESULT</span></span>|<span data-ttu-id="6755d-107">Описание</span><span class="sxs-lookup"><span data-stu-id="6755d-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6755d-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="6755d-108">S_OK</span></span>|<span data-ttu-id="6755d-109">`Reset` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="6755d-109">`Reset` returned successfully.</span></span>|  
|<span data-ttu-id="6755d-110">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6755d-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6755d-111">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="6755d-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6755d-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6755d-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6755d-113">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="6755d-113">The call timed out.</span></span>|  
|<span data-ttu-id="6755d-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6755d-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6755d-115">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="6755d-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6755d-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6755d-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6755d-117">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="6755d-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6755d-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6755d-118">E_FAIL</span></span>|<span data-ttu-id="6755d-119">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="6755d-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6755d-120">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="6755d-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6755d-121">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="6755d-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6755d-122">Требования</span><span class="sxs-lookup"><span data-stu-id="6755d-122">Requirements</span></span>  
 <span data-ttu-id="6755d-123">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6755d-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6755d-124">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6755d-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6755d-125">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6755d-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6755d-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6755d-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6755d-127">См. также</span><span class="sxs-lookup"><span data-stu-id="6755d-127">See also</span></span>

- [<span data-ttu-id="6755d-128">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="6755d-128">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="6755d-129">Интерфейс IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="6755d-129">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="6755d-130">Интерфейс IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="6755d-130">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="6755d-131">Интерфейс IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="6755d-131">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="6755d-132">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="6755d-132">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)

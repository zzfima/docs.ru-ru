---
title: Метод IHostManualEvent::Set
ms.date: 03/30/2017
api_name:
- IHostManualEvent.Set
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent::Set
helpviewer_keywords:
- Set method, IHostManualEvent interface [.NET Framework hosting]
- IHostManualEvent::Set method [.NET Framework hosting]
ms.assetid: e930c174-f71d-4faa-bb59-f0fb3df4d77b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3a10d7d5069b8fe42144517a028ed9258b0633da
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440607"
---
# <a name="ihostmanualeventset-method"></a><span data-ttu-id="b6200-102">Метод IHostManualEvent::Set</span><span class="sxs-lookup"><span data-stu-id="b6200-102">IHostManualEvent::Set Method</span></span>
<span data-ttu-id="b6200-103">Задает текущий [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) экземпляр сигнальное состояние.</span><span class="sxs-lookup"><span data-stu-id="b6200-103">Sets the current [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance to a signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6200-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b6200-104">Syntax</span></span>  
  
```  
HRESULT Set ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="b6200-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b6200-105">Return Value</span></span>  
  
|<span data-ttu-id="b6200-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b6200-106">HRESULT</span></span>|<span data-ttu-id="b6200-107">Описание</span><span class="sxs-lookup"><span data-stu-id="b6200-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b6200-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="b6200-108">S_OK</span></span>|<span data-ttu-id="b6200-109">`Set` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="b6200-109">`Set` returned successfully.</span></span>|  
|<span data-ttu-id="b6200-110">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b6200-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b6200-111">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="b6200-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b6200-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b6200-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b6200-113">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="b6200-113">The call timed out.</span></span>|  
|<span data-ttu-id="b6200-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b6200-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b6200-115">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="b6200-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b6200-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b6200-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b6200-117">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="b6200-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b6200-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b6200-118">E_FAIL</span></span>|<span data-ttu-id="b6200-119">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="b6200-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b6200-120">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="b6200-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b6200-121">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b6200-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b6200-122">Требования</span><span class="sxs-lookup"><span data-stu-id="b6200-122">Requirements</span></span>  
 <span data-ttu-id="b6200-123">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6200-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6200-124">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b6200-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b6200-125">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b6200-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b6200-126">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6200-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6200-127">См. также</span><span class="sxs-lookup"><span data-stu-id="b6200-127">See Also</span></span>  
 [<span data-ttu-id="b6200-128">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="b6200-128">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="b6200-129">Интерфейс IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="b6200-129">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="b6200-130">Интерфейс IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="b6200-130">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="b6200-131">Интерфейс IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="b6200-131">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 [<span data-ttu-id="b6200-132">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="b6200-132">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)

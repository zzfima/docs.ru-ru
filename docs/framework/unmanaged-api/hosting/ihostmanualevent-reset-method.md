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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59148568"
---
# <a name="ihostmanualeventreset-method"></a><span data-ttu-id="53a0c-102">Метод IHostManualEvent::Reset</span><span class="sxs-lookup"><span data-stu-id="53a0c-102">IHostManualEvent::Reset Method</span></span>
<span data-ttu-id="53a0c-103">Сбрасывает текущий [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) экземпляра в сигнальное состояние.</span><span class="sxs-lookup"><span data-stu-id="53a0c-103">Resets the current [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance to a non-signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53a0c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="53a0c-104">Syntax</span></span>  
  
```  
HRESULT Reset ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="53a0c-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="53a0c-105">Return Value</span></span>  
  
|<span data-ttu-id="53a0c-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="53a0c-106">HRESULT</span></span>|<span data-ttu-id="53a0c-107">Описание</span><span class="sxs-lookup"><span data-stu-id="53a0c-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="53a0c-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="53a0c-108">S_OK</span></span>|`Reset` <span data-ttu-id="53a0c-109">успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="53a0c-109">returned successfully.</span></span>|  
|<span data-ttu-id="53a0c-110">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="53a0c-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="53a0c-111">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="53a0c-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="53a0c-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="53a0c-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="53a0c-113">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="53a0c-113">The call timed out.</span></span>|  
|<span data-ttu-id="53a0c-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="53a0c-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="53a0c-115">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="53a0c-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="53a0c-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="53a0c-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="53a0c-117">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="53a0c-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="53a0c-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="53a0c-118">E_FAIL</span></span>|<span data-ttu-id="53a0c-119">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="53a0c-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="53a0c-120">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="53a0c-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="53a0c-121">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="53a0c-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="53a0c-122">Требования</span><span class="sxs-lookup"><span data-stu-id="53a0c-122">Requirements</span></span>  
 <span data-ttu-id="53a0c-123">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53a0c-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53a0c-124">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="53a0c-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="53a0c-125">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="53a0c-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="53a0c-126">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="53a0c-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="53a0c-127">См. также</span><span class="sxs-lookup"><span data-stu-id="53a0c-127">See also</span></span>

- [<span data-ttu-id="53a0c-128">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="53a0c-128">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="53a0c-129">Интерфейс IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="53a0c-129">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="53a0c-130">Интерфейс IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="53a0c-130">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="53a0c-131">Интерфейс IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="53a0c-131">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="53a0c-132">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="53a0c-132">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)

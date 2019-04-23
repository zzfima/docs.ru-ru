---
title: Метод IHostAutoEvent::Set
ms.date: 03/30/2017
api_name:
- IHostAutoEvent.Set
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAutoEvent::Set
helpviewer_keywords:
- Set method, IHostAutoEvent interface [.NET Framework hosting]
- IHostAutoEvent::Set method [.NET Framework hosting]
ms.assetid: 46becf3e-bc0e-4338-85c0-9ab0df76a1d0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5af9f55bdcfe23f0b2a051b33cb1280f312820a7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59227019"
---
# <a name="ihostautoeventset-method"></a><span data-ttu-id="5f3ee-102">Метод IHostAutoEvent::Set</span><span class="sxs-lookup"><span data-stu-id="5f3ee-102">IHostAutoEvent::Set Method</span></span>
<span data-ttu-id="5f3ee-103">Задает текущий [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) экземпляр сигнальное состояние.</span><span class="sxs-lookup"><span data-stu-id="5f3ee-103">Sets the current [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance to a signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f3ee-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5f3ee-104">Syntax</span></span>  
  
```  
HRESULT Set ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="5f3ee-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5f3ee-105">Return Value</span></span>  
  
|<span data-ttu-id="5f3ee-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5f3ee-106">HRESULT</span></span>|<span data-ttu-id="5f3ee-107">Описание</span><span class="sxs-lookup"><span data-stu-id="5f3ee-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5f3ee-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="5f3ee-108">S_OK</span></span>|<span data-ttu-id="5f3ee-109">`Set` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="5f3ee-109">`Set` returned successfully.</span></span>|  
|<span data-ttu-id="5f3ee-110">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5f3ee-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5f3ee-111">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="5f3ee-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5f3ee-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5f3ee-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5f3ee-113">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="5f3ee-113">The call timed out.</span></span>|  
|<span data-ttu-id="5f3ee-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5f3ee-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5f3ee-115">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="5f3ee-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5f3ee-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5f3ee-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5f3ee-117">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="5f3ee-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5f3ee-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5f3ee-118">E_FAIL</span></span>|<span data-ttu-id="5f3ee-119">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="5f3ee-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5f3ee-120">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="5f3ee-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5f3ee-121">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5f3ee-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5f3ee-122">Требования</span><span class="sxs-lookup"><span data-stu-id="5f3ee-122">Requirements</span></span>  
 <span data-ttu-id="5f3ee-123">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f3ee-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f3ee-124">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5f3ee-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5f3ee-125">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5f3ee-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5f3ee-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f3ee-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f3ee-127">См. также</span><span class="sxs-lookup"><span data-stu-id="5f3ee-127">See also</span></span>

- [<span data-ttu-id="5f3ee-128">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="5f3ee-128">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="5f3ee-129">Интерфейс IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="5f3ee-129">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="5f3ee-130">Интерфейс IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="5f3ee-130">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="5f3ee-131">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="5f3ee-131">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)

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
ms.openlocfilehash: e443ec3f743d56f0fe7e4e1c794f16bab2db8314
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763961"
---
# <a name="ihostautoeventset-method"></a><span data-ttu-id="5d337-102">Метод IHostAutoEvent::Set</span><span class="sxs-lookup"><span data-stu-id="5d337-102">IHostAutoEvent::Set Method</span></span>
<span data-ttu-id="5d337-103">Задает текущий [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) экземпляр сигнальное состояние.</span><span class="sxs-lookup"><span data-stu-id="5d337-103">Sets the current [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance to a signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d337-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5d337-104">Syntax</span></span>  
  
```cpp  
HRESULT Set ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="5d337-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5d337-105">Return Value</span></span>  
  
|<span data-ttu-id="5d337-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5d337-106">HRESULT</span></span>|<span data-ttu-id="5d337-107">Описание</span><span class="sxs-lookup"><span data-stu-id="5d337-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5d337-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="5d337-108">S_OK</span></span>|<span data-ttu-id="5d337-109">`Set` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="5d337-109">`Set` returned successfully.</span></span>|  
|<span data-ttu-id="5d337-110">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5d337-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5d337-111">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="5d337-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5d337-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5d337-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5d337-113">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="5d337-113">The call timed out.</span></span>|  
|<span data-ttu-id="5d337-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5d337-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5d337-115">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="5d337-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5d337-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5d337-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5d337-117">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="5d337-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5d337-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5d337-118">E_FAIL</span></span>|<span data-ttu-id="5d337-119">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="5d337-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5d337-120">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="5d337-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5d337-121">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5d337-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5d337-122">Требования</span><span class="sxs-lookup"><span data-stu-id="5d337-122">Requirements</span></span>  
 <span data-ttu-id="5d337-123">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d337-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d337-124">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5d337-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5d337-125">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5d337-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5d337-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d337-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d337-127">См. также</span><span class="sxs-lookup"><span data-stu-id="5d337-127">See also</span></span>

- [<span data-ttu-id="5d337-128">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="5d337-128">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="5d337-129">Интерфейс IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="5d337-129">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="5d337-130">Интерфейс IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="5d337-130">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="5d337-131">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="5d337-131">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)

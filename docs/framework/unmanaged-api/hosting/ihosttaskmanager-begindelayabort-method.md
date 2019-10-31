---
title: Метод IHostTaskManager::BeginDelayAbort
ms.date: 03/30/2017
api_name:
- IHostTaskManager.BeginDelayAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::BeginDelayAbort
helpviewer_keywords:
- BeginDelayAbort method [.NET Framework hosting]
- IHostTaskManager::BeginDelayAbort method [.NET Framework hosting]
ms.assetid: 75f42a8b-ed68-4718-a030-a179cfba7d72
topic_type:
- apiref
ms.openlocfilehash: b765d5449cebbdec5f106a8e4743fee2f0ee5521
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133141"
---
# <a name="ihosttaskmanagerbegindelayabort-method"></a><span data-ttu-id="d47f6-102">Метод IHostTaskManager::BeginDelayAbort</span><span class="sxs-lookup"><span data-stu-id="d47f6-102">IHostTaskManager::BeginDelayAbort Method</span></span>
<span data-ttu-id="d47f6-103">Уведомляет узел о том, что управляемый код вводит точку, в которой не нужно прерывать текущую задачу.</span><span class="sxs-lookup"><span data-stu-id="d47f6-103">Notifies the host that managed code is entering a period in which the current task must not be aborted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d47f6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d47f6-104">Syntax</span></span>  
  
```cpp  
HRESULT BeginDelayAbort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="d47f6-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d47f6-105">Return Value</span></span>  
  
|<span data-ttu-id="d47f6-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d47f6-106">HRESULT</span></span>|<span data-ttu-id="d47f6-107">Описание</span><span class="sxs-lookup"><span data-stu-id="d47f6-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d47f6-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="d47f6-108">S_OK</span></span>|<span data-ttu-id="d47f6-109">`BeginDelayAbort` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="d47f6-109">`BeginDelayAbort` returned successfully.</span></span>|  
|<span data-ttu-id="d47f6-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d47f6-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d47f6-111">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="d47f6-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d47f6-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d47f6-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d47f6-113">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="d47f6-113">The call timed out.</span></span>|  
|<span data-ttu-id="d47f6-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d47f6-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d47f6-115">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="d47f6-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d47f6-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d47f6-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d47f6-117">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="d47f6-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d47f6-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d47f6-118">E_FAIL</span></span>|<span data-ttu-id="d47f6-119">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="d47f6-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d47f6-120">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="d47f6-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d47f6-121">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d47f6-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d47f6-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="d47f6-122">E_UNEXPECTED</span></span>|<span data-ttu-id="d47f6-123">`BeginDelayAbort` уже вызван, но соответствующий вызов [EndDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md) еще не получен.</span><span class="sxs-lookup"><span data-stu-id="d47f6-123">`BeginDelayAbort` has already been called, but the corresponding call to [EndDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md) has not yet been received.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d47f6-124">Заметки</span><span class="sxs-lookup"><span data-stu-id="d47f6-124">Remarks</span></span>  
 <span data-ttu-id="d47f6-125">Узел не должен прерывать текущую задачу до тех пор, пока не будет вызван `EndDelayAbort`.</span><span class="sxs-lookup"><span data-stu-id="d47f6-125">The host must not abort the current task until `EndDelayAbort` is called.</span></span> <span data-ttu-id="d47f6-126">Если другой вызов `BeginDelayAbort` выполняется без промежуточного вызова `EndDelayAbort`, узел должен вернуть E_UNEXPECTED из `BeginDelayAbort`и не должен предпринимать никаких действий.</span><span class="sxs-lookup"><span data-stu-id="d47f6-126">If another call to `BeginDelayAbort` is made without an intervening call to `EndDelayAbort`, the host should return E_UNEXPECTED from `BeginDelayAbort`, and should take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d47f6-127">Требования</span><span class="sxs-lookup"><span data-stu-id="d47f6-127">Requirements</span></span>  
 <span data-ttu-id="d47f6-128">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d47f6-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d47f6-129">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d47f6-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d47f6-130">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d47f6-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d47f6-131">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d47f6-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d47f6-132">См. также</span><span class="sxs-lookup"><span data-stu-id="d47f6-132">See also</span></span>

- [<span data-ttu-id="d47f6-133">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="d47f6-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="d47f6-134">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="d47f6-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="d47f6-135">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="d47f6-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

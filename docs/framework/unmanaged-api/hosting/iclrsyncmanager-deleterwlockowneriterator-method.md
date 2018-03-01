---
title: "Метод ICLRSyncManager::DeleteRWLockOwnerIterator"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRSyncManager.DeleteRWLockOwnerIterator
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager::DeleteRWLockOwnerIterator
helpviewer_keywords:
- ICLRSyncManager::DeleteRWLockOwnerIterator method [.NET Framework hosting]
- DeleteRWLockOwnerIterator method [.NET Framework hosting]
ms.assetid: fcfd340a-b7d6-44e4-8167-2c05b789d483
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: dce6699dc625c5c867befe1bc2e307cfaea7719a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iclrsyncmanagerdeleterwlockowneriterator-method"></a><span data-ttu-id="c80c4-102">Метод ICLRSyncManager::DeleteRWLockOwnerIterator</span><span class="sxs-lookup"><span data-stu-id="c80c4-102">ICLRSyncManager::DeleteRWLockOwnerIterator Method</span></span>
<span data-ttu-id="c80c4-103">Запросы, что общеязыковой среды выполнения (CLR) уничтожить итератор, который был создан с помощью вызова [ICLRSyncManager::CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span><span class="sxs-lookup"><span data-stu-id="c80c4-103">Requests that the common language runtime (CLR) destroy an iterator that was created by a call to [ICLRSyncManager::CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c80c4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c80c4-104">Syntax</span></span>  
  
```  
HRESULT DeleteRWLockOwnerIterator (  
    [in] SIZE_T  Iterator  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c80c4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c80c4-105">Parameters</span></span>  
 `Iterator`  
 <span data-ttu-id="c80c4-106">[in] Итератор, который был создан с помощью вызова `CreateRWLockOwnerIterator`.</span><span class="sxs-lookup"><span data-stu-id="c80c4-106">[in] The iterator that was created by using a call to `CreateRWLockOwnerIterator`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c80c4-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c80c4-107">Return Value</span></span>  
  
|<span data-ttu-id="c80c4-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c80c4-108">HRESULT</span></span>|<span data-ttu-id="c80c4-109">Описание</span><span class="sxs-lookup"><span data-stu-id="c80c4-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c80c4-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c80c4-110">S_OK</span></span>|<span data-ttu-id="c80c4-111">`DeleteRWLockOwnerIterator`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="c80c4-111">`DeleteRWLockOwnerIterator` returned successfully.</span></span>|  
|<span data-ttu-id="c80c4-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c80c4-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c80c4-113">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="c80c4-113">The CLR has not been loaded into a process, or is in a state in which it cannot run managed code or successfully process the call.</span></span>|  
|<span data-ttu-id="c80c4-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c80c4-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c80c4-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="c80c4-115">The call timed out.</span></span>|  
|<span data-ttu-id="c80c4-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c80c4-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c80c4-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="c80c4-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c80c4-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c80c4-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c80c4-119">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="c80c4-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c80c4-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c80c4-120">E_FAIL</span></span>|<span data-ttu-id="c80c4-121">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="c80c4-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c80c4-122">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="c80c4-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c80c4-123">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c80c4-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c80c4-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="c80c4-124">Remarks</span></span>  
 <span data-ttu-id="c80c4-125">Узел может вызвать этот метод и `CreateRWLockOwnerIterator` чтобы убедиться, что его реализация потоков остается синхронизированной.</span><span class="sxs-lookup"><span data-stu-id="c80c4-125">The host can call this method and `CreateRWLockOwnerIterator` to ensure that its threading implementation remains synchronized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c80c4-126">Требования</span><span class="sxs-lookup"><span data-stu-id="c80c4-126">Requirements</span></span>  
 <span data-ttu-id="c80c4-127">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c80c4-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c80c4-128">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c80c4-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c80c4-129">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c80c4-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c80c4-130">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c80c4-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c80c4-131">См. также</span><span class="sxs-lookup"><span data-stu-id="c80c4-131">See Also</span></span>  
 [<span data-ttu-id="c80c4-132">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="c80c4-132">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="c80c4-133">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="c80c4-133">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)

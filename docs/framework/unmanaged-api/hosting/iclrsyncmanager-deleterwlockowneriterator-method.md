---
title: Метод ICLRSyncManager::DeleteRWLockOwnerIterator
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 008e76b57ed0925eaae29cf7d2b451fc9ddd08a1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54730104"
---
# <a name="iclrsyncmanagerdeleterwlockowneriterator-method"></a><span data-ttu-id="663dd-102">Метод ICLRSyncManager::DeleteRWLockOwnerIterator</span><span class="sxs-lookup"><span data-stu-id="663dd-102">ICLRSyncManager::DeleteRWLockOwnerIterator Method</span></span>
<span data-ttu-id="663dd-103">Запрашивает, что общеязыковая среда выполнения (CLR) уничтожить итератор, который был создан с помощью вызова [ICLRSyncManager::CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span><span class="sxs-lookup"><span data-stu-id="663dd-103">Requests that the common language runtime (CLR) destroy an iterator that was created by a call to [ICLRSyncManager::CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="663dd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="663dd-104">Syntax</span></span>  
  
```  
HRESULT DeleteRWLockOwnerIterator (  
    [in] SIZE_T  Iterator  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="663dd-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="663dd-105">Parameters</span></span>  
 `Iterator`  
 <span data-ttu-id="663dd-106">[in] Итератор, который был создан с помощью вызова `CreateRWLockOwnerIterator`.</span><span class="sxs-lookup"><span data-stu-id="663dd-106">[in] The iterator that was created by using a call to `CreateRWLockOwnerIterator`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="663dd-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="663dd-107">Return Value</span></span>  
  
|<span data-ttu-id="663dd-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="663dd-108">HRESULT</span></span>|<span data-ttu-id="663dd-109">Описание</span><span class="sxs-lookup"><span data-stu-id="663dd-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="663dd-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="663dd-110">S_OK</span></span>|<span data-ttu-id="663dd-111">`DeleteRWLockOwnerIterator` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="663dd-111">`DeleteRWLockOwnerIterator` returned successfully.</span></span>|  
|<span data-ttu-id="663dd-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="663dd-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="663dd-113">Среда CLR не было загружено в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="663dd-113">The CLR has not been loaded into a process, or is in a state in which it cannot run managed code or successfully process the call.</span></span>|  
|<span data-ttu-id="663dd-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="663dd-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="663dd-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="663dd-115">The call timed out.</span></span>|  
|<span data-ttu-id="663dd-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="663dd-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="663dd-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="663dd-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="663dd-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="663dd-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="663dd-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="663dd-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="663dd-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="663dd-120">E_FAIL</span></span>|<span data-ttu-id="663dd-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="663dd-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="663dd-122">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="663dd-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="663dd-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="663dd-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="663dd-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="663dd-124">Remarks</span></span>  
 <span data-ttu-id="663dd-125">Узел может вызвать этот метод и `CreateRWLockOwnerIterator` чтобы убедиться, что его реализация потоков остается синхронизированной.</span><span class="sxs-lookup"><span data-stu-id="663dd-125">The host can call this method and `CreateRWLockOwnerIterator` to ensure that its threading implementation remains synchronized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="663dd-126">Требования</span><span class="sxs-lookup"><span data-stu-id="663dd-126">Requirements</span></span>  
 <span data-ttu-id="663dd-127">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="663dd-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="663dd-128">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="663dd-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="663dd-129">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="663dd-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="663dd-130">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="663dd-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="663dd-131">См. также</span><span class="sxs-lookup"><span data-stu-id="663dd-131">See also</span></span>
- [<span data-ttu-id="663dd-132">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="663dd-132">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="663dd-133">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="663dd-133">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)

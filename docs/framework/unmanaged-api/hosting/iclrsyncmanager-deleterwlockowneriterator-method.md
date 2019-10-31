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
ms.openlocfilehash: fb02b5c941e15d172140565e8efb625234947cd7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130576"
---
# <a name="iclrsyncmanagerdeleterwlockowneriterator-method"></a><span data-ttu-id="d5ee0-102">Метод ICLRSyncManager::DeleteRWLockOwnerIterator</span><span class="sxs-lookup"><span data-stu-id="d5ee0-102">ICLRSyncManager::DeleteRWLockOwnerIterator Method</span></span>
<span data-ttu-id="d5ee0-103">Запрашивает уничтожение итератора, созданного с помощью вызова метода [ICLRSyncManager:: CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md), в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="d5ee0-103">Requests that the common language runtime (CLR) destroy an iterator that was created by a call to [ICLRSyncManager::CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5ee0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d5ee0-104">Syntax</span></span>  
  
```cpp  
HRESULT DeleteRWLockOwnerIterator (  
    [in] SIZE_T  Iterator  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d5ee0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d5ee0-105">Parameters</span></span>  
 `Iterator`  
 <span data-ttu-id="d5ee0-106">окне Итератор, который был создан с помощью вызова метода `CreateRWLockOwnerIterator`.</span><span class="sxs-lookup"><span data-stu-id="d5ee0-106">[in] The iterator that was created by using a call to `CreateRWLockOwnerIterator`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d5ee0-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d5ee0-107">Return Value</span></span>  
  
|<span data-ttu-id="d5ee0-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d5ee0-108">HRESULT</span></span>|<span data-ttu-id="d5ee0-109">Описание</span><span class="sxs-lookup"><span data-stu-id="d5ee0-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d5ee0-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d5ee0-110">S_OK</span></span>|<span data-ttu-id="d5ee0-111">`DeleteRWLockOwnerIterator` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="d5ee0-111">`DeleteRWLockOwnerIterator` returned successfully.</span></span>|  
|<span data-ttu-id="d5ee0-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d5ee0-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d5ee0-113">Среда CLR не была загружена в процесс или находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="d5ee0-113">The CLR has not been loaded into a process, or is in a state in which it cannot run managed code or successfully process the call.</span></span>|  
|<span data-ttu-id="d5ee0-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d5ee0-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d5ee0-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="d5ee0-115">The call timed out.</span></span>|  
|<span data-ttu-id="d5ee0-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d5ee0-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d5ee0-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="d5ee0-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d5ee0-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d5ee0-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d5ee0-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="d5ee0-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d5ee0-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d5ee0-120">E_FAIL</span></span>|<span data-ttu-id="d5ee0-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="d5ee0-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d5ee0-122">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="d5ee0-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d5ee0-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d5ee0-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d5ee0-124">Заметки</span><span class="sxs-lookup"><span data-stu-id="d5ee0-124">Remarks</span></span>  
 <span data-ttu-id="d5ee0-125">Узел может вызвать этот метод и `CreateRWLockOwnerIterator`, чтобы убедиться в том, что его реализация потоков остается синхронизированной.</span><span class="sxs-lookup"><span data-stu-id="d5ee0-125">The host can call this method and `CreateRWLockOwnerIterator` to ensure that its threading implementation remains synchronized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5ee0-126">Требования</span><span class="sxs-lookup"><span data-stu-id="d5ee0-126">Requirements</span></span>  
 <span data-ttu-id="d5ee0-127">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5ee0-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5ee0-128">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d5ee0-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d5ee0-129">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d5ee0-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d5ee0-130">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5ee0-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5ee0-131">См. также</span><span class="sxs-lookup"><span data-stu-id="d5ee0-131">See also</span></span>

- [<span data-ttu-id="d5ee0-132">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="d5ee0-132">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="d5ee0-133">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="d5ee0-133">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)

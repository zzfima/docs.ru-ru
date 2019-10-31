---
title: Метод ICLRTask::LocksHeld
ms.date: 03/30/2017
api_name:
- ICLRTask.LocksHeld
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::LocksHeld
helpviewer_keywords:
- LocksHeld method [.NET Framework hosting]
- ICLRTask::LocksHeld method [.NET Framework hosting]
ms.assetid: e88a4dc3-02cc-4703-a474-292b71c40657
topic_type:
- apiref
ms.openlocfilehash: 3a3c42e2877957e3bbf5031e6ba650e4c9e0364e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73195950"
---
# <a name="iclrtasklocksheld-method"></a><span data-ttu-id="30850-102">Метод ICLRTask::LocksHeld</span><span class="sxs-lookup"><span data-stu-id="30850-102">ICLRTask::LocksHeld Method</span></span>
<span data-ttu-id="30850-103">Возвращает количество блокировок, которые в настоящее время удерживаются в задаче.</span><span class="sxs-lookup"><span data-stu-id="30850-103">Gets the number of locks currently held on the task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30850-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="30850-104">Syntax</span></span>  
  
```cpp  
HRESULT LocksHeld (  
    [out] SIZE_T *pLockCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="30850-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="30850-105">Parameters</span></span>  
 `pLockCount`  
 <span data-ttu-id="30850-106">заполняет Количество блокировок, удерживаемых для задачи во время вызова метода.</span><span class="sxs-lookup"><span data-stu-id="30850-106">[out] The number of locks held on the task at the time of the method call.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="30850-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="30850-107">Return Value</span></span>  
  
|<span data-ttu-id="30850-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="30850-108">HRESULT</span></span>|<span data-ttu-id="30850-109">Описание</span><span class="sxs-lookup"><span data-stu-id="30850-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="30850-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="30850-110">S_OK</span></span>|<span data-ttu-id="30850-111">`LocksHeld` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="30850-111">`LocksHeld` returned successfully.</span></span>|  
|<span data-ttu-id="30850-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="30850-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="30850-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="30850-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="30850-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="30850-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="30850-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="30850-115">The call timed out.</span></span>|  
|<span data-ttu-id="30850-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="30850-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="30850-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="30850-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="30850-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="30850-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="30850-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="30850-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="30850-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="30850-120">E_FAIL</span></span>|<span data-ttu-id="30850-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="30850-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="30850-122">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="30850-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="30850-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="30850-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="30850-124">Требования</span><span class="sxs-lookup"><span data-stu-id="30850-124">Requirements</span></span>  
 <span data-ttu-id="30850-125">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30850-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30850-126">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="30850-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="30850-127">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="30850-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="30850-128">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30850-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30850-129">См. также</span><span class="sxs-lookup"><span data-stu-id="30850-129">See also</span></span>

- [<span data-ttu-id="30850-130">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="30850-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="30850-131">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="30850-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="30850-132">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="30850-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="30850-133">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="30850-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

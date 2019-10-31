---
title: Метод IHostTaskManager::SetCLRTaskManager
ms.date: 03/30/2017
api_name:
- IHostTaskManager.SetCLRTaskManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::SetCLRTaskManager
helpviewer_keywords:
- IHostTaskManager::SetCLRTaskManager method [.NET Framework hosting]
- SetCLRTaskManager method [.NET Framework hosting]
ms.assetid: ec90ee83-bd4b-408b-9274-62a923ab86a1
topic_type:
- apiref
ms.openlocfilehash: c674cc43065bf8ea102bec1c5134757380454913
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141238"
---
# <a name="ihosttaskmanagersetclrtaskmanager-method"></a><span data-ttu-id="fb192-102">Метод IHostTaskManager::SetCLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="fb192-102">IHostTaskManager::SetCLRTaskManager Method</span></span>
<span data-ttu-id="fb192-103">Предоставляет узлу указатель интерфейса на экземпляр [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) , реализованный средой CLR.</span><span class="sxs-lookup"><span data-stu-id="fb192-103">Provides the host with an interface pointer to an [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) instance implemented by the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb192-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fb192-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRTaskManager (  
    [in] ICLRTaskManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fb192-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fb192-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="fb192-106">окне Указатель на экземпляр `ICLRTaskManager`, реализованный средой CLR.</span><span class="sxs-lookup"><span data-stu-id="fb192-106">[in] A pointer to an `ICLRTaskManager` instance implemented by the common language runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fb192-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fb192-107">Return Value</span></span>  
  
|<span data-ttu-id="fb192-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fb192-108">HRESULT</span></span>|<span data-ttu-id="fb192-109">Описание</span><span class="sxs-lookup"><span data-stu-id="fb192-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fb192-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="fb192-110">S_OK</span></span>|<span data-ttu-id="fb192-111">`SetCLRTaskManager` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="fb192-111">`SetCLRTaskManager` returned successfully.</span></span>|  
|<span data-ttu-id="fb192-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fb192-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fb192-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="fb192-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fb192-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fb192-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fb192-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="fb192-115">The call timed out.</span></span>|  
|<span data-ttu-id="fb192-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fb192-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fb192-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="fb192-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fb192-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fb192-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fb192-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="fb192-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fb192-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fb192-120">E_FAIL</span></span>|<span data-ttu-id="fb192-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="fb192-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fb192-122">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="fb192-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fb192-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="fb192-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fb192-124">Заметки</span><span class="sxs-lookup"><span data-stu-id="fb192-124">Remarks</span></span>  
 <span data-ttu-id="fb192-125">Среда выполнения вызывает `SetCLRTaskManager`, чтобы предоставить узлу указатель интерфейса на экземпляр `ICLRTaskManager`.</span><span class="sxs-lookup"><span data-stu-id="fb192-125">The runtime calls `SetCLRTaskManager` to provide the host with an interface pointer to an `ICLRTaskManager` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb192-126">Требования</span><span class="sxs-lookup"><span data-stu-id="fb192-126">Requirements</span></span>  
 <span data-ttu-id="fb192-127">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb192-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb192-128">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="fb192-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fb192-129">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="fb192-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fb192-130">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb192-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb192-131">См. также</span><span class="sxs-lookup"><span data-stu-id="fb192-131">See also</span></span>

- [<span data-ttu-id="fb192-132">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="fb192-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="fb192-133">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="fb192-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="fb192-134">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="fb192-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="fb192-135">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="fb192-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

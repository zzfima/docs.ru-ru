---
title: Метод IHostControl::GetHostManager
ms.date: 03/30/2017
api_name:
- IHostControl.GetHostManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostControl::GetHostManager
helpviewer_keywords:
- GetHostManager method [.NET Framework hosting]
- IHostControl::GetHostManager method [.NET Framework hosting]
ms.assetid: 0fa34bca-ed18-4626-9e78-d33684d18edb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cad7b319a20bce09779821af6f50aea086880c26
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59187353"
---
# <a name="ihostcontrolgethostmanager-method"></a><span data-ttu-id="c2441-102">Метод IHostControl::GetHostManager</span><span class="sxs-lookup"><span data-stu-id="c2441-102">IHostControl::GetHostManager Method</span></span>
<span data-ttu-id="c2441-103">Получает указатель интерфейса для реализации интерфейса с указанным `IID`.</span><span class="sxs-lookup"><span data-stu-id="c2441-103">Gets an interface pointer to the host's implementation of the interface with the specified `IID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2441-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c2441-104">Syntax</span></span>  
  
```  
HRESULT GetHostManager (  
    [in] REFIID riid,  
    [out, iid_is(riid)] void** ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2441-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c2441-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="c2441-106">[in] `IID` Интерфейса, запрашивая общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="c2441-106">[in] The `IID` of the interface that the common language runtime (CLR) is querying for.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="c2441-107">[out] Указатель на интерфейс, реализуемый основным приложением, или значение null, если узел не поддерживает этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="c2441-107">[out] A pointer to the host-implemented interface, or null if the host does not support this interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c2441-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c2441-108">Return Value</span></span>  
  
|<span data-ttu-id="c2441-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c2441-109">HRESULT</span></span>|<span data-ttu-id="c2441-110">Описание</span><span class="sxs-lookup"><span data-stu-id="c2441-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c2441-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="c2441-111">S_OK</span></span>|`GetHostManager` <span data-ttu-id="c2441-112">успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="c2441-112">returned successfully.</span></span>|  
|<span data-ttu-id="c2441-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c2441-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c2441-114">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="c2441-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c2441-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c2441-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c2441-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="c2441-116">The call timed out.</span></span>|  
|<span data-ttu-id="c2441-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c2441-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c2441-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="c2441-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c2441-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c2441-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c2441-120">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="c2441-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c2441-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c2441-121">E_FAIL</span></span>|<span data-ttu-id="c2441-122">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="c2441-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c2441-123">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="c2441-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c2441-124">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c2441-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c2441-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="c2441-125">E_INVALIDARG</span></span>|<span data-ttu-id="c2441-126">Запрошенный `IID` является недопустимым.</span><span class="sxs-lookup"><span data-stu-id="c2441-126">The requested `IID` is not valid.</span></span>|  
|<span data-ttu-id="c2441-127">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="c2441-127">E_NOINTERFACE</span></span>|<span data-ttu-id="c2441-128">Запрошенный интерфейс не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="c2441-128">The requested interface is not supported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2441-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="c2441-129">Remarks</span></span>  
 <span data-ttu-id="c2441-130">Среда CLR запрос на узел, чтобы определить, поддерживает ли один или несколько из следующих интерфейсов:</span><span class="sxs-lookup"><span data-stu-id="c2441-130">The CLR queries the host to determine whether it supports one or more of the following interfaces:</span></span>  
  
-   [<span data-ttu-id="c2441-131">IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="c2441-131">IHostMemoryManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
  
-   [<span data-ttu-id="c2441-132">IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="c2441-132">IHostTaskManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
  
-   [<span data-ttu-id="c2441-133">IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="c2441-133">IHostThreadPoolManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)  
  
-   [<span data-ttu-id="c2441-134">IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="c2441-134">IHostIoCompletionManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
  
-   [<span data-ttu-id="c2441-135">IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="c2441-135">IHostSyncManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
  
-   [<span data-ttu-id="c2441-136">IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="c2441-136">IHostAssemblyManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
  
-   [<span data-ttu-id="c2441-137">IHostGCManager</span><span class="sxs-lookup"><span data-stu-id="c2441-137">IHostGCManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)  
  
-   [<span data-ttu-id="c2441-138">IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="c2441-138">IHostPolicyManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
  
-   [<span data-ttu-id="c2441-139">IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="c2441-139">IHostSecurityManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
  
 <span data-ttu-id="c2441-140">Если узел поддерживает указанный интерфейс, он задает `ppObject` к его реализации этого интерфейса.</span><span class="sxs-lookup"><span data-stu-id="c2441-140">If the host supports the specified interface, it sets `ppObject` to its implementation of that interface.</span></span> <span data-ttu-id="c2441-141">В противном случае он устанавливает `ppObject` значение null.</span><span class="sxs-lookup"><span data-stu-id="c2441-141">Otherwise, it sets `ppObject` to null.</span></span>  
  
 <span data-ttu-id="c2441-142">Среда CLR не вызывает `Release` на диспетчеры узлов, даже в том случае, если вы завершаете работу.</span><span class="sxs-lookup"><span data-stu-id="c2441-142">The CLR does not call `Release` on host managers, even when you shut it down.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2441-143">Требования</span><span class="sxs-lookup"><span data-stu-id="c2441-143">Requirements</span></span>  
 <span data-ttu-id="c2441-144">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2441-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2441-145">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c2441-145">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c2441-146">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c2441-146">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="c2441-147">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="c2441-147">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c2441-148">См. также</span><span class="sxs-lookup"><span data-stu-id="c2441-148">See also</span></span>

- [<span data-ttu-id="c2441-149">Интерфейс IHostControl</span><span class="sxs-lookup"><span data-stu-id="c2441-149">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)

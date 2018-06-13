---
title: Метод IHostSecurityManager::SetSecurityContext
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.SetSecurityContext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::SetSecurityContext
helpviewer_keywords:
- SetSecurityContext method [.NET Framework hosting]
- IHostSecurityManager::SetSecurityContext method [.NET Framework hosting]
ms.assetid: e4372384-ee69-48d7-97e0-8fab7866597a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e07edd75e80db2c275821a64bef5213da60ee853
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442086"
---
# <a name="ihostsecuritymanagersetsecuritycontext-method"></a><span data-ttu-id="a2b05-102">Метод IHostSecurityManager::SetSecurityContext</span><span class="sxs-lookup"><span data-stu-id="a2b05-102">IHostSecurityManager::SetSecurityContext Method</span></span>
<span data-ttu-id="a2b05-103">Задает контекст безопасности текущего потока.</span><span class="sxs-lookup"><span data-stu-id="a2b05-103">Sets the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2b05-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a2b05-104">Syntax</span></span>  
  
```  
HRESULT SetSecurityContext (  
    [in]  EContextType eContextType,  
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a2b05-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a2b05-105">Parameters</span></span>  
 `eContextType`  
 <span data-ttu-id="a2b05-106">[in] Один из [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) значений, указывающее, какой тип контекста общеязыковой среды выполнения (CLR) размещение на узле.</span><span class="sxs-lookup"><span data-stu-id="a2b05-106">[in] One of the [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) values, indicating what type of context the common language runtime (CLR) is placing on the host.</span></span>  
  
 `ppSecurityContext`  
 <span data-ttu-id="a2b05-107">[out] Указатель на новый адрес [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) объекта.</span><span class="sxs-lookup"><span data-stu-id="a2b05-107">[out] A pointer to the address of a new [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a2b05-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a2b05-108">Return Value</span></span>  
  
|<span data-ttu-id="a2b05-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a2b05-109">HRESULT</span></span>|<span data-ttu-id="a2b05-110">Описание</span><span class="sxs-lookup"><span data-stu-id="a2b05-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a2b05-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="a2b05-111">S_OK</span></span>|<span data-ttu-id="a2b05-112">`SetSecurityContext` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="a2b05-112">`SetSecurityContext` returned successfully.</span></span>|  
|<span data-ttu-id="a2b05-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a2b05-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a2b05-114">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="a2b05-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a2b05-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a2b05-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a2b05-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="a2b05-116">The call timed out.</span></span>|  
|<span data-ttu-id="a2b05-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a2b05-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a2b05-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="a2b05-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a2b05-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a2b05-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a2b05-120">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="a2b05-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a2b05-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a2b05-121">E_FAIL</span></span>|<span data-ttu-id="a2b05-122">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="a2b05-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a2b05-123">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="a2b05-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a2b05-124">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a2b05-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a2b05-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="a2b05-125">Remarks</span></span>  
 <span data-ttu-id="a2b05-126">Среда CLR вызывает `SetSecurityContext` в различных сценариях.</span><span class="sxs-lookup"><span data-stu-id="a2b05-126">The CLR calls `SetSecurityContext` in several scenarios.</span></span> <span data-ttu-id="a2b05-127">Перед запуском класс и модуль конструкторы и методы завершения, среда CLR вызывает `SetSecurityContext` для защиты от сбоев при выполнении узла.</span><span class="sxs-lookup"><span data-stu-id="a2b05-127">Before it executes class and module constructors and finalizers, the CLR calls `SetSecurityContext` to protect the host from execution failures.</span></span> <span data-ttu-id="a2b05-128">Она затем выполняет Сброс контекста безопасности в исходное состояние после выполнения конструктора или метода завершения, с помощью другого вызова `SetSecurityContext`.</span><span class="sxs-lookup"><span data-stu-id="a2b05-128">It then resets the security context to its original state after execution of the constructor or finalizer, by using another call to `SetSecurityContext`.</span></span> <span data-ttu-id="a2b05-129">То же самое происходит с завершения ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="a2b05-129">A similar pattern occurs with I/O completion.</span></span> <span data-ttu-id="a2b05-130">Если на узле реализован [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md), среда CLR вызывает `SetSecurityContext` после узел вызывает метод [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md).</span><span class="sxs-lookup"><span data-stu-id="a2b05-130">If the host implements [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md), the CLR calls `SetSecurityContext` after the host calls [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md).</span></span>  
  
 <span data-ttu-id="a2b05-131">В точках асинхронные рабочие потоки, среда CLR вызывает `SetSecurityContext` в <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> или в [IHostThreadPoolManager::QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md)в зависимости от того, является ли узел или среда CLR реализует пула потоков.</span><span class="sxs-lookup"><span data-stu-id="a2b05-131">At asynchronous points in worker threads, the CLR calls `SetSecurityContext` within <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> or within [IHostThreadPoolManager::QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md), depending on whether the host or the CLR is implementing the thread pool.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2b05-132">Требования</span><span class="sxs-lookup"><span data-stu-id="a2b05-132">Requirements</span></span>  
 <span data-ttu-id="a2b05-133">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2b05-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2b05-134">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a2b05-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a2b05-135">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a2b05-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a2b05-136">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2b05-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2b05-137">См. также</span><span class="sxs-lookup"><span data-stu-id="a2b05-137">See Also</span></span>  
 <xref:System.Threading.ThreadPool?displayProperty=nameWithType>  
 [<span data-ttu-id="a2b05-138">Перечисление EContextType</span><span class="sxs-lookup"><span data-stu-id="a2b05-138">EContextType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)  
 [<span data-ttu-id="a2b05-139">Интерфейс ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="a2b05-139">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="a2b05-140">Интерфейс IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="a2b05-140">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
 [<span data-ttu-id="a2b05-141">Интерфейс IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="a2b05-141">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [<span data-ttu-id="a2b05-142">Интерфейс IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="a2b05-142">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 [<span data-ttu-id="a2b05-143">Интерфейс IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="a2b05-143">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)

---
title: "Метод IHostSecurityManager::SetSecurityContext"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSecurityManager.SetSecurityContext
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSecurityManager::SetSecurityContext
helpviewer_keywords:
- SetSecurityContext method [.NET Framework hosting]
- IHostSecurityManager::SetSecurityContext method [.NET Framework hosting]
ms.assetid: e4372384-ee69-48d7-97e0-8fab7866597a
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c25b8bb0effb4e5e1e61447c74c9729989d04702
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsecuritymanagersetsecuritycontext-method"></a><span data-ttu-id="33123-102">Метод IHostSecurityManager::SetSecurityContext</span><span class="sxs-lookup"><span data-stu-id="33123-102">IHostSecurityManager::SetSecurityContext Method</span></span>
<span data-ttu-id="33123-103">Задает контекст безопасности текущего потока.</span><span class="sxs-lookup"><span data-stu-id="33123-103">Sets the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33123-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="33123-104">Syntax</span></span>  
  
```  
HRESULT SetSecurityContext (  
    [in]  EContextType eContextType,  
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="33123-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="33123-105">Parameters</span></span>  
 `eContextType`  
 <span data-ttu-id="33123-106">[in] Один из [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) значений, указывающее, какой тип контекста общеязыковой среды выполнения (CLR) размещение на узле.</span><span class="sxs-lookup"><span data-stu-id="33123-106">[in] One of the [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) values, indicating what type of context the common language runtime (CLR) is placing on the host.</span></span>  
  
 `ppSecurityContext`  
 <span data-ttu-id="33123-107">[out] Указатель на новый адрес [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) объекта.</span><span class="sxs-lookup"><span data-stu-id="33123-107">[out] A pointer to the address of a new [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="33123-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="33123-108">Return Value</span></span>  
  
|<span data-ttu-id="33123-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="33123-109">HRESULT</span></span>|<span data-ttu-id="33123-110">Описание</span><span class="sxs-lookup"><span data-stu-id="33123-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="33123-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="33123-111">S_OK</span></span>|<span data-ttu-id="33123-112">`SetSecurityContext`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="33123-112">`SetSecurityContext` returned successfully.</span></span>|  
|<span data-ttu-id="33123-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="33123-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="33123-114">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="33123-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="33123-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="33123-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="33123-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="33123-116">The call timed out.</span></span>|  
|<span data-ttu-id="33123-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="33123-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="33123-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="33123-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="33123-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="33123-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="33123-120">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="33123-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="33123-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="33123-121">E_FAIL</span></span>|<span data-ttu-id="33123-122">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="33123-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="33123-123">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="33123-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="33123-124">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="33123-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33123-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="33123-125">Remarks</span></span>  
 <span data-ttu-id="33123-126">Среда CLR вызывает `SetSecurityContext` в различных сценариях.</span><span class="sxs-lookup"><span data-stu-id="33123-126">The CLR calls `SetSecurityContext` in several scenarios.</span></span> <span data-ttu-id="33123-127">Перед запуском класс и модуль конструкторы и методы завершения, среда CLR вызывает `SetSecurityContext` для защиты от сбоев при выполнении узла.</span><span class="sxs-lookup"><span data-stu-id="33123-127">Before it executes class and module constructors and finalizers, the CLR calls `SetSecurityContext` to protect the host from execution failures.</span></span> <span data-ttu-id="33123-128">Она затем выполняет Сброс контекста безопасности в исходное состояние после выполнения конструктора или метода завершения, с помощью другого вызова `SetSecurityContext`.</span><span class="sxs-lookup"><span data-stu-id="33123-128">It then resets the security context to its original state after execution of the constructor or finalizer, by using another call to `SetSecurityContext`.</span></span> <span data-ttu-id="33123-129">То же самое происходит с завершения ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="33123-129">A similar pattern occurs with I/O completion.</span></span> <span data-ttu-id="33123-130">Если на узле реализован [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md), среда CLR вызывает `SetSecurityContext` после узел вызывает метод [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md).</span><span class="sxs-lookup"><span data-stu-id="33123-130">If the host implements [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md), the CLR calls `SetSecurityContext` after the host calls [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md).</span></span>  
  
 <span data-ttu-id="33123-131">В точках асинхронные рабочие потоки, среда CLR вызывает `SetSecurityContext` в <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> или в [IHostThreadPoolManager::QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md)в зависимости от того, является ли узел или среда CLR реализует пула потоков.</span><span class="sxs-lookup"><span data-stu-id="33123-131">At asynchronous points in worker threads, the CLR calls `SetSecurityContext` within <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> or within [IHostThreadPoolManager::QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md), depending on whether the host or the CLR is implementing the thread pool.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33123-132">Требования</span><span class="sxs-lookup"><span data-stu-id="33123-132">Requirements</span></span>  
 <span data-ttu-id="33123-133">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33123-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33123-134">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="33123-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="33123-135">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="33123-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="33123-136">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33123-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33123-137">См. также</span><span class="sxs-lookup"><span data-stu-id="33123-137">See Also</span></span>  
 <xref:System.Threading.ThreadPool?displayProperty=nameWithType>  
 [<span data-ttu-id="33123-138">Econtexttype-перечисление</span><span class="sxs-lookup"><span data-stu-id="33123-138">EContextType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)  
 [<span data-ttu-id="33123-139">ICLRIoCompletionManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="33123-139">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="33123-140">IHostIoCompletionManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="33123-140">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
 [<span data-ttu-id="33123-141">IHostSecurityContext-интерфейс</span><span class="sxs-lookup"><span data-stu-id="33123-141">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [<span data-ttu-id="33123-142">IHostSecurityManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="33123-142">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 [<span data-ttu-id="33123-143">IHostThreadPoolManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="33123-143">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)

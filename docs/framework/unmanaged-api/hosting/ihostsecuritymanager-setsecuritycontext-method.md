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
ms.workload: dotnet
ms.openlocfilehash: 29a7652e20c08b9de584a9e11ac343ad92f40653
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsecuritymanagersetsecuritycontext-method"></a><span data-ttu-id="ac2a3-102">Метод IHostSecurityManager::SetSecurityContext</span><span class="sxs-lookup"><span data-stu-id="ac2a3-102">IHostSecurityManager::SetSecurityContext Method</span></span>
<span data-ttu-id="ac2a3-103">Задает контекст безопасности текущего потока.</span><span class="sxs-lookup"><span data-stu-id="ac2a3-103">Sets the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac2a3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ac2a3-104">Syntax</span></span>  
  
```  
HRESULT SetSecurityContext (  
    [in]  EContextType eContextType,  
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ac2a3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ac2a3-105">Parameters</span></span>  
 `eContextType`  
 <span data-ttu-id="ac2a3-106">[in] Один из [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) значений, указывающее, какой тип контекста общеязыковой среды выполнения (CLR) размещение на узле.</span><span class="sxs-lookup"><span data-stu-id="ac2a3-106">[in] One of the [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) values, indicating what type of context the common language runtime (CLR) is placing on the host.</span></span>  
  
 `ppSecurityContext`  
 <span data-ttu-id="ac2a3-107">[out] Указатель на новый адрес [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) объекта.</span><span class="sxs-lookup"><span data-stu-id="ac2a3-107">[out] A pointer to the address of a new [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ac2a3-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ac2a3-108">Return Value</span></span>  
  
|<span data-ttu-id="ac2a3-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ac2a3-109">HRESULT</span></span>|<span data-ttu-id="ac2a3-110">Описание</span><span class="sxs-lookup"><span data-stu-id="ac2a3-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ac2a3-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="ac2a3-111">S_OK</span></span>|<span data-ttu-id="ac2a3-112">`SetSecurityContext`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="ac2a3-112">`SetSecurityContext` returned successfully.</span></span>|  
|<span data-ttu-id="ac2a3-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ac2a3-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ac2a3-114">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="ac2a3-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ac2a3-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ac2a3-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ac2a3-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="ac2a3-116">The call timed out.</span></span>|  
|<span data-ttu-id="ac2a3-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ac2a3-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ac2a3-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="ac2a3-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ac2a3-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ac2a3-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ac2a3-120">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="ac2a3-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ac2a3-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ac2a3-121">E_FAIL</span></span>|<span data-ttu-id="ac2a3-122">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="ac2a3-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ac2a3-123">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="ac2a3-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ac2a3-124">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ac2a3-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac2a3-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="ac2a3-125">Remarks</span></span>  
 <span data-ttu-id="ac2a3-126">Среда CLR вызывает `SetSecurityContext` в различных сценариях.</span><span class="sxs-lookup"><span data-stu-id="ac2a3-126">The CLR calls `SetSecurityContext` in several scenarios.</span></span> <span data-ttu-id="ac2a3-127">Перед запуском класс и модуль конструкторы и методы завершения, среда CLR вызывает `SetSecurityContext` для защиты от сбоев при выполнении узла.</span><span class="sxs-lookup"><span data-stu-id="ac2a3-127">Before it executes class and module constructors and finalizers, the CLR calls `SetSecurityContext` to protect the host from execution failures.</span></span> <span data-ttu-id="ac2a3-128">Она затем выполняет Сброс контекста безопасности в исходное состояние после выполнения конструктора или метода завершения, с помощью другого вызова `SetSecurityContext`.</span><span class="sxs-lookup"><span data-stu-id="ac2a3-128">It then resets the security context to its original state after execution of the constructor or finalizer, by using another call to `SetSecurityContext`.</span></span> <span data-ttu-id="ac2a3-129">То же самое происходит с завершения ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="ac2a3-129">A similar pattern occurs with I/O completion.</span></span> <span data-ttu-id="ac2a3-130">Если на узле реализован [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md), среда CLR вызывает `SetSecurityContext` после узел вызывает метод [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md).</span><span class="sxs-lookup"><span data-stu-id="ac2a3-130">If the host implements [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md), the CLR calls `SetSecurityContext` after the host calls [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md).</span></span>  
  
 <span data-ttu-id="ac2a3-131">В точках асинхронные рабочие потоки, среда CLR вызывает `SetSecurityContext` в <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> или в [IHostThreadPoolManager::QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md)в зависимости от того, является ли узел или среда CLR реализует пула потоков.</span><span class="sxs-lookup"><span data-stu-id="ac2a3-131">At asynchronous points in worker threads, the CLR calls `SetSecurityContext` within <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> or within [IHostThreadPoolManager::QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md), depending on whether the host or the CLR is implementing the thread pool.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac2a3-132">Требования</span><span class="sxs-lookup"><span data-stu-id="ac2a3-132">Requirements</span></span>  
 <span data-ttu-id="ac2a3-133">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac2a3-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac2a3-134">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ac2a3-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ac2a3-135">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ac2a3-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ac2a3-136">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac2a3-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac2a3-137">См. также</span><span class="sxs-lookup"><span data-stu-id="ac2a3-137">See Also</span></span>  
 <xref:System.Threading.ThreadPool?displayProperty=nameWithType>  
 [<span data-ttu-id="ac2a3-138">Перечисление EContextType</span><span class="sxs-lookup"><span data-stu-id="ac2a3-138">EContextType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)  
 [<span data-ttu-id="ac2a3-139">Интерфейс ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="ac2a3-139">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="ac2a3-140">Интерфейс IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="ac2a3-140">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
 [<span data-ttu-id="ac2a3-141">Интерфейс IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="ac2a3-141">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [<span data-ttu-id="ac2a3-142">Интерфейс IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="ac2a3-142">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 [<span data-ttu-id="ac2a3-143">Интерфейс IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="ac2a3-143">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)

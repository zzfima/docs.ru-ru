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
ms.openlocfilehash: 676a1d50202333203c13fcf916dbb14a6d91fb8f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121442"
---
# <a name="ihostsecuritymanagersetsecuritycontext-method"></a><span data-ttu-id="b2811-102">Метод IHostSecurityManager::SetSecurityContext</span><span class="sxs-lookup"><span data-stu-id="b2811-102">IHostSecurityManager::SetSecurityContext Method</span></span>
<span data-ttu-id="b2811-103">Задает контекст безопасности выполняемого в данный момент потока.</span><span class="sxs-lookup"><span data-stu-id="b2811-103">Sets the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2811-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b2811-104">Syntax</span></span>  
  
```cpp  
HRESULT SetSecurityContext (  
    [in]  EContextType eContextType,  
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2811-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b2811-105">Parameters</span></span>  
 `eContextType`  
 <span data-ttu-id="b2811-106">окне Одно из значений [еконтексттипе](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) , указывающее, какой тип контекста используется средой CLR для размещения на узле.</span><span class="sxs-lookup"><span data-stu-id="b2811-106">[in] One of the [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) values, indicating what type of context the common language runtime (CLR) is placing on the host.</span></span>  
  
 `ppSecurityContext`  
 <span data-ttu-id="b2811-107">заполняет Указатель на адрес нового объекта [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="b2811-107">[out] A pointer to the address of a new [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b2811-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b2811-108">Return Value</span></span>  
  
|<span data-ttu-id="b2811-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b2811-109">HRESULT</span></span>|<span data-ttu-id="b2811-110">Описание</span><span class="sxs-lookup"><span data-stu-id="b2811-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b2811-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="b2811-111">S_OK</span></span>|<span data-ttu-id="b2811-112">`SetSecurityContext` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="b2811-112">`SetSecurityContext` returned successfully.</span></span>|  
|<span data-ttu-id="b2811-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b2811-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b2811-114">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="b2811-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b2811-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b2811-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b2811-116">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="b2811-116">The call timed out.</span></span>|  
|<span data-ttu-id="b2811-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b2811-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b2811-118">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="b2811-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b2811-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b2811-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b2811-120">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="b2811-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b2811-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b2811-121">E_FAIL</span></span>|<span data-ttu-id="b2811-122">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="b2811-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b2811-123">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="b2811-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b2811-124">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b2811-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b2811-125">Заметки</span><span class="sxs-lookup"><span data-stu-id="b2811-125">Remarks</span></span>  
 <span data-ttu-id="b2811-126">Среда CLR вызывает `SetSecurityContext` в нескольких сценариях.</span><span class="sxs-lookup"><span data-stu-id="b2811-126">The CLR calls `SetSecurityContext` in several scenarios.</span></span> <span data-ttu-id="b2811-127">Перед выполнением конструкторов классов и модулей и методов завершения среда CLR вызывает `SetSecurityContext` для защиты узла от сбоев при выполнении.</span><span class="sxs-lookup"><span data-stu-id="b2811-127">Before it executes class and module constructors and finalizers, the CLR calls `SetSecurityContext` to protect the host from execution failures.</span></span> <span data-ttu-id="b2811-128">Затем он сбрасывает контекст безопасности до исходного состояния после выполнения конструктора или метода завершения, используя другой вызов `SetSecurityContext`.</span><span class="sxs-lookup"><span data-stu-id="b2811-128">It then resets the security context to its original state after execution of the constructor or finalizer, by using another call to `SetSecurityContext`.</span></span> <span data-ttu-id="b2811-129">Аналогичный шаблон происходит при завершении ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="b2811-129">A similar pattern occurs with I/O completion.</span></span> <span data-ttu-id="b2811-130">Если узел реализует [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md), среда CLR вызывает `SetSecurityContext` после того, как узел вызывает [ICLRIoCompletionManager:: OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md).</span><span class="sxs-lookup"><span data-stu-id="b2811-130">If the host implements [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md), the CLR calls `SetSecurityContext` after the host calls [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md).</span></span>  
  
 <span data-ttu-id="b2811-131">В асинхронных точках рабочих потоков среда CLR вызывает `SetSecurityContext` в <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> или в пределах [IHostThreadPoolManager:: QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md)в зависимости от того, реализует ли узел или CLR пул потоков.</span><span class="sxs-lookup"><span data-stu-id="b2811-131">At asynchronous points in worker threads, the CLR calls `SetSecurityContext` within <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> or within [IHostThreadPoolManager::QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md), depending on whether the host or the CLR is implementing the thread pool.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2811-132">Требования</span><span class="sxs-lookup"><span data-stu-id="b2811-132">Requirements</span></span>  
 <span data-ttu-id="b2811-133">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2811-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2811-134">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="b2811-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b2811-135">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b2811-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b2811-136">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2811-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2811-137">См. также</span><span class="sxs-lookup"><span data-stu-id="b2811-137">See also</span></span>

- <xref:System.Threading.ThreadPool?displayProperty=nameWithType>
- [<span data-ttu-id="b2811-138">Перечисление EContextType</span><span class="sxs-lookup"><span data-stu-id="b2811-138">EContextType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)
- [<span data-ttu-id="b2811-139">Интерфейс ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="b2811-139">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="b2811-140">Интерфейс IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="b2811-140">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="b2811-141">Интерфейс IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="b2811-141">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="b2811-142">Интерфейс IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="b2811-142">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="b2811-143">Интерфейс IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="b2811-143">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)

---
title: Метод IHostTask::Alert
ms.date: 03/30/2017
api_name:
- IHostTask.Alert
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::Alert
helpviewer_keywords:
- IHostTask::Alert method [.NET Framework hosting]
- Alert method, IHostTask interface [.NET Framework hosting]
ms.assetid: 5245d4b5-b6c3-48df-9cb9-8caf059f43fb
topic_type:
- apiref
ms.openlocfilehash: b2fc1d6c45eb72410ccfa1071064aa1a31ae46e6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121405"
---
# <a name="ihosttaskalert-method"></a><span data-ttu-id="2a69e-102">Метод IHostTask::Alert</span><span class="sxs-lookup"><span data-stu-id="2a69e-102">IHostTask::Alert Method</span></span>
<span data-ttu-id="2a69e-103">Запрашивает выход узла из задачи, представленной текущим экземпляром [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) , поэтому задачу можно прервать.</span><span class="sxs-lookup"><span data-stu-id="2a69e-103">Requests that the host wake the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance, so the task can be aborted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a69e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2a69e-104">Syntax</span></span>  
  
```cpp  
HRESULT Alert ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="2a69e-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2a69e-105">Return Value</span></span>  
  
|<span data-ttu-id="2a69e-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2a69e-106">HRESULT</span></span>|<span data-ttu-id="2a69e-107">Описание</span><span class="sxs-lookup"><span data-stu-id="2a69e-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2a69e-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="2a69e-108">S_OK</span></span>|<span data-ttu-id="2a69e-109">Метод успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="2a69e-109">The method returned successfully.</span></span>|  
|<span data-ttu-id="2a69e-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2a69e-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2a69e-111">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="2a69e-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2a69e-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2a69e-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2a69e-113">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="2a69e-113">The call timed out.</span></span>|  
|<span data-ttu-id="2a69e-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2a69e-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2a69e-115">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="2a69e-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2a69e-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2a69e-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2a69e-117">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="2a69e-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2a69e-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2a69e-118">E_FAIL</span></span>|<span data-ttu-id="2a69e-119">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="2a69e-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2a69e-120">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="2a69e-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2a69e-121">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2a69e-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2a69e-122">Заметки</span><span class="sxs-lookup"><span data-stu-id="2a69e-122">Remarks</span></span>  
 <span data-ttu-id="2a69e-123">Среда CLR вызывает метод `Alert` при вызове <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> из пользовательского кода или при завершении работы <xref:System.AppDomain>, связанного с текущим <xref:System.Threading.Thread>.</span><span class="sxs-lookup"><span data-stu-id="2a69e-123">The CLR calls the `Alert` method when <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> is called from user code, or when the <xref:System.AppDomain> associated with the current <xref:System.Threading.Thread> shuts down.</span></span> <span data-ttu-id="2a69e-124">Узел должен возвращаться немедленно, так как вызов выполняется асинхронно.</span><span class="sxs-lookup"><span data-stu-id="2a69e-124">The host must return immediately, because the call is made asynchronously.</span></span> <span data-ttu-id="2a69e-125">Если узел не может немедленно предупредить задачу, он должен пробудиться при следующем входе в состояние, в котором она может быть оповещена.</span><span class="sxs-lookup"><span data-stu-id="2a69e-125">If the host cannot alert the task immediately, it must wake up the next time it enters a state in which it can be alerted.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2a69e-126">`Alert` влияет только на те задачи, к которым среда выполнения передала значение [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) WAIT_ALERTABLE для таких методов, как [Join](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md).</span><span class="sxs-lookup"><span data-stu-id="2a69e-126">`Alert` affects only those tasks to which the runtime has passed a [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) value of WAIT_ALERTABLE to methods such as [Join](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a69e-127">Требования</span><span class="sxs-lookup"><span data-stu-id="2a69e-127">Requirements</span></span>  
 <span data-ttu-id="2a69e-128">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a69e-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a69e-129">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="2a69e-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2a69e-130">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2a69e-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2a69e-131">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a69e-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a69e-132">См. также</span><span class="sxs-lookup"><span data-stu-id="2a69e-132">See also</span></span>

- [<span data-ttu-id="2a69e-133">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="2a69e-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="2a69e-134">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="2a69e-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="2a69e-135">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="2a69e-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="2a69e-136">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="2a69e-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

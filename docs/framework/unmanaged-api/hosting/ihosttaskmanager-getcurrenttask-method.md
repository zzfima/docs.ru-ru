---
title: Метод IHostTaskManager::GetCurrentTask
ms.date: 03/30/2017
api_name:
- IHostTaskManager.GetCurrentTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::GetCurrentTask
helpviewer_keywords:
- GetCurrentTask method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::GetCurrentTask method [.NET Framework hosting]
ms.assetid: f17bca49-90bd-4dee-a5e1-b9a57ea46f85
topic_type:
- apiref
ms.openlocfilehash: d1d6ddfe7834a1c6f22b9195042d32363d6ea6cc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133039"
---
# <a name="ihosttaskmanagergetcurrenttask-method"></a><span data-ttu-id="a962d-102">Метод IHostTaskManager::GetCurrentTask</span><span class="sxs-lookup"><span data-stu-id="a962d-102">IHostTaskManager::GetCurrentTask Method</span></span>
<span data-ttu-id="a962d-103">Возвращает указатель интерфейса на задачу, которая выполняется в данный момент в потоке операционной системы, из которого выполняется этот вызов.</span><span class="sxs-lookup"><span data-stu-id="a962d-103">Gets an interface pointer to the task that is currently executing on the operating system thread from which this call is made.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a962d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a962d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentTask (  
    [out] IHostTask **pTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a962d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a962d-105">Parameters</span></span>  
 `pTask`  
 <span data-ttu-id="a962d-106">заполняет Указатель на адрес экземпляра [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) , представляющий выполняемую в данный момент задачу, или значение null, если ни одна из задач в данный момент не выполняется.</span><span class="sxs-lookup"><span data-stu-id="a962d-106">[out] A pointer to the address of an [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that represents the currently executing task, or null, if no task is currently executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a962d-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a962d-107">Return Value</span></span>  
  
|<span data-ttu-id="a962d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a962d-108">HRESULT</span></span>|<span data-ttu-id="a962d-109">Описание</span><span class="sxs-lookup"><span data-stu-id="a962d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a962d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a962d-110">S_OK</span></span>|<span data-ttu-id="a962d-111">`GetCurrentTask` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="a962d-111">`GetCurrentTask` returned successfully.</span></span>|  
|<span data-ttu-id="a962d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a962d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a962d-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="a962d-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a962d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a962d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a962d-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="a962d-115">The call timed out.</span></span>|  
|<span data-ttu-id="a962d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a962d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a962d-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="a962d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a962d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a962d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a962d-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="a962d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a962d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a962d-120">E_FAIL</span></span>|<span data-ttu-id="a962d-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="a962d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a962d-122">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="a962d-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a962d-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a962d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a962d-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="a962d-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="a962d-125">`GetCurrentTask` был вызван в потоке операционной системы за пределами элемента управления узла.</span><span class="sxs-lookup"><span data-stu-id="a962d-125">`GetCurrentTask` was called on an operating system thread outside the control of the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a962d-126">Заметки</span><span class="sxs-lookup"><span data-stu-id="a962d-126">Remarks</span></span>  
 <span data-ttu-id="a962d-127">Узел может также присвоить параметру `pTask` значение null, чтобы предотвратить невозможность запуска задачи из-за входа в среду CLR.</span><span class="sxs-lookup"><span data-stu-id="a962d-127">The host can also set the `pTask` parameter to null to prevent a task that it did not initiate from entering the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a962d-128">Требования</span><span class="sxs-lookup"><span data-stu-id="a962d-128">Requirements</span></span>  
 <span data-ttu-id="a962d-129">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a962d-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a962d-130">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a962d-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a962d-131">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a962d-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a962d-132">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a962d-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a962d-133">См. также</span><span class="sxs-lookup"><span data-stu-id="a962d-133">See also</span></span>

- [<span data-ttu-id="a962d-134">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="a962d-134">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="a962d-135">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="a962d-135">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="a962d-136">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="a962d-136">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="a962d-137">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="a962d-137">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

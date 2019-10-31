---
title: Метод IHostTask::GetPriority
ms.date: 03/30/2017
api_name:
- IHostTask.GetPriority
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::GetPriority
helpviewer_keywords:
- GetPriority method [.NET Framework hosting]
- IHostTask::GetPriority method [.NET Framework hosting]
ms.assetid: 4b463cd6-77c1-4f9a-8518-346ad8fc4b70
topic_type:
- apiref
ms.openlocfilehash: 6c33fa6d2e6cb09f013c5334461e61235db549f7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121421"
---
# <a name="ihosttaskgetpriority-method"></a><span data-ttu-id="2db0d-102">Метод IHostTask::GetPriority</span><span class="sxs-lookup"><span data-stu-id="2db0d-102">IHostTask::GetPriority Method</span></span>
<span data-ttu-id="2db0d-103">Возвращает уровень приоритета потока задачи, представленной текущим экземпляром [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="2db0d-103">Gets the thread priority level of the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2db0d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2db0d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPriority (  
    [out] int *pPriority  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2db0d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2db0d-105">Parameters</span></span>  
 `pPriority`  
 <span data-ttu-id="2db0d-106">заполняет Указатель на целое число, указывающее уровень приоритета потока задачи, представленной текущим экземпляром `IHostTask`.</span><span class="sxs-lookup"><span data-stu-id="2db0d-106">[out] A pointer to an integer that indicates the thread priority level of the task represented by the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2db0d-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2db0d-107">Return Value</span></span>  
  
|<span data-ttu-id="2db0d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2db0d-108">HRESULT</span></span>|<span data-ttu-id="2db0d-109">Описание</span><span class="sxs-lookup"><span data-stu-id="2db0d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2db0d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2db0d-110">S_OK</span></span>|<span data-ttu-id="2db0d-111">`GetPriority` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="2db0d-111">`GetPriority` returned successfully.</span></span>|  
|<span data-ttu-id="2db0d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2db0d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2db0d-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="2db0d-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2db0d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2db0d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2db0d-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="2db0d-115">The call timed out.</span></span>|  
|<span data-ttu-id="2db0d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2db0d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2db0d-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="2db0d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2db0d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2db0d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2db0d-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="2db0d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2db0d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2db0d-120">E_FAIL</span></span>|<span data-ttu-id="2db0d-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="2db0d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2db0d-122">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="2db0d-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2db0d-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2db0d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2db0d-124">Заметки</span><span class="sxs-lookup"><span data-stu-id="2db0d-124">Remarks</span></span>  
 <span data-ttu-id="2db0d-125">Значения уровня приоритета потока определяются функцией Win32 `SetThreadPriority`.</span><span class="sxs-lookup"><span data-stu-id="2db0d-125">Thread priority level values are defined by the Win32 `SetThreadPriority` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2db0d-126">Требования</span><span class="sxs-lookup"><span data-stu-id="2db0d-126">Requirements</span></span>  
 <span data-ttu-id="2db0d-127">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2db0d-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2db0d-128">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="2db0d-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2db0d-129">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2db0d-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2db0d-130">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2db0d-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2db0d-131">См. также</span><span class="sxs-lookup"><span data-stu-id="2db0d-131">See also</span></span>

- [<span data-ttu-id="2db0d-132">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="2db0d-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="2db0d-133">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="2db0d-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="2db0d-134">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="2db0d-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="2db0d-135">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="2db0d-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

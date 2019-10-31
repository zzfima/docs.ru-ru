---
title: Метод IHostTaskManager::Sleep
ms.date: 03/30/2017
api_name:
- IHostTaskManager.Sleep
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::Sleep
helpviewer_keywords:
- IHostTaskManager::Sleep method [.NET Framework hosting]
- Sleep method, IHostTaskManager interface [.NET Framework hosting]
ms.assetid: f67d25f3-9199-4c5f-b1e8-1c819243cfd5
topic_type:
- apiref
ms.openlocfilehash: 7eedf052b6f2285799940b394d9891975230cb72
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132929"
---
# <a name="ihosttaskmanagersleep-method"></a><span data-ttu-id="2b930-102">Метод IHostTaskManager::Sleep</span><span class="sxs-lookup"><span data-stu-id="2b930-102">IHostTaskManager::Sleep Method</span></span>
<span data-ttu-id="2b930-103">Уведомляет узел о том, что текущая задача переходит в спящий режим.</span><span class="sxs-lookup"><span data-stu-id="2b930-103">Notifies the host that the current task is going to sleep.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b930-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2b930-104">Syntax</span></span>  
  
```cpp  
HRESULT Sleep (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b930-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2b930-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="2b930-106">окне Интервал времени в миллисекундах, в течение которого поток будет в спящем режиме.</span><span class="sxs-lookup"><span data-stu-id="2b930-106">[in] The time interval, in milliseconds, that the thread will sleep.</span></span>  
  
 `option`  
 <span data-ttu-id="2b930-107">окне Одно из значений перечисления [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) , указывающее, какое действие должно предпринять узел при блокировке этого действия.</span><span class="sxs-lookup"><span data-stu-id="2b930-107">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) enumeration values, indicating what action the host should take if this action blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2b930-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2b930-108">Return Value</span></span>  
  
|<span data-ttu-id="2b930-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2b930-109">HRESULT</span></span>|<span data-ttu-id="2b930-110">Описание</span><span class="sxs-lookup"><span data-stu-id="2b930-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2b930-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="2b930-111">S_OK</span></span>|<span data-ttu-id="2b930-112">`Sleep` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="2b930-112">`Sleep` returned successfully.</span></span>|  
|<span data-ttu-id="2b930-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2b930-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2b930-114">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="2b930-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2b930-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2b930-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2b930-116">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="2b930-116">The call timed out.</span></span>|  
|<span data-ttu-id="2b930-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2b930-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2b930-118">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="2b930-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2b930-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2b930-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2b930-120">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="2b930-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2b930-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2b930-121">E_FAIL</span></span>|<span data-ttu-id="2b930-122">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="2b930-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2b930-123">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="2b930-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2b930-124">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2b930-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2b930-125">Заметки</span><span class="sxs-lookup"><span data-stu-id="2b930-125">Remarks</span></span>  
 <span data-ttu-id="2b930-126">Среда CLR обычно вызывает `IHostTaskManager::Sleep` при вызове <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> из пользовательского кода.</span><span class="sxs-lookup"><span data-stu-id="2b930-126">The CLR typically calls `IHostTaskManager::Sleep` when <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> is called from user code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b930-127">Требования</span><span class="sxs-lookup"><span data-stu-id="2b930-127">Requirements</span></span>  
 <span data-ttu-id="2b930-128">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b930-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b930-129">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="2b930-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2b930-130">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2b930-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2b930-131">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b930-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b930-132">См. также</span><span class="sxs-lookup"><span data-stu-id="2b930-132">See also</span></span>

- [<span data-ttu-id="2b930-133">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="2b930-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="2b930-134">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="2b930-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="2b930-135">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="2b930-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="2b930-136">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="2b930-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

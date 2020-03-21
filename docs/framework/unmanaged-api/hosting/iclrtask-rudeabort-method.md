---
title: Метод ICLRTask::RudeAbort
ms.date: 03/30/2017
api_name:
- ICLRTask.RudeAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::RudeAbort
helpviewer_keywords:
- RudeAbort method, ICLRTask interface [.NET Framework hosting]
- ICLRTask::RudeAbort method [.NET Framework hosting]
ms.assetid: b5785468-fcd7-4cc3-8a5d-8796337b53fc
topic_type:
- apiref
ms.openlocfilehash: aacf9de36dc39b63ed36b672e31f40704413d608
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176335"
---
# <a name="iclrtaskrudeabort-method"></a><span data-ttu-id="85e3d-102">Метод ICLRTask::RudeAbort</span><span class="sxs-lookup"><span data-stu-id="85e3d-102">ICLRTask::RudeAbort Method</span></span>
<span data-ttu-id="85e3d-103">Поручает общему времени выполнения языка (CLR) немедленно и безоговорочно прервать задачу, представленную текущим экземпляром [Интерфейса ICLRTask.](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)</span><span class="sxs-lookup"><span data-stu-id="85e3d-103">Instructs the common language runtime (CLR) to abort the task represented by the current [ICLRTask Interface](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance immediately and unconditionally.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85e3d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="85e3d-104">Syntax</span></span>  
  
```cpp  
HRESULT RudeAbort ();
```  
  
## <a name="return-value"></a><span data-ttu-id="85e3d-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="85e3d-105">Return Value</span></span>  
  
|<span data-ttu-id="85e3d-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="85e3d-106">HRESULT</span></span>|<span data-ttu-id="85e3d-107">Описание</span><span class="sxs-lookup"><span data-stu-id="85e3d-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="85e3d-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="85e3d-108">S_OK</span></span>|<span data-ttu-id="85e3d-109">`RudeAbort`вернулся успешно.</span><span class="sxs-lookup"><span data-stu-id="85e3d-109">`RudeAbort` returned successfully.</span></span>|  
|<span data-ttu-id="85e3d-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="85e3d-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="85e3d-111">CLR не был загружен в процесс, или CLR находится в состоянии, в котором он не может запустить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="85e3d-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="85e3d-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="85e3d-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="85e3d-113">Вызов приурочен.</span><span class="sxs-lookup"><span data-stu-id="85e3d-113">The call timed out.</span></span>|  
|<span data-ttu-id="85e3d-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="85e3d-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="85e3d-115">Звонящее не владеет замком.</span><span class="sxs-lookup"><span data-stu-id="85e3d-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="85e3d-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="85e3d-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="85e3d-117">Событие было отменено в то время как заблокированный поток или волокно ждало на нем.</span><span class="sxs-lookup"><span data-stu-id="85e3d-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="85e3d-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="85e3d-118">E_FAIL</span></span>|<span data-ttu-id="85e3d-119">Произошел неизвестный катастрофический сбой.</span><span class="sxs-lookup"><span data-stu-id="85e3d-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="85e3d-120">Когда метод возвращается E_FAIL, CLR больше не используется в процессе.</span><span class="sxs-lookup"><span data-stu-id="85e3d-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="85e3d-121">Последующие вызовы к методам хостинга возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="85e3d-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="85e3d-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="85e3d-122">Remarks</span></span>  
 <span data-ttu-id="85e3d-123">Хост `RudeAbort` призывает немедленно прервать задачу.</span><span class="sxs-lookup"><span data-stu-id="85e3d-123">A host calls `RudeAbort` to abort a task immediately.</span></span> <span data-ttu-id="85e3d-124">Окончательные процедуры обработки и обработки исключений не гарантируются выполнением.</span><span class="sxs-lookup"><span data-stu-id="85e3d-124">Finalizers and exception handling routines are not guaranteed to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85e3d-125">Требования</span><span class="sxs-lookup"><span data-stu-id="85e3d-125">Requirements</span></span>  
 <span data-ttu-id="85e3d-126">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85e3d-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85e3d-127">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="85e3d-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="85e3d-128">**Библиотека:** Включено в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="85e3d-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="85e3d-129">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85e3d-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85e3d-130">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="85e3d-130">See also</span></span>

- [<span data-ttu-id="85e3d-131">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="85e3d-131">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="85e3d-132">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="85e3d-132">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="85e3d-133">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="85e3d-133">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="85e3d-134">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="85e3d-134">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

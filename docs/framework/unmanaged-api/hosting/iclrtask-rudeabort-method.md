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
ms.openlocfilehash: 69e3ecfc82985d52bd5b14e9faf2566e395b622b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124659"
---
# <a name="iclrtaskrudeabort-method"></a><span data-ttu-id="ef6cd-102">Метод ICLRTask::RudeAbort</span><span class="sxs-lookup"><span data-stu-id="ef6cd-102">ICLRTask::RudeAbort Method</span></span>
<span data-ttu-id="ef6cd-103">Инструктирует среду CLR, чтобы немедленно и безусловно прерывать выполнение задачи, представленной текущим экземпляром [интерфейса ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="ef6cd-103">Instructs the common language runtime (CLR) to abort the task represented by the current [ICLRTask Interface](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance immediately and unconditionally.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef6cd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ef6cd-104">Syntax</span></span>  
  
```cpp  
HRESULT RudeAbort ();   
```  
  
## <a name="return-value"></a><span data-ttu-id="ef6cd-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ef6cd-105">Return Value</span></span>  
  
|<span data-ttu-id="ef6cd-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ef6cd-106">HRESULT</span></span>|<span data-ttu-id="ef6cd-107">Описание</span><span class="sxs-lookup"><span data-stu-id="ef6cd-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ef6cd-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="ef6cd-108">S_OK</span></span>|<span data-ttu-id="ef6cd-109">`RudeAbort` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="ef6cd-109">`RudeAbort` returned successfully.</span></span>|  
|<span data-ttu-id="ef6cd-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ef6cd-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ef6cd-111">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="ef6cd-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ef6cd-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ef6cd-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ef6cd-113">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="ef6cd-113">The call timed out.</span></span>|  
|<span data-ttu-id="ef6cd-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ef6cd-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ef6cd-115">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="ef6cd-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ef6cd-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ef6cd-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ef6cd-117">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="ef6cd-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ef6cd-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ef6cd-118">E_FAIL</span></span>|<span data-ttu-id="ef6cd-119">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="ef6cd-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ef6cd-120">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="ef6cd-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ef6cd-121">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ef6cd-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ef6cd-122">Заметки</span><span class="sxs-lookup"><span data-stu-id="ef6cd-122">Remarks</span></span>  
 <span data-ttu-id="ef6cd-123">Узел вызывает `RudeAbort` для немедленного прерывания задачи.</span><span class="sxs-lookup"><span data-stu-id="ef6cd-123">A host calls `RudeAbort` to abort a task immediately.</span></span> <span data-ttu-id="ef6cd-124">Выполнение методов завершения и подпрограмм обработки исключений не гарантируется.</span><span class="sxs-lookup"><span data-stu-id="ef6cd-124">Finalizers and exception handling routines are not guaranteed to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef6cd-125">Требования</span><span class="sxs-lookup"><span data-stu-id="ef6cd-125">Requirements</span></span>  
 <span data-ttu-id="ef6cd-126">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef6cd-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef6cd-127">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ef6cd-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ef6cd-128">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ef6cd-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ef6cd-129">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef6cd-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef6cd-130">См. также</span><span class="sxs-lookup"><span data-stu-id="ef6cd-130">See also</span></span>

- [<span data-ttu-id="ef6cd-131">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="ef6cd-131">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="ef6cd-132">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="ef6cd-132">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="ef6cd-133">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="ef6cd-133">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="ef6cd-134">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="ef6cd-134">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

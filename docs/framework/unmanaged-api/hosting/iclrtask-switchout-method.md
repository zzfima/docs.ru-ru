---
title: Метод ICLRTask::SwitchOut
ms.date: 03/30/2017
api_name:
- ICLRTask.SwitchOut
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::SwitchOut
helpviewer_keywords:
- ICLRTask::SwitchOut method [.NET Framework hosting]
- SwitchOut method [.NET Framework hosting]
ms.assetid: b6fb168c-b24b-4ecf-a390-2b5ba3317ae6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5b0a4450b6cfa98d0c939c148229d48d0b1d4c7c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54556578"
---
# <a name="iclrtaskswitchout-method"></a><span data-ttu-id="267a0-102">Метод ICLRTask::SwitchOut</span><span class="sxs-lookup"><span data-stu-id="267a0-102">ICLRTask::SwitchOut Method</span></span>
<span data-ttu-id="267a0-103">Уведомляет среду (CLR), задача, представленная текущим [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) экземпляр больше не находится в рабочем состоянии.</span><span class="sxs-lookup"><span data-stu-id="267a0-103">Notifies the common language runtime (CLR) that the task represented by the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance is no longer in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="267a0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="267a0-104">Syntax</span></span>  
  
```  
HRESULT SwitchOut ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="267a0-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="267a0-105">Return Value</span></span>  
  
|<span data-ttu-id="267a0-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="267a0-106">HRESULT</span></span>|<span data-ttu-id="267a0-107">Описание</span><span class="sxs-lookup"><span data-stu-id="267a0-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="267a0-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="267a0-108">S_OK</span></span>|<span data-ttu-id="267a0-109">`SwitchOut` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="267a0-109">`SwitchOut` returned successfully.</span></span>|  
|<span data-ttu-id="267a0-110">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="267a0-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="267a0-111">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="267a0-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="267a0-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="267a0-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="267a0-113">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="267a0-113">The call timed out.</span></span>|  
|<span data-ttu-id="267a0-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="267a0-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="267a0-115">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="267a0-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="267a0-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="267a0-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="267a0-117">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="267a0-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="267a0-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="267a0-118">E_FAIL</span></span>|<span data-ttu-id="267a0-119">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="267a0-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="267a0-120">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="267a0-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="267a0-121">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="267a0-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="267a0-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="267a0-122">Remarks</span></span>  
 <span data-ttu-id="267a0-123">Узел вызывает `SwitchOut` сообщать среде CLR, что временно остановил выполнение задачи, текущий `ICLRTask` представленное экземпляром и перенесет задачи.</span><span class="sxs-lookup"><span data-stu-id="267a0-123">A host calls `SwitchOut` to inform the CLR that it has temporarily stopped executing the task that the current `ICLRTask` instance represents, and will reschedule the task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="267a0-124">Требования</span><span class="sxs-lookup"><span data-stu-id="267a0-124">Requirements</span></span>  
 <span data-ttu-id="267a0-125">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="267a0-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="267a0-126">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="267a0-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="267a0-127">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="267a0-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="267a0-128">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="267a0-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="267a0-129">См. также</span><span class="sxs-lookup"><span data-stu-id="267a0-129">See also</span></span>
- [<span data-ttu-id="267a0-130">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="267a0-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="267a0-131">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="267a0-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="267a0-132">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="267a0-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="267a0-133">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="267a0-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

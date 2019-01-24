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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7b1c5132be72cfd9f70d3a81297425109f636195
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54623768"
---
# <a name="ihosttaskalert-method"></a><span data-ttu-id="0686b-102">Метод IHostTask::Alert</span><span class="sxs-lookup"><span data-stu-id="0686b-102">IHostTask::Alert Method</span></span>
<span data-ttu-id="0686b-103">Запросы, что узел пробуждения задач, представленный текущим [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) экземпляра, поэтому задача может быть прервана.</span><span class="sxs-lookup"><span data-stu-id="0686b-103">Requests that the host wake the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance, so the task can be aborted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0686b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0686b-104">Syntax</span></span>  
  
```  
HRESULT Alert ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="0686b-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0686b-105">Return Value</span></span>  
  
|<span data-ttu-id="0686b-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0686b-106">HRESULT</span></span>|<span data-ttu-id="0686b-107">Описание</span><span class="sxs-lookup"><span data-stu-id="0686b-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0686b-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="0686b-108">S_OK</span></span>|<span data-ttu-id="0686b-109">Метод возвратился успешно.</span><span class="sxs-lookup"><span data-stu-id="0686b-109">The method returned successfully.</span></span>|  
|<span data-ttu-id="0686b-110">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0686b-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0686b-111">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="0686b-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0686b-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0686b-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0686b-113">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="0686b-113">The call timed out.</span></span>|  
|<span data-ttu-id="0686b-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0686b-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0686b-115">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="0686b-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0686b-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0686b-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0686b-117">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="0686b-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0686b-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0686b-118">E_FAIL</span></span>|<span data-ttu-id="0686b-119">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="0686b-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0686b-120">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="0686b-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0686b-121">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0686b-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0686b-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="0686b-122">Remarks</span></span>  
 <span data-ttu-id="0686b-123">Среда CLR вызывает `Alert` метод при <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> вызывается из пользовательского кода, или когда <xref:System.AppDomain> связанный с текущим <xref:System.Threading.Thread> завершает работу.</span><span class="sxs-lookup"><span data-stu-id="0686b-123">The CLR calls the `Alert` method when <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> is called from user code, or when the <xref:System.AppDomain> associated with the current <xref:System.Threading.Thread> shuts down.</span></span> <span data-ttu-id="0686b-124">Узел должен возвращаться немедленно, так как вызов выполняется асинхронно.</span><span class="sxs-lookup"><span data-stu-id="0686b-124">The host must return immediately, because the call is made asynchronously.</span></span> <span data-ttu-id="0686b-125">Если узел не может немедленно предупредить об этой задаче, он пробуждения следующий раз, он переходит в состояние, в котором его можно получать оповещения.</span><span class="sxs-lookup"><span data-stu-id="0686b-125">If the host cannot alert the task immediately, it must wake up the next time it enters a state in which it can be alerted.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0686b-126">`Alert` затрагивает только те задачи, к которым среда выполнения достиг [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) значение WAIT_ALERTABLE для методов, таких как [Join](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md).</span><span class="sxs-lookup"><span data-stu-id="0686b-126">`Alert` affects only those tasks to which the runtime has passed a [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) value of WAIT_ALERTABLE to methods such as [Join](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0686b-127">Требования</span><span class="sxs-lookup"><span data-stu-id="0686b-127">Requirements</span></span>  
 <span data-ttu-id="0686b-128">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0686b-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0686b-129">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0686b-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0686b-130">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0686b-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0686b-131">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0686b-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0686b-132">См. также</span><span class="sxs-lookup"><span data-stu-id="0686b-132">See also</span></span>
- [<span data-ttu-id="0686b-133">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="0686b-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="0686b-134">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="0686b-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="0686b-135">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="0686b-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="0686b-136">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="0686b-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

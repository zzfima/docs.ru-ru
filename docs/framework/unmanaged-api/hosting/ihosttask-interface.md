---
title: Интерфейс IHostTask
ms.date: 03/30/2017
api_name:
- IHostTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask
helpviewer_keywords:
- IHostTask interface [.NET Framework hosting]
ms.assetid: a71dbbd5-64b8-47eb-9f03-8e8c85fbe2bc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d862c02e96487049fb88f80665d32caf6939ed1e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54555949"
---
# <a name="ihosttask-interface"></a><span data-ttu-id="e89c5-102">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="e89c5-102">IHostTask Interface</span></span>
<span data-ttu-id="e89c5-103">Предоставляет методы, позволяющие общеязыковой среды выполнения (CLR) для взаимодействия с узлом для управления задачами.</span><span class="sxs-lookup"><span data-stu-id="e89c5-103">Provides methods that allow the common language runtime (CLR) to communicate with the host to manage tasks.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e89c5-104">Методы</span><span class="sxs-lookup"><span data-stu-id="e89c5-104">Methods</span></span>  
  
|<span data-ttu-id="e89c5-105">Метод</span><span class="sxs-lookup"><span data-stu-id="e89c5-105">Method</span></span>|<span data-ttu-id="e89c5-106">Описание</span><span class="sxs-lookup"><span data-stu-id="e89c5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e89c5-107">Метод Alert</span><span class="sxs-lookup"><span data-stu-id="e89c5-107">Alert Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md)|<span data-ttu-id="e89c5-108">Запросы, что узел пробуждения задач, представленный текущим `IHostTask` экземпляра, поэтому задача может быть прервана.</span><span class="sxs-lookup"><span data-stu-id="e89c5-108">Requests that the host wake the task represented by the current `IHostTask` instance, so the task can be aborted.</span></span>|  
|[<span data-ttu-id="e89c5-109">Метод GetPriority</span><span class="sxs-lookup"><span data-stu-id="e89c5-109">GetPriority Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)|<span data-ttu-id="e89c5-110">Возвращает уровень приоритета потока задачи, представленный текущим `IHostTask` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="e89c5-110">Gets the thread priority level of the task represented by the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="e89c5-111">Метод Join</span><span class="sxs-lookup"><span data-stu-id="e89c5-111">Join Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md)|<span data-ttu-id="e89c5-112">Блокирует вызывающий задачу до выполнения задачи, представленный текущим `IHostTask` завершения экземпляра, по истечении указанного интервала времени, или [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) вызывается.</span><span class="sxs-lookup"><span data-stu-id="e89c5-112">Blocks the calling task until the task represented by the current `IHostTask` instance completes, the specified time interval elapses, or [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) is called.</span></span>|  
|[<span data-ttu-id="e89c5-113">Метод SetCLRTask</span><span class="sxs-lookup"><span data-stu-id="e89c5-113">SetCLRTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md)|<span data-ttu-id="e89c5-114">Связывает [интерфейс ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) экземпляра с текущим `IHostTask` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="e89c5-114">Associates an [ICLRTask Interface](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance with the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="e89c5-115">Метод SetPriority</span><span class="sxs-lookup"><span data-stu-id="e89c5-115">SetPriority Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setpriority-method.md)|<span data-ttu-id="e89c5-116">Уровень запросов, настройки, узел приоритет потока для задачи, представленный текущим `IHostTask` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="e89c5-116">Requests that the host adjust the thread priority level for the task represented by the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="e89c5-117">Метод Start</span><span class="sxs-lookup"><span data-stu-id="e89c5-117">Start Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md)|<span data-ttu-id="e89c5-118">Запросы, что узел перемещения задач, представленный текущим `IHostTask` экземпляр из приостановленного состояния к активному состоянию, в котором можно выполнять код.</span><span class="sxs-lookup"><span data-stu-id="e89c5-118">Requests that the host move the task represented by the current `IHostTask` instance from a suspended state to a live state, in which code can be executed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e89c5-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="e89c5-119">Remarks</span></span>  
 <span data-ttu-id="e89c5-120">Среда CLR вызывает методы, определенные `IHostTask` запустить задачу, задать его приоритет потока, уровень, и т. д.</span><span class="sxs-lookup"><span data-stu-id="e89c5-120">The CLR calls methods defined by `IHostTask` to start a task, set its thread priority level, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e89c5-121">Требования</span><span class="sxs-lookup"><span data-stu-id="e89c5-121">Requirements</span></span>  
 <span data-ttu-id="e89c5-122">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e89c5-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e89c5-123">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e89c5-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e89c5-124">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e89c5-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e89c5-125">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e89c5-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e89c5-126">См. также</span><span class="sxs-lookup"><span data-stu-id="e89c5-126">See also</span></span>
- [<span data-ttu-id="e89c5-127">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="e89c5-127">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="e89c5-128">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="e89c5-128">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="e89c5-129">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="e89c5-129">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="e89c5-130">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="e89c5-130">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)

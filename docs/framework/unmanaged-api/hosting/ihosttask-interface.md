---
title: "Интерфейс IHostTask"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: bbffe2a171c112d4e9650b2c1b2a9ce1f010f382
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ihosttask-interface"></a><span data-ttu-id="5441c-102">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="5441c-102">IHostTask Interface</span></span>
<span data-ttu-id="5441c-103">Предоставляет методы, позволяющие общеязыковой среды выполнения (CLR) для взаимодействия с основным приложением для управления задачами.</span><span class="sxs-lookup"><span data-stu-id="5441c-103">Provides methods that allow the common language runtime (CLR) to communicate with the host to manage tasks.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5441c-104">Методы</span><span class="sxs-lookup"><span data-stu-id="5441c-104">Methods</span></span>  
  
|<span data-ttu-id="5441c-105">Метод</span><span class="sxs-lookup"><span data-stu-id="5441c-105">Method</span></span>|<span data-ttu-id="5441c-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="5441c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5441c-107">Метод Alert</span><span class="sxs-lookup"><span data-stu-id="5441c-107">Alert Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md)|<span data-ttu-id="5441c-108">Запросы, что узел пробуждения задач, представленный текущим `IHostTask` экземпляра, поэтому задача может быть прервана.</span><span class="sxs-lookup"><span data-stu-id="5441c-108">Requests that the host wake the task represented by the current `IHostTask` instance, so the task can be aborted.</span></span>|  
|[<span data-ttu-id="5441c-109">Метод GetPriority</span><span class="sxs-lookup"><span data-stu-id="5441c-109">GetPriority Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)|<span data-ttu-id="5441c-110">Возвращает уровень приоритета потока задачи, представленный текущим `IHostTask` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="5441c-110">Gets the thread priority level of the task represented by the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="5441c-111">Метод Join</span><span class="sxs-lookup"><span data-stu-id="5441c-111">Join Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md)|<span data-ttu-id="5441c-112">Блокирует вызывающий задачу до выполнения задачи, представленный текущим `IHostTask` завершения экземпляра, истечения заданного интервала, или [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) вызывается.</span><span class="sxs-lookup"><span data-stu-id="5441c-112">Blocks the calling task until the task represented by the current `IHostTask` instance completes, the specified time interval elapses, or [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) is called.</span></span>|  
|[<span data-ttu-id="5441c-113">Метод SetCLRTask</span><span class="sxs-lookup"><span data-stu-id="5441c-113">SetCLRTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md)|<span data-ttu-id="5441c-114">Связывает [ICLRTask-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) экземпляра с текущим `IHostTask` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="5441c-114">Associates an [ICLRTask Interface](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance with the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="5441c-115">Метод SetPriority</span><span class="sxs-lookup"><span data-stu-id="5441c-115">SetPriority Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setpriority-method.md)|<span data-ttu-id="5441c-116">Уровень запросов, настройки, узле приоритет потока для задачи, представленный текущим `IHostTask` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="5441c-116">Requests that the host adjust the thread priority level for the task represented by the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="5441c-117">Метод Start</span><span class="sxs-lookup"><span data-stu-id="5441c-117">Start Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md)|<span data-ttu-id="5441c-118">Запросы, что узел перемещения задач, представленный текущим `IHostTask` экземпляр из приостановленного состояния к активному состоянию, в котором можно выполнять код.</span><span class="sxs-lookup"><span data-stu-id="5441c-118">Requests that the host move the task represented by the current `IHostTask` instance from a suspended state to a live state, in which code can be executed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5441c-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="5441c-119">Remarks</span></span>  
 <span data-ttu-id="5441c-120">Среда CLR вызывает методы, определенные `IHostTask` запустить задачу, установите его приоритет потока уровень, и т. д.</span><span class="sxs-lookup"><span data-stu-id="5441c-120">The CLR calls methods defined by `IHostTask` to start a task, set its thread priority level, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5441c-121">Требования</span><span class="sxs-lookup"><span data-stu-id="5441c-121">Requirements</span></span>  
 <span data-ttu-id="5441c-122">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5441c-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5441c-123">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5441c-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5441c-124">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5441c-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5441c-125">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5441c-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5441c-126">См. также</span><span class="sxs-lookup"><span data-stu-id="5441c-126">See Also</span></span>  
 [<span data-ttu-id="5441c-127">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="5441c-127">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="5441c-128">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="5441c-128">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="5441c-129">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="5441c-129">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="5441c-130">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="5441c-130">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)

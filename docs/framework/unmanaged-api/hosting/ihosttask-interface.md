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
ms.openlocfilehash: df1fb24c4003f77523ef01a4029fd19cc55a3fef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ihosttask-interface"></a><span data-ttu-id="4b721-102">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="4b721-102">IHostTask Interface</span></span>
<span data-ttu-id="4b721-103">Предоставляет методы, позволяющие общеязыковой среды выполнения (CLR) для взаимодействия с основным приложением для управления задачами.</span><span class="sxs-lookup"><span data-stu-id="4b721-103">Provides methods that allow the common language runtime (CLR) to communicate with the host to manage tasks.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4b721-104">Методы</span><span class="sxs-lookup"><span data-stu-id="4b721-104">Methods</span></span>  
  
|<span data-ttu-id="4b721-105">Метод</span><span class="sxs-lookup"><span data-stu-id="4b721-105">Method</span></span>|<span data-ttu-id="4b721-106">Описание</span><span class="sxs-lookup"><span data-stu-id="4b721-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4b721-107">Метод Alert</span><span class="sxs-lookup"><span data-stu-id="4b721-107">Alert Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md)|<span data-ttu-id="4b721-108">Запросы, что узел пробуждения задач, представленный текущим `IHostTask` экземпляра, поэтому задача может быть прервана.</span><span class="sxs-lookup"><span data-stu-id="4b721-108">Requests that the host wake the task represented by the current `IHostTask` instance, so the task can be aborted.</span></span>|  
|[<span data-ttu-id="4b721-109">Метод GetPriority</span><span class="sxs-lookup"><span data-stu-id="4b721-109">GetPriority Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)|<span data-ttu-id="4b721-110">Возвращает уровень приоритета потока задачи, представленный текущим `IHostTask` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="4b721-110">Gets the thread priority level of the task represented by the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="4b721-111">Метод Join</span><span class="sxs-lookup"><span data-stu-id="4b721-111">Join Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md)|<span data-ttu-id="4b721-112">Блокирует вызывающий задачу до выполнения задачи, представленный текущим `IHostTask` завершения экземпляра, истечения заданного интервала, или [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) вызывается.</span><span class="sxs-lookup"><span data-stu-id="4b721-112">Blocks the calling task until the task represented by the current `IHostTask` instance completes, the specified time interval elapses, or [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) is called.</span></span>|  
|[<span data-ttu-id="4b721-113">Метод SetCLRTask</span><span class="sxs-lookup"><span data-stu-id="4b721-113">SetCLRTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md)|<span data-ttu-id="4b721-114">Связывает [ICLRTask-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) экземпляра с текущим `IHostTask` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="4b721-114">Associates an [ICLRTask Interface](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance with the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="4b721-115">Метод SetPriority</span><span class="sxs-lookup"><span data-stu-id="4b721-115">SetPriority Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setpriority-method.md)|<span data-ttu-id="4b721-116">Уровень запросов, настройки, узле приоритет потока для задачи, представленный текущим `IHostTask` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="4b721-116">Requests that the host adjust the thread priority level for the task represented by the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="4b721-117">Метод Start</span><span class="sxs-lookup"><span data-stu-id="4b721-117">Start Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md)|<span data-ttu-id="4b721-118">Запросы, что узел перемещения задач, представленный текущим `IHostTask` экземпляр из приостановленного состояния к активному состоянию, в котором можно выполнять код.</span><span class="sxs-lookup"><span data-stu-id="4b721-118">Requests that the host move the task represented by the current `IHostTask` instance from a suspended state to a live state, in which code can be executed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4b721-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="4b721-119">Remarks</span></span>  
 <span data-ttu-id="4b721-120">Среда CLR вызывает методы, определенные `IHostTask` запустить задачу, установите его приоритет потока уровень, и т. д.</span><span class="sxs-lookup"><span data-stu-id="4b721-120">The CLR calls methods defined by `IHostTask` to start a task, set its thread priority level, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b721-121">Требования</span><span class="sxs-lookup"><span data-stu-id="4b721-121">Requirements</span></span>  
 <span data-ttu-id="4b721-122">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b721-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b721-123">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4b721-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4b721-124">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4b721-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4b721-125">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b721-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b721-126">См. также</span><span class="sxs-lookup"><span data-stu-id="4b721-126">See Also</span></span>  
 [<span data-ttu-id="4b721-127">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="4b721-127">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="4b721-128">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="4b721-128">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="4b721-129">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="4b721-129">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="4b721-130">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="4b721-130">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)

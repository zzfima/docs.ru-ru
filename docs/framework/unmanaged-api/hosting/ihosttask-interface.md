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
ms.openlocfilehash: 18dfee606f3d41229aa58a5b4bb9380b87c4efa5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121393"
---
# <a name="ihosttask-interface"></a><span data-ttu-id="8b088-102">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="8b088-102">IHostTask Interface</span></span>
<span data-ttu-id="8b088-103">Предоставляет методы, позволяющие среде CLR взаимодействовать с узлом для управления задачами.</span><span class="sxs-lookup"><span data-stu-id="8b088-103">Provides methods that allow the common language runtime (CLR) to communicate with the host to manage tasks.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8b088-104">Методы</span><span class="sxs-lookup"><span data-stu-id="8b088-104">Methods</span></span>  
  
|<span data-ttu-id="8b088-105">Метод</span><span class="sxs-lookup"><span data-stu-id="8b088-105">Method</span></span>|<span data-ttu-id="8b088-106">Описание</span><span class="sxs-lookup"><span data-stu-id="8b088-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8b088-107">Метод Alert</span><span class="sxs-lookup"><span data-stu-id="8b088-107">Alert Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md)|<span data-ttu-id="8b088-108">Запрашивает выход узла из задачи, представленной текущим экземпляром `IHostTask`, поэтому задачу можно прервать.</span><span class="sxs-lookup"><span data-stu-id="8b088-108">Requests that the host wake the task represented by the current `IHostTask` instance, so the task can be aborted.</span></span>|  
|[<span data-ttu-id="8b088-109">Метод GetPriority</span><span class="sxs-lookup"><span data-stu-id="8b088-109">GetPriority Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)|<span data-ttu-id="8b088-110">Возвращает уровень приоритета потока задачи, представленной текущим экземпляром `IHostTask`.</span><span class="sxs-lookup"><span data-stu-id="8b088-110">Gets the thread priority level of the task represented by the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="8b088-111">Метод Join</span><span class="sxs-lookup"><span data-stu-id="8b088-111">Join Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md)|<span data-ttu-id="8b088-112">Блокирует вызывающую задачу до тех пор, пока задача, представленная текущим экземпляром `IHostTask`, не завершится, заданный интервал времени истечет или будет вызван метод [IHostTask:: Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) .</span><span class="sxs-lookup"><span data-stu-id="8b088-112">Blocks the calling task until the task represented by the current `IHostTask` instance completes, the specified time interval elapses, or [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) is called.</span></span>|  
|[<span data-ttu-id="8b088-113">Метод SetCLRTask</span><span class="sxs-lookup"><span data-stu-id="8b088-113">SetCLRTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md)|<span data-ttu-id="8b088-114">Связывает экземпляр [интерфейса ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) с текущим экземпляром `IHostTask`.</span><span class="sxs-lookup"><span data-stu-id="8b088-114">Associates an [ICLRTask Interface](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance with the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="8b088-115">Метод SetPriority</span><span class="sxs-lookup"><span data-stu-id="8b088-115">SetPriority Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setpriority-method.md)|<span data-ttu-id="8b088-116">Запрашивает у узла настройку уровня приоритета потока для задачи, представленной текущим экземпляром `IHostTask`.</span><span class="sxs-lookup"><span data-stu-id="8b088-116">Requests that the host adjust the thread priority level for the task represented by the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="8b088-117">Метод Start</span><span class="sxs-lookup"><span data-stu-id="8b088-117">Start Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md)|<span data-ttu-id="8b088-118">Запрашивает, что узел перемещает задачу, представленную текущим экземпляром `IHostTask`, из приостановленного состояния в активное состояние, в котором можно выполнить код.</span><span class="sxs-lookup"><span data-stu-id="8b088-118">Requests that the host move the task represented by the current `IHostTask` instance from a suspended state to a live state, in which code can be executed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8b088-119">Заметки</span><span class="sxs-lookup"><span data-stu-id="8b088-119">Remarks</span></span>  
 <span data-ttu-id="8b088-120">Среда CLR вызывает методы, определенные `IHostTask`, для запуска задачи, установки ее уровня приоритета и т. д.</span><span class="sxs-lookup"><span data-stu-id="8b088-120">The CLR calls methods defined by `IHostTask` to start a task, set its thread priority level, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b088-121">Требования</span><span class="sxs-lookup"><span data-stu-id="8b088-121">Requirements</span></span>  
 <span data-ttu-id="8b088-122">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b088-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b088-123">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="8b088-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8b088-124">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="8b088-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8b088-125">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b088-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b088-126">См. также</span><span class="sxs-lookup"><span data-stu-id="8b088-126">See also</span></span>

- [<span data-ttu-id="8b088-127">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="8b088-127">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="8b088-128">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="8b088-128">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="8b088-129">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="8b088-129">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="8b088-130">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="8b088-130">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)

---
title: Интерфейс ICLRTaskManager
ms.date: 03/30/2017
api_name:
- ICLRTaskManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager
helpviewer_keywords:
- ICLRTaskManager interface [.NET Framework hosting]
ms.assetid: 2bd55e0c-001b-41fd-b29d-f01670fe8216
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 14c2c9b70ac2e57983ea4b16772add6a1dff5ff4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="iclrtaskmanager-interface"></a><span data-ttu-id="b5a3e-102">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="b5a3e-102">ICLRTaskManager Interface</span></span>
<span data-ttu-id="b5a3e-103">Предоставляет методы, позволяющие основному приложению явным образом запросить общеязыковой среды выполнения (CLR) создайте новую задачу, выполняемую задачу и задать географического язык и региональные параметры для задачи.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-103">Provides methods that allow the host to request explicitly that the common language runtime (CLR) create a new task, get the currently executing task, and set the geographic language and culture for the task.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b5a3e-104">Методы</span><span class="sxs-lookup"><span data-stu-id="b5a3e-104">Methods</span></span>  
  
|<span data-ttu-id="b5a3e-105">Метод</span><span class="sxs-lookup"><span data-stu-id="b5a3e-105">Method</span></span>|<span data-ttu-id="b5a3e-106">Описание</span><span class="sxs-lookup"><span data-stu-id="b5a3e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b5a3e-107">Метод CreateTask</span><span class="sxs-lookup"><span data-stu-id="b5a3e-107">CreateTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-createtask-method.md)|<span data-ttu-id="b5a3e-108">Явно запрашивает, создайте новый том, что среда CLR [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-108">Requests explicitly that the CLR create a new [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance.</span></span>|  
|[<span data-ttu-id="b5a3e-109">Метод GetCurrentTask</span><span class="sxs-lookup"><span data-stu-id="b5a3e-109">GetCurrentTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-getcurrenttask-method.md)|<span data-ttu-id="b5a3e-110">Возвращает `ICLRTask` экземпляр, представляющий выполняющийся в данный момент задачу.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-110">Gets the `ICLRTask` instance that represents the task that is currently executing.</span></span>|  
|[<span data-ttu-id="b5a3e-111">Метод GetCurrentTaskType</span><span class="sxs-lookup"><span data-stu-id="b5a3e-111">GetCurrentTaskType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-getcurrenttasktype-method.md)|<span data-ttu-id="b5a3e-112">Получает тип задачи, выполняемой в данный момент.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-112">Gets the type of the task that is currently executing.</span></span>|  
|[<span data-ttu-id="b5a3e-113">Метод SetLocale</span><span class="sxs-lookup"><span data-stu-id="b5a3e-113">SetLocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-setlocale-method.md)|<span data-ttu-id="b5a3e-114">Уведомляет среду CLR, узла изменило идентификатор языкового стандарта в текущей выполняемой задаче.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-114">Notifies the CLR that the host has modified the locale identifier on the currently executing task.</span></span>|  
|[<span data-ttu-id="b5a3e-115">Метод SetUILocale</span><span class="sxs-lookup"><span data-stu-id="b5a3e-115">SetUILocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-setuilocale-method.md)|<span data-ttu-id="b5a3e-116">Уведомляет общеязыковая среда выполнения о том, что узел изменил идентификатор языкового стандарта интерфейса пользователя в текущей выполняемой задачи.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-116">Notifies the common language runtime that the host has modified the user interface locale identifier on the currently executing task.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b5a3e-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="b5a3e-117">Remarks</span></span>  
 <span data-ttu-id="b5a3e-118">Каждая задача, на котором работает в размещенной среде имеет оба представления на стороне узла (экземпляр [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)) и на стороне среды CLR (экземпляр [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)).</span><span class="sxs-lookup"><span data-stu-id="b5a3e-118">Each task that is running in a hosted environment has representations both on the host side (an instance of [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)) and on the CLR side (an instance of [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)).</span></span> <span data-ttu-id="b5a3e-119">Узел или среда CLR может инициировать создание задачи, но представление главного узла должен быть связан с соответствующей представление на стороне среды CLR для обеспечения успешного обмена данными между узлом и CLR связи с этой задачей.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-119">Either the host or the CLR can initiate the creation of a task, but the host-side representation must be associated with a corresponding CLR-side representation to ensure successful communication between the host and the CLR regarding the task.</span></span> <span data-ttu-id="b5a3e-120">Два объекта должно быть создано и создать ее экземпляр перед управляемый код может выполнять в потоке операционной системы.</span><span class="sxs-lookup"><span data-stu-id="b5a3e-120">The two objects must be created and instantiated before managed code can execute on an operating system thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5a3e-121">Требования</span><span class="sxs-lookup"><span data-stu-id="b5a3e-121">Requirements</span></span>  
 <span data-ttu-id="b5a3e-122">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5a3e-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5a3e-123">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b5a3e-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b5a3e-124">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b5a3e-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b5a3e-125">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5a3e-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5a3e-126">См. также</span><span class="sxs-lookup"><span data-stu-id="b5a3e-126">See Also</span></span>  
 [<span data-ttu-id="b5a3e-127">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="b5a3e-127">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="b5a3e-128">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="b5a3e-128">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="b5a3e-129">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="b5a3e-129">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="b5a3e-130">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="b5a3e-130">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)

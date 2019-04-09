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
ms.openlocfilehash: 19ef7cb78791496de76e5741f8254ee88563c776
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59134664"
---
# <a name="iclrtaskmanager-interface"></a><span data-ttu-id="2e483-102">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="2e483-102">ICLRTaskManager Interface</span></span>
<span data-ttu-id="2e483-103">Предоставляет методы, позволяющие основному приложению явным образом запросить общеязыковой среды выполнения (CLR) создайте новую задачу, выполняемую задачу и задать географических язык и язык и региональные параметры для задачи.</span><span class="sxs-lookup"><span data-stu-id="2e483-103">Provides methods that allow the host to request explicitly that the common language runtime (CLR) create a new task, get the currently executing task, and set the geographic language and culture for the task.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2e483-104">Методы</span><span class="sxs-lookup"><span data-stu-id="2e483-104">Methods</span></span>  
  
|<span data-ttu-id="2e483-105">Метод</span><span class="sxs-lookup"><span data-stu-id="2e483-105">Method</span></span>|<span data-ttu-id="2e483-106">Описание</span><span class="sxs-lookup"><span data-stu-id="2e483-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2e483-107">Метод CreateTask</span><span class="sxs-lookup"><span data-stu-id="2e483-107">CreateTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-createtask-method.md)|<span data-ttu-id="2e483-108">Запрашивает явным образом, что среда CLR создаст новый [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="2e483-108">Requests explicitly that the CLR create a new [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance.</span></span>|  
|[<span data-ttu-id="2e483-109">Метод GetCurrentTask</span><span class="sxs-lookup"><span data-stu-id="2e483-109">GetCurrentTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-getcurrenttask-method.md)|<span data-ttu-id="2e483-110">Получает `ICLRTask` экземпляр, который представляет задачу, которая в данный момент.</span><span class="sxs-lookup"><span data-stu-id="2e483-110">Gets the `ICLRTask` instance that represents the task that is currently executing.</span></span>|  
|[<span data-ttu-id="2e483-111">Метод GetCurrentTaskType</span><span class="sxs-lookup"><span data-stu-id="2e483-111">GetCurrentTaskType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-getcurrenttasktype-method.md)|<span data-ttu-id="2e483-112">Получает тип задачи, выполняемой в данный момент.</span><span class="sxs-lookup"><span data-stu-id="2e483-112">Gets the type of the task that is currently executing.</span></span>|  
|[<span data-ttu-id="2e483-113">Метод SetLocale</span><span class="sxs-lookup"><span data-stu-id="2e483-113">SetLocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-setlocale-method.md)|<span data-ttu-id="2e483-114">Уведомляет CLR о том, что узел изменил идентификатор языкового стандарта в текущей выполняемой задачи.</span><span class="sxs-lookup"><span data-stu-id="2e483-114">Notifies the CLR that the host has modified the locale identifier on the currently executing task.</span></span>|  
|[<span data-ttu-id="2e483-115">Метод SetUILocale</span><span class="sxs-lookup"><span data-stu-id="2e483-115">SetUILocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-setuilocale-method.md)|<span data-ttu-id="2e483-116">Уведомляет среду о том, что узел изменил идентификатор языка интерфейса пользователя в текущей выполняемой задаче.</span><span class="sxs-lookup"><span data-stu-id="2e483-116">Notifies the common language runtime that the host has modified the user interface locale identifier on the currently executing task.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2e483-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="2e483-117">Remarks</span></span>  
 <span data-ttu-id="2e483-118">Каждая задача, на котором работает в размещенной среде имеет оба представления на стороне главного приложения (экземпляр [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)) и на стороне среды CLR (экземпляр [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)).</span><span class="sxs-lookup"><span data-stu-id="2e483-118">Each task that is running in a hosted environment has representations both on the host side (an instance of [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)) and on the CLR side (an instance of [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)).</span></span> <span data-ttu-id="2e483-119">На узле или среда CLR может инициировать создание задачи, но представление на стороне узла должна быть связана с соответствующей представление на стороне среды CLR для обеспечения успешной связи между узлом и среда CLR связи с этой задачей.</span><span class="sxs-lookup"><span data-stu-id="2e483-119">Either the host or the CLR can initiate the creation of a task, but the host-side representation must be associated with a corresponding CLR-side representation to ensure successful communication between the host and the CLR regarding the task.</span></span> <span data-ttu-id="2e483-120">Два объекта должны быть и ее экземпляр перед выполнением управляемого кода в потоке операционной системы.</span><span class="sxs-lookup"><span data-stu-id="2e483-120">The two objects must be created and instantiated before managed code can execute on an operating system thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e483-121">Требования</span><span class="sxs-lookup"><span data-stu-id="2e483-121">Requirements</span></span>  
 <span data-ttu-id="2e483-122">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e483-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e483-123">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2e483-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2e483-124">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2e483-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="2e483-125">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="2e483-125">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2e483-126">См. также</span><span class="sxs-lookup"><span data-stu-id="2e483-126">See also</span></span>

- [<span data-ttu-id="2e483-127">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="2e483-127">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="2e483-128">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="2e483-128">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="2e483-129">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="2e483-129">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="2e483-130">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="2e483-130">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)

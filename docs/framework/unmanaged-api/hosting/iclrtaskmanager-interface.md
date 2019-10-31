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
ms.openlocfilehash: e25a6a03a836b8b4964b8260c974c8e8d8d9998d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73092186"
---
# <a name="iclrtaskmanager-interface"></a><span data-ttu-id="ca0f9-102">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="ca0f9-102">ICLRTaskManager Interface</span></span>
<span data-ttu-id="ca0f9-103">Предоставляет методы, позволяющие узлу явно запрашивать, что среда CLR создает новую задачу, получает выполняемую в данный момент задачу и задает язык и региональные параметры для задачи.</span><span class="sxs-lookup"><span data-stu-id="ca0f9-103">Provides methods that allow the host to request explicitly that the common language runtime (CLR) create a new task, get the currently executing task, and set the geographic language and culture for the task.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ca0f9-104">Методы</span><span class="sxs-lookup"><span data-stu-id="ca0f9-104">Methods</span></span>  
  
|<span data-ttu-id="ca0f9-105">Метод</span><span class="sxs-lookup"><span data-stu-id="ca0f9-105">Method</span></span>|<span data-ttu-id="ca0f9-106">Описание</span><span class="sxs-lookup"><span data-stu-id="ca0f9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ca0f9-107">Метод CreateTask</span><span class="sxs-lookup"><span data-stu-id="ca0f9-107">CreateTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-createtask-method.md)|<span data-ttu-id="ca0f9-108">Явно запрашивает, что среда CLR создает новый экземпляр [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="ca0f9-108">Requests explicitly that the CLR create a new [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance.</span></span>|  
|[<span data-ttu-id="ca0f9-109">Метод GetCurrentTask</span><span class="sxs-lookup"><span data-stu-id="ca0f9-109">GetCurrentTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-getcurrenttask-method.md)|<span data-ttu-id="ca0f9-110">Возвращает экземпляр `ICLRTask`, представляющий выполняемую в данный момент задачу.</span><span class="sxs-lookup"><span data-stu-id="ca0f9-110">Gets the `ICLRTask` instance that represents the task that is currently executing.</span></span>|  
|[<span data-ttu-id="ca0f9-111">Метод GetCurrentTaskType</span><span class="sxs-lookup"><span data-stu-id="ca0f9-111">GetCurrentTaskType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-getcurrenttasktype-method.md)|<span data-ttu-id="ca0f9-112">Возвращает тип выполняемой в данный момент задачи.</span><span class="sxs-lookup"><span data-stu-id="ca0f9-112">Gets the type of the task that is currently executing.</span></span>|  
|[<span data-ttu-id="ca0f9-113">Метод SetLocale</span><span class="sxs-lookup"><span data-stu-id="ca0f9-113">SetLocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-setlocale-method.md)|<span data-ttu-id="ca0f9-114">Уведомляет среду CLR о том, что узел изменил идентификатор локали в выполняющейся задаче.</span><span class="sxs-lookup"><span data-stu-id="ca0f9-114">Notifies the CLR that the host has modified the locale identifier on the currently executing task.</span></span>|  
|[<span data-ttu-id="ca0f9-115">Метод SetUILocale</span><span class="sxs-lookup"><span data-stu-id="ca0f9-115">SetUILocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-setuilocale-method.md)|<span data-ttu-id="ca0f9-116">Уведомляет среду CLR о том, что узел изменил идентификатор локали пользовательского интерфейса для выполняемой в данный момент задачи.</span><span class="sxs-lookup"><span data-stu-id="ca0f9-116">Notifies the common language runtime that the host has modified the user interface locale identifier on the currently executing task.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca0f9-117">Заметки</span><span class="sxs-lookup"><span data-stu-id="ca0f9-117">Remarks</span></span>  
 <span data-ttu-id="ca0f9-118">Каждая задача, выполняемая в среде размещения, имеет представления на стороне размещения (экземпляр [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)) и на стороне среды CLR (экземпляре [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)).</span><span class="sxs-lookup"><span data-stu-id="ca0f9-118">Each task that is running in a hosted environment has representations both on the host side (an instance of [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)) and on the CLR side (an instance of [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)).</span></span> <span data-ttu-id="ca0f9-119">Приложение или среда CLR могут инициировать создание задачи, но представление на стороне главного приложения должно быть связано с соответствующим представлением на стороне среды CLR для обеспечения успешной связи между узлом и средой CLR, относящейся к задаче.</span><span class="sxs-lookup"><span data-stu-id="ca0f9-119">Either the host or the CLR can initiate the creation of a task, but the host-side representation must be associated with a corresponding CLR-side representation to ensure successful communication between the host and the CLR regarding the task.</span></span> <span data-ttu-id="ca0f9-120">Перед выполнением управляемого кода в потоке операционной системы необходимо создать и создать экземпляры этих двух объектов.</span><span class="sxs-lookup"><span data-stu-id="ca0f9-120">The two objects must be created and instantiated before managed code can execute on an operating system thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca0f9-121">Требования</span><span class="sxs-lookup"><span data-stu-id="ca0f9-121">Requirements</span></span>  
 <span data-ttu-id="ca0f9-122">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca0f9-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca0f9-123">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ca0f9-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ca0f9-124">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ca0f9-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ca0f9-125">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca0f9-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca0f9-126">См. также</span><span class="sxs-lookup"><span data-stu-id="ca0f9-126">See also</span></span>

- [<span data-ttu-id="ca0f9-127">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="ca0f9-127">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="ca0f9-128">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="ca0f9-128">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="ca0f9-129">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="ca0f9-129">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="ca0f9-130">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="ca0f9-130">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)

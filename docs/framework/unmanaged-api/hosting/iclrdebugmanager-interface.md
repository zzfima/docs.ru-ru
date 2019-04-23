---
title: Интерфейс ICLRDebugManager
ms.date: 03/30/2017
api_name:
- ICLRDebugManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager
helpviewer_keywords:
- ICLRDebugManager interface [.NET Framework hosting]
ms.assetid: e835062c-c7d6-4945-8a44-2de7ebf3928e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 22c3a480e2b68377e300df1083b3178ee4e2d2a9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59198846"
---
# <a name="iclrdebugmanager-interface"></a><span data-ttu-id="0e0e8-102">Интерфейс ICLRDebugManager</span><span class="sxs-lookup"><span data-stu-id="0e0e8-102">ICLRDebugManager Interface</span></span>
<span data-ttu-id="0e0e8-103">Предоставляет методы, которые позволяют ведущему приложению связать набор задач с идентификатором и понятное имя.</span><span class="sxs-lookup"><span data-stu-id="0e0e8-103">Provides methods that allow a host to associate a set of tasks with an identifier and a friendly name.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0e0e8-104">Методы</span><span class="sxs-lookup"><span data-stu-id="0e0e8-104">Methods</span></span>  
  
|<span data-ttu-id="0e0e8-105">Метод</span><span class="sxs-lookup"><span data-stu-id="0e0e8-105">Method</span></span>|<span data-ttu-id="0e0e8-106">Описание</span><span class="sxs-lookup"><span data-stu-id="0e0e8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0e0e8-107">Метод BeginConnection</span><span class="sxs-lookup"><span data-stu-id="0e0e8-107">BeginConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)|<span data-ttu-id="0e0e8-108">Устанавливает новое соединение между узлом и отладчик связывания задачи с идентификатором и понятное имя.</span><span class="sxs-lookup"><span data-stu-id="0e0e8-108">Establishes a new connection between the host and the debugger to associate tasks with an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="0e0e8-109">Метод EndConnection</span><span class="sxs-lookup"><span data-stu-id="0e0e8-109">EndConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)|<span data-ttu-id="0e0e8-110">Удаляет связь между список задач и идентификатора и понятным именем.</span><span class="sxs-lookup"><span data-stu-id="0e0e8-110">Removes the association between a list of tasks and an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="0e0e8-111">Метод GetDacl</span><span class="sxs-lookup"><span data-stu-id="0e0e8-111">GetDacl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-getdacl-method.md)|<span data-ttu-id="0e0e8-112">Этот метод не реализован.</span><span class="sxs-lookup"><span data-stu-id="0e0e8-112">This method is not implemented.</span></span>|  
|[<span data-ttu-id="0e0e8-113">Метод IsDebuggerAttached</span><span class="sxs-lookup"><span data-stu-id="0e0e8-113">IsDebuggerAttached Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-isdebuggerattached-method.md)|<span data-ttu-id="0e0e8-114">Получает значение, показывающее, присоединен ли отладчик к процессу.</span><span class="sxs-lookup"><span data-stu-id="0e0e8-114">Gets a value that indicates whether a debugger is attached to the process.</span></span>|  
|[<span data-ttu-id="0e0e8-115">Метод SetConnectionTasks</span><span class="sxs-lookup"><span data-stu-id="0e0e8-115">SetConnectionTasks Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)|<span data-ttu-id="0e0e8-116">Связывает список [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) экземпляры с идентификатором и понятное имя.</span><span class="sxs-lookup"><span data-stu-id="0e0e8-116">Associates a list of [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instances with an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="0e0e8-117">Метод SetDacl</span><span class="sxs-lookup"><span data-stu-id="0e0e8-117">SetDacl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setdacl-method.md)|<span data-ttu-id="0e0e8-118">Этот метод не реализован.</span><span class="sxs-lookup"><span data-stu-id="0e0e8-118">This method is not implemented.</span></span>|  
|[<span data-ttu-id="0e0e8-119">Метод SetSymbolReadingPolicy</span><span class="sxs-lookup"><span data-stu-id="0e0e8-119">SetSymbolReadingPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md)|<span data-ttu-id="0e0e8-120">Задает политику для чтения файлов базы данных (PDB).</span><span class="sxs-lookup"><span data-stu-id="0e0e8-120">Sets the policy for reading program database (PDB) files.</span></span> <span data-ttu-id="0e0e8-121">Политика определяет, включаются ли сведения о файлах и номера строк в стеках вызовов.</span><span class="sxs-lookup"><span data-stu-id="0e0e8-121">The policy determines whether information about line numbers and files is included in call stacks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0e0e8-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="0e0e8-122">Remarks</span></span>  
 <span data-ttu-id="0e0e8-123">В сценариях отладки, узел может потребоваться сгруппировать задачи в соответствии с собственной логикой программирования.</span><span class="sxs-lookup"><span data-stu-id="0e0e8-123">In debugging scenarios, a host might want to group tasks according to its own programming logic.</span></span> <span data-ttu-id="0e0e8-124">Например группирование позволит разработчику видят только те задачи, необходимые для API разработчика, вместо всего списка задач, выполняемых в процессе.</span><span class="sxs-lookup"><span data-stu-id="0e0e8-124">For example, a grouping would allow a developer to see only the tasks required by the developer's APIs, instead of seeing every task running in the process.</span></span> <span data-ttu-id="0e0e8-125">`ICLRDebugManager` позволяет узлу для реализации такого рода группирования.</span><span class="sxs-lookup"><span data-stu-id="0e0e8-125">`ICLRDebugManager` allows the host to implement this kind of grouping.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0e0e8-126">Три `ICLRDebugManager` методы, `BeginConnection`, `SetConnectionTasks` и `EndConnection`, зависят от друг с другом.</span><span class="sxs-lookup"><span data-stu-id="0e0e8-126">Three `ICLRDebugManager` methods, `BeginConnection`, `SetConnectionTasks` and `EndConnection`, are dependent upon each other.</span></span> <span data-ttu-id="0e0e8-127">Они должны вызываться в заданном порядке работала должным образом.</span><span class="sxs-lookup"><span data-stu-id="0e0e8-127">They must be called in the given order to work as expected.</span></span>  
  
 <span data-ttu-id="0e0e8-128">Группирование, идентификаторы и понятные имена, назначаемые узлом группированию, не имеют смысла для общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="0e0e8-128">The grouping, and the identifiers and friendly names that the host assigns to the grouping, have no meaning for the common language runtime (CLR).</span></span> <span data-ttu-id="0e0e8-129">Среда CLR передает информацию по отладчику.</span><span class="sxs-lookup"><span data-stu-id="0e0e8-129">The CLR merely passes the information along to the debugger.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e0e8-130">Требования</span><span class="sxs-lookup"><span data-stu-id="0e0e8-130">Requirements</span></span>  
 <span data-ttu-id="0e0e8-131">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e0e8-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e0e8-132">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0e0e8-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0e0e8-133">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0e0e8-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0e0e8-134">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e0e8-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e0e8-135">См. также</span><span class="sxs-lookup"><span data-stu-id="0e0e8-135">See also</span></span>

- [<span data-ttu-id="0e0e8-136">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="0e0e8-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)

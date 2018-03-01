---
title: "Интерфейс ICLRDebugManager"
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8e712f22156e96cfc58e9c1a835077ba21ecd184
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdebugmanager-interface"></a><span data-ttu-id="f7d88-102">Интерфейс ICLRDebugManager</span><span class="sxs-lookup"><span data-stu-id="f7d88-102">ICLRDebugManager Interface</span></span>
<span data-ttu-id="f7d88-103">Предоставляет методы, позволяющие ведущему приложению связать набор задач с идентификатором и понятным именем.</span><span class="sxs-lookup"><span data-stu-id="f7d88-103">Provides methods that allow a host to associate a set of tasks with an identifier and a friendly name.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f7d88-104">Методы</span><span class="sxs-lookup"><span data-stu-id="f7d88-104">Methods</span></span>  
  
|<span data-ttu-id="f7d88-105">Метод</span><span class="sxs-lookup"><span data-stu-id="f7d88-105">Method</span></span>|<span data-ttu-id="f7d88-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="f7d88-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f7d88-107">Метод BeginConnection</span><span class="sxs-lookup"><span data-stu-id="f7d88-107">BeginConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)|<span data-ttu-id="f7d88-108">Устанавливает новое соединение между узлом и отладчик связывания задачи с идентификатором и понятным именем.</span><span class="sxs-lookup"><span data-stu-id="f7d88-108">Establishes a new connection between the host and the debugger to associate tasks with an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="f7d88-109">Метод EndConnection</span><span class="sxs-lookup"><span data-stu-id="f7d88-109">EndConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)|<span data-ttu-id="f7d88-110">Удаляет связь между список задач и идентификатором и понятным именем.</span><span class="sxs-lookup"><span data-stu-id="f7d88-110">Removes the association between a list of tasks and an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="f7d88-111">Метод GetDacl</span><span class="sxs-lookup"><span data-stu-id="f7d88-111">GetDacl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-getdacl-method.md)|<span data-ttu-id="f7d88-112">Этот метод не реализован.</span><span class="sxs-lookup"><span data-stu-id="f7d88-112">This method is not implemented.</span></span>|  
|[<span data-ttu-id="f7d88-113">Метод IsDebuggerAttached</span><span class="sxs-lookup"><span data-stu-id="f7d88-113">IsDebuggerAttached Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-isdebuggerattached-method.md)|<span data-ttu-id="f7d88-114">Получает значение, показывающее, присоединен ли отладчик к процессу.</span><span class="sxs-lookup"><span data-stu-id="f7d88-114">Gets a value that indicates whether a debugger is attached to the process.</span></span>|  
|[<span data-ttu-id="f7d88-115">Метод SetConnectionTasks</span><span class="sxs-lookup"><span data-stu-id="f7d88-115">SetConnectionTasks Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)|<span data-ttu-id="f7d88-116">Связывает список [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) экземпляры с идентификатором и понятное имя.</span><span class="sxs-lookup"><span data-stu-id="f7d88-116">Associates a list of [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instances with an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="f7d88-117">Метод SetDacl</span><span class="sxs-lookup"><span data-stu-id="f7d88-117">SetDacl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setdacl-method.md)|<span data-ttu-id="f7d88-118">Этот метод не реализован.</span><span class="sxs-lookup"><span data-stu-id="f7d88-118">This method is not implemented.</span></span>|  
|[<span data-ttu-id="f7d88-119">Метод SetSymbolReadingPolicy</span><span class="sxs-lookup"><span data-stu-id="f7d88-119">SetSymbolReadingPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md)|<span data-ttu-id="f7d88-120">Задает политику для чтения файлов базы данных (PDB).</span><span class="sxs-lookup"><span data-stu-id="f7d88-120">Sets the policy for reading program database (PDB) files.</span></span> <span data-ttu-id="f7d88-121">Политика определяет, включены ли сведения о номерах строк и файлах в стеки вызовов.</span><span class="sxs-lookup"><span data-stu-id="f7d88-121">The policy determines whether information about line numbers and files is included in call stacks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f7d88-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="f7d88-122">Remarks</span></span>  
 <span data-ttu-id="f7d88-123">В сценариях отладки узлу может потребоваться для группирования задач в соответствии с собственной логикой программирования.</span><span class="sxs-lookup"><span data-stu-id="f7d88-123">In debugging scenarios, a host might want to group tasks according to its own programming logic.</span></span> <span data-ttu-id="f7d88-124">Например группирование позволит разработчику видеть только действия, необходимые для API разработчика, вместо всего списка задач, выполняемых в процессе.</span><span class="sxs-lookup"><span data-stu-id="f7d88-124">For example, a grouping would allow a developer to see only the tasks required by the developer's APIs, instead of seeing every task running in the process.</span></span> <span data-ttu-id="f7d88-125">`ICLRDebugManager`Позволяет ведущему приложению реализовать этот вид группировки.</span><span class="sxs-lookup"><span data-stu-id="f7d88-125">`ICLRDebugManager` allows the host to implement this kind of grouping.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f7d88-126">Три `ICLRDebugManager` методы, `BeginConnection`, `SetConnectionTasks` и `EndConnection`, зависящие от друг с другом.</span><span class="sxs-lookup"><span data-stu-id="f7d88-126">Three `ICLRDebugManager` methods, `BeginConnection`, `SetConnectionTasks` and `EndConnection`, are dependent upon each other.</span></span> <span data-ttu-id="f7d88-127">Они должны вызываться в определенном порядке для правильной работы.</span><span class="sxs-lookup"><span data-stu-id="f7d88-127">They must be called in the given order to work as expected.</span></span>  
  
 <span data-ttu-id="f7d88-128">Группирование, идентификаторы и понятные имена, назначаемые узлом группированию, не имеют смысла для общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="f7d88-128">The grouping, and the identifiers and friendly names that the host assigns to the grouping, have no meaning for the common language runtime (CLR).</span></span> <span data-ttu-id="f7d88-129">Среда CLR передает информацию по отладчику.</span><span class="sxs-lookup"><span data-stu-id="f7d88-129">The CLR merely passes the information along to the debugger.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7d88-130">Требования</span><span class="sxs-lookup"><span data-stu-id="f7d88-130">Requirements</span></span>  
 <span data-ttu-id="f7d88-131">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7d88-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7d88-132">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f7d88-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f7d88-133">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f7d88-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f7d88-134">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7d88-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7d88-135">См. также</span><span class="sxs-lookup"><span data-stu-id="f7d88-135">See Also</span></span>  
 [<span data-ttu-id="f7d88-136">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="f7d88-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)

---
title: "Интерфейс ICLRDebugManager"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDebugManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRDebugManager
helpviewer_keywords: ICLRDebugManager interface [.NET Framework hosting]
ms.assetid: e835062c-c7d6-4945-8a44-2de7ebf3928e
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0e537b955524f2721868ddf5da9fccf68f9d4efd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="iclrdebugmanager-interface"></a><span data-ttu-id="9256e-102">Интерфейс ICLRDebugManager</span><span class="sxs-lookup"><span data-stu-id="9256e-102">ICLRDebugManager Interface</span></span>
<span data-ttu-id="9256e-103">Предоставляет методы, позволяющие ведущему приложению связать набор задач с идентификатором и понятным именем.</span><span class="sxs-lookup"><span data-stu-id="9256e-103">Provides methods that allow a host to associate a set of tasks with an identifier and a friendly name.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9256e-104">Методы</span><span class="sxs-lookup"><span data-stu-id="9256e-104">Methods</span></span>  
  
|<span data-ttu-id="9256e-105">Метод</span><span class="sxs-lookup"><span data-stu-id="9256e-105">Method</span></span>|<span data-ttu-id="9256e-106">Описание</span><span class="sxs-lookup"><span data-stu-id="9256e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9256e-107">Beginconnection-метод</span><span class="sxs-lookup"><span data-stu-id="9256e-107">BeginConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)|<span data-ttu-id="9256e-108">Устанавливает новое соединение между узлом и отладчик связывания задачи с идентификатором и понятным именем.</span><span class="sxs-lookup"><span data-stu-id="9256e-108">Establishes a new connection between the host and the debugger to associate tasks with an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="9256e-109">EndConnection-метод</span><span class="sxs-lookup"><span data-stu-id="9256e-109">EndConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)|<span data-ttu-id="9256e-110">Удаляет связь между список задач и идентификатором и понятным именем.</span><span class="sxs-lookup"><span data-stu-id="9256e-110">Removes the association between a list of tasks and an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="9256e-111">Getdacl-метод</span><span class="sxs-lookup"><span data-stu-id="9256e-111">GetDacl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-getdacl-method.md)|<span data-ttu-id="9256e-112">Этот метод не реализован.</span><span class="sxs-lookup"><span data-stu-id="9256e-112">This method is not implemented.</span></span>|  
|[<span data-ttu-id="9256e-113">Метод IsDebuggerAttached</span><span class="sxs-lookup"><span data-stu-id="9256e-113">IsDebuggerAttached Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-isdebuggerattached-method.md)|<span data-ttu-id="9256e-114">Получает значение, показывающее, присоединен ли отладчик к процессу.</span><span class="sxs-lookup"><span data-stu-id="9256e-114">Gets a value that indicates whether a debugger is attached to the process.</span></span>|  
|[<span data-ttu-id="9256e-115">SetConnectionTasks-метод</span><span class="sxs-lookup"><span data-stu-id="9256e-115">SetConnectionTasks Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)|<span data-ttu-id="9256e-116">Связывает список [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) экземпляры с идентификатором и понятное имя.</span><span class="sxs-lookup"><span data-stu-id="9256e-116">Associates a list of [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instances with an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="9256e-117">Setdacl-метод</span><span class="sxs-lookup"><span data-stu-id="9256e-117">SetDacl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setdacl-method.md)|<span data-ttu-id="9256e-118">Этот метод не реализован.</span><span class="sxs-lookup"><span data-stu-id="9256e-118">This method is not implemented.</span></span>|  
|[<span data-ttu-id="9256e-119">Setsymbolreadingpolicy-метод</span><span class="sxs-lookup"><span data-stu-id="9256e-119">SetSymbolReadingPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md)|<span data-ttu-id="9256e-120">Задает политику для чтения файлов базы данных (PDB).</span><span class="sxs-lookup"><span data-stu-id="9256e-120">Sets the policy for reading program database (PDB) files.</span></span> <span data-ttu-id="9256e-121">Политика определяет, включены ли сведения о номерах строк и файлах в стеки вызовов.</span><span class="sxs-lookup"><span data-stu-id="9256e-121">The policy determines whether information about line numbers and files is included in call stacks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9256e-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="9256e-122">Remarks</span></span>  
 <span data-ttu-id="9256e-123">В сценариях отладки узлу может потребоваться для группирования задач в соответствии с собственной логикой программирования.</span><span class="sxs-lookup"><span data-stu-id="9256e-123">In debugging scenarios, a host might want to group tasks according to its own programming logic.</span></span> <span data-ttu-id="9256e-124">Например группирование позволит разработчику видеть только действия, необходимые для API разработчика, вместо всего списка задач, выполняемых в процессе.</span><span class="sxs-lookup"><span data-stu-id="9256e-124">For example, a grouping would allow a developer to see only the tasks required by the developer's APIs, instead of seeing every task running in the process.</span></span> <span data-ttu-id="9256e-125">`ICLRDebugManager`Позволяет ведущему приложению реализовать этот вид группировки.</span><span class="sxs-lookup"><span data-stu-id="9256e-125">`ICLRDebugManager` allows the host to implement this kind of grouping.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9256e-126">Три `ICLRDebugManager` методы, `BeginConnection`, `SetConnectionTasks` и `EndConnection`, зависящие от друг с другом.</span><span class="sxs-lookup"><span data-stu-id="9256e-126">Three `ICLRDebugManager` methods, `BeginConnection`, `SetConnectionTasks` and `EndConnection`, are dependent upon each other.</span></span> <span data-ttu-id="9256e-127">Они должны вызываться в определенном порядке для правильной работы.</span><span class="sxs-lookup"><span data-stu-id="9256e-127">They must be called in the given order to work as expected.</span></span>  
  
 <span data-ttu-id="9256e-128">Группирование, идентификаторы и понятные имена, назначаемые узлом группированию, не имеют смысла для общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="9256e-128">The grouping, and the identifiers and friendly names that the host assigns to the grouping, have no meaning for the common language runtime (CLR).</span></span> <span data-ttu-id="9256e-129">Среда CLR передает информацию по отладчику.</span><span class="sxs-lookup"><span data-stu-id="9256e-129">The CLR merely passes the information along to the debugger.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9256e-130">Требования</span><span class="sxs-lookup"><span data-stu-id="9256e-130">Requirements</span></span>  
 <span data-ttu-id="9256e-131">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9256e-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9256e-132">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9256e-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9256e-133">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9256e-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9256e-134">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9256e-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9256e-135">См. также</span><span class="sxs-lookup"><span data-stu-id="9256e-135">See Also</span></span>  
 [<span data-ttu-id="9256e-136">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="9256e-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)

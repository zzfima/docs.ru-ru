---
title: "Метод ICorDebugManagedCallback2::ChangeConnection"
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
- ICorDebugManagedCallback2.ChangeConnection
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::ChangeConnection
helpviewer_keywords:
- ICorDebugManagedCallback2::ChangeConnection method [.NET Framework debugging]
- ChangeConnection method [.NET Framework debugging]
ms.assetid: 7263f9a9-4c0b-4d82-a181-288873fb2b18
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2ba7e84c11f2fc8619b7046e222a742ee3298554
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallback2changeconnection-method"></a><span data-ttu-id="0bc28-102">Метод ICorDebugManagedCallback2::ChangeConnection</span><span class="sxs-lookup"><span data-stu-id="0bc28-102">ICorDebugManagedCallback2::ChangeConnection Method</span></span>
<span data-ttu-id="0bc28-103">Уведомляет отладчик об изменении набора задач, связанных с заданным подключением.</span><span class="sxs-lookup"><span data-stu-id="0bc28-103">Notifies the debugger that the set of tasks associated with the specified connection has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bc28-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0bc28-104">Syntax</span></span>  
  
```  
HRESULT ChangeConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0bc28-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0bc28-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="0bc28-106">[in] Указатель на объект «ICorDebugProcess», который представляет собой процесс, содержащий измененное соединение.</span><span class="sxs-lookup"><span data-stu-id="0bc28-106">[in] A pointer to an "ICorDebugProcess" object that represents the process containing the connection that changed.</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="0bc28-107">[in] Идентификатор соединения, которая изменена.</span><span class="sxs-lookup"><span data-stu-id="0bc28-107">[in] The ID of the connection that changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0bc28-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="0bc28-108">Remarks</span></span>  
 <span data-ttu-id="0bc28-109">Объект `ChangeConnection` обратный вызов будет запускаться в любом из следующих случаев:</span><span class="sxs-lookup"><span data-stu-id="0bc28-109">A `ChangeConnection` callback will be fired in either of the following cases:</span></span>  
  
-   <span data-ttu-id="0bc28-110">Когда отладчик подключается к процессу, содержащий подключения.</span><span class="sxs-lookup"><span data-stu-id="0bc28-110">When a debugger attaches to a process that contains connections.</span></span> <span data-ttu-id="0bc28-111">В этом случае среда выполнения создаст и отправки [ICorDebugManagedCallback2::CreateConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-createconnection-method.md) событий и `ChangeConnection` событий для каждого соединения в процессе.</span><span class="sxs-lookup"><span data-stu-id="0bc28-111">In this case, the runtime will generate and dispatch a [ICorDebugManagedCallback2::CreateConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-createconnection-method.md) event and a `ChangeConnection` event for each connection in the process.</span></span> <span data-ttu-id="0bc28-112">Объект `ChangeConnection` событие создается для каждого существующего подключения, независимо от того, это подключение набор задач был изменен с момента его создания.</span><span class="sxs-lookup"><span data-stu-id="0bc28-112">A `ChangeConnection` event is generated for every existing connection, regardless of whether that connection’s set of tasks has been changed since its creation.</span></span>  
  
-   <span data-ttu-id="0bc28-113">Если узел вызывает [ICLRDebugManager::SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md) в [API размещения](../../../../docs/framework/unmanaged-api/hosting/index.md).</span><span class="sxs-lookup"><span data-stu-id="0bc28-113">When a host calls [ICLRDebugManager::SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md) in the [Hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md).</span></span>  
  
 <span data-ttu-id="0bc28-114">Отладчик должен просканировать все потоки в процессе, чтобы собрать новые изменения.</span><span class="sxs-lookup"><span data-stu-id="0bc28-114">The debugger should scan all threads in the process to pick up the new changes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0bc28-115">Требования</span><span class="sxs-lookup"><span data-stu-id="0bc28-115">Requirements</span></span>  
 <span data-ttu-id="0bc28-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0bc28-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0bc28-117">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0bc28-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0bc28-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0bc28-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0bc28-119">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0bc28-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bc28-120">См. также</span><span class="sxs-lookup"><span data-stu-id="0bc28-120">See Also</span></span>  
 [<span data-ttu-id="0bc28-121">Интерфейс ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="0bc28-121">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [<span data-ttu-id="0bc28-122">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="0bc28-122">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)

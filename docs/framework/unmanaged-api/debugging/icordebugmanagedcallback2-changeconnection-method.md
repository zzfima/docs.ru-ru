---
title: "Метод ICorDebugManagedCallback2::ChangeConnection"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback2.ChangeConnection
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback2::ChangeConnection
helpviewer_keywords:
- ICorDebugManagedCallback2::ChangeConnection method [.NET Framework debugging]
- ChangeConnection method [.NET Framework debugging]
ms.assetid: 7263f9a9-4c0b-4d82-a181-288873fb2b18
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7c62859cb6a3e61af9670834db169410cecb6787
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmanagedcallback2changeconnection-method"></a><span data-ttu-id="ac75c-102">Метод ICorDebugManagedCallback2::ChangeConnection</span><span class="sxs-lookup"><span data-stu-id="ac75c-102">ICorDebugManagedCallback2::ChangeConnection Method</span></span>
<span data-ttu-id="ac75c-103">Уведомляет отладчик об изменении набора задач, связанных с заданным подключением.</span><span class="sxs-lookup"><span data-stu-id="ac75c-103">Notifies the debugger that the set of tasks associated with the specified connection has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac75c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ac75c-104">Syntax</span></span>  
  
```  
HRESULT ChangeConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ac75c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ac75c-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="ac75c-106">[in] Указатель на объект «ICorDebugProcess», который представляет собой процесс, содержащий измененное соединение.</span><span class="sxs-lookup"><span data-stu-id="ac75c-106">[in] A pointer to an "ICorDebugProcess" object that represents the process containing the connection that changed.</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="ac75c-107">[in] Идентификатор соединения, которая изменена.</span><span class="sxs-lookup"><span data-stu-id="ac75c-107">[in] The ID of the connection that changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ac75c-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="ac75c-108">Remarks</span></span>  
 <span data-ttu-id="ac75c-109">Объект `ChangeConnection` обратный вызов будет запускаться в любом из следующих случаев:</span><span class="sxs-lookup"><span data-stu-id="ac75c-109">A `ChangeConnection` callback will be fired in either of the following cases:</span></span>  
  
-   <span data-ttu-id="ac75c-110">Когда отладчик подключается к процессу, содержащий подключения.</span><span class="sxs-lookup"><span data-stu-id="ac75c-110">When a debugger attaches to a process that contains connections.</span></span> <span data-ttu-id="ac75c-111">В этом случае среда выполнения создаст и отправки [ICorDebugManagedCallback2::CreateConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-createconnection-method.md) событий и `ChangeConnection` событий для каждого соединения в процессе.</span><span class="sxs-lookup"><span data-stu-id="ac75c-111">In this case, the runtime will generate and dispatch a [ICorDebugManagedCallback2::CreateConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-createconnection-method.md) event and a `ChangeConnection` event for each connection in the process.</span></span> <span data-ttu-id="ac75c-112">Объект `ChangeConnection` событие создается для каждого существующего подключения, независимо от того, это подключение набор задач был изменен с момента его создания.</span><span class="sxs-lookup"><span data-stu-id="ac75c-112">A `ChangeConnection` event is generated for every existing connection, regardless of whether that connection’s set of tasks has been changed since its creation.</span></span>  
  
-   <span data-ttu-id="ac75c-113">Если узел вызывает [ICLRDebugManager::SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md) в [API размещения](../../../../docs/framework/unmanaged-api/hosting/index.md).</span><span class="sxs-lookup"><span data-stu-id="ac75c-113">When a host calls [ICLRDebugManager::SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md) in the [Hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md).</span></span>  
  
 <span data-ttu-id="ac75c-114">Отладчик должен просканировать все потоки в процессе, чтобы собрать новые изменения.</span><span class="sxs-lookup"><span data-stu-id="ac75c-114">The debugger should scan all threads in the process to pick up the new changes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac75c-115">Требования</span><span class="sxs-lookup"><span data-stu-id="ac75c-115">Requirements</span></span>  
 <span data-ttu-id="ac75c-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac75c-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac75c-117">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ac75c-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ac75c-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ac75c-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ac75c-119">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac75c-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac75c-120">См. также</span><span class="sxs-lookup"><span data-stu-id="ac75c-120">See Also</span></span>  
 [<span data-ttu-id="ac75c-121">ICorDebugManagedCallback2-интерфейс</span><span class="sxs-lookup"><span data-stu-id="ac75c-121">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [<span data-ttu-id="ac75c-122">ICorDebugManagedCallback-интерфейс</span><span class="sxs-lookup"><span data-stu-id="ac75c-122">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)

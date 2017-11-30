---
title: "Метод ICorDebugManagedCallback2::CreateConnection"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback2.CreateConnection
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback2::CreateConnection
helpviewer_keywords:
- CreateConnection method [.NET Framework debugging]
- ICorDebugManagedCallback2::CreateConnection method [.NET Framework debugging]
ms.assetid: 49e647be-9d63-4250-9d11-704e2a400d1b
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 716321508c18a415dc8e5c1c3e7e350deaf00a4f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmanagedcallback2createconnection-method"></a><span data-ttu-id="b4b99-102">Метод ICorDebugManagedCallback2::CreateConnection</span><span class="sxs-lookup"><span data-stu-id="b4b99-102">ICorDebugManagedCallback2::CreateConnection Method</span></span>
<span data-ttu-id="b4b99-103">Уведомляет отладчик о том, создания нового соединения.</span><span class="sxs-lookup"><span data-stu-id="b4b99-103">Notifies the debugger that a new connection has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4b99-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b4b99-104">Syntax</span></span>  
  
```  
HRESULT CreateConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId,  
    [in] WCHAR                *pConnName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b4b99-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b4b99-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="b4b99-106">[in] Указатель на объект «ICorDebugProcess», представляет собой процесс, в которой был создан соединения</span><span class="sxs-lookup"><span data-stu-id="b4b99-106">[in] A pointer to an "ICorDebugProcess" object that represents the process in which the connection was created</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="b4b99-107">[in] Идентификатор нового подключения.</span><span class="sxs-lookup"><span data-stu-id="b4b99-107">[in] The ID of the new connection.</span></span>  
  
 `pConnName`  
 <span data-ttu-id="b4b99-108">[in] Указатель на имя нового подключения.</span><span class="sxs-lookup"><span data-stu-id="b4b99-108">[in] A pointer to the name of the new connection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b4b99-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="b4b99-109">Remarks</span></span>  
 <span data-ttu-id="b4b99-110">Объект `CreateConnection` обратный вызов будет запускаться в любом из следующих случаев:</span><span class="sxs-lookup"><span data-stu-id="b4b99-110">A `CreateConnection` callback will be fired in either of the following cases:</span></span>  
  
-   <span data-ttu-id="b4b99-111">Когда отладчик подключается к процессу, содержащий подключения.</span><span class="sxs-lookup"><span data-stu-id="b4b99-111">When a debugger attaches to a process that contains connections.</span></span> <span data-ttu-id="b4b99-112">В этом случае среда выполнения создаст и отправки `CreateConnection` событий и [ICorDebugManagedCallback2::ChangeConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-changeconnection-method.md) событий для каждого соединения в процессе.</span><span class="sxs-lookup"><span data-stu-id="b4b99-112">In this case, the runtime will generate and dispatch a `CreateConnection` event and a [ICorDebugManagedCallback2::ChangeConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-changeconnection-method.md) event for each connection in the process.</span></span>  
  
-   <span data-ttu-id="b4b99-113">Если узел вызывает [ICLRDebugManager::BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) в [API размещения](../../../../docs/framework/unmanaged-api/hosting/index.md).</span><span class="sxs-lookup"><span data-stu-id="b4b99-113">When a host calls [ICLRDebugManager::BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) in the [Hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4b99-114">Требования</span><span class="sxs-lookup"><span data-stu-id="b4b99-114">Requirements</span></span>  
 <span data-ttu-id="b4b99-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4b99-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4b99-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b4b99-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b4b99-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b4b99-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b4b99-118">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4b99-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4b99-119">См. также</span><span class="sxs-lookup"><span data-stu-id="b4b99-119">See Also</span></span>  
 [<span data-ttu-id="b4b99-120">ICorDebugManagedCallback2-интерфейс</span><span class="sxs-lookup"><span data-stu-id="b4b99-120">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [<span data-ttu-id="b4b99-121">ICorDebugManagedCallback-интерфейс</span><span class="sxs-lookup"><span data-stu-id="b4b99-121">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)

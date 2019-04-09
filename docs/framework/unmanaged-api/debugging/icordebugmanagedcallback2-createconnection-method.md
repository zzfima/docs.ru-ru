---
title: Метод ICorDebugManagedCallback2::CreateConnection
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.CreateConnection
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::CreateConnection
helpviewer_keywords:
- CreateConnection method [.NET Framework debugging]
- ICorDebugManagedCallback2::CreateConnection method [.NET Framework debugging]
ms.assetid: 49e647be-9d63-4250-9d11-704e2a400d1b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f5035cd22ed099cec5e327c6957b13bcee52c766
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59191128"
---
# <a name="icordebugmanagedcallback2createconnection-method"></a><span data-ttu-id="c4e69-102">Метод ICorDebugManagedCallback2::CreateConnection</span><span class="sxs-lookup"><span data-stu-id="c4e69-102">ICorDebugManagedCallback2::CreateConnection Method</span></span>
<span data-ttu-id="c4e69-103">Уведомляет отладчик для создания нового соединения.</span><span class="sxs-lookup"><span data-stu-id="c4e69-103">Notifies the debugger that a new connection has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4e69-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c4e69-104">Syntax</span></span>  
  
```  
HRESULT CreateConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId,  
    [in] WCHAR                *pConnName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4e69-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c4e69-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="c4e69-106">[in] Указатель на объект «ICorDebugProcess», представляющий процесс, в котором был создан соединения</span><span class="sxs-lookup"><span data-stu-id="c4e69-106">[in] A pointer to an "ICorDebugProcess" object that represents the process in which the connection was created</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="c4e69-107">[in] Идентификатор нового подключения.</span><span class="sxs-lookup"><span data-stu-id="c4e69-107">[in] The ID of the new connection.</span></span>  
  
 `pConnName`  
 <span data-ttu-id="c4e69-108">[in] Указатель на имя нового подключения.</span><span class="sxs-lookup"><span data-stu-id="c4e69-108">[in] A pointer to the name of the new connection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4e69-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="c4e69-109">Remarks</span></span>  
 <span data-ttu-id="c4e69-110">Объект `CreateConnection` обратного вызова будет запускаться в любом из следующих случаев:</span><span class="sxs-lookup"><span data-stu-id="c4e69-110">A `CreateConnection` callback will be fired in either of the following cases:</span></span>  
  
-   <span data-ttu-id="c4e69-111">Когда отладчик подключается к процессу, который содержит соединения.</span><span class="sxs-lookup"><span data-stu-id="c4e69-111">When a debugger attaches to a process that contains connections.</span></span> <span data-ttu-id="c4e69-112">В этом случае среда выполнения создаст и диспетчеризации `CreateConnection` событий и [ICorDebugManagedCallback2::ChangeConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-changeconnection-method.md) событий для каждого соединения в процессе.</span><span class="sxs-lookup"><span data-stu-id="c4e69-112">In this case, the runtime will generate and dispatch a `CreateConnection` event and a [ICorDebugManagedCallback2::ChangeConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-changeconnection-method.md) event for each connection in the process.</span></span>  
  
-   <span data-ttu-id="c4e69-113">Если узел вызывает [ICLRDebugManager::BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) в [API размещения](../../../../docs/framework/unmanaged-api/hosting/index.md).</span><span class="sxs-lookup"><span data-stu-id="c4e69-113">When a host calls [ICLRDebugManager::BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) in the [Hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4e69-114">Требования</span><span class="sxs-lookup"><span data-stu-id="c4e69-114">Requirements</span></span>  
 <span data-ttu-id="c4e69-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4e69-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4e69-116">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c4e69-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c4e69-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4e69-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="c4e69-118">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="c4e69-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c4e69-119">См. также</span><span class="sxs-lookup"><span data-stu-id="c4e69-119">See also</span></span>

- [<span data-ttu-id="c4e69-120">Интерфейс ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="c4e69-120">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="c4e69-121">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="c4e69-121">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)

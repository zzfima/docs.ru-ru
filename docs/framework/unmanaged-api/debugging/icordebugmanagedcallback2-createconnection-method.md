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
ms.openlocfilehash: e98748b523b948dc002f2ebc4e2e79fc7d659918
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76781594"
---
# <a name="icordebugmanagedcallback2createconnection-method"></a><span data-ttu-id="0cf7a-102">Метод ICorDebugManagedCallback2::CreateConnection</span><span class="sxs-lookup"><span data-stu-id="0cf7a-102">ICorDebugManagedCallback2::CreateConnection Method</span></span>
<span data-ttu-id="0cf7a-103">Уведомляет отладчик о создании нового соединения.</span><span class="sxs-lookup"><span data-stu-id="0cf7a-103">Notifies the debugger that a new connection has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0cf7a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0cf7a-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId,  
    [in] WCHAR                *pConnName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0cf7a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0cf7a-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="0cf7a-106">окне Указатель на объект "ICorDebugProcess", представляющий процесс, в котором было создано соединение</span><span class="sxs-lookup"><span data-stu-id="0cf7a-106">[in] A pointer to an "ICorDebugProcess" object that represents the process in which the connection was created</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="0cf7a-107">окне Идентификатор нового соединения.</span><span class="sxs-lookup"><span data-stu-id="0cf7a-107">[in] The ID of the new connection.</span></span>  
  
 `pConnName`  
 <span data-ttu-id="0cf7a-108">окне Указатель на имя нового соединения.</span><span class="sxs-lookup"><span data-stu-id="0cf7a-108">[in] A pointer to the name of the new connection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0cf7a-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="0cf7a-109">Remarks</span></span>  
 <span data-ttu-id="0cf7a-110">Обратный вызов `CreateConnection` будет срабатывать в одном из следующих случаев.</span><span class="sxs-lookup"><span data-stu-id="0cf7a-110">A `CreateConnection` callback will be fired in either of the following cases:</span></span>  
  
- <span data-ttu-id="0cf7a-111">При присоединении отладчика к процессу, который содержит соединения.</span><span class="sxs-lookup"><span data-stu-id="0cf7a-111">When a debugger attaches to a process that contains connections.</span></span> <span data-ttu-id="0cf7a-112">В этом случае среда выполнения создаст и отправит событие `CreateConnection` и событие [ICorDebugManagedCallback2:: чанжеконнектион](icordebugmanagedcallback2-changeconnection-method.md) для каждого соединения в процессе.</span><span class="sxs-lookup"><span data-stu-id="0cf7a-112">In this case, the runtime will generate and dispatch a `CreateConnection` event and a [ICorDebugManagedCallback2::ChangeConnection](icordebugmanagedcallback2-changeconnection-method.md) event for each connection in the process.</span></span>  
  
- <span data-ttu-id="0cf7a-113">Когда узел вызывает [ICLRDebugManager:: бегинконнектион](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) в [API размещения](../../../../docs/framework/unmanaged-api/hosting/index.md).</span><span class="sxs-lookup"><span data-stu-id="0cf7a-113">When a host calls [ICLRDebugManager::BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) in the [Hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0cf7a-114">Требования</span><span class="sxs-lookup"><span data-stu-id="0cf7a-114">Requirements</span></span>  
 <span data-ttu-id="0cf7a-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0cf7a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0cf7a-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0cf7a-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0cf7a-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0cf7a-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0cf7a-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0cf7a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cf7a-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="0cf7a-119">See also</span></span>

- [<span data-ttu-id="0cf7a-120">Интерфейс ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="0cf7a-120">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="0cf7a-121">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="0cf7a-121">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)

---
title: "Метод ICorDebugManagedCallback::ExitProcess"
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
- ICorDebugManagedCallback.ExitProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::ExitProcess
helpviewer_keywords:
- ExitProcess method, ICorDebugManagedCallback interface [.NET Framework debugging]
- ICorDebugManagedCallback::ExitProcess method [.NET Framework debugging]
ms.assetid: 63a7d47a-0d54-4e29-9767-9f09feaa38b7
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7be74520fff65b113f54d82305a84dd183286876
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbackexitprocess-method"></a><span data-ttu-id="0fe0b-102">Метод ICorDebugManagedCallback::ExitProcess</span><span class="sxs-lookup"><span data-stu-id="0fe0b-102">ICorDebugManagedCallback::ExitProcess Method</span></span>
<span data-ttu-id="0fe0b-103">Уведомляет отладчик о том, что процесс завершен.</span><span class="sxs-lookup"><span data-stu-id="0fe0b-103">Notifies the debugger that a process has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fe0b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0fe0b-104">Syntax</span></span>  
  
```  
HRESULT ExitProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0fe0b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0fe0b-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="0fe0b-106">[in] Указатель на объект ICorDebugProcess, представляет собой процесс.</span><span class="sxs-lookup"><span data-stu-id="0fe0b-106">[in] A pointer to an ICorDebugProcess object that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0fe0b-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="0fe0b-107">Remarks</span></span>  
 <span data-ttu-id="0fe0b-108">Не удается продолжить выполнение после `ExitProcess` событий.</span><span class="sxs-lookup"><span data-stu-id="0fe0b-108">You cannot continue from an `ExitProcess` event.</span></span> <span data-ttu-id="0fe0b-109">Это событие вызывается асинхронно с другими событиями во время процесса появляется нужно остановить.</span><span class="sxs-lookup"><span data-stu-id="0fe0b-109">This event may fire asynchronously to other events while the process appears to be stopped.</span></span> <span data-ttu-id="0fe0b-110">Это может произойти, если при остановке, обычно вследствие внешних завершает процесс.</span><span class="sxs-lookup"><span data-stu-id="0fe0b-110">This can occur if the process terminates while stopped, usually due to some external force.</span></span>  
  
 <span data-ttu-id="0fe0b-111">Если обратный вызов управляемого уже обрабатывает общеязыковой среды выполнения (CLR), это событие будет отложено до после возвращения из этого обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="0fe0b-111">If the common language runtime (CLR) is already dispatching a managed callback, this event will be delayed until after that callback has returned.</span></span>  
  
 <span data-ttu-id="0fe0b-112">`ExitProcess` Событие является только событие выхода или выгрузки, которое гарантированно вызывается при завершении работы.</span><span class="sxs-lookup"><span data-stu-id="0fe0b-112">The `ExitProcess` event is the only exit/unload event that is guaranteed to get called on shutdown.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0fe0b-113">Требования</span><span class="sxs-lookup"><span data-stu-id="0fe0b-113">Requirements</span></span>  
 <span data-ttu-id="0fe0b-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0fe0b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0fe0b-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0fe0b-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0fe0b-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0fe0b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0fe0b-117">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0fe0b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fe0b-118">См. также</span><span class="sxs-lookup"><span data-stu-id="0fe0b-118">See Also</span></span>  
 [<span data-ttu-id="0fe0b-119">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="0fe0b-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)

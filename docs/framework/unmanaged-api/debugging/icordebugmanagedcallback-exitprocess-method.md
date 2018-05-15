---
title: Метод ICorDebugManagedCallback::ExitProcess
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 42330296defe90980dd431ce39765a549057b82a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugmanagedcallbackexitprocess-method"></a><span data-ttu-id="fcffd-102">Метод ICorDebugManagedCallback::ExitProcess</span><span class="sxs-lookup"><span data-stu-id="fcffd-102">ICorDebugManagedCallback::ExitProcess Method</span></span>
<span data-ttu-id="fcffd-103">Уведомляет отладчик о том, что процесс завершен.</span><span class="sxs-lookup"><span data-stu-id="fcffd-103">Notifies the debugger that a process has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcffd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fcffd-104">Syntax</span></span>  
  
```  
HRESULT ExitProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fcffd-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fcffd-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="fcffd-106">[in] Указатель на объект ICorDebugProcess, представляет собой процесс.</span><span class="sxs-lookup"><span data-stu-id="fcffd-106">[in] A pointer to an ICorDebugProcess object that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fcffd-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="fcffd-107">Remarks</span></span>  
 <span data-ttu-id="fcffd-108">Не удается продолжить выполнение после `ExitProcess` событий.</span><span class="sxs-lookup"><span data-stu-id="fcffd-108">You cannot continue from an `ExitProcess` event.</span></span> <span data-ttu-id="fcffd-109">Это событие вызывается асинхронно с другими событиями во время процесса появляется нужно остановить.</span><span class="sxs-lookup"><span data-stu-id="fcffd-109">This event may fire asynchronously to other events while the process appears to be stopped.</span></span> <span data-ttu-id="fcffd-110">Это может произойти, если при остановке, обычно вследствие внешних завершает процесс.</span><span class="sxs-lookup"><span data-stu-id="fcffd-110">This can occur if the process terminates while stopped, usually due to some external force.</span></span>  
  
 <span data-ttu-id="fcffd-111">Если обратный вызов управляемого уже обрабатывает общеязыковой среды выполнения (CLR), это событие будет отложено до после возвращения из этого обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="fcffd-111">If the common language runtime (CLR) is already dispatching a managed callback, this event will be delayed until after that callback has returned.</span></span>  
  
 <span data-ttu-id="fcffd-112">`ExitProcess` Событие является только событие выхода или выгрузки, которое гарантированно вызывается при завершении работы.</span><span class="sxs-lookup"><span data-stu-id="fcffd-112">The `ExitProcess` event is the only exit/unload event that is guaranteed to get called on shutdown.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fcffd-113">Требования</span><span class="sxs-lookup"><span data-stu-id="fcffd-113">Requirements</span></span>  
 <span data-ttu-id="fcffd-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fcffd-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fcffd-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fcffd-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fcffd-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fcffd-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fcffd-117">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fcffd-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcffd-118">См. также</span><span class="sxs-lookup"><span data-stu-id="fcffd-118">See Also</span></span>  
 [<span data-ttu-id="fcffd-119">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="fcffd-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)

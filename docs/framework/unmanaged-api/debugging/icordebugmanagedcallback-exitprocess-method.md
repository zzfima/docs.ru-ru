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
ms.openlocfilehash: b33b38b85bd5b8cfb3502e3fadcd739aac37b2dc
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57476377"
---
# <a name="icordebugmanagedcallbackexitprocess-method"></a><span data-ttu-id="de439-102">Метод ICorDebugManagedCallback::ExitProcess</span><span class="sxs-lookup"><span data-stu-id="de439-102">ICorDebugManagedCallback::ExitProcess Method</span></span>
<span data-ttu-id="de439-103">Уведомляет отладчик о том, что процесс завершен.</span><span class="sxs-lookup"><span data-stu-id="de439-103">Notifies the debugger that a process has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de439-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="de439-104">Syntax</span></span>  
  
```  
HRESULT ExitProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="de439-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="de439-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="de439-106">[in] Указатель на объект ICorDebugProcess, представляющий процесс.</span><span class="sxs-lookup"><span data-stu-id="de439-106">[in] A pointer to an ICorDebugProcess object that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="de439-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="de439-107">Remarks</span></span>  
 <span data-ttu-id="de439-108">Не удается продолжить выполнение после `ExitProcess` событий.</span><span class="sxs-lookup"><span data-stu-id="de439-108">You cannot continue from an `ExitProcess` event.</span></span> <span data-ttu-id="de439-109">Это событие вызывается асинхронно с другими событиями во время появится нужный процесс нужно остановить.</span><span class="sxs-lookup"><span data-stu-id="de439-109">This event may fire asynchronously to other events while the process appears to be stopped.</span></span> <span data-ttu-id="de439-110">Это может произойти, если процесс прерывается во время остановки, обычно вследствие внешних.</span><span class="sxs-lookup"><span data-stu-id="de439-110">This can occur if the process terminates while stopped, usually due to some external force.</span></span>  
  
 <span data-ttu-id="de439-111">Если среда CLR (CLR), который уже обслуживается управляемом обратном вызове, это событие будет отложено до после возвращения ответного вызова.</span><span class="sxs-lookup"><span data-stu-id="de439-111">If the common language runtime (CLR) is already dispatching a managed callback, this event will be delayed until after that callback has returned.</span></span>  
  
 <span data-ttu-id="de439-112">`ExitProcess` Это единственное событие завершения и выгрузки, гарантированно вызывается при завершении работы.</span><span class="sxs-lookup"><span data-stu-id="de439-112">The `ExitProcess` event is the only exit/unload event that is guaranteed to get called on shutdown.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de439-113">Требования</span><span class="sxs-lookup"><span data-stu-id="de439-113">Requirements</span></span>  
 <span data-ttu-id="de439-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de439-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de439-115">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="de439-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="de439-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="de439-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="de439-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de439-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de439-118">См. также</span><span class="sxs-lookup"><span data-stu-id="de439-118">See also</span></span>
- [<span data-ttu-id="de439-119">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="de439-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)

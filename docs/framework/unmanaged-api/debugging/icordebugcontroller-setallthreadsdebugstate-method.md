---
title: Метод ICorDebugController::SetAllThreadsDebugState
ms.date: 03/30/2017
api_name:
- ICorDebugController.SetAllThreadsDebugState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::SetAllThreadsDebugState
helpviewer_keywords:
- SetAllThreadsDebugState method [.NET Framework debugging]
- ICorDebugController::SetAllThreadsDebugState method [.NET Framework debugging]
ms.assetid: bdda4bd7-4743-4d58-a22b-8067e967db95
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0dffe95df75fafe293c225c513db7ff7896765fa
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57501777"
---
# <a name="icordebugcontrollersetallthreadsdebugstate-method"></a><span data-ttu-id="23aed-102">Метод ICorDebugController::SetAllThreadsDebugState</span><span class="sxs-lookup"><span data-stu-id="23aed-102">ICorDebugController::SetAllThreadsDebugState Method</span></span>
<span data-ttu-id="23aed-103">Задает состояние отладки все управляемые потоки в процессе.</span><span class="sxs-lookup"><span data-stu-id="23aed-103">Sets the debug state of all managed threads in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23aed-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="23aed-104">Syntax</span></span>  
  
```  
HRESULT SetAllThreadsDebugState (  
    [in] CorDebugThreadState  state,  
    [in] ICorDebugThread      *pExceptThisThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="23aed-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="23aed-105">Parameters</span></span>  
 `state`  
 <span data-ttu-id="23aed-106">[in] Значение перечисления «CorDebugThreadState», которое указывает состояние потока для отладки.</span><span class="sxs-lookup"><span data-stu-id="23aed-106">[in] A value of the "CorDebugThreadState" enumeration that specifies the state of the thread for debugging.</span></span>  
  
 `pExceptThisThread`  
 <span data-ttu-id="23aed-107">[in] Указатель на объект «ICorDebugThread», который представляет поток, который требуется исключить из параметра состояние отладки.</span><span class="sxs-lookup"><span data-stu-id="23aed-107">[in] A pointer to an "ICorDebugThread" object that represents a thread to be exempted from the debug state setting.</span></span> <span data-ttu-id="23aed-108">Если это значение равно null, ни один поток не исключен.</span><span class="sxs-lookup"><span data-stu-id="23aed-108">If this value is null, no thread is exempted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="23aed-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="23aed-109">Remarks</span></span>  
 <span data-ttu-id="23aed-110">`SetAllThreadsDebugState` Метод может повлиять на потоки, которые не видны через [метод EnumerateThreads](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md), поэтому потоки, которые были приостановлены с `SetAllThreadsDebugState` метод потребуется возобновления, с `SetAllThreadsDebugState` метод.</span><span class="sxs-lookup"><span data-stu-id="23aed-110">The `SetAllThreadsDebugState` method may affect threads that are not visible via [EnumerateThreads Method](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md), so threads that were suspended with the `SetAllThreadsDebugState` method will need to be resumed with the `SetAllThreadsDebugState` method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23aed-111">Требования</span><span class="sxs-lookup"><span data-stu-id="23aed-111">Requirements</span></span>  
 <span data-ttu-id="23aed-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23aed-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23aed-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="23aed-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="23aed-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="23aed-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="23aed-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23aed-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23aed-116">См. также</span><span class="sxs-lookup"><span data-stu-id="23aed-116">See also</span></span>


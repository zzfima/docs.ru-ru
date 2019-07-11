---
title: Метод ICorDebugController::Continue
ms.date: 03/30/2017
api_name:
- ICorDebugController.Continue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Continue
helpviewer_keywords:
- Continue method [.NET Framework debugging]
- ICorDebugController::Continue method [.NET Framework debugging]
ms.assetid: 8684cd06-ad3e-48ef-832e-15320e1f43a2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c3a4e98a7265bda288b20b1cee1a10ab11990e8e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67748883"
---
# <a name="icordebugcontrollercontinue-method"></a><span data-ttu-id="be6d7-102">Метод ICorDebugController::Continue</span><span class="sxs-lookup"><span data-stu-id="be6d7-102">ICorDebugController::Continue Method</span></span>
<span data-ttu-id="be6d7-103">Возобновляет выполнение управляемых потоков после вызова [метод Stop](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).</span><span class="sxs-lookup"><span data-stu-id="be6d7-103">Resumes execution of managed threads after a call to [Stop Method](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be6d7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="be6d7-104">Syntax</span></span>  
  
```cpp  
HRESULT Continue (  
    [in] BOOL fIsOutOfBand  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="be6d7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="be6d7-105">Parameters</span></span>  
 `fIsOutOfBand`  
 <span data-ttu-id="be6d7-106">[in] Значение `true` в событие каналу; в противном случае значение `false`.</span><span class="sxs-lookup"><span data-stu-id="be6d7-106">[in] Set to `true` if continuing from an out-of-band event; otherwise, set to `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="be6d7-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="be6d7-107">Remarks</span></span>  
 <span data-ttu-id="be6d7-108">`Continue` Продолжение процесса после вызова `ICorDebugController::Stop` метод.</span><span class="sxs-lookup"><span data-stu-id="be6d7-108">`Continue` continues the process after a call to the `ICorDebugController::Stop` method.</span></span>  
  
 <span data-ttu-id="be6d7-109">При выполнении отладки в смешанном режиме, не следует вызывать `Continue` на Win32 событий потоков, если не является продолжением-внешнее событие.</span><span class="sxs-lookup"><span data-stu-id="be6d7-109">When doing mixed-mode debugging, do not call `Continue` on the Win32 event thread unless you are continuing from an out-of-band event.</span></span>  
  
 <span data-ttu-id="be6d7-110">*События внутри диапазона* управляемое событие или обычное неуправляемое событие во время которого отладчик поддерживает взаимодействие с управляемым состоянием процесса.</span><span class="sxs-lookup"><span data-stu-id="be6d7-110">An *in-band event* is either a managed event or a normal unmanaged event during which the debugger supports interaction with the managed state of the process.</span></span> <span data-ttu-id="be6d7-111">В этом случае отладчик получает [ICorDebugUnmanagedCallback::DebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-debugevent-method.md) обратного вызова с его `fOutOfBand` параметру присвоить `false`.</span><span class="sxs-lookup"><span data-stu-id="be6d7-111">In this case, the debugger receives the [ICorDebugUnmanagedCallback::DebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-debugevent-method.md) callback with its `fOutOfBand` parameter set to `false`.</span></span>  
  
 <span data-ttu-id="be6d7-112">*-Внешнее событие* — это неуправляемых событий во время которого взаимодействие с управляемым состоянием процесса невозможна, пока процесс будет остановлен из-за события.</span><span class="sxs-lookup"><span data-stu-id="be6d7-112">An *out-of-band event* is an unmanaged event during which interaction with the managed state of the process is impossible while the process is stopped due to the event.</span></span> <span data-ttu-id="be6d7-113">В этом случае отладчик получает `ICorDebugUnmanagedCallback::DebugEvent` обратного вызова с его `fOutOfBand` параметру присвоить `true`.</span><span class="sxs-lookup"><span data-stu-id="be6d7-113">In this case, the debugger receives the `ICorDebugUnmanagedCallback::DebugEvent` callback with its `fOutOfBand` parameter set to `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be6d7-114">Требования</span><span class="sxs-lookup"><span data-stu-id="be6d7-114">Requirements</span></span>  
 <span data-ttu-id="be6d7-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be6d7-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be6d7-116">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="be6d7-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="be6d7-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="be6d7-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="be6d7-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be6d7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be6d7-119">См. также</span><span class="sxs-lookup"><span data-stu-id="be6d7-119">See also</span></span>

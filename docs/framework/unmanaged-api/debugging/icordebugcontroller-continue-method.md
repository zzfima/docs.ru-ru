---
title: "Метод ICorDebugController::Continue"
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e6a96145801aa8ef6482e30e9c00b763d2501f36
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcontrollercontinue-method"></a><span data-ttu-id="18eed-102">Метод ICorDebugController::Continue</span><span class="sxs-lookup"><span data-stu-id="18eed-102">ICorDebugController::Continue Method</span></span>
<span data-ttu-id="18eed-103">Возобновление выполнения управляемых потоков после вызова [метод Stop](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).</span><span class="sxs-lookup"><span data-stu-id="18eed-103">Resumes execution of managed threads after a call to [Stop Method](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18eed-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="18eed-104">Syntax</span></span>  
  
```  
HRESULT Continue (  
    [in] BOOL fIsOutOfBand  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="18eed-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="18eed-105">Parameters</span></span>  
 `fIsOutOfBand`  
 <span data-ttu-id="18eed-106">[in] Значение `true` в событие по каналу; в противном случае — значение `false`.</span><span class="sxs-lookup"><span data-stu-id="18eed-106">[in] Set to `true` if continuing from an out-of-band event; otherwise, set to `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="18eed-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="18eed-107">Remarks</span></span>  
 <span data-ttu-id="18eed-108">`Continue`Продолжение процесса после вызова `ICorDebugController::Stop` метод.</span><span class="sxs-lookup"><span data-stu-id="18eed-108">`Continue` continues the process after a call to the `ICorDebugController::Stop` method.</span></span>  
  
 <span data-ttu-id="18eed-109">При выполнении отладки в смешанном режиме, не следует вызывать `Continue` на Win32 событий потока, если необходимо продолжить из события по каналу.</span><span class="sxs-lookup"><span data-stu-id="18eed-109">When doing mixed-mode debugging, do not call `Continue` on the Win32 event thread unless you are continuing from an out-of-band event.</span></span>  
  
 <span data-ttu-id="18eed-110">*В противном случае* управляемое событие или обычное неуправляемое событие, во время которого отладчик поддерживает взаимодействие с управляемым состоянием процесса.</span><span class="sxs-lookup"><span data-stu-id="18eed-110">An *in-band event* is either a managed event or a normal unmanaged event during which the debugger supports interaction with the managed state of the process.</span></span> <span data-ttu-id="18eed-111">В этом случае отладчик получает [ICorDebugUnmanagedCallback::DebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-debugevent-method.md) обратного вызова с его `fOutOfBand` равным `false`.</span><span class="sxs-lookup"><span data-stu-id="18eed-111">In this case, the debugger receives the [ICorDebugUnmanagedCallback::DebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-debugevent-method.md) callback with its `fOutOfBand` parameter set to `false`.</span></span>  
  
 <span data-ttu-id="18eed-112">*Событий по каналу* неуправляемые событие во время которого взаимодействие с управляемым состоянием процесса невозможна, пока процесс остановлен из-за событие.</span><span class="sxs-lookup"><span data-stu-id="18eed-112">An *out-of-band event* is an unmanaged event during which interaction with the managed state of the process is impossible while the process is stopped due to the event.</span></span> <span data-ttu-id="18eed-113">В этом случае отладчик получает `ICorDebugUnmanagedCallback::DebugEvent` обратного вызова с его `fOutOfBand` равным `true`.</span><span class="sxs-lookup"><span data-stu-id="18eed-113">In this case, the debugger receives the `ICorDebugUnmanagedCallback::DebugEvent` callback with its `fOutOfBand` parameter set to `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18eed-114">Требования</span><span class="sxs-lookup"><span data-stu-id="18eed-114">Requirements</span></span>  
 <span data-ttu-id="18eed-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="18eed-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18eed-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="18eed-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="18eed-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="18eed-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="18eed-118">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18eed-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18eed-119">См. также</span><span class="sxs-lookup"><span data-stu-id="18eed-119">See Also</span></span>  
 

---
title: Интерфейс ICorDebugRuntimeUnwindableFrame
ms.date: 03/30/2017
api_name:
- ICorDebugUnwindableFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugUnwindableFrame
helpviewer_keywords:
- ICorDebugUnwindableFrame interface [.NET Framework debugging]
ms.assetid: cd6a3982-6ed3-4909-808d-a66055e813e0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f006085aba140264e2a2605adce39924dbe082e4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54568118"
---
# <a name="icordebugruntimeunwindableframe-interface"></a><span data-ttu-id="1f7c5-102">Интерфейс ICorDebugRuntimeUnwindableFrame</span><span class="sxs-lookup"><span data-stu-id="1f7c5-102">ICorDebugRuntimeUnwindableFrame Interface</span></span>
<span data-ttu-id="1f7c5-103">Предоставляет поддержку для неуправляемых методов, которым требуется среда CLR для раскручивания кадра.</span><span class="sxs-lookup"><span data-stu-id="1f7c5-103">Provides support for unmanaged methods that require the common language runtime (CLR) to unwind a frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1f7c5-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="1f7c5-104">Remarks</span></span>  
 <span data-ttu-id="1f7c5-105">`ICorDebugRuntimeUnwindableFrame` является специальной версией ICorDebugFrame интерфейса.</span><span class="sxs-lookup"><span data-stu-id="1f7c5-105">`ICorDebugRuntimeUnwindableFrame` is a specialized version of the ICorDebugFrame interface.</span></span> <span data-ttu-id="1f7c5-106">Он используется неуправляемых методов, которым требуется среда выполнения для раскручивания кадра текущего стека.</span><span class="sxs-lookup"><span data-stu-id="1f7c5-106">It is used by unmanaged methods that require the runtime to unwind a frame on the current stack.</span></span> <span data-ttu-id="1f7c5-107">Существующие соглашения по раскрутке не работают, так как они не используют JIT-скомпилированный код.</span><span class="sxs-lookup"><span data-stu-id="1f7c5-107">Existing unwinding conventions do not work, because they do not use JIT-compiled code.</span></span> <span data-ttu-id="1f7c5-108">Когда отладчик видит нераскручиваемых кадр, следует использовать [ICorDebugStackWalk::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md) способ очистки, но она проверку должен выполнять самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="1f7c5-108">When the debugger sees an unwindable frame, it should use the [ICorDebugStackWalk::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md) method to unwind it, but it should perform inspection itself.</span></span> <span data-ttu-id="1f7c5-109">Когда отладчик получает `ICorDebugRuntimeUnwindableFrame`, оно может вызвать [ICorDebugStackWalk::GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) метод для извлечения контекста фрейма.</span><span class="sxs-lookup"><span data-stu-id="1f7c5-109">When the debugger receives an `ICorDebugRuntimeUnwindableFrame`, it can call the [ICorDebugStackWalk::GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) method to retrieve the context of the frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f7c5-110">Требования</span><span class="sxs-lookup"><span data-stu-id="1f7c5-110">Requirements</span></span>  
 <span data-ttu-id="1f7c5-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1f7c5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f7c5-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1f7c5-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1f7c5-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1f7c5-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1f7c5-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f7c5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f7c5-115">См. также</span><span class="sxs-lookup"><span data-stu-id="1f7c5-115">See also</span></span>
- [<span data-ttu-id="1f7c5-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="1f7c5-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="1f7c5-117">Отладка</span><span class="sxs-lookup"><span data-stu-id="1f7c5-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)

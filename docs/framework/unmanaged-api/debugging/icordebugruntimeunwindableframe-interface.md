---
title: "Интерфейс ICorDebugRuntimeUnwindableFrame"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugUnwindableFrame
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugUnwindableFrame
helpviewer_keywords: ICorDebugUnwindableFrame interface [.NET Framework debugging]
ms.assetid: cd6a3982-6ed3-4909-808d-a66055e813e0
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 003bbab399a9ad0ffe2f1d761aea18ff71ba1834
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugruntimeunwindableframe-interface"></a><span data-ttu-id="6701c-102">Интерфейс ICorDebugRuntimeUnwindableFrame</span><span class="sxs-lookup"><span data-stu-id="6701c-102">ICorDebugRuntimeUnwindableFrame Interface</span></span>
<span data-ttu-id="6701c-103">Предоставляет поддержку для неуправляемых методов, которым требуется среда CLR для раскручивания кадра.</span><span class="sxs-lookup"><span data-stu-id="6701c-103">Provides support for unmanaged methods that require the common language runtime (CLR) to unwind a frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6701c-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="6701c-104">Remarks</span></span>  
 <span data-ttu-id="6701c-105">`ICorDebugRuntimeUnwindableFrame`является специальной версией оператора ICorDebugFrame-интерфейс.</span><span class="sxs-lookup"><span data-stu-id="6701c-105">`ICorDebugRuntimeUnwindableFrame` is a specialized version of the ICorDebugFrame interface.</span></span> <span data-ttu-id="6701c-106">Он используется неуправляемых методов, которым требуется среда выполнения для раскручивания кадра текущего стека.</span><span class="sxs-lookup"><span data-stu-id="6701c-106">It is used by unmanaged methods that require the runtime to unwind a frame on the current stack.</span></span> <span data-ttu-id="6701c-107">Существующие соглашения по раскрутке не работают, так как они не используют JIT-скомпилированный код.</span><span class="sxs-lookup"><span data-stu-id="6701c-107">Existing unwinding conventions do not work, because they do not use JIT-compiled code.</span></span> <span data-ttu-id="6701c-108">Когда отладчик видит удаляемых кадр, следует использовать [ICorDebugStackWalk::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md) метод, чтобы развернуть его, но его проверку должен выполнять самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="6701c-108">When the debugger sees an unwindable frame, it should use the [ICorDebugStackWalk::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md) method to unwind it, but it should perform inspection itself.</span></span> <span data-ttu-id="6701c-109">Когда отладчик получает `ICorDebugRuntimeUnwindableFrame`, он может вызвать [ICorDebugStackWalk::GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) метод для извлечения контекста кадра.</span><span class="sxs-lookup"><span data-stu-id="6701c-109">When the debugger receives an `ICorDebugRuntimeUnwindableFrame`, it can call the [ICorDebugStackWalk::GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) method to retrieve the context of the frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6701c-110">Требования</span><span class="sxs-lookup"><span data-stu-id="6701c-110">Requirements</span></span>  
 <span data-ttu-id="6701c-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6701c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6701c-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6701c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6701c-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6701c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6701c-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6701c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6701c-115">См. также</span><span class="sxs-lookup"><span data-stu-id="6701c-115">See Also</span></span>  
 [<span data-ttu-id="6701c-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="6701c-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="6701c-117">Отладка</span><span class="sxs-lookup"><span data-stu-id="6701c-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)

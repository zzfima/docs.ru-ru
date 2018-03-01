---
title: "Интерфейс ICorDebugStackWalk"
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
- ICorDebugStackWalk
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk
helpviewer_keywords:
- ICorDebugStackWalk interface [.NET Framework debugging]
ms.assetid: 16d695e8-975d-431b-8421-e9e6c3e3f476
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 018ed69e52efd21ca25029284c70f1c8493d877f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugstackwalk-interface"></a><span data-ttu-id="54220-102">Интерфейс ICorDebugStackWalk</span><span class="sxs-lookup"><span data-stu-id="54220-102">ICorDebugStackWalk Interface</span></span>
<span data-ttu-id="54220-103">Обеспечивает методы для получения управляемых методов или кадров в стеке потока.</span><span class="sxs-lookup"><span data-stu-id="54220-103">Provides methods for getting the managed methods, or frames, on a thread’s stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="54220-104">Методы</span><span class="sxs-lookup"><span data-stu-id="54220-104">Methods</span></span>  
  
|<span data-ttu-id="54220-105">Метод</span><span class="sxs-lookup"><span data-stu-id="54220-105">Method</span></span>|<span data-ttu-id="54220-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="54220-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="54220-107">Метод GetContext</span><span class="sxs-lookup"><span data-stu-id="54220-107">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md)|<span data-ttu-id="54220-108">Возвращает контекст для текущего кадра в `ICorDebugStackWalk` объекта.</span><span class="sxs-lookup"><span data-stu-id="54220-108">Returns the context for the current frame in the `ICorDebugStackWalk` object.</span></span>|  
|[<span data-ttu-id="54220-109">Метод SetContext</span><span class="sxs-lookup"><span data-stu-id="54220-109">SetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md)|<span data-ttu-id="54220-110">Наборы `ICorDebugStackWalk` текущего контекста объекта действительный контекст для потока.</span><span class="sxs-lookup"><span data-stu-id="54220-110">Sets the `ICorDebugStackWalk` object’s current context to a valid context for the thread.</span></span>|  
|[<span data-ttu-id="54220-111">Метод Next</span><span class="sxs-lookup"><span data-stu-id="54220-111">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md)|<span data-ttu-id="54220-112">Перемещает `ICorDebugStackWalk` объекта следующий кадр.</span><span class="sxs-lookup"><span data-stu-id="54220-112">Moves the `ICorDebugStackWalk` object to the next frame.</span></span>|  
|[<span data-ttu-id="54220-113">Метод GetFrame</span><span class="sxs-lookup"><span data-stu-id="54220-113">GetFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getframe-method.md)|<span data-ttu-id="54220-114">Получает текущий кадр `ICorDebugStackWalk` объекта.</span><span class="sxs-lookup"><span data-stu-id="54220-114">Gets the current frame in the `ICorDebugStackWalk` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="54220-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="54220-115">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="54220-116">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="54220-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54220-117">Требования</span><span class="sxs-lookup"><span data-stu-id="54220-117">Requirements</span></span>  
 <span data-ttu-id="54220-118">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54220-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54220-119">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="54220-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="54220-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="54220-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="54220-121">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54220-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54220-122">См. также</span><span class="sxs-lookup"><span data-stu-id="54220-122">See Also</span></span>  
 [<span data-ttu-id="54220-123">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="54220-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="54220-124">Отладка</span><span class="sxs-lookup"><span data-stu-id="54220-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)

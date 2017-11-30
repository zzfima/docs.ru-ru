---
title: "Интерфейс ICorDebugStackWalk"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStackWalk
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStackWalk
helpviewer_keywords: ICorDebugStackWalk interface [.NET Framework debugging]
ms.assetid: 16d695e8-975d-431b-8421-e9e6c3e3f476
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0c8a4421b716614081368755388bd2ab8d8fe22e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugstackwalk-interface"></a><span data-ttu-id="0818e-102">Интерфейс ICorDebugStackWalk</span><span class="sxs-lookup"><span data-stu-id="0818e-102">ICorDebugStackWalk Interface</span></span>
<span data-ttu-id="0818e-103">Обеспечивает методы для получения управляемых методов или кадров в стеке потока.</span><span class="sxs-lookup"><span data-stu-id="0818e-103">Provides methods for getting the managed methods, or frames, on a thread’s stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0818e-104">Методы</span><span class="sxs-lookup"><span data-stu-id="0818e-104">Methods</span></span>  
  
|<span data-ttu-id="0818e-105">Метод</span><span class="sxs-lookup"><span data-stu-id="0818e-105">Method</span></span>|<span data-ttu-id="0818e-106">Описание</span><span class="sxs-lookup"><span data-stu-id="0818e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0818e-107">Метод GetContext</span><span class="sxs-lookup"><span data-stu-id="0818e-107">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md)|<span data-ttu-id="0818e-108">Возвращает контекст для текущего кадра в `ICorDebugStackWalk` объекта.</span><span class="sxs-lookup"><span data-stu-id="0818e-108">Returns the context for the current frame in the `ICorDebugStackWalk` object.</span></span>|  
|[<span data-ttu-id="0818e-109">Метод SetContext</span><span class="sxs-lookup"><span data-stu-id="0818e-109">SetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md)|<span data-ttu-id="0818e-110">Наборы `ICorDebugStackWalk` текущего контекста объекта действительный контекст для потока.</span><span class="sxs-lookup"><span data-stu-id="0818e-110">Sets the `ICorDebugStackWalk` object’s current context to a valid context for the thread.</span></span>|  
|[<span data-ttu-id="0818e-111">Метод Next</span><span class="sxs-lookup"><span data-stu-id="0818e-111">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md)|<span data-ttu-id="0818e-112">Перемещает `ICorDebugStackWalk` объекта следующий кадр.</span><span class="sxs-lookup"><span data-stu-id="0818e-112">Moves the `ICorDebugStackWalk` object to the next frame.</span></span>|  
|[<span data-ttu-id="0818e-113">Метод GetFrame</span><span class="sxs-lookup"><span data-stu-id="0818e-113">GetFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getframe-method.md)|<span data-ttu-id="0818e-114">Получает текущий кадр `ICorDebugStackWalk` объекта.</span><span class="sxs-lookup"><span data-stu-id="0818e-114">Gets the current frame in the `ICorDebugStackWalk` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0818e-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="0818e-115">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0818e-116">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="0818e-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0818e-117">Требования</span><span class="sxs-lookup"><span data-stu-id="0818e-117">Requirements</span></span>  
 <span data-ttu-id="0818e-118">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0818e-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0818e-119">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0818e-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0818e-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0818e-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0818e-121">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0818e-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0818e-122">См. также</span><span class="sxs-lookup"><span data-stu-id="0818e-122">See Also</span></span>  
 [<span data-ttu-id="0818e-123">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="0818e-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="0818e-124">Отладка</span><span class="sxs-lookup"><span data-stu-id="0818e-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)

---
title: Интерфейс ICorDebugStackWalk
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e33e9be112a6a10f89b88005496ce2e63dff2d54
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59080687"
---
# <a name="icordebugstackwalk-interface"></a><span data-ttu-id="21f49-102">Интерфейс ICorDebugStackWalk</span><span class="sxs-lookup"><span data-stu-id="21f49-102">ICorDebugStackWalk Interface</span></span>
<span data-ttu-id="21f49-103">Обеспечивает методы для получения управляемых методов или кадров в стеке потока.</span><span class="sxs-lookup"><span data-stu-id="21f49-103">Provides methods for getting the managed methods, or frames, on a thread’s stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="21f49-104">Методы</span><span class="sxs-lookup"><span data-stu-id="21f49-104">Methods</span></span>  
  
|<span data-ttu-id="21f49-105">Метод</span><span class="sxs-lookup"><span data-stu-id="21f49-105">Method</span></span>|<span data-ttu-id="21f49-106">Описание</span><span class="sxs-lookup"><span data-stu-id="21f49-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="21f49-107">Метод GetContext</span><span class="sxs-lookup"><span data-stu-id="21f49-107">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md)|<span data-ttu-id="21f49-108">Возвращает контекст для текущего кадра в `ICorDebugStackWalk` объекта.</span><span class="sxs-lookup"><span data-stu-id="21f49-108">Returns the context for the current frame in the `ICorDebugStackWalk` object.</span></span>|  
|[<span data-ttu-id="21f49-109">Метод SetContext</span><span class="sxs-lookup"><span data-stu-id="21f49-109">SetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md)|<span data-ttu-id="21f49-110">Наборы `ICorDebugStackWalk` текущего контекста объекта для допустимого контекста потока.</span><span class="sxs-lookup"><span data-stu-id="21f49-110">Sets the `ICorDebugStackWalk` object’s current context to a valid context for the thread.</span></span>|  
|[<span data-ttu-id="21f49-111">Метод Next</span><span class="sxs-lookup"><span data-stu-id="21f49-111">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md)|<span data-ttu-id="21f49-112">Перемещает `ICorDebugStackWalk` объекта следующий кадр.</span><span class="sxs-lookup"><span data-stu-id="21f49-112">Moves the `ICorDebugStackWalk` object to the next frame.</span></span>|  
|[<span data-ttu-id="21f49-113">Метод GetFrame</span><span class="sxs-lookup"><span data-stu-id="21f49-113">GetFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getframe-method.md)|<span data-ttu-id="21f49-114">Получает текущий кадр `ICorDebugStackWalk` объекта.</span><span class="sxs-lookup"><span data-stu-id="21f49-114">Gets the current frame in the `ICorDebugStackWalk` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="21f49-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="21f49-115">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="21f49-116">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="21f49-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21f49-117">Требования</span><span class="sxs-lookup"><span data-stu-id="21f49-117">Requirements</span></span>  
 <span data-ttu-id="21f49-118">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21f49-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21f49-119">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="21f49-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="21f49-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="21f49-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="21f49-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21f49-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21f49-122">См. также</span><span class="sxs-lookup"><span data-stu-id="21f49-122">See also</span></span>

- [<span data-ttu-id="21f49-123">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="21f49-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="21f49-124">Отладка</span><span class="sxs-lookup"><span data-stu-id="21f49-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)

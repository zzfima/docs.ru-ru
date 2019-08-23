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
ms.openlocfilehash: 06ce2da435df9458ca59d76fa426becbede2e619
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69959678"
---
# <a name="icordebugstackwalk-interface"></a><span data-ttu-id="f8c61-102">Интерфейс ICorDebugStackWalk</span><span class="sxs-lookup"><span data-stu-id="f8c61-102">ICorDebugStackWalk Interface</span></span>
<span data-ttu-id="f8c61-103">Обеспечивает методы для получения управляемых методов или кадров в стеке потока.</span><span class="sxs-lookup"><span data-stu-id="f8c61-103">Provides methods for getting the managed methods, or frames, on a thread’s stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f8c61-104">Методы</span><span class="sxs-lookup"><span data-stu-id="f8c61-104">Methods</span></span>  
  
|<span data-ttu-id="f8c61-105">Метод</span><span class="sxs-lookup"><span data-stu-id="f8c61-105">Method</span></span>|<span data-ttu-id="f8c61-106">Описание</span><span class="sxs-lookup"><span data-stu-id="f8c61-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f8c61-107">Метод GetContext</span><span class="sxs-lookup"><span data-stu-id="f8c61-107">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md)|<span data-ttu-id="f8c61-108">Возвращает контекст для текущего кадра в `ICorDebugStackWalk` объекте.</span><span class="sxs-lookup"><span data-stu-id="f8c61-108">Returns the context for the current frame in the `ICorDebugStackWalk` object.</span></span>|  
|[<span data-ttu-id="f8c61-109">Метод SetContext</span><span class="sxs-lookup"><span data-stu-id="f8c61-109">SetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md)|<span data-ttu-id="f8c61-110">Задает для текущего контекста объектадопустимыйконтекстдляпотока.`ICorDebugStackWalk`</span><span class="sxs-lookup"><span data-stu-id="f8c61-110">Sets the `ICorDebugStackWalk` object’s current context to a valid context for the thread.</span></span>|  
|[<span data-ttu-id="f8c61-111">Метод Next</span><span class="sxs-lookup"><span data-stu-id="f8c61-111">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md)|<span data-ttu-id="f8c61-112">Перемещает `ICorDebugStackWalk` объект на следующий кадр.</span><span class="sxs-lookup"><span data-stu-id="f8c61-112">Moves the `ICorDebugStackWalk` object to the next frame.</span></span>|  
|[<span data-ttu-id="f8c61-113">Метод GetFrame</span><span class="sxs-lookup"><span data-stu-id="f8c61-113">GetFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getframe-method.md)|<span data-ttu-id="f8c61-114">Возвращает текущий кадр в `ICorDebugStackWalk` объекте.</span><span class="sxs-lookup"><span data-stu-id="f8c61-114">Gets the current frame in the `ICorDebugStackWalk` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f8c61-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="f8c61-115">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f8c61-116">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="f8c61-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8c61-117">Требования</span><span class="sxs-lookup"><span data-stu-id="f8c61-117">Requirements</span></span>  
 <span data-ttu-id="f8c61-118">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8c61-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8c61-119">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="f8c61-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f8c61-120">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="f8c61-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f8c61-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8c61-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8c61-122">См. также</span><span class="sxs-lookup"><span data-stu-id="f8c61-122">See also</span></span>

- [<span data-ttu-id="f8c61-123">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="f8c61-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="f8c61-124">Отладка</span><span class="sxs-lookup"><span data-stu-id="f8c61-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)

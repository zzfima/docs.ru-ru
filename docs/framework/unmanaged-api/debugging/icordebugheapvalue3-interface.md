---
title: Интерфейс ICorDebugHeapValue3
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue3
helpviewer_keywords:
- ICorDebugHeapValue3 interface [.NET Framework debugging]
ms.assetid: 9c421bb0-e647-4b2d-a986-f3d578cc7f20
topic_type:
- apiref
ms.openlocfilehash: b062faffc22e444bd4d3b4a0c67f2a08d7af3560
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131106"
---
# <a name="icordebugheapvalue3-interface"></a><span data-ttu-id="163e6-102">Интерфейс ICorDebugHeapValue3</span><span class="sxs-lookup"><span data-stu-id="163e6-102">ICorDebugHeapValue3 Interface</span></span>
<span data-ttu-id="163e6-103">Предоставляет свойства блокировки монитора объектов.</span><span class="sxs-lookup"><span data-stu-id="163e6-103">Exposes the monitor lock properties of objects.</span></span> <span data-ttu-id="163e6-104">Этот интерфейс расширяет интерфейсы ICorDebugHeapValue и ICorDebugHeapValue2.</span><span class="sxs-lookup"><span data-stu-id="163e6-104">This interface extends the ICorDebugHeapValue and ICorDebugHeapValue2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="163e6-105">Методы</span><span class="sxs-lookup"><span data-stu-id="163e6-105">Methods</span></span>  
  
|<span data-ttu-id="163e6-106">Метод</span><span class="sxs-lookup"><span data-stu-id="163e6-106">Method</span></span>|<span data-ttu-id="163e6-107">Описание</span><span class="sxs-lookup"><span data-stu-id="163e6-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="163e6-108">Метод GetThreadOwningMonitorLock</span><span class="sxs-lookup"><span data-stu-id="163e6-108">GetThreadOwningMonitorLock Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-getthreadowningmonitorlock-method.md)|<span data-ttu-id="163e6-109">Возвращает управляемый поток, которому принадлежит блокировка монитора для этого объекта.</span><span class="sxs-lookup"><span data-stu-id="163e6-109">Returns the managed thread that owns the monitor lock on this object.</span></span>|  
|[<span data-ttu-id="163e6-110">Метод GetMonitorEventWaitList</span><span class="sxs-lookup"><span data-stu-id="163e6-110">GetMonitorEventWaitList Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-getmonitoreventwaitlist-method.md)|<span data-ttu-id="163e6-111">Предоставляет упорядоченный список потоков, поставленных в очередь на событие, связанное с блокировкой монитора.</span><span class="sxs-lookup"><span data-stu-id="163e6-111">Provides an ordered list of threads that are queued on the event that is associated with a monitor lock.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="163e6-112">Заметки</span><span class="sxs-lookup"><span data-stu-id="163e6-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="163e6-113">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="163e6-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="163e6-114">Требования</span><span class="sxs-lookup"><span data-stu-id="163e6-114">Requirements</span></span>  
 <span data-ttu-id="163e6-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="163e6-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="163e6-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="163e6-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="163e6-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="163e6-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="163e6-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="163e6-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="163e6-119">См. также</span><span class="sxs-lookup"><span data-stu-id="163e6-119">See also</span></span>

- [<span data-ttu-id="163e6-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="163e6-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="163e6-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="163e6-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)

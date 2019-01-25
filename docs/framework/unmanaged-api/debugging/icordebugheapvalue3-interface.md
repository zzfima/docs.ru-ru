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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 08a9bc8aa4aa70ad6b01c58abccd145ae43d8a52
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54568302"
---
# <a name="icordebugheapvalue3-interface"></a><span data-ttu-id="5b061-102">Интерфейс ICorDebugHeapValue3</span><span class="sxs-lookup"><span data-stu-id="5b061-102">ICorDebugHeapValue3 Interface</span></span>
<span data-ttu-id="5b061-103">Предоставляет свойства блокировки монитора объектов.</span><span class="sxs-lookup"><span data-stu-id="5b061-103">Exposes the monitor lock properties of objects.</span></span> <span data-ttu-id="5b061-104">Этот интерфейс расширяет интерфейс ICorDebugHeapValue и ICorDebugHeapValue2.</span><span class="sxs-lookup"><span data-stu-id="5b061-104">This interface extends the ICorDebugHeapValue and ICorDebugHeapValue2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5b061-105">Методы</span><span class="sxs-lookup"><span data-stu-id="5b061-105">Methods</span></span>  
  
|<span data-ttu-id="5b061-106">Метод</span><span class="sxs-lookup"><span data-stu-id="5b061-106">Method</span></span>|<span data-ttu-id="5b061-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="5b061-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5b061-108">Метод GetThreadOwningMonitorLock</span><span class="sxs-lookup"><span data-stu-id="5b061-108">GetThreadOwningMonitorLock Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-getthreadowningmonitorlock-method.md)|<span data-ttu-id="5b061-109">Возвращает управляемый поток, которому принадлежит блокировка монитора для этого объекта.</span><span class="sxs-lookup"><span data-stu-id="5b061-109">Returns the managed thread that owns the monitor lock on this object.</span></span>|  
|[<span data-ttu-id="5b061-110">Метод GetMonitorEventWaitList</span><span class="sxs-lookup"><span data-stu-id="5b061-110">GetMonitorEventWaitList Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-getmonitoreventwaitlist-method.md)|<span data-ttu-id="5b061-111">Предоставляет упорядоченный список потоков, которые поставлены в очередь на события, связанного с блокировкой монитора.</span><span class="sxs-lookup"><span data-stu-id="5b061-111">Provides an ordered list of threads that are queued on the event that is associated with a monitor lock.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5b061-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="5b061-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5b061-113">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="5b061-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b061-114">Требования</span><span class="sxs-lookup"><span data-stu-id="5b061-114">Requirements</span></span>  
 <span data-ttu-id="5b061-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b061-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b061-116">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5b061-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5b061-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5b061-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5b061-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b061-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b061-119">См. также</span><span class="sxs-lookup"><span data-stu-id="5b061-119">See also</span></span>
- [<span data-ttu-id="5b061-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="5b061-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="5b061-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="5b061-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)

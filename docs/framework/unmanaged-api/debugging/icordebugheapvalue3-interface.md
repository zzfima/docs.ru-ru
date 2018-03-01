---
title: "Интерфейс ICorDebugHeapValue3"
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c7110ea2e39411d65d70ea14992959cdddc1d3bb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugheapvalue3-interface"></a><span data-ttu-id="a31a2-102">Интерфейс ICorDebugHeapValue3</span><span class="sxs-lookup"><span data-stu-id="a31a2-102">ICorDebugHeapValue3 Interface</span></span>
<span data-ttu-id="a31a2-103">Предоставляет свойства блокировки монитора объектов.</span><span class="sxs-lookup"><span data-stu-id="a31a2-103">Exposes the monitor lock properties of objects.</span></span> <span data-ttu-id="a31a2-104">Этот интерфейс расширяет интерфейс ICorDebugHeapValue и ICorDebugHeapValue2.</span><span class="sxs-lookup"><span data-stu-id="a31a2-104">This interface extends the ICorDebugHeapValue and ICorDebugHeapValue2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a31a2-105">Методы</span><span class="sxs-lookup"><span data-stu-id="a31a2-105">Methods</span></span>  
  
|<span data-ttu-id="a31a2-106">Метод</span><span class="sxs-lookup"><span data-stu-id="a31a2-106">Method</span></span>|<span data-ttu-id="a31a2-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="a31a2-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a31a2-108">Метод GetThreadOwningMonitorLock</span><span class="sxs-lookup"><span data-stu-id="a31a2-108">GetThreadOwningMonitorLock Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-getthreadowningmonitorlock-method.md)|<span data-ttu-id="a31a2-109">Возвращает управляемый поток, который владеет блокировкой монитора на этот объект.</span><span class="sxs-lookup"><span data-stu-id="a31a2-109">Returns the managed thread that owns the monitor lock on this object.</span></span>|  
|[<span data-ttu-id="a31a2-110">Метод GetMonitorEventWaitList</span><span class="sxs-lookup"><span data-stu-id="a31a2-110">GetMonitorEventWaitList Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-getmonitoreventwaitlist-method.md)|<span data-ttu-id="a31a2-111">Предоставляет упорядоченный список потоков, которые находятся в очереди на события, связанного с блокировкой монитора.</span><span class="sxs-lookup"><span data-stu-id="a31a2-111">Provides an ordered list of threads that are queued on the event that is associated with a monitor lock.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a31a2-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="a31a2-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a31a2-113">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="a31a2-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a31a2-114">Требования</span><span class="sxs-lookup"><span data-stu-id="a31a2-114">Requirements</span></span>  
 <span data-ttu-id="a31a2-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a31a2-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a31a2-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a31a2-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a31a2-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a31a2-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a31a2-118">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a31a2-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a31a2-119">См. также</span><span class="sxs-lookup"><span data-stu-id="a31a2-119">See Also</span></span>  
 [<span data-ttu-id="a31a2-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="a31a2-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="a31a2-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="a31a2-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)

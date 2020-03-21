---
title: Интерфейс ICorProfilerInfo10
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 4c5d553744008734037975d6e63e1b07b89cf886
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175074"
---
# <a name="icorprofilerinfo10-interface"></a><span data-ttu-id="a44a7-102">Интерфейс ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="a44a7-102">ICorProfilerInfo10 Interface</span></span>

<span data-ttu-id="a44a7-103">Подкласс [ICorProfilerInfo9,](icorprofilerinfo9-interface.md) который предоставляет методы для изменения функции IL, информации запроса из времени выполнения, а также приостановить и возобновить время выполнения.</span><span class="sxs-lookup"><span data-stu-id="a44a7-103">A subclass of [ICorProfilerInfo9](icorprofilerinfo9-interface.md) that provides methods to modify function IL, query information from the runtime, and suspend and resume the runtime.</span></span>

## <a name="methods"></a><span data-ttu-id="a44a7-104">Методы</span><span class="sxs-lookup"><span data-stu-id="a44a7-104">Methods</span></span>  

| <span data-ttu-id="a44a7-105">Метод</span><span class="sxs-lookup"><span data-stu-id="a44a7-105">Method</span></span>|<span data-ttu-id="a44a7-106">Описание</span><span class="sxs-lookup"><span data-stu-id="a44a7-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="a44a7-107">Метод EnumerateObjectReferences</span><span class="sxs-lookup"><span data-stu-id="a44a7-107">EnumerateObjectReferences Method</span></span>](icorprofilerinfo10-enumerateobjectreferences-method.md)|<span data-ttu-id="a44a7-108">С учетом ObjectID, обратный вызов и clientData перечисляет ссылку на каждый объект (если таковой имеется).</span><span class="sxs-lookup"><span data-stu-id="a44a7-108">Given an ObjectID, callback and clientData, enumerates each object reference (if any).</span></span> |
|[<span data-ttu-id="a44a7-109">Метод IsFrozenObject</span><span class="sxs-lookup"><span data-stu-id="a44a7-109">IsFrozenObject Method</span></span>](icorprofilerinfo10-isfrozenobject-method.md)|<span data-ttu-id="a44a7-110">Учитывая ObjectID, определяет, находится ли объект в сегменте только для чтения.</span><span class="sxs-lookup"><span data-stu-id="a44a7-110">Given an ObjectID, determines whether the object is in a read-only segment.</span></span> |
|[<span data-ttu-id="a44a7-111">Метод GetLOHObjectSizeThreshold</span><span class="sxs-lookup"><span data-stu-id="a44a7-111">GetLOHObjectSizeThreshold Method</span></span>](icorprofilerinfo10-getlohobjectsizethreshold-method.md)|<span data-ttu-id="a44a7-112">Получает значение настроенного порога LOH.</span><span class="sxs-lookup"><span data-stu-id="a44a7-112">Gets the value of the configured LOH threshold.</span></span> |
|[<span data-ttu-id="a44a7-113">Метод RequestReJITWithInliners</span><span class="sxs-lookup"><span data-stu-id="a44a7-113">RequestReJITWithInliners Method</span></span>](icorprofilerinfo10-requestrejitwithinliners-method.md)| <span data-ttu-id="a44a7-114">Перекладывает запрошенные методы, а также любые inliners из запрошенных методов.</span><span class="sxs-lookup"><span data-stu-id="a44a7-114">ReJITs the methods requested, as well as any inliners of the methods requested.</span></span>  |
|[<span data-ttu-id="a44a7-115">Метод SuspendRuntime</span><span class="sxs-lookup"><span data-stu-id="a44a7-115">SuspendRuntime Method</span></span>](icorprofilerinfo10-suspendruntime-method.md)| <span data-ttu-id="a44a7-116">Приостанавливает время выполнения без выполнения GC.</span><span class="sxs-lookup"><span data-stu-id="a44a7-116">Suspends the runtime without performing a GC.</span></span> |
|[<span data-ttu-id="a44a7-117">Метод ResumeRuntime</span><span class="sxs-lookup"><span data-stu-id="a44a7-117">ResumeRuntime Method</span></span>](icorprofilerinfo10-resumeruntime-method.md)| <span data-ttu-id="a44a7-118">Возобновляет время выполнения без выполнения GC.</span><span class="sxs-lookup"><span data-stu-id="a44a7-118">Resumes the runtime without performing a GC.</span></span> |

## <a name="requirements"></a><span data-ttu-id="a44a7-119">Требования</span><span class="sxs-lookup"><span data-stu-id="a44a7-119">Requirements</span></span>  
<span data-ttu-id="a44a7-120">**Платформы:** Смотрите [операционные системы, поддерживаемые .NET Core.](../../../core/install/dependencies.md?pivots=os-windows)</span><span class="sxs-lookup"><span data-stu-id="a44a7-120">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?pivots=os-windows).</span></span>  
<span data-ttu-id="a44a7-121">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a44a7-121">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="a44a7-122">**Версии .NET:**[!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a44a7-122">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="a44a7-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a44a7-123">See also</span></span>

- [<span data-ttu-id="a44a7-124">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="a44a7-124">Profiling Interfaces</span></span>](profiling-interfaces.md)

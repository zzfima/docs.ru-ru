---
title: Интерфейс ICorProfilerInfo10
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 496959ecac5b16f1faa138aec90c5194d15cb105
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2019
ms.locfileid: "68974014"
---
# <a name="icorprofilerinfo10-interface"></a><span data-ttu-id="c98ed-102">Интерфейс ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="c98ed-102">ICorProfilerInfo10 Interface</span></span>

<span data-ttu-id="c98ed-103">Подкласс [ICorProfilerInfo9](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-interface.md) , предоставляющий методы для изменения Il функции, запроса сведений из среды выполнения, а также приостановки и возобновления работы среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="c98ed-103">A subclass of [ICorProfilerInfo9](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-interface.md) that provides methods to modify function IL, query information from the runtime, and suspend and resume the runtime.</span></span>

## <a name="methods"></a><span data-ttu-id="c98ed-104">Методы</span><span class="sxs-lookup"><span data-stu-id="c98ed-104">Methods</span></span>  

| <span data-ttu-id="c98ed-105">Метод</span><span class="sxs-lookup"><span data-stu-id="c98ed-105">Method</span></span>|<span data-ttu-id="c98ed-106">Описание</span><span class="sxs-lookup"><span data-stu-id="c98ed-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="c98ed-107">Метод Енумератеобжектреференцес</span><span class="sxs-lookup"><span data-stu-id="c98ed-107">EnumerateObjectReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-enumerateobjectreferences-method.md)|<span data-ttu-id="c98ed-108">При наличии ObjectID, callback и Клиентдата перечисляет ссылки на все объекты (если таковые имеются).</span><span class="sxs-lookup"><span data-stu-id="c98ed-108">Given an ObjectID, callback and clientData, enumerates each object reference (if any).</span></span> |
|[<span data-ttu-id="c98ed-109">Метод Исфрозенобжект</span><span class="sxs-lookup"><span data-stu-id="c98ed-109">IsFrozenObject Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-isfrozenobject-method.md)|<span data-ttu-id="c98ed-110">Определяет, находится ли объект в сегменте, доступном только для чтения.</span><span class="sxs-lookup"><span data-stu-id="c98ed-110">Given an ObjectID, determines whether the object is in a read-only segment.</span></span> |
|[<span data-ttu-id="c98ed-111">Метод Жетлохобжектсизесрешолд</span><span class="sxs-lookup"><span data-stu-id="c98ed-111">GetLOHObjectSizeThreshold Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-getlohobjectsizethreshold-method.md)|<span data-ttu-id="c98ed-112">Возвращает значение заданного порога LOH.</span><span class="sxs-lookup"><span data-stu-id="c98ed-112">Gets the value of the configured LOH threshold.</span></span> |
|[<span data-ttu-id="c98ed-113">Метод Рекуестрежитвисинлинерс</span><span class="sxs-lookup"><span data-stu-id="c98ed-113">RequestReJITWithInliners Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-requestrejitwithinliners-method.md)| <span data-ttu-id="c98ed-114">Режитс запрошенные методы, а также любые запрашиваются методы.</span><span class="sxs-lookup"><span data-stu-id="c98ed-114">ReJITs the methods requested, as well as any inliners of the methods requested.</span></span>  |
|[<span data-ttu-id="c98ed-115">Метод Суспендрунтиме</span><span class="sxs-lookup"><span data-stu-id="c98ed-115">SuspendRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-suspendruntime-method.md)| <span data-ttu-id="c98ed-116">Приостанавливает выполнение среды выполнения без выполнения сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="c98ed-116">Suspends the runtime without performing a GC.</span></span> |
|[<span data-ttu-id="c98ed-117">Метод Ресумерунтиме</span><span class="sxs-lookup"><span data-stu-id="c98ed-117">ResumeRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-resumeruntime-method.md)| <span data-ttu-id="c98ed-118">Возобновляет работу среды выполнения без выполнения сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="c98ed-118">Resumes the runtime without performing a GC.</span></span> |

## <a name="requirements"></a><span data-ttu-id="c98ed-119">Требования</span><span class="sxs-lookup"><span data-stu-id="c98ed-119">Requirements</span></span>  
<span data-ttu-id="c98ed-120">**Платформ** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span><span class="sxs-lookup"><span data-stu-id="c98ed-120">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>  
<span data-ttu-id="c98ed-121">**Заголовок.** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="c98ed-121">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="c98ed-122">**Версии .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c98ed-122">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span> 
## <a name="see-also"></a><span data-ttu-id="c98ed-123">См. также</span><span class="sxs-lookup"><span data-stu-id="c98ed-123">See also</span></span>
- [<span data-ttu-id="c98ed-124">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="c98ed-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)

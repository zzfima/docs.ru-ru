---
title: Интерфейс ICorProfilerInfo10
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 06cce79fbb2b2eb143e77e3c6fda194e47d4f4f3
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928801"
---
# <a name="icorprofilerinfo10-interface"></a><span data-ttu-id="a12bb-102">Интерфейс ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="a12bb-102">ICorProfilerInfo10 Interface</span></span>

<span data-ttu-id="a12bb-103">Подкласс [ICorProfilerInfo9](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-interface.md) , предоставляющий методы для изменения Il функции, запроса сведений из среды выполнения, а также приостановки и возобновления работы среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="a12bb-103">A subclass of [ICorProfilerInfo9](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-interface.md) that provides methods to modify function IL, query information from the runtime, and suspend and resume the runtime.</span></span>

## <a name="methods"></a><span data-ttu-id="a12bb-104">Методы</span><span class="sxs-lookup"><span data-stu-id="a12bb-104">Methods</span></span>  

| <span data-ttu-id="a12bb-105">Метод</span><span class="sxs-lookup"><span data-stu-id="a12bb-105">Method</span></span>|<span data-ttu-id="a12bb-106">Описание</span><span class="sxs-lookup"><span data-stu-id="a12bb-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="a12bb-107">Метод Енумератеобжектреференцес</span><span class="sxs-lookup"><span data-stu-id="a12bb-107">EnumerateObjectReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-enumerateobjectreferences-method.md)|<span data-ttu-id="a12bb-108">При наличии ObjectID, callback и Клиентдата перечисляет ссылки на все объекты (если таковые имеются).</span><span class="sxs-lookup"><span data-stu-id="a12bb-108">Given an ObjectID, callback and clientData, enumerates each object reference (if any).</span></span> |
|[<span data-ttu-id="a12bb-109">Метод Исфрозенобжект</span><span class="sxs-lookup"><span data-stu-id="a12bb-109">IsFrozenObject Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-isfrozenobject-method.md)|<span data-ttu-id="a12bb-110">Определяет, находится ли объект в сегменте, доступном только для чтения.</span><span class="sxs-lookup"><span data-stu-id="a12bb-110">Given an ObjectID, determines whether the object is in a read-only segment.</span></span> |
|[<span data-ttu-id="a12bb-111">Метод Жетлохобжектсизесрешолд</span><span class="sxs-lookup"><span data-stu-id="a12bb-111">GetLOHObjectSizeThreshold Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-getlohobjectsizethreshold-method.md)|<span data-ttu-id="a12bb-112">Возвращает значение заданного порога LOH.</span><span class="sxs-lookup"><span data-stu-id="a12bb-112">Gets the value of the configured LOH threshold.</span></span> |
|[<span data-ttu-id="a12bb-113">Метод Рекуестрежитвисинлинерс</span><span class="sxs-lookup"><span data-stu-id="a12bb-113">RequestReJITWithInliners Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-requestrejitwithinliners-method.md)| <span data-ttu-id="a12bb-114">Режитс запрошенные методы, а также любые запрашиваются методы.</span><span class="sxs-lookup"><span data-stu-id="a12bb-114">ReJITs the methods requested, as well as any inliners of the methods requested.</span></span>  |
|[<span data-ttu-id="a12bb-115">Метод Суспендрунтиме</span><span class="sxs-lookup"><span data-stu-id="a12bb-115">SuspendRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-suspendruntime-method.md)| <span data-ttu-id="a12bb-116">Приостанавливает выполнение среды выполнения без выполнения сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="a12bb-116">Suspends the runtime without performing a GC.</span></span> |
|[<span data-ttu-id="a12bb-117">Метод Ресумерунтиме</span><span class="sxs-lookup"><span data-stu-id="a12bb-117">ResumeRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-resumeruntime-method.md)| <span data-ttu-id="a12bb-118">Возобновляет работу среды выполнения без выполнения сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="a12bb-118">Resumes the runtime without performing a GC.</span></span> |

## <a name="requirements"></a><span data-ttu-id="a12bb-119">Требования</span><span class="sxs-lookup"><span data-stu-id="a12bb-119">Requirements</span></span>  
<span data-ttu-id="a12bb-120">**Платформ** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span><span class="sxs-lookup"><span data-stu-id="a12bb-120">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>  
<span data-ttu-id="a12bb-121">**Заголовок.** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="a12bb-121">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="a12bb-122">**Версии .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a12bb-122">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span> 

## <a name="see-also"></a><span data-ttu-id="a12bb-123">См. также</span><span class="sxs-lookup"><span data-stu-id="a12bb-123">See also</span></span>

- [<span data-ttu-id="a12bb-124">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="a12bb-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)

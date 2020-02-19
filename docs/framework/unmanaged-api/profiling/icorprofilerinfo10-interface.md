---
title: Интерфейс ICorProfilerInfo10
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 30179c7c198a343baa3fa01ae64f6d580a3f9e7e
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452205"
---
# <a name="icorprofilerinfo10-interface"></a><span data-ttu-id="4279b-102">Интерфейс ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="4279b-102">ICorProfilerInfo10 Interface</span></span>

<span data-ttu-id="4279b-103">Подкласс [ICorProfilerInfo9](icorprofilerinfo9-interface.md) , предоставляющий методы для изменения Il функции, запроса сведений из среды выполнения, а также приостановки и возобновления работы среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="4279b-103">A subclass of [ICorProfilerInfo9](icorprofilerinfo9-interface.md) that provides methods to modify function IL, query information from the runtime, and suspend and resume the runtime.</span></span>

## <a name="methods"></a><span data-ttu-id="4279b-104">Методы</span><span class="sxs-lookup"><span data-stu-id="4279b-104">Methods</span></span>  

| <span data-ttu-id="4279b-105">Метод</span><span class="sxs-lookup"><span data-stu-id="4279b-105">Method</span></span>|<span data-ttu-id="4279b-106">Description</span><span class="sxs-lookup"><span data-stu-id="4279b-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="4279b-107">Метод Енумератеобжектреференцес</span><span class="sxs-lookup"><span data-stu-id="4279b-107">EnumerateObjectReferences Method</span></span>](icorprofilerinfo10-enumerateobjectreferences-method.md)|<span data-ttu-id="4279b-108">При наличии ObjectID, callback и Клиентдата перечисляет ссылки на все объекты (если таковые имеются).</span><span class="sxs-lookup"><span data-stu-id="4279b-108">Given an ObjectID, callback and clientData, enumerates each object reference (if any).</span></span> |
|[<span data-ttu-id="4279b-109">Метод Исфрозенобжект</span><span class="sxs-lookup"><span data-stu-id="4279b-109">IsFrozenObject Method</span></span>](icorprofilerinfo10-isfrozenobject-method.md)|<span data-ttu-id="4279b-110">Определяет, находится ли объект в сегменте, доступном только для чтения.</span><span class="sxs-lookup"><span data-stu-id="4279b-110">Given an ObjectID, determines whether the object is in a read-only segment.</span></span> |
|[<span data-ttu-id="4279b-111">Метод Жетлохобжектсизесрешолд</span><span class="sxs-lookup"><span data-stu-id="4279b-111">GetLOHObjectSizeThreshold Method</span></span>](icorprofilerinfo10-getlohobjectsizethreshold-method.md)|<span data-ttu-id="4279b-112">Возвращает значение заданного порога LOH.</span><span class="sxs-lookup"><span data-stu-id="4279b-112">Gets the value of the configured LOH threshold.</span></span> |
|[<span data-ttu-id="4279b-113">Метод Рекуестрежитвисинлинерс</span><span class="sxs-lookup"><span data-stu-id="4279b-113">RequestReJITWithInliners Method</span></span>](icorprofilerinfo10-requestrejitwithinliners-method.md)| <span data-ttu-id="4279b-114">Режитс запрошенные методы, а также любые запрашиваются методы.</span><span class="sxs-lookup"><span data-stu-id="4279b-114">ReJITs the methods requested, as well as any inliners of the methods requested.</span></span>  |
|[<span data-ttu-id="4279b-115">Метод Суспендрунтиме</span><span class="sxs-lookup"><span data-stu-id="4279b-115">SuspendRuntime Method</span></span>](icorprofilerinfo10-suspendruntime-method.md)| <span data-ttu-id="4279b-116">Приостанавливает выполнение среды выполнения без выполнения сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="4279b-116">Suspends the runtime without performing a GC.</span></span> |
|[<span data-ttu-id="4279b-117">Метод Ресумерунтиме</span><span class="sxs-lookup"><span data-stu-id="4279b-117">ResumeRuntime Method</span></span>](icorprofilerinfo10-resumeruntime-method.md)| <span data-ttu-id="4279b-118">Возобновляет работу среды выполнения без выполнения сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="4279b-118">Resumes the runtime without performing a GC.</span></span> |

## <a name="requirements"></a><span data-ttu-id="4279b-119">Требования</span><span class="sxs-lookup"><span data-stu-id="4279b-119">Requirements</span></span>  
<span data-ttu-id="4279b-120">**Платформы:** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/install/dependencies.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="4279b-120">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?pivots=os-windows).</span></span>  
<span data-ttu-id="4279b-121">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4279b-121">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="4279b-122">**Версии .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4279b-122">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span> 

## <a name="see-also"></a><span data-ttu-id="4279b-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4279b-123">See also</span></span>

- [<span data-ttu-id="4279b-124">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="4279b-124">Profiling Interfaces</span></span>](profiling-interfaces.md)

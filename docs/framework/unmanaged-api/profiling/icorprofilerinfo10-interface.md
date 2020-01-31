---
title: Интерфейс ICorProfilerInfo10
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: e90a1ffbc037636e4296bbd4f4c3c5082885e9f3
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863248"
---
# <a name="icorprofilerinfo10-interface"></a><span data-ttu-id="0822a-102">Интерфейс ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="0822a-102">ICorProfilerInfo10 Interface</span></span>

<span data-ttu-id="0822a-103">Подкласс [ICorProfilerInfo9](icorprofilerinfo9-interface.md) , предоставляющий методы для изменения Il функции, запроса сведений из среды выполнения, а также приостановки и возобновления работы среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="0822a-103">A subclass of [ICorProfilerInfo9](icorprofilerinfo9-interface.md) that provides methods to modify function IL, query information from the runtime, and suspend and resume the runtime.</span></span>

## <a name="methods"></a><span data-ttu-id="0822a-104">Методы</span><span class="sxs-lookup"><span data-stu-id="0822a-104">Methods</span></span>  

| <span data-ttu-id="0822a-105">Метод</span><span class="sxs-lookup"><span data-stu-id="0822a-105">Method</span></span>|<span data-ttu-id="0822a-106">Описание</span><span class="sxs-lookup"><span data-stu-id="0822a-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="0822a-107">Метод Енумератеобжектреференцес</span><span class="sxs-lookup"><span data-stu-id="0822a-107">EnumerateObjectReferences Method</span></span>](icorprofilerinfo10-enumerateobjectreferences-method.md)|<span data-ttu-id="0822a-108">При наличии ObjectID, callback и Клиентдата перечисляет ссылки на все объекты (если таковые имеются).</span><span class="sxs-lookup"><span data-stu-id="0822a-108">Given an ObjectID, callback and clientData, enumerates each object reference (if any).</span></span> |
|[<span data-ttu-id="0822a-109">Метод Исфрозенобжект</span><span class="sxs-lookup"><span data-stu-id="0822a-109">IsFrozenObject Method</span></span>](icorprofilerinfo10-isfrozenobject-method.md)|<span data-ttu-id="0822a-110">Определяет, находится ли объект в сегменте, доступном только для чтения.</span><span class="sxs-lookup"><span data-stu-id="0822a-110">Given an ObjectID, determines whether the object is in a read-only segment.</span></span> |
|[<span data-ttu-id="0822a-111">Метод Жетлохобжектсизесрешолд</span><span class="sxs-lookup"><span data-stu-id="0822a-111">GetLOHObjectSizeThreshold Method</span></span>](icorprofilerinfo10-getlohobjectsizethreshold-method.md)|<span data-ttu-id="0822a-112">Возвращает значение заданного порога LOH.</span><span class="sxs-lookup"><span data-stu-id="0822a-112">Gets the value of the configured LOH threshold.</span></span> |
|[<span data-ttu-id="0822a-113">Метод Рекуестрежитвисинлинерс</span><span class="sxs-lookup"><span data-stu-id="0822a-113">RequestReJITWithInliners Method</span></span>](icorprofilerinfo10-requestrejitwithinliners-method.md)| <span data-ttu-id="0822a-114">Режитс запрошенные методы, а также любые запрашиваются методы.</span><span class="sxs-lookup"><span data-stu-id="0822a-114">ReJITs the methods requested, as well as any inliners of the methods requested.</span></span>  |
|[<span data-ttu-id="0822a-115">Метод Суспендрунтиме</span><span class="sxs-lookup"><span data-stu-id="0822a-115">SuspendRuntime Method</span></span>](icorprofilerinfo10-suspendruntime-method.md)| <span data-ttu-id="0822a-116">Приостанавливает выполнение среды выполнения без выполнения сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="0822a-116">Suspends the runtime without performing a GC.</span></span> |
|[<span data-ttu-id="0822a-117">Метод Ресумерунтиме</span><span class="sxs-lookup"><span data-stu-id="0822a-117">ResumeRuntime Method</span></span>](icorprofilerinfo10-resumeruntime-method.md)| <span data-ttu-id="0822a-118">Возобновляет работу среды выполнения без выполнения сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="0822a-118">Resumes the runtime without performing a GC.</span></span> |

## <a name="requirements"></a><span data-ttu-id="0822a-119">Требования</span><span class="sxs-lookup"><span data-stu-id="0822a-119">Requirements</span></span>  
<span data-ttu-id="0822a-120">**Платформы:** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="0822a-120">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>  
<span data-ttu-id="0822a-121">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0822a-121">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="0822a-122">**Версии .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0822a-122">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span> 

## <a name="see-also"></a><span data-ttu-id="0822a-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="0822a-123">See also</span></span>

- [<span data-ttu-id="0822a-124">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="0822a-124">Profiling Interfaces</span></span>](profiling-interfaces.md)

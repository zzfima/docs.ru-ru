---
title: 'ICorProfilerInfo10:: Енумератеобжектреференцес'
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.EnumerateObjectReferences
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 7fd62e0d3d9173f3b75882131e57126075c0677f
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863313"
---
# <a name="icorprofilerinfo10enumerateobjectreferences-method"></a><span data-ttu-id="ead85-102">Метод ICorProfilerInfo10:: Енумератеобжектреференцес</span><span class="sxs-lookup"><span data-stu-id="ead85-102">ICorProfilerInfo10::EnumerateObjectReferences Method</span></span>

<span data-ttu-id="ead85-103">При наличии ObjectID, callback и Клиентдата перечисляет ссылки на все объекты (если таковые имеются).</span><span class="sxs-lookup"><span data-stu-id="ead85-103">Given an ObjectID, callback and clientData, enumerates each object reference (if any).</span></span>

## <a name="syntax"></a><span data-ttu-id="ead85-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ead85-104">Syntax</span></span>

```cpp
HRESULT EnumerateObjectReferences( [in] ObjectID objectId,
                                   [in] ObjectReferenceCallback callback,
                                   [in] void* clientData);
```

## <a name="parameters"></a><span data-ttu-id="ead85-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ead85-105">Parameters</span></span>

- `objectId`

  <span data-ttu-id="ead85-106">\[в] объект для перечисления ссылок.</span><span class="sxs-lookup"><span data-stu-id="ead85-106">\[in] The object to enumerate references on.</span></span>

- `callback`

  <span data-ttu-id="ead85-107">\[в] функция, которая будет вызываться со ссылками для объекта.</span><span class="sxs-lookup"><span data-stu-id="ead85-107">\[in] The function that will be called with the references for the object.</span></span>

- `clientData`

  <span data-ttu-id="ead85-108">\[in] данные, предоставленные профилировщиком, передаются в функцию `callback`.</span><span class="sxs-lookup"><span data-stu-id="ead85-108">\[in] Profiler-provided data to pass to the `callback` function.</span></span>

## <a name="remarks"></a><span data-ttu-id="ead85-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="ead85-109">Remarks</span></span>

<span data-ttu-id="ead85-110">Метод `EnumerateObjectReferences` аналогичен [ObjectReferences](icorprofilercallback-objectreferences-method.md), за исключением того, что он просматривает ссылки по запросу для профилировщика вместо предварительного выделения массива для хранения ссылок.</span><span class="sxs-lookup"><span data-stu-id="ead85-110">The `EnumerateObjectReferences` method is similar to [ObjectReferences](icorprofilercallback-objectreferences-method.md), except that it walks the references on demand for the profiler instead of pre-allocating an array to store the references.</span></span>

## <a name="requirements"></a><span data-ttu-id="ead85-111">Требования</span><span class="sxs-lookup"><span data-stu-id="ead85-111">Requirements</span></span>

<span data-ttu-id="ead85-112">**Платформы:** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="ead85-112">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>

<span data-ttu-id="ead85-113">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ead85-113">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="ead85-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ead85-114">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="ead85-115">**Версии .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ead85-115">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="ead85-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="ead85-116">See also</span></span>

- [<span data-ttu-id="ead85-117">Интерфейс ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="ead85-117">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)

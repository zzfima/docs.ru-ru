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
ms.openlocfilehash: 9aadf9701444d215291b6fc19cc8cd61ca832837
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452244"
---
# <a name="icorprofilerinfo10enumerateobjectreferences-method"></a><span data-ttu-id="0197c-102">Метод ICorProfilerInfo10:: Енумератеобжектреференцес</span><span class="sxs-lookup"><span data-stu-id="0197c-102">ICorProfilerInfo10::EnumerateObjectReferences Method</span></span>

<span data-ttu-id="0197c-103">При наличии ObjectID, callback и Клиентдата перечисляет ссылки на все объекты (если таковые имеются).</span><span class="sxs-lookup"><span data-stu-id="0197c-103">Given an ObjectID, callback and clientData, enumerates each object reference (if any).</span></span>

## <a name="syntax"></a><span data-ttu-id="0197c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0197c-104">Syntax</span></span>

```cpp
HRESULT EnumerateObjectReferences( [in] ObjectID objectId,
                                   [in] ObjectReferenceCallback callback,
                                   [in] void* clientData);
```

## <a name="parameters"></a><span data-ttu-id="0197c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0197c-105">Parameters</span></span>

- `objectId`

  <span data-ttu-id="0197c-106">\[в] объект для перечисления ссылок.</span><span class="sxs-lookup"><span data-stu-id="0197c-106">\[in] The object to enumerate references on.</span></span>

- `callback`

  <span data-ttu-id="0197c-107">\[в] функция, которая будет вызываться со ссылками для объекта.</span><span class="sxs-lookup"><span data-stu-id="0197c-107">\[in] The function that will be called with the references for the object.</span></span>

- `clientData`

  <span data-ttu-id="0197c-108">\[in] данные, предоставленные профилировщиком, передаются в функцию `callback`.</span><span class="sxs-lookup"><span data-stu-id="0197c-108">\[in] Profiler-provided data to pass to the `callback` function.</span></span>

## <a name="remarks"></a><span data-ttu-id="0197c-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="0197c-109">Remarks</span></span>

<span data-ttu-id="0197c-110">Метод `EnumerateObjectReferences` аналогичен [ObjectReferences](icorprofilercallback-objectreferences-method.md), за исключением того, что он просматривает ссылки по запросу для профилировщика вместо предварительного выделения массива для хранения ссылок.</span><span class="sxs-lookup"><span data-stu-id="0197c-110">The `EnumerateObjectReferences` method is similar to [ObjectReferences](icorprofilercallback-objectreferences-method.md), except that it walks the references on demand for the profiler instead of pre-allocating an array to store the references.</span></span>

## <a name="requirements"></a><span data-ttu-id="0197c-111">Требования</span><span class="sxs-lookup"><span data-stu-id="0197c-111">Requirements</span></span>

<span data-ttu-id="0197c-112">**Платформы:** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/install/dependencies.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="0197c-112">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?pivots=os-windows).</span></span>

<span data-ttu-id="0197c-113">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0197c-113">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="0197c-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0197c-114">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="0197c-115">**Версии .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0197c-115">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="0197c-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0197c-116">See also</span></span>

- [<span data-ttu-id="0197c-117">Интерфейс ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="0197c-117">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)

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
ms.openlocfilehash: ac193b6b78434245b8f11a4f627b4e1992feb8a7
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69661275"
---
# <a name="icorprofilerinfo10enumerateobjectreferences-method"></a><span data-ttu-id="18008-102">Метод ICorProfilerInfo10:: Енумератеобжектреференцес</span><span class="sxs-lookup"><span data-stu-id="18008-102">ICorProfilerInfo10::EnumerateObjectReferences Method</span></span>

<span data-ttu-id="18008-103">При наличии ObjectID, callback и Клиентдата перечисляет ссылки на все объекты (если таковые имеются).</span><span class="sxs-lookup"><span data-stu-id="18008-103">Given an ObjectID, callback and clientData, enumerates each object reference (if any).</span></span>

## <a name="syntax"></a><span data-ttu-id="18008-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="18008-104">Syntax</span></span>

```cpp
HRESULT EnumerateObjectReferences( [in] ObjectID objectId,
                                   [in] ObjectReferenceCallback callback,
                                   [in] void* clientData);
```

#### <a name="parameters"></a><span data-ttu-id="18008-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="18008-105">Parameters</span></span>

`objectId` \
<span data-ttu-id="18008-106">окне Объект для перечисления ссылок.</span><span class="sxs-lookup"><span data-stu-id="18008-106">[in] The object to enumerate references on.</span></span>

`callback` \
<span data-ttu-id="18008-107">окне Функция, которая будет вызываться со ссылками для объекта.</span><span class="sxs-lookup"><span data-stu-id="18008-107">[in] The function that will be called with the references for the object.</span></span>

`clientData` \
<span data-ttu-id="18008-108">окне Данные, предоставленные профилировщиком, передаются `callback` в функцию.</span><span class="sxs-lookup"><span data-stu-id="18008-108">[in] Profiler-provided data to pass to the `callback` function.</span></span>

## <a name="remarks"></a><span data-ttu-id="18008-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="18008-109">Remarks</span></span>

<span data-ttu-id="18008-110">Метод `EnumerateObjectReferences` аналогичен [ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md), за исключением того, что он просматривает ссылки по запросу для профилировщика вместо предварительного выделения массива для хранения ссылок.</span><span class="sxs-lookup"><span data-stu-id="18008-110">The `EnumerateObjectReferences` method is similar to [ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md), except that it walks the references on demand for the profiler instead of pre-allocating an array to store the references.</span></span>

## <a name="requirements"></a><span data-ttu-id="18008-111">Требования</span><span class="sxs-lookup"><span data-stu-id="18008-111">Requirements</span></span>

<span data-ttu-id="18008-112">**Платформ** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span><span class="sxs-lookup"><span data-stu-id="18008-112">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>

<span data-ttu-id="18008-113">**Заголовок.** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="18008-113">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="18008-114">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="18008-114">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="18008-115">**Версии .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18008-115">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="18008-116">См. также</span><span class="sxs-lookup"><span data-stu-id="18008-116">See also</span></span>

- [<span data-ttu-id="18008-117">Интерфейс ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="18008-117">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)

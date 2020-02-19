---
title: 'ICorProfilerInfo10:: Жетлохобжектсизесрешолд'
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.GetLOHObjectSizeThreshold
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 7a0f6f6bea5bc919ebfe9c9acc3b02a31eaa7cd0
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452218"
---
# <a name="icorprofilerinfo10getlohobjectsizethreshold-method"></a><span data-ttu-id="d962e-102">Метод ICorProfilerInfo10:: Жетлохобжектсизесрешолд</span><span class="sxs-lookup"><span data-stu-id="d962e-102">ICorProfilerInfo10::GetLOHObjectSizeThreshold Method</span></span>

<span data-ttu-id="d962e-103">Возвращает значение заданного порога кучи больших объектов (LOH).</span><span class="sxs-lookup"><span data-stu-id="d962e-103">Gets the value of the configured large object heap (LOH) threshold.</span></span>

## <a name="syntax"></a><span data-ttu-id="d962e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d962e-104">Syntax</span></span>

```cpp
HRESULT GetLOHObjectSizeThreshold( [out] DWORD *pThreshold );
```

## <a name="parameters"></a><span data-ttu-id="d962e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d962e-105">Parameters</span></span>

- `pThreshold`

  <span data-ttu-id="d962e-106">\[out] пороговое значение кучи больших объектов в байтах.</span><span class="sxs-lookup"><span data-stu-id="d962e-106">\[out] The large object heap threshold in bytes.</span></span>

## <a name="remarks"></a><span data-ttu-id="d962e-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="d962e-107">Remarks</span></span>

<span data-ttu-id="d962e-108">Объекты, превышающие пороговое значение кучи больших объектов, будут выделены в куче больших объектов.</span><span class="sxs-lookup"><span data-stu-id="d962e-108">Objects larger than the large object heap threshold will be allocated on the large object heap.</span></span> <span data-ttu-id="d962e-109">Начиная с .NET Core 3,0, порог кучи больших объектов можно настроить, `pThreshold` будет содержать пороговое значение активной кучи больших объектов в байтах.</span><span class="sxs-lookup"><span data-stu-id="d962e-109">Starting with .NET Core 3.0 the large object heap threshold is configurable, `pThreshold` will contain the active large object heap threshold size in bytes.</span></span>

## <a name="requirements"></a><span data-ttu-id="d962e-110">Требования</span><span class="sxs-lookup"><span data-stu-id="d962e-110">Requirements</span></span>

<span data-ttu-id="d962e-111">**Платформы:** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/install/dependencies.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="d962e-111">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?pivots=os-windows).</span></span>

<span data-ttu-id="d962e-112">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d962e-112">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="d962e-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d962e-113">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="d962e-114">**Версии .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d962e-114">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="d962e-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d962e-115">See also</span></span>

- [<span data-ttu-id="d962e-116">Интерфейс ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="d962e-116">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)

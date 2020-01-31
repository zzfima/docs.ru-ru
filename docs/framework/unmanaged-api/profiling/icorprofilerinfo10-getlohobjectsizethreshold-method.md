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
ms.openlocfilehash: 95473a8ce8d5fd7540228ecd9767448e51b5b326
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868988"
---
# <a name="icorprofilerinfo10getlohobjectsizethreshold-method"></a><span data-ttu-id="ebdc4-102">Метод ICorProfilerInfo10:: Жетлохобжектсизесрешолд</span><span class="sxs-lookup"><span data-stu-id="ebdc4-102">ICorProfilerInfo10::GetLOHObjectSizeThreshold Method</span></span>

<span data-ttu-id="ebdc4-103">Возвращает значение заданного порога кучи больших объектов (LOH).</span><span class="sxs-lookup"><span data-stu-id="ebdc4-103">Gets the value of the configured large object heap (LOH) threshold.</span></span>

## <a name="syntax"></a><span data-ttu-id="ebdc4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ebdc4-104">Syntax</span></span>

```cpp
HRESULT GetLOHObjectSizeThreshold( [out] DWORD *pThreshold );
```

## <a name="parameters"></a><span data-ttu-id="ebdc4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ebdc4-105">Parameters</span></span>

- `pThreshold`

  <span data-ttu-id="ebdc4-106">\[out] пороговое значение кучи больших объектов в байтах.</span><span class="sxs-lookup"><span data-stu-id="ebdc4-106">\[out] The large object heap threshold in bytes.</span></span>

## <a name="remarks"></a><span data-ttu-id="ebdc4-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="ebdc4-107">Remarks</span></span>

<span data-ttu-id="ebdc4-108">Объекты, превышающие пороговое значение кучи больших объектов, будут выделены в куче больших объектов.</span><span class="sxs-lookup"><span data-stu-id="ebdc4-108">Objects larger than the large object heap threshold will be allocated on the large object heap.</span></span> <span data-ttu-id="ebdc4-109">Начиная с .NET Core 3,0, порог кучи больших объектов можно настроить, `pThreshold` будет содержать пороговое значение активной кучи больших объектов в байтах.</span><span class="sxs-lookup"><span data-stu-id="ebdc4-109">Starting with .NET Core 3.0 the large object heap threshold is configurable, `pThreshold` will contain the active large object heap threshold size in bytes.</span></span>

## <a name="requirements"></a><span data-ttu-id="ebdc4-110">Требования</span><span class="sxs-lookup"><span data-stu-id="ebdc4-110">Requirements</span></span>

<span data-ttu-id="ebdc4-111">**Платформы:** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="ebdc4-111">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>

<span data-ttu-id="ebdc4-112">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ebdc4-112">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="ebdc4-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ebdc4-113">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="ebdc4-114">**Версии .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ebdc4-114">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="ebdc4-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="ebdc4-115">See also</span></span>

- [<span data-ttu-id="ebdc4-116">Интерфейс ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="ebdc4-116">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)

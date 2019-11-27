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
ms.openlocfilehash: 7a38ee4ae74ca5b96dd082e752fc733eb85fca3f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427024"
---
# <a name="icorprofilerinfo10getlohobjectsizethreshold-method"></a><span data-ttu-id="e6856-102">Метод ICorProfilerInfo10:: Жетлохобжектсизесрешолд</span><span class="sxs-lookup"><span data-stu-id="e6856-102">ICorProfilerInfo10::GetLOHObjectSizeThreshold Method</span></span>

<span data-ttu-id="e6856-103">Возвращает значение заданного порога кучи больших объектов (LOH).</span><span class="sxs-lookup"><span data-stu-id="e6856-103">Gets the value of the configured large object heap (LOH) threshold.</span></span>

## <a name="syntax"></a><span data-ttu-id="e6856-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e6856-104">Syntax</span></span>

```cpp
HRESULT GetLOHObjectSizeThreshold( [out] DWORD *pThreshold );
```

#### <a name="parameters"></a><span data-ttu-id="e6856-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e6856-105">Parameters</span></span>

`pThreshold` \
<span data-ttu-id="e6856-106">заполняет Пороговое значение кучи больших объектов в байтах.</span><span class="sxs-lookup"><span data-stu-id="e6856-106">[out] The large object heap threshold in bytes.</span></span>

## <a name="remarks"></a><span data-ttu-id="e6856-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="e6856-107">Remarks</span></span>

<span data-ttu-id="e6856-108">Объекты, превышающие пороговое значение кучи больших объектов, будут выделены в куче больших объектов.</span><span class="sxs-lookup"><span data-stu-id="e6856-108">Objects larger than the large object heap threshold will be allocated on the large object heap.</span></span> <span data-ttu-id="e6856-109">Начиная с .NET Core 3,0, порог кучи больших объектов можно настроить, `pThreshold` будет содержать пороговое значение активной кучи больших объектов в байтах.</span><span class="sxs-lookup"><span data-stu-id="e6856-109">Starting with .NET Core 3.0 the large object heap threshold is configurable, `pThreshold` will contain the active large object heap threshold size in bytes.</span></span>

## <a name="requirements"></a><span data-ttu-id="e6856-110">Требования</span><span class="sxs-lookup"><span data-stu-id="e6856-110">Requirements</span></span>

<span data-ttu-id="e6856-111">**Платформы:** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="e6856-111">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>

<span data-ttu-id="e6856-112">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e6856-112">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="e6856-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e6856-113">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="e6856-114">**Версии .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6856-114">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="e6856-115">См. также</span><span class="sxs-lookup"><span data-stu-id="e6856-115">See also</span></span>

- [<span data-ttu-id="e6856-116">Интерфейс ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="e6856-116">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)

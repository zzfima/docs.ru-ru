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
ms.openlocfilehash: 8c9a85e9f00027f597795eea55a9bbb0364790f8
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69661242"
---
# <a name="icorprofilerinfo10getlohobjectsizethreshold-method"></a><span data-ttu-id="1ffd1-102">Метод ICorProfilerInfo10:: Жетлохобжектсизесрешолд</span><span class="sxs-lookup"><span data-stu-id="1ffd1-102">ICorProfilerInfo10::GetLOHObjectSizeThreshold Method</span></span>

<span data-ttu-id="1ffd1-103">Возвращает значение заданного порога кучи больших объектов (LOH).</span><span class="sxs-lookup"><span data-stu-id="1ffd1-103">Gets the value of the configured large object heap (LOH) threshold.</span></span>

## <a name="syntax"></a><span data-ttu-id="1ffd1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1ffd1-104">Syntax</span></span>

```cpp
HRESULT GetLOHObjectSizeThreshold( [out] DWORD *pThreshold );
```

#### <a name="parameters"></a><span data-ttu-id="1ffd1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1ffd1-105">Parameters</span></span>

`pThreshold` \
<span data-ttu-id="1ffd1-106">заполняет Пороговое значение кучи больших объектов в байтах.</span><span class="sxs-lookup"><span data-stu-id="1ffd1-106">[out] The large object heap threshold in bytes.</span></span>

## <a name="remarks"></a><span data-ttu-id="1ffd1-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="1ffd1-107">Remarks</span></span>

<span data-ttu-id="1ffd1-108">Объекты, превышающие пороговое значение кучи больших объектов, будут выделены в куче больших объектов.</span><span class="sxs-lookup"><span data-stu-id="1ffd1-108">Objects larger than the large object heap threshold will be allocated on the large object heap.</span></span> <span data-ttu-id="1ffd1-109">Начиная с .NET Core 3,0, порог кучи больших объектов можно настроить, `pThreshold` он будет содержать пороговое значение активной кучи больших объектов в байтах.</span><span class="sxs-lookup"><span data-stu-id="1ffd1-109">Starting with .NET Core 3.0 the large object heap threshold is configurable, `pThreshold` will contain the active large object heap threshold size in bytes.</span></span>

## <a name="requirements"></a><span data-ttu-id="1ffd1-110">Требования</span><span class="sxs-lookup"><span data-stu-id="1ffd1-110">Requirements</span></span>

<span data-ttu-id="1ffd1-111">**Платформ** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span><span class="sxs-lookup"><span data-stu-id="1ffd1-111">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>

<span data-ttu-id="1ffd1-112">**Заголовок.** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="1ffd1-112">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="1ffd1-113">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="1ffd1-113">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="1ffd1-114">**Версии .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ffd1-114">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="1ffd1-115">См. также</span><span class="sxs-lookup"><span data-stu-id="1ffd1-115">See also</span></span>

- [<span data-ttu-id="1ffd1-116">Интерфейс ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="1ffd1-116">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)

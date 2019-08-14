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
ms.openlocfilehash: d6b6575cf04635b40b504b11bc415f61f05b4205
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2019
ms.locfileid: "68974024"
---
# <a name="icorprofilerinfo10getlohobjectsizethreshold-method"></a><span data-ttu-id="1745b-102">Метод ICorProfilerInfo10:: Жетлохобжектсизесрешолд</span><span class="sxs-lookup"><span data-stu-id="1745b-102">ICorProfilerInfo10::GetLOHObjectSizeThreshold Method</span></span>
  
 <span data-ttu-id="1745b-103">Возвращает значение заданного порога кучи больших объектов (LOH).</span><span class="sxs-lookup"><span data-stu-id="1745b-103">Gets the value of the configured large object heap (LOH) threshold.</span></span>   
  
## <a name="syntax"></a><span data-ttu-id="1745b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1745b-104">Syntax</span></span>  
  
```cpp
HRESULT GetLOHObjectSizeThreshold( [out] DWORD *pThreshold );
```  
  
#### <a name="parameters"></a><span data-ttu-id="1745b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1745b-105">Parameters</span></span>  
 `pThreshold` \
 <span data-ttu-id="1745b-106">заполняет Пороговое значение кучи больших объектов в байтах.</span><span class="sxs-lookup"><span data-stu-id="1745b-106">[out] The large object heap threshold in bytes.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="1745b-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="1745b-107">Remarks</span></span>  
 <span data-ttu-id="1745b-108">Объекты, превышающие пороговое значение кучи больших объектов, будут выделены в куче больших объектов.</span><span class="sxs-lookup"><span data-stu-id="1745b-108">Objects larger than the large object heap threshold will be allocated on the large object heap.</span></span> <span data-ttu-id="1745b-109">Начиная с .NET Core 3,0, порог кучи больших объектов можно настроить, `pThreshold` он будет содержать пороговое значение активной кучи больших объектов в байтах.</span><span class="sxs-lookup"><span data-stu-id="1745b-109">Starting with .NET Core 3.0 the large object heap threshold is configurable, `pThreshold` will contain the active large object heap threshold size in bytes.</span></span>

## <a name="requirements"></a><span data-ttu-id="1745b-110">Требования</span><span class="sxs-lookup"><span data-stu-id="1745b-110">Requirements</span></span>  
 <span data-ttu-id="1745b-111">**Платформ** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span><span class="sxs-lookup"><span data-stu-id="1745b-111">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>  
  
 <span data-ttu-id="1745b-112">**Заголовок.** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="1745b-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1745b-113">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="1745b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1745b-114">**Версии .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1745b-114">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1745b-115">См. также</span><span class="sxs-lookup"><span data-stu-id="1745b-115">See also</span></span>
- [<span data-ttu-id="1745b-116">Интерфейс ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="1745b-116">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)


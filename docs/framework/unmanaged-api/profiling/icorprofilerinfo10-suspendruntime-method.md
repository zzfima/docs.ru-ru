---
title: 'ICorProfilerInfo10:: Суспендрунтиме'
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.SuspendRuntime
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: f5104c779f99ef9f26a9eccc00008ded62336d8e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426963"
---
# <a name="icorprofilerinfo10suspendruntime-method"></a><span data-ttu-id="4a7ac-102">Метод ICorProfilerInfo10:: Суспендрунтиме</span><span class="sxs-lookup"><span data-stu-id="4a7ac-102">ICorProfilerInfo10::SuspendRuntime Method</span></span>

<span data-ttu-id="4a7ac-103">Приостанавливает выполнение среды выполнения без выполнения сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="4a7ac-103">Suspends the runtime without performing a GC.</span></span>

## <a name="syntax"></a><span data-ttu-id="4a7ac-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4a7ac-104">Syntax</span></span>

```cpp
HRESULT SuspendRuntime();
```

## <a name="requirements"></a><span data-ttu-id="4a7ac-105">Требования</span><span class="sxs-lookup"><span data-stu-id="4a7ac-105">Requirements</span></span>

<span data-ttu-id="4a7ac-106">**Платформы:** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="4a7ac-106">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>

<span data-ttu-id="4a7ac-107">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4a7ac-107">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="4a7ac-108">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4a7ac-108">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="4a7ac-109">**Версии .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a7ac-109">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="4a7ac-110">См. также</span><span class="sxs-lookup"><span data-stu-id="4a7ac-110">See also</span></span>

- [<span data-ttu-id="4a7ac-111">Интерфейс ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="4a7ac-111">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)

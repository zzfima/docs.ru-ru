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
ms.openlocfilehash: 8d00718579f44a164cd83e2b05d41f70f1c65785
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452153"
---
# <a name="icorprofilerinfo10suspendruntime-method"></a><span data-ttu-id="b204c-102">Метод ICorProfilerInfo10:: Суспендрунтиме</span><span class="sxs-lookup"><span data-stu-id="b204c-102">ICorProfilerInfo10::SuspendRuntime Method</span></span>

<span data-ttu-id="b204c-103">Приостанавливает выполнение среды выполнения без выполнения сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="b204c-103">Suspends the runtime without performing a GC.</span></span>

## <a name="syntax"></a><span data-ttu-id="b204c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b204c-104">Syntax</span></span>

```cpp
HRESULT SuspendRuntime();
```

## <a name="requirements"></a><span data-ttu-id="b204c-105">Требования</span><span class="sxs-lookup"><span data-stu-id="b204c-105">Requirements</span></span>

<span data-ttu-id="b204c-106">**Платформы:** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/install/dependencies.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="b204c-106">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?pivots=os-windows).</span></span>

<span data-ttu-id="b204c-107">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b204c-107">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="b204c-108">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b204c-108">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="b204c-109">**Версии .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b204c-109">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="b204c-110">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b204c-110">See also</span></span>

- [<span data-ttu-id="b204c-111">Интерфейс ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="b204c-111">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)

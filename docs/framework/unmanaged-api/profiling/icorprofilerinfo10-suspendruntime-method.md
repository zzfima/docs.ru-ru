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
ms.openlocfilehash: 74300a12d000565a63cd7ea862c759d47b87bbe1
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69665700"
---
# <a name="icorprofilerinfo10suspendruntime-method"></a><span data-ttu-id="c3ab8-102">Метод ICorProfilerInfo10:: Суспендрунтиме</span><span class="sxs-lookup"><span data-stu-id="c3ab8-102">ICorProfilerInfo10::SuspendRuntime Method</span></span>

<span data-ttu-id="c3ab8-103">Приостанавливает выполнение среды выполнения без выполнения сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="c3ab8-103">Suspends the runtime without performing a GC.</span></span>

## <a name="syntax"></a><span data-ttu-id="c3ab8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c3ab8-104">Syntax</span></span>

```cpp
HRESULT SuspendRuntime();
```

## <a name="requirements"></a><span data-ttu-id="c3ab8-105">Требования</span><span class="sxs-lookup"><span data-stu-id="c3ab8-105">Requirements</span></span>

<span data-ttu-id="c3ab8-106">**Платформ** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span><span class="sxs-lookup"><span data-stu-id="c3ab8-106">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>

<span data-ttu-id="c3ab8-107">**Заголовок.** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="c3ab8-107">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="c3ab8-108">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="c3ab8-108">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="c3ab8-109">**Версии .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3ab8-109">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="c3ab8-110">См. также</span><span class="sxs-lookup"><span data-stu-id="c3ab8-110">See also</span></span>

- [<span data-ttu-id="c3ab8-111">Интерфейс ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="c3ab8-111">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)

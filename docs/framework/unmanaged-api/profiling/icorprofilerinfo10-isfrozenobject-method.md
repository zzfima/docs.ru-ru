---
title: 'ICorProfilerInfo10:: Исфрозенобжект'
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.IsFrozenObject
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 21f9cb415f913a9c865a487f6e80523344db811e
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452192"
---
# <a name="icorprofilerinfo10isfrozenobject-method"></a><span data-ttu-id="806f4-102">Метод ICorProfilerInfo10:: Исфрозенобжект</span><span class="sxs-lookup"><span data-stu-id="806f4-102">ICorProfilerInfo10::IsFrozenObject Method</span></span>

<span data-ttu-id="806f4-103">Определяет, находится ли объект в сегменте, доступном только для чтения.</span><span class="sxs-lookup"><span data-stu-id="806f4-103">Given an ObjectID, determines whether the object is in a read-only segment.</span></span>

## <a name="syntax"></a><span data-ttu-id="806f4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="806f4-104">Syntax</span></span>

```cpp
HRESULT IsFrozenObject( [in]  ObjectID objectId,
                        [out] BOOL *pbFrozen);
```

## <a name="parameters"></a><span data-ttu-id="806f4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="806f4-105">Parameters</span></span>

- `objectId`

  <span data-ttu-id="806f4-106">\[в] объект для проверки.</span><span class="sxs-lookup"><span data-stu-id="806f4-106">\[in] The object to examine.</span></span>

- `pbFrozen`

  <span data-ttu-id="806f4-107">\[out] `BOOL`, указывающий, находится ли объект в сегменте, доступном только для чтения.</span><span class="sxs-lookup"><span data-stu-id="806f4-107">\[out] A `BOOL` indicating if the object is in a read-only segment.</span></span>

## <a name="requirements"></a><span data-ttu-id="806f4-108">Требования</span><span class="sxs-lookup"><span data-stu-id="806f4-108">Requirements</span></span>

<span data-ttu-id="806f4-109">**Платформы:** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/install/dependencies.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="806f4-109">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?pivots=os-windows).</span></span>

<span data-ttu-id="806f4-110">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="806f4-110">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="806f4-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="806f4-111">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="806f4-112">**Версии .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="806f4-112">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="806f4-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="806f4-113">See also</span></span>

- [<span data-ttu-id="806f4-114">Интерфейс ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="806f4-114">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)

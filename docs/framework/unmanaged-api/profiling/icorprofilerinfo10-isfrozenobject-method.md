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
ms.openlocfilehash: b6dabefceba038a129148f7ba36d4ffcfc425c80
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790037"
---
# <a name="icorprofilerinfo10isfrozenobject-method"></a><span data-ttu-id="bb962-102">Метод ICorProfilerInfo10:: Исфрозенобжект</span><span class="sxs-lookup"><span data-stu-id="bb962-102">ICorProfilerInfo10::IsFrozenObject Method</span></span>

<span data-ttu-id="bb962-103">Определяет, находится ли объект в сегменте, доступном только для чтения.</span><span class="sxs-lookup"><span data-stu-id="bb962-103">Given an ObjectID, determines whether the object is in a read-only segment.</span></span>

## <a name="syntax"></a><span data-ttu-id="bb962-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bb962-104">Syntax</span></span>

```cpp
HRESULT IsFrozenObject( [in]  ObjectID objectId,
                        [out] BOOL *pbFrozen);
```

## <a name="parameters"></a><span data-ttu-id="bb962-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bb962-105">Parameters</span></span>

- `objectId`

  <span data-ttu-id="bb962-106">\[в] объект для проверки.</span><span class="sxs-lookup"><span data-stu-id="bb962-106">\[in] The object to examine.</span></span>

- `pbFrozen`

  <span data-ttu-id="bb962-107">\[out] `BOOL`, указывающий, находится ли объект в сегменте, доступном только для чтения.</span><span class="sxs-lookup"><span data-stu-id="bb962-107">\[out] A `BOOL` indicating if the object is in a read-only segment.</span></span>

## <a name="requirements"></a><span data-ttu-id="bb962-108">Требования</span><span class="sxs-lookup"><span data-stu-id="bb962-108">Requirements</span></span>

<span data-ttu-id="bb962-109">**Платформы:** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="bb962-109">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>

<span data-ttu-id="bb962-110">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bb962-110">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="bb962-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb962-111">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="bb962-112">**Версии .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb962-112">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="bb962-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="bb962-113">See also</span></span>

- [<span data-ttu-id="bb962-114">Интерфейс ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="bb962-114">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)

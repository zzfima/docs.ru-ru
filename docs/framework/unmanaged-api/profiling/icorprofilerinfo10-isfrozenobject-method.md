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
ms.openlocfilehash: d212c06c7ddc9f22095c0b95f19fd1083482435c
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69661223"
---
# <a name="icorprofilerinfo10isfrozenobject-method"></a><span data-ttu-id="4900d-102">Метод ICorProfilerInfo10:: Исфрозенобжект</span><span class="sxs-lookup"><span data-stu-id="4900d-102">ICorProfilerInfo10::IsFrozenObject Method</span></span>

<span data-ttu-id="4900d-103">Определяет, находится ли объект в сегменте, доступном только для чтения.</span><span class="sxs-lookup"><span data-stu-id="4900d-103">Given an ObjectID, determines whether the object is in a read-only segment.</span></span>

## <a name="syntax"></a><span data-ttu-id="4900d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4900d-104">Syntax</span></span>

```cpp
HRESULT IsFrozenObject( [in]  ObjectID objectId,
                        [out] BOOL *pbFrozen);
```

#### <a name="parameters"></a><span data-ttu-id="4900d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4900d-105">Parameters</span></span>

`objectId` \
<span data-ttu-id="4900d-106">окне Объект для проверки.</span><span class="sxs-lookup"><span data-stu-id="4900d-106">[in] The object to examine.</span></span>

`pbFrozen` \
<span data-ttu-id="4900d-107">заполняет Значение `BOOL` типа, указывающее, находится ли объект в сегменте, доступном только для чтения.</span><span class="sxs-lookup"><span data-stu-id="4900d-107">[out] A `BOOL` indicating if the object is in a read-only segment.</span></span>

## <a name="requirements"></a><span data-ttu-id="4900d-108">Требования</span><span class="sxs-lookup"><span data-stu-id="4900d-108">Requirements</span></span>

<span data-ttu-id="4900d-109">**Платформ** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span><span class="sxs-lookup"><span data-stu-id="4900d-109">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>

<span data-ttu-id="4900d-110">**Заголовок.** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="4900d-110">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="4900d-111">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="4900d-111">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="4900d-112">**Версии .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4900d-112">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="4900d-113">См. также</span><span class="sxs-lookup"><span data-stu-id="4900d-113">See also</span></span>

- [<span data-ttu-id="4900d-114">Интерфейс ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="4900d-114">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)

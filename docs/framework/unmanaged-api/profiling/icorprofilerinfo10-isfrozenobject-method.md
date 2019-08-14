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
ms.openlocfilehash: 05f25d8fb61a16f41a82a987529017db6a687740
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2019
ms.locfileid: "68973994"
---
# <a name="icorprofilerinfo10isfrozenobject-method"></a><span data-ttu-id="c1a75-102">Метод ICorProfilerInfo10:: Исфрозенобжект</span><span class="sxs-lookup"><span data-stu-id="c1a75-102">ICorProfilerInfo10::IsFrozenObject Method</span></span>
  
 <span data-ttu-id="c1a75-103">Определяет, находится ли объект в сегменте, доступном только для чтения.</span><span class="sxs-lookup"><span data-stu-id="c1a75-103">Given an ObjectID, determines whether the object is in a read-only segment.</span></span>   
  
## <a name="syntax"></a><span data-ttu-id="c1a75-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c1a75-104">Syntax</span></span>  
  
```cpp
HRESULT IsFrozenObject( [in]  ObjectID objectId,
                        [out] BOOL *pbFrozen);
```  
  
#### <a name="parameters"></a><span data-ttu-id="c1a75-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c1a75-105">Parameters</span></span>  
 
 `objectId` \
 <span data-ttu-id="c1a75-106">окне Объект для проверки.</span><span class="sxs-lookup"><span data-stu-id="c1a75-106">[in] The object to examine.</span></span>

 `pbFrozen` \
 <span data-ttu-id="c1a75-107">заполняет Значение `BOOL` типа, указывающее, находится ли объект в сегменте, доступном только для чтения.</span><span class="sxs-lookup"><span data-stu-id="c1a75-107">[out] A `BOOL` indicating if the object is in a read-only segment.</span></span>

## <a name="requirements"></a><span data-ttu-id="c1a75-108">Требования</span><span class="sxs-lookup"><span data-stu-id="c1a75-108">Requirements</span></span>  
 <span data-ttu-id="c1a75-109">**Платформ** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span><span class="sxs-lookup"><span data-stu-id="c1a75-109">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>  
  
 <span data-ttu-id="c1a75-110">**Заголовок.** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="c1a75-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c1a75-111">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="c1a75-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c1a75-112">**Версии .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1a75-112">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="c1a75-113">См. также</span><span class="sxs-lookup"><span data-stu-id="c1a75-113">See also</span></span>
- [<span data-ttu-id="c1a75-114">Интерфейс ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="c1a75-114">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)


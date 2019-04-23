---
title: Структура COR_PRF_GC_GENERATION_RANGE
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_GENERATION_RANGE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_GENERATION_RANGE
helpviewer_keywords:
- COR_PRF_GC_GENERATION_RANGE structure [.NET Framework profiling]
ms.assetid: e7e07273-8d10-4a68-807e-59634e3f8c5e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 646c4e37a7fab503a26557f9fdfc926b1186b17b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59216708"
---
# <a name="corprfgcgenerationrange-structure"></a><span data-ttu-id="af8bc-102">Структура COR_PRF_GC_GENERATION_RANGE</span><span class="sxs-lookup"><span data-stu-id="af8bc-102">COR_PRF_GC_GENERATION_RANGE Structure</span></span>
<span data-ttu-id="af8bc-103">Описывает диапазон (т. е., блок) памяти, который занимается сборкой мусора.</span><span class="sxs-lookup"><span data-stu-id="af8bc-103">Describes a range (that is, block) of memory that is undergoing garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af8bc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="af8bc-104">Syntax</span></span>  
  
```  
typedef struct COR_PRF_GC_GENERATION_RANGE {  
    COR_PRF_GC_GENERATION generation;  
    ObjectID rangeStart;  
    UINT_PTR rangeLength;  
    UINT_PTR rangeLengthReserved;  
} COR_PRF_GC_GENERATION_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="af8bc-105">Участники</span><span class="sxs-lookup"><span data-stu-id="af8bc-105">Members</span></span>  
  
|<span data-ttu-id="af8bc-106">Член</span><span class="sxs-lookup"><span data-stu-id="af8bc-106">Member</span></span>|<span data-ttu-id="af8bc-107">Описание</span><span class="sxs-lookup"><span data-stu-id="af8bc-107">Description</span></span>|  
|------------|-----------------|  
|`generation`|<span data-ttu-id="af8bc-108">Значение [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) принадлежит перечисления, указывающее поколение, к которому блока памяти.</span><span class="sxs-lookup"><span data-stu-id="af8bc-108">A value of the [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) enumeration that specifies the generation to which the block of memory belongs.</span></span>|  
|`rangeStart`|<span data-ttu-id="af8bc-109">Идентификатор объекта, который указывает начальное положение блока памяти.</span><span class="sxs-lookup"><span data-stu-id="af8bc-109">The ID of an object that specifies the starting location of the block of memory.</span></span>|  
|`rangeLength`|<span data-ttu-id="af8bc-110">Указатель на целое число, указывающее размер используемой части блока памяти (то есть, объем памяти, используемой в блоке).</span><span class="sxs-lookup"><span data-stu-id="af8bc-110">A pointer to an integer that specifies the size of the used portion of the memory block (that is, the amount of memory used within the block).</span></span>|  
|`rangeLengthReserved`|<span data-ttu-id="af8bc-111">Указатель на целое число, указывающее размер блока памяти (то есть, объем памяти, зарезервированной для блока).</span><span class="sxs-lookup"><span data-stu-id="af8bc-111">A pointer to an integer that specifies the size of the memory block (that is, the amount of memory reserved for the block).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af8bc-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="af8bc-112">Remarks</span></span>  
 <span data-ttu-id="af8bc-113">`rangeLength` Гарантируется, что значение является точным только если [ICorProfilerInfo2::GetGenerationBounds](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getgenerationbounds-method.md) или [ICorProfilerInfo2::GetObjectGeneration](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getobjectgeneration-method.md), оба из которых используют `COR_PRF_GC_GENERATION_RANGE` Структура, вызывается из [ICorProfilerCallback2::GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md) или [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="af8bc-113">The `rangeLength` value is guaranteed to be accurate only if [ICorProfilerInfo2::GetGenerationBounds](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getgenerationbounds-method.md) or [ICorProfilerInfo2::GetObjectGeneration](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getobjectgeneration-method.md), both of which use the `COR_PRF_GC_GENERATION_RANGE` structure, is called from the [ICorProfilerCallback2::GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md) or the [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af8bc-114">Требования</span><span class="sxs-lookup"><span data-stu-id="af8bc-114">Requirements</span></span>  
 <span data-ttu-id="af8bc-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af8bc-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af8bc-116">**Заголовок.** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="af8bc-116">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="af8bc-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="af8bc-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="af8bc-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af8bc-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af8bc-119">См. также</span><span class="sxs-lookup"><span data-stu-id="af8bc-119">See also</span></span>

- [<span data-ttu-id="af8bc-120">Структуры профилирования</span><span class="sxs-lookup"><span data-stu-id="af8bc-120">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)

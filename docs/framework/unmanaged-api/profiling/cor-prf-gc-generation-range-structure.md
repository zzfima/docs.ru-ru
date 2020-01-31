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
ms.openlocfilehash: 682aac9729519e0861ae6e6f60df78a30063c278
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867217"
---
# <a name="cor_prf_gc_generation_range-structure"></a><span data-ttu-id="5547f-102">Структура COR_PRF_GC_GENERATION_RANGE</span><span class="sxs-lookup"><span data-stu-id="5547f-102">COR_PRF_GC_GENERATION_RANGE Structure</span></span>
<span data-ttu-id="5547f-103">Описывает диапазон (т. е., блок) памяти, который занимается сборкой мусора.</span><span class="sxs-lookup"><span data-stu-id="5547f-103">Describes a range (that is, block) of memory that is undergoing garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5547f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5547f-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_PRF_GC_GENERATION_RANGE {  
    COR_PRF_GC_GENERATION generation;  
    ObjectID rangeStart;  
    UINT_PTR rangeLength;  
    UINT_PTR rangeLengthReserved;  
} COR_PRF_GC_GENERATION_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="5547f-105">Участники</span><span class="sxs-lookup"><span data-stu-id="5547f-105">Members</span></span>  
  
|<span data-ttu-id="5547f-106">Член</span><span class="sxs-lookup"><span data-stu-id="5547f-106">Member</span></span>|<span data-ttu-id="5547f-107">Описание</span><span class="sxs-lookup"><span data-stu-id="5547f-107">Description</span></span>|  
|------------|-----------------|  
|`generation`|<span data-ttu-id="5547f-108">Значение перечисления [COR_PRF_GC_GENERATION](cor-prf-gc-generation-enumeration.md) , указывающее поколение, к которому принадлежит блок памяти.</span><span class="sxs-lookup"><span data-stu-id="5547f-108">A value of the [COR_PRF_GC_GENERATION](cor-prf-gc-generation-enumeration.md) enumeration that specifies the generation to which the block of memory belongs.</span></span>|  
|`rangeStart`|<span data-ttu-id="5547f-109">Идентификатор объекта, указывающего начальное расположение блока памяти.</span><span class="sxs-lookup"><span data-stu-id="5547f-109">The ID of an object that specifies the starting location of the block of memory.</span></span>|  
|`rangeLength`|<span data-ttu-id="5547f-110">Указатель на целое число, задающее размер используемой части блока памяти (то есть объема памяти, используемого в блоке).</span><span class="sxs-lookup"><span data-stu-id="5547f-110">A pointer to an integer that specifies the size of the used portion of the memory block (that is, the amount of memory used within the block).</span></span>|  
|`rangeLengthReserved`|<span data-ttu-id="5547f-111">Указатель на целое число, задающее размер блока памяти (то есть объема памяти, зарезервированного для блока).</span><span class="sxs-lookup"><span data-stu-id="5547f-111">A pointer to an integer that specifies the size of the memory block (that is, the amount of memory reserved for the block).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5547f-112">Заметки</span><span class="sxs-lookup"><span data-stu-id="5547f-112">Remarks</span></span>  
 <span data-ttu-id="5547f-113">Значение `rangeLength` гарантируется точно, только если [ICorProfilerInfo2:: GetGenerationBounds](icorprofilerinfo2-getgenerationbounds-method.md) или [ICorProfilerInfo2:: GetObjectGeneration](icorprofilerinfo2-getobjectgeneration-method.md), оба из которых используют структуру `COR_PRF_GC_GENERATION_RANGE`, вызываются из метода [ICorProfilerCallback2:: GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md) или [ICorProfilerCallback2:: GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="5547f-113">The `rangeLength` value is guaranteed to be accurate only if [ICorProfilerInfo2::GetGenerationBounds](icorprofilerinfo2-getgenerationbounds-method.md) or [ICorProfilerInfo2::GetObjectGeneration](icorprofilerinfo2-getobjectgeneration-method.md), both of which use the `COR_PRF_GC_GENERATION_RANGE` structure, is called from the [ICorProfilerCallback2::GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md) or the [ICorProfilerCallback2::GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5547f-114">Требования</span><span class="sxs-lookup"><span data-stu-id="5547f-114">Requirements</span></span>  
 <span data-ttu-id="5547f-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5547f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5547f-116">**Заголовок:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="5547f-116">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="5547f-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5547f-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5547f-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5547f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5547f-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="5547f-119">See also</span></span>

- [<span data-ttu-id="5547f-120">Структуры профилирования</span><span class="sxs-lookup"><span data-stu-id="5547f-120">Profiling Structures</span></span>](profiling-structures.md)

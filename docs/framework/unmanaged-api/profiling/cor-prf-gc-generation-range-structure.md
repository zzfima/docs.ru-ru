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
ms.openlocfilehash: 0bdb8cd02e0beb69e3ec594b0aadd741a5f0d924
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428336"
---
# <a name="cor_prf_gc_generation_range-structure"></a>Структура COR_PRF_GC_GENERATION_RANGE
Описывает диапазон (т. е., блок) памяти, который занимается сборкой мусора.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef struct COR_PRF_GC_GENERATION_RANGE {  
    COR_PRF_GC_GENERATION generation;  
    ObjectID rangeStart;  
    UINT_PTR rangeLength;  
    UINT_PTR rangeLengthReserved;  
} COR_PRF_GC_GENERATION_RANGE;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`generation`|Значение перечисления [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) , указывающее поколение, к которому принадлежит блок памяти.|  
|`rangeStart`|Идентификатор объекта, указывающего начальное расположение блока памяти.|  
|`rangeLength`|Указатель на целое число, задающее размер используемой части блока памяти (то есть объема памяти, используемого в блоке).|  
|`rangeLengthReserved`|Указатель на целое число, задающее размер блока памяти (то есть объема памяти, зарезервированного для блока).|  
  
## <a name="remarks"></a>Примечания  
 Значение `rangeLength` гарантируется точно, только если [ICorProfilerInfo2:: GetGenerationBounds](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getgenerationbounds-method.md) или [ICorProfilerInfo2:: GetObjectGeneration](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getobjectgeneration-method.md), оба из которых используют структуру `COR_PRF_GC_GENERATION_RANGE`, вызываются из метода [ICorProfilerCallback2:: GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md) или [ICorProfilerCallback2:: GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf. idl  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Структуры профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)

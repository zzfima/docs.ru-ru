---
title: Метод ICorProfilerCallback::RootReferences
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RootReferences
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RootReferences
helpviewer_keywords:
- RootReferences method [.NET Framework profiling]
- ICorProfilerCallback::RootReferences method [.NET Framework profiling]
ms.assetid: dbdf853b-d1a4-4828-8ef7-53d121d8e6ae
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a68ea07c40c966422be6ebb663e62508032c2610
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67750448"
---
# <a name="icorprofilercallbackrootreferences-method"></a>Метод ICorProfilerCallback::RootReferences
Уведомляет профилировщик о корневыми ссылками после сборки мусора.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT RootReferences(  
    [in] ULONG    cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[] );  
```  
  
## <a name="parameters"></a>Параметры  
 `cRootRefs`  
 [in] Число ссылок в `rootRefIds` массива.  
  
 `rootRefIds`  
 [in] Массив идентификаторов объектов, которые ссылаются на статический объект или объект в стеке.  
  
## <a name="remarks"></a>Примечания  
 Оба `RootReferences` и [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) вызываемые для уведомления профилировщика. Обычно профилировщик реализует одно из них, но не оба одновременно, так как данные, передаваемые `RootReferences2` является надмножеством информации, переданной в `RootReferences`.  
  
 Существует возможность `rootRefIds` массив должен содержать пустой объект. Например все ссылки на объекты, объявленные в стеке, рассматриваются как корни сборщиком мусора и всегда будет считаться.  
  
 Идентификаторы объектов, возвращенных `RootReferences` являются недопустимыми во время обратного вызова, так как сборка мусора может находиться в процессе перемещения объектов из старого адреса в новые адреса. Таким образом, профилировщики не должны пытаться проверять объекты во время `RootReferences` вызова. Когда [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) является именем, все объекты были перемещены в новые расположения и можно безопасно проверить.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)

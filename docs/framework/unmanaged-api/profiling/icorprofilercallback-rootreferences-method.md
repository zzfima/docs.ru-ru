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
ms.openlocfilehash: 9c96cacf508ef5c056a1ff4469247393fdfb9e9e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444472"
---
# <a name="icorprofilercallbackrootreferences-method"></a>Метод ICorProfilerCallback::RootReferences
Уведомляет профилировщик о получении сведений о корневых ссылках после сборки мусора.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT RootReferences(  
    [in] ULONG    cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[] );  
```  
  
## <a name="parameters"></a>Параметры  
 `cRootRefs`  
 окне Число ссылок в массиве `rootRefIds`.  
  
 `rootRefIds`  
 окне Массив идентификаторов объектов, ссылающихся либо на статический объект, либо на объект в стеке.  
  
## <a name="remarks"></a>Примечания  
 Для уведомления профилировщика вызываются `RootReferences` и [ICorProfilerCallback2:: RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) . Как правило, профилировщики реализуют один или другой, но не оба, так как сведения, передаваемые в `RootReferences2`, являются надмножеством, передаваемыми `RootReferences`.  
  
 Массив `rootRefIds` может содержать объект null. Например, все ссылки на объекты, объявленные в стеке, рассматриваются сборщиком мусора как корни и всегда будут сообщать о них.  
  
 Идентификаторы объектов, возвращаемые `RootReferences`, недопустимы в самом обратном вызове, так как сборка мусора может находиться в процессе перемещения объектов из старых адресов в новые адреса. Таким образом, профилировщики не должны пытаться проверять объекты во время вызова `RootReferences`. При вызове [ICorProfilerCallback2:: GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) все объекты были перемещены в новые расположения и могут быть безопасно проверены.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)

---
title: Метод ICorProfilerCallback::ObjectReferences
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ObjectReferences
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ObjectReferences
helpviewer_keywords:
- ObjectReferences method [.NET Framework profiling]
- ICorProfilerCallback::ObjectReferences method [.NET Framework profiling]
ms.assetid: dd5e9b64-b4a3-4ba6-9be6-ddb540f4ffcf
topic_type:
- apiref
ms.openlocfilehash: 6e6cc44c2f9028c0e26c4f933242cad93e3a98c3
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866095"
---
# <a name="icorprofilercallbackobjectreferences-method"></a>Метод ICorProfilerCallback::ObjectReferences
Уведомляет профилировщик об объектах в памяти, на которые ссылается указанный объект.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ObjectReferences(  
    [in]  ObjectID objectId,  
    [in]  ClassID  classId,  
    [in]  ULONG    cObjectRefs,  
    [in, size_is(cObjectRefs)] ObjectID objectRefIds[] );  
```  
  
## <a name="parameters"></a>Параметры  
 `objectId`  
 окне Идентификатор объекта, ссылающегося на объекты.  
  
 `classId`  
 окне Идентификатор класса, экземпляр которого является указанным объектом.  
  
 `cObjectRefs`  
 окне Количество объектов, на которые ссылается указанный объект (то есть количество элементов в массиве `objectRefIds`).  
  
 `objectRefIds`  
 окне Массив идентификаторов объектов, на которые ссылается `objectId`.  
  
## <a name="remarks"></a>Заметки  
 Метод `ObjectReferences` вызывается для каждого объекта, остающегося в куче после завершения сборки мусора. Если профилировщик возвращает ошибку из этого обратного вызова, службы профилирования будут прекращены вызовом этого обратного вызова до следующей сборки мусора.  
  
 Обратный вызов `ObjectReferences` можно использовать в сочетании с обратным вызовом [ICorProfilerCallback:: RootReferences](icorprofilercallback-rootreferences-method.md) , чтобы создать полный граф ссылки на объект для среды выполнения. Среда CLR гарантирует, что каждая ссылка на объект выводится только один раз методом `ObjectReferences`.  
  
 Идентификаторы объектов, возвращаемые `ObjectReferences`, недопустимы во время обратного вызова, так как сборка мусора может находиться в середине перемещения объектов. Таким образом, профилировщики не должны пытаться проверять объекты во время вызова `ObjectReferences`. При вызове [ICorProfilerCallback2:: GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) сборка мусора завершается, и проверка может быть безопасно выполнена.  
  
 Значение NULL `ClassId` указывает, что `objectId` имеет тип, выгружаемый.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)

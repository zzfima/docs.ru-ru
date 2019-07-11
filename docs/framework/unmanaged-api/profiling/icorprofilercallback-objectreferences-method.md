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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4141c79502dae89ec228e4e39da121615f292786
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782976"
---
# <a name="icorprofilercallbackobjectreferences-method"></a>Метод ICorProfilerCallback::ObjectReferences
Уведомляет профилировщик об объектах в памяти, на которые ссылаются заданным объектом.  
  
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
 [in] Идентификатор объекта, который ссылается на объекты.  
  
 `classId`  
 [in] Идентификатор, указанный объект является экземпляром класса.  
  
 `cObjectRefs`  
 [in] Число объектов, на которые ссылается указанный объект (то есть, количество элементов в `objectRefIds` массива).  
  
 `objectRefIds`  
 [in] Массив идентификаторов объектов, на которые ссылаются по `objectId`.  
  
## <a name="remarks"></a>Примечания  
 `ObjectReferences` Метод вызывается для каждого объекта, оставшихся в куче, после завершения сбора мусора. Если профилировщик возвращает сообщение об ошибке из этого обратного вызова, профилирующей службы будет прекратить вызов этой функции обратного вызова до следующей сборки мусора.  
  
 `ObjectReferences` Обратного вызова можно использовать в сочетании с [ICorProfilerCallback::RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) обратного вызова, чтобы создать диаграмму полный объект ссылки для среды выполнения. Среда CLR (CLR) гарантирует, что каждая ссылка объекта выводится только один раз `ObjectReferences` метод.  
  
 Идентификаторы объектов, возвращенных `ObjectReferences` являются недопустимыми во время обратного вызова, так как сборка мусора может находиться в процессе перемещения объектов. Таким образом, профилировщики не должны пытаться проверять объекты во время `ObjectReferences` вызова. Когда [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) вызывается сборке мусора коллекции завершена, и можно безопасно выполнить проверку.  
  
 Значение null `ClassId` указывает, что `objectId` имеет тип, который выгружается.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)

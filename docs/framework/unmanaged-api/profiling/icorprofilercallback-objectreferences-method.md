---
title: "Метод ICorProfilerCallback::ObjectReferences"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ObjectReferences
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ObjectReferences
helpviewer_keywords:
- ObjectReferences method [.NET Framework profiling]
- ICorProfilerCallback::ObjectReferences method [.NET Framework profiling]
ms.assetid: dd5e9b64-b4a3-4ba6-9be6-ddb540f4ffcf
topic_type: apiref
caps.latest.revision: "18"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5cdebc1984f86d3801759f8f987df8fb89d82e3a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackobjectreferences-method"></a>Метод ICorProfilerCallback::ObjectReferences
Уведомляет профилировщик об объектах в памяти, на которые ссылаются заданным объектом.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT ObjectReferences(  
    [in]  ObjectID objectId,  
    [in]  ClassID  classId,  
    [in]  ULONG    cObjectRefs,  
    [in, size_is(cObjectRefs)] ObjectID objectRefIds[] );  
```  
  
#### <a name="parameters"></a>Параметры  
 `objectId`  
 [in] Идентификатор объекта, который ссылается на объекты.  
  
 `classId`  
 [in] Идентификатор, указанный объект является экземпляром класса.  
  
 `cObjectRefs`  
 [in] Число объектов ссылается указанный объект (то есть, количество элементов в `objectRefIds` массива).  
  
 `objectRefIds`  
 [in] Массив идентификаторов объектов, на которые ссылаются по `objectId`.  
  
## <a name="remarks"></a>Примечания  
 `ObjectReferences` Метод вызывается для каждого объекта, оставшихся в куче после завершения сборки мусора. Если профилировщик возвращает сообщение об ошибке из этого обратного вызова, профилирующей службы перестанет работать, вызов этого обратного вызова до следующей сборки мусора.  
  
 `ObjectReferences` Обратного вызова можно использовать в сочетании с [ICorProfilerCallback::RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) обратного вызова, чтобы создать граф ссылок полный объект среды выполнения. Общеязыковая среда выполнения (CLR) гарантирует, что каждая ссылка объекта выводится только один раз `ObjectReferences` метод.  
  
 Идентификаторы объектов, возвращенных `ObjectReferences` являются недопустимыми во время обратного вызова, так как сборка мусора может находиться в процессе перемещения объектов. Таким образом, профилировщик должен не пытаться проверять объекты во время `ObjectReferences` вызова. Когда [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) вызывается сборке мусора коллекции завершена, и можно безопасно выполнить проверку.  
  
 Значение null `ClassId` указывает, что `objectId` имеет тип, который будет выгружен.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)

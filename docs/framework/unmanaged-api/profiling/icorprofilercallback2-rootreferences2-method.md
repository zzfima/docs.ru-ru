---
title: "Метод ICorProfilerCallback2::RootReferences2"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback2.RootReferences2
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback2::RootReferences2
helpviewer_keywords:
- RootReferences2 method [.NET Framework profiling]
- ICorProfilerCallback2::RootReferences2 method [.NET Framework profiling]
ms.assetid: 55a2f907-d216-42eb-8f2f-e5d59c2eebd6
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 29a5a3051b75df18a08498369aa5707a53caf75f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback2rootreferences2-method"></a>Метод ICorProfilerCallback2::RootReferences2
Уведомляет профилировщик о корневых ссылках после сборки мусора. Этот метод является расширением [ICorProfilerCallback::RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) метод.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT RootReferences2(  
    [in] ULONG  cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[],  
    [in, size_is(cRootRefs)] COR_PRF_GC_ROOT_KIND rootKinds[],  
    [in, size_is(cRootRefs)] COR_PRF_GC_ROOT_FLAGS rootFlags[],  
    [in, size_is(cRootRefs)] UINT_PTR rootIds[]);  
```  
  
#### <a name="parameters"></a>Параметры  
 `cRootRefs`  
 [in] Число элементов в `rootRefIds`, `rootKinds`, `rootFlags`, и `rootIds` массивов.  
  
 `rootRefIds`  
 [in] Массив идентификаторов объектов, каждый из которых ссылается на статический объект или объект в стеке. Элементы в `rootKinds` массива предоставляют сведения для классификации соответствующих элементов в `rootRefIds` массива.  
  
 `rootKinds`  
 [in] Массив [COR_PRF_GC_ROOT_KIND](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-kind-enumeration.md) значения, указывающие тип корне сборки мусора.  
  
 `rootFlags`  
 [in] Массив [COR_PRF_GC_ROOT_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-flags-enumeration.md) значения, описывающие свойства корне сборки мусора.  
  
 `rootIds`  
 [in] Массив UINT_PTR значений этой точки в целое число, содержащий дополнительные сведения о корне сборки мусора, в зависимости от значения `rootKinds` параметра.  
  
 Если типом корня является стек, ИД корня соответствует функции, содержащей переменную. Если идентификатор корня равен 0, функция является неименованные внутренней среде CLR. Если типом корня является дескриптор, идентификатор корня соответствует дескриптору сборки мусора. Для других типов корня идентификатор является непрозрачным значением и его следует игнорировать.  
  
## <a name="remarks"></a>Примечания  
 `rootRefIds`, `rootKinds`, `rootFlags`, И `rootIds` массивы являются параллельными массивами. То есть `rootRefIds[i]`, `rootKinds[i]`, `rootFlags[i]`, и `rootIds[i]` относятся тот же корневой.  
  
 Оба `RootReferences` и `RootReferences2` вызывается для уведомления профилировщика. Обычно профилировщик реализует один метод или другой, но не оба, так как сведения передаются в `RootReferences2` является надмножеством переданный `RootReferences`.  
  
 Возможно, для операций в `rootRefIds` должно быть равно нулю, что означает, что соответствующий корневой ссылки имеет значение null, а не ссылки на объект в управляемой куче.  
  
 Идентификаторы объектов, возвращенных `RootReferences2` являются недопустимыми во время обратного вызова, так как сборка мусора может находиться в процессе перемещения объектов со старых адресов на новые адреса. В связи с этим профилировщикам не следует пытаться проверять объекты во время вызова `RootReferences2`. Когда [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) — вызывается, все объекты были перемещены в новые расположения и можно безопасно проверить.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [Интерфейс ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)

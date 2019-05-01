---
title: Метод ICorProfilerCallback2::RootReferences2
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.RootReferences2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::RootReferences2
helpviewer_keywords:
- RootReferences2 method [.NET Framework profiling]
- ICorProfilerCallback2::RootReferences2 method [.NET Framework profiling]
ms.assetid: 55a2f907-d216-42eb-8f2f-e5d59c2eebd6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 09616243aef272be041573864effd25017cc65c1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992034"
---
# <a name="icorprofilercallback2rootreferences2-method"></a>Метод ICorProfilerCallback2::RootReferences2
Уведомляет профилировщик о корневыми ссылками, после сборки мусора. Этот метод является расширением [ICorProfilerCallback::RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) метод.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT RootReferences2(  
    [in] ULONG  cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[],  
    [in, size_is(cRootRefs)] COR_PRF_GC_ROOT_KIND rootKinds[],  
    [in, size_is(cRootRefs)] COR_PRF_GC_ROOT_FLAGS rootFlags[],  
    [in, size_is(cRootRefs)] UINT_PTR rootIds[]);  
```  
  
## <a name="parameters"></a>Параметры  
 `cRootRefs`  
 [in] Число элементов в `rootRefIds`, `rootKinds`, `rootFlags`, и `rootIds` массивов.  
  
 `rootRefIds`  
 [in] Массив идентификаторов объектов, каждый из которых ссылается на статический объект или объект в стеке. Элементы в `rootKinds` массива предоставляют сведения для классификации соответствующих элементов в `rootRefIds` массива.  
  
 `rootKinds`  
 [in] Массив [COR_PRF_GC_ROOT_KIND](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-kind-enumeration.md) значения, указывающие тип корня сборки мусора.  
  
 `rootFlags`  
 [in] Массив [COR_PRF_GC_ROOT_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-flags-enumeration.md) значения, описывающие свойства корня сборки мусора.  
  
 `rootIds`  
 [in] Массив UINT_PTR значений, которые указывают на целое число, содержащий дополнительные сведения о корне сборки мусора, в зависимости от значения `rootKinds` параметра.  
  
 Тип корня представляет собой стек, корневой является ли идентификатор для функции, содержащую нужную переменную. Если идентификатор корня равен 0, функция является безымянной внутренней среде CLR. Если тип корневого элемента является дескриптором, идентификатор корня соответствует дескриптору сборки мусора. Для других типов корня идентификатор является непрозрачным значением и его следует игнорировать.  
  
## <a name="remarks"></a>Примечания  
 `rootRefIds`, `rootKinds`, `rootFlags`, И `rootIds` массивы являются параллельными массивами. То есть `rootRefIds[i]`, `rootKinds[i]`, `rootFlags[i]`, и `rootIds[i]` относятся таким же корнем.  
  
 Оба `RootReferences` и `RootReferences2` вызываемые для уведомления профилировщика. Обычно профилировщик реализует один метод или другой, но не оба, так как данные, передаваемые `RootReferences2` является надмножеством информации, переданной в `RootReferences`.  
  
 Возможно, для операций в `rootRefIds` должно быть равно нулю, что означает, что соответствующая ссылка корневой имеет значение null и не ссылается на объект в управляемой куче.  
  
 Идентификаторы объектов, возвращенных `RootReferences2` являются недопустимыми во время обратного вызова, так как сборка мусора может находиться в процессе перемещения объектов из старого адреса в новые адреса. В связи с этим профилировщикам не следует пытаться проверять объекты во время вызова `RootReferences2`. Когда [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) является именем, все объекты были перемещены в новые расположения и можно безопасно проверить.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [Интерфейс ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)

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
ms.openlocfilehash: a9ce9a7a56847efcadf09924ffc56c41f20a1c58
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865731"
---
# <a name="icorprofilercallback2rootreferences2-method"></a>Метод ICorProfilerCallback2::RootReferences2
Уведомляет профилировщик о корневых ссылках после сборки мусора. Этот метод является расширением метода [ICorProfilerCallback:: RootReferences](icorprofilercallback-rootreferences-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT RootReferences2(  
    [in] ULONG  cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[],  
    [in, size_is(cRootRefs)] COR_PRF_GC_ROOT_KIND rootKinds[],  
    [in, size_is(cRootRefs)] COR_PRF_GC_ROOT_FLAGS rootFlags[],  
    [in, size_is(cRootRefs)] UINT_PTR rootIds[]);  
```  
  
## <a name="parameters"></a>Параметры  
 `cRootRefs`  
 окне Число элементов в массивах `rootRefIds`, `rootKinds`, `rootFlags`и `rootIds`.  
  
 `rootRefIds`  
 окне Массив идентификаторов объектов, каждый из которых ссылается на статический объект или объект в стеке. Элементы в массиве `rootKinds` предоставляют сведения для классификации соответствующих элементов в массиве `rootRefIds`.  
  
 `rootKinds`  
 окне Массив значений [COR_PRF_GC_ROOT_KIND](cor-prf-gc-root-kind-enumeration.md) , указывающих тип корня сборки мусора.  
  
 `rootFlags`  
 окне Массив значений [COR_PRF_GC_ROOT_FLAGS](cor-prf-gc-root-flags-enumeration.md) , описывающих свойства корня сборки мусора.  
  
 `rootIds`  
 окне Массив значений UINT_PTR, указывающих на целое число, которое содержит дополнительные сведения об корне сборки мусора в зависимости от значения параметра `rootKinds`.  
  
 Если корневым типом является стек, то для функции, содержащей переменную, используется корневой идентификатор. Если этот корневой идентификатор равен 0, функция является неименованной функцией, которая является внутренней для среды CLR. Если корневой тип является обработчиком, корневой идентификатор — для обработчика сборки мусора. Для других корневых типов идентификатор является непрозрачным значением и должен игнорироваться.  
  
## <a name="remarks"></a>Заметки  
 Массивы `rootRefIds`, `rootKinds`, `rootFlags`и `rootIds` являются параллельными массивами. То есть `rootRefIds[i]`, `rootKinds[i]`, `rootFlags[i]`и `rootIds[i]` имеют один и тот же корень.  
  
 Для уведомления профилировщика вызываются `RootReferences` и `RootReferences2`. Профилировщики, как правило, реализуют один метод или другой, но не оба, так как сведения, передаваемые в `RootReferences2`, являются надмножеством, передаваемыми `RootReferences`.  
  
 Записи в `rootRefIds` могут быть равны нулю, что означает, что соответствующая корневая ссылка имеет значение NULL и не ссылается на объект в управляемой куче.  
  
 Идентификаторы объектов, возвращаемые `RootReferences2`, недопустимы в самом обратном вызове, так как сборка мусора может находиться в процессе перемещения объектов из старых адресов в новые адреса. В связи с этим профилировщикам не следует пытаться проверять объекты во время вызова `RootReferences2`. При вызове [ICorProfilerCallback2:: GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) все объекты были перемещены в новые расположения и могут быть безопасно проверены.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
- [Интерфейс ICorProfilerCallback2](icorprofilercallback2-interface.md)

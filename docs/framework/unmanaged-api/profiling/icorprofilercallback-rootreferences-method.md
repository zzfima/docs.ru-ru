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
ms.openlocfilehash: 467d065ab4d47e698c7043697ebe2ccf5f98a3cf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallbackrootreferences-method"></a>Метод ICorProfilerCallback::RootReferences
Уведомляет профилировщик с информацией о корневых ссылках после сборки мусора.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT RootReferences(  
    [in] ULONG    cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[] );  
```  
  
#### <a name="parameters"></a>Параметры  
 `cRootRefs`  
 [in] Число ссылок в `rootRefIds` массива.  
  
 `rootRefIds`  
 [in] Массив идентификаторов объектов, которые ссылаются на статический объект или объект в стеке.  
  
## <a name="remarks"></a>Примечания  
 Оба `RootReferences` и [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) вызывается для уведомления профилировщика. Обычно профилировщик реализует один из них, но не одновременно, так как сведения передаются в `RootReferences2` является надмножеством переданный `RootReferences`.  
  
 Существует возможность `rootRefIds` массива содержит пустой объект. Например все ссылки на объекты, объявленные в стеке, считаются корней сборщиком мусора и будут отображаться.  
  
 Идентификаторы объектов, возвращенных `RootReferences` являются недопустимыми во время обратного вызова, так как сборка мусора может находиться в процессе перемещения объектов со старых адресов на новые адреса. Таким образом, профилировщик должен не пытаться проверять объекты во время `RootReferences` вызова. Когда [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) — вызывается, все объекты были перемещены в новые расположения и можно безопасно проверить.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)

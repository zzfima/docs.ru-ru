---
title: Метод ICorProfilerCallback::ExceptionCatcherEnter
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionCatcherEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCatcherEnter
helpviewer_keywords:
- ICorProfilerCallback::ExceptionCatcherEnter method [.NET Framework profiling]
- ExceptionCatcherEnter method [.NET Framework profiling]
ms.assetid: 41462329-a648-46f0-ae6d-728b94c31aa9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d8a87fb05a49c2813cf4d299c3663419be1640b4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallbackexceptioncatcherenter-method"></a>Метод ICorProfilerCallback::ExceptionCatcherEnter
Уведомляет профилировщик, управление передается соответствующему `catch` блока.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT ExceptionCatcherEnter(  
    [in] FunctionID functionId,  
    [in] ObjectID   objectId);  
```  
  
#### <a name="parameters"></a>Параметры  
 `functionId`  
 [in] Функция, содержащая идентификатор `catch` блока.  
  
 `objectId`  
 [in] Идентификатор обрабатываемое исключение.  
  
## <a name="remarks"></a>Примечания  
 `ExceptionCatcherEnter` Метод вызывается только в том случае, если точка catch находится в коде, скомпилированном с помощью время JIT-компилятора. Исключение, которое будет перехвачено в неуправляемый код или во внутреннем коде среды выполнения не будет вызывать это уведомление. `objectId` Значение передается еще раз с момента сбора мусора может перемещен объект с момента `ExceptionThrown` уведомления.  
  
 Профилировщик не должен блокироваться при реализации этого метода, так как стек может находиться в состоянии, допускающем сборку мусора, и поэтому не удастся включить сборку мусора. Если здесь профилировщик блокируется и выполняется сборка мусора, среда выполнения будет блокироваться до возвращает этот обратный вызов.  
  
 Реализация этого метода профилировщика не должны вызывать управляемый код или каким-либо образом вызывать распределения управляемой памяти.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [Метод ExceptionCatcherLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)

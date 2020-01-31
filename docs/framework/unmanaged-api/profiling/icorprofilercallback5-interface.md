---
title: Интерфейс ICorProfilerCallback5
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback5
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback5
helpviewer_keywords:
- ICorProfilerCallback5 interface [.NET Framework profiling]
ms.assetid: 61d2e9ef-5f1f-4771-8847-239616e35d84
topic_type:
- apiref
ms.openlocfilehash: 7981e7d2d2a4588e56d3c30d0ede2d003fdcd32e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865029"
---
# <a name="icorprofilercallback5-interface"></a>Интерфейс ICorProfilerCallback5
Дополняет сведения, чтобы помочь профилировщику определить полное закрытие динамических объектов при использовании метода [ICorProfilerCallback:: RootReferences](icorprofilercallback-rootreferences-method.md) или [ICorProfilerCallback2:: RootReferences2](icorprofilercallback2-rootreferences2-method.md) вместе с методами [ICorProfilerCallback:: ObjectReferences](icorprofilercallback-objectreferences-method.md) и [ConditionalWeakTableElementReferences](icorprofilercallback5-conditionalweaktableelementreferences-method.md) .  
  
 Для подписки на уведомления, связанные с зависимыми дескрипторами профилировщик управляемой памяти должен реализовать `ICorProfilerCallback5`.  
  
## <a name="remarks"></a>Заметки  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод ConditionalWeakTableElementReferences](icorprofilercallback5-conditionalweaktableelementreferences-method.md)|Идентифицирует транзитивное замыкание объектов, на которые ссылаются эти корневые элементы как через прямые ссылки на поля члена, так и через зависимости `ConditionalWeakTable`.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейсы профилирования](profiling-interfaces.md)
- [Интерфейс ICorProfilerCallback2](icorprofilercallback2-interface.md)

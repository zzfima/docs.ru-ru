---
title: Интерфейс ICorDebugEval
ms.date: 03/30/2017
api_name:
- ICorDebugEval
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval
helpviewer_keywords:
- ICorDebugEval interface [.NET Framework debugging]
ms.assetid: 3a5c9815-832d-47e1-b7f7-bbba135d7cf1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 745917af176de47999737c87833c23df9c75ea7b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59080869"
---
# <a name="icordebugeval-interface"></a>Интерфейс ICorDebugEval

Предоставляет методы, позволяющие отладчику выполнять код в контексте отлаживаемого кода.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Abort](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-abort-method.md)|Прерывает вычисление это `ICorDebugEval` объект в данный момент выполняет.|  
|[Метод CallFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-callfunction-method.md)|Настраивает вызов указанной функции. (Устарело в .NET Framework версии 2.0; используйте [ICorDebugEval2::CallParameterizedFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md) вместо.)|  
|[Метод CreateValue](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-createvalue-method.md)|Получает указатель интерфейса на объект «ICorDebugValue» указанного типа, с начальным значением, равным нулю или null. (Устарело в .NET Framework 2.0; используйте [ICorDebugEval2::CreateValueForType](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md) вместо.)|  
|[Метод GetResult](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-getresult-method.md)|Получает указатель интерфейса на `ICorDebugValue` , содержащий результаты оценки.|  
|[Метод GetThread](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-getthread-method.md)|Получает указатель интерфейса, для которых эта оценка выполняется или будет выполняться «ICorDebugThread».|  
|[Метод IsActive](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-isactive-method.md)|Получает значение, указывающее, является ли это `ICorDebugEval` объекта в данный момент.|  
|[Метод NewArray](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-newarray-method.md)|Выделяет новый массив элементов указанного типа и измерений. (Устарело в .NET Framework 2.0; используйте [ICorDebugEval2::NewParameterizedArray](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md) вместо.)|  
|[Метод NewObject](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-newobject-method.md)|Выделяет новый экземпляр объекта и вызывает заданный метод конструктора. (Устарело в .NET Framework 2.0; используйте [ICorDebugEval2::NewParameterizedObject](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md) вместо.)|  
|[Метод NewObjectNoConstructor](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-newobjectnoconstructor-method.md)|Выделяет новый экземпляр объекта указанного типа, не пытается вызвать метод-конструктор. (Устарело в .NET Framework 2.0; используйте [ICorDebugEval2::NewParameterizedObjectNoConstructor](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md) вместо.)|  
|[Метод NewString](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-newstring-method.md)|Выделяет новый строковый объект с указанным содержимым.|  
  
## <a name="remarks"></a>Примечания  
 `ICorDebugEval` Объект создается в контексте определенного потока, который используется для выполнения оценок. Все объекты и типы, используемые в данной оценке должен находиться на том же домене приложения. Этот домен приложения не должны совпадать с текущего домена приложения потока. Оценки могут быть вложенными.  
  
 Пока не вызовет отладчик не выполняйте операции вычисления [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md), а затем получает [ICorDebugManagedCallback::EvalComplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-evalcomplete-method.md) обратного вызова. Если вам нужно использовать функцию оценки не разрешение запуска других потоков, приостановить потоки либо при помощи [ICorDebugController::SetAllThreadsDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md) или [ICorDebugController::Stop](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md)перед вызовом [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md).  
  
 Поскольку пользовательский код выполняется вычисление во время выполнения, могут возникать любого события отладки, включая загрузки класса и точки останова. Отладчик будет получать обратные вызовы, в обычном режиме, для этих событий. Состояние оценки будет рассматриваться как часть проверки состояния программы в обычном режиме. Цепочка стека будет `CHAIN_FUNC_EVAL` цепочки (см. в разделе «CorDebugStepReason» перечисления и [ICorDebugChain::GetReason](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md) метод). Полный API отладчика будет продолжать работу в обычном режиме.  
  
 Если заблокированной или бесконечный зацикливания пользовательский код может никогда не завершен. В этом случае необходимо вызвать [ICorDebugEval::Abort](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-abort-method.md) перед возобновлением работы программы.  
  
> [!NOTE]
>  Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

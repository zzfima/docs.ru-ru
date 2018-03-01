---
title: "ICorDebugEval интерфейс1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 77e97e31a20c392eebae1b373bb1af53f87c23e9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugeval-interface1"></a>ICorDebugEval интерфейс1
Предоставляет методы, позволяющие отладчику выполнять код в контексте отлаживаемого кода.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание:|  
|------------|-----------------|  
|[Метод Abort](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-abort-method.md)|Прерывает вычисление это `ICorDebugEval` объекта в данный момент производит.|  
|[Метод CallFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-callfunction-method.md)|Настраивает вызов указанной функции. (Устарело в .NET Framework версии 2.0; используйте [ICorDebugEval2::CallParameterizedFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md) вместо.)|  
|[Метод CreateValue](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-createvalue-method.md)|Получает указатель интерфейса на объект «ICorDebugValue» указанного типа с начальным значением, равным нулю или null. (Устарело в .NET Framework 2.0; используйте [ICorDebugEval2::CreateValueForType](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md) вместо.)|  
|[Метод GetResult](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-getresult-method.md)|Возвращает указатель интерфейса `ICorDebugValue` , содержащий результаты оценки.|  
|[Метод GetThread](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-getthread-method.md)|Получает указатель интерфейса, для которых эта оценка выполняется или будет выполняться «ICorDebugThread».|  
|[Метод IsActive](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-isactive-method.md)|Возвращает значение, указывающее, является ли это `ICorDebugEval` объекта в данный момент.|  
|[Метод NewArray](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-newarray-method.md)|Выделяет новый массив с заданным типом элементов и измерений. (Устарело в .NET Framework 2.0; используйте [ICorDebugEval2::NewParameterizedArray](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md) вместо.)|  
|[Метод NewObject](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-newobject-method.md)|Выделяет новый экземпляр объекта и вызывает заданный метод конструктора. (Устарело в .NET Framework 2.0; используйте [ICorDebugEval2::NewParameterizedObject](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md) вместо.)|  
|[Метод NewObjectNoConstructor](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-newobjectnoconstructor-method.md)|Выделяет новый экземпляр объекта указанного типа, не предпринимая попытки вызвать метод конструктора. (Устарело в .NET Framework 2.0; используйте [ICorDebugEval2::NewParameterizedObjectNoConstructor](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md) вместо.)|  
|[Метод NewString](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-newstring-method.md)|Выделяет новый строковый объект с указанным содержимым.|  
  
## <a name="remarks"></a>Примечания  
 `ICorDebugEval` Объект создается в контексте определенного потока, который используется для выполнения оценок. Все объекты и типы, используемые в данной оценке должен находиться на том же домене приложения. Домен приложения не должны совпадать с текущего домена приложения потока. Оценки могут быть вложенными.  
  
 Операции вычисления не завершены, пока не отладчик вызывает [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md), а затем принимается [ICorDebugManagedCallback::EvalComplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-evalcomplete-method.md) обратного вызова. Если необходимо использовать функцию оценки не разрешение запуска других потоков, приостановить потоки с помощью [ICorDebugController::SetAllThreadsDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md) или [ICorDebugController::Stop](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md)перед вызовом [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md).  
  
 Поскольку пользовательский код выполняется во время вычисления, могут возникать все события отладки, включая загрузки класса и точки останова. Отладчик будет получать обратные вызовы, как обычно, для этих событий. Состояние оценки, будет отображаться как часть проверки состояния программы в обычном режиме. Цепочка стека будет `CHAIN_FUNC_EVAL` цепочки (в перечислении «CorDebugStepReason» и [ICorDebugChain::GetReason](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md) метода). Весь интерфейс API отладчика будет продолжать работу в обычном режиме.  
  
 Если взаимоблокировки или состояния бесконечного зацикливания пользовательский код может никогда не завершаются. В этом случае необходимо вызвать [ICorDebugEval::Abort](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-abort-method.md) перед возобновлением работы программы.  
  
> [!NOTE]
>  Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
    
    
    
 [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

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
ms.openlocfilehash: 33b1afca0b7b662cb7f922e20ba0d6d614c319f2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73085036"
---
# <a name="icordebugeval-interface"></a>Интерфейс ICorDebugEval

Предоставляет методы, позволяющие отладчику выполнять код в контексте отлаживаемого кода.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Abort](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-abort-method.md)|Прерывает вычисление, которое данный объект `ICorDebugEval` сейчас выполняет.|  
|[Метод CallFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-callfunction-method.md)|Настраивает вызов указанной функции. (Является устаревшим в .NET Framework версии 2,0; вместо этого используйте [ICorDebugEval2:: каллпараметеризедфунктион](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md) .)|  
|[Метод CreateValue](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-createvalue-method.md)|Получает указатель интерфейса на объект "ICorDebugValue" указанного типа с начальным нулевым значением или значением NULL. (Является устаревшим в .NET Framework 2,0; используйте вместо него [ICorDebugEval2:: креатевалуефортипе](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md) .)|  
|[Метод GetResult](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-getresult-method.md)|Возвращает указатель интерфейса на `ICorDebugValue`, содержащий результаты вычисления.|  
|[Метод GetThread](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-getthread-method.md)|Возвращает указатель интерфейса для "ICorDebugThread", в котором выполняется эта оценка или выполняется.|  
|[Метод IsActive](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-isactive-method.md)|Возвращает значение, указывающее, выполняется ли в данный момент объект `ICorDebugEval`.|  
|[Метод NewArray](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-newarray-method.md)|Выделяет новый массив указанного типа элемента и измерений. (Является устаревшим в .NET Framework 2,0; используйте вместо него [ICorDebugEval2:: NewParameterizedArray](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md) .)|  
|[Метод NewObject](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-newobject-method.md)|Выделяет новый экземпляр объекта и вызывает указанный метод конструктора. (Является устаревшим в .NET Framework 2,0; используйте вместо него [ICorDebugEval2:: невпараметеризедобжект](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md) .)|  
|[Метод NewObjectNoConstructor](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-newobjectnoconstructor-method.md)|Выделяет новый экземпляр объекта указанного типа без попытки вызова метода конструктора. (Является устаревшим в .NET Framework 2,0; используйте вместо него [ICorDebugEval2:: невпараметеризедобжектноконструктор](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md) .)|  
|[Метод NewString](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-newstring-method.md)|Выделяет новый строковый объект с указанным содержимым.|  
  
## <a name="remarks"></a>Заметки  
 Объект `ICorDebugEval` создается в контексте конкретного потока, используемого для выполнения оценок. Все объекты и типы, используемые в данной оценке, должны находиться в одном домене приложения. Этот домен приложения не должен совпадать с именем текущего домена приложения потока. Вычисления могут быть вложенными.  
  
 Операции оценки не завершаются до тех пор, пока отладчик не вызовет [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md), а затем получает обратный вызов [ICorDebugManagedCallback:: евалкомплете](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-evalcomplete-method.md) . Если необходимо использовать функцию оценки, не разрешая выполнение других потоков, приостановите потоки с помощью [ICorDebugController:: SetAllThreadsDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md) или [ICorDebugController:: Остановите](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md) перед вызовом [ ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md).  
  
 Поскольку пользовательский код выполняется при выполнении оценки, могут возникать любые события отладки, включая загрузку классов и точки останова. Для этих событий отладчик будет принимать обратные вызовы, как обычные. Состояние оценки будет рассматриваться как часть проверки нормального состояния программы. Цепочка стека будет представлять собой цепочку `CHAIN_FUNC_EVAL` (см. перечисление "Кордебугстепреасон" и метод [ICorDebugChain::-Reason](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md) ). Полный API отладчика продолжит работать в нормальном режиме.  
  
 В случае возникновения взаимоблокировки или бесконечной циклической ситуации код пользователя может никогда не завершиться. В этом случае необходимо вызвать метод [ICorDebugEval:: Abort](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-abort-method.md) , прежде чем возобновить работу программы.  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

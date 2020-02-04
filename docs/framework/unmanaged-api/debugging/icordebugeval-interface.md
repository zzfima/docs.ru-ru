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
ms.openlocfilehash: c9e2dc95bf78d95e5d608a8ce6e9462345c20a07
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788735"
---
# <a name="icordebugeval-interface"></a>Интерфейс ICorDebugEval

Предоставляет методы, позволяющие отладчику выполнять код в контексте отлаживаемого кода.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Abort](icordebugeval-abort-method.md)|Прерывает вычисление, которое данный объект `ICorDebugEval` сейчас выполняет.|  
|[Метод CallFunction](icordebugeval-callfunction-method.md)|Настраивает вызов указанной функции. (Является устаревшим в .NET Framework версии 2,0; вместо этого используйте [ICorDebugEval2:: каллпараметеризедфунктион](icordebugeval2-callparameterizedfunction-method.md) .)|  
|[Метод CreateValue](icordebugeval-createvalue-method.md)|Получает указатель интерфейса на объект "ICorDebugValue" указанного типа с начальным нулевым значением или значением NULL. (Является устаревшим в .NET Framework 2,0; используйте вместо него [ICorDebugEval2:: креатевалуефортипе](icordebugeval2-createvaluefortype-method.md) .)|  
|[Метод GetResult](icordebugeval-getresult-method.md)|Возвращает указатель интерфейса на `ICorDebugValue`, содержащий результаты вычисления.|  
|[Метод GetThread](icordebugeval-getthread-method.md)|Возвращает указатель интерфейса для "ICorDebugThread", в котором выполняется эта оценка или выполняется.|  
|[Метод IsActive](icordebugeval-isactive-method.md)|Возвращает значение, указывающее, выполняется ли в данный момент объект `ICorDebugEval`.|  
|[Метод NewArray](icordebugeval-newarray-method.md)|Выделяет новый массив указанного типа элемента и измерений. (Является устаревшим в .NET Framework 2,0; используйте вместо него [ICorDebugEval2:: NewParameterizedArray](icordebugeval2-newparameterizedarray-method.md) .)|  
|[Метод NewObject](icordebugeval-newobject-method.md)|Выделяет новый экземпляр объекта и вызывает указанный метод конструктора. (Является устаревшим в .NET Framework 2,0; используйте вместо него [ICorDebugEval2:: невпараметеризедобжект](icordebugeval2-newparameterizedobject-method.md) .)|  
|[Метод NewObjectNoConstructor](icordebugeval-newobjectnoconstructor-method.md)|Выделяет новый экземпляр объекта указанного типа без попытки вызова метода конструктора. (Является устаревшим в .NET Framework 2,0; используйте вместо него [ICorDebugEval2:: невпараметеризедобжектноконструктор](icordebugeval2-newparameterizedobjectnoconstructor-method.md) .)|  
|[Метод NewString](icordebugeval-newstring-method.md)|Выделяет новый строковый объект с указанным содержимым.|  
  
## <a name="remarks"></a>Заметки  
 Объект `ICorDebugEval` создается в контексте конкретного потока, используемого для выполнения оценок. Все объекты и типы, используемые в данной оценке, должны находиться в одном домене приложения. Этот домен приложения не должен совпадать с именем текущего домена приложения потока. Вычисления могут быть вложенными.  
  
 Операции оценки не завершаются до тех пор, пока отладчик не вызовет [ICorDebugController:: Continue](icordebugcontroller-continue-method.md), а затем получает обратный вызов [ICorDebugManagedCallback:: евалкомплете](icordebugmanagedcallback-evalcomplete-method.md) . Если необходимо использовать функцию оценки, не разрешая выполнение других потоков, приостановите потоки с помощью [ICorDebugController:: SetAllThreadsDebugState](icordebugcontroller-setallthreadsdebugstate-method.md) или [ICorDebugController:: Остановите](icordebugcontroller-stop-method.md) перед вызовом [ICorDebugController:: Continue](icordebugcontroller-continue-method.md).  
  
 Поскольку пользовательский код выполняется при выполнении оценки, могут возникать любые события отладки, включая загрузку классов и точки останова. Для этих событий отладчик будет принимать обратные вызовы, как обычные. Состояние оценки будет рассматриваться как часть проверки нормального состояния программы. Цепочка стека будет представлять собой цепочку `CHAIN_FUNC_EVAL` (см. перечисление "Кордебугстепреасон" и метод [ICorDebugChain::-Reason](icordebugchain-getreason-method.md) ). Полный API отладчика продолжит работать в нормальном режиме.  
  
 В случае возникновения взаимоблокировки или бесконечной циклической ситуации код пользователя может никогда не завершиться. В этом случае необходимо вызвать метод [ICorDebugEval:: Abort](icordebugeval-abort-method.md) , прежде чем возобновить работу программы.  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейсы отладки](debugging-interfaces.md)

---
title: Интерфейс ICorDebugFunction
ms.date: 03/30/2017
api_name:
- ICorDebugFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction
helpviewer_keywords:
- ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: 783faea9-8083-41c1-b04a-51a81ac4c8f3
topic_type:
- apiref
ms.openlocfilehash: eb2b1e218314be01898ce90c4378fb713f9bf6ba
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137854"
---
# <a name="icordebugfunction-interface"></a>Интерфейс ICorDebugFunction

Представляет управляемую функцию или метод.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод CreateBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-createbreakpoint-method.md)|Создает точку останова в начале этой функции.|  
|[Метод GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getclass-method.md)|Возвращает объект ICorDebugClass, представляющий класс, членом которого является эта функция.|  
|[Метод GetCurrentVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md)|Возвращает номер версии последнего изменения, внесенного в эту функцию.|  
|[Метод GetILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getilcode-method.md)|Возвращает код MSIL для этой функции.|  
|[Метод GetLocalVarSigToken](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getlocalvarsigtoken-method.md)|Возвращает маркер метаданных для сигнатуры локальной переменной функции, представленной данным экземпляром `ICorDebugFunction`.|  
|[Метод GetModule](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getmodule-method.md)|Возвращает модуль, в котором определена эта функция.|  
|[Метод GetNativeCode](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getnativecode-method.md)|Получает машинный код для этой функции.|  
|[Метод GetToken](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-gettoken-method.md)|Возвращает маркер метаданных для этой функции.|  
  
## <a name="remarks"></a>Заметки  
 Интерфейс `ICorDebugFunction` не представляет функцию с параметрами универсального типа. Например, экземпляр `ICorDebugFunction` будет представлять `Func<T>`, но не `Func<string>`. Вызовите метод [ICorDebugILFrame2:: енумератетипепараметерс](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md) , чтобы получить параметры универсального типа.  
  
 Связь между маркером метаданных метода, `mdMethodDef`и `ICorDebugFunction`ным объектом метода зависит от того, разрешена ли функция "изменить и продолжить" для функции:  
  
- Если функция "изменить и продолжить" не разрешена для функции, между объектом `ICorDebugFunction` и маркером `mdMethodDef` существует связь "один к одному". То есть функция имеет один объект `ICorDebugFunction` и один маркер `mdMethodDef`.  
  
- Если функция "изменить и продолжить" разрешена для функции, между объектом `ICorDebugFunction` и маркером `mdMethodDef` существует связь "многие к одному". Это значит, что функция может иметь много экземпляров `ICorDebugFunction`, по одной для каждой версии функции, но только один маркер `mdMethodDef`.  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:**  Коргуидс. lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

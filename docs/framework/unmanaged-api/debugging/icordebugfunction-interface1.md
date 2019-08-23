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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ae65c59efe1d925b5e058e8664d1e093fdfec875
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917207"
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
|[Метод GetLocalVarSigToken](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getlocalvarsigtoken-method.md)|Возвращает маркер метаданных для сигнатуры локальной переменной функции, представленной этим `ICorDebugFunction` экземпляром.|  
|[Метод GetModule](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getmodule-method.md)|Возвращает модуль, в котором определена эта функция.|  
|[Метод GetNativeCode](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getnativecode-method.md)|Получает машинный код для этой функции.|  
|[Метод GetToken](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-gettoken-method.md)|Возвращает маркер метаданных для этой функции.|  
  
## <a name="remarks"></a>Примечания  
 `ICorDebugFunction` Интерфейс не представляет функцию с параметрами универсального типа. Например, `ICorDebugFunction` экземпляр будет представлять `Func<T>` , но не `Func<string>`. Вызовите метод [ICorDebugILFrame2:: енумератетипепараметерс](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md) , чтобы получить параметры универсального типа.  
  
 Связь между маркером `mdMethodDef`метаданных метода, и `ICorDebugFunction` объектом метода зависит от того, разрешена ли функция "изменить и продолжить" для функции:  
  
- Если функция "изменить и продолжить" не разрешена для функции, между `ICorDebugFunction` объектом `mdMethodDef` и токеном существует связь "один к одному". То есть функция имеет один `ICorDebugFunction` объект и один `mdMethodDef` токен.  
  
- Если для функции разрешен режим "изменить и продолжить", между `ICorDebugFunction` объектом `mdMethodDef` и токеном существует связь "многие к одному". Это значит, что функция может иметь много экземпляров `ICorDebugFunction`, по одной для каждой версии функции, но только один `mdMethodDef` токен.  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug. idl, CorDebug. h  
  
 **Библиотечная**  Коргуидс. lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

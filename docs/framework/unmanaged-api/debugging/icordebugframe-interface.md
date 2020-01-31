---
title: Интерфейс ICorDebugFrame
ms.date: 03/30/2017
api_name:
- ICorDebugFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame
helpviewer_keywords:
- ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 0c48f764-3c64-4602-b2f4-4ffc60eb2c65
topic_type:
- apiref
ms.openlocfilehash: ba138e79e0d6fb6f9c5e9c3efe3466f3c88cccae
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782624"
---
# <a name="icordebugframe-interface"></a>Интерфейс ICorDebugFrame

Представляет кадр текущего стека.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод CreateStepper](icordebugframe-createstepper-method.md)|Возвращает объект ICorDebugStepper для выполнения операций с заходом относительно этого `ICorDebugFrame`.|  
|[Метод GetCallee](icordebugframe-getcallee-method.md)|Возвращает указатель на `ICorDebugFrame` в текущей цепочке, вызвавшей этот кадр, или возвращает значение null, если это внутренняя рамка в цепочке.|  
|[Метод GetCaller](icordebugframe-getcaller-method.md)|Возвращает указатель на `ICorDebugFrame` в текущей цепочке, вызвавшей этот кадр, или возвращает значение null, если это внешняя рамка в цепочке.|  
|[Метод GetChain](icordebugframe-getchain-method.md)|Возвращает указатель на ICorDebugChain, частью которого является этот `ICorDebugFrame`.|  
|[Метод GetCode](icordebugframe-getcode-method.md)|Возвращает указатель на ICorDebugCode, связанный с этим кадром стека.|  
|[Метод GetFunction](icordebugframe-getfunction-method.md)|Возвращает указатель на ICorDebugFunction, содержащий код, связанный с этим кадром стека.|  
|[Метод GetFunctionToken](icordebugframe-getfunctiontoken-method.md)|Возвращает маркер метаданных для функции, которая содержит код, связанный с этим кадром стека.|  
|[Метод GetStackRange](icordebugframe-getstackrange-method.md)|Возвращает диапазон абсолютных адресов кадра стека, представленного данным `ICorDebugFrame`.|  
  
## <a name="remarks"></a>Заметки  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейсы отладки](debugging-interfaces.md)

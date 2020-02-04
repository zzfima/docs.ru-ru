---
title: Интерфейс ICorDebugProcess6
ms.date: 03/30/2017
ms.assetid: 34a10ac2-882c-4797-8369-f120e8e640c7
ms.openlocfilehash: 73ef1a64deaf5420246fc1ab3e9f88ba5bf049a5
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792236"
---
# <a name="icordebugprocess6-interface"></a>Интерфейс ICorDebugProcess6
Логически расширяет интерфейс ICorDebugProcess, чтобы включить такие функции как декодирование событий управляемой отладки, которые кодируются в события отладки собственных исключений и разделение виртуальных модулей.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод DecodeEvent](icordebugprocess6-decodeevent-method.md)|Декодирует события управляемой отладки, которые были инкапсулированы в полезную нагрузку из событий отладки специально созданных собственных исключений.|  
|[Метод EnableVirtualModuleSplitting](icordebugprocess6-enablevirtualmodulesplitting-method.md)|Позволяет включить или отключить разделение виртуальных модулей.|  
|[Метод GetCode](icordebugprocess6-getcode-method.md)|Получает информацию об управляемом коде по адресу определенного кода.|  
|[Метод GetExportStepInfo](icordebugprocess6-getexportstepinfo-method.md)|Предоставляет информацию о функциях, экспортируемых в ходе выполнения, для пошагового перемещения по управляемому коду.|  
|[Метод MarkDebuggerAttached](icordebugprocess6-markdebuggerattached-method.md)|Изменяет внутреннее состояние отлаживаемого кода таким образом, что метод <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> в библиотеке классов платформы .NET Framework возвращает `true`.|  
|[Метод ProcessStateChanged](icordebugprocess6-processstatechanged-method.md)|Уведомляет [ICorDebug](icordebug-interface.md) о том, что процесс выполняется.|  
  
## <a name="remarks"></a>Заметки  
  
> [!NOTE]
> Этот интерфейс доступен только в машинном коде .NET. Попытка вызова метода `QueryInterface` для получения указателя интерфейса возвращает `E_NOINTERFACE` для сценариев ICorDebug вне .NET Native.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)

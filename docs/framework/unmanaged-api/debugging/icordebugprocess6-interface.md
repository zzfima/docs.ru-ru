---
title: "Интерфейс ICorDebugProcess6"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 34a10ac2-882c-4797-8369-f120e8e640c7
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 222007d03d8ace00f97c01cf2a02f0dc293bbf78
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess6-interface"></a>Интерфейс ICorDebugProcess6
Логически расширяет интерфейс ICorDebugProcess, чтобы включить такие возможности как декодирование событий управляемой отладки, которые кодируются в события отладки собственных исключений и разделение виртуальных модулей.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md)|Декодирует события управляемой отладки, которые были инкапсулированы в полезную нагрузку из событий отладки специально созданных собственных исключений.|  
|[Метод EnableVirtualModuleSplitting](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-enablevirtualmodulesplitting-method.md)|Позволяет включить или отключить разделение виртуальных модулей.|  
|[Метод GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getcode-method.md)|Получает информацию об управляемом коде по адресу определенного кода.|  
|[Метод GetExportStepInfo](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md)|Предоставляет информацию о функциях, экспортируемых в ходе выполнения, для пошагового перемещения по управляемому коду.|  
|[Метод MarkDebuggerAttached](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-markdebuggerattached-method.md)|Изменяет внутреннее состояние отлаживаемого кода таким образом, что метод <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> в библиотеке классов платформы .NET Framework возвращает `true`.|  
|[Метод ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md)|Уведомляет [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) , на котором выполняется процесс.|  
  
## <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Этот интерфейс доступен только в машинном коде .NET. Попытка вызова метода `QueryInterface` для получения указателя интерфейса возвращает `E_NOINTERFACE` для сценариев ICorDebug вне .NET Native.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)

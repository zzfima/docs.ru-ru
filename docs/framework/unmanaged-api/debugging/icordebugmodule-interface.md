---
title: Интерфейс ICorDebugModule
ms.date: 03/30/2017
api_name:
- ICorDebugModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule
helpviewer_keywords:
- ICorDebugModule interface [.NET Framework debugging]
ms.assetid: 32e4d6fa-e5a3-413e-9166-d5e2871d3114
topic_type:
- apiref
ms.openlocfilehash: 971d6a6a2157c48dcb9105e9f523b1f077098479
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129489"
---
# <a name="icordebugmodule-interface"></a>Интерфейс ICorDebugModule

Представляет модуль среды CLR, который является либо исполняемым файлом, либо библиотекой динамической компоновки (DLL).  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод CreateBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-createbreakpoint-method.md)|Не реализовано.|  
|[Метод EnableClassLoadCallbacks](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-enableclassloadcallbacks-method.md)|Определяет, вызываются ли для этого модуля обратные вызовы [ICorDebugManagedCallback:: loadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) и [ICorDebugManagedCallback:: унлоадкласс](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) .|  
|[Метод EnableJITDebugging](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-enablejitdebugging-method.md)|Определяет, будет ли JIT-компилятор сохранить отладочную информацию для методов в этом модуле.|  
|[Метод GetAssembly](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getassembly-method.md)|Возвращает содержащуюся сборку для этого модуля.|  
|[Метод GetBaseAddress](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getbaseaddress-method.md)|Возвращает базовый адрес модуля.|  
|[Метод GetClassFromToken](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getclassfromtoken-method.md)|Возвращает ICorDebugClass из метаданных.|  
|[Метод GetEditAndContinueSnapshot](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-geteditandcontinuesnapshot-method.md)|Не рекомендуется.|  
|[Метод GetFunctionFromRVA](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getfunctionfromrva-method.md)|Не реализовано.|  
|[Метод GetFunctionFromToken](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getfunctionfromtoken-method.md)|Возвращает функцию, заданную маркером метаданных.|  
|[Метод GetGlobalVariableValue](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getglobalvariablevalue-method.md)|Возвращает объект значения для указанной глобальной переменной.|  
|[Метод GetMetaDataInterface](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getmetadatainterface-method.md)|Возвращает указатель интерфейса метаданных, который может использоваться для проверки метаданных модуля.|  
|[Метод GetName](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getname-method.md)|Возвращает имя файла модуля.|  
|[Метод GetProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getprocess-method.md)|Возвращает содержащий процесс для этого модуля.|  
|[Метод GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getsize-method.md)|Возвращает размер модуля в байтах.|  
|[Метод GetToken](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-gettoken-method.md)|Возвращает маркер для записи таблицы для этого модуля.|  
|[Метод IsDynamic](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-isdynamic-method.md)|Указывает, является ли модуль динамическим.|  
|[Метод IsInMemory](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-isinmemory-method.md)|Указывает, существует ли этот модуль только в памяти.|  
  
## <a name="remarks"></a>Заметки  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

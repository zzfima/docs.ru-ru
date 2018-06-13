---
title: ICorDebugModule интерфейс1
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: db4a980929a644d2862a382f147505644313da7b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422241"
---
# <a name="icordebugmodule-interface1"></a>ICorDebugModule интерфейс1
Представляет общий модуль среды выполнения (CLR) языка, который представляет исполняемого файла или библиотеки динамической компоновки (DLL).  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод CreateBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-createbreakpoint-method.md)|Не реализовано.|  
|[Метод EnableClassLoadCallbacks](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-enableclassloadcallbacks-method.md)|Определяет, является ли [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) и [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) , называются обратные вызовы для этого модуля.|  
|[Метод EnableJITDebugging](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-enablejitdebugging-method.md)|Определяет, сохраняет ли компилятор just-in-time (JIT), сведения об отладке для методов в этом модуле.|  
|[Метод GetAssembly](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getassembly-method.md)|Возвращает содержащей сборки для этого модуля.|  
|[Метод GetBaseAddress](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getbaseaddress-method.md)|Получает базовый адрес модуля.|  
|[Метод GetClassFromToken](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getclassfromtoken-method.md)|Возвращает ICorDebugClass из метаданных.|  
|[Метод GetEditAndContinueSnapshot](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-geteditandcontinuesnapshot-method.md)|Не рекомендуется.|  
|[Метод GetFunctionFromRVA](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getfunctionfromrva-method.md)|Не реализовано.|  
|[Метод GetFunctionFromToken](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getfunctionfromtoken-method.md)|Возвращает функцию, которая указывается токеном метаданных.|  
|[Метод GetGlobalVariableValue](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getglobalvariablevalue-method.md)|Возвращает объект значения для заданной глобальной переменной.|  
|[Метод GetMetaDataInterface](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getmetadatainterface-method.md)|Возвращает указатель на интерфейс метаданных, который может использоваться для просмотра метаданных для модуля.|  
|[Метод GetName](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getname-method.md)|Возвращает имя файла модуля.|  
|[Метод GetProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getprocess-method.md)|Получает процесс, содержащий для этого модуля.|  
|[Метод GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getsize-method.md)|Получает размер модуля в байтах.|  
|[Метод GetToken](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-gettoken-method.md)|Получает маркер для записи таблицы для этого модуля.|  
|[Метод IsDynamic](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-isdynamic-method.md)|Указывает, является ли динамический модуль.|  
|[Метод IsInMemory](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-isinmemory-method.md)|Указывает, существует ли этот модуль только в памяти.|  
  
## <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

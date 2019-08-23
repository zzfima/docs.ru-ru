---
title: Интерфейс ICorDebugProcess
ms.date: 03/30/2017
api_name:
- ICorDebugProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess
helpviewer_keywords:
- ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: be86f4b5-418a-4c5c-a67c-97148c65ed8c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b99630ba60cd84254024b91dba9ef9922fd7e041
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943302"
---
# <a name="icordebugprocess-interface"></a>Интерфейс ICorDebugProcess
Представляет процесс, выполняющий управляемый код. Этот интерфейс является подклассом ICorDebugController.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод ClearCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-clearcurrentexception-method.md)|Очищает текущее неуправляемое исключение для данного потока.|  
|[Метод EnableLogMessages](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enablelogmessages-method.md)|Включает и отключает отправку сообщений журнала отладчику.|  
|[Метод EnumerateAppDomains](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enumerateappdomains-method.md)|Перечисляет все домены приложений в процессе.|  
|[Метод EnumerateObjects](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enumerateobjects-method.md)|Не реализовано.|  
|[Метод GetHandle](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-gethandle-method.md)|Возвращает маркер процесса.|  
|[Метод GetHelperThreadID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-gethelperthreadid-method.md)|Возвращает идентификатор потока операционной системы (ОС) для внутреннего вспомогательного потока отладчика.|  
|[Метод GetID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md)|Возвращает идентификатор операционной системы (ОС) процесса.|  
|[Метод GetObject](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getobject-method.md)|Не реализовано.|  
|[Метод GetThread](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthread-method.md)|Возвращает экземпляр ICorDebugThread с указанным ИДЕНТИФИКАТОРом потока ОС.|  
|[Метод GetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthreadcontext-method.md)|Возвращает контекст для заданного потока.|  
|[Метод IsOSSuspended](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-isossuspended-method.md)|Определяет, был ли поток приостановлен в результате остановки процесса отладчиком.|  
|[Метод IsTransitionStub](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-istransitionstub-method.md)|Определяет, находится ли адрес в заглушке, что приведет к переходу в управляемый код.|  
|[Метод ModifyLogSwitch](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-modifylogswitch-method.md)|Задает уровень серьезности указанного переключателя журнала.|  
|[Метод ReadMemory](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-readmemory-method.md)|Считывает память из процесса.|  
|[Метод SetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-setthreadcontext-method.md)|Задает контекст для заданного потока.|  
|[Метод ThreadForFiberCookie](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-threadforfibercookie-method.md)|Не рекомендуется.|  
|[Метод WriteMemory](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-writememory-method.md)|Записывает данные в область памяти в процессе.|  
  
## <a name="remarks"></a>Примечания  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug. idl, CorDebug. h  
  
 **Библиотечная** Коргуидс. lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

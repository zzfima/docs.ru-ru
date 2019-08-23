---
title: Интерфейс ICorDebug
ms.date: 03/30/2017
api_name:
- ICorDebug
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug
helpviewer_keywords:
- ICorDebug interface [.NET Framework debugging]
ms.assetid: 33f431d7-ab1a-494d-8af2-20ab15aba194
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: afbf480d69e97662b5963706bb8c192aec0325a2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966297"
---
# <a name="icordebug-interface"></a>Интерфейс ICorDebug
Предоставляет методы, позволяющие разработчикам отлаживать приложения в среде среды CLR.  
  
> [!NOTE]
> Отладка в смешанном режиме (управляемый и машинный код) не поддерживается в Windows 95, Windows 98 или Windows ME или на платформах, отличных от x86 (например, IA64 и AMD64).  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод CanLaunchOrAttach](../../../../docs/framework/unmanaged-api/debugging/icordebug-canlaunchorattach-method.md)|Определяет, возможен ли запуск нового процесса или присоединение к данному процессу в контексте текущей конфигурации компьютера и среды выполнения.|  
|[Метод CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md)|Запускает процесс и его основной поток под управлением отладчика.|  
|[Метод DebugActiveProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md)|Присоединяет отладчик к существующему процессу.|  
|[Метод EnumerateProcesses](../../../../docs/framework/unmanaged-api/debugging/icordebug-enumerateprocesses-method.md)|Возвращает перечислитель для отлаживаемых процессов.|  
|[Метод GetProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-getprocess-method.md)|Возвращает объект "ICorDebugProcess" с заданным ИДЕНТИФИКАТОРом процесса.|  
|[Метод Initialize](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md)|Инициализирует `ICorDebug` объект.|  
|[Метод SetManagedHandler](../../../../docs/framework/unmanaged-api/debugging/icordebug-setmanagedhandler-method.md)|Указывает объект обработчика событий для управляемых событий.|  
|[Метод SetUnmanagedHandler](../../../../docs/framework/unmanaged-api/debugging/icordebug-setunmanagedhandler-method.md)|Указывает объект обработчика событий для неуправляемых событий.|  
|[Метод Terminate](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md)|`ICorDebug` Завершает объект.|  
  
## <a name="remarks"></a>Примечания  
 `ICorDebug`представляет цикл обработки событий для процесса отладчика. Перед освобождением этого интерфейса отладчик должен ожидать обратного вызова [ICorDebugManagedCallback:: ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) для всех отлаживаемых процессов.  
  
 `ICorDebug` Объект является начальным объектом для управления всеми дальнейшими управляемыми отладками. В .NET Framework версиях 1,0 и 1,1 этот объект был объектом, `CoClass` созданным из com. В .NET Framework версии 2,0 этот объект больше `CoClass` не является объектом. Она должна быть создана функцией [CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md) , которая поддерживает больше версий. Эта новая функция создания позволяет клиентам получить определенную реализацию `ICorDebug`, которая также эмулирует определенную версию API отладки.  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug. idl, CorDebug. h  
  
 **Библиотечная** Коргуидс. lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

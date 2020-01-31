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
ms.openlocfilehash: 0ca66f001d04bc86b64e0fe2d1cd37559e4fc633
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76785119"
---
# <a name="icordebug-interface"></a>Интерфейс ICorDebug
Предоставляет методы, позволяющие разработчикам отлаживать приложения в среде среды CLR.  
  
> [!NOTE]
> Отладка в смешанном режиме (управляемый и машинный код) не поддерживается в Windows 95, Windows 98 или Windows ME или на платформах, отличных от x86 (например, IA64 и AMD64).  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод CanLaunchOrAttach](icordebug-canlaunchorattach-method.md)|Определяет, возможен ли запуск нового процесса или присоединение к данному процессу в контексте текущей конфигурации компьютера и среды выполнения.|  
|[Метод CreateProcess](icordebug-createprocess-method.md)|Запускает процесс и его основной поток под управлением отладчика.|  
|[Метод DebugActiveProcess](icordebug-debugactiveprocess-method.md)|Присоединяет отладчик к существующему процессу.|  
|[Метод EnumerateProcesses](icordebug-enumerateprocesses-method.md)|Возвращает перечислитель для отлаживаемых процессов.|  
|[Метод GetProcess](icordebug-getprocess-method.md)|Возвращает объект "ICorDebugProcess" с заданным ИДЕНТИФИКАТОРом процесса.|  
|[Метод Initialize](icordebug-initialize-method.md)|Инициализирует объект `ICorDebug`.|  
|[Метод SetManagedHandler](icordebug-setmanagedhandler-method.md)|Указывает объект обработчика событий для управляемых событий.|  
|[Метод SetUnmanagedHandler](icordebug-setunmanagedhandler-method.md)|Указывает объект обработчика событий для неуправляемых событий.|  
|[Метод Terminate](icordebug-terminate-method.md)|Завершает объект `ICorDebug`.|  
  
## <a name="remarks"></a>Заметки  
 `ICorDebug` представляет цикл обработки событий для процесса отладчика. Перед освобождением этого интерфейса отладчик должен ожидать обратного вызова [ICorDebugManagedCallback:: ExitProcess](icordebugmanagedcallback-exitprocess-method.md) для всех отлаживаемых процессов.  
  
 Объект `ICorDebug` является начальным объектом для управления всеми дальнейшими управляемыми отладками. В .NET Framework версиях 1,0 и 1,1 этот объект был `CoClass` объектом, созданным из COM. В .NET Framework версии 2,0 этот объект больше не является объектом `CoClass`. Она должна быть создана функцией [CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md) , которая поддерживает больше версий. Эта новая функция создания позволяет клиентам получить определенную реализацию `ICorDebug`, которая также эмулирует определенную версию API отладки.  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейсы отладки](debugging-interfaces.md)

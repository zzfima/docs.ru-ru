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
ms.openlocfilehash: 193232ce1006a9cf209db9330343386404948440
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59168289"
---
# <a name="icordebug-interface"></a>Интерфейс ICorDebug
Предоставляет методы, позволяющие разработчикам отлаживать приложения в среде CLR (CLR).  
  
> [!NOTE]
>  Отладка в смешанном режиме (управляемый и машинный код) не поддерживается в Windows 95, Windows 98 или Windows ME или на платформах, отличных от — x86 (например, IA64 и AMD64).  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод CanLaunchOrAttach](../../../../docs/framework/unmanaged-api/debugging/icordebug-canlaunchorattach-method.md)|Определяет, возможна ли запуск нового процесса или вложение в данный процесс в контексте текущей конфигурации компьютера и среды выполнения.|  
|[Метод CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md)|Запускает процесс и основной поток под контролем отладчика.|  
|[Метод DebugActiveProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md)|Присоединяет отладчик к существующему процессу.|  
|[Метод EnumerateProcesses](../../../../docs/framework/unmanaged-api/debugging/icordebug-enumerateprocesses-method.md)|Получает перечислитель для отлаживаемых процессов.|  
|[Метод GetProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-getprocess-method.md)|Возвращает объект «ICorDebugProcess» с идентификатором указанного процесса.|  
|[Метод Initialize](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md)|Инициализирует `ICorDebug` объекта.|  
|[Метод SetManagedHandler](../../../../docs/framework/unmanaged-api/debugging/icordebug-setmanagedhandler-method.md)|Указывает объект обработчика событий для управляемых событий.|  
|[Метод SetUnmanagedHandler](../../../../docs/framework/unmanaged-api/debugging/icordebug-setunmanagedhandler-method.md)|Указывает объект обработчика событий для неуправляемых событий.|  
|[Метод Terminate](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md)|Завершает `ICorDebug` объекта.|  
  
## <a name="remarks"></a>Примечания  
 `ICorDebug` представляет цикл обработки событий для процесса отладчика. Отладчик должен ожидать [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) обратного вызова от всех процессов, отлаживаемых перед тем как освободить этот интерфейс.  
  
 `ICorDebug` Объект является исходный объект для управления все дополнительные управляемые отладки. В .NET Framework версий 1.0 и 1.1, этот объект был `CoClass` объект, созданный из COM. В .NET Framework версии 2.0, этот объект больше не `CoClass` объекта. Она должна быть создана путем [CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md) функцию, которая более следящее за версией. Эта новая функция создания позволяет клиентам получать реализации `ICorDebug`, которое также позволяет эмулировать определенную версию API отладки.  
  
> [!NOTE]
>  Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

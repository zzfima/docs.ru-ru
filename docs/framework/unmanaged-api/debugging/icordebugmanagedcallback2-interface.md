---
title: "Интерфейс ICorDebugManagedCallback2"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback2
helpviewer_keywords: ICorDebugManagedCallback2 interface [.NET Framework debugging]
ms.assetid: cf7b7cfa-1c4b-4d8c-be70-4f9ed15a788b
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0d5b8ac63d200e54d25b58870089f6c062397186
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmanagedcallback2-interface"></a>Интерфейс ICorDebugManagedCallback2
Предоставляет методы для поддержки обработки исключений отладчика и управляемых помощников по отладке (MDA). `ICorDebugManagedCallback2`является логическим расширением интерфейса [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) интерфейса.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод ChangeConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-changeconnection-method.md)|Уведомляет отладчик об изменении набора задач, связанных с заданным подключением.|  
|[Метод CreateConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-createconnection-method.md)|Уведомляет отладчик о том, создания нового соединения.|  
|[Метод DestroyConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-destroyconnection-method.md)|Уведомляет отладчик о том, что указанное соединение было прервано.|  
|[Метод исключений](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md)|Уведомляет отладчик о начале поиска для обработчика исключений.|  
|[Метод ExceptionUnwind](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exceptionunwind-method.md)|Предоставляет уведомление о состоянии во время процесса очистки исключения.|  
|[Метод FunctionRemapComplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapcomplete-method.md)|Уведомляет отладчик о том, что выполнение кода переключил до новой версии редактируемой функции.|  
|[Метод FunctionRemapOpportunity](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapopportunity-method.md)|Уведомляет отладчик о том, что выполнение кода достигнет точки последовательности в более старой версии редактируемой функции.|  
|[Метод MDANotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-mdanotification-method.md)|Предоставляет уведомление о том, что при выполнении кода было обнаружено сообщение управляемый помощник по отладке.|  
  
## <a name="remarks"></a>Примечания  
 `ICorDebugManagedCallback2` Расширяет интерфейс `ICorDebugManagedCallback` интерфейс для обработки новых событий отладки, представленных в .NET Framework версии 2.0.  
  
 Отладчик должен реализовать `ICorDebugManagedCallback2` при отладке приложений .NET Framework 2.0. Экземпляр `ICorDebugManagedCallback` или `ICorDebugManagedCallback2` передается как объект обратного вызова для [ICorDebug::SetManagedHandler](../../../../docs/framework/unmanaged-api/debugging/icordebug-setmanagedhandler-method.md).  
  
> [!NOTE]
>  Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Диагностика ошибок посредством помощников по отладке управляемого кода](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [ICorDebugManagedCallback-интерфейс](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
